---
description: Microsoft Edge 拡張機能を作成する方法について説明します
title: 拡張機能の作成
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 15cb7a4c187210c885b5d75770bda1c590a8c5d1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235009"
---
# <span data-ttu-id="fe2e5-104">Microsoft Edge 拡張機能の作成</span><span class="sxs-lookup"><span data-stu-id="fe2e5-104">Creating A Microsoft Edge Extension</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="fe2e5-105">このガイドでは、Microsoft Edge の拡張機能を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-105">In this guide, learn to create an extension for Microsoft Edge.</span></span>  <span data-ttu-id="fe2e5-106">この拡張例を使用すると、マニフェスト ファイル [、ユーザー インターフェイス、][MicrosoftDocs] およびバックグラウンド スクリプトとコンテンツ スクリプトの作成を行docs.microsoft.comページの特定の CSS を操作できます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-106">This example extension allows you to manipulate specific CSS for [docs.microsoft.com][MicrosoftDocs] pages including walking you through creation of a manifest file, the user interface, and background and content scripts.</span></span>  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.comが青に変更されました":::
   <span data-ttu-id="fe2e5-108">Docs.microsoft.comが青に変更されました</span><span class="sxs-lookup"><span data-stu-id="fe2e5-108">Docs.microsoft.com body changed to blue</span></span>
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

<span data-ttu-id="fe2e5-109">このチュートリアルでは、ブラウザー拡張機能の基本と動作について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-109">This tutorial assumes you have basic understanding of what a browser extension is and how it work.</span></span>  <span data-ttu-id="fe2e5-110">拡張機能の構成要素の詳細については、「拡張機能の構造」 [を参照してください][MDNAnatomyExtension]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-110">For more imformation about the building blocks for extensions, see [Anatomy of an extension][MDNAnatomyExtension].</span></span>  

<span data-ttu-id="fe2e5-111">GitHub で完全な [サンプルのコードをダウンロードします][GithubMicrosoftEdgeExtensionsDemosColorChanger]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-111">Download the code for the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="fe2e5-112">マニフェスト ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="fe2e5-112">Building the manifest file</span></span>  

<span data-ttu-id="fe2e5-113">まず、拡張機能のディレクトリを作成し、名前を指定します `color-changer` 。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-113">To begin, create a directory for your extension and name it `color-changer`.</span></span>  

<span data-ttu-id="fe2e5-114">フォルダー内 `color-changer` に、次の名前のファイルを作成します `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-114">Inside the `color-changer` folder, create a file named `manifest.json`.</span></span>  <span data-ttu-id="fe2e5-115">このファイルは、すべての拡張子に必要であり、拡張子名からアクセス許可に至るまで、拡張子に関する重要 `manifest.json` な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-115">The `manifest.json` file is required for all extensions and provides important information for the extension, ranging from the extension name to the permissions.</span></span>  

> [!NOTE] 
> <span data-ttu-id="fe2e5-116">このガイドでは、このガイドで使用する必要があるすべてのマニフェスト キーについて詳しい情報を示しますが、サポートされているマニフェスト キーと推奨されるマニフェスト キーの一覧については、「サポートされているマニフェスト キー」を [参照してください][ExtensionsApisupportManifestKeys]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-116">This guide walks you through all the manifest keys you must use in this guide, but for a list of all supported and recommended manifest keys, see [Supported manifest keys][ExtensionsApisupportManifestKeys].</span></span>  

<span data-ttu-id="fe2e5-117">内部 `manifest.json` に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-117">Inside `manifest.json`, add the following code.</span></span>  

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

### <span data-ttu-id="fe2e5-118">マニフェスト キーの定義</span><span class="sxs-lookup"><span data-stu-id="fe2e5-118">Manifest key definitions</span></span>  

| <span data-ttu-id="fe2e5-119">キー</span><span class="sxs-lookup"><span data-stu-id="fe2e5-119">Key</span></span> | <span data-ttu-id="fe2e5-120">詳細</span><span class="sxs-lookup"><span data-stu-id="fe2e5-120">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="fe2e5-121">name</span><span class="sxs-lookup"><span data-stu-id="fe2e5-121">name</span></span>][MDNManifestjsonName] | <span data-ttu-id="fe2e5-122">拡張機能の名前。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-122">The name of the extension.</span></span>  |  
| [<span data-ttu-id="fe2e5-123">author</span><span class="sxs-lookup"><span data-stu-id="fe2e5-123">author</span></span>][MDNManifestjsonAuthor] | <span data-ttu-id="fe2e5-124">拡張機能の作成者。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-124">The author of the extension.</span></span>  |  
| [<span data-ttu-id="fe2e5-125">version</span><span class="sxs-lookup"><span data-stu-id="fe2e5-125">version</span></span>][MDNManifestjsonVersion] | <span data-ttu-id="fe2e5-126">内線番号のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-126">The extension version number.</span></span>  |  
| [<span data-ttu-id="fe2e5-127">description</span><span class="sxs-lookup"><span data-stu-id="fe2e5-127">description</span></span>][MDNManifestjsonDescription] | <span data-ttu-id="fe2e5-128">Microsoft Edge の拡張機能メニューの [About] セクションに表示される拡張機能の説明。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-128">The description of the extension displayed in the About section of the extension menu in Microsoft Edge.</span></span>  |  
| [<span data-ttu-id="fe2e5-129">permissions</span><span class="sxs-lookup"><span data-stu-id="fe2e5-129">permissions</span></span>][MDNManifestjsonPermissions] | <span data-ttu-id="fe2e5-130">拡張情報のアクセス許可を要求する文字列の配列。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-130">An array of strings requesting permissions for the extension.</span></span>  <span data-ttu-id="fe2e5-131">拡張機能の場合は、アクセスした Web サイトを表示するためのアクセス許可 ("tabs"\) を要求し、" に一致する URL のコンテンツを更新します `*://docs.microsoft.com/*` 。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-131">For your extension, you are requesting permissions to see the websites visited \("tabs"\) and to update content on URLs matching "`*://docs.microsoft.com/*`".</span></span>  |  
| [<span data-ttu-id="fe2e5-132">browser_action</span><span class="sxs-lookup"><span data-stu-id="fe2e5-132">browser_action</span></span>][MDNManifestjsonBrowserAction] | <span data-ttu-id="fe2e5-133">アイコンの情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-133">Contains the information for an icon.</span></span> <span data-ttu-id="fe2e5-134">アイコンは、アドレス バーの右側にある Microsoft Edge ツール バーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-134">The icon is placed on the Microsoft Edge toolbar, to the right of the address bar.</span></span>  |  

