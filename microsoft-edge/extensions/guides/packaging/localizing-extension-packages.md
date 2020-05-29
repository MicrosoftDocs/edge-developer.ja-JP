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
# <span data-ttu-id="6401a-104">Microsoft Edge extensions for Windows と Microsoft Store のローカライズ</span><span class="sxs-lookup"><span data-stu-id="6401a-104">Localizing Microsoft Edge extensions for Windows and the Microsoft Store</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="6401a-105">このガイドでは、Microsoft Edge 拡張機能をローカライズして、リリース時に複数のロケールが使えるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6401a-105">This guide walks through how to localize your Microsoft Edge extension so that it's ready for multiple locales upon release.</span></span> <span data-ttu-id="6401a-106">内線番号を完全にローカライズするには、Windows と Microsoft ストアの両方の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-106">To fully localize your extension, you'll need to follow the steps for both Windows and the Microsoft Store.</span></span>

<span data-ttu-id="6401a-107">Microsoft Edge の拡張機能リソースをローカライズする場合は、[国際化ガイド](../internationalization.md)で i18n フレームワークを使用する方法を学習できます。</span><span class="sxs-lookup"><span data-stu-id="6401a-107">If you want to localize your extension resources for Microsoft Edge, you can learn how to use the i18n framework in the [Internationalization guide](../internationalization.md).</span></span>


