---
description: 拡張機能の概要パート1
title: コンテンツスクリプトを使用して、ページ本文タグの下に NASA 画像を動的に挿入する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: b37184f0188b72ec868ab3de3f2341c0694ee42c
ms.sourcegitcommit: 0bc1312a1e6a0ac37cf385201db4361fc05184fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10683645"
---
# <span data-ttu-id="34acc-104">コンテンツスクリプトを使用して、ページ本文タグの下に NASA 画像を動的に挿入する</span><span class="sxs-lookup"><span data-stu-id="34acc-104">Dynamically Insert NASA Picture Below The Page Body Tag Using Content Scripts</span></span>  
  
[<span data-ttu-id="34acc-105">このパートの完成した拡張パッケージソース</span><span class="sxs-lookup"><span data-stu-id="34acc-105">Completed Extension Package Source for This Part</span></span>][ArchiveExtensionGettingStartedPart2]  

## <span data-ttu-id="34acc-106">概要</span><span class="sxs-lookup"><span data-stu-id="34acc-106">Overview</span></span>  

<span data-ttu-id="34acc-107">パート2では、作成した星の画像を表示しないようにポップアップメニューを更新する方法について説明します。ただし、その画像をタイトルと標準の HTML ボタンで置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="34acc-107">In part 2, you learn to update your pop-up menu to not show the static stars image you had before, but to replace that image with a title and a standard HTML button.</span></span>  <span data-ttu-id="34acc-108">このボタンは、選択すると、拡張機能に埋め込まれた星の画像をコンテンツページに渡します。</span><span class="sxs-lookup"><span data-stu-id="34acc-108">That button, when selected, passes that stars image, which is embedded in the Extension, to the content page.</span></span>  <span data-ttu-id="34acc-109">この画像は、アクティブなブラウザータブに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="34acc-109">That image, is inserted into the active browser tab.</span></span>  

*   <span data-ttu-id="34acc-110">このガイドで説明する拡張テクノロジ</span><span class="sxs-lookup"><span data-stu-id="34acc-110">Extension technologies covered in this guide</span></span>  
    *   <span data-ttu-id="34acc-111">拡張子に JavaScript ライブラリを挿入する</span><span class="sxs-lookup"><span data-stu-id="34acc-111">Injecting JavaScript libraries into Extension</span></span>  
    *   <span data-ttu-id="34acc-112">ブラウザーのタブへの拡張アセットの公開</span><span class="sxs-lookup"><span data-stu-id="34acc-112">Exposing Extension assets to browser tabs</span></span>  
    *   <span data-ttu-id="34acc-113">既存のブラウザータブにコンテンツページを含める</span><span class="sxs-lookup"><span data-stu-id="34acc-113">Including content pages in existing browser tabs</span></span>  
    *   <span data-ttu-id="34acc-114">コンテンツページでポップアップからのメッセージを聞き、返信する</span><span class="sxs-lookup"><span data-stu-id="34acc-114">Having content pages listen for messages from pop-ups and respond</span></span>  

## <span data-ttu-id="34acc-115">ポップアップから画像を削除し、ボタンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="34acc-115">Remove the image from the pop-up and replace it with a button</span></span>  

<span data-ttu-id="34acc-116">まず、 `popup.html` タイトルとボタンを表示する、いくつかのまっすぐな前方のマークアップでファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="34acc-116">First, update your `popup.html` file with some straight forward markup that displays a title and a button.</span></span>  <span data-ttu-id="34acc-117">このボタンをすぐにプログラムでプログラムしますが、ここでは空の JavaScript ファイルへの参照を含め `popup.js` ます。</span><span class="sxs-lookup"><span data-stu-id="34acc-117">You program that button shortly, but for now, just include a reference to an empty JavaScript file `popup.js`.</span></span>  <span data-ttu-id="34acc-118">次に、更新 HTML を示します。</span><span class="sxs-lookup"><span data-stu-id="34acc-118">Here is update HTML.</span></span>  

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
        <h1>Show the NASA Picture of the Day</h1>
        <h2>(select the image to remove)</h2>
        <button id="sendmessageid">Display</button>
        <script src="popup.js"></script>
    </body>
