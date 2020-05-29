---
description: 拡張機能の概要パート1
title: その日の NASA の絵を飛び出すシンプルな拡張機能を構築する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: dd5c1dab0cb9b54b79be7d2728cb9bfde0945185
ms.sourcegitcommit: 0bc1312a1e6a0ac37cf385201db4361fc05184fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10683624"
---
# <span data-ttu-id="c3b54-104">その日の NASA の絵を飛び出すシンプルな拡張機能を構築する</span><span class="sxs-lookup"><span data-stu-id="c3b54-104">Build A Simple Extension That Pops Up NASA Picture Of The Day</span></span>  

[<span data-ttu-id="c3b54-105">このパートの完成した拡張パッケージソース</span><span class="sxs-lookup"><span data-stu-id="c3b54-105">Completed Extension Package Source for This Part</span></span>][ArchiveExtensionGettingStartedPart1]  

## <span data-ttu-id="c3b54-106">概要</span><span class="sxs-lookup"><span data-stu-id="c3b54-106">Overview</span></span>  

<span data-ttu-id="c3b54-107">パート1では、空のディレクトリから開始する非常にシンプルな Edge Chromium 拡張機能を作成することを目標としています。</span><span class="sxs-lookup"><span data-stu-id="c3b54-107">In part 1, the goal is to build a very simple Edge Chromium Extension starting with an empty directory.</span></span>  <span data-ttu-id="c3b54-108">この拡張機能の目標は、次のタスクを実行することです。</span><span class="sxs-lookup"><span data-stu-id="c3b54-108">The goal for this Extension is to complete the following tasks.</span></span>  

*   <span data-ttu-id="c3b54-109">複数の場所で使用される可能性がある、さまざまなサイズの拡張のアイコンを作成する</span><span class="sxs-lookup"><span data-stu-id="c3b54-109">Create icons for the Extension that may be used in multiple places and in different sizes</span></span>  
*   <span data-ttu-id="c3b54-110">簡単なファイルを作成する `manifest.json`</span><span class="sxs-lookup"><span data-stu-id="c3b54-110">Create a simple `manifest.json` file</span></span>  
*   <span data-ttu-id="c3b54-111">選択されたときに、その日の NASA の画像が含まれたポップアップウィンドウを表示する起動アイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="c3b54-111">Display a launch icon that when selected displays a pop-up window containing the NASA picture of the day</span></span>  

## <span data-ttu-id="c3b54-112">マニフェストファイルの基本</span><span class="sxs-lookup"><span data-stu-id="c3b54-112">The manifest file basics</span></span>  

<span data-ttu-id="c3b54-113">すべての拡張パッケージには `manifest.json` 、ルートにファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3b54-113">Every Extension package must have a `manifest.json` file at the root.</span></span>  <span data-ttu-id="c3b54-114">これは、拡張機能の青写真と考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b54-114">You should think of this as the blueprint for the Extension.</span></span>  <span data-ttu-id="c3b54-115">この機能は、ブラウザーエンジンに、Extension が想定している拡張 API のバージョン、拡張機能の名前と説明、その他多くの詳細情報を示します。これについては、このマルチパート拡張機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3b54-115">It tells the browser engine what version of the Extension API the Extension expects, the name and description of the Extension, and lots of other details, many of which are discussed in this multi-part Extension Getting Started guide.</span></span>  

<span data-ttu-id="c3b54-116">以下は簡単</span><span class="sxs-lookup"><span data-stu-id="c3b54-116">Below is the simple</span></span>  `manifest.json`  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium Extension to show the NASA Picture of the Day."
}
```  

## <span data-ttu-id="c3b54-117">拡張機能のアイコンのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c3b54-117">Extension icons setup</span></span>  

<span data-ttu-id="c3b54-118">次に、ファイルにいくつかのアイコンを追加 `manifest.json` し `/icons` ます (アイコンファイルを使って新しいディレクトリを作成します)。</span><span class="sxs-lookup"><span data-stu-id="c3b54-118">Next add some icons to `manifest.json` file \(and create a new `/icons` directory with the icons files\).</span></span>  <span data-ttu-id="c3b54-119">アイコンは、拡張機能 \ (存在する場合) を起動するためにユーザーが選択したボタンの背景画像や、適切なその他の場所に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-119">The icons are used for the background image of the button the user selects to launch the extension \(if there is one\), and other places that are appropriate.</span></span>  

`PNG` <span data-ttu-id="c3b54-120">は推奨される形式ですが、、、、を使用することもでき `BMP` `GIF` `ICO` `JPEG` ます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-120">is the recommended format, but you may also use `BMP`, `GIF`, `ICO` and `JPEG`.</span></span>  <span data-ttu-id="c3b54-121">常に少なくとも 128 x 128 ピクセルのサイズアイコンを設定することをお勧めします。ブラウザーは必要に応じて、自動的にサイズを変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3b54-121">It is recommended to always have at least a 128x128 pixels size icon and the browser automatically resizes it as necessary.</span></span>  

<span data-ttu-id="c3b54-122">ディレクトリ構造は、次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="c3b54-122">Your directory structure should look like the following diagram.</span></span>  

<!--  
:::image type="complex" source="./media/part1-heirarchy.png" alt-text="Directory Structure":::
   Directory Structure
:::image-end:::
-->  

<!--![Directory Structure][ImagePart1Heirarchy]  -->  

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

<span data-ttu-id="c3b54-123">更新された `manifest.json` ファイルは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-123">Your updated `manifest.json` file should appear as follows.</span></span>  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to show the NASA Picture of the Day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    }
}
```  