#### <span data-ttu-id="fe2e5-135">browser_actionの定義</span><span class="sxs-lookup"><span data-stu-id="fe2e5-135">browser_action Key definitions</span></span>  

| <span data-ttu-id="fe2e5-136">キー</span><span class="sxs-lookup"><span data-stu-id="fe2e5-136">Key</span></span> | <span data-ttu-id="fe2e5-137">詳細</span><span class="sxs-lookup"><span data-stu-id="fe2e5-137">Details</span></span> |  
|:--- |:--- |  
| `default_icon` | <span data-ttu-id="fe2e5-138">ツール バーで使用されるアイコン。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-138">The icon that is used in the toolbar.</span></span>  |  
| `default_title` | <span data-ttu-id="fe2e5-139">ユーザーがツール バーのアイコンの上にマウス ポインターを置くと表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-139">The text that is displayed when a user hovers over the icon in the toolbar.</span></span>  |  
| `default_popup` | <span data-ttu-id="fe2e5-140">ポップアップ ウィンドウの HTML ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-140">The path to the HTML file for the pop-up window.</span></span>  |  

<span data-ttu-id="fe2e5-141">マニフェスト ファイルを作成したら、拡張機能のユーザー インターフェイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-141">Now that you have created the manifest file, you need a user interface for the extension.</span></span>  

## <span data-ttu-id="fe2e5-142">ポップアップの作成</span><span class="sxs-lookup"><span data-stu-id="fe2e5-142">Creating the pop-up</span></span>  

<span data-ttu-id="fe2e5-143">拡張機能の場合は、次のようなユーザー インターフェイスのポップアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-143">For your extension, create a pop-up for the user interface, like below.</span></span>  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="拡張機能のポップアップ インターフェイス":::
   <span data-ttu-id="fe2e5-145">拡張機能のポップアップ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe2e5-145">The pop-up interface of the extension</span></span>
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

<span data-ttu-id="fe2e5-146">フォルダーのルートに `popup.html` 名前を付け、ファイルを作成 `color-changer` します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-146">Create a file named `popup.html` in the root of your `color-changer` folder.</span></span>  <span data-ttu-id="fe2e5-147">次のコードを貼り付けます `popup.html` 。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-147">Paste the following code into `popup.html`.</span></span>  

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

<span data-ttu-id="fe2e5-148">In, `popup.html` you create a title, a paragraph, and three buttons \(Aliceblue, Alicesilk, and Reset\).</span><span class="sxs-lookup"><span data-stu-id="fe2e5-148">In `popup.html`, you create a title, a paragraph, and three buttons \(Aliceblue, Cornsilk, and Reset\).</span></span>  

