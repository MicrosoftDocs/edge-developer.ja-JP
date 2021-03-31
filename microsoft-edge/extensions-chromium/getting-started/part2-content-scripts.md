---
description: コンテンツ スクリプトを使用してページ本文タグの下に NASA ピクチャを動的に挿入する
title: 拡張機能のチュートリアルを作成する パート 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, Web 開発, html, css, javascript, developer, extensions
ms.openlocfilehash: 48af14c33a368a3449acb88b4dfb875ad5398e7a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397917"
---
# <a name="create-an-extension-tutorial-part-2"></a><span data-ttu-id="f4175-104">拡張機能のチュートリアルを作成する パート 2</span><span class="sxs-lookup"><span data-stu-id="f4175-104">Create an extension tutorial Part 2</span></span>  
  
[<span data-ttu-id="f4175-105">このパーツの拡張パッケージ ソースの完成</span><span class="sxs-lookup"><span data-stu-id="f4175-105">Completed Extension Package Source for This Part</span></span>][ArchiveExtensionGettingStartedPart2]    

## <a name="overview"></a><span data-ttu-id="f4175-106">概要</span><span class="sxs-lookup"><span data-stu-id="f4175-106">Overview</span></span>  

<span data-ttu-id="f4175-107">このチュートリアルでは、次の拡張テクノロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f4175-107">This tutorial covers the following extension technologies.</span></span>
*   <span data-ttu-id="f4175-108">JavaScript ライブラリを拡張機能に挿入する</span><span class="sxs-lookup"><span data-stu-id="f4175-108">Injecting JavaScript libraries into extension</span></span>  
*   <span data-ttu-id="f4175-109">拡張機能のアセットをブラウザー タブに公開する</span><span class="sxs-lookup"><span data-stu-id="f4175-109">Exposing extension assets to browser tabs</span></span>  
*   <span data-ttu-id="f4175-110">既存のブラウザー タブにコンテンツ ページを含む</span><span class="sxs-lookup"><span data-stu-id="f4175-110">Including content pages in existing browser tabs</span></span>  
*   <span data-ttu-id="f4175-111">コンテンツ ページでポップアップからのメッセージをリッスンして応答する</span><span class="sxs-lookup"><span data-stu-id="f4175-111">Having content pages listen for messages from pop-ups and respond</span></span>  

<span data-ttu-id="f4175-112">ポップアップ メニューを更新して、静的開始イメージをタイトルと標準の HTML ボタンに置き換える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4175-112">You'll learn to update your pop-up menu to replace your static starts image with a title and a standard HTML button.</span></span>  <span data-ttu-id="f4175-113">このボタンを選択すると、拡張機能に埋め込まれている星の画像がコンテンツ ページに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f4175-113">That button, when selected, passes that stars image, which is embedded in the extension, to the content page.</span></span>  <span data-ttu-id="f4175-114">そのイメージは、アクティブなブラウザー タブに挿入されます。詳細については、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f4175-114">That image, is inserted into the active browser tab. Follow the below steps for further details.</span></span>

1.  <span data-ttu-id="f4175-115">ポップアップから画像を削除し、ボタンに置き換える</span><span class="sxs-lookup"><span data-stu-id="f4175-115">Remove the image from the pop-up and replace it with a button</span></span>  

<span data-ttu-id="f4175-116">まず、タイトルと `popup.html` ボタンを表示する簡単なマークアップでファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="f4175-116">First, update your `popup.html` file with some straight forward markup that displays a title and a button.</span></span>  <span data-ttu-id="f4175-117">このボタンをすぐにプログラムしますが、今のところ、空の JavaScript ファイルへの参照を含める必要があります `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="f4175-117">You'll program that button shortly, but for now, just include a reference to an empty JavaScript file `popup.js`.</span></span>  <span data-ttu-id="f4175-118">更新 HTML を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f4175-118">Here is update HTML.</span></span>  

```html
<html>
    <head>
        <meta charset="utf-8" />
        <style>
            body {
                width: 500px;
            }
            button {
                background-color: #336dab;
                border: none;
                color: white;
                padding: 15px 32px;
                text-align: center;
                font-size: 16px;
            }
        </style>
    </head>
    <body>
        <h1>Show the NASA picture of the day</h1>
        <h2>(select the image to remove)</h2>
        <button id="sendmessageid">Display</button>
        <script src="popup.js"></script>
    </body>
