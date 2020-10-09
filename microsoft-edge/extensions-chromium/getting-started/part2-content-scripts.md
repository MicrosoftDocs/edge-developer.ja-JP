---
description: コンテンツスクリプトを使用して、ページ本文タグの下に NASA 画像を動的に挿入する
title: 拡張チュートリアルパート2を作成する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 755b70635c93d7331ef3ac985625ba7ac5689679
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104715"
---
# <span data-ttu-id="72d6a-104">拡張チュートリアルパート2を作成する</span><span class="sxs-lookup"><span data-stu-id="72d6a-104">Create an extension tutorial Part 2</span></span>  
  
[<span data-ttu-id="72d6a-105">このパートの完成した拡張パッケージソース</span><span class="sxs-lookup"><span data-stu-id="72d6a-105">Completed Extension Package Source for This Part</span></span>][ArchiveExtensionGettingStartedPart2]    

## <span data-ttu-id="72d6a-106">概要</span><span class="sxs-lookup"><span data-stu-id="72d6a-106">Overview</span></span>  

<span data-ttu-id="72d6a-107">このチュートリアルでは、次の拡張技術について説明します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-107">This tutorial covers the following extension technologies.</span></span>
*   <span data-ttu-id="72d6a-108">拡張子に JavaScript ライブラリを挿入する</span><span class="sxs-lookup"><span data-stu-id="72d6a-108">Injecting JavaScript libraries into extension</span></span>  
*   <span data-ttu-id="72d6a-109">ブラウザーのタブへの拡張アセットの公開</span><span class="sxs-lookup"><span data-stu-id="72d6a-109">Exposing extension assets to browser tabs</span></span>  
*   <span data-ttu-id="72d6a-110">既存のブラウザータブにコンテンツページを含める</span><span class="sxs-lookup"><span data-stu-id="72d6a-110">Including content pages in existing browser tabs</span></span>  
*   <span data-ttu-id="72d6a-111">コンテンツページでポップアップからのメッセージを聞き、返信する</span><span class="sxs-lookup"><span data-stu-id="72d6a-111">Having content pages listen for messages from pop-ups and respond</span></span>  

<span data-ttu-id="72d6a-112">ポップアップメニューを更新して、静的なスタート画像をタイトルと標準の HTML ボタンに置き換える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-112">You'll learn to update your pop-up menu to replace your static starts image with a title and a standard HTML button.</span></span>  <span data-ttu-id="72d6a-113">このボタンは、選択すると、拡張機能に埋め込まれた星の画像をコンテンツページに渡します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-113">That button, when selected, passes that stars image, which is embedded in the extension, to the content page.</span></span>  <span data-ttu-id="72d6a-114">この画像は、アクティブなブラウザータブに挿入されます。詳細については、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="72d6a-114">That image, is inserted into the active browser tab. Follow the below steps for further details.</span></span>

1.  <span data-ttu-id="72d6a-115">ポップアップから画像を削除し、ボタンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-115">Remove the image from the pop-up and replace it with a button</span></span>  

<span data-ttu-id="72d6a-116">まず、 `popup.html` タイトルとボタンを表示する、いくつかのまっすぐな前方のマークアップでファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-116">First, update your `popup.html` file with some straight forward markup that displays a title and a button.</span></span>  <span data-ttu-id="72d6a-117">このボタンはすぐにプログラムでプログラミングしますが、ここでは空の JavaScript ファイルへの参照を含め `popup.js` ます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-117">You'll program that button shortly, but for now, just include a reference to an empty JavaScript file `popup.js`.</span></span>  <span data-ttu-id="72d6a-118">次に、更新 HTML を示します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-118">Here is update HTML.</span></span>  

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

<span data-ttu-id="72d6a-119">拡張機能を更新して開くと、ポップアップボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-119">After updating and opening the extension, a pop-up opens with a display button.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="拡張アイコンを押した後に表示される l popup.htm":::
   <span data-ttu-id="72d6a-121">拡張アイコンを押した後に表示される l popup.htm</span><span class="sxs-lookup"><span data-stu-id="72d6a-121">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