<span data-ttu-id="fe2e5-149">次に、フォルダーを作成し `css` 、その中に名前を付けるという名前のファイルを作成します `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-149">Now create a folder named `css` and inside create a file named `styles.css`.</span></span>  <span data-ttu-id="fe2e5-150">以下のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-150">Add the styles below.</span></span>  

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

<span data-ttu-id="fe2e5-151">この CSS は、拡張機能にいくつかの基本的なスタイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-151">This CSS gives our extension some basic styles.</span></span>  <span data-ttu-id="fe2e5-152">拡張機能をカスタマイズするためのスタイルを自由に追加できます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-152">Feel free to add more styles to customize your extension.</span></span>  

<span data-ttu-id="fe2e5-153">次に、ポップアップを操作する JavaScript ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-153">Next, you must create the JavaScript file that interacts with the pop-up.</span></span>  <span data-ttu-id="fe2e5-154">フォルダーと `js` 、その中に名前を付けられたファイルを `popup.js` 作成します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-154">Create a `js` folder and a file named `popup.js` inside.</span></span>  <span data-ttu-id="fe2e5-155">次 `popup.js` のコードで更新します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-155">Update `popup.js` with the following code.</span></span>  

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

<span data-ttu-id="fe2e5-156">タブ API では、ブラウザーのタブを操作し、スクリプトとスタイルをページ `popup.js` コンテンツに挿入できます。 [][MDNApiTabs]</span><span class="sxs-lookup"><span data-stu-id="fe2e5-156">In `popup.js`, the [tabs][MDNApiTabs] API allows you to interact with the tabs of the browser and inject script and styles into the page content.</span></span>  <span data-ttu-id="fe2e5-157">[tabs.insertCSS()][MDNApiTabsInsertcss]メソッドを使用して、指定した CSS をページに挿入し、指定したボタンがクリックされた場合に[docs.microsoft.com][MicrosoftDocs]のヘッダーを別の色に変更します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-157">Using the [tabs.insertCSS()][MDNApiTabsInsertcss] method, you inject the specified CSS into the page which changes the header on [docs.microsoft.com][MicrosoftDocs] to a different color when the specified button is clicked.</span></span>  

<span data-ttu-id="fe2e5-158">これで基本的なポップアップ機能が作成されたので、拡張機能にアイコンを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-158">Now that you have the basic pop-up functionality, add icons to the extension.</span></span>  

## <span data-ttu-id="fe2e5-159">アイコンの追加</span><span class="sxs-lookup"><span data-stu-id="fe2e5-159">Adding icons</span></span>  

<span data-ttu-id="fe2e5-160">アイコンは、ブラウザーのツール バー、拡張機能メニュー、その他の場所の拡張機能を表す場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-160">Icons are used to represent the extension in the browser toolbar, the extensions menu, and other places.</span></span>  <span data-ttu-id="fe2e5-161">[GitHub で拡張機能のアイコンをダウンロードします][GithubMicrosoftEdgeExtensionsDemosColorChangerImages]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-161">Download the [icons for your extension on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChangerImages].</span></span> <span data-ttu-id="fe2e5-162">Microsoft Edge の拡張機能アイコンの詳細については、「デザイン ガイド」を [参照してください][ExtensionsGuidesDesignIcons]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-162">For more information about extension icons in Microsoft Edge, see [Design Guide][ExtensionsGuidesDesignIcons].</span></span>  

<span data-ttu-id="fe2e5-163">拡張機能のアイコンをダウンロードした後、アイコンをフォルダー内 `images` に保存します `color-changer` 。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-163">After you download the extension icons, save the icons in an `images` folder inside `color-changer`.</span></span>  

<span data-ttu-id="fe2e5-164">ツール バーに表示されるアイコンは、前のセクションで既にマニフェスト ファイルに追加した browser_action キーの内側を使用 `default_icon` して設定されます。 [][MDNManifestjsonBrowserAction]</span><span class="sxs-lookup"><span data-stu-id="fe2e5-164">The icon that appears in the toolbar is set using `default_icon` inside of the [browser_action][MDNManifestjsonBrowserAction] key, which you already added to your manifest file in an earlier section.</span></span>  

<span data-ttu-id="fe2e5-165">キー `icons` は、[拡張機能の設定] メニューで使用するアイコンを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-165">The `icons` key defines which icons should be used in the Extensions settings menus.</span></span>  <span data-ttu-id="fe2e5-166">以下では、さまざまな画面解像度を考慮して、サイズが異なる複数のアイコンを指定しています。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-166">Below, you are specifying multiple icons with different sizes to account for different screen resolutions.</span></span>  <span data-ttu-id="fe2e5-167">アイコンの名前。アイコンの `25` `48` 高さ (ピクセル単位) です。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-167">The name of the icons, `25` and `48` are the heights in pixels of the icons.</span></span>  

<span data-ttu-id="fe2e5-168">ファイルの [manifest.jsに][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 、次のトップ レベル キーを含める `icons` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-168">In the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file, include a top-level key for `icons`.</span></span>  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### <span data-ttu-id="fe2e5-169">マニフェスト キーの定義</span><span class="sxs-lookup"><span data-stu-id="fe2e5-169">Manifest Key definitions</span></span>  

| <span data-ttu-id="fe2e5-170">キー</span><span class="sxs-lookup"><span data-stu-id="fe2e5-170">Key</span></span> | <span data-ttu-id="fe2e5-171">詳細</span><span class="sxs-lookup"><span data-stu-id="fe2e5-171">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="fe2e5-172">アイコン</span><span class="sxs-lookup"><span data-stu-id="fe2e5-172">icons</span></span>][MDNManifestjsonIcons] | <span data-ttu-id="fe2e5-173">拡張機能のルート ディレクトリに対するイメージ サイズとイメージ パスのキーと値のペアを持つ拡張機能 `px` のアイコン。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-173">The icons for your extension with key-value pairs of image size in `px` and image path relative to the root directory of the extension.</span></span> |  

> [!NOTE]
> <span data-ttu-id="fe2e5-174">このガイドで後 `inactive##.png` で説明する images フォルダーにある名前のアイコンを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-174">Use the icons named `inactive##.png` located in the images folder later in this guide.</span></span>  