</html>
```  

<span data-ttu-id="f4175-119">拡張機能を更新して開くと、ポップアップが表示ボタンで開きます。</span><span class="sxs-lookup"><span data-stu-id="f4175-119">After updating and opening the extension, a pop-up opens with a display button.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.htmのアイコンを選択した後に l が表示される":::
   <span data-ttu-id="f4175-121">popup.htmのアイコンを選択した後に l が表示される</span><span class="sxs-lookup"><span data-stu-id="f4175-121">popup.html display after selecting the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after selecting the Extension icon][ImagePart2Popupdialog]  -->  

2.  <span data-ttu-id="f4175-122">ブラウザー タブの上部に画像を表示する更新戦略</span><span class="sxs-lookup"><span data-stu-id="f4175-122">Update strategy to display image at the top of the browser tab</span></span>  

<span data-ttu-id="f4175-123">ボタンを追加した後、次のタスクは、アクティブなタブ ページの上部にイメージ ファイル `images/stars.jpeg` を表示することです。</span><span class="sxs-lookup"><span data-stu-id="f4175-123">After adding the button, the next task is to make it bring up the `images/stars.jpeg` image file at the top of the active tab page.</span></span>  

<span data-ttu-id="f4175-124">各タブ ページは、独自のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4175-124">Remember, each tab page runs in its own thread.</span></span> <span data-ttu-id="f4175-125">また、拡張機能は別のスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4175-125">Also, the extension uses a different thread.</span></span>  <span data-ttu-id="f4175-126">最初に、タブ ページに挿入されるコンテンツ スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4175-126">First, create a content script that is injected into the tab page.</span></span>  <span data-ttu-id="f4175-127">次に、ポップアップからタブ ページで実行されているコンテンツ スクリプトにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f4175-127">Then, send a message from your pop-up to that content script running on the tab page.</span></span> <span data-ttu-id="f4175-128">コンテンツ スクリプトは、表示するイメージを記述するメッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f4175-128">The content script receives the message, which describes which image should be displayed.</span></span>  

3. <span data-ttu-id="f4175-129">メッセージを送信するポップアップ JavaScript を作成する</span><span class="sxs-lookup"><span data-stu-id="f4175-129">Create the pop-up JavaScript to send a message</span></span>  

<span data-ttu-id="f4175-130">最初に、まだ作成されていないコンテンツ スクリプトにメッセージを送信するコードを作成して追加します。このスクリプトでは、ブラウザー タブを一瞬作成して挿入 `popup/popup.js` する必要があります。 これを行うには、次のコードはポップアップ `onclick` 表示ボタンにイベントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4175-130">First, create `popup/popup.js` and add code to send a message to your not-yet-created content script that you must momentarily create and inject into your browser tab.  To do that, the following code adds an `onclick` event to your pop-up display button.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

<span data-ttu-id="f4175-131">イベントで `onclick` 、現在のブラウザー タブを探します。 次に、拡張機能 `chrome.tabs.sendmessage` API を使用して、そのタブにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f4175-131">In the `onclick` event, find the current browser tab.  Then, use the `chrome.tabs.sendmessage` Extension API to send a message to that tab.</span></span>  

<span data-ttu-id="f4175-132">そのメッセージでは、表示するイメージの URL を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4175-132">In that message you must include the URL to the image you want to display.</span></span> <span data-ttu-id="f4175-133">また、挿入された画像に割り当てる一意の ID を送信します。</span><span class="sxs-lookup"><span data-stu-id="f4175-133">Also, send a unique ID to assign to the inserted image.</span></span>  <span data-ttu-id="f4175-134">コンテンツ挿入 JavaScript で生成することもできますが、後で明らかな理由から、ここで一意の ID を生成し、まだ作成されていないコンテンツ スクリプトに渡します `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="f4175-134">You may choose to let the content insertion JavaScript generate that, but for reasons that become apparent later, generate that unique ID here in `popup.js` and pass it to the not-yet-created content script.</span></span>  

