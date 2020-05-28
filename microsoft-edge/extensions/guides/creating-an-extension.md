---
description: Microsoft Edge 拡張機能を作成する方法について説明します。
title: 内線番号を作成する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: a08fc6bd604ce810895e7103f7f6384dbedc9f78
ms.sourcegitcommit: 0bc1312a1e6a0ac37cf385201db4361fc05184fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10683652"
---
# <span data-ttu-id="c88f8-104">Microsoft Edge 拡張機能の作成</span><span class="sxs-lookup"><span data-stu-id="c88f8-104">Creating A Microsoft Edge Extension</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="c88f8-105">このガイドでは、Microsoft Edge 用の拡張機能を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-105">In this guide, learn to create an extension for Microsoft Edge.</span></span>  <span data-ttu-id="c88f8-106">この例の拡張機能を使用すると、マニフェストファイル、ユーザーインターフェイス、バックグラウンドおよびコンテンツスクリプトの作成を[docs.microsoft.com][MicrosoftDocs]するなど、特定の CSS を操作することができます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-106">This example extension allows you to manipulate specific CSS for [docs.microsoft.com][MicrosoftDocs] pages including walking you through creation of a manifest file, the user interface, and background and content scripts.</span></span>  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.com 本文が青に変更されました":::
   <span data-ttu-id="c88f8-108">Docs.microsoft.com 本文が青に変更されました</span><span class="sxs-lookup"><span data-stu-id="c88f8-108">Docs.microsoft.com body changed to blue</span></span>
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

<span data-ttu-id="c88f8-109">このチュートリアルでは、ブラウザーの拡張機能の概要とそのしくみについて、基本的に理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c88f8-109">This tutorial assumes you have basic understanding of what a browser extension is and how it work.</span></span>  <span data-ttu-id="c88f8-110">拡張機能の構築要素について詳しくは、「[拡張機能の構造][MDNAnatomyExtension]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-110">For more imformation about the building blocks for extensions, see [Anatomy of an extension][MDNAnatomyExtension].</span></span>  

<span data-ttu-id="c88f8-111">[GitHub の完全なサンプル][GithubMicrosoftEdgeExtensionsDemosColorChanger]コードをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-111">Download the code for the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="c88f8-112">マニフェストファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="c88f8-112">Building the manifest file</span></span>  

<span data-ttu-id="c88f8-113">開始するには、拡張機能用のディレクトリを作成し、名前を付ける必要が `color-changer` あります。</span><span class="sxs-lookup"><span data-stu-id="c88f8-113">To begin, create a directory for your extension and name it `color-changer`.</span></span>  

<span data-ttu-id="c88f8-114">フォルダー内 `color-changer` で、という名前のファイルを作成し `manifest.json` ます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-114">Inside the `color-changer` folder, create a file named `manifest.json`.</span></span>  <span data-ttu-id="c88f8-115">`manifest.json`ファイルはすべての拡張機能に必要であり、拡張機能の名前からアクセス許可までの重要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-115">The `manifest.json` file is required for all extensions and provides important information for the extension, ranging from the extension name to the permissions.</span></span>  

> [!NOTE] 
> <span data-ttu-id="c88f8-116">このガイドでは、このガイドで使用する必要があるすべてのマニフェストキーについて説明しますが、サポートされているすべてのマニフェストキーと推奨マニフェストキーの一覧については、「[サポートされているマニフェストキー][ExtensionsApisupportManifestKeys]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-116">This guide walks you through all the manifest keys you must use in this guide, but for a list of all supported and recommended manifest keys, see [Supported manifest keys][ExtensionsApisupportManifestKeys].</span></span>  

<span data-ttu-id="c88f8-117">内部 `manifest.json` に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-117">Inside `manifest.json`, add the following code.</span></span>  

```json
{
  "name": "Color Changer",
  "author": "Microsoft Edge Extension Developer",
  "version": "1.0",
  "description": "Change the color of the body on docs.microsoft.com",
  "permissions": [
    "*://docs.microsoft.com/*",
    "tabs"
  ], 
  "browser_action": {
    "default_icon": {
      "20": "images/color-changer20.png",
      "40": "images/color-changer40.png"
    },
    "default_title": "Color Changer",
    "default_popup": "popup.html"
  }
}
```  

### <span data-ttu-id="c88f8-118">マニフェストキーの定義</span><span class="sxs-lookup"><span data-stu-id="c88f8-118">Manifest key definitions</span></span>  