> [!NOTE]
> <span data-ttu-id="6401a-108">拡張機能で複数の言語がサポートされていない場合は、「 [Microsoft Store での名前と説明のローカライズ」](#localizing-name-and-description-in-the-microsoft-store)に進んでください。</span><span class="sxs-lookup"><span data-stu-id="6401a-108">If your extension doesn't support multiple languages, you can skip to [Localizing name and description in the Microsoft Store](#localizing-name-and-description-in-the-microsoft-store).</span></span>


## <span data-ttu-id="6401a-109">ローカライズプロセスの概要</span><span class="sxs-lookup"><span data-stu-id="6401a-109">The localization process overview</span></span>

<span data-ttu-id="6401a-110">内線番号を多くのユーザーが利用できるようにするための最初のステップとして、複数の言語に対応するように[package.appxmanifest を設定](#configuring-the-appxmanifest)します。</span><span class="sxs-lookup"><span data-stu-id="6401a-110">The first step towards getting your extension available to a wide audience is to [configure its AppxManifest](#configuring-the-appxmanifest) for multiple languages.</span></span> <span data-ttu-id="6401a-111">Microsoft ストアでは、拡張機能でサポートされている言語がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-111">In the Microsoft Store, this will show users what languages your extension supports.</span></span> <span data-ttu-id="6401a-112">拡張子の名前を[WINDOWS UI と Microsoft Store でローカライズ](#localizing-extension-resources-for-windows-and-the-microsoft-store)する場合は、package.appxmanifest 内の特定のフィールドも変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-112">Certain fields in the AppxManifest will also need to be changed if you want the name of your extension to be [localized in the Windows UI and the Microsoft Store](#localizing-extension-resources-for-windows-and-the-microsoft-store).</span></span>


<span data-ttu-id="6401a-113">Package.appxmanifest を構成したら、サポート対象として指定した言語の[JSON 文字列リソースを作成](#creating-json-string-resources)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-113">Once your AppxManifest is configured, you'll need to [create JSON string resources](#creating-json-string-resources) for the languages that you indicated as supported.</span></span> <span data-ttu-id="6401a-114">そのためには、各言語の resjson ファイルを作成する必要があります。この場合、各ファイルには、その言語に含まれるすべての UI 文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6401a-114">This requires creating a .resjson file for each language, where each file has all the UI strings of that language within it.</span></span>


<span data-ttu-id="6401a-115">サポートされている言語の resjson ファイルが作成されたら、 [pri リソースファイルを作成する必要があり](#creating-the-resources-file)ます。</span><span class="sxs-lookup"><span data-stu-id="6401a-115">After the .resjson files for the supported languages have been made, a [.pri resource file will need to be created](#creating-the-resources-file).</span></span> <span data-ttu-id="6401a-116">これは、 [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)に付属の**makepri**ツールへの構成ファイルを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-116">This will be created by using a configuration file to the **MakePRI** tool that comes with the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).</span></span> 

> [!NOTE]
> <span data-ttu-id="6401a-117">MakePri ツールを使用するために Windows 10 SDK をダウンロードするだけの場合は、"デスクトップアプリ用 Windows SDK 署名ツール" および "Windows SDK for UWP マネージアプリ" の機能のみを選択して、ダウンロードを軽量にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6401a-117">If you are only downloading the Windows 10 SDK to use the MakePri.exe tool, you can select only the "Windows SDK Signing Tools for Desktop Apps" and "Windows SDK for UWP Managed Apps" features to keep the download lighter.</span></span> <span data-ttu-id="6401a-118">MakePri ツールは、C:\Program Files (x86) \Windows Kits\10\bin\10.0.17713.0. のサブフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-118">The MakePri.exe tool will appear in subfolders of C:\Program Files (x86)\Windows Kits\10\bin\10.0.17713.0.</span></span>


<span data-ttu-id="6401a-119">拡張機能をアップロードしたら、最後の手順として、 [Microsoft ストアで名前と説明をローカライズ](#localizing-name-and-description-in-the-microsoft-store)します。</span><span class="sxs-lookup"><span data-stu-id="6401a-119">Once you've uploaded your extension, the final step is to [localize the name and description in the Microsoft Store](#localizing-name-and-description-in-the-microsoft-store).</span></span>

> [!NOTE]
> <span data-ttu-id="6401a-120">Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="6401a-120">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="6401a-121">Microsoft Store の一部として要求が送信された場合は、skype[に](https://aka.ms/extension-request)連絡して、将来の更新についてご検討ください。</span><span class="sxs-lookup"><span data-stu-id="6401a-121">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>



## <span data-ttu-id="6401a-122">Package.appxmanifest を構成する</span><span class="sxs-lookup"><span data-stu-id="6401a-122">Configuring the AppXManifest</span></span>

<span data-ttu-id="6401a-123">Microsoft Store の拡張子 "サポートされている言語" リストは、Package.appxmanifest の値に基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-123">Your extension's "Supported languages" list in the Microsoft Store is generated based on its AppXManifest values.</span></span> <span data-ttu-id="6401a-124">この一覧は、要素を使って指定し `Resource` ます。</span><span class="sxs-lookup"><span data-stu-id="6401a-124">This list is specified using the `Resource` element.</span></span>


![設定のイメージ](./../../media/language-app-details.png)

<span data-ttu-id="6401a-126">内線番号でサポートされている言語のリストを指定するには、 `Resource` 次に示す形式で要素を追加します (こ `Resource` の要素は、Microsoft Store での英語、ドイツ語、フランス語のサポートを示します)。</span><span class="sxs-lookup"><span data-stu-id="6401a-126">To specify the list of languages that are supported by your extension, you can add a `Resource` element in the format seen below (this `Resource` element will show support for English, German, and French in the Microsoft Store):</span></span>

```xml
<Resources>
    <Resource Language="en-us"/>
    <Resource Language="de-de"/>
    <Resource Language="fr-fr"/>
</Resources>
```

<span data-ttu-id="6401a-127">Microsoft Store でサポートされている言語または言語コードの詳細については、「[サポートされる言語](https://msdn.microsoft.com/windows/uwp/publish/supported-languages)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6401a-127">See [Supported languages](https://msdn.microsoft.com/windows/uwp/publish/supported-languages) for info on the languages/language codes that the Microsoft Store supports.</span></span>


<span data-ttu-id="6401a-128">Package.appxmanifest でパブリックに表示されるすべての要素にローカライズされた文字列を指定するには、の形式でリソース識別子を使う必要があり `ms-resource:<resource id>` ます。</span><span class="sxs-lookup"><span data-stu-id="6401a-128">In order to specify localized strings for all publicly visible elements in the AppxManifest, you'll have to use a resource identifier in the format of `ms-resource:<resource id>`.</span></span>

<span data-ttu-id="6401a-129">以下のスニペットでは、完全な Package.appxmanifest を作成しています。</span><span class="sxs-lookup"><span data-stu-id="6401a-129">The snippets below make a complete AppxManifest.</span></span> <span data-ttu-id="6401a-130">ローカライズされたリソースファイルから次の値を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-130">The following values should be retrieved from localized resource files:</span></span>

- <span data-ttu-id="6401a-131">Properties\DisplayName</span><span class="sxs-lookup"><span data-stu-id="6401a-131">Properties\DisplayName</span></span>
- <span data-ttu-id="6401a-132">Properties\Description</span><span class="sxs-lookup"><span data-stu-id="6401a-132">Properties\Description</span></span>
- <span data-ttu-id="6401a-133">Properties\PublisherDisplayName</span><span class="sxs-lookup"><span data-stu-id="6401a-133">Properties\PublisherDisplayName</span></span>


```xml
<Properties>
    <DisplayName>ms-resource:DisplayName</DisplayName>
    <Description>ms-resource:Description</Description>
    <Logo>Assets\PackageLogo.png</Logo>
    <PublisherDisplayName>ms-resource:PublisherName</PublisherDisplayName>
</Properties>
```

- <span data-ttu-id="6401a-134">Application\ Application\ visualelement¥ DisplayName</span><span class="sxs-lookup"><span data-stu-id="6401a-134">Applications\Application\VisualElements\DisplayName</span></span>
- <span data-ttu-id="6401a-135">Application\ Application\ visualelementの説明</span><span class="sxs-lookup"><span data-stu-id="6401a-135">Applications\Application\VisualElements\Description</span></span>
- <span data-ttu-id="6401a-136">Applications\Application\Extensions\Extension\AppExtension\DisplayName</span><span class="sxs-lookup"><span data-stu-id="6401a-136">Applications\Application\Extensions\Extension\AppExtension\DisplayName</span></span>

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


## <span data-ttu-id="6401a-137">Windows と Microsoft ストアの拡張リソースのローカライズ</span><span class="sxs-lookup"><span data-stu-id="6401a-137">Localizing extension resources for Windows and the Microsoft Store</span></span>

<span data-ttu-id="6401a-138">Package.appxmanifest が複数の言語に対応するように構成されたため、拡張機能での UI のローカライズと、Windows および Microsoft ストアの拡張機能のローカライズの間に知っておく必要がある主な違いがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="6401a-138">Now that your AppxManifest is configured for multiple languages, there are some key differences you should know between localizing the UI within your extension and localizing your extension for Windows and the Microsoft Store.</span></span>

<span data-ttu-id="6401a-139">Microsoft edge extensions は Microsoft Edge の外部では実行されませんが、Windows 内で管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6401a-139">While Microsoft Edge extensions don't run outside of Microsoft Edge, the management of them can occur within Windows.</span></span> <span data-ttu-id="6401a-140">たとえば、ユーザーは設定アプリで自分の拡張子を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6401a-140">For example, users can manage their extensions in the Settings app:</span></span>


![設定のイメージ](./../../media/settings.png)



<span data-ttu-id="6401a-142">Windows の設定アプリで表示される拡張機能の名前は、Package.appxmanifest から取得されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-142">The name of the extension that shows up in the Settings app in Windows comes from the AppXManifest.</span></span> <span data-ttu-id="6401a-143">この値が英語でハードコードされている場合は、英語以外の Windows デバイスでは英語版の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-143">If this value is hardcoded in English, the English version of the name will show up on non-English Windows devices.</span></span> <span data-ttu-id="6401a-144">拡張機能のブランドが英語のみの場合は、ハードコーディングしたままにしても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="6401a-144">If the branding of your extension is English only, it's ok to leave it hardcoded.</span></span>


> [!NOTE]
> <span data-ttu-id="6401a-145">Windows で Microsoft Edge 拡張機能のローカライズされた名前を使用する場合は、Package.appxmanifest ファイルで変更を行う前に、ローカライズされた名前も[使用可能で、予約済み](./extensions-in-the-windows-dev-center.md#name-reservation)であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6401a-145">If you want to use localized names for your Microsoft Edge Extension in Windows, make sure the localized names are also [available and reserved](./extensions-in-the-windows-dev-center.md#name-reservation) before you make the changes in the AppXManifest file.</span></span> <span data-ttu-id="6401a-146">名前が予約されていない場合は、Windows デベロッパーセンターに最終的なパッケージをアップロードすると、次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-146">If the names are not reserved, you'll get the following error when you upload the final package to Windows Dev Center:</span></span></br></br>

![言語エラー](./../../media/language-error.png)</br></br>


<span data-ttu-id="6401a-148">JavaScript 拡張機能に対して定義されている i18n ベースのローカライズインフラストラクチャは、Microsoft Edge 環境内でのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-148">The i18n based localization infrastructure that's defined for JavaScript extensions is only applicable within the Microsoft Edge environment.</span></span>

<span data-ttu-id="6401a-149">Microsoft Edge 以外の Windows と Microsoft Store では、サポートされているローカライズフレームワークはユニバーサル Windows プラットフォーム (UWP) のローカライズフレームワークに基づいています。</span><span class="sxs-lookup"><span data-stu-id="6401a-149">Outside of Microsoft Edge, within Windows and the Microsoft Store, the only supported localization framework is based on the Universal Windows Platform (UWP) localization framework.</span></span>

<span data-ttu-id="6401a-150">HTML ベースの Windows アプリでは、JSON ベースのリソースをサポートしていますが、JSON リソースのスキーマは JavaScript 拡張機能に対して定義されているものと一致しません。</span><span class="sxs-lookup"><span data-stu-id="6401a-150">While we do support JSON based resources for HTML based Windows apps, the schema for the JSON resources doesn't match the one defined for JavaScript extensions.</span></span>


<span data-ttu-id="6401a-151">[HTML ベースの Windows アプリ](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx)では、次の主な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="6401a-151">The following are the key differences in [HTML based Windows apps](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx):</span></span>
-    <span data-ttu-id="6401a-152">リソースは、json ファイルではなく、resjson ファイルで指定されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-152">Resources are specified in .resjson files instead of .json files.</span></span>
-    <span data-ttu-id="6401a-153">サポートされるロケールは、最初のロケールが既定のロケールである Package.appxmanifest ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-153">The locales supported should be specified in the AppXManifest file, with the first locale being the default locale.</span></span>
-    <span data-ttu-id="6401a-154">HTML ベースの Windows アプリのリソースでは、次のスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-154">HTML based Windows apps resources use the following schema:</span></span>
    ```json
    {
        "greeting"              : "Hello",
        "_greeting.comment"     : "A welcome greeting.",

        "farewell"              : "Goodbye",
        "_farewell.comment"     : "A goodbye."
    }
    ```
    <span data-ttu-id="6401a-155">アンダースコアで示されている名前と値のペアは、対応する文字列リソースに対してコメントとなります。</span><span class="sxs-lookup"><span data-stu-id="6401a-155">The name/value pair denoted by an underscore are comments for the corresponding string resource.</span></span>
-    <span data-ttu-id="6401a-156">resjson ファイルは、AppX パッケージの作成時に含める必要がある .pri ファイルにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="6401a-156">.resjson files are compiled into .pri files which must be included during AppX package creation.</span></span>


### <span data-ttu-id="6401a-157">JSON 文字列リソースの作成</span><span class="sxs-lookup"><span data-stu-id="6401a-157">Creating JSON string resources</span></span>
<span data-ttu-id="6401a-158">構成済みの Package.appxmanifest と、国際化と UWP のローカライズフレームワークの違いが強調表示されているので、リソースファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6401a-158">With a configured AppxManifest in hand and the differences between the i18n and UWP localization frameworks highlighted, you're ready to create your resource files.</span></span>

<span data-ttu-id="6401a-159">マニフェストでは、Microsoft Edge 拡張機能パッケージに適用できるリソース文字列は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="6401a-159">Only one resource string in the manifest is applicable to Microsoft Edge extension packages.</span></span> <span data-ttu-id="6401a-160">この `DisplayName` 文字列は、一般的に JavaScript 拡張機能でローカライズされ、Windows で想定される resjson ファイルに簡単にマッピングできます。</span><span class="sxs-lookup"><span data-stu-id="6401a-160">The `DisplayName` string is commonly localized in JavaScript extensions, and can be easily mapped to the .resjson files that Windows expects.</span></span> <span data-ttu-id="6401a-161">ローカライズする唯一のリソースであると仮定します。ここでは、作成する必要がある resjson ファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="6401a-161">Assuming that this is the only resource that you would like to localize, here is a sample .resjson file that should be created:</span></span>

```json
{
    "DisplayName"              : "Jigsaw",
    "_DisplayName.comment"     : "Name of extension."
}
```

<span data-ttu-id="6401a-162">各 resjson ファイルのリソース ID は、Package.appxmanifest で使用されている ID と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-162">The resource ID in each .resjson file needs to match the ID used in the AppXManifest.</span></span> <span data-ttu-id="6401a-163">上の例の resjson スニペットを使って、対応する Package.appxmanifest エントリは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6401a-163">Using the example .resjson snippet above, the corresponding AppXManifest entry should be:</span></span>

`DisplayName="ms-resource:DisplayName"`

<span data-ttu-id="6401a-164">拡張機能でサポートされている各言語には、対応するリソース. resjson ファイルがあり、次のフォルダー構造に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-164">Each language that your extension supports should have a corresponding resources.resjson file and be placed in the following folder structure:</span></span>

![言語フォルダー構造](./../../media/resources-folder.png)


### <span data-ttu-id="6401a-166">リソースファイルの作成</span><span class="sxs-lookup"><span data-stu-id="6401a-166">Creating the resources file</span></span>
<span data-ttu-id="6401a-167">すべての resjson ファイルを作成したら、パッケージリソースインデックス (PRI) ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6401a-167">Once you've created all your .resjson files, you're ready to create your package resource index (PRI) file.</span></span> <span data-ttu-id="6401a-168">このファイルには、サポートされているすべての言語のリソースが保存されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-168">This file stores the resources for all your supported languages.</span></span> <span data-ttu-id="6401a-169">これを行うには、Windows 10 SDK に含まれている**Makepri**ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6401a-169">To do this you can use the **MakePRI** tool which is included with the Windows 10 SDK.</span></span>


<span data-ttu-id="6401a-170">まず、構成ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-170">First you'll need to create the configuration file.</span></span> <span data-ttu-id="6401a-171">これにより、リソースの既定の修飾子とプラットフォームが定義されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-171">This defines the default qualifiers and platform for the resources.</span></span> <span data-ttu-id="6401a-172">この例では、既定の言語である英語 (米国) とプラットフォームの Windows 10 を作成します。</span><span class="sxs-lookup"><span data-stu-id="6401a-172">For this example, make the default language English (US) and the platform Windows 10.</span></span> <span data-ttu-id="6401a-173">これを行うには、[ルートフォルダー] に次のコンテンツを含む priconfig.xml ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6401a-173">To do this, create a priconfig.xml file with the following content in the [Root folder]:</span></span>

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

<span data-ttu-id="6401a-175">これで、構成ファイルと MakePRI ツールを使って、リソースの pri ファイルを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6401a-175">Now you can use the configuration file and the MakePRI tool to create the resources.pri file.</span></span> <span data-ttu-id="6401a-176">この例では、プロジェクトのルートの場所は [ルートフォルダー] になります。</span><span class="sxs-lookup"><span data-stu-id="6401a-176">For this example, the root location for the project will be [Root folder].</span></span>


```cmd
MakePRI new /pr [Root folder] /cf [Root folder]\priconfig.xml /mn [Root folder]\AppxManifest.xml /of [Root folder]\resources.pri /o
```

<span data-ttu-id="6401a-177">これで、ルートフォルダに1つのリソース pri ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-177">You should now have one resources.pri file in your root folder:</span></span>

![リソースフォルダー](./../../media/resources.png)


## <span data-ttu-id="6401a-179">Microsoft Store での名前と説明のローカライズ</span><span class="sxs-lookup"><span data-stu-id="6401a-179">Localizing name and description in the Microsoft Store</span></span>

<span data-ttu-id="6401a-180">ローカライズされた完全なパッケージをアップロードしようとすると、Windows デベロッパーセンターは、複数の言語がサポートされていることを検出し、それぞれに対応するローカライズされた名前と説明を確認します。</span><span class="sxs-lookup"><span data-stu-id="6401a-180">Once you try to upload your complete, localized package, the Windows Dev Center will detect that more than one language is supported and check that you have corresponding localized names and descriptions for each.</span></span> <span data-ttu-id="6401a-181">ローカライズされた値が見つからない場合は、値を提供するまで、申請はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6401a-181">If any of the localized values are missing, your submission will be blocked until you provide the values.</span></span>

<span data-ttu-id="6401a-182">(Windows ではなく) Microsoft ストアのローカライズされた名前と説明だけが必要な場合は、[拡張機能のローカライズ](./extensions-in-the-windows-dev-center.md#name-reservation)された名前をすべて予約してください。</span><span class="sxs-lookup"><span data-stu-id="6401a-182">If you are only interested in providing a localized name and description for the Microsoft Store (and not Windows), you can do so by [reserving all the localized names for your extension](./extensions-in-the-windows-dev-center.md#name-reservation).</span></span>


<span data-ttu-id="6401a-183">追加のローカライズされた名前を予約すると、更新された申請を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6401a-183">Once you've reserved additional localized names, you can create an updated submission.</span></span> <span data-ttu-id="6401a-184">[説明] セクションでは、Microsoft ストア登録情報の追加言語を管理できます。</span><span class="sxs-lookup"><span data-stu-id="6401a-184">In the description section you can manage additional languages for your Microsoft Store listing:</span></span>

![日本語アプリの説明](./../../media/manage-description-languages.png)

<span data-ttu-id="6401a-186">[追加言語の管理] を選択すると、Microsoft ストアの登録情報に追加する言語を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="6401a-186">Once you've selected "Manage additional languages", you'll get to select which languages you want to add to your Microsoft Store listing.</span></span> <span data-ttu-id="6401a-187">新しい言語は、「説明」セクションに「その他の説明言語」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-187">The new language will show up as 'Additional description language' in the "Description" section.</span></span>

<span data-ttu-id="6401a-188">[説明] セクションの個々のリンクをクリックすると、各言語のローカライズされた名前、説明、リリースノート、およびビジュアルアセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6401a-188">You can click on the individual link in the "Description" section to provide a localized name and description, release notes, and visual assets for each language.</span></span> <span data-ttu-id="6401a-189">Microsoft Store の説明は、Package.appxmanifest から抽出されません。</span><span class="sxs-lookup"><span data-stu-id="6401a-189">The description for the Microsoft Store is not extracted from the AppXManifest.</span></span> <span data-ttu-id="6401a-190">ローカライズされた各説明は、Windows デベロッパーセンターで手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6401a-190">Each localized description needs to be manually entered in the Windows Dev Center:</span></span>

![日本語アプリの説明](./../../media/japanese-app-description.png)

<span data-ttu-id="6401a-192">ローカライズされた説明が送信され、拡張機能が公開されると、Microsoft Store の拡張子のローカライズされたページにアクセスするすべてのユーザーに、次の UI が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6401a-192">Once the localized descriptions are submitted and the extension is published, anyone accessing a localized page of the extension in the Microsoft Store will see the following UI:</span></span>

![日本語の windows ストア](./../../media/japanese-windows-store.png)
 

## <span data-ttu-id="6401a-194">Package.appxmanifest サンプル</span><span class="sxs-lookup"><span data-stu-id="6401a-194">AppxManifest samples</span></span>

### <span data-ttu-id="6401a-195">ローカライズされていない Package.appxmanifest</span><span class="sxs-lookup"><span data-stu-id="6401a-195">Non-localized AppxManifest</span></span>
<span data-ttu-id="6401a-196">次の例は、ローカライズされていない Package.appxmanifest を示しており、"en-us" ロケールのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6401a-196">The following example shows an AppxManifest that isn't localized, and only supports the "en-us" locale.</span></span>


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


#### <span data-ttu-id="6401a-197">ローカライズされた Package.appxmanifest</span><span class="sxs-lookup"><span data-stu-id="6401a-197">Localized AppxManifest</span></span>
<span data-ttu-id="6401a-198">この Package.appxmanifest サンプルは、"en-us" 以外の8つのロケールにローカライズされています。</span><span class="sxs-lookup"><span data-stu-id="6401a-198">This AppxManifest sample is localized for eight other locales besides "en-us".</span></span> <span data-ttu-id="6401a-199">発生したアイテムを確認し `ms-resource:<resource id>` ます。</span><span class="sxs-lookup"><span data-stu-id="6401a-199">Notice the `ms-resource:<resource id>` occurrences:</span></span>


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