2.  <span data-ttu-id="72d6a-122">ブラウザータブの上部に画像が表示されるように更新方法</span><span class="sxs-lookup"><span data-stu-id="72d6a-122">Update strategy to display image at the top of the browser tab</span></span>  

<span data-ttu-id="72d6a-123">ボタンを追加した後は、次のタスクとして、 `images/stars.jpeg` アクティブなタブページの上部に画像ファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-123">After adding the button, the next task is to make it bring up the `images/stars.jpeg` image file at the top of the active tab page.</span></span>  

<span data-ttu-id="72d6a-124">タブページはそれぞれ独自のスレッドで実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="72d6a-124">Remember, each tab page runs in its own thread.</span></span> <span data-ttu-id="72d6a-125">また、拡張機能では別のスレッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-125">Also, the extension uses a different thread.</span></span>  <span data-ttu-id="72d6a-126">まず、タブページに挿入されたコンテンツスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-126">First, create a content script that is injected into the tab page.</span></span>  <span data-ttu-id="72d6a-127">次に、ポップアップから、タブページで実行されているコンテンツスクリプトにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-127">Then, send a message from your pop-up to that content script running on the tab page.</span></span> <span data-ttu-id="72d6a-128">コンテンツスクリプトは、どの画像を表示するかを説明するメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-128">The content script receives the message, which describes which image should be displayed.</span></span>  

3. <span data-ttu-id="72d6a-129">ポップアップ JavaScript を作成してメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="72d6a-129">Create the pop-up JavaScript to send a message</span></span>  

<span data-ttu-id="72d6a-130">最初に、まだ作成されて `popup/popup.js` いないコンテンツスクリプトにメッセージを送信するコードを作成して追加します。これにより、ブラウザータブに一時的に作成して挿入する必要があります。 そのためには、次のコードでは、 `onclick` ポップアップ表示ボタンにイベントを追加します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-130">First, create `popup/popup.js` and add code to send a message to your not-yet-created content script that you must momentarily create and inject into your browser tab.  To do that, the following code adds an `onclick` event to your pop-up display button.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

<span data-ttu-id="72d6a-131">イベントの `onclick` [現在のブラウザー] タブを見つけます。 次に、拡張 API を使用し `chrome.tabs.sendmessage` て、そのタブにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-131">In the `onclick` event, find the current browser tab.  Then, use the `chrome.tabs.sendmessage` Extension API to send a message to that tab.</span></span>  

<span data-ttu-id="72d6a-132">このメッセージでは、表示する画像の URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72d6a-132">In that message you must include the URL to the image you want to display.</span></span> <span data-ttu-id="72d6a-133">また、挿入した画像に割り当てるための一意の ID を送信します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-133">Also, send a unique ID to assign to the inserted image.</span></span>  <span data-ttu-id="72d6a-134">コンテンツ挿入の JavaScript によって生成されるようにすることもできますが、後で明らかになる理由については、その一意の ID をここで生成 `popup.js` し、まだ作成されていないコンテンツスクリプトに渡します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-134">You may choose to let the content insertion JavaScript generate that, but for reasons that become apparent later, generate that unique ID here in `popup.js` and pass it to the not-yet-created content script.</span></span>  

<span data-ttu-id="72d6a-135">次のコードスニペットでは、の更新されたコードの概要を示して `popup/popup.js` います。</span><span class="sxs-lookup"><span data-stu-id="72d6a-135">The following code snippet outlines the updated code in `popup/popup.js`.</span></span>  <span data-ttu-id="72d6a-136">また、この記事で後述する現在のタブ ID を渡します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-136">Also, pass in the current tab ID, which is used later in this article.</span></span>  

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

4. <span data-ttu-id="72d6a-137">任意のブラウザータブから星の .jpeg を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="72d6a-137">Make your stars.jpeg available from any browser tab</span></span>  