| <span data-ttu-id="c88f8-119">Key</span><span class="sxs-lookup"><span data-stu-id="c88f8-119">Key</span></span> | <span data-ttu-id="c88f8-120">詳細</span><span class="sxs-lookup"><span data-stu-id="c88f8-120">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="c88f8-121">name</span><span class="sxs-lookup"><span data-stu-id="c88f8-121">name</span></span>][MDNManifestjsonName] | <span data-ttu-id="c88f8-122">拡張機能の名前。</span><span class="sxs-lookup"><span data-stu-id="c88f8-122">The name of the extension.</span></span>  |  
| [<span data-ttu-id="c88f8-123">著作者</span><span class="sxs-lookup"><span data-stu-id="c88f8-123">author</span></span>][MDNManifestjsonAuthor] | <span data-ttu-id="c88f8-124">内線番号の作成者。</span><span class="sxs-lookup"><span data-stu-id="c88f8-124">The author of the extension.</span></span>  |  
| [<span data-ttu-id="c88f8-125">version</span><span class="sxs-lookup"><span data-stu-id="c88f8-125">version</span></span>][MDNManifestjsonVersion] | <span data-ttu-id="c88f8-126">拡張機能のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="c88f8-126">The extension version number.</span></span>  |  
| [<span data-ttu-id="c88f8-127">description</span><span class="sxs-lookup"><span data-stu-id="c88f8-127">description</span></span>][MDNManifestjsonDescription] | <span data-ttu-id="c88f8-128">Microsoft Edge の [拡張] メニューの [バージョン情報] セクションに表示される拡張機能の説明です。</span><span class="sxs-lookup"><span data-stu-id="c88f8-128">The description of the extension displayed in the About section of the extension menu in Microsoft Edge.</span></span>  |  
| [<span data-ttu-id="c88f8-129">権限</span><span class="sxs-lookup"><span data-stu-id="c88f8-129">permissions</span></span>][MDNManifestjsonPermissions] | <span data-ttu-id="c88f8-130">拡張子のアクセス許可を要求する文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="c88f8-130">An array of strings requesting permissions for the extension.</span></span>  <span data-ttu-id="c88f8-131">お客様の内線番号については、アクセス許可を要求している web サイトが表示され `*://docs.microsoft.com/*` ます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-131">For your extension, you are requesting permissions to see the websites visited \("tabs"\) and to update content on URLs matching "`*://docs.microsoft.com/*`".</span></span>  |  
| [<span data-ttu-id="c88f8-132">browser_action</span><span class="sxs-lookup"><span data-stu-id="c88f8-132">browser_action</span></span>][MDNManifestjsonBrowserAction] | <span data-ttu-id="c88f8-133">アイコンの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c88f8-133">Contains the information for an icon.</span></span> <span data-ttu-id="c88f8-134">アイコンは、Microsoft Edge ツールバーのアドレスバーの右側に配置されます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-134">The icon is placed on the Microsoft Edge toolbar, to the right of the address bar.</span></span>  |  

#### <span data-ttu-id="c88f8-135">browser_action キーの定義</span><span class="sxs-lookup"><span data-stu-id="c88f8-135">browser_action Key definitions</span></span>  

| <span data-ttu-id="c88f8-136">Key</span><span class="sxs-lookup"><span data-stu-id="c88f8-136">Key</span></span> | <span data-ttu-id="c88f8-137">詳細</span><span class="sxs-lookup"><span data-stu-id="c88f8-137">Details</span></span> |  
|:--- |:--- |  
| `default_icon` | <span data-ttu-id="c88f8-138">ツールバーで使用されるアイコン。</span><span class="sxs-lookup"><span data-stu-id="c88f8-138">The icon that is used in the toolbar.</span></span>  |  
| `default_title` | <span data-ttu-id="c88f8-139">ユーザーがツールバーのアイコンの上にマウスポインターを置いたときに表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="c88f8-139">The text that is displayed when a user hovers over the icon in the toolbar.</span></span>  |  
| `default_popup` | <span data-ttu-id="c88f8-140">ポップアップウィンドウの HTML ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="c88f8-140">The path to the HTML file for the pop-up window.</span></span>  |  

<span data-ttu-id="c88f8-141">マニフェストファイルを作成したので、拡張機能のユーザーインターフェイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c88f8-141">Now that you have created the manifest file, you need a user interface for the extension.</span></span>  

## <span data-ttu-id="c88f8-142">ポップアップの作成</span><span class="sxs-lookup"><span data-stu-id="c88f8-142">Creating the pop-up</span></span>  

<span data-ttu-id="c88f8-143">拡張機能については、次のように、ユーザーインターフェイス用のポップアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-143">For your extension, create a pop-up for the user interface, like below.</span></span>  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="拡張機能のポップアップインターフェイス":::
   <span data-ttu-id="c88f8-145">拡張機能のポップアップインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c88f8-145">The pop-up interface of the extension</span></span>
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

<span data-ttu-id="c88f8-146">フォルダーのルートに、という名前のファイルを作成 `popup.html` `color-changer` します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-146">Create a file named `popup.html` in the root of your `color-changer` folder.</span></span>  <span data-ttu-id="c88f8-147">次のコードを貼り付け `popup.html` ます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-147">Paste the following code into `popup.html`.</span></span>  

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" type="text/css" href="css/styles.css" />
    </head>
    <body>
        <h1>Creating a Microsoft Edge Extension</h1>
        <p>Color Changer</p>
        <input id="aliceblue" type="button" value="Aliceblue" />
        <input id="cornsilk" type="button" value="Cornsilk" />
        <input id="reset" type="button" value="Reset" />
        <script src="js/popup.js"></script>
    </body>
