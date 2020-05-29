---
ms.assetid: 5eefa3d8-8626-4486-bd90-1361400d6468
description: Microsoft Edge 拡張機能を手動でパッケージ化して、正しくパッケージされているかどうかをテストする方法について説明します。
title: 拡張パッケージの作成とテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、パッケージ
ms.custom: seodec18
ms.openlocfilehash: a76737d76c8f08c8e79992f0804fdbd34d4ed970
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569450"
---
# Microsoft Edge 拡張機能 AppX パッケージの作成とテスト  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

Microsoft Edge extensions は、ユニバーサル Windows アプリのパッケージの場合と同様に、AppX としてパッケージ化されています。 Windows 10 記念日更新時には、appx に対して新しいスキーマが導入され、appx に Microsoft Edge extension をコンテンツとして含めることができます。

Microsoft Edge extension AppXs の作成方法がわかっている場合は、「 [ManifoldJS を使って拡張子をパッケージ化する](./using-manifoldjs-to-package-extensions.md)」を参照してください。これを行うには、node.js ベースのツールを使用する方法について説明しています。

> [!NOTE]
> Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。 お客様の内線番号の作成、パッケージ化、テストが完了したら、[延長申請フォーム](https://aka.ms/extension-request)でリクエストを送信してください。



## 申請フォルダーの準備

申請のために拡張機能を準備するには、次の構造のフォルダーを作成する必要があります。

![フォルダー構造の画像。 [My Extension folder] の内部には、Package.appxmanifest、Extension folder、および Assets フォルダーがあります。](./../../media/packaging_folder-structure.png)

フォルダーのルートに、Package.appxmanifest ファイルを含める必要があります。 このファイルは、パッケージのコンテンツとレイアウトを指定するために使われます。

また、Microsoft Store で使用される UI アセットを含む [アセット] フォルダーと、拡張機能のファイル (スクリプト、アイコンなど) が含まれる拡張フォルダーも用意しておく必要があります。

> [!IMPORTANT]
> パッケージ用の別のフォルダー構造を作成することはできますが、フォルダー構造は Package.appxmanifest 値と一致する必要があります。

### Package.appxmanifest
Package.appxmanifest ファイルは、Windows アプリを展開、表示、または更新するためにシステムが必要とする情報が含まれている XML ドキュメントです。 このファイルには、パッケージ id、機能、およびビジュアル要素も含まれます。 すべてのアプリパッケージには、1つの Package.appxmanifest ファイルが含まれている必要があります。

開発者は、Package.appxmanifest ファイルに次のテンプレートを使うことができます。

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
  xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
  xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
  xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
  IgnorableNamespaces="uap3">

  <Identity
    Name="[REPLACE WITH PACKAGE/IDENTITYNAME]"
    Publisher="[REPLACE WITH PACKAGE/IDENTITY/PUBLISHER]"
    Version="[REPLACE WITH PACKAGE VERSION in the form X.X.X.0]"/>

  <Properties>
    <DisplayName>[REPLACE WITH RESERVED STORE NAME]</DisplayName>
    <PublisherDisplayName>[REPLACE WITH PACKAGE/PROPERTIES/PUBLISHERDISPLAYNAME]</PublisherDisplayName>
    <Logo>[REPLACE WITH RELATIVE PATH TO 50x50 ICON]</Logo>
  </Properties>

  <Dependencies>
    <TargetDeviceFamily Name="Windows.Desktop"
      MinVersion="10.0.14393.0"
      MaxVersionTested="10.0.14800.0" />
  </Dependencies>

  <Resources>
    <Resource Language="en-us"/>
  </Resources>

  <Applications>
    <Application Id="App">
      <uap:VisualElements
        AppListEntry="none"
        DisplayName="[REPLACE WITH RESERVED STORE NAME]"
        Square150x150Logo="[REPLACE WITH RELATIVE PATH TO 150x150 ICON]"
        Square44x44Logo="[REPLACE WITH RELATIVE PATH TO 44x44 ICON]"
        Description="This is the description of the extension"
        BackgroundColor="white">
      </uap:VisualElements>
    <Extensions>
    <uap3:Extension Category="windows.appExtension">
    <uap3:AppExtension Name="com.microsoft.edge.extension"
        Id="EdgeExtension"
        PublicFolder="Extension"
      DisplayName="[REPLACE WITH RESERVED STORE NAME]">
    </uap3:AppExtension>
    </uap3:Extension>
    </Extensions>
 </Application>
</Applications>
</Package>
```

#### アプリ id テンプレートの値
Windows デベロッパーセンターを通じて[拡張機能の名前を予約](./extensions-in-the-windows-dev-center.md#name-reservation)すると、package.appxmanifest で次の値を置き換えるために必要なパッケージ id 情報を見つけることができます。

- `Name`
- `Publisher`
- `DisplayName`
- `PublisherDisplayName`

[アプリ id] ページにアクセスするには、次の手順を実行します。

1. [Windows デベロッパーセンター](https://developer.microsoft.com/windows/)に移動します。
2. 開発者アカウントにサインインします。
3. ダッシュボードに移動します。
4. 拡張機能の名前を選択します。

   ![内線番号リスト](./../../media/select-app.png)
5. アプリを登録した後、[アプリの管理] セクションの下にある [アプリ id] ページに移動します。

   ![アプリ id ページ](./../../media/app-identity.png)


テンプレートに示されているように、[アプリ id] ページから値を Package.appxmanifest テンプレートに設定できるようになりました。


```xml
<Identity
  Name="37369abigailc.MyExtension"
  Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
  Version="[REPLACE WITH PACKAGE VERSION in the form X.X.X.0]" />

<Properties>
  <DisplayName>My Extension</DisplayName>
  <PublisherDisplayName>abigailc</PublisherDisplayName>
  <Logo>[REPLACE WITH RELATIVE PATH TO 50x50 ICON]</Logo>
</Properties>
```

#### JSON マニフェストのテンプレート値
Package.appxmanifest の一部の値は、JSON マニフェストで定義されている値と一致する必要があります。 拡張機能の JSON マニフェストに基づいて、package.appxmanifest 内の次の値を更新してください。

- `Version` -これは、拡張機能の JSON マニフェストに記載されているバージョンです。 文字列は、最後の整数が0になるように、x.x.x.x の形式と一致する必要があります。 例: 1.2.3.0

   ```xml
   <Identity
     Name="37369abigailc.MyExtension"
     Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
     Version="1.0.0.0" />
   ```

- `Description` -これは、拡張機能の JSON マニフェストの説明のコピーです。

  ```xml
  <uap:VisualElements
    AppListEntry="none"
    DisplayName="My Extension"
    Square150x150Logo="[REPLACE WITH RELATIVE PATH TO 150x150 ICON]"
    Square44x44Logo="[REPLACE WITH RELATIVE PATH TO 44x44 ICON]"
    Description="This extension will allow you to quickly print by clicking the browser action."
    BackgroundColor="white">
  </uap:VisualElements>
  ```


### 資産フォルダー

[アセット] フォルダーでは、3つの異なるアイコンサイズが必要です。 これらのアイコンは、Microsoft ストアと Windows UI で使用されます。 これらのアイコンの詳細については、[デザイン](./../design.md#icons-for-packaging)ガイドを参照してください。

![3つのアイコンサイズがある [アセット] フォルダー](./../../media/assets-folder.png)

必要な UI アセットを作成したら、Package.appxmanifest を更新して適切なファイルをポイントします。

- 44 x 44

   ```xml
   Square44x44Logo="Assets/icon_44.png"
   ```

- 場合は

  ```xml
   <Logo>Assets/icon_50.png</Logo>
  ```

- 150 x 150

  ```xml
  Square150x150Logo="Assets/icon_150.png"
  ```


### 拡張機能フォルダー
拡張機能ファイル (フォルダー構造の保持) を拡張機能フォルダーにコピーします。 `manifest.json`[Extension folder] のルートにあることを確認します。

![すべての拡張ファイルが含まれる extension フォルダー](./../../media/extension-folder.png)


### 複数のロケールのサポート
拡張機能が複数の言語をサポートしている場合は、必要なすべてのロケールを使用して AppX パッケージを構成し、Microsoft Store で適切にローカライズされたアイコンと説明を表示することができます。 詳細については、「[ローカライズ拡張機能パッケージ](./localizing-extension-packages.md)」を参照してください。

### Appx の作成

Appx を作成するには、makeappx のパスを見つける必要があります。 これは通常、64ビットコンピューターを使用している場合に、次の場所にあります。

`C:\Program Files (x86)\Windows Kits\10\bin\x64`

拡張機能の AppX パッケージを作成するには、次のコマンドを実行します。

`[Path to makeappx] makeappx pack /h SHA256 /d [Path to package folder created in #1] /p [Path to the appx file that you want to create]`

パスの入力が完了すると、次のようになります。

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe pack /h SHA256 /d "C:\Extension\My Extension" /p C:\Extension\MyExtension.appx`

### Appx を展開する
以前に生成された AppX を展開して、延長の次のイテレーションの出発点として使用したり、AppX が正しく作成されたことを確認したりすることができます。

これを行うには、次のコマンドを実行して、Microsoft Edge 拡張機能の AppX パッケージをアンパックします。

`[Path to makeappx] makeappx unpack /v /p [Path to appx file you want to unpack] /d [Path to the location where you want to create the package folder]`

入力した内容は、次のようになります。

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe unpack /v /p "C:\Extension\MyExtension.appx" /d "C:\Extension\My Extension"`





## AppX パッケージのテスト

Microsoft edge 拡張機能 AppX パッケージは、Microsoft Edge でサイドローディングしてテストできます。 サイドローディング拡張 AppX パッケージは、ユニバーサル Windows アプリのサイドローディングと似ています。 パッケージに署名するための証明書を作成し、Windows にパッケージを追加する必要があります。

### 付き

パッケージの署名と認定プロセスの詳細については、「[アプリパッケージ署名証明書を作成する方法](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx)と、 [SignTool を使ってアプリパッケージに署名する](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx)方法」を参照してください。

> [!NOTE]
> Microsoft Store に提出する前に、拡張パッケージに署名する必要はありません。ストア取り込みプロセスは、お客に対応しています。

作成した証明書を使用してパッケージに署名した後も、ローカルコンピューターの信頼された証明書ストアにインストールするまでは、アプリパッケージの展開については、その証明書はローカルコンピューターによって信頼されません。 この操作を行うには、Windows に付属している Certutil を使用できます。

WindowsCertutil で証明書をインストールするには、管理者として Cmd.exe を実行し、次のコマンドを実行します。

`Certutil -addStore TrustedPeople MyKey.cer`

証明書が使用されなくなったら、管理者のコマンドプロンプトから次のコマンドを実行して、証明書を削除することをお勧めします。

`Certutil -delStore TrustedPeople certID`

CertID は、証明書のシリアル番号です。 証明書のシリアル番号を確認するには、次のコマンドを実行します。

`Certutil -store TrustedPeople`

### 展開
Microsoft Edge 拡張機能 AppX パッケージを展開するには、PowerShell で次のコマンドを実行します (管理者として)。

`Add-AppxPackage [path to AppX]`

## WebDriver を使った自動テスト

お客様は、お客様が Microsoft edge を webdriver モードで起動したときに自動的に拡張テストを行うことができます。 これにより、ページ上のコンテンツを操作するすべての拡張機能の自動テストを設定し、適切な動作が行われていることを確認できます。

自動テストのために拡張機能をサイドローディングには、の下に拡張機能のフォルダーを保存する必要があり `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\` ます。 拡張機能がディレクトリ内にある場合は、 `LocalState` オブジェクトを作成して機能を追加する必要があり [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) `extensionPaths` ます。 この機能の値は、 `LocalState` Microsoft Edge が WebDriver モードで開始されたときに、サイドローディングを行う必要がある拡張子 (ディレクトリ内) への絶対パスの配列です。

WebDriver を使った Microsoft Edge のサイドローディング拡張機能の完全なサンプルについては、次の[C# ファイル](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs)を確認してください。
