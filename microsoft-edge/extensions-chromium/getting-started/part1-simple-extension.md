---
description: その日の NASA の画像をポップアップする拡張機能を作成する
title: 拡張機能のチュートリアルを作成する - パート 1
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium, Web 開発, html, css, javascript, developer, extensions
ms.openlocfilehash: dfbe7893ce576c223d2b1d39ec21b6c5f46d8356
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397511"
---
# <a name="create-an-extension-tutorial---part-1"></a><span data-ttu-id="19e73-104">拡張機能のチュートリアルを作成する - パート 1</span><span class="sxs-lookup"><span data-stu-id="19e73-104">Create an extension tutorial - Part 1</span></span>  

## <a name="overview"></a><span data-ttu-id="19e73-105">概要</span><span class="sxs-lookup"><span data-stu-id="19e73-105">Overview</span></span>  

<span data-ttu-id="19e73-106">このチュートリアルの目的は、空のディレクトリから始まる Microsoft Edge (Chromium) 拡張機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="19e73-106">The goal for this tutorial is to build a Microsoft Edge (Chromium) extension starting with an empty directory.</span></span>  <span data-ttu-id="19e73-107">その日の NASA の画像をポップアップする拡張機能を作成しています。</span><span class="sxs-lookup"><span data-stu-id="19e73-107">You are building an extension that pops up the NASA picture of the day.</span></span> <span data-ttu-id="19e73-108">このチュートリアルでは、次のアクションを実行して拡張機能を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19e73-108">In this tutorial, learn how to create an extension by completing the following actions.</span></span>  

*   <span data-ttu-id="19e73-109">ファイルの `manifest.json` 作成。</span><span class="sxs-lookup"><span data-stu-id="19e73-109">Creating a `manifest.json` file.</span></span>  
*   <span data-ttu-id="19e73-110">アイコンの追加。</span><span class="sxs-lookup"><span data-stu-id="19e73-110">Adding icons.</span></span>  
*   <span data-ttu-id="19e73-111">既定のポップアップ ダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="19e73-111">Opening a default pop-up dialog.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="19e73-112">開始する前に</span><span class="sxs-lookup"><span data-stu-id="19e73-112">Before you Begin</span></span>

<span data-ttu-id="19e73-113">このチュートリアルで構築する完成した拡張機能をテストするには、ソース コードを [ダウンロードします][ArchiveExtensionGettingStartedPart1]。</span><span class="sxs-lookup"><span data-stu-id="19e73-113">To test out the completed extension that you are building in this tutorial, download the [source code][ArchiveExtensionGettingStartedPart1].</span></span>  

## <a name="step-1-create-a-manifestjson-file"></a><span data-ttu-id="19e73-114">手順 1: ファイルにmanifest.js作成する</span><span class="sxs-lookup"><span data-stu-id="19e73-114">Step 1: Create a manifest.json file</span></span>

<span data-ttu-id="19e73-115">すべての拡張パッケージには、ルート `manifest.json` にファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="19e73-115">Every extension package must have a `manifest.json` file at the root.</span></span>  <span data-ttu-id="19e73-116">マニフェストには、拡張機能の詳細、拡張機能パッケージのバージョン、拡張機能の名前と説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19e73-116">The manifest provides details of your extension, the extension package version, the extension name and description, and so on.</span></span>  

<span data-ttu-id="19e73-117">次のコード スニペットは、ファイルに必要な基本情報の概要を示 `manifest.json` しています。</span><span class="sxs-lookup"><span data-stu-id="19e73-117">The following code snippet outlines the basic information needed in your `manifest.json` file.</span></span>  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to display the NASA picture of the day."
}
```  

## <a name="step-2-add-icons"></a><span data-ttu-id="19e73-118">手順 2: アイコンを追加する</span><span class="sxs-lookup"><span data-stu-id="19e73-118">Step 2: Add icons</span></span>  

<span data-ttu-id="19e73-119">まず、プロジェクトに `icons` ディレクトリを作成し、アイコン イメージ ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="19e73-119">Start by creating the `icons` directory in your project to store the icon image files.</span></span>  <span data-ttu-id="19e73-120">アイコンは、ユーザーが拡張機能を起動するために選択したボタンの背景画像に使用されます。</span><span class="sxs-lookup"><span data-stu-id="19e73-120">The icons are used for the background image of the button that users select to launch the extension.</span></span>  

:::image type="complex" source="./media/part1-badge1.png" alt-text="拡張機能を開くツールバーのアイコン":::
   <span data-ttu-id="19e73-122">拡張機能を開くツールバーのアイコン</span><span class="sxs-lookup"><span data-stu-id="19e73-122">Icon on the toolbar to open your extension</span></span>  
:::image-end:::  

<span data-ttu-id="19e73-123">アイコンの場合は、次の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="19e73-123">For icons, we recommend using:</span></span> 
*   `PNG` <span data-ttu-id="19e73-124">アイコンの形式を指定しますが、形式 `BMP` を `GIF` 使用 `ICO` `JPEG` できます。</span><span class="sxs-lookup"><span data-stu-id="19e73-124">format for icons, but you may also use `BMP`, `GIF`, `ICO` or `JPEG` formats.</span></span>  
*   <span data-ttu-id="19e73-125">128 x 128 px の画像で、必要に応じてブラウザーによってサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="19e73-125">Images that are 128 x 128 px, which are resized by the browser if necessary.</span></span>  

<span data-ttu-id="19e73-126">プロジェクトのディレクトリは、次の構造に似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e73-126">The directories of your project should be similar to the following structure.</span></span>   

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

<span data-ttu-id="19e73-127">次に、アイコンをファイルに追加 `manifest.json` します。</span><span class="sxs-lookup"><span data-stu-id="19e73-127">Next, add the icons to the `manifest.json` file.</span></span> <span data-ttu-id="19e73-128">アイコン情報 `manifest.json` を使用してファイルを更新し、次のコード スニペットと一致します。</span><span class="sxs-lookup"><span data-stu-id="19e73-128">Update your `manifest.json` file with the icons information so that it matches the following code snippet.</span></span> <span data-ttu-id="19e73-129">次 `png` のコードに記載されているファイルは、この記事で前述したダウンロード ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="19e73-129">The `png` files listed in the following code are available in the download file mentioned earlier in this article.</span></span>  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to show the NASA picture of the day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    }
}
```  