<span data-ttu-id="f4175-135">次のコード スニペットでは、更新されたコードの概要を示します `popup/popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="f4175-135">The following code snippet outlines the updated code in `popup/popup.js`.</span></span>  <span data-ttu-id="f4175-136">また、この記事の後半で使用される現在のタブ ID を渡します。</span><span class="sxs-lookup"><span data-stu-id="f4175-136">Also, pass in the current tab ID, which is used later in this article.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
    sendMessageId.onclick = function() {
        chrome.tabs.query({ active: true, currentWindow: true }, function(tabs) {
            chrome.tabs.sendMessage(
                tabs[0].id,
                {
                    url: chrome.extension.getURL("images/stars.jpeg"),
                    imageDivId: `${guidGenerator()}`,
                    tabId: tabs[0].id
                },
                function(response) {
                    window.close();
                }
            );
            function guidGenerator() {
                const S4 = function () {
                    return (((1 + Math.random()) * 0x10000) | 0).toString(16).substring(1);
                };
                return (S4() + S4() + "-" + S4() + "-" + S4() + "-" + S4() + "-" + S4() + S4() + S4());
            }
        });
    };
}
```  

4. <span data-ttu-id="f4175-137">任意のブラウザー タブから stars.jpeg を使用可能にする</span><span class="sxs-lookup"><span data-stu-id="f4175-137">Make your stars.jpeg available from any browser tab</span></span>  

<span data-ttu-id="f4175-138">前のセクションのように余分なプレフィックスを付けずに相対 URL を渡すのではなく、クロム拡張機能 API を使用する必要がある理由は、おそらく疑問に `images/stars.jpeg` `chrome.extension.getURL` 思うかもしれません。</span><span class="sxs-lookup"><span data-stu-id="f4175-138">You're probably wondering why, when you pass the `images/stars.jpeg` must you use the `chrome.extension.getURL` chrome Extension API instead of just passing in the relative URL without the extra prefix like in the previous section.</span></span>  <span data-ttu-id="f4175-139">ところで、画像を添付して返される余分なプレフィックス `getUrl` は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f4175-139">By the way, that extra prefix, returned by `getUrl` with the image attached looks something like the following.</span></span>  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

<span data-ttu-id="f4175-140">その理由は、要素の属性を使用してコンテンツ ページにイメージ `src` `img` を挿入しているからです。</span><span class="sxs-lookup"><span data-stu-id="f4175-140">The reason is that you're injecting the image using the `src` attribute of the `img` element into the content page.</span></span>  <span data-ttu-id="f4175-141">コンテンツ ページは、拡張機能を実行しているスレッドと同じではない一意のスレッドで実行されています。</span><span class="sxs-lookup"><span data-stu-id="f4175-141">The content page is running on a unique thread that isn't the same as the thread running the Extension.</span></span>  <span data-ttu-id="f4175-142">静的イメージ ファイルが正しく動作するには、静的イメージ ファイルを Web アセットとして公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4175-142">You must expose the static image file as a web asset for it to work correctly.</span></span>  

<span data-ttu-id="f4175-143">ファイルに別のエントリを追加 `manifest.json` して、イメージがすべてのブラウザー タブで使用できると宣言します。</span><span class="sxs-lookup"><span data-stu-id="f4175-143">Add another entry in the `manifest.json` file to declare that the image is available to all browser tabs.</span></span>  <span data-ttu-id="f4175-144">このエントリは、次の \(コンテンツ スクリプト宣言を追加するときに、以下の完全なファイルに表示されます `manifest.json` \)。</span><span class="sxs-lookup"><span data-stu-id="f4175-144">That entry is as follows \(you should see it in the full `manifest.json` file below when you add the content script declaration coming up\).</span></span>  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