</html>
```  

<span data-ttu-id="c88f8-148">では、 `popup.html` タイトル、段落、3つのボタン \ (Aliceblue、Cornsilk、および Reset \) を作成します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-148">In `popup.html`, you create a title, a paragraph, and three buttons \(Aliceblue, Cornsilk, and Reset\).</span></span>  

<span data-ttu-id="c88f8-149">次に、という名前のフォルダーを作成して、という名前 `css` のファイルを作成し `styles.css` ます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-149">Now create a folder named `css` and inside create a file named `styles.css`.</span></span>  <span data-ttu-id="c88f8-150">以下のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-150">Add the styles below.</span></span>  

```css
/* main styles */
* {
    font-family: 'Segoe UI';
}

h1 {
    font-weight: 600;
    font-size: .9em;
}

p {
    font-weight: 500;
    font-size: .8em;
    margin-bottom: 10px;  
}
```  

<span data-ttu-id="c88f8-151">この CSS には、拡張機能がいくつかの基本的なスタイルで用意されています。</span><span class="sxs-lookup"><span data-stu-id="c88f8-151">This CSS gives our extension some basic styles.</span></span>  <span data-ttu-id="c88f8-152">さらにスタイルを追加して、拡張機能をカスタマイズしてください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-152">Feel free to add more styles to customize your extension.</span></span>  

<span data-ttu-id="c88f8-153">次に、ポップアップと連携する JavaScript ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c88f8-153">Next, you must create the JavaScript file that interacts with the pop-up.</span></span>  <span data-ttu-id="c88f8-154">フォルダーと、in と `js` いう名前のファイルを作成 `popup.js` します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-154">Create a `js` folder and a file named `popup.js` inside.</span></span>  <span data-ttu-id="c88f8-155">`popup.js`次のコードを使用して更新します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-155">Update `popup.js` with the following code.</span></span>  

```JavaScript
// get the buttons by id
let aliceblue = document.getElementById('aliceblue');
let cornsilk = document.getElementById('cornsilk');
let reset = document.getElementById('reset');

// use tabs.insertCSS to change header color on button click

// aliceblue
aliceblue.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: aliceblue !important; }"});
};

// cornsilk
cornsilk.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: cornsilk !important; }"});
};

// back to original
reset.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: none !important; }"});
};
```  

<span data-ttu-id="c88f8-156">の `popup.js` [タブ][MDNApiTabs]API では、ブラウザーのタブを操作したり、スクリプトとスタイルをページコンテンツに挿入したりできます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-156">In `popup.js`, the [tabs][MDNApiTabs] API allows you to interact with the tabs of the browser and inject script and styles into the page content.</span></span>  <span data-ttu-id="c88f8-157">[Tabs css ()][MDNApiTabsInsertcss]メソッドを使用して、指定した css をページに挿入して、指定したボタンをクリックしたときに[docs.microsoft.com][MicrosoftDocs]のヘッダーを別の色に変更します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-157">Using the [tabs.insertCSS()][MDNApiTabsInsertcss] method, you inject the specified CSS into the page which changes the header on [docs.microsoft.com][MicrosoftDocs] to a different color when the specified button is clicked.</span></span>  

<span data-ttu-id="c88f8-158">基本的なポップアップ機能を使用したので、拡張機能にアイコンを追加します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-158">Now that you have the basic pop-up functionality, add icons to the extension.</span></span>  

## <span data-ttu-id="c88f8-159">アイコンの追加</span><span class="sxs-lookup"><span data-stu-id="c88f8-159">Adding icons</span></span>  

<span data-ttu-id="c88f8-160">アイコンは、ブラウザーのツールバー、[拡張機能] メニュー、その他の場所で拡張機能を表すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-160">Icons are used to represent the extension in the browser toolbar, the extensions menu, and other places.</span></span>  <span data-ttu-id="c88f8-161">GitHub の[拡張機能のアイコン][GithubMicrosoftEdgeExtensionsDemosColorChangerImages]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c88f8-161">Download the [icons for your extension on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChangerImages].</span></span> <span data-ttu-id="c88f8-162">Microsoft Edge の拡張機能アイコンの詳細については、「[デザインガイド][ExtensionsGuidesDesignIcons]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-162">For more information about extension icons in Microsoft Edge, see [Design Guide][ExtensionsGuidesDesignIcons].</span></span>  

<span data-ttu-id="c88f8-163">拡張機能のアイコンをダウンロードしたら、その中のフォルダーにアイコンを保存し `images` `color-changer` ます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-163">After you download the extension icons, save the icons in an `images` folder inside `color-changer`.</span></span>  

<span data-ttu-id="c88f8-164">ツールバーに表示されるアイコンは、 `default_icon` 前のセクションで既にマニフェストファイルに追加した[browser_action][MDNManifestjsonBrowserAction]キーの内部で設定されています。</span><span class="sxs-lookup"><span data-stu-id="c88f8-164">The icon that appears in the toolbar is set using `default_icon` inside of the [browser_action][MDNManifestjsonBrowserAction] key, which you already added to your manifest file in an earlier section.</span></span>  

<span data-ttu-id="c88f8-165">この `icons` キーは、[拡張設定] メニューで使用するアイコンを定義します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-165">The `icons` key defines which icons should be used in the Extensions settings menus.</span></span>  <span data-ttu-id="c88f8-166">次に、異なるサイズの複数のアイコンを指定して、さまざまな画面解像度を考慮します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-166">Below, you are specifying multiple icons with different sizes to account for different screen resolutions.</span></span>  <span data-ttu-id="c88f8-167">アイコンの名前 `25` `48` 。アイコンの高さ (ピクセル単位) です。</span><span class="sxs-lookup"><span data-stu-id="c88f8-167">The name of the icons, `25` and `48` are the heights in pixels of the icons.</span></span>  

<span data-ttu-id="c88f8-168">[Manifest.xml][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]ファイルで、の最上位レベルのキーを含め `icons` ます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-168">In the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file, include a top-level key for `icons`.</span></span>  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### <span data-ttu-id="c88f8-169">マニフェストキーの定義</span><span class="sxs-lookup"><span data-stu-id="c88f8-169">Manifest Key definitions</span></span>  

| <span data-ttu-id="c88f8-170">Key</span><span class="sxs-lookup"><span data-stu-id="c88f8-170">Key</span></span> | <span data-ttu-id="c88f8-171">詳細</span><span class="sxs-lookup"><span data-stu-id="c88f8-171">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="c88f8-172">アイコン</span><span class="sxs-lookup"><span data-stu-id="c88f8-172">icons</span></span>][MDNManifestjsonIcons] | <span data-ttu-id="c88f8-173">拡張子の `px` ルートディレクトリを基準とした、イメージのサイズとイメージのパスのキーと値のペアのアイコン。</span><span class="sxs-lookup"><span data-stu-id="c88f8-173">The icons for your extension with key-value pairs of image size in `px` and image path relative to the root directory of the extension.</span></span> |  

> [!NOTE]
> <span data-ttu-id="c88f8-174">`inactive##.png`このガイドで後述する images フォルダーの下にあるアイコンを使用します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-174">Use the icons named `inactive##.png` located in the images folder later in this guide.</span></span>  

