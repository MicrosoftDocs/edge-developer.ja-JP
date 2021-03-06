---
description: Microsoft Edge 拡張機能パッケージをローカライズして、リリース時に複数の地域に対応する方法について説明します。
title: 拡張機能パッケージのローカライズ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: c4043c1e-15ac-4210-8851-3804c7708f49
keywords: edge, Web 開発, html, css, javascript, developer
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d5dd21f82fd746ad619e9d89a1526ff6a511d615
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397721"
---
# <a name="localizing-microsoft-edge-extensions-for-windows-and-the-microsoft-store"></a>Windows と Microsoft Store の Microsoft Edge 拡張機能のローカライズ  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

このガイドでは、Microsoft Edge 拡張機能をローカライズして、リリース時に複数のローカライズの準備が整う方法について説明します。  拡張機能を完全にローカライズするには、Windows と Microsoft ストアの両方の手順に従う必要があります。  

Microsoft Edge の拡張リソースをローカライズする場合は、国際化ガイドの i18n フレームワークを使用する [方法について説明します](../internationalization.md)。  

> [!NOTE]
> 拡張機能が複数の言語をサポートしない場合は、Microsoft Store の [名前と説明のローカライズ] [にスキップできます](#localizing-name-and-description-in-the-microsoft-store)。  

## <a name="the-localization-process-overview"></a>ローカライズ プロセスの概要  

拡張機能を幅広い対象ユーザーに提供する最初の手順は、複数の言語用に [AppxManifest](#configuring-the-appxmanifest) を構成します。  Microsoft Store では、拡張機能でサポートされている言語がユーザーに表示されます。  拡張機能の名前を Windows UI と Microsoft Store にローカライズする場合は、AppxManifest の特定のフィールドも変更する [必要があります](#localizing-extension-resources-for-windows-and-the-microsoft-store)。  

AppxManifest を構成したら、サポートされている言語の [JSON](#creating-json-string-resources) 文字列リソースを作成する必要があります。  これには、各言語のファイルを作成する必要があります。各ファイルには、その言語のすべての `.resjson` UI 文字列が含まれます。  

サポートされている `.resjson` 言語のファイルが作成された後 [、.pri リソース ファイルを作成する必要があります](#creating-the-resources-file)。 これは [、Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)に付属する MakePRI ツールに構成ファイルを使用して作成されます。  

> [!NOTE]
> ツールを使用するために Windows 10 SDK のみをダウンロードしている場合は、ダウンロードを軽く保つために、デスクトップ アプリ用 Windows SDK 署名ツールと UWP マネージ アプリ用 `MakePri.exe` **Windows** **SDK**のみを選択できます。  ツール `MakePri.exe` はのサブフォルダーに表示されます `C:\Program Files (x86)\Windows Kits\10\bin\10.0.17713.0` 。  

拡張機能をアップロードしたら、最後に Microsoft Store で名前と説明をローカライズ [します](#localizing-name-and-description-in-the-microsoft-store)。  

> [!NOTE]
> Microsoft Edge 拡張機能を Microsoft Store に提出する機能は、現在制限付き機能です。  **Microsoft Store の一** 部として要求を受け取り、今後の更新について検討します。  

## <a name="configuring-the-appxmanifest"></a>AppXManifest の構成  

Microsoft Store の拡張機能の [サポートされている言語] リストは、その AppXManifest 値に基づいて生成されます。  このリストは、要素を使用して指定 `Resource` します。  

![アプリの詳細](../../media/language-app-details.png)  

拡張機能でサポートされている言語の一覧を指定するには、次の形式で要素を追加できます (この要素では `Resource` 、Microsoft Store\で英語、ドイツ語、フランス語のサポートが `Resource` 表示されます)。  

```xml
<Resources>
    <Resource Language="en-us"/>
    <Resource Language="de-de"/>
    <Resource Language="fr-fr"/>
</Resources>
```  

Microsoft Store [でサポートされている言語](/windows/uwp/publish/supported-languages) /言語コードについては、「サポートされている言語」を参照してください。  

AppxManifest のすべてのパブリックに表示される要素にローカライズされた文字列を指定するには、 の形式でリソース識別子を使用する必要があります `ms-resource:<resource id>` 。  

以下のスニペットでは、完全な AppxManifest を作成します。 ローカライズされたリソース ファイルから次の値を取得する必要があります。  

*   Properties\DisplayName  
*   Properties\Description  
*   Properties\PublisherDisplayName  

```xml
<Properties>
    <DisplayName>ms-resource:DisplayName</DisplayName>
    <Description>ms-resource:Description</Description>
    <Logo>Assets\PackageLogo.png</Logo>
    <PublisherDisplayName>ms-resource:PublisherName</PublisherDisplayName>
</Properties>
```  

*   Applications\Application\VisualElements\DisplayName  
*   Applications\Application\VisualElements\Description  
*   Applications\Application\Extensions\Extension\AppExtension\DisplayName  

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

## <a name="localizing-extension-resources-for-windows-and-the-microsoft-store"></a>Windows と Microsoft ストアの拡張機能リソースのローカライズ  

AppxManifest が複数の言語用に構成されたので、拡張機能内で UI をローカライズし、Windows と Microsoft Store の拡張機能をローカライズする場合には、いくつかの重要な違いがあります。  

Microsoft Edge 拡張機能は Microsoft Edge 以外では実行されませんが、その管理は Windows 内で行われる可能性があります。  たとえば、ユーザーは設定アプリで拡張機能を管理できます。  

![設定アプリ](../../media/settings.png)  

Windows の設定アプリに表示される拡張機能の名前は、AppXManifest から取得されます。  この値が英語でハードコードされている場合、英語以外の Windows デバイスに名前の英語版が表示されます。  拡張機能のブランド化が英語のみである場合は、ハードコードされたままにしておいても問題ない。  

> [!NOTE]
> Windows で Microsoft Edge Extension にローカライズされた名前を使用する場合は、AppXManifest ファイルで変更を行う前に、ローカライズされた名前も使用可能で予約済みである必要があります。 [](./extensions-in-the-windows-dev-center.md#name-reservation)  名前が予約されていない場合、最終パッケージを Windows デベロッパー センターにアップロードすると、次のようなエラー メッセージが表示されます。  
> 
> ![言語エラー](../../media/language-error.png)  

JavaScript 拡張機能用に定義されている i18n ベースのローカライズ インフラストラクチャは、Microsoft Edge 環境内でのみ適用できます。  

Microsoft Edge 以外の Windows および Microsoft Store では、サポートされているローカライズ フレームワークは、ユニバーサル Windows プラットフォーム (UWP) ローカライズ フレームワークに基づいてのみサポートされます。  

HTML ベースの Windows アプリの JSON ベースのリソースをサポートしますが、JSON リソースのスキーマは JavaScript 拡張機能に定義されているスキーマと一致しません。  

HTML ベースの Windows アプリの主 [な違いは次のとおりです](/previous-versions/windows/apps/hh465228(v=win.10))。  

*   リソースは、ファイルではなく `.resjson` ファイルで指定 `.json` されます。  
*   サポートされるロケールは AppXManifest ファイルで指定する必要があります。最初のロケールは既定のロケールです。  
*   HTML ベースの Windows アプリ のリソースは、次のスキーマを使用します。  
    
    ```json
    {
        "greeting"              : "Hello",
        "_greeting.comment"     : "A welcome greeting.",

        "farewell"              : "Goodbye",
        "_farewell.comment"     : "A goodbye."
    }
    ```  
    
    アンダースコアで示される名前/値のペアは、対応する文字列リソースのコメントです。  
*   `.resjson` ファイルは `.pri` 、AppX パッケージの作成時に含める必要があるファイルにコンパイルされます。  
    
### <a name="creating-json-string-resources"></a>JSON 文字列リソースの作成  

構成された AppxManifest を使用し、i18n と UWP のローカライズ フレームワークの違いが強調表示された状態で、リソース ファイルを作成する準備が整いました。  

マニフェスト内の 1 つのリソース文字列だけが Microsoft Edge 拡張パッケージに適用されます。  文字列は一般的に JavaScript 拡張機能にローカライズされ、Windows が期待するファイル `DisplayName` `.resjson` に簡単にマップできます。  ローカライズするリソースがこれが唯一のリソースだと仮定すると、作成するサンプル `.resjson` ファイルを次に示します。  

```json
{
    "DisplayName"              : "Jigsaw",
    "_DisplayName.comment"     : "Name of extension."
}
```  

各ファイルのリソース ID `.resjson` は、AppXManifest で使用される ID と一致する必要があります。  上記のサンプル `.resjson` スニペットを使用して、対応する AppXManifest エントリは次のようになります。  

`DisplayName="ms-resource:DisplayName"`  

拡張機能でサポートされている各言語には、対応するリソース ファイルが含まれます `.resjson` 。次のフォルダー構造に配置する必要があります。  

![言語フォルダー構造](../../media/resources-folder.png)  

### <a name="creating-the-resources-file"></a>リソース ファイルの作成  

すべてのファイルを作成したら、パッケージ リソース インデックス `.resjson` \(PRI\) ファイルを作成する準備ができました。  このファイルには、サポートされているすべての言語のリソースが格納されます。  これを行うには、Windows 10 SDK に含まれている **MakePRI** ツールを使用できます。  

まず、構成ファイルを作成する必要があります。  これにより、リソースの既定の修飾子とプラットフォームが定義されます。  この例では、既定の言語とプラットフォーム `English (US)` の Windows 10 を作成します。  これを行うには、次の `priconfig.xml` コンテンツを含むファイルを作成します `[Root folder]` 。  

![フォルダー内の priconfig](../../media/priconfig.png)  

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

これで、構成ファイルと MakePRI ツールを使用して resources.pri ファイルを作成できます。  この例では、プロジェクトのルートの場所は `[Root folder]` .  

```cmd
MakePRI new /pr [Root folder] /cf [Root folder]\priconfig.xml /mn [Root folder]\AppxManifest.xml /of [Root folder]\resources.pri /o
```  

ルート フォルダーに resources.pri ファイルが 1 つ必要です。  

![resources フォルダー](../../media/resources.png)  

## <a name="localizing-name-and-description-in-the-microsoft-store"></a>Microsoft Store での名前と説明のローカライズ  

ローカライズされた完全なパッケージをアップロードすると、Windows デベロッパー センターは複数の言語がサポートされているのを検出し、対応するローカライズされた名前と説明がそれぞれあるか確認します。  ローカライズされた値が不足している場合は、値を指定するまで申請がブロックされます。  

Microsoft Store (Windows ではなく) のローカライズされた名前と説明のみを提供する場合は、拡張機能のすべてのローカライズされた名前を予約して指定 [できます](./extensions-in-the-windows-dev-center.md#name-reservation)。  

追加のローカライズされた名前を予約したら、更新された申請を作成できます。  [説明] セクションでは、Microsoft Store 登録情報の追加言語を管理できます。  

![説明言語の管理](../../media/manage-description-languages.png)  

[追加の言語 **の管理]** を選択すると、Microsoft ストアの登録情報に追加する言語を選択できます。  新しい言語は、[説明] セクション **に [追加の説明言語** ] **として表示** されます。  

[説明] セクションの個々のリンク**** をクリックすると、言語ごとにローカライズされた名前と説明、リリース ノート、ビジュアル アセットを指定できます。  Microsoft Store の説明は AppXManifest から抽出されません。  ローカライズされた各説明は、Windows デベロッパー センターに手動で入力する必要があります。  

![日本語アプリの説明](../../media/japanese-app-description.png)  

ローカライズされた説明が送信され、拡張機能が発行されると、Microsoft Store の拡張機能のローカライズされたページにアクセスするユーザーには、次の UI が表示されます。  

![日本のウィンドウ ストア](../../media/japanese-windows-store.png)  

## <a name="appxmanifest-samples"></a>AppxManifest サンプル  

### <a name="non-localized-appxmanifest"></a>ローカライズされていない AppxManifest  

次の例は、ローカライズされていない AppxManifest を示し、ロケールのみをサポート `en-us` しています。  

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

#### <a name="localized-appxmanifest"></a>ローカライズされた AppxManifest  

この AppxManifest サンプルは、"ja-us" 以外の 8 つのロケールにローカライズされています。 発生に `ms-resource:<resource id>` 注意してください。  

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