> [!NOTE]
> <span data-ttu-id="c3b54-124">`png`このページの一番上に記載されている zip ダウンロードで、前のコードに記載されているアイコンファイルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-124">The icon `png` files listed previous code are available in the zip download mentioned at the top of this page.</span></span>  

## <span data-ttu-id="c3b54-125">既定のポップアップダイアログを追加する</span><span class="sxs-lookup"><span data-stu-id="c3b54-125">Adding a default pop-up dialog</span></span>  

<span data-ttu-id="c3b54-126">次に、 `HTML` ユーザーが拡張機能アイコンを選択したときに自動的に実行されるファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3b54-126">Now, create an `HTML` file that is automatically run when the user selects on the extension icon.</span></span>  

:::image type="complex" source="./media/part1-badge1.png" alt-text="ツールバーバッジのアイコン":::
   <span data-ttu-id="c3b54-128">ツールバーバッジのアイコン</span><span class="sxs-lookup"><span data-stu-id="c3b54-128">Toolbar Badge Icon</span></span>
:::image-end:::

<!--![Toolbar Badge Icon][ImagePart1Badge1]  -->  

<span data-ttu-id="c3b54-129">HTML ファイルには、という名前が付いてい `popup/popup.html` ます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-129">The HTML file is named `popup/popup.html`.</span></span>  <span data-ttu-id="c3b54-130">[拡張機能] アイコンを選択 `popup/popup.html` すると、ダイアログの外側にある [モーダル] ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-130">Selecting the Extension icon launches `popup/popup.html` as modal dialog that stays up until you select outside the dialog.</span></span>  

<span data-ttu-id="c3b54-131">そのためには、次のコードの下のにある [既定のポップアップとしてファイルを登録します] を選び `manifest.json` `browser_action` ます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-131">For this, register the file as a default pop-up in the `manifest.json` under `browser_action` in the following code.</span></span>  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium Extension to show the NASA Picture of the Day.",
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

<span data-ttu-id="c3b54-132">ディレクトリで、 `popup` ファイルを追加して、 `popup.html` 星の画像を表示します。</span><span class="sxs-lookup"><span data-stu-id="c3b54-132">In the `popup` directory , add the file `popup.html` and have it render the stars image.</span></span>  <span data-ttu-id="c3b54-133">ファイルを次に示し `popup.html` ます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-133">Here is the `popup.html` file.</span></span>  

```html
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>NASA Picture of the Day</title>
    </head>
    <body>
        <div>
            <img src="/images/stars.jpeg" alt="stars" />
        </div>
    </body>
</html>
```  

 <span data-ttu-id="c3b54-134">また、 `images/stars.jpeg` ファイルで参照されている画像ファイルを追加し `popup.html` ます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-134">Also, add an image file `images/stars.jpeg` that is referenced in the `popup.html` file.</span></span>  

<span data-ttu-id="c3b54-135">次の図は、この例の拡張機能のディレクトリ構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="c3b54-135">The directory structure for the example Extension is displayed in the following diagram.</span></span>  

<!--  
:::image type="complex" source="./media/part1-heirarchy1.png" alt-text="Directory Structure for Extension":::
   Directory Structure for Extension
:::image-end:::
-->  

<!--![Directory Structure for Extension][ImagePart1Heirarchy1]  -->  

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

> [!NOTE]
> <span data-ttu-id="c3b54-136">`images/stars.jpeg`前の画像に記載されているファイルは、 [zip ダウンロード][ArchiveExtensionGettingStartedPart1]で参照できます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-136">The `images/stars.jpeg` file listed in the previous image is available in the [zip download][ArchiveExtensionGettingStartedPart1].</span></span>  

<span data-ttu-id="c3b54-137">これは、機能拡張を構築するために必要なものです。</span><span class="sxs-lookup"><span data-stu-id="c3b54-137">That is everything you need to build a working Extension.</span></span>  <span data-ttu-id="c3b54-138">これまでの残りのすべてを試してください。</span><span class="sxs-lookup"><span data-stu-id="c3b54-138">All that is left to is test it.</span></span>  

<span data-ttu-id="c3b54-139">次のセクションでは、Microsoft Edge \ (Chromium) ブラウザーに拡張機能 \ (サイドローディング \ とも呼ばれます) をロードして、それをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3b54-139">The next section explains how to load the Extension \(sometimes called side loading\) into the Microsoft Edge \(Chromium\) browser to test it.</span></span>  