## <span data-ttu-id="c88f8-175">拡張機能のテスト</span><span class="sxs-lookup"><span data-stu-id="c88f8-175">Testing the extension</span></span>  

<span data-ttu-id="c88f8-176">これで、ユーザーインターフェイスと作成したアイコンが追加されました。拡張機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="c88f8-176">Now that you have added the user interface and created icons, test your extension.</span></span>  <span data-ttu-id="c88f8-177">Microsoft Edge に[拡張機能を追加][ExtensionsGuidesAddingRemovingExtensionsAdding]するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-177">Walk through the steps for [Adding an extension][ExtensionsGuidesAddingRemovingExtensionsAdding] to Microsoft Edge.</span></span>  <span data-ttu-id="c88f8-178">その後、このガイドに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c88f8-178">Afterwards, return to this guide.</span></span>  

<span data-ttu-id="c88f8-179">拡張機能を追加した後で、任意の[docs.microsoft.com][MicrosoftDocs]ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-179">After you add your extension, navigate to any [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="c88f8-180">ブラウザーの操作をクリックすると、次のポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-180">You should see the following pop-up after clicking on the browser action.</span></span>  <span data-ttu-id="c88f8-181">[Docs.microsoft.com][MicrosoftDocs]本文の色も色を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c88f8-181">The color of the [docs.microsoft.com][MicrosoftDocs] body should also change color.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.com ヘッダーが Aliceblue に変更されました":::
         <span data-ttu-id="c88f8-183">Docs.microsoft.com ヘッダーが Aliceblue に変更されました</span><span class="sxs-lookup"><span data-stu-id="c88f8-183">Docs.microsoft.com header changed to Aliceblue</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.com ヘッダーが Cornsilk に変更されました":::
         <span data-ttu-id="c88f8-185">Docs.microsoft.com ヘッダーが Cornsilk に変更されました</span><span class="sxs-lookup"><span data-stu-id="c88f8-185">Docs.microsoft.com header changed to Cornsilk</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

<span data-ttu-id="c88f8-186">機能しないエラーや機能が発生した場合は、「[デバッグ拡張機能][ExtensionsGuidesDebuggingExtensions]ガイド」または「 [GitHub の完全なサンプル][GithubMicrosoftEdgeExtensionsDemosColorChanger]をダウンロードする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-186">If you encounter any errors or functionality that does not work, see the [Debugging extensions][ExtensionsGuidesDebuggingExtensions] guide or download the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="c88f8-187">コンテンツとバックグラウンドスクリプトの追加</span><span class="sxs-lookup"><span data-stu-id="c88f8-187">Adding content and background scripts</span></span>  

<span data-ttu-id="c88f8-188">さらに一歩進んで、 [docs.microsoft.com][MicrosoftDocs]ドメイン以外のページで機能しないようにするためのロジックを追加します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-188">Go one step further and add logic to disable the extension from working on pages outside the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  

<span data-ttu-id="c88f8-189">まず、[コンテンツスクリプト][MDNContentScripts]を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c88f8-189">You must first create a [content script][MDNContentScripts].</span></span>  <span data-ttu-id="c88f8-190">次に、特定の web ページのコンテキストで実行されるコンテンツスクリプトを作成して、web ページのコンテンツにアクセスできるようにし、バックグラウンドスクリプトと通信できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c88f8-190">Next, you must create content scripts that run in the context of a particular web page, are able to access the content of a web page, and are able to communicate with background scripts.</span></span>  <span data-ttu-id="c88f8-191">`js`ディレクトリ内で、という名前のファイルを作成 `content.js` し、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-191">Inside of your `js` directory, create a file named `content.js` and add the following code.</span></span>  

