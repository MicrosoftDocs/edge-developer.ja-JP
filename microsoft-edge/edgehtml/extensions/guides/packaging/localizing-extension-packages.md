---
ms.assetid: c4043c1e-15ac-4210-8851-3804c7708f49
description: Microsoft Edge 拡張機能パッケージをローカライズして、リリース時に複数のローカライズの準備が整う方法について説明します。
title: 拡張機能パッケージのローカライズ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cfa85eda47fd71099bb5d201d1cf85992931228c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234929"
---
# <span data-ttu-id="32f8e-104">Windows と Microsoft Store 向け Microsoft Edge 拡張機能のローカライズ</span><span class="sxs-lookup"><span data-stu-id="32f8e-104">Localizing Microsoft Edge extensions for Windows and the Microsoft Store</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="32f8e-105">このガイドでは、Microsoft Edge 拡張機能をローカライズして、リリース時に複数のローカライズの準備が整う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-105">This guide walks through how to localize your Microsoft Edge extension so that it's ready for multiple locales upon release.</span></span> <span data-ttu-id="32f8e-106">拡張機能を完全にローカライズするには、Windows と Microsoft Store の両方の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-106">To fully localize your extension, you'll need to follow the steps for both Windows and the Microsoft Store.</span></span>

<span data-ttu-id="32f8e-107">Microsoft Edge の拡張機能リソースをローカライズする場合は、国際化ガイドで i18n フレームワークを使用する方法 [について説明します](../internationalization.md)。</span><span class="sxs-lookup"><span data-stu-id="32f8e-107">If you want to localize your extension resources for Microsoft Edge, you can learn how to use the i18n framework in the [Internationalization guide](../internationalization.md).</span></span>


