---
description: その日の NASA の画像をポップアップする拡張機能を作成する
title: 拡張チュートリアルを作成する-パート1
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 3809bfac714621cf97184127132487ed93958a2f
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104708"
---
# <span data-ttu-id="31a9c-104">拡張チュートリアルを作成する-パート1</span><span class="sxs-lookup"><span data-stu-id="31a9c-104">Create an extension tutorial - Part 1</span></span>  

## <span data-ttu-id="31a9c-105">概要</span><span class="sxs-lookup"><span data-stu-id="31a9c-105">Overview</span></span>  

<span data-ttu-id="31a9c-106">このチュートリアルの目標は、空のディレクトリから開始する Microsoft Edge (Chromium) の拡張機能を構築することです。</span><span class="sxs-lookup"><span data-stu-id="31a9c-106">The goal for this tutorial is to build a Microsoft Edge (Chromium) extension starting with an empty directory.</span></span> <span data-ttu-id="31a9c-107">この日の NASA の画像をポップアップする拡張機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-107">We'll build an extension that pops up the NASA picture of the day.</span></span> <span data-ttu-id="31a9c-108">このチュートリアルでは、次の方法で拡張機能を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-108">In this tutorial, you'll learn how to create an extension by:</span></span>

*   <span data-ttu-id="31a9c-109">ファイルを作成する `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="31a9c-109">Creating a `manifest.json` file.</span></span>  
*   <span data-ttu-id="31a9c-110">アイコンを追加します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-110">Adding icons.</span></span>  
*   <span data-ttu-id="31a9c-111">既定のポップアップダイアログを開く。</span><span class="sxs-lookup"><span data-stu-id="31a9c-111">Opening a default pop-up dialog.</span></span>  

## <span data-ttu-id="31a9c-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="31a9c-112">Before you Begin</span></span>

<span data-ttu-id="31a9c-113">このチュートリアルで構築する完成した拡張機能をテストするには、 [ソースコード][ArchiveExtensionGettingStartedPart1]をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="31a9c-113">If you'd like to test out the completed extension that you'll build in this tutorial, download the [source code][ArchiveExtensionGettingStartedPart1].</span></span>  

## <span data-ttu-id="31a9c-114">手順 1: ファイルを作成する `manifest.json`</span><span class="sxs-lookup"><span data-stu-id="31a9c-114">Step 1: Create a `manifest.json` file</span></span>

<span data-ttu-id="31a9c-115">すべての拡張パッケージには `manifest.json` 、ルートにファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="31a9c-115">Every extension package must have a `manifest.json` file at the root.</span></span>  <span data-ttu-id="31a9c-116">マニフェストには、拡張機能の詳細、拡張機能パッケージのバージョン、拡張機能の名前と説明などが用意されています。</span><span class="sxs-lookup"><span data-stu-id="31a9c-116">The manifest provides details of your extension, the extension package version, the extension name and description, and so on.</span></span>  

<span data-ttu-id="31a9c-117">次のコードスニペットでは、ファイルに必要な基本的な情報を示して `manifest.json` います。</span><span class="sxs-lookup"><span data-stu-id="31a9c-117">The following code snippet outlines the basic information needed in your `manifest.json` file.</span></span>  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to display the NASA picture of the day."
}
```  

## <span data-ttu-id="31a9c-118">手順 2: アイコンを追加する</span><span class="sxs-lookup"><span data-stu-id="31a9c-118">Step 2: Add icons</span></span>  

<span data-ttu-id="31a9c-119">まず `icons` 、アイコンイメージファイルを格納するディレクトリをプロジェクトに作成します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-119">Start by creating the `icons` directory in your project to store the icon image files.</span></span>  <span data-ttu-id="31a9c-120">アイコンは、ユーザーが拡張機能を起動するために選択したボタンの背景画像に使用されます。</span><span class="sxs-lookup"><span data-stu-id="31a9c-120">The icons are used for the background image of the button that users select to launch the extension.</span></span>  

:::image type="complex" source="./media/part1-badge1.png" alt-text="拡張機能を開くためのツールバーのアイコン":::
   <span data-ttu-id="31a9c-122">拡張機能を開くためのツールバーのアイコン</span><span class="sxs-lookup"><span data-stu-id="31a9c-122">Icon on the toolbar to open your extension</span></span>
:::image-end:::