## <span data-ttu-id="c3b54-140">ブラウザーで拡張機能をローカルで実行する (サイドロード \)</span><span class="sxs-lookup"><span data-stu-id="c3b54-140">Run your Extension locally in your browser while developing it \(side-loading\)</span></span>  

<span data-ttu-id="c3b54-141">Microsoft Edge \ (Chromium) ブラウザーには、開発中に拡張機能をデバッグできる安全で簡単な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c3b54-141">The Microsoft Edge \(Chromium\) browser provides a safe and simple way for you to run as well as debug your Extensions while you are developing.</span></span>  

<span data-ttu-id="c3b54-142">このプロセスは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="c3b54-142">The process is quite simple.</span></span>  <span data-ttu-id="c3b54-143">まず、ブラウザーの上部にある3つの点を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b54-143">You must first select the three dots at the top of your browser.</span></span>  <span data-ttu-id="c3b54-144">次に、 `Extensions` 次の図に示すように、コンテキストメニューから選びます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-144">Next, choose `Extensions` from the context menu as shown in the following image.</span></span>  

:::image type="complex" source="./media/part1-threedots.png" alt-text="拡張機能の選択":::
   <span data-ttu-id="c3b54-146">拡張機能の選択</span><span class="sxs-lookup"><span data-stu-id="c3b54-146">Choose Extensions</span></span>
:::image-end:::

<!--![Choose Extensions][ImagePart1Threedots]  -->  

<span data-ttu-id="c3b54-147">次の図に示すように、[**拡張機能**] ページを表示している場合は、次の図に示すように、ページの左下のトグルを有効にして、**開発者モード**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c3b54-147">When you are on the **Extensions** page as shown in the following image, enable the **Developer mode** by enabling the toggle at the bottom left of the page as shown in the following image.</span></span>  

:::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="開発者モードを有効にする":::
   <span data-ttu-id="c3b54-149">開発者モードを有効にする</span><span class="sxs-lookup"><span data-stu-id="c3b54-149">Enable Developer Mode</span></span>
:::image-end:::

<!--![Enable Developer Mode][ImagePart1DevelopermodeToggle]  -->  

## <span data-ttu-id="c3b54-150">サイドロードされた拡張機能のインストールと更新</span><span class="sxs-lookup"><span data-stu-id="c3b54-150">Installing and updating side-loaded Extensions</span></span>  

<span data-ttu-id="c3b54-151">初めて拡張機能をインストールする場合は、次の画像のようなオプションを選択し `Load Unpacked` ます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-151">The first time you want to install your Extension, you choose the `Load Unpacked` option as shown in the following image.</span></span>  <span data-ttu-id="c3b54-152">これにより、ファイルによって拡張アセットファイルが保存されているディレクトリを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-152">This prompts you for a directory where you have your Extension assets file by file.</span></span>  <span data-ttu-id="c3b54-153">これにより、ストアからダウンロードした場合と同じように拡張機能がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-153">This installs the Extension as if you had downloaded it from a store.</span></span>  

:::image type="complex" source="./media/part1-installed-extension.png" alt-text="インストールされている拡張機能":::
   <span data-ttu-id="c3b54-155">インストールされている拡張機能</span><span class="sxs-lookup"><span data-stu-id="c3b54-155">Installed Extensions</span></span>
:::image-end:::

<!--![Installed Extensions][ImagePart1InstalledExtension]  -->  

<span data-ttu-id="c3b54-156">拡張機能をインストールしたら、拡張機能の一覧の下にあるボタンを選択して更新することができ `Reload` ます。</span><span class="sxs-lookup"><span data-stu-id="c3b54-156">After you install your Extension, you may update it by selecting the `Reload` button under your Extension listing.</span></span>  

<span data-ttu-id="c3b54-157">ブラウザーから拡張機能を削除するには、 `Remove` 拡張機能一覧の下部にあるボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3b54-157">To remove the Extension from your browser, click the `Remove` button on the bottom of the Extension listing.</span></span>  

## <span data-ttu-id="c3b54-158">デバッグ用の拡張機能</span><span class="sxs-lookup"><span data-stu-id="c3b54-158">Debugging Extensions</span></span>  

<span data-ttu-id="c3b54-159">拡張機能のデバッグは非常に簡単で、Edge Chromium DevTools のすべての機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c3b54-159">Debugging Extensions is quite easy and supports all of the features in Edge Chromium DevTools.</span></span>  <span data-ttu-id="c3b54-160">ただし、これらの詳細は、この「はじめに」のガイドでは説明していませんが、拡張機能を正常に構築するには非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="c3b54-160">Those details however are not covered in this getting started guide but are very important to successfully build Extensions.</span></span>  

<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: ./extension-source/extension-getting-started-part1.zip "このパーツの完成した拡張パッケージソース |Microsoft ドキュメント"  