## <span data-ttu-id="fe2e5-175">拡張機能のテスト</span><span class="sxs-lookup"><span data-stu-id="fe2e5-175">Testing the extension</span></span>  

<span data-ttu-id="fe2e5-176">ユーザー インターフェイスを追加し、アイコンを作成したら、拡張機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-176">Now that you have added the user interface and created icons, test your extension.</span></span>  <span data-ttu-id="fe2e5-177">Microsoft Edge に拡張機能を [追加する手順][ExtensionsGuidesAddingRemovingExtensionsAdding] について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-177">Walk through the steps for [Adding an extension][ExtensionsGuidesAddingRemovingExtensionsAdding] to Microsoft Edge.</span></span>  <span data-ttu-id="fe2e5-178">その後、このガイドに戻ってください。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-178">Afterwards, return to this guide.</span></span>  

<span data-ttu-id="fe2e5-179">拡張機能を追加した後、任意のページに [docs.microsoft.com][MicrosoftDocs] します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-179">After you add your extension, navigate to any [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="fe2e5-180">ブラウザーの操作をクリックすると、次のポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-180">You should see the following pop-up after clicking on the browser action.</span></span>  <span data-ttu-id="fe2e5-181">本文の色も [docs.microsoft.com][MicrosoftDocs] 変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-181">The color of the [docs.microsoft.com][MicrosoftDocs] body should also change color.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.comヘッダーが Aliceblue に変更されました":::
         <span data-ttu-id="fe2e5-183">Docs.microsoft.comヘッダーが Aliceblue に変更されました</span><span class="sxs-lookup"><span data-stu-id="fe2e5-183">Docs.microsoft.com header changed to Aliceblue</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.comヘッダーが次の値に変更されました":::
         <span data-ttu-id="fe2e5-185">Docs.microsoft.comヘッダーが次の値に変更されました</span><span class="sxs-lookup"><span data-stu-id="fe2e5-185">Docs.microsoft.com header changed to Cornsilk</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

<span data-ttu-id="fe2e5-186">動作しないエラーや機能が発生した場合は、デバッグ拡張機能のガイド[][ExtensionsGuidesDebuggingExtensions]を参照するか、GitHub で完全なサンプル[をダウンロードしてください][GithubMicrosoftEdgeExtensionsDemosColorChanger]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-186">If you encounter any errors or functionality that does not work, see the [Debugging extensions][ExtensionsGuidesDebuggingExtensions] guide or download the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="fe2e5-187">コンテンツとバックグラウンド スクリプトの追加</span><span class="sxs-lookup"><span data-stu-id="fe2e5-187">Adding content and background scripts</span></span>  

<span data-ttu-id="fe2e5-188">もう 1 つの手順に進み、拡張機能がドメイン外のページで機能することを無効にするロジック [docs.microsoft.com][MicrosoftDocs] します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-188">Go one step further and add logic to disable the extension from working on pages outside the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  

<span data-ttu-id="fe2e5-189">最初にコンテンツ スクリプトを作成 [する必要があります][MDNContentScripts]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-189">You must first create a [content script][MDNContentScripts].</span></span>  <span data-ttu-id="fe2e5-190">次に、特定の Web ページのコンテキストで実行し、Web ページのコンテンツにアクセスし、バックグラウンド スクリプトと通信できるコンテンツ スクリプトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-190">Next, you must create content scripts that run in the context of a particular web page, are able to access the content of a web page, and are able to communicate with background scripts.</span></span>  <span data-ttu-id="fe2e5-191">ディレクトリ内に `js` 、名前を付け、次の `content.js` コードを追加するファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-191">Inside of your `js` directory, create a file named `content.js` and add the following code.</span></span>  

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