> [!NOTE]
> <span data-ttu-id="32f8e-108">拡張機能が複数の言語をサポートしない場合は、Microsoft Store のローカライズ名と説明 [にスキップできます](#localizing-name-and-description-in-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="32f8e-108">If your extension doesn't support multiple languages, you can skip to [Localizing name and description in the Microsoft Store](#localizing-name-and-description-in-the-microsoft-store).</span></span>


## <span data-ttu-id="32f8e-109">ローカライズ プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="32f8e-109">The localization process overview</span></span>

<span data-ttu-id="32f8e-110">幅広いユーザーが拡張機能を利用する最初の手順は、複数の言語用に [AppxManifest](#configuring-the-appxmanifest) を構成する方法です。</span><span class="sxs-lookup"><span data-stu-id="32f8e-110">The first step towards getting your extension available to a wide audience is to [configure its AppxManifest](#configuring-the-appxmanifest) for multiple languages.</span></span> <span data-ttu-id="32f8e-111">Microsoft Store では、拡張機能がサポートする言語がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-111">In the Microsoft Store, this will show users what languages your extension supports.</span></span> <span data-ttu-id="32f8e-112">拡張機能の名前を Windows UI と Microsoft Store にローカライズする場合は、AppxManifest の特定のフィールドも変更する [必要があります](#localizing-extension-resources-for-windows-and-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="32f8e-112">Certain fields in the AppxManifest will also need to be changed if you want the name of your extension to be [localized in the Windows UI and the Microsoft Store](#localizing-extension-resources-for-windows-and-the-microsoft-store).</span></span>


<span data-ttu-id="32f8e-113">AppxManifest を構成したら、サポートされている言語の [JSON](#creating-json-string-resources) 文字列リソースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-113">Once your AppxManifest is configured, you'll need to [create JSON string resources](#creating-json-string-resources) for the languages that you indicated as supported.</span></span> <span data-ttu-id="32f8e-114">これには、言語ごとに .resjson ファイルを作成する必要があります。各ファイルには、その言語のすべての UI 文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-114">This requires creating a .resjson file for each language, where each file has all the UI strings of that language within it.</span></span>


<span data-ttu-id="32f8e-115">サポートされている言語の .resjson ファイルを作成した後、.pri リソース ファイル [を作成する必要があります](#creating-the-resources-file)。</span><span class="sxs-lookup"><span data-stu-id="32f8e-115">After the .resjson files for the supported languages have been made, a [.pri resource file will need to be created](#creating-the-resources-file).</span></span> <span data-ttu-id="32f8e-116">これは[、Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)に付属する**MakePRI**ツールの構成ファイルを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-116">This will be created by using a configuration file to the **MakePRI** tool that comes with the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).</span></span> 

> [!NOTE]
> <span data-ttu-id="32f8e-117">MakePri.exe ツールを使用するために Windows 10 SDK のみをダウンロードする場合は、"Windows SDK Signing Tools for Desktop Apps" および "Windows SDK for UWP Managed Apps" の機能のみを選択して、ダウンロードを軽くすることができます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-117">If you are only downloading the Windows 10 SDK to use the MakePri.exe tool, you can select only the "Windows SDK Signing Tools for Desktop Apps" and "Windows SDK for UWP Managed Apps" features to keep the download lighter.</span></span> <span data-ttu-id="32f8e-118">このMakePri.exe C:\Program Files (x86)\Windows Kits\10\bin\10.0.17713.0 のサブフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-118">The MakePri.exe tool will appear in subfolders of C:\Program Files (x86)\Windows Kits\10\bin\10.0.17713.0.</span></span>


<span data-ttu-id="32f8e-119">拡張機能をアップロードしたら、最後の手順として、Microsoft Store の名前と [説明をローカライズします](#localizing-name-and-description-in-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="32f8e-119">Once you've uploaded your extension, the final step is to [localize the name and description in the Microsoft Store](#localizing-name-and-description-in-the-microsoft-store).</span></span>

> [!NOTE]
> <span data-ttu-id="32f8e-120">Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="32f8e-120">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="32f8e-121">Microsoft Store[の一](https://aka.ms/extension-request)部としてお客様からのリクエストをお問い合わせください。今後の更新について検討します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-121">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>



## <span data-ttu-id="32f8e-122">AppXManifest の構成</span><span class="sxs-lookup"><span data-stu-id="32f8e-122">Configuring the AppXManifest</span></span>

<span data-ttu-id="32f8e-123">Microsoft Store の拡張機能の "サポートされている言語" リストは、AppXManifest の値に基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-123">Your extension's "Supported languages" list in the Microsoft Store is generated based on its AppXManifest values.</span></span> <span data-ttu-id="32f8e-124">このリストは、要素を使用して指定 `Resource` します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-124">This list is specified using the `Resource` element.</span></span>


![設定の画像 - 言語アプリの詳細](./../../media/language-app-details.png)

<span data-ttu-id="32f8e-126">拡張機能でサポートされている言語の一覧を指定するには、次に示す形式で要素を追加できます (この要素では、Microsoft Store で英語、ドイツ語、およびフランス語のサポートが表示されます `Resource` `Resource` )。</span><span class="sxs-lookup"><span data-stu-id="32f8e-126">To specify the list of languages that are supported by your extension, you can add a `Resource` element in the format seen below (this `Resource` element will show support for English, German, and French in the Microsoft Store):</span></span>

```xml
<Resources>
    <Resource Language="en-us"/>
    <Resource Language="de-de"/>
    <Resource Language="fr-fr"/>
</Resources>
```

<span data-ttu-id="32f8e-127">Microsoft Store [でサポートされている言語](https://msdn.microsoft.com/windows/uwp/publish/supported-languages) /言語コードについては、「サポートされている言語」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32f8e-127">See [Supported languages](https://msdn.microsoft.com/windows/uwp/publish/supported-languages) for info on the languages/language codes that the Microsoft Store supports.</span></span>


<span data-ttu-id="32f8e-128">AppxManifest で公開されている要素すべてについてローカライズされた文字列を指定するには、リソース識別子を次の形式で使用する必要があります `ms-resource:<resource id>` 。</span><span class="sxs-lookup"><span data-stu-id="32f8e-128">In order to specify localized strings for all publicly visible elements in the AppxManifest, you'll have to use a resource identifier in the format of `ms-resource:<resource id>`.</span></span>

<span data-ttu-id="32f8e-129">次のスニペットは、完全な AppxManifest を作成します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-129">The snippets below make a complete AppxManifest.</span></span> <span data-ttu-id="32f8e-130">ローカライズされたリソース ファイルから次の値を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-130">The following values should be retrieved from localized resource files:</span></span>

- <span data-ttu-id="32f8e-131">Properties\DisplayName</span><span class="sxs-lookup"><span data-stu-id="32f8e-131">Properties\DisplayName</span></span>
- <span data-ttu-id="32f8e-132">Properties\Description</span><span class="sxs-lookup"><span data-stu-id="32f8e-132">Properties\Description</span></span>
- <span data-ttu-id="32f8e-133">Properties\PublisherDisplayName</span><span class="sxs-lookup"><span data-stu-id="32f8e-133">Properties\PublisherDisplayName</span></span>


```xml
<Properties>
    <DisplayName>ms-resource:DisplayName</DisplayName>
    <Description>ms-resource:Description</Description>
    <Logo>Assets\PackageLogo.png</Logo>
    <PublisherDisplayName>ms-resource:PublisherName</PublisherDisplayName>
</Properties>
```

- <span data-ttu-id="32f8e-134">Applications\Application\VisualElements\DisplayName</span><span class="sxs-lookup"><span data-stu-id="32f8e-134">Applications\Application\VisualElements\DisplayName</span></span>
- <span data-ttu-id="32f8e-135">Applications\Application\VisualElements\Description</span><span class="sxs-lookup"><span data-stu-id="32f8e-135">Applications\Application\VisualElements\Description</span></span>
- <span data-ttu-id="32f8e-136">Applications\Application\Extensions\Extension\AppExtension\DisplayName</span><span class="sxs-lookup"><span data-stu-id="32f8e-136">Applications\Application\Extensions\Extension\AppExtension\DisplayName</span></span>

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


## <span data-ttu-id="32f8e-137">Windows と Microsoft Store の拡張機能リソースのローカライズ</span><span class="sxs-lookup"><span data-stu-id="32f8e-137">Localizing extension resources for Windows and the Microsoft Store</span></span>

<span data-ttu-id="32f8e-138">AppxManifest が複数の言語に対して構成されたので、拡張機能内での UI のローカライズと、Windows と Microsoft Store の拡張機能のローカライズの間には、いくつかの重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-138">Now that your AppxManifest is configured for multiple languages, there are some key differences you should know between localizing the UI within your extension and localizing your extension for Windows and the Microsoft Store.</span></span>

<span data-ttu-id="32f8e-139">Microsoft Edge 拡張機能は Microsoft Edge の外部では実行されませんが、Windows 内で管理できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-139">While Microsoft Edge extensions don't run outside of Microsoft Edge, the management of them can occur within Windows.</span></span> <span data-ttu-id="32f8e-140">たとえば、ユーザーは設定アプリで拡張機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-140">For example, users can manage their extensions in the Settings app:</span></span>


![設定の画像](./../../media/settings.png)



<span data-ttu-id="32f8e-142">Windows の設定アプリに表示される拡張機能の名前は、AppXManifest から取得されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-142">The name of the extension that shows up in the Settings app in Windows comes from the AppXManifest.</span></span> <span data-ttu-id="32f8e-143">この値が英語でハードコードされている場合、英語バージョンの名前は英語以外の Windows デバイスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-143">If this value is hardcoded in English, the English version of the name will show up on non-English Windows devices.</span></span> <span data-ttu-id="32f8e-144">拡張機能のブランド化が英語のみである場合は、ハードコードされたままにしておいても問題ない。</span><span class="sxs-lookup"><span data-stu-id="32f8e-144">If the branding of your extension is English only, it's ok to leave it hardcoded.</span></span>


> [!NOTE]
> <span data-ttu-id="32f8e-145">Windows の Microsoft Edge Extension にローカライズされた名前を使用する場合は、AppXManifest ファイルを変更する前に、ローカライズされた名前も使用可能で予約済みである必要があります。 [](./extensions-in-the-windows-dev-center.md#name-reservation)</span><span class="sxs-lookup"><span data-stu-id="32f8e-145">If you want to use localized names for your Microsoft Edge Extension in Windows, make sure the localized names are also [available and reserved](./extensions-in-the-windows-dev-center.md#name-reservation) before you make the changes in the AppXManifest file.</span></span> <span data-ttu-id="32f8e-146">名前が予約されていない場合、最終的なパッケージを Windows デベロッパー センターにアップロードすると、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-146">If the names are not reserved, you'll get the following error when you upload the final package to Windows Dev Center:</span></span></br></br>

![言語エラー](./../../media/language-error.png)</br></br>


<span data-ttu-id="32f8e-148">JavaScript 拡張機能用に定義された i18n ベースのローカライズ インフラストラクチャは、Microsoft Edge 環境内でのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-148">The i18n based localization infrastructure that's defined for JavaScript extensions is only applicable within the Microsoft Edge environment.</span></span>

<span data-ttu-id="32f8e-149">Microsoft Edge の外部、Windows および Microsoft Store 内でサポートされている唯一のローカライズ フレームワークは、ユニバーサル Windows プラットフォーム (UWP) ローカライズ フレームワークに基づいています。</span><span class="sxs-lookup"><span data-stu-id="32f8e-149">Outside of Microsoft Edge, within Windows and the Microsoft Store, the only supported localization framework is based on the Universal Windows Platform (UWP) localization framework.</span></span>

<span data-ttu-id="32f8e-150">HTML ベースの Windows アプリでは JSON ベースのリソースをサポートしますが、JSON リソースのスキーマは JavaScript 拡張機能に定義されているスキーマと一致しません。</span><span class="sxs-lookup"><span data-stu-id="32f8e-150">While we do support JSON based resources for HTML based Windows apps, the schema for the JSON resources doesn't match the one defined for JavaScript extensions.</span></span>


<span data-ttu-id="32f8e-151">HTML ベースの Windows アプリの主 [な違いを次に示します](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx)。</span><span class="sxs-lookup"><span data-stu-id="32f8e-151">The following are the key differences in [HTML based Windows apps](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx):</span></span>
-    <span data-ttu-id="32f8e-152">リソースは .json ファイルではなく .resjson ファイルで指定されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-152">Resources are specified in .resjson files instead of .json files.</span></span>
-    <span data-ttu-id="32f8e-153">サポートされるロケールは AppXManifest ファイルで指定する必要があります。最初のロケールは既定のロケールです。</span><span class="sxs-lookup"><span data-stu-id="32f8e-153">The locales supported should be specified in the AppXManifest file, with the first locale being the default locale.</span></span>
-    <span data-ttu-id="32f8e-154">HTML ベースの Windows アプリ リソースは、次のスキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-154">HTML based Windows apps resources use the following schema:</span></span>
    ```json
    {
        "greeting"              : "Hello",
        "_greeting.comment"     : "A welcome greeting.",

        "farewell"              : "Goodbye",
        "_farewell.comment"     : "A goodbye."
    }
    ```
    <span data-ttu-id="32f8e-155">アンダースコアで示される名前と値のペアは、対応する文字列リソースのコメントです。</span><span class="sxs-lookup"><span data-stu-id="32f8e-155">The name/value pair denoted by an underscore are comments for the corresponding string resource.</span></span>
-    <span data-ttu-id="32f8e-156">.resjson ファイルは .pri ファイルにコンパイルされ、AppX パッケージの作成時に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-156">.resjson files are compiled into .pri files which must be included during AppX package creation.</span></span>


### <span data-ttu-id="32f8e-157">JSON 文字列リソースの作成</span><span class="sxs-lookup"><span data-stu-id="32f8e-157">Creating JSON string resources</span></span>
<span data-ttu-id="32f8e-158">AppxManifest が構成され、i18n と UWP のローカライズ フレームワークの違いが強調表示された状態で、リソース ファイルを作成する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="32f8e-158">With a configured AppxManifest in hand and the differences between the i18n and UWP localization frameworks highlighted, you're ready to create your resource files.</span></span>

<span data-ttu-id="32f8e-159">マニフェスト内のリソース文字列は、Microsoft Edge 拡張機能パッケージに 1 つしか適用できません。</span><span class="sxs-lookup"><span data-stu-id="32f8e-159">Only one resource string in the manifest is applicable to Microsoft Edge extension packages.</span></span> <span data-ttu-id="32f8e-160">文字列は一般に JavaScript 拡張機能にローカライズされ、Windows が期待する `DisplayName` .resjson ファイルに簡単にマップできます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-160">The `DisplayName` string is commonly localized in JavaScript extensions, and can be easily mapped to the .resjson files that Windows expects.</span></span> <span data-ttu-id="32f8e-161">これがローカライズする唯一のリソースである場合、作成する必要があるサンプルの .resjson ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-161">Assuming that this is the only resource that you would like to localize, here is a sample .resjson file that should be created:</span></span>

```json
{
    "DisplayName"              : "Jigsaw",
    "_DisplayName.comment"     : "Name of extension."
}
```

<span data-ttu-id="32f8e-162">各 .resjson ファイルのリソース ID は、AppXManifest で使用される ID と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-162">The resource ID in each .resjson file needs to match the ID used in the AppXManifest.</span></span> <span data-ttu-id="32f8e-163">上記の .resjson スニペットの例を使用すると、対応する AppXManifest エントリは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-163">Using the example .resjson snippet above, the corresponding AppXManifest entry should be:</span></span>

`DisplayName="ms-resource:DisplayName"`

<span data-ttu-id="32f8e-164">拡張機能がサポートする各言語は、対応する resources.resjson ファイルを持ち、次のフォルダー構造に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-164">Each language that your extension supports should have a corresponding resources.resjson file and be placed in the following folder structure:</span></span>

![言語フォルダーの構造](./../../media/resources-folder.png)


### <span data-ttu-id="32f8e-166">リソース ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="32f8e-166">Creating the resources file</span></span>
<span data-ttu-id="32f8e-167">すべての .resjson ファイルを作成したら、パッケージ リソース インデックス (PRI) ファイルを作成する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="32f8e-167">Once you've created all your .resjson files, you're ready to create your package resource index (PRI) file.</span></span> <span data-ttu-id="32f8e-168">このファイルには、サポートされている言語のリソースすべてが格納されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-168">This file stores the resources for all your supported languages.</span></span> <span data-ttu-id="32f8e-169">これを行うには、Windows 10 SDK に付属の **MakePRI** ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-169">To do this you can use the **MakePRI** tool which is included with the Windows 10 SDK.</span></span>


<span data-ttu-id="32f8e-170">最初に、構成ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-170">First you'll need to create the configuration file.</span></span> <span data-ttu-id="32f8e-171">これにより、リソースの既定の修飾子とプラットフォームが定義されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-171">This defines the default qualifiers and platform for the resources.</span></span> <span data-ttu-id="32f8e-172">この例では、既定の言語を英語 (米国) とプラットフォーム Windows 10 に設定します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-172">For this example, make the default language English (US) and the platform Windows 10.</span></span> <span data-ttu-id="32f8e-173">これを行うには、[ルート フォルダー] priconfig.xml内容を含む新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-173">To do this, create a priconfig.xml file with the following content in the [Root folder]:</span></span>

![フォルダー内の priconfig](./../../media/priconfig.png)


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

<span data-ttu-id="32f8e-175">これで、構成ファイルと MakePRI ツールを使用して resources.pri ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-175">Now you can use the configuration file and the MakePRI tool to create the resources.pri file.</span></span> <span data-ttu-id="32f8e-176">この例では、プロジェクトのルートの場所は [ルート フォルダー] です。</span><span class="sxs-lookup"><span data-stu-id="32f8e-176">For this example, the root location for the project will be [Root folder].</span></span>


```cmd
MakePRI new /pr [Root folder] /cf [Root folder]\priconfig.xml /mn [Root folder]\AppxManifest.xml /of [Root folder]\resources.pri /o
```

<span data-ttu-id="32f8e-177">これで、ルート フォルダーに resources.pri ファイルが 1 つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-177">You should now have one resources.pri file in your root folder:</span></span>

![resources フォルダー](./../../media/resources.png)


## <span data-ttu-id="32f8e-179">Microsoft Store での名前と説明のローカライズ</span><span class="sxs-lookup"><span data-stu-id="32f8e-179">Localizing name and description in the Microsoft Store</span></span>

<span data-ttu-id="32f8e-180">ローカライズされた完全なパッケージをアップロードすると、Windows デベロッパー センターは複数の言語がサポートされているのを検出し、対応するローカライズされた名前と説明が用意されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="32f8e-180">Once you try to upload your complete, localized package, the Windows Dev Center will detect that more than one language is supported and check that you have corresponding localized names and descriptions for each.</span></span> <span data-ttu-id="32f8e-181">ローカライズされた値が不足している場合、値を指定するまで申請はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-181">If any of the localized values are missing, your submission will be blocked until you provide the values.</span></span>

<span data-ttu-id="32f8e-182">(Windows ではなく) Microsoft Store のローカライズされた名前と説明のみを提供する場合は、拡張機能のローカライズされた名前を予約することで行 [います](./extensions-in-the-windows-dev-center.md#name-reservation)。</span><span class="sxs-lookup"><span data-stu-id="32f8e-182">If you are only interested in providing a localized name and description for the Microsoft Store (and not Windows), you can do so by [reserving all the localized names for your extension](./extensions-in-the-windows-dev-center.md#name-reservation).</span></span>


<span data-ttu-id="32f8e-183">追加のローカライズされた名前を予約したら、更新された申請を作成できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-183">Once you've reserved additional localized names, you can create an updated submission.</span></span> <span data-ttu-id="32f8e-184">説明セクションでは、Microsoft Store 登録情報の追加の言語を管理できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-184">In the description section you can manage additional languages for your Microsoft Store listing:</span></span>

![日本語アプリの説明 - 管理](./../../media/manage-description-languages.png)

<span data-ttu-id="32f8e-186">[追加の言語の管理] を選択すると、Microsoft Store 登録情報に追加する言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-186">Once you've selected "Manage additional languages", you'll get to select which languages you want to add to your Microsoft Store listing.</span></span> <span data-ttu-id="32f8e-187">新しい言語は、[説明] セクションに [追加の説明言語] として表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-187">The new language will show up as 'Additional description language' in the "Description" section.</span></span>

<span data-ttu-id="32f8e-188">[説明] セクションの個々のリンクをクリックすると、各言語のローカライズされた名前と説明、リリース ノート、ビジュアル アセットを提供できます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-188">You can click on the individual link in the "Description" section to provide a localized name and description, release notes, and visual assets for each language.</span></span> <span data-ttu-id="32f8e-189">Microsoft Store の説明は、AppXManifest から抽出されません。</span><span class="sxs-lookup"><span data-stu-id="32f8e-189">The description for the Microsoft Store is not extracted from the AppXManifest.</span></span> <span data-ttu-id="32f8e-190">ローカライズされた説明は、Windows デベロッパー センターに手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f8e-190">Each localized description needs to be manually entered in the Windows Dev Center:</span></span>

![日本語アプリの説明](./../../media/japanese-app-description.png)

<span data-ttu-id="32f8e-192">ローカライズされた説明が提出され、拡張機能が公開されると、Microsoft Store で拡張機能のローカライズされたページにアクセスするユーザーには、次の UI が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32f8e-192">Once the localized descriptions are submitted and the extension is published, anyone accessing a localized page of the extension in the Microsoft Store will see the following UI:</span></span>

![日本語の Windows ストア](./../../media/japanese-windows-store.png)
 

## <span data-ttu-id="32f8e-194">AppxManifest サンプル</span><span class="sxs-lookup"><span data-stu-id="32f8e-194">AppxManifest samples</span></span>

### <span data-ttu-id="32f8e-195">ローカライズされていない AppxManifest</span><span class="sxs-lookup"><span data-stu-id="32f8e-195">Non-localized AppxManifest</span></span>
<span data-ttu-id="32f8e-196">次の例は、ローカライズされていない AppxManifest を示しています。"en-us" ロケールのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="32f8e-196">The following example shows an AppxManifest that isn't localized, and only supports the "en-us" locale.</span></span>


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


#### <span data-ttu-id="32f8e-197">ローカライズされた AppxManifest</span><span class="sxs-lookup"><span data-stu-id="32f8e-197">Localized AppxManifest</span></span>
<span data-ttu-id="32f8e-198">この AppxManifest サンプルは、"en-us" 以外の 8 つのロケールにローカライズされています。</span><span class="sxs-lookup"><span data-stu-id="32f8e-198">This AppxManifest sample is localized for eight other locales besides "en-us".</span></span> <span data-ttu-id="32f8e-199">次の状況 `ms-resource:<resource id>` に注意してください。</span><span class="sxs-lookup"><span data-stu-id="32f8e-199">Notice the `ms-resource:<resource id>` occurrences:</span></span>


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