<span data-ttu-id="f4175-145">これで、現在アクティブなタブ ページに埋め込まれているコンテンツ ページにメッセージを送信するコードをファイルに記述しましたが、そのコンテンツ ページは作成および挿入されません `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="f4175-145">You've now written the code in your `popup.js` file to send a message to the content page that is embedded on the current active tab page, but you haven't created and injected that content page.</span></span>  <span data-ttu-id="f4175-146">今すぐ行います。</span><span class="sxs-lookup"><span data-stu-id="f4175-146">Do that now.</span></span>  

5.  <span data-ttu-id="f4175-147">コンテンツと web manifest.jsに対するユーザー 設定を更新する</span><span class="sxs-lookup"><span data-stu-id="f4175-147">Update your manifest.json for content and web access</span></span>  

<span data-ttu-id="f4175-148">を含 `manifest.json` む更新され `content-scripts` 、 `web_accessible_resources` 次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f4175-148">The updated `manifest.json` that includes the `content-scripts` and `web_accessible_resources` is as follows.</span></span>  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to show the NASA picture of the day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    },
    "browser_action": {
        "default_popup": "popup/popup.html"
    },
    "content_scripts": [
        {
            "matches": [
              "<all_urls>"
            ],
            "js": ["lib/jquery.min.js","content-scripts/content.js"]
        }
    ],
    "web_accessible_resources": [
        "images/*.jpeg"
    ]
}
```  

