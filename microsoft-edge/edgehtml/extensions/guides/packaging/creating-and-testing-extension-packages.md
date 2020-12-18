---
ms.assetid: 5eefa3d8-8626-4486-bd90-1361400d6468
description: Microsoft Edge 拡張機能を手動でパッケージ化し、正しくパッケージ化されていないかテストする方法について説明します。
title: 拡張機能パッケージの作成とテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者, パッケージ化
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 44316f4dd47b3b6b26014ff24673ddfd16a72ddb
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234936"
---
# Microsoft Edge 拡張機能 AppX パッケージの作成とテスト  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

Microsoft Edge 拡張機能は、ユニバーサル Windows アプリのパッケージ化と同様に、AppX としてパッケージ化されます。 Windows 10 Anniversary Update では、AppX 用に新しいスキーマが導入され、AppX に Microsoft Edge 拡張機能をコンテンツとして含めさせることができます。

Microsoft Edge 拡張機能の AppX の作成方法が既にわかっている場合は [、「ExtensionJS](./using-manifoldjs-to-package-extensions.md) を使って拡張機能をパッケージ化する」にスキップして、Node.js ベースのツールを使ってこのすべての手順を実行する方法について説明します。

> [!NOTE]
> Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。 拡張機能を作成、パッケージ化、テストしたら、拡張機能の提出フォームで要求 [を送信してください](https://aka.ms/extension-request)。

## 提出フォルダーの準備

提出用に拡張機能を準備するには、次の構造のフォルダーを作成する必要があります。

![フォルダー構造のイメージ。 [マイ拡張機能] フォルダー内にAppxManifest.xml、拡張フォルダー、および Assets フォルダーがあります。](./../../media/packaging_folder-structure.png)

フォルダーのルートに、新しいファイルをAppXManifest.xmlがあります。 このファイルは、パッケージの内容とレイアウトを指定するために使用されます。

また、Microsoft Store で使用する UI アセットを含む Assets フォルダーと、拡張機能のファイル (スクリプト、アイコンなど) を含む拡張フォルダーも必要です。

> [!IMPORTANT]
> パッケージ用に別のフォルダー構造を作成できますが、フォルダー構造は AppXManifest の値と一致している必要があります。

### AppXManifest.xml
AppXManifest ファイルは、システムが Windows アプリを展開、表示、または更新するために必要な情報を含む XML ドキュメントです。 このファイルには、パッケージ ID、機能、ビジュアル要素も含まれています。 すべてのアプリ パッケージには、1 つの AppXManifest ファイルを含める必要があります。

開発者は、次のテンプレートを使用してファイルAppXManifest.xmlできます。

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

#### アプリ ID テンプレートの値
Windows デベロッパー[](./extensions-in-the-windows-dev-center.md#name-reservation)センターで拡張機能の名前を予約すると、次の値を置き換えるのに必要なパッケージ ID 情報を検索AppXManifest.xml。

-   `Name`
-   `Publisher`
-   `DisplayName`
-   `PublisherDisplayName`

次の手順を使用して、アプリ ID ページにアクセスできます。

1.  Windows デベロッパー [センターに移動します](https://developer.microsoft.com/windows/)。
2.  開発者アカウントにサインインします。
3.  ダッシュボードに移動します。
4.  拡張機能の名前を選択します。
    
    ![拡張リスト](./../../media/select-app.png)
    
5.  アプリの管理セクションの下にある [アプリ ID] ページに移動します (アプリを登録した後)。
    
    ![アプリ ID ページ](./../../media/app-identity.png)
    
これで、次のように、AppXManifest テンプレートにアプリ ID ページの値を設定できます。

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

#### JSON マニフェスト テンプレートの値
AppXManifest の一部の値は、JSON マニフェストで定義されている値と一致する必要があります。 拡張機能の JSON マニフェストに基づいてappxmanifest.xmlの値を更新してください。

-   `Version` - これは拡張機能の JSON マニフェストに一覧表示されているバージョンです。 文字列は、最後の整数が 0 である必要がある X.X.X.X.X 形式と一致する必要があります。 例: 1.2.3.0
    
    ```xml
    <Identity
         Name="37369abigailc.MyExtension"
         Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
         Version="1.0.0.0" />
    ```  
    
-   `Description` - これは拡張機能の JSON マニフェスト内の説明のコピーです。
    
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
    
### Assets フォルダー

Assets フォルダー内には、3 つの異なるアイコン サイズが必要です。 これらのアイコンは、Microsoft Store と Windows UI で使います。 これらのアイコンについて詳しくは、デザイン ガイドをご [覧](./../design.md#icons-for-packaging) ください。

![assets フォルダーに 3 つのアイコン サイズがある](./../../media/assets-folder.png)

必要な UI アセットを作成したら、次のAppXManifest.xmlをポイントして更新します。

-   44 x 44
    
    ```xml
    Square44x44Logo="Assets/icon_44.png"
    ```  
    
-   50x50
    
    ```xml
    <Logo>Assets/icon_50.png</Logo>
    ```  
    
-   150 x 150
    
    ```xml
    Square150x150Logo="Assets/icon_150.png"
    ```  
    
### 拡張フォルダー
(フォルダー構造を維持する) 拡張子ファイルを拡張フォルダーにコピーします。 ルートに `manifest.json` Extension フォルダーが設定されている必要があります。

![すべての拡張子ファイルを含む拡張フォルダー](./../../media/extension-folder.png)

### 複数のロケールのサポート
拡張機能が複数の言語をサポートしている場合は、適切なローカライズされたアイコンと説明が Microsoft Store に表示されるのに必要なすべてのロケールで AppX パッケージを構成できます。 詳細 [については、「拡張機能パッケージのローカライズ](./localizing-extension-packages.md) 」を参照してください。

### Appx の作成

Appx を作成するには、makeappx のパスを見つける必要があります。 これは通常、64 ビット コンピューターを使用している場合は、次の場所に位置します。

`C:\Program Files (x86)\Windows Kits\10\bin\x64`

次のコマンドを実行して、拡張機能の AppX パッケージを作成します。

`[Path to makeappx] makeappx pack /h SHA256 /d [Path to package folder created in #1] /p [Path to the appx file that you want to create]`

パスを入力すると、次のように表示されます。

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe pack /h SHA256 /d "C:\Extension\My Extension" /p C:\Extension\MyExtension.appx`

### Appx のアンパック
以前に生成された AppX を展開して、拡張機能の次の反復の開始点として使用したり、AppX が正しく作成されていることを確認したりすることもできます。

これを行うには、次のコマンドを実行して、Microsoft Edge 拡張機能の AppX パッケージを展開します。

```shell
[Path to makeappx] makeappx unpack /v /p [Path to appx file you want to unpack] /d [Path to the location where you want to create the package folder]
```  

入力すると、次のように表示されます。

```text
C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe unpack /v /p "C:\Extension\MyExtension.appx" /d "C:\Extension\My Extension"
```  

## AppX パッケージのテスト

Microsoft Edge 拡張機能 AppX パッケージは、Microsoft Edge でサイドロードすることでテストできます。 拡張 AppX パッケージのサイドローディングは、ユニバーサル Windows アプリのサイドローディングに似ています。 パッケージに署名する証明書を作成し、パッケージを Windows に追加する必要があります。

### 署名

パッケージ [の署名と認定](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx) プロセスについて詳しくは、アプリ パッケージ署名証明書を作成する方法と [SignTool](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx) を使ってアプリ パッケージに署名する方法をご覧ください。

> [!NOTE]
> Microsoft Store に提出する前に、拡張機能パッケージに署名する必要があります。ストアの取り込みプロセスで処理されます。

作成した証明書でパッケージに署名した後も、ローカル コンピューターの信頼された証明書ストアにインストールするまで、アプリ パッケージの展開に関して証明書はローカル コンピューターによって信頼されません。 Windows に付属Certutil.exeを使用してこれを行います。

WindowsCertutil.exe証明書をインストールCmd.exe管理者として実行し、次のコマンドを実行します。

```shell
Certutil -addStore TrustedPeople MyKey.cer
```  

証明書が使用されなくなったら、管理者のコマンド プロンプトから次のコマンドを実行して、証明書を削除するようお勧めします。

```shell
Certutil -delStore TrustedPeople certID
```  

certID は証明書のシリアル番号です。 証明書のシリアル番号を確認するには、次のコマンドを実行します。

```shell
Certutil -store TrustedPeople
```  

### 展開
PowerShell で (管理者として) 次のコマンドを実行すると、Microsoft Edge Extension AppX パッケージを展開できます。

```powershell
Add-AppxPackage [path to AppX]
```  

## WebDriver を使用した自動テスト

Anniversary Update では、WebDriver を使用して Microsoft Edge の拡張機能をプログラムでサイドロードして、Microsoft Edge を WebDriver モードで起動するときに拡張機能の自動テストを有効にできます。 これにより、ページ上のコンテンツを操作する拡張機能の自動テストを設定し、正しい動作が表示されていることを確認できます。

自動テスト用に拡張機能をサイドロードするには、拡張機能のフォルダーを下に保存する必要があります `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\` 。 拡張機能がディレクトリに入った後、オブジェクトを作成し、そのオブジェクトに `LocalState` [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) 機能を追加する `extensionPaths` 必要があります。 この機能の値は、Microsoft Edge が WebDriver モードで起動するときにサイドロードする拡張機能 (ディレクトリ内) への絶対パス `LocalState` の配列です。

WebDriver を使用して Microsoft Edge で拡張機能をサイドローディングする完全なサンプルについては、次の [C#](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs) ファイルを参照してください。