<span data-ttu-id="fe2e5-192">このスクリプトは、現在のページの URL を取得し、現在のページが現在のドメイン上 `document.location.href` [docs.microsoft.com][MicrosoftDocs] します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-192">This script gets the URL of the current page through `document.location.href` and verifies whether the current page is on the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  <span data-ttu-id="fe2e5-193">[ページ][MicrosoftDocs]が docs.microsoft.com ドメイン \(\など) 上にない場合、非アクティブなアイコン \(灰色表示されたアイコン\) へのパスは [https://www.bing.com/][|::ref1::|] [runtime.sendMessage()][MDNApiRuntimeSendmessage]を使用してバックグラウンド スクリプトに送信されます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-193">If the page is not on the [docs.microsoft.com][MicrosoftDocs] domain \(for example  [https://www.bing.com/][|::ref1::|]\), the paths to the inactive icons \(grayed out icons\) are sent to the background script using [runtime.sendMessage()][MDNApiRuntimeSendmessage].</span></span>  

<span data-ttu-id="fe2e5-194">次のキーを含 [manifest.jsファイル][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] のファイル名を更新する必要 `content_scripts` があります。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-194">You must update the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file to include the following `content_scripts` key.</span></span>  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### <span data-ttu-id="fe2e5-195">マニフェスト キーの定義</span><span class="sxs-lookup"><span data-stu-id="fe2e5-195">Manifest Key definitions</span></span>  

| <span data-ttu-id="fe2e5-196">キー</span><span class="sxs-lookup"><span data-stu-id="fe2e5-196">Key</span></span> | <span data-ttu-id="fe2e5-197">詳細</span><span class="sxs-lookup"><span data-stu-id="fe2e5-197">Details</span></span> |  
|:--- |:---- |  
| [<span data-ttu-id="fe2e5-198">content_scripts</span><span class="sxs-lookup"><span data-stu-id="fe2e5-198">content_scripts</span></span>][MDNManifestjsonContentScripts] | <span data-ttu-id="fe2e5-199">ブラウザーが読み込むコンテンツ スクリプトに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-199">Contains the information about which content scripts the browser should load.</span></span> |  

#### <span data-ttu-id="fe2e5-200">content_scriptsの定義</span><span class="sxs-lookup"><span data-stu-id="fe2e5-200">content_scripts Key definitions</span></span>  

| <span data-ttu-id="fe2e5-201">キー</span><span class="sxs-lookup"><span data-stu-id="fe2e5-201">Key</span></span> | <span data-ttu-id="fe2e5-202">詳細</span><span class="sxs-lookup"><span data-stu-id="fe2e5-202">Details</span></span> |  
|:--- |:---- |  
| `matches` <span data-ttu-id="fe2e5-203">\(required\)</span><span class="sxs-lookup"><span data-stu-id="fe2e5-203">\(required\)</span></span> | <span data-ttu-id="fe2e5-204">コンテンツ スクリプトを読み込む前に一致する URL パターン。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-204">The URL pattern to match prior to loading the content script.</span></span> |  
| `js` | <span data-ttu-id="fe2e5-205">一致する URL に読み込む必要があるスクリプト。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-205">The script that should be loaded on matching URLs.</span></span> |  
| `run_at` | <span data-ttu-id="fe2e5-206">キーの JavaScript ファイルが挿入 `js` される場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-206">Specifies where the JavaScript files from the `js` key are injected.</span></span> |  

<span data-ttu-id="fe2e5-207">次に、バックグラウンド スクリプトを [作成する必要があります][MDNAnatomyExtensionBackgroundScripts]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-207">Next, you must create a [background script][MDNAnatomyExtensionBackgroundScripts].</span></span>  <span data-ttu-id="fe2e5-208">バックグラウンド スクリプトはブラウザーのバックグラウンドで実行され、Web ページまたはブラウザー ウィンドウの有効期間とは別に実行され、コンテンツ スクリプトと通信できます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-208">Background scripts run in the background of the browser, run independently of the lifetime of a web page or browser window, and are able to communicate with content scripts.</span></span>  

<span data-ttu-id="fe2e5-209">フォルダー内に `js` 、名前を付け、次の `background.js` コードを追加するファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-209">Inside of your `js` folder, create a file named `background.js` and add the following code.</span></span>  

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

<span data-ttu-id="fe2e5-210">[runtime.onMessage メソッドは][MDNApiRuntimeOnmessage]、コンテンツ スクリプト[から runtime.sendMessage()][MDNApiRuntimeSendmessage]をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-210">The [runtime.onMessage][MDNApiRuntimeOnmessage] method listens for [runtime.sendMessage()][MDNApiRuntimeSendmessage] from the content script.</span></span>  <span data-ttu-id="fe2e5-211">ページのドメインが指定されていない場合docs.microsoft.com [][MicrosoftDocs] [browserAction.setIcon()][MDNApiBrowseractionSeticon]メソッドは、アイコン パスを非アクティブなイメージに設定します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-211">If the domain of the page is not [docs.microsoft.com][MicrosoftDocs], then [browserAction.setIcon()][MDNApiBrowseractionSeticon] method sets the icon paths to the inactive images.</span></span>  

<span data-ttu-id="fe2e5-212">また、このスクリプトはブラウザー アクション \([browserAction.disable][MDApiBrowseractionDisable]\) を無効にし、ユーザーがブラウザーの操作をページの外部でクリック[docs.microsoft.comします。][MicrosoftDocs]</span><span class="sxs-lookup"><span data-stu-id="fe2e5-212">The script also disables the browser action \([browserAction.disable][MDApiBrowseractionDisable]\), so that users are not able to click on the browser action outside of a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  

<span data-ttu-id="fe2e5-213">ファイルに対してバックグラウンド スクリプトをmanifest.js[ する必要][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] があります。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-213">You must add the background script to the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file.</span></span>  <span data-ttu-id="fe2e5-214">マニフェストに次 `background` のキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-214">Add the following `background` key to your manifest.</span></span>  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### <span data-ttu-id="fe2e5-215">マニフェスト キーの定義</span><span class="sxs-lookup"><span data-stu-id="fe2e5-215">Manifest Key definitions</span></span>  

| <span data-ttu-id="fe2e5-216">キー</span><span class="sxs-lookup"><span data-stu-id="fe2e5-216">Key</span></span> | <span data-ttu-id="fe2e5-217">詳細</span><span class="sxs-lookup"><span data-stu-id="fe2e5-217">Details</span></span>|  
|:--- |:--- |  
| [<span data-ttu-id="fe2e5-218">背景</span><span class="sxs-lookup"><span data-stu-id="fe2e5-218">background</span></span>][MDNManifestjsonBackground] | <span data-ttu-id="fe2e5-219">バックグラウンド スクリプトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-219">Contains the background scripts.</span></span> |  

#### <span data-ttu-id="fe2e5-220">バックグラウンド キーの定義</span><span class="sxs-lookup"><span data-stu-id="fe2e5-220">background Key definitions</span></span>  

| <span data-ttu-id="fe2e5-221">キー</span><span class="sxs-lookup"><span data-stu-id="fe2e5-221">Key</span></span> | <span data-ttu-id="fe2e5-222">詳細</span><span class="sxs-lookup"><span data-stu-id="fe2e5-222">Details</span></span> |  
|:--- |:--- |  
| `scripts` | <span data-ttu-id="fe2e5-223">JavaScript ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-223">The path to a JavaScript file.</span></span> |  
| `persistent` <span data-ttu-id="fe2e5-224">(必須)</span><span class="sxs-lookup"><span data-stu-id="fe2e5-224">(required)</span></span> | <span data-ttu-id="fe2e5-225">これは、次の値に設定する `true` 必要があります `false` 。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-225">This must be set to `true` or `false`.</span></span>  <span data-ttu-id="fe2e5-226">設定すると、 `true` バックグラウンド スクリプトが読み込まれ、閲覧セクション全体で保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-226">If set to `true`, the background script is loaded and persists for the entire browsing section.</span></span>  <span data-ttu-id="fe2e5-227">設定されている場合、バックグラウンド スクリプトは遅延と一緒に読み込まれ、閲覧 `false` セッションで保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-227">If set to `false`, the background script is loaded with a delay and persists for the browsing session.</span></span> |  

<span data-ttu-id="fe2e5-228">拡張機能を再読み込みし、もう一度テストします。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-228">Reload your extension and test again.</span></span>  <span data-ttu-id="fe2e5-229">To reload your extension: click the **...** for settings and more in Microsoft Edge, click **Extensions,** click on your extension \(**Color Changer**\), and click **Reload extension**.</span><span class="sxs-lookup"><span data-stu-id="fe2e5-229">To reload your extension: click the **...** for settings and more in Microsoft Edge, click **Extensions**, click on your extension \(**Color Changer**\), and click **Reload extension**.</span></span>  

<span data-ttu-id="fe2e5-230">次に、新しいタブを開くか、新しいページではない既存のタブ [docs.microsoft.com][MicrosoftDocs] します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-230">Now, open a new tab or refresh an existing tab that is not a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="fe2e5-231">You should see the inactive icon and not be able to click on the browser action.</span><span class="sxs-lookup"><span data-stu-id="fe2e5-231">You should see the inactive icon and not be able to click on the browser action.</span></span>  

<span data-ttu-id="fe2e5-232">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-232">Congratulations!</span></span>  <span data-ttu-id="fe2e5-233">Microsoft Edge の拡張機能を作成しました。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-233">You created an extension for Microsoft Edge!</span></span>  <span data-ttu-id="fe2e5-234">[GitHub で完全なサンプルを表示します][GithubMicrosoftEdgeExtensionsDemosColorChanger]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-234">View the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  <span data-ttu-id="fe2e5-235">拡張機能の詳細については、続きを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-235">Continue reading to learn more about extensions.</span></span>  

## <span data-ttu-id="fe2e5-236">より複雑な拡張機能の作成</span><span class="sxs-lookup"><span data-stu-id="fe2e5-236">Writing a more complex extension</span></span>  

<span data-ttu-id="fe2e5-237">より複雑な拡張機能を作成する場合</span><span class="sxs-lookup"><span data-stu-id="fe2e5-237">Want to write a more complex extension?</span></span>  <span data-ttu-id="fe2e5-238">MdN の 2 番目の拡張機能である MdN の 2 番目の拡張機能 [をご覧ください][MDNYourSecondWebextension]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-238">Take a look at the Beastify extension on MDN in the article, [Your second extension][MDNYourSecondWebextension].</span></span>  <span data-ttu-id="fe2e5-239">Microsoft Edge の拡張機能モデルは Firefox の拡張機能モデルとは少し異なります。2[][MDNYourSecondWebextension]番目の拡張機能で作成された 1 つ目の拡張機能は、Microsoft Edge で機能するように適合されました。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-239">The extension model for Microsoft Edge differs slightly from the extension model for Firefox, the Beastify extension created in [Your second extension][MDNYourSecondWebextension] was adapted to function in Microsoft Edge.</span></span>  <span data-ttu-id="fe2e5-240">GitHub で [確認してください][GithubMicrosoftEdgeExtensionsDemosBeastify]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-240">Check it out on [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify].</span></span>  

<span data-ttu-id="fe2e5-241">MDN (2 番目の [拡張機能)][MDNYourSecondWebextension]に関する記事を見ながら、次のセクションに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-241">While walking through the article on MDN, [Your second extension][MDNYourSecondWebextension], keep in mind the following sections.</span></span>  

### <span data-ttu-id="fe2e5-242">API</span><span class="sxs-lookup"><span data-stu-id="fe2e5-242">APIs</span></span>  

<span data-ttu-id="fe2e5-243">Microsoft Edge [でサポートされている][ExtensionsAPIsupportApis] 拡張機能 API の一覧については、「サポートされる API」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-243">See the [Supported APIs][ExtensionsAPIsupportApis] page for a list of supported extensions APIs in Microsoft Edge.</span></span>  

### <span data-ttu-id="fe2e5-244">アイコンのサイズ</span><span class="sxs-lookup"><span data-stu-id="fe2e5-244">Icon sizes</span></span>  

<span data-ttu-id="fe2e5-245">Microsoft Edge の推奨される拡張アイコンのサイズは `20px` 、次 `25px` `30px` のとおりです `40px` 。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-245">Preferred extension icon sizes for Microsoft Edge are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="fe2e5-246">その他のサポートされるサイズは `19px` `35px` 、,, and `38px` です。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-246">Other supported sizes are `19px`, `35px`, and `38px`.</span></span>  <span data-ttu-id="fe2e5-247">アイコンのサイズとベスト プラクティスについて詳しくは、デザイン ガイドをご [覧][ExtensionsGuidesDesign] ください。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-247">For more info on icon sizes and best practices, see the [Design][ExtensionsGuidesDesign] guide.</span></span>  

### <span data-ttu-id="fe2e5-248">JavaScript</span><span class="sxs-lookup"><span data-stu-id="fe2e5-248">JavaScript</span></span>  

<span data-ttu-id="fe2e5-249">Microsoft Edge の拡張機能モデルでは、JavaScript Promise はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-249">The extension model for Microsoft Edge does not support JavaScript Promises.</span></span>  <span data-ttu-id="fe2e5-250">代わりに、コールバックを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-250">Instead, use callbacks.</span></span>  <span data-ttu-id="fe2e5-251">拡張機能でコールバックを使用するその他の例については、クイック印刷デモとテキスト[][GithubMicrosoftEdgeExtensionsDemosQuickPrint]スワップ デモ[をご覧ください][GithubMicrosoftEdgeExtensionsDemosTextSwap]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-251">For more examples of using callbacks in an extension, take a look at the  [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] and [Text Swap][GithubMicrosoftEdgeExtensionsDemosTextSwap] demos.</span></span>  

<span data-ttu-id="fe2e5-252">次のビデオ [のクイック印刷][GithubMicrosoftEdgeExtensionsDemosQuickPrint] の例を説明します。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-252">Walk through the [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] example in the following video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### <span data-ttu-id="fe2e5-253">Manifest.jsオン</span><span class="sxs-lookup"><span data-stu-id="fe2e5-253">Manifest.json</span></span>  

*   <span data-ttu-id="fe2e5-254">キー `author` は Microsoft Edge で必要です</span><span class="sxs-lookup"><span data-stu-id="fe2e5-254">The `author` key is required in Microsoft Edge</span></span>  
*   <span data-ttu-id="fe2e5-255">キー `activeTab` は Microsoft Edge ではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="fe2e5-255">The `activeTab` key is not supported in Microsoft Edge</span></span>  

<span data-ttu-id="fe2e5-256">ブラウザー拡張機能について詳 [しくは、MDN][MDNBrowserExtensions]の [Web ドキュメントをご覧ください][MDNWebDocs]。</span><span class="sxs-lookup"><span data-stu-id="fe2e5-256">For more information on [Browser Extensions][MDNBrowserExtensions], see [MDN web docs][MDNWebDocs].</span></span>  

<!-- image links -->  

<!--[ImageColorChangerHeader]: ../media/color-changer_header.png "Docs.microsoft.com body changed to blue"  -->  
<!--[ImageColorChangerPopup]: ../media/color-changer_popup.png "The pop-up interface of the extension"  -->  
<!--[ImageColorChangerHeaderAliceblue]: ../media/color-changer_header_aliceblue.png "[Docs.microsoft.com header changed to Aliceblue"  -->  
<!--[ImageColorChangerHeaderCornsilk]: ../media/color-changer_header_cornsilk.png "Docs.microsoft.com header changed to Cornsilk"  -->  

<!-- links -->  

[ExtensionsGuidesAddingRemovingExtensionsAdding]: ./adding-and-removing-extensions.md#adding-an-extension "拡張機能の追加 - Microsoft Edge の拡張機能の追加、移動、削除 |Microsoft Docs"  
[ExtensionsGuidesDebuggingExtensions]: ./debugging-extensions.md "拡張機能のデバッグ |Microsoft Docs"  
[ExtensionsGuidesDesign]: ./design.md "Microsoft Edge 拡張機能の設計ガイドライン |Microsoft Docs"  
[ExtensionsGuidesDesignIcons]: ./design.md#icons "アイコン - Microsoft Edge 拡張機能の設計ガイドライン |Microsoft Docs"  
[ExtensionsAPIsupportApis]: ../api-support/supported-apis.md " サポートされている API |Microsoft Docs"  
[ExtensionsApisupportManifestKeys]: ../api-support/supported-manifest-keys.md "サポートされているマニフェスト キー |Microsoft Docs"  

[MicrosoftDocs]: https://docs.microsoft.com "Microsoft Docs"  

[MDNWebDocs]: https://developer.mozilla.org "MDN Web ドキュメント"  
[MDNBrowserExtensions]: https://developer.mozilla.org/Add-ons/WebExtensions "ブラウザーの拡張機能 | MDN"  
[MDNAnatomyExtension]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension "拡張機能の構造 |MDN"  
[MDNAnatomyExtensionBackgroundScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#Background_scripts "バックグラウンド スクリプト - 拡張機能の構造 |MDN"  
[MDApiBrowseractionDisable]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/disable "browserAction.disable() - API |MDN" 
[MDNApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction.setIcon() - API |MDN"  
[MDNApiRuntimeOnmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onmessage "runtime.onMessage - API |MDN"  
[MDNApiRuntimeSendmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage "runtime.sendMessage() - API |MDN"  
[MDNApiTabs]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs "タブ - API |MDN"  
[MDNApiTabsInsertcss]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/insertCSS "tabs.insertCSS() - API |MDN"  
[MDNContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "コンテンツ スクリプト |MDN"  
[MDNManifestjsonAuthor]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author "author - manifest.json |MDN"  
[MDNManifestjsonBackground]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/background "background - manifest.json |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/browser_action "browser_action - manifest.json |MDN"  
[MDNManifestjsonContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_scripts "content_scripts - manifest.json |MDN"  
[MDNManifestjsonDescription]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/description "description - manifest.json |MDN"  
[MDNManifestjsonIcons]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/icons "アイコン - manifest.jsオン |MDN"  
[MDNManifestjsonName]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/name "name - manifest.json |MDN"  
[MDNManifestjsonPermissions]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions "permissions - manifest.json |MDN"  
[MDNManifestjsonVersion]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/version "version - manifest.json |MDN"  
[MDNYourSecondWebextension]: https://developer.mozilla.org/Add-ons/WebExtensions/Your_second_WebExtension "2 番目の拡張機能 |MDN"  

[Bing]: https://www.bing.com "Bing"  

[GithubMicrosoftEdgeExtensionsDemosBeastify]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/beastify_edge "Ify - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChanger]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer "カラー Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerImages]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer/images "画像 - カラー Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/color_changer/manifest.json "Manifest.jsオン - カラー Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosQuickPrint]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/quick_print "クイック印刷 - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosTextSwap]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/text_swap "テキスト スワップ - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