<span data-ttu-id="72d6a-138">このような場合は、前のセクションの `images/stars.jpeg` `chrome.extension.getURL` ように追加プレフィックスを指定せずに、相対 URL を渡す代わりに、Chrome 拡張機能 API を使用する必要があることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="72d6a-138">You're probably wondering why, when you pass the `images/stars.jpeg` must you use the `chrome.extension.getURL` chrome Extension API instead of just passing in the relative URL without the extra prefix like in the previous section.</span></span>  <span data-ttu-id="72d6a-139">このように、添付された画像によって返される追加のプレフィックスは、 `getUrl` 次のようになります。</span><span class="sxs-lookup"><span data-stu-id="72d6a-139">By the way, that extra prefix, returned by `getUrl` with the image attached looks something like the following.</span></span>  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

<span data-ttu-id="72d6a-140">その理由は、 `src` 要素の属性を使ってコンテンツページに画像を挿入するためです `img` 。</span><span class="sxs-lookup"><span data-stu-id="72d6a-140">The reason is that you're injecting the image using the `src` attribute of the `img` element into the content page.</span></span>  <span data-ttu-id="72d6a-141">コンテンツページは、拡張機能を実行しているスレッドと同じではない一意のスレッドで実行されています。</span><span class="sxs-lookup"><span data-stu-id="72d6a-141">The content page is running on a unique thread that isn't the same as the thread running the Extension.</span></span>  <span data-ttu-id="72d6a-142">静的な画像ファイルを正常に動作させるには、web アセットとして公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72d6a-142">You must expose the static image file as a web asset for it to work correctly.</span></span>  

<span data-ttu-id="72d6a-143">ファイルに別のエントリを追加して `manifest.json` 、すべてのブラウザータブでその画像が利用可能であることを宣言します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-143">Add another entry in the `manifest.json` file to declare that the image is available to all browser tabs.</span></span>  <span data-ttu-id="72d6a-144">このエントリは次のようになります (コンテンツスクリプトの宣言を追加するときは、以下の完全なファイルで確認してください `manifest.json` \)。</span><span class="sxs-lookup"><span data-stu-id="72d6a-144">That entry is as follows \(you should see it in the full `manifest.json` file below when you add the content script declaration coming up\).</span></span>  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

<span data-ttu-id="72d6a-145">`popup.js`現在のアクティブなタブページに埋め込まれたコンテンツページにメッセージを送信するコードをファイルに記述しましたが、そのコンテンツページを作成して挿入することはできません。</span><span class="sxs-lookup"><span data-stu-id="72d6a-145">You've now written the code in your `popup.js` file to send a message to the content page that is embedded on the current active tab page, but you haven't created and injected that content page.</span></span>  <span data-ttu-id="72d6a-146">これを実行します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-146">Do that now.</span></span>  

5.  <span data-ttu-id="72d6a-147">コンテンツと web アクセスの manifest.jsを更新する</span><span class="sxs-lookup"><span data-stu-id="72d6a-147">Update your manifest.json for content and web access</span></span>  

<span data-ttu-id="72d6a-148">And を含む更新は次のように `manifest.json` `content-scripts` `web_accessible_resources` なります。</span><span class="sxs-lookup"><span data-stu-id="72d6a-148">The updated `manifest.json` that includes the `content-scripts` and `web_accessible_resources` is as follows.</span></span>  

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

<span data-ttu-id="72d6a-149">追加したセクションは `content_scripts` です。</span><span class="sxs-lookup"><span data-stu-id="72d6a-149">The section you added is `content_scripts`.</span></span>  <span data-ttu-id="72d6a-150">`matches`属性はに設定されてい `<all_urls>` ます。つまり、 `content_scripts` 各タブが読み込まれると、すべてのブラウザータブページにすべてのファイルが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-150">The `matches` attribute is set to `<all_urls>`, which means that all files in `content_scripts` are injected into all browser tab pages when each tab is loaded.</span></span>  <span data-ttu-id="72d6a-151">挿入できる許可されているファイルの種類は JavaScript と CSS です。</span><span class="sxs-lookup"><span data-stu-id="72d6a-151">The allowed files types that can be injected are JavaScript and CSS.</span></span>  <span data-ttu-id="72d6a-152">も追加されました `libjquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="72d6a-152">You also added `libjquery.min.js`.</span></span>  <span data-ttu-id="72d6a-153">このセクションの最初に記載されているダウンロードの内容を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-153">You're able to include that from the download mentioned at the top of the section.</span></span>  