```javascript
// get the URL of the page
var url = document.location.href;

// if not on a docs.microsoft.com domain
if (url.indexOf("//docs.microsoft.com") === -1) {
    // send inactive icons
    browser.runtime.sendMessage({
        "iconPath20": "images/inactive20.png",
        "iconPath40": "images/inactive40.png"
    });
}
```  

<span data-ttu-id="c88f8-192">このスクリプトは、現在のページの URL を取得 `document.location.href` し、現在のページが[docs.microsoft.com][MicrosoftDocs]ドメインにあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-192">This script gets the URL of the current page through `document.location.href` and verifies whether the current page is on the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  <span data-ttu-id="c88f8-193">ページが[docs.microsoft.com][MicrosoftDocs]ドメインにない場合 ( [https://www.bing.com/][|::ref1::|] \ など)、非アクティブアイコン (灰色のアイコン) へのパスは、 [sendMessage ()][MDNApiRuntimeSendmessage]を使ってバックグラウンドスクリプトに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-193">If the page is not on the [docs.microsoft.com][MicrosoftDocs] domain \(for example  [https://www.bing.com/][|::ref1::|]\), the paths to the inactive icons \(grayed out icons\) are sent to the background script using [runtime.sendMessage()][MDNApiRuntimeSendmessage].</span></span>  

<span data-ttu-id="c88f8-194">次のキーを含めるには、 [manifest.xml][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]ファイルを更新する必要があります。 `content_scripts`</span><span class="sxs-lookup"><span data-stu-id="c88f8-194">You must update the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file to include the following `content_scripts` key.</span></span>  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### <span data-ttu-id="c88f8-195">マニフェストキーの定義</span><span class="sxs-lookup"><span data-stu-id="c88f8-195">Manifest Key definitions</span></span>  

| <span data-ttu-id="c88f8-196">Key</span><span class="sxs-lookup"><span data-stu-id="c88f8-196">Key</span></span> | <span data-ttu-id="c88f8-197">詳細</span><span class="sxs-lookup"><span data-stu-id="c88f8-197">Details</span></span> |  
|:--- |:---- |  
| [<span data-ttu-id="c88f8-198">content_scripts</span><span class="sxs-lookup"><span data-stu-id="c88f8-198">content_scripts</span></span>][MDNManifestjsonContentScripts] | <span data-ttu-id="c88f8-199">ブラウザーが読み込むコンテンツスクリプトに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c88f8-199">Contains the information about which content scripts the browser should load.</span></span> |  

#### <span data-ttu-id="c88f8-200">content_scripts キーの定義</span><span class="sxs-lookup"><span data-stu-id="c88f8-200">content_scripts Key definitions</span></span>  

| <span data-ttu-id="c88f8-201">Key</span><span class="sxs-lookup"><span data-stu-id="c88f8-201">Key</span></span> | <span data-ttu-id="c88f8-202">詳細</span><span class="sxs-lookup"><span data-stu-id="c88f8-202">Details</span></span> |  
|:--- |:---- |  
| `matches` <span data-ttu-id="c88f8-203">\ (必須 \)</span><span class="sxs-lookup"><span data-stu-id="c88f8-203">\(required\)</span></span> | <span data-ttu-id="c88f8-204">コンテンツスクリプトを読み込む前に照合する URL パターン。</span><span class="sxs-lookup"><span data-stu-id="c88f8-204">The URL pattern to match prior to loading the content script.</span></span> |  
| `js` | <span data-ttu-id="c88f8-205">一致する Url に読み込む必要があるスクリプト。</span><span class="sxs-lookup"><span data-stu-id="c88f8-205">The script that should be loaded on matching URLs.</span></span> |  
| `run_at` | <span data-ttu-id="c88f8-206">キーからの JavaScript ファイルを挿入する場所を指定し `js` ます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-206">Specifies where the JavaScript files from the `js` key are injected.</span></span> |  

<span data-ttu-id="c88f8-207">次に、[バックグラウンドスクリプト][MDNAnatomyExtensionBackgroundScripts]を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c88f8-207">Next, you must create a [background script][MDNAnatomyExtensionBackgroundScripts].</span></span>  <span data-ttu-id="c88f8-208">バックグラウンドスクリプトは、ブラウザーのバックグラウンドで実行され、web ページまたはブラウザーウィンドウの有効期間とは無関係に動作し、コンテンツスクリプトと通信できます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-208">Background scripts run in the background of the browser, run independently of the lifetime of a web page or browser window, and are able to communicate with content scripts.</span></span>  

<span data-ttu-id="c88f8-209">`js`フォルダー内で、という名前のファイルを作成 `background.js` し、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-209">Inside of your `js` folder, create a file named `background.js` and add the following code.</span></span>  

```javascript
// listen for sendMessage() from content script
browser.runtime.onMessage.addListener(
    function (request, sender, sendResponse) {
        // set the icon for the browser action from sendMessage() in content script
        browser.browserAction.setIcon({
            path: {
                "20": request.iconPath20,
                "40": request.iconPath40
            },
            tabId: sender.tab.id
        });
        // disable browser action for the current tab
        browser.browserAction.disable(sender.tab.id);
    });
```  

<span data-ttu-id="c88f8-210">[OnMessage][MDNApiRuntimeOnmessage]メソッドは、コンテンツスクリプトから[実行時の sendMessage ()][MDNApiRuntimeSendmessage]をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="c88f8-210">The [runtime.onMessage][MDNApiRuntimeOnmessage] method listens for [runtime.sendMessage()][MDNApiRuntimeSendmessage] from the content script.</span></span>  <span data-ttu-id="c88f8-211">ページのドメインが[docs.microsoft.com][MicrosoftDocs]ではない場合、 [setIcon ()][MDNApiBrowseractionSeticon]メソッドは、非アクティブな画像へのアイコンパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-211">If the domain of the page is not [docs.microsoft.com][MicrosoftDocs], then [browserAction.setIcon()][MDNApiBrowseractionSeticon] method sets the icon paths to the inactive images.</span></span>  

<span data-ttu-id="c88f8-212">このスクリプトでは、ブラウザーのアクション \ ([Browseraction][MDApiBrowseractionDisable]) を無効にして、ユーザーが[docs.microsoft.com][MicrosoftDocs]ページ以外でブラウザーの操作をクリックできないようにします。</span><span class="sxs-lookup"><span data-stu-id="c88f8-212">The script also disables the browser action \([browserAction.disable][MDApiBrowseractionDisable]\), so that users are not able to click on the browser action outside of a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  

<span data-ttu-id="c88f8-213">[マニフェスト][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]ファイルにバックグラウンドスクリプトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c88f8-213">You must add the background script to the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file.</span></span>  <span data-ttu-id="c88f8-214">`background`マニフェストに次のキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-214">Add the following `background` key to your manifest.</span></span>  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### <span data-ttu-id="c88f8-215">マニフェストキーの定義</span><span class="sxs-lookup"><span data-stu-id="c88f8-215">Manifest Key definitions</span></span>  

| <span data-ttu-id="c88f8-216">Key</span><span class="sxs-lookup"><span data-stu-id="c88f8-216">Key</span></span> | <span data-ttu-id="c88f8-217">詳細</span><span class="sxs-lookup"><span data-stu-id="c88f8-217">Details</span></span>|  
|:--- |:--- |  
| [<span data-ttu-id="c88f8-218">背景</span><span class="sxs-lookup"><span data-stu-id="c88f8-218">background</span></span>][MDNManifestjsonBackground] | <span data-ttu-id="c88f8-219">バックグラウンドスクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c88f8-219">Contains the background scripts.</span></span> |  

#### <span data-ttu-id="c88f8-220">バックグラウンドキーの定義</span><span class="sxs-lookup"><span data-stu-id="c88f8-220">background Key definitions</span></span>  

| <span data-ttu-id="c88f8-221">Key</span><span class="sxs-lookup"><span data-stu-id="c88f8-221">Key</span></span> | <span data-ttu-id="c88f8-222">詳細</span><span class="sxs-lookup"><span data-stu-id="c88f8-222">Details</span></span> |  
|:--- |:--- |  
| `scripts` | <span data-ttu-id="c88f8-223">JavaScript ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="c88f8-223">The path to a JavaScript file.</span></span> |  
| `persistent` <span data-ttu-id="c88f8-224">(必須)</span><span class="sxs-lookup"><span data-stu-id="c88f8-224">(required)</span></span> | <span data-ttu-id="c88f8-225">これは、またはに設定する必要があり `true` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-225">This must be set to `true` or `false`.</span></span>  <span data-ttu-id="c88f8-226">をに設定する `true` と、バックグラウンドスクリプトが読み込まれ、閲覧セクション全体に対して保持されます。</span><span class="sxs-lookup"><span data-stu-id="c88f8-226">If set to `true`, the background script is loaded and persists for the entire browsing section.</span></span>  <span data-ttu-id="c88f8-227">がに設定 `false` されている場合は、バックグラウンドスクリプトに遅延が含まれており、閲覧セッションのために存続します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-227">If set to `false`, the background script is loaded with a delay and persists for the browsing session.</span></span> |  

<span data-ttu-id="c88f8-228">延長をリロードして、もう一度テストしてください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-228">Reload your extension and test again.</span></span>  <span data-ttu-id="c88f8-229">拡張機能を再ロードするには: [設定] の [詳細] をクリックします。 Microsoft Edge の場合**は、[** **拡張機能**] をクリックし、拡張機能 \ (**カラーチェンジャー**\) をクリックし、[**拡張機能の再読み込み**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88f8-229">To reload your extension: click the **...** for settings and more in Microsoft Edge, click **Extensions**, click on your extension \(**Color Changer**\), and click **Reload extension**.</span></span>  

<span data-ttu-id="c88f8-230">次に、新しいタブを開くか、 [docs.microsoft.com][MicrosoftDocs]ページではない既存のタブを更新します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-230">Now, open a new tab or refresh an existing tab that is not a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="c88f8-231">[非アクティブ] アイコンが表示され、ブラウザーのアクションをクリックできません。</span><span class="sxs-lookup"><span data-stu-id="c88f8-231">You should see the inactive icon and not be able to click on the browser action.</span></span>  

<span data-ttu-id="c88f8-232">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="c88f8-232">Congratulations!</span></span>  <span data-ttu-id="c88f8-233">Microsoft Edge 用の拡張機能を作成しました。</span><span class="sxs-lookup"><span data-stu-id="c88f8-233">You created an extension for Microsoft Edge!</span></span>  <span data-ttu-id="c88f8-234">[GitHub の完全なサンプル][GithubMicrosoftEdgeExtensionsDemosColorChanger]を表示します。</span><span class="sxs-lookup"><span data-stu-id="c88f8-234">View the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  <span data-ttu-id="c88f8-235">拡張機能の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-235">Continue reading to learn more about extensions.</span></span>  

## <span data-ttu-id="c88f8-236">より複雑な拡張機能の作成</span><span class="sxs-lookup"><span data-stu-id="c88f8-236">Writing a more complex extension</span></span>  

<span data-ttu-id="c88f8-237">より複雑な拡張子を作成したい場合</span><span class="sxs-lookup"><span data-stu-id="c88f8-237">Want to write a more complex extension?</span></span>  <span data-ttu-id="c88f8-238">[2 つ目の拡張機能][MDNYourSecondWebextension]である、記事の MDN の Beastify extension を見てみてください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-238">Take a look at the Beastify extension on MDN in the article, [Your second extension][MDNYourSecondWebextension].</span></span>  <span data-ttu-id="c88f8-239">Microsoft Edge の拡張モデルは Firefox の拡張モデルとは少し異なります。[第2の拡張機能][MDNYourSecondWebextension]で作成された Beastify extension は、microsoft edge で機能するように調整されています。</span><span class="sxs-lookup"><span data-stu-id="c88f8-239">The extension model for Microsoft Edge differs slightly from the extension model for Firefox, the Beastify extension created in [Your second extension][MDNYourSecondWebextension] was adapted to function in Microsoft Edge.</span></span>  <span data-ttu-id="c88f8-240">[GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify]で確認してください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-240">Check it out on [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify].</span></span>  

<span data-ttu-id="c88f8-241">MDN の記事をウォークしながら、 [2 つ目の拡張機能][MDNYourSecondWebextension]については、次のセクションを念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-241">While walking through the article on MDN, [Your second extension][MDNYourSecondWebextension], keep in mind the following sections.</span></span>  

### <span data-ttu-id="c88f8-242">API</span><span class="sxs-lookup"><span data-stu-id="c88f8-242">APIs</span></span>  

<span data-ttu-id="c88f8-243">Microsoft Edge でサポートされている拡張機能 Api の一覧については、「[サポートされている api][ExtensionsAPIsupportApis] 」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-243">See the [Supported APIs][ExtensionsAPIsupportApis] page for a list of supported extensions APIs in Microsoft Edge.</span></span>  

### <span data-ttu-id="c88f8-244">アイコンのサイズ</span><span class="sxs-lookup"><span data-stu-id="c88f8-244">Icon sizes</span></span>  

<span data-ttu-id="c88f8-245">Microsoft Edge の優先拡張機能アイコンのサイズは、、、、 `20px` `25px` `30px` `40px` です。</span><span class="sxs-lookup"><span data-stu-id="c88f8-245">Preferred extension icon sizes for Microsoft Edge are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="c88f8-246">サポートされているその他のサイズは、、、 `19px` `35px` `38px` です。</span><span class="sxs-lookup"><span data-stu-id="c88f8-246">Other supported sizes are `19px`, `35px`, and `38px`.</span></span>  <span data-ttu-id="c88f8-247">アイコンのサイズとベストプラクティスの詳細については、[設計][ExtensionsGuidesDesign]ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-247">For more info on icon sizes and best practices, see the [Design][ExtensionsGuidesDesign] guide.</span></span>  

### <span data-ttu-id="c88f8-248">JavaScript</span><span class="sxs-lookup"><span data-stu-id="c88f8-248">JavaScript</span></span>  

<span data-ttu-id="c88f8-249">Microsoft Edge の拡張モデルでは、JavaScript の約束はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c88f8-249">The extension model for Microsoft Edge does not support JavaScript Promises.</span></span>  <span data-ttu-id="c88f8-250">代わりに、コールバックを使います。</span><span class="sxs-lookup"><span data-stu-id="c88f8-250">Instead, use callbacks.</span></span>  <span data-ttu-id="c88f8-251">拡張機能でコールバックを使う方法の例については、「[クイック印刷][GithubMicrosoftEdgeExtensionsDemosQuickPrint]と[テキスト交換][GithubMicrosoftEdgeExtensionsDemosTextSwap]のデモ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-251">For more examples of using callbacks in an extension, take a look at the  [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] and [Text Swap][GithubMicrosoftEdgeExtensionsDemosTextSwap] demos.</span></span>  

<span data-ttu-id="c88f8-252">[クイック印刷][GithubMicrosoftEdgeExtensionsDemosQuickPrint]の例については、次のビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-252">Walk through the [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] example in the following video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### <span data-ttu-id="c88f8-253">Manifest.xml</span><span class="sxs-lookup"><span data-stu-id="c88f8-253">Manifest.json</span></span>  

*   <span data-ttu-id="c88f8-254">`author`Microsoft Edge ではキーが必要です</span><span class="sxs-lookup"><span data-stu-id="c88f8-254">The `author` key is required in Microsoft Edge</span></span>  
*   <span data-ttu-id="c88f8-255">`activeTab`Microsoft Edge では、キーはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="c88f8-255">The `activeTab` key is not supported in Microsoft Edge</span></span>  

<span data-ttu-id="c88f8-256">[ブラウザーの拡張機能][MDNBrowserExtensions]の詳細については、「 [MDN web ドキュメント][MDNWebDocs]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88f8-256">For more information on [Browser Extensions][MDNBrowserExtensions], see [MDN web docs][MDNWebDocs].</span></span>  

<!-- image links -->  

<!--[ImageColorChangerHeader]: ../media/color-changer_header.png "Docs.microsoft.com body changed to blue"  -->  
<!--[ImageColorChangerPopup]: ../media/color-changer_popup.png "The pop-up interface of the extension"  -->  
<!--[ImageColorChangerHeaderAliceblue]: ../media/color-changer_header_aliceblue.png "[Docs.microsoft.com header changed to Aliceblue"  -->  
<!--[ImageColorChangerHeaderCornsilk]: ../media/color-changer_header_cornsilk.png "Docs.microsoft.com header changed to Cornsilk"  -->  

<!-- links -->  

[ExtensionsGuidesAddingRemovingExtensionsAdding]: ./adding-and-removing-extensions.md#adding-an-extension "拡張機能の追加-Microsoft Edge の拡張機能の追加、移動、削除 |Microsoft ドキュメント"  
[ExtensionsGuidesDebuggingExtensions]: ./debugging-extensions.md "拡張機能のデバッグ |Microsoft ドキュメント"  
[ExtensionsGuidesDesign]: ./design.md "Microsoft Edge Extensions の設計ガイドライン |Microsoft ドキュメント"  
[ExtensionsGuidesDesignIcons]: ./design.md#icons "アイコン-Microsoft Edge Extensions のデザインガイドライン |Microsoft ドキュメント"  
[ExtensionsAPIsupportApis]: ../api-support/supported-apis.md "サポートされている Api |Microsoft ドキュメント"  
[ExtensionsApisupportManifestKeys]: ../api-support/supported-manifest-keys.md "サポートされているマニフェストキー |Microsoft ドキュメント"  

[MicrosoftDocs]: https://docs.microsoft.com "Microsoft ドキュメント"  

[MDNWebDocs]: https://developer.mozilla.org "MDN Web ドキュメント"  
[MDNBrowserExtensions]: https://developer.mozilla.org/Add-ons/WebExtensions "ブラウザーの拡張機能 |MDN"  
[MDNAnatomyExtension]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension "拡張機能の構造 |MDN"  
[MDNAnatomyExtensionBackgroundScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#Background_scripts "バックグラウンドスクリプト-拡張機能の構造 |MDN"  
[MDApiBrowseractionDisable]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/disable "browserAction. disable ()-API |MDN" 
[MDNApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction ()-API |MDN"  
[MDNApiRuntimeOnmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onmessage "onMessage-API |MDN"  
[MDNApiRuntimeSendmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage "runtime ()-API |MDN"  
[MDNApiTabs]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs "タブ-API |MDN"  
[MDNApiTabsInsertcss]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/insertCSS "tabs Css ()-API |MDN"  
[MDNContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "コンテンツスクリプト |MDN"  
[MDNManifestjsonAuthor]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author "作成-マニフェスト |MDN"  
[MDNManifestjsonBackground]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/background "バックグラウンド-マニフェスト |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/browser_action "browser_action-manifest |MDN"  
[MDNManifestjsonContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_scripts "content_scripts-manifest |MDN"  
[MDNManifestjsonDescription]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/description "説明-manifest.xml |MDN"  
[MDNManifestjsonIcons]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/icons "アイコン-manifest |MDN"  
[MDNManifestjsonName]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/name "name-manifest |MDN"  
[MDNManifestjsonPermissions]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions "権限-manifest |MDN"  
[MDNManifestjsonVersion]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/version "バージョン-manifest |MDN"  
[MDNYourSecondWebextension]: https://developer.mozilla.org/Add-ons/WebExtensions/Your_second_WebExtension "2つ目の内線番号 |MDN"  

[Bing]: https://www.bing.com "Bing"  

[GithubMicrosoftEdgeExtensionsDemosBeastify]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/beastify_edge "Beastify-MicrosoftEdge/MicrosoftEdge-デモ |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChanger]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer "カラーチェンジャー-MicrosoftEdge/MicrosoftEdge-デモ機能-デモ |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerImages]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer/images "画像-カラーチェンジャー-MicrosoftEdge/MicrosoftEdge-デモ |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/color_changer/manifest.json "Manifest.xml-カラーチェンジャー-MicrosoftEdge/MicrosoftEdge-デモ |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosQuickPrint]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/quick_print "クイック印刷-MicrosoftEdge/MicrosoftEdge-デモ機能GitHub"  
[GithubMicrosoftEdgeExtensionsDemosTextSwap]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/text_swap "テキストの MicrosoftEdge/MicrosoftEdge-デモ機能-デモ |GitHub"  