<span data-ttu-id="f4175-149">追加したセクションはです `content_scripts` 。</span><span class="sxs-lookup"><span data-stu-id="f4175-149">The section you added is `content_scripts`.</span></span>  <span data-ttu-id="f4175-150">属性 `matches` はに設定されています。つまり、各タブが読み込まれると、すべてのファイルがすべてのブラウザー タブ ページ `<all_urls>` `content_scripts` に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="f4175-150">The `matches` attribute is set to `<all_urls>`, which means that all files in `content_scripts` are injected into all browser tab pages when each tab is loaded.</span></span>  <span data-ttu-id="f4175-151">挿入できるファイルの種類は JavaScript と CSS です。</span><span class="sxs-lookup"><span data-stu-id="f4175-151">The allowed files types that can be injected are JavaScript and CSS.</span></span>  <span data-ttu-id="f4175-152">また、追加しました `libjquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="f4175-152">You also added `libjquery.min.js`.</span></span>  <span data-ttu-id="f4175-153">セクションの上部に記載されているダウンロードから、そのファイルを含めできます。</span><span class="sxs-lookup"><span data-stu-id="f4175-153">You're able to include that from the download mentioned at the top of the section.</span></span>  

6. <span data-ttu-id="f4175-154">jQuery を追加し、関連付けられたスレッドについて理解する</span><span class="sxs-lookup"><span data-stu-id="f4175-154">Add jQuery and understanding the associated thread</span></span>  

<span data-ttu-id="f4175-155">挿入するコンテンツ スクリプトで、jQuery \( \) の使用を `$` 計画します。</span><span class="sxs-lookup"><span data-stu-id="f4175-155">In the content scripts that you're injecting, plan on using jQuery \(`$`\).</span></span>  <span data-ttu-id="f4175-156">jQuery の minified バージョンを追加し、拡張機能パッケージに . `lib\jquery.min.js`</span><span class="sxs-lookup"><span data-stu-id="f4175-156">You added a minified version of jQuery and put it in your Extension package as `lib\jquery.min.js`.</span></span>  <span data-ttu-id="f4175-157">これらのコンテンツ スクリプトは個々のサンドボックスで実行されます。つまり、ページに挿入された jQuery はコンテンツ `popup.js` と共有されません。</span><span class="sxs-lookup"><span data-stu-id="f4175-157">These content scripts run in individual sandboxes, which means that the jQuery injected into the `popup.js` page isn't shared with the content.</span></span>  

<span data-ttu-id="f4175-158">ブラウザー タブが読み込まれた Web ページで JavaScript を実行している場合でも、挿入されたコンテンツにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="f4175-158">Keep in mind that even if the browser tab has JavaScript running on it on the loaded web page, any content injected doesn't have access to that.</span></span>  <span data-ttu-id="f4175-159">挿入された JavaScript には、そのブラウザー タブに読み込まれた実際の DOM へのアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="f4175-159">That injected JavaScript just has access to the actual DOM loaded in that browser tab.</span></span>  

7. <span data-ttu-id="f4175-160">コンテンツ スクリプト メッセージ リスナーの追加</span><span class="sxs-lookup"><span data-stu-id="f4175-160">Add the content script message listener</span></span>  

<span data-ttu-id="f4175-161">セクションに `content-scripts\content.js` 基づいてすべてのブラウザー タブ ページに挿入されるファイルを次に示 `manifest.json` `content-scripts` します。</span><span class="sxs-lookup"><span data-stu-id="f4175-161">Here is that `content-scripts\content.js` file that gets injected into every browser tab page based on your `manifest.json` `content-scripts` section.</span></span>  

```javascript
chrome.runtime.onMessage.addListener(function(request, sender, sendResponse) {
    $("body").prepend(
        `<img  src="${request.url}" id="${request.imageDivId}"
               class="slide-image" /> `
    );
    $("head").prepend(
        `<style>
          .slide-image {
              height: auto;
              width: 100vw;
          }
        </style>`
    );
    $(`#${request.imageDivId}`).click(function() {
        $(`#${request.imageDivId}`).remove(`#${request.imageDivId}`);
    });
    sendResponse({ fromcontent: "This message is from content.js" });
});
```  

<span data-ttu-id="f4175-162">上記の JavaScript では、Extension API メソッドを使用して登録 `listener` `chrome.runtime.onMessage.addListener` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4175-162">Notice that all the above JavaScript does is to register a `listener` using the `chrome.runtime.onMessage.addListener` Extension API method.</span></span>  <span data-ttu-id="f4175-163">このリスナーは、前述の Extension API メソッドで送信したメッセージ `popup.js` のようなメッセージ `chrome.tabs.sendMessage` を待機します。</span><span class="sxs-lookup"><span data-stu-id="f4175-163">This listener waits for messages like the one you sent from the `popup.js` described earlier with the `chrome.tabs.sendMessage` Extension API method.</span></span>  

<span data-ttu-id="f4175-164">メソッドの最初のパラメーターは、最初のパラメーターである要求が渡されるメッセージの詳細を持つ `addListener` 関数です。</span><span class="sxs-lookup"><span data-stu-id="f4175-164">The first parameter of the `addListener` method is a function whose first parameter, request, is the details of the message being passed in.</span></span>  <span data-ttu-id="f4175-165">メソッドを使用する場合は、最初のパラメーターの属性は、 `popup.js` `sendMessage` および `url` `imageDivId` です。</span><span class="sxs-lookup"><span data-stu-id="f4175-165">Remember, from `popup.js`, when you used the `sendMessage` method, those attributes of the first parameter are `url` and `imageDivId`.</span></span>  

<span data-ttu-id="f4175-166">イベントがリスナーによって処理される場合、最初のパラメーターである関数が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4175-166">When an event is processed by the listener, the function that is the first parameter is run.</span></span>  <span data-ttu-id="f4175-167">その関数の最初のパラメーターは、 によって割り当てられた属性を持つオブジェクトです `sendMessage` 。</span><span class="sxs-lookup"><span data-stu-id="f4175-167">The first parameter of that function is an object that has attributes as assigned by `sendMessage`.</span></span>  <span data-ttu-id="f4175-168">この関数は、単に 3 つの jQuery スクリプト行を処理します。</span><span class="sxs-lookup"><span data-stu-id="f4175-168">That function simply processes the three jQuery script lines.</span></span>  

*   <span data-ttu-id="f4175-169">最初のスクリプト行は、要素にクラスとして割り当てる必要があるセクションを DOM ヘッダーに動的 **\<style\>** `slide-image` に挿入 `img` します。</span><span class="sxs-lookup"><span data-stu-id="f4175-169">The first script line dynamically inserts into the DOM header a **\<style\>** section that you must assign as a `slide-image` class to your `img` element.</span></span>  
*   <span data-ttu-id="f4175-170">2 番目のスクリプト行は、クラスが割り当てられているブラウザー タブのすぐ下に、そのイメージ要素の ID として要素 `img` `body` `slide-image` `imageDivId` を追加します。</span><span class="sxs-lookup"><span data-stu-id="f4175-170">The second script line appends an `img` element right below the `body` of your browser tab that has the `slide-image` class assigned as well as the `imageDivId` as the ID of that image element.</span></span>  
*   <span data-ttu-id="f4175-171">3 番目のスクリプト行は、イメージ全体をカバーするイベントを追加し、ユーザーはイメージの任意の場所を選択でき、そのイメージはページ \(と共にイベント リスナー\) から削除されます `click` 。</span><span class="sxs-lookup"><span data-stu-id="f4175-171">The third script line adds a `click` event that covers the entire image allowing the user to select anywhere on the image and that image is removed from the page \(along with it is event listener\).</span></span>  

8. <span data-ttu-id="f4175-172">選択した場合に表示される画像を削除する機能を追加する</span><span class="sxs-lookup"><span data-stu-id="f4175-172">Add functionality to remove the displayed image when selected</span></span>  

<span data-ttu-id="f4175-173">これで、任意のページを参照して [拡張機能] アイコンを選択すると、ポップアップ メニューが次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4175-173">Now, when you browse to any page and select your **Extension** icon, the pop-up menu is displayed as follows.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.htmのアイコンを選択した後に l が表示される":::
   <span data-ttu-id="f4175-175">popup.htmのアイコンを選択した後に l が表示される</span><span class="sxs-lookup"><span data-stu-id="f4175-175">popup.html display after selecting the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after selecting the Extension icon][ImagePart2Popupdialog]  -->  

<span data-ttu-id="f4175-176">ボタンを選択すると `Display` 、以下の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4175-176">When you select the `Display` button, you get what is below.</span></span>  <span data-ttu-id="f4175-177">イメージ上の任意の場所を選択すると、その image 要素が削除され、タブ ページが元の位置に `stars.jpeg` 折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="f4175-177">If you select anywhere on the `stars.jpeg` image, that image element is removed and tab pages collapses back to what was originally displayed.</span></span>  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="ブラウザーに表示される画像":::
   <span data-ttu-id="f4175-179">ブラウザーに表示される画像</span><span class="sxs-lookup"><span data-stu-id="f4175-179">The image showing in browser</span></span>
:::image-end:::

<span data-ttu-id="f4175-180">拡張機能アイコンのポップアップからメッセージを正常に送信する拡張機能を作成し、ブラウザー タブでコンテンツとして実行されている JavaScript を動的に挿入しました。 挿入されたコンテンツは、静的な星の jpeg を表示するイメージ要素を設定します。</span><span class="sxs-lookup"><span data-stu-id="f4175-180">You've created an Extension that successfully sends a message from the extension icon pop-up, and dynamically inserted JavaScript running as content on the browser tab.  The injected content sets the image element to display your static stars jpeg.</span></span>  

<!-- image links -->  


<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part2/extension-getting-started-part2 "完成した拡張パッケージ ソース |Microsoft Docs"  