<span data-ttu-id="31a9c-123">アイコンの場合は、次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31a9c-123">For icons, we recommend using:</span></span> 
*   `PNG` <span data-ttu-id="31a9c-124">アイコンの書式を設定しますが、、、 `BMP` `GIF` `ICO` または形式を使用することもでき `JPEG` ます。</span><span class="sxs-lookup"><span data-stu-id="31a9c-124">format for icons, but you may also use `BMP`, `GIF`, `ICO` or `JPEG` formats.</span></span>  
*   <span data-ttu-id="31a9c-125">128 x 128 ピクセルの画像。必要に応じてブラウザーでサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="31a9c-125">Images that are 128 x 128 px, which are resized by the browser if necessary.</span></span>  

<span data-ttu-id="31a9c-126">プロジェクトのディレクトリは、次のような構造になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="31a9c-126">The directories of your project should be similar to the following structure.</span></span>   

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

<span data-ttu-id="31a9c-127">次に、ファイルにアイコンを追加 `manifest.json` します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-127">Next, add the icons to the `manifest.json` file.</span></span> <span data-ttu-id="31a9c-128">`manifest.json`次のコードスニペットと一致するように、アイコンの情報でファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-128">Update your `manifest.json` file with the icons information so that it matches the following code snippet.</span></span> <span data-ttu-id="31a9c-129">`png`次のコードに記載されているファイルは、この記事の前半で説明したダウンロードファイルで入手できます。</span><span class="sxs-lookup"><span data-stu-id="31a9c-129">The `png` files listed in the following code are available in the download file mentioned earlier in this article.</span></span>  

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

## <span data-ttu-id="31a9c-130">手順 3: 既定のポップアップダイアログを開く</span><span class="sxs-lookup"><span data-stu-id="31a9c-130">Step 3: Open a default pop-up dialog</span></span>  

<span data-ttu-id="31a9c-131">次に、 `HTML` ユーザーが拡張機能を起動したときに実行されるファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-131">Now, create a `HTML` file that's run when the user launches your extension.</span></span>  <span data-ttu-id="31a9c-132">`popup.html`という名前のディレクトリにある HTML ファイルを作成 `popup` します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-132">Create the HTML file called `popup.html` in a directory called `popup`.</span></span>  <span data-ttu-id="31a9c-133">ユーザーが拡張機能を起動するためにアイコンを選択すると、 `popup/popup.html` モーダルダイアログとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="31a9c-133">When users select the icon to launch the extension, `popup/popup.html` is displayed as a modal dialog.</span></span>  

<span data-ttu-id="31a9c-134">次のコードスニペットから、星の画像を表示するコードを追加し `popup.html` ます。</span><span class="sxs-lookup"><span data-stu-id="31a9c-134">Add the code from the following code snippet to `popup.html` to display the stars image.</span></span>  

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

<span data-ttu-id="31a9c-135">画像ファイルを `images/stars.jpeg` images フォルダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-135">Ensure that you add the image file `images/stars.jpeg` to the images folder.</span></span>  <span data-ttu-id="31a9c-136">プロジェクトのディレクトリは、次のような構造になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="31a9c-136">The directories of your project should be similar to the following structure.</span></span>   

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

<span data-ttu-id="31a9c-137">最後に、 `manifest.json` `browser_action` 次のコードスニペットに示すように、でポップアップを登録していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31a9c-137">Finally, ensure you register the pop-up in `manifest.json` under `browser_action`, as shown in the following code snippet.</span></span>  

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

## <span data-ttu-id="31a9c-138">次のステップ</span><span class="sxs-lookup"><span data-stu-id="31a9c-138">Next steps</span></span>
<span data-ttu-id="31a9c-139">これは、作業拡張機能を開発するために必要なものです。</span><span class="sxs-lookup"><span data-stu-id="31a9c-139">That's everything you need to develop a working extension.</span></span> <span data-ttu-id="31a9c-140">次に、サイドローディングに進み、拡張機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="31a9c-140">Now, continue on to sideload and test your extension.</span></span> <span data-ttu-id="31a9c-141">詳細については、「 [サイドローディングの拡張機能][TestExtensionSideload]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31a9c-141">For more information, see [Sideload an extension][TestExtensionSideload].</span></span>  


<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part1/part1 "完成した拡張パッケージソース |Microsoft ドキュメント"

[TestExtensionSideload]: ./extension-sideloading.md "拡張機能をテストする (サイドローディング) |Microsoft ドキュメント"