</html>
```  

<span data-ttu-id="34acc-119">拡張機能を更新して拡張機能起動アイコンを選ぶと、次のポップアップに表示される [表示] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34acc-119">After updating your Extension and selecting the Extension launch icon, the have the following pop-up includes a display button.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="拡張子アイコンを押した後のポップアップ表示":::
   <span data-ttu-id="34acc-121">拡張子アイコンを押した後のポップアップ表示</span><span class="sxs-lookup"><span data-stu-id="34acc-121">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

## <span data-ttu-id="34acc-122">ブラウザータブの上部に画像を表示する方法が更新されました</span><span class="sxs-lookup"><span data-stu-id="34acc-122">Updated strategy to display image at the top of the browser tab</span></span>  

<span data-ttu-id="34acc-123">ボタンを追加した後は、次のタスクとして、 `images/stars.jpeg` アクティブなタブページの上部に画像ファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="34acc-123">After adding the button, the next task is to make it bring up the `images/stars.jpeg` image file at the top of the active tab page.</span></span>  

<span data-ttu-id="34acc-124">各タブページには固有のスレッドがあり、拡張には別個のスレッドがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="34acc-124">Remember, each tab page has a unique own thread and the Extension has a separate thread.</span></span>  <span data-ttu-id="34acc-125">そのため、まずコンテンツスクリプトを作成し、そのコンテンツスクリプトをタブページに挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34acc-125">So, you must first create a content script and inject that content script into the tab page.</span></span>  <span data-ttu-id="34acc-126">この操作を行うと、タブページ上で実行されているコンテンツスクリプトにメッセージを送信する必要があります。コンテンツスクリプトは、表示する画像とその表示方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="34acc-126">Once you do that, you must send a message from your pop-up to that content script running on the tab page telling that content script what image to show, and how to show it.</span></span>  

## <span data-ttu-id="34acc-127">メッセージを送信するためのポップアップ JavaScript の作成</span><span class="sxs-lookup"><span data-stu-id="34acc-127">Creating the pop-up JavaScript to send a message</span></span>  

<span data-ttu-id="34acc-128">最初に、まだ作成されて `popup/popup.js` いないコンテンツスクリプトにメッセージを送信するコードを作成して追加します。これにより、ブラウザータブに一時的に作成して挿入する必要があります。 そのためには、次のコードでは、 `onclick` ポップアップ表示ボタンにイベントを追加します。</span><span class="sxs-lookup"><span data-stu-id="34acc-128">First, create `popup/popup.js` and add code to send a message to your not-yet-created content script that you must momentarily create and inject into your browser tab.  To do that, the following code adds an `onclick` event to your pop-up display button.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

<span data-ttu-id="34acc-129">`onclick`このイベントでは、現在のブラウザーのタブを確認する必要があります (開いているブラウザーが1つだけの場合は、それが1つであることを意味します)。</span><span class="sxs-lookup"><span data-stu-id="34acc-129">In the `onclick` event, what you must do is find the current browser tab \(if there is only one open it is that one\).</span></span>  <span data-ttu-id="34acc-130">その後、そのタブが見つかったら、 `chrome.tabs.sendmessage` EXTENSION API を使ってそのタブにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="34acc-130">Then, once you find that tab, use the `chrome.tabs.sendmessage` Extension API to send a message to that tab.</span></span>  

<span data-ttu-id="34acc-131">このメッセージには、表示する画像の URL を含める必要があります。また、挿入した画像に割り当てる必要がある一意の ID を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34acc-131">In that message you must include the URL to the image you want to display, and you want to send a unique ID that should be assigned to that inserted image.</span></span>  <span data-ttu-id="34acc-132">コンテンツ挿入の JavaScript によって生成されるようにすることもできますが、後で明らかになる理由については、その一意の ID をここで生成 `popup.js` し、まだ作成されていないコンテンツスクリプトに渡します。</span><span class="sxs-lookup"><span data-stu-id="34acc-132">You may choose to let the content insertion JavaScript generate that, but for reasons that become apparent later, generate that unique ID here in `popup.js` and pass it to the not-yet-created content script.</span></span>  

<span data-ttu-id="34acc-133">更新されたファイルを次に示し `popup/popup.js` ます。</span><span class="sxs-lookup"><span data-stu-id="34acc-133">Here is your updated `popup/popup.js` file.</span></span>  <span data-ttu-id="34acc-134">また、それ以降のセクションで必要な現在のタブ ID を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="34acc-134">Also, pass in the current tab ID which you should need in a later section but for now, is not be used.</span></span>  

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

## <span data-ttu-id="34acc-135">任意のブラウザータブから星の .jpeg を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="34acc-135">Making your stars.jpeg available from any browser tab</span></span>  

<span data-ttu-id="34acc-136">このような場合は、前のセクションの `images/stars.jpeg` `chrome.extension.getURL` ように追加プレフィックスを指定せずに、相対 URL を渡す代わりに、CHROME 拡張 API を使用する必要があると考えられます。</span><span class="sxs-lookup"><span data-stu-id="34acc-136">You are probably wondering why, when you pass the `images/stars.jpeg` must you use the `chrome.extension.getURL` chrome Extension API instead of just passing in the relative URL without the extra prefix like in the previous section.</span></span>  <span data-ttu-id="34acc-137">このように、添付された画像によって返される追加のプレフィックスは、 `getUrl` 次のようになります。</span><span class="sxs-lookup"><span data-stu-id="34acc-137">By the way, that extra prefix, returned by `getUrl` with the image attached looks something like the following.</span></span>  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

<span data-ttu-id="34acc-138">その理由は、要素の属性を使用して `src` コンテンツページに画像を挿入するためです `img` 。</span><span class="sxs-lookup"><span data-stu-id="34acc-138">The reason is that you are injecting the image using the `src` attribute of the `img` element into the content page.</span></span>  <span data-ttu-id="34acc-139">コンテンツページは、拡張機能を実行しているスレッドとは異なる固有のスレッドで実行されています。</span><span class="sxs-lookup"><span data-stu-id="34acc-139">The content page is running on a unique thread that is not the same as the thread running the Extension.</span></span>  <span data-ttu-id="34acc-140">静的な画像ファイルを正常に動作させるには、web アセットとして公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34acc-140">You must expose the static image file as a web asset for it to work correctly.</span></span>  

<span data-ttu-id="34acc-141">そのためには、ファイルに別のエントリを追加する必要があり `manifest.json` ます。</span><span class="sxs-lookup"><span data-stu-id="34acc-141">To do that, you must add another entry in the `manifest.json` file.</span></span>  <span data-ttu-id="34acc-142">どのブラウザータブからでもアクセスできるようにイメージを宣言する必要があります。 このエントリは次のようになります (コンテンツスクリプトの宣言を追加するときは、以下の完全なファイルで確認してください `manifest.json` \)。</span><span class="sxs-lookup"><span data-stu-id="34acc-142">You must declare the image to be accessible from any browser tab.  That entry is as follows \(you should see it in the full `manifest.json` file below when you add the content script declaration coming up\).</span></span>  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

<span data-ttu-id="34acc-143">`popup.js`現在のアクティブなタブページに埋め込まれたコンテンツページにメッセージを送信するためのコードをファイルに書き込みましたが、そのコンテンツページを作成して挿入していません。</span><span class="sxs-lookup"><span data-stu-id="34acc-143">You have now written the code in your `popup.js` file to send a message to the content page that is embedded on the current active tab page, but you have not created and injected that content page.</span></span>  <span data-ttu-id="34acc-144">これを実行します。</span><span class="sxs-lookup"><span data-stu-id="34acc-144">Do that now.</span></span>  

## <span data-ttu-id="34acc-145">コンテンツと web アクセス用のマニフェストの更新</span><span class="sxs-lookup"><span data-stu-id="34acc-145">Updating your manifest.json for content and web access</span></span>  

<span data-ttu-id="34acc-146">And を含む更新は次のように `manifest.json` `content-scripts` `web_accessible_resources` なります。</span><span class="sxs-lookup"><span data-stu-id="34acc-146">The updated `manifest.json` that includes the `content-scripts` and `web_accessible_resources` is as follows.</span></span>  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium Extension to show the NASA Picture of the Day.",
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

<span data-ttu-id="34acc-147">追加したセクションは `content_scripts` です。</span><span class="sxs-lookup"><span data-stu-id="34acc-147">The section you added is `content_scripts`.</span></span>  <span data-ttu-id="34acc-148">この属性が設定されて `matches` `<all_urls>` いる場合、 **content_scripts**セクションに含まれるすべてのファイルが、読み込まれるたびにすべてのブラウザータブページに挿入されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="34acc-148">The attribute `matches` set to `<all_urls>` means that all the files mention in the **content_scripts** section is injected into all browser tab pages when each are loaded.</span></span>  <span data-ttu-id="34acc-149">ここに挿入できるファイルの種類は、javascript と css です。</span><span class="sxs-lookup"><span data-stu-id="34acc-149">The allowable types of files that are able to be injected here are javascript and css.</span></span>  <span data-ttu-id="34acc-150">も追加されました `libjquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="34acc-150">You also added `libjquery.min.js`.</span></span>  <span data-ttu-id="34acc-151">このセクションの一番上に記載されているダウンロードからそのような情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="34acc-151">You are able to include that from the download mentioned at the top of the section.</span></span>  