6. <span data-ttu-id="72d6a-154">JQuery を追加し、関連付けられたスレッドについて理解する</span><span class="sxs-lookup"><span data-stu-id="72d6a-154">Add jQuery and understanding the associated thread</span></span>  

<span data-ttu-id="72d6a-155">挿入するコンテンツスクリプトで、jQuery \ (\) の使用を計画し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-155">In the content scripts that you're injecting, plan on using jQuery \(`$`\).</span></span>  <span data-ttu-id="72d6a-156">JQuery の縮小版を追加し、内線番号をとして追加しました `lib\jquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="72d6a-156">You added a minified version of jQuery and put it in your Extension package as `lib\jquery.min.js`.</span></span>  <span data-ttu-id="72d6a-157">これらのコンテンツスクリプトは個々のサンドボックスで実行されるため、ページに挿入された jQuery は `popup.js` コンテンツと共有されません。</span><span class="sxs-lookup"><span data-stu-id="72d6a-157">These content scripts run in individual sandboxes, which means that the jQuery injected into the `popup.js` page isn't shared with the content.</span></span>  

<span data-ttu-id="72d6a-158">読み込まれた web ページの [ブラウザー] タブで JavaScript を実行している場合でも、挿入されたコンテンツにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="72d6a-158">Keep in mind that even if the browser tab has JavaScript running on it on the loaded web page, any content injected doesn't have access to that.</span></span>  <span data-ttu-id="72d6a-159">挿入された JavaScript は、そのブラウザータブに読み込まれている実際の DOM にアクセスするだけです。</span><span class="sxs-lookup"><span data-stu-id="72d6a-159">That injected JavaScript just has access to the actual DOM loaded in that browser tab.</span></span>  

7. <span data-ttu-id="72d6a-160">コンテンツスクリプトメッセージリスナーを追加する</span><span class="sxs-lookup"><span data-stu-id="72d6a-160">Add the content script message listener</span></span>  

<span data-ttu-id="72d6a-161">`content-scripts\content.js`セクションに基づいて、すべてのブラウザータブページに挿入されるファイルを次に示し `manifest.json` `content-scripts` ます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-161">Here is that `content-scripts\content.js` file that gets injected into every browser tab page based on your `manifest.json` `content-scripts` section.</span></span>  

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

<span data-ttu-id="72d6a-162">上記の JavaScript はすべて、 `listener` EXTENSION API メソッドを使用してを登録することに注意して `chrome.runtime.onMessage.addListener` ください。</span><span class="sxs-lookup"><span data-stu-id="72d6a-162">Notice that all the above JavaScript does is to register a `listener` using the `chrome.runtime.onMessage.addListener` Extension API method.</span></span>  <span data-ttu-id="72d6a-163">このリスナーは、前に説明したように、Extension API メソッドで送信したメッセージなどのメッセージを待機 `popup.js` `chrome.tabs.sendMessage` します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-163">This listener waits for messages like the one you sent from the `popup.js` described earlier with the `chrome.tabs.sendMessage` Extension API method.</span></span>  

<span data-ttu-id="72d6a-164">メソッドの1番目のパラメーター `addListener` は、渡されるメッセージの詳細を最初のパラメーターとして要求する関数です。</span><span class="sxs-lookup"><span data-stu-id="72d6a-164">The first parameter of the `addListener` method is a function whose first parameter, request, is the details of the message being passed in.</span></span>  <span data-ttu-id="72d6a-165">`popup.js`メソッドを使ったとき、最初の `sendMessage` パラメーターの属性は and であることを覚え `url` ておいて `imageDivId` ください。</span><span class="sxs-lookup"><span data-stu-id="72d6a-165">Remember, from `popup.js`, when you used the `sendMessage` method, those attributes of the first parameter are `url` and `imageDivId`.</span></span>  