## <a name="step-3-open-a-default-pop-up-dialog"></a><span data-ttu-id="19e73-130">手順 3: 既定のポップアップ ダイアログを開く</span><span class="sxs-lookup"><span data-stu-id="19e73-130">Step 3: Open a default pop-up dialog</span></span>  

<span data-ttu-id="19e73-131">次に、ユーザーが `HTML` 拡張機能を起動するときに実行するファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="19e73-131">Now, create a `HTML` file to run when the user launches your extension.</span></span>  <span data-ttu-id="19e73-132">という名前のディレクトリに HTML `popup.html` ファイルを作成します `popup` 。</span><span class="sxs-lookup"><span data-stu-id="19e73-132">Create the HTML file named `popup.html` in a directory named `popup`.</span></span>  <span data-ttu-id="19e73-133">ユーザーが拡張機能を起動するアイコンを選択すると `popup/popup.html` 、モーダル ダイアログとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="19e73-133">When users select the icon to launch the extension, `popup/popup.html` is displayed as a modal dialog.</span></span>  

<span data-ttu-id="19e73-134">星の画像を表示するには、次のコード スニペット `popup.html` のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="19e73-134">Add the code from the following code snippet to `popup.html` to display the stars image.</span></span>  

```html
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>NASA picture of the day</title>
    </head>
    <body>
        <div>
            <img src="/images/stars.jpeg" alt="Display the stars image" />
        </div>
    </body>
</html>
```  

<span data-ttu-id="19e73-135">イメージ ファイルを images フォルダー `images/stars.jpeg` に追加してください。</span><span class="sxs-lookup"><span data-stu-id="19e73-135">Ensure that you add the image file `images/stars.jpeg` to the images folder.</span></span>  <span data-ttu-id="19e73-136">プロジェクトのディレクトリは、次の構造に似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e73-136">The directories of your project should be similar to the following structure.</span></span>   

```shell
└── part1
    ├── _manifest.json
    ├── icons
    │   ├── nasapod16x16.png
    │   ├── nasapod32x32.png
    │   ├── nasapod48x48.png
    │   └── nasapod128x128.png
    ├── images
    │   └── stars.jpeg
    └── popup
        └── popup.html
```  

<span data-ttu-id="19e73-137">最後に、次のコード スニペットに示すように、ポップアップを `manifest.json` `browser_action` [下] に登録してください。</span><span class="sxs-lookup"><span data-stu-id="19e73-137">Finally, ensure you register the pop-up in `manifest.json` under `browser_action`, as shown in the following code snippet.</span></span>  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to display the NASA picture of the day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    },
    "browser_action": {
        "default_popup": "popup/popup.html"
    }
}
```  

## <a name="next-steps"></a><span data-ttu-id="19e73-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="19e73-138">Next steps</span></span>
<span data-ttu-id="19e73-139">これは、作業拡張機能を開発するために必要なすべてです。</span><span class="sxs-lookup"><span data-stu-id="19e73-139">That is everything you need to develop a working extension.</span></span>  <span data-ttu-id="19e73-140">次に、引き続きサイドロードを行い、拡張機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="19e73-140">Now, continue on to sideload and test your extension.</span></span> <span data-ttu-id="19e73-141">詳細については、「拡張機能を [サイドロードする」に移動します][TestExtensionSideload]。</span><span class="sxs-lookup"><span data-stu-id="19e73-141">For more information, navigate to [Sideload an extension][TestExtensionSideload].</span></span>  

<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part1/part1 "完成した拡張パッケージ ソース |Microsoft Docs"

[TestExtensionSideload]: ./extension-sideloading.md "拡張機能 (サイドローディング) のテスト|Microsoft Docs"