## <span data-ttu-id="34acc-152">JQuery の追加と関連するスレッドの理解</span><span class="sxs-lookup"><span data-stu-id="34acc-152">Adding jQuery and understanding the associated thread</span></span>  

<span data-ttu-id="34acc-153">挿入するコンテンツスクリプトで、jQuery \ (\) の使用を計画し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="34acc-153">In the content scripts you are injecting, plan on using jQuery \(`$`\).</span></span>  <span data-ttu-id="34acc-154">JQuery の縮小版を追加し、内線番号をとして追加しました `lib\jquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="34acc-154">You added a minified version of jQuery and put it in your Extension package as `lib\jquery.min.js`.</span></span>  <span data-ttu-id="34acc-155">これらのコンテンツスクリプトは、並べ替えの個別のサンドボックスで実行されます。つまり、ページに挿入された jQuery は `popup.js` コンテンツと共有されません。</span><span class="sxs-lookup"><span data-stu-id="34acc-155">These content scripts run in an individual sandbox of sorts, which means that the jQuery injected into the `popup.js` page does not share with the content.</span></span>  

<span data-ttu-id="34acc-156">読み込まれた web ページ上の JavaScript がブラウザータブで実行されている場合でも、挿入されたコンテンツにはアクセスできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="34acc-156">Keep in mind that even if the browser tab has JavaScript running on it on the loaded web page, any content injected does not have access to that.</span></span>  <span data-ttu-id="34acc-157">挿入された JavaScript は、そのブラウザータブに読み込まれている実際の DOM にアクセスするだけです。</span><span class="sxs-lookup"><span data-stu-id="34acc-157">That injected JavaScript just has access to the actual DOM loaded in that browser tab.</span></span>  

## <span data-ttu-id="34acc-158">コンテンツスクリプトメッセージリスナーの追加</span><span class="sxs-lookup"><span data-stu-id="34acc-158">Adding the content script message listener</span></span>  

<span data-ttu-id="34acc-159">`content-scripts\content.js`セクションに基づいて、すべてのブラウザータブページに挿入されるファイルを次に示し `manifest.json` `content-scripts` ます。</span><span class="sxs-lookup"><span data-stu-id="34acc-159">Here is that `content-scripts\content.js` file that gets injected into every browser tab page based on your `manifest.json` `content-scripts` section.</span></span>  

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

<span data-ttu-id="34acc-160">上記の JavaScript はすべて、 `listener` EXTENSION API メソッドを使用してを登録することに注意して `chrome.runtime.onMessage.addListener` ください。</span><span class="sxs-lookup"><span data-stu-id="34acc-160">Notice that all the above JavaScript does is to register a `listener` using the `chrome.runtime.onMessage.addListener` Extension API method.</span></span>  <span data-ttu-id="34acc-161">このリスナーは、前に説明したように、Extension API メソッドで送信したメッセージなどのメッセージを待機 `popup.js` `chrome.tabs.sendMessage` します。</span><span class="sxs-lookup"><span data-stu-id="34acc-161">This listener waits for messages like the one you sent from the `popup.js` described earlier with the `chrome.tabs.sendMessage` Extension API method.</span></span>  

<span data-ttu-id="34acc-162">メソッドの1番目のパラメーター `addListener` は、渡されるメッセージの詳細を最初のパラメーターとして要求する関数です。</span><span class="sxs-lookup"><span data-stu-id="34acc-162">The first parameter of the `addListener` method is a function whose first parameter, request, is the details of the message being passed in.</span></span>  <span data-ttu-id="34acc-163">`popup.js`メソッドを使ったとき、最初の `sendMessage` パラメーターの属性は and であることを覚え `url` ておいて `imageDivId` ください。</span><span class="sxs-lookup"><span data-stu-id="34acc-163">Remember, from `popup.js`, when you used the `sendMessage` method, those attributes of the first parameter are `url` and `imageDivId`.</span></span>  

<span data-ttu-id="34acc-164">リスナーによってイベントが処理されると、最初のパラメーターである関数が実行されます。</span><span class="sxs-lookup"><span data-stu-id="34acc-164">When an event is processed by the listener, the function that is the first parameter is run.</span></span>  <span data-ttu-id="34acc-165">この関数の最初のパラメーターは、によって割り当てられた属性を含むオブジェクトです `sendMessage` 。</span><span class="sxs-lookup"><span data-stu-id="34acc-165">The first parameter of that function is an object that has attributes as assigned by `sendMessage`.</span></span>  <span data-ttu-id="34acc-166">この関数は、3つの jQuery スクリプト行を処理するだけです。</span><span class="sxs-lookup"><span data-stu-id="34acc-166">That function simply processes the three jQuery script lines.</span></span>  

*   <span data-ttu-id="34acc-167">最初に、 **\<style\>** クラスとして要素に割り当てる必要があるセクションが DOM ヘッダーに動的に挿入され `slide-image` `img` ます。</span><span class="sxs-lookup"><span data-stu-id="34acc-167">The first dynamically inserts into the DOM header a **\<style\>** section that you must assign as a `slide-image` class to your `img` element.</span></span>  
*   <span data-ttu-id="34acc-168">2番目の例では、 `img` ブラウザーのタブのすぐ下に、そのクラスが割り当てられている `body` クラスと `slide-image` 、 `imageDivId` そのイメージ要素の ID として要素が追加されます。</span><span class="sxs-lookup"><span data-stu-id="34acc-168">The second, appends an `img` element right below the `body` of your browser tab that has the `slide-image` class assigned as well as the `imageDivId` as the ID of that image element.</span></span>  
*   <span data-ttu-id="34acc-169">3番目は、画像全体をカバーするイベントを追加し `click` ます。これにより、ユーザーは画像上の任意の場所を選ぶことができ、その画像はページから (イベントリスナー \ と共に) 削除されます。</span><span class="sxs-lookup"><span data-stu-id="34acc-169">The third adds a `click` event that covers the entire image allowing the user to select any place on the image and that image is be removed from the page \(along with it is event listener\).</span></span>  

## <span data-ttu-id="34acc-170">選択時に表示されている画像を削除する機能の追加</span><span class="sxs-lookup"><span data-stu-id="34acc-170">Adding functionality to remove the displayed image when selected</span></span>  

<span data-ttu-id="34acc-171">これで、任意のページを参照して**拡張機能**アイコンを選択すると、次のようにポップアップメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34acc-171">Now, when you browse to any page and select your **Extension** icon, the pop-up menu is displayed as follows.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="拡張子アイコンを押した後のポップアップ表示":::
   <span data-ttu-id="34acc-173">拡張子アイコンを押した後のポップアップ表示</span><span class="sxs-lookup"><span data-stu-id="34acc-173">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

<span data-ttu-id="34acc-174">ボタンを選択すると `Display` 、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34acc-174">When you select the `Display` button, you get what is below.</span></span>  <span data-ttu-id="34acc-175">画像上の任意の場所を選択する `stars.jpeg` と、その画像要素が削除され、タブページが元の表示に戻るまで折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="34acc-175">If you select anywhere on the `stars.jpeg` image, that image element is removed and tab pages collapses back to what was originally displayed.</span></span>  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="ブラウザーに表示されている画像":::
   <span data-ttu-id="34acc-177">ブラウザーに表示されている画像</span><span class="sxs-lookup"><span data-stu-id="34acc-177">The image showing in browser</span></span>
:::image-end:::

<!--![The image showing in browser][ImagePart2Showingimage]  -->  

<span data-ttu-id="34acc-178">これで、[ブラウザー] タブのコンテンツとして動的に挿入された JavaScript に、拡張子アイコンのポップアップからメッセージを正常に送信できる拡張機能が作成されました。 このように挿入されたコンテンツは、静止した星 jpeg を表示するためにイメージ要素を設定します。</span><span class="sxs-lookup"><span data-stu-id="34acc-178">You have now created an Extension that successfully sends a message from the Extension icon pop-up, to the dynamically inserted JavaScript running as content on the browser tab.  That injected content set the image element to display your static stars jpeg.</span></span>  

<!-- image links -->  

<!--[ImagePart2Popupdialog]: ./media/part2-popupdialog.png "popup.html display after pressing the Extension icon"  -->  
<!--[ImagePart2Showingimage]: ./media/part2-showingimage.png "The image showing in browser"  -->

<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: ./extension-source/extension-getting-started-part2.zip "このパーツの完成した拡張パッケージソース |Microsoft ドキュメント"  