<span data-ttu-id="72d6a-166">リスナーによってイベントが処理されると、最初のパラメーターである関数が実行されます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-166">When an event is processed by the listener, the function that is the first parameter is run.</span></span>  <span data-ttu-id="72d6a-167">この関数の最初のパラメーターは、によって割り当てられた属性を含むオブジェクトです `sendMessage` 。</span><span class="sxs-lookup"><span data-stu-id="72d6a-167">The first parameter of that function is an object that has attributes as assigned by `sendMessage`.</span></span>  <span data-ttu-id="72d6a-168">この関数は、3つの jQuery スクリプト行を処理するだけです。</span><span class="sxs-lookup"><span data-stu-id="72d6a-168">That function simply processes the three jQuery script lines.</span></span>  

*   <span data-ttu-id="72d6a-169">最初のスクリプト行では、 **\<style\>** クラスとして要素に割り当てる必要があるセクションが DOM ヘッダーに動的に挿入され `slide-image` `img` ます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-169">The first script line dynamically inserts into the DOM header a **\<style\>** section that you must assign as a `slide-image` class to your `img` element.</span></span>  
*   <span data-ttu-id="72d6a-170">2番目のスクリプト行は、その `img` `body` `slide-image` `imageDivId` 画像要素の ID として、そのクラスが割り当てられていることを示す、ブラウザータブのすぐ下に要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="72d6a-170">The second script line appends an `img` element right below the `body` of your browser tab that has the `slide-image` class assigned as well as the `imageDivId` as the ID of that image element.</span></span>  
*   <span data-ttu-id="72d6a-171">3番目のスクリプト行は、ユーザーが画像の任意の場所を選択できるように、画像全体をカバーするイベントを追加し `click` ます。このイベントは、その画像がページから削除されます (その他はイベントリスナーとなります)。</span><span class="sxs-lookup"><span data-stu-id="72d6a-171">The third script line adds a `click` event that covers the entire image allowing the user to select anywhere on the image and that image is removed from the page \(along with it is event listener\).</span></span>  

8. <span data-ttu-id="72d6a-172">選択したときに表示される画像を削除する機能を追加する</span><span class="sxs-lookup"><span data-stu-id="72d6a-172">Add functionality to remove the displayed image when selected</span></span>  

<span data-ttu-id="72d6a-173">これで、任意のページを参照して **拡張機能** アイコンを選択すると、次のようにポップアップメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-173">Now, when you browse to any page and select your **Extension** icon, the pop-up menu is displayed as follows.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="拡張アイコンを押した後に表示される l popup.htm":::
   <span data-ttu-id="72d6a-175">拡張アイコンを押した後に表示される l popup.htm</span><span class="sxs-lookup"><span data-stu-id="72d6a-175">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

<span data-ttu-id="72d6a-176">ボタンを選択すると `Display` 、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-176">When you select the `Display` button, you get what is below.</span></span>  <span data-ttu-id="72d6a-177">画像上の任意の場所を選択する `stars.jpeg` と、その画像要素が削除され、タブページが元の表示に戻るまで折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-177">If you select anywhere on the `stars.jpeg` image, that image element is removed and tab pages collapses back to what was originally displayed.</span></span>  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="拡張アイコンを押した後に表示される l popup.htm":::
   <span data-ttu-id="72d6a-179">ブラウザーに表示されている画像</span><span class="sxs-lookup"><span data-stu-id="72d6a-179">The image showing in browser</span></span>
:::image-end:::

<span data-ttu-id="72d6a-180">内線番号のアイコンのポップアップからメッセージを正常に送信し、[ブラウザー] タブのコンテンツとして動的に挿入された JavaScript を作成した拡張機能を作成しました。 挿入されたコンテンツによって、静的な星 jpeg が表示されるようにイメージ要素が設定されます。</span><span class="sxs-lookup"><span data-stu-id="72d6a-180">You've created an Extension that successfully sends a message from the extension icon pop-up, and dynamically inserted JavaScript running as content on the browser tab.  The injected content sets the image element to display your static stars jpeg.</span></span>  

<!-- image links -->  


<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part2/extension-getting-started-part2 "完成した拡張パッケージソース |Microsoft ドキュメント"  
