---
ms.assetid: c4043c1e-15ac-4210-8851-3804c7708f49
description: Microsoft Edge 拡張機能パッケージをローカライズして、リリース時に複数のロケールで使えるようにする方法について説明します。
title: 拡張パッケージのローカライズ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: a6a920b80e915bb14c7ea24abcc54105e5b34eb0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569445"
---
# Microsoft Edge extensions for Windows と Microsoft Store のローカライズ  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

このガイドでは、Microsoft Edge 拡張機能をローカライズして、リリース時に複数のロケールが使えるようにする方法について説明します。 内線番号を完全にローカライズするには、Windows と Microsoft ストアの両方の手順を実行する必要があります。

Microsoft Edge の拡張機能リソースをローカライズする場合は、[国際化ガイド](../internationalization.md)で i18n フレームワークを使用する方法を学習できます。


> [!NOTE]
> 拡張機能で複数の言語がサポートされていない場合は、「 [Microsoft Store での名前と説明のローカライズ」](#localizing-name-and-description-in-the-microsoft-store)に進んでください。


## ローカライズプロセスの概要

内線番号を多くのユーザーが利用できるようにするための最初のステップとして、複数の言語に対応するように[package.appxmanifest を設定](#configuring-the-appxmanifest)します。 Microsoft ストアでは、拡張機能でサポートされている言語がユーザーに表示されます。 拡張子の名前を[WINDOWS UI と Microsoft Store でローカライズ](#localizing-extension-resources-for-windows-and-the-microsoft-store)する場合は、package.appxmanifest 内の特定のフィールドも変更する必要があります。


Package.appxmanifest を構成したら、サポート対象として指定した言語の[JSON 文字列リソースを作成](#creating-json-string-resources)する必要があります。 そのためには、各言語の resjson ファイルを作成する必要があります。この場合、各ファイルには、その言語に含まれるすべての UI 文字列が含まれます。


サポートされている言語の resjson ファイルが作成されたら、 [pri リソースファイルを作成する必要があり](#creating-the-resources-file)ます。 これは、 [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)に付属の**makepri**ツールへの構成ファイルを使用して作成されます。 

> [!NOTE]
> MakePri ツールを使用するために Windows 10 SDK をダウンロードするだけの場合は、"デスクトップアプリ用 Windows SDK 署名ツール" および "Windows SDK for UWP マネージアプリ" の機能のみを選択して、ダウンロードを軽量にすることができます。 MakePri ツールは、C:\Program Files (x86) \Windows Kits\10\bin\10.0.17713.0. のサブフォルダーに表示されます。


拡張機能をアップロードしたら、最後の手順として、 [Microsoft ストアで名前と説明をローカライズ](#localizing-name-and-description-in-the-microsoft-store)します。

> [!NOTE]
> Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。 Microsoft Store の一部として要求が送信された場合は、skype[に](https://aka.ms/extension-request)連絡して、将来の更新についてご検討ください。



## Package.appxmanifest を構成する

Microsoft Store の拡張子 "サポートされている言語" リストは、Package.appxmanifest の値に基づいて生成されます。 この一覧は、要素を使って指定し `Resource` ます。


![設定のイメージ](./../../media/language-app-details.png)

内線番号でサポートされている言語のリストを指定するには、 `Resource` 次に示す形式で要素を追加します (こ `Resource` の要素は、Microsoft Store での英語、ドイツ語、フランス語のサポートを示します)。

```xml
<Resources>
    <Resource Language="en-us"/>
    <Resource Language="de-de"/>
    <Resource Language="fr-fr"/>
</Resources>
```

Microsoft Store でサポートされている言語または言語コードの詳細については、「[サポートされる言語](https://msdn.microsoft.com/windows/uwp/publish/supported-languages)」を参照してください。


Package.appxmanifest でパブリックに表示されるすべての要素にローカライズされた文字列を指定するには、の形式でリソース識別子を使う必要があり `ms-resource:<resource id>` ます。

以下のスニペットでは、完全な Package.appxmanifest を作成しています。 ローカライズされたリソースファイルから次の値を取得する必要があります。

- Properties\DisplayName
- Properties\Description
- Properties\PublisherDisplayName


```xml
<Properties>
    <DisplayName>ms-resource:DisplayName</DisplayName>
    <Description>ms-resource:Description</Description>
    <Logo>Assets\PackageLogo.png</Logo>
    <PublisherDisplayName>ms-resource:PublisherName</PublisherDisplayName>
</Properties>
```

- Application\ Application\ visualelement¥ DisplayName
- Application\ Application\ visualelementの説明
- Applications\Application\Extensions\Extension\AppExtension\DisplayName

```xml
<Applications>
    <Application Id="App">
      <uap:VisualElements
        AppListEntry="none"
            DisplayName="ms-resource:DisplayName"
       Square150x150Logo="Assets\Square150x150Logo.png"
       Square44x44Logo="Assets\Square44x44Logo.png"
            Description="ms-resource:Description"
        BackgroundColor="transparent">
      </uap:VisualElements>
      <Extensions>
      <uap3:Extension Category="windows.appExtension">
        <uap3:AppExtension Name="com.microsoft.edge.extension"
            Id="MicrosoftTranslate"
            PublicFolder="Extension"
            DisplayName="ms-resource:DisplayName">
        </uap3:AppExtension>
      </uap3:Extension>
      </Extensions>
    </Application>
  </Applications>
```


## Windows と Microsoft ストアの拡張リソースのローカライズ

Package.appxmanifest が複数の言語に対応するように構成されたため、拡張機能での UI のローカライズと、Windows および Microsoft ストアの拡張機能のローカライズの間に知っておく必要がある主な違いがいくつかあります。

Microsoft edge extensions は Microsoft Edge の外部では実行されませんが、Windows 内で管理することができます。 たとえば、ユーザーは設定アプリで自分の拡張子を管理することができます。


![設定のイメージ](./../../media/settings.png)



Windows の設定アプリで表示される拡張機能の名前は、Package.appxmanifest から取得されます。 この値が英語でハードコードされている場合は、英語以外の Windows デバイスでは英語版の名前が表示されます。 拡張機能のブランドが英語のみの場合は、ハードコーディングしたままにしても問題ありません。


> [!NOTE]
> Windows で Microsoft Edge 拡張機能のローカライズされた名前を使用する場合は、Package.appxmanifest ファイルで変更を行う前に、ローカライズされた名前も[使用可能で、予約済み](./extensions-in-the-windows-dev-center.md#name-reservation)であることを確認してください。 名前が予約されていない場合は、Windows デベロッパーセンターに最終的なパッケージをアップロードすると、次のエラーメッセージが表示されます。</br></br>

![言語エラー](./../../media/language-error.png)</br></br>


JavaScript 拡張機能に対して定義されている i18n ベースのローカライズインフラストラクチャは、Microsoft Edge 環境内でのみ適用されます。

Microsoft Edge 以外の Windows と Microsoft Store では、サポートされているローカライズフレームワークはユニバーサル Windows プラットフォーム (UWP) のローカライズフレームワークに基づいています。

HTML ベースの Windows アプリでは、JSON ベースのリソースをサポートしていますが、JSON リソースのスキーマは JavaScript 拡張機能に対して定義されているものと一致しません。


[HTML ベースの Windows アプリ](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx)では、次の主な違いがあります。
-    リソースは、json ファイルではなく、resjson ファイルで指定されます。
-    サポートされるロケールは、最初のロケールが既定のロケールである Package.appxmanifest ファイルで指定する必要があります。
-    HTML ベースの Windows アプリのリソースでは、次のスキーマが使用されます。
    ```json
    {
        "greeting"              : "Hello",
        "_greeting.comment"     : "A welcome greeting.",

        "farewell"              : "Goodbye",
        "_farewell.comment"     : "A goodbye."
    }
    ```
    アンダースコアで示されている名前と値のペアは、対応する文字列リソースに対してコメントとなります。
-    resjson ファイルは、AppX パッケージの作成時に含める必要がある .pri ファイルにコンパイルされます。


### JSON 文字列リソースの作成
構成済みの Package.appxmanifest と、国際化と UWP のローカライズフレームワークの違いが強調表示されているので、リソースファイルを作成することができます。

マニフェストでは、Microsoft Edge 拡張機能パッケージに適用できるリソース文字列は1つだけです。 この `DisplayName` 文字列は、一般的に JavaScript 拡張機能でローカライズされ、Windows で想定される resjson ファイルに簡単にマッピングできます。 ローカライズする唯一のリソースであると仮定します。ここでは、作成する必要がある resjson ファイルの例を示します。

```json
{
    "DisplayName"              : "Jigsaw",
    "_DisplayName.comment"     : "Name of extension."
}
```

各 resjson ファイルのリソース ID は、Package.appxmanifest で使用されている ID と一致する必要があります。 上の例の resjson スニペットを使って、対応する Package.appxmanifest エントリは次のようになります。

`DisplayName="ms-resource:DisplayName"`

拡張機能でサポートされている各言語には、対応するリソース. resjson ファイルがあり、次のフォルダー構造に配置されている必要があります。

![言語フォルダー構造](./../../media/resources-folder.png)


### リソースファイルの作成
すべての resjson ファイルを作成したら、パッケージリソースインデックス (PRI) ファイルを作成することができます。 このファイルには、サポートされているすべての言語のリソースが保存されます。 これを行うには、Windows 10 SDK に含まれている**Makepri**ツールを使用できます。


まず、構成ファイルを作成する必要があります。 これにより、リソースの既定の修飾子とプラットフォームが定義されます。 この例では、既定の言語である英語 (米国) とプラットフォームの Windows 10 を作成します。 これを行うには、[ルートフォルダー] に次のコンテンツを含む priconfig.xml ファイルを作成します。

![フォルダー内の priconfig.xml](./../../media/priconfig.png)


```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<resources targetOsVersion="10.0.0" majorVersion="1">
    <index root="\" startIndexAt="\">
        <default>
            <qualifier name="Language" value="en-US"/>
            <qualifier name="Contrast" value="standard"/>
            <qualifier name="HomeRegion" value="001"/>
            <qualifier name="TargetSize" value="256"/>
            <qualifier name="LayoutDirection" value="LTR"/>
            <qualifier name="Theme" value="dark"/>
            <qualifier name="AlternateForm" value=""/>
            <qualifier name="DXFeatureLevel" value="DX9"/>
            <qualifier name="Configuration" value=""/>
            <qualifier name="DeviceFamily" value="Universal"/>
            <qualifier name="Custom" value=""/>
        </default>
        <indexer-config type="folder" foldernameAsQualifier="true" filenameAsQualifier="true" qualifierDelimiter="."/>
        <indexer-config type="resw" convertDotsToSlashes="true" initialPath=""/>
        <indexer-config type="resjson" initialPath=""/>
        <indexer-config type="PRI"/>
    </index>
</resources>
```

これで、構成ファイルと MakePRI ツールを使って、リソースの pri ファイルを作成できるようになりました。 この例では、プロジェクトのルートの場所は [ルートフォルダー] になります。


```cmd
MakePRI new /pr [Root folder] /cf [Root folder]\priconfig.xml /mn [Root folder]\AppxManifest.xml /of [Root folder]\resources.pri /o
```

これで、ルートフォルダに1つのリソース pri ファイルが表示されます。

![リソースフォルダー](./../../media/resources.png)


## Microsoft Store での名前と説明のローカライズ

ローカライズされた完全なパッケージをアップロードしようとすると、Windows デベロッパーセンターは、複数の言語がサポートされていることを検出し、それぞれに対応するローカライズされた名前と説明を確認します。 ローカライズされた値が見つからない場合は、値を提供するまで、申請はブロックされます。

(Windows ではなく) Microsoft ストアのローカライズされた名前と説明だけが必要な場合は、[拡張機能のローカライズ](./extensions-in-the-windows-dev-center.md#name-reservation)された名前をすべて予約してください。


追加のローカライズされた名前を予約すると、更新された申請を作成できます。 [説明] セクションでは、Microsoft ストア登録情報の追加言語を管理できます。

![日本語アプリの説明](./../../media/manage-description-languages.png)

[追加言語の管理] を選択すると、Microsoft ストアの登録情報に追加する言語を選ぶことができます。 新しい言語は、「説明」セクションに「その他の説明言語」と表示されます。

[説明] セクションの個々のリンクをクリックすると、各言語のローカライズされた名前、説明、リリースノート、およびビジュアルアセットを指定できます。 Microsoft Store の説明は、Package.appxmanifest から抽出されません。 ローカライズされた各説明は、Windows デベロッパーセンターで手動で入力する必要があります。

![日本語アプリの説明](./../../media/japanese-app-description.png)

ローカライズされた説明が送信され、拡張機能が公開されると、Microsoft Store の拡張子のローカライズされたページにアクセスするすべてのユーザーに、次の UI が表示されます。

![日本語の windows ストア](./../../media/japanese-windows-store.png)
 

## Package.appxmanifest サンプル

### ローカライズされていない Package.appxmanifest
次の例は、ローカライズされていない Package.appxmanifest を示しており、"en-us" ロケールのみをサポートしています。


```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap3">
    <Identity
        Name="63533cct23.Jigsaw"
        Publisher="CN=932A7C4A-0308-4632-9E2F-5931E8F02B7C"
        Version="1.3.0.0" />

    <Properties>
        <DisplayName>Jigsaw</DisplayName>
        <PublisherDisplayName>cct23</PublisherDisplayName>
        <Logo>Assets\icon-50.png</Logo>
    </Properties>

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.14393.0" MaxVersionTested="10.0.14800.0" />
    </Dependencies>

    <Resources>
        <Resource Language="en-us" />
    </Resources>

    <Applications>
        <Application Id="App">
            <uap:VisualElements
                AppListEntry="none"
                DisplayName="Jigsaw"
                Square150x150Logo="Assets\icon-150.png"
                Square44x44Logo="Assets\icon-44.png"
                Description="This is a jigsaw puzzle app"
                BackgroundColor="transparent">
            </uap:VisualElements>
            <Extensions>
                <uap3:Extension Category="windows.appExtension">
                    <uap3:AppExtension
                        Name="com.microsoft.edge.extension"
                        Id="EdgeExtension"
                        PublicFolder="Extension"
                        DisplayName="Jigsaw">
                        <uap3:Properties>
                            <Capabilities>
                                <Capability Name="websiteContent"/>
                                <Capability Name="websiteInfo"/>
                                <Capability Name="browserStorage"/>
                            </Capabilities>
                        </uap3:Properties>
                    </uap3:AppExtension>
                </uap3:Extension>
            </Extensions>
        </Application>
    </Applications>
</Package>
```


#### ローカライズされた Package.appxmanifest
この Package.appxmanifest サンプルは、"en-us" 以外の8つのロケールにローカライズされています。 発生したアイテムを確認し `ms-resource:<resource id>` ます。


```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap3">
    <Identity
        Name="63533cct23.Jigsaw"
        Publisher="CN=932A7C4A-0308-4632-9E2F-5931E8F02B7C"
        Version="1.3.0.0" />

    <Properties>
        <DisplayName>ms-resource:DisplayName</DisplayName>
        <PublisherDisplayName>cct23</PublisherDisplayName>
        <Logo>Assets\icon-50.png</Logo>
    </Properties>

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.14393.0" MaxVersionTested="10.0.14800.0" />
    </Dependencies>

    <Resources>
        <Resource Language="en-us" />
        <Resource Language="de" />
        <Resource Language="en" />
        <Resource Language="en-gb" />
        <Resource Language="es" />
        <Resource Language="fr" />
        <Resource Language="it" />
        <Resource Language="ja" />
        <Resource Language="zh-cn" />
    </Resources>

    <Applications>
        <Application Id="App">
            <uap:VisualElements
                AppListEntry="none"
                DisplayName="ms-resource:DisplayName"
                Square150x150Logo="Assets\icon-150.png"
                Square44x44Logo="Assets\icon-44.png"
                Description="ms-resource:Description"
                BackgroundColor="transparent">
            </uap:VisualElements>
            <Extensions>
                <uap3:Extension Category="windows.appExtension">
                    <uap3:AppExtension
                        Name="com.microsoft.edge.extension"
                        Id="EdgeExtension"
                        PublicFolder="Extension"
                        DisplayName="ms-resource:DisplayName">
                        <uap3:Properties>
                            <Capabilities>
                                <Capability Name="websiteContent"/>
                                <Capability Name="websiteInfo"/>
                                <Capability Name="browserStorage"/>
                            </Capabilities>
                        </uap3:Properties>
                    </uap3:AppExtension>
                </uap3:Extension>
            </Extensions>
        </Application>
    </Applications>
</Package>
```
