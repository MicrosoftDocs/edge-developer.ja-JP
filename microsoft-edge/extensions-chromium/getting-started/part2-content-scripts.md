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
# 拡張チュートリアルパート2を作成する  
  
[このパートの完成した拡張パッケージソース][ArchiveExtensionGettingStartedPart2]    

## 概要  

このチュートリアルでは、次の拡張技術について説明します。
*   拡張子に JavaScript ライブラリを挿入する  
*   ブラウザーのタブへの拡張アセットの公開  
*   既存のブラウザータブにコンテンツページを含める  
*   コンテンツページでポップアップからのメッセージを聞き、返信する  

ポップアップメニューを更新して、静的なスタート画像をタイトルと標準の HTML ボタンに置き換える方法について説明します。  このボタンは、選択すると、拡張機能に埋め込まれた星の画像をコンテンツページに渡します。  この画像は、アクティブなブラウザータブに挿入されます。詳細については、次の手順に従ってください。

1.  ポップアップから画像を削除し、ボタンに置き換えます。  

まず、 `popup.html` タイトルとボタンを表示する、いくつかのまっすぐな前方のマークアップでファイルを更新します。  このボタンはすぐにプログラムでプログラミングしますが、ここでは空の JavaScript ファイルへの参照を含め `popup.js` ます。  次に、更新 HTML を示します。  

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

拡張機能を更新して開くと、ポップアップボタンが表示されます。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="拡張アイコンを押した後に表示される l popup.htm":::
   拡張アイコンを押した後に表示される l popup.htm
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

2.  ブラウザータブの上部に画像が表示されるように更新方法  

ボタンを追加した後は、次のタスクとして、 `images/stars.jpeg` アクティブなタブページの上部に画像ファイルを設定します。  

タブページはそれぞれ独自のスレッドで実行されることに注意してください。 また、拡張機能では別のスレッドが使用されます。  まず、タブページに挿入されたコンテンツスクリプトを作成します。  次に、ポップアップから、タブページで実行されているコンテンツスクリプトにメッセージを送信します。 コンテンツスクリプトは、どの画像を表示するかを説明するメッセージを受信します。  

3. ポップアップ JavaScript を作成してメッセージを送信する  

最初に、まだ作成されて `popup/popup.js` いないコンテンツスクリプトにメッセージを送信するコードを作成して追加します。これにより、ブラウザータブに一時的に作成して挿入する必要があります。 そのためには、次のコードでは、 `onclick` ポップアップ表示ボタンにイベントを追加します。  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

イベントの `onclick` [現在のブラウザー] タブを見つけます。 次に、拡張 API を使用し `chrome.tabs.sendmessage` て、そのタブにメッセージを送信します。  

このメッセージでは、表示する画像の URL を指定する必要があります。 また、挿入した画像に割り当てるための一意の ID を送信します。  コンテンツ挿入の JavaScript によって生成されるようにすることもできますが、後で明らかになる理由については、その一意の ID をここで生成 `popup.js` し、まだ作成されていないコンテンツスクリプトに渡します。  

次のコードスニペットでは、の更新されたコードの概要を示して `popup/popup.js` います。  また、この記事で後述する現在のタブ ID を渡します。  

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

4. 任意のブラウザータブから星の .jpeg を使用できるようにします。  

このような場合は、前のセクションの `images/stars.jpeg` `chrome.extension.getURL` ように追加プレフィックスを指定せずに、相対 URL を渡す代わりに、Chrome 拡張機能 API を使用する必要があることをお勧めします。  このように、添付された画像によって返される追加のプレフィックスは、 `getUrl` 次のようになります。  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

その理由は、 `src` 要素の属性を使ってコンテンツページに画像を挿入するためです `img` 。  コンテンツページは、拡張機能を実行しているスレッドと同じではない一意のスレッドで実行されています。  静的な画像ファイルを正常に動作させるには、web アセットとして公開する必要があります。  

ファイルに別のエントリを追加して `manifest.json` 、すべてのブラウザータブでその画像が利用可能であることを宣言します。  このエントリは次のようになります (コンテンツスクリプトの宣言を追加するときは、以下の完全なファイルで確認してください `manifest.json` \)。  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

`popup.js`現在のアクティブなタブページに埋め込まれたコンテンツページにメッセージを送信するコードをファイルに記述しましたが、そのコンテンツページを作成して挿入することはできません。  これを実行します。  

5.  コンテンツと web アクセスの manifest.jsを更新する  

And を含む更新は次のように `manifest.json` `content-scripts` `web_accessible_resources` なります。  

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

追加したセクションは `content_scripts` です。  `matches`属性はに設定されてい `<all_urls>` ます。つまり、 `content_scripts` 各タブが読み込まれると、すべてのブラウザータブページにすべてのファイルが挿入されます。  挿入できる許可されているファイルの種類は JavaScript と CSS です。  も追加されました `libjquery.min.js` 。  このセクションの最初に記載されているダウンロードの内容を含めることができます。  

6. JQuery を追加し、関連付けられたスレッドについて理解する  

挿入するコンテンツスクリプトで、jQuery \ (\) の使用を計画し `$` ます。  JQuery の縮小版を追加し、内線番号をとして追加しました `lib\jquery.min.js` 。  これらのコンテンツスクリプトは個々のサンドボックスで実行されるため、ページに挿入された jQuery は `popup.js` コンテンツと共有されません。  

読み込まれた web ページの [ブラウザー] タブで JavaScript を実行している場合でも、挿入されたコンテンツにはアクセスできません。  挿入された JavaScript は、そのブラウザータブに読み込まれている実際の DOM にアクセスするだけです。  

7. コンテンツスクリプトメッセージリスナーを追加する  

`content-scripts\content.js`セクションに基づいて、すべてのブラウザータブページに挿入されるファイルを次に示し `manifest.json` `content-scripts` ます。  

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

上記の JavaScript はすべて、 `listener` EXTENSION API メソッドを使用してを登録することに注意して `chrome.runtime.onMessage.addListener` ください。  このリスナーは、前に説明したように、Extension API メソッドで送信したメッセージなどのメッセージを待機 `popup.js` `chrome.tabs.sendMessage` します。  

メソッドの1番目のパラメーター `addListener` は、渡されるメッセージの詳細を最初のパラメーターとして要求する関数です。  `popup.js`メソッドを使ったとき、最初の `sendMessage` パラメーターの属性は and であることを覚え `url` ておいて `imageDivId` ください。  

リスナーによってイベントが処理されると、最初のパラメーターである関数が実行されます。  この関数の最初のパラメーターは、によって割り当てられた属性を含むオブジェクトです `sendMessage` 。  この関数は、3つの jQuery スクリプト行を処理するだけです。  

*   最初のスクリプト行では、 **\<style\>** クラスとして要素に割り当てる必要があるセクションが DOM ヘッダーに動的に挿入され `slide-image` `img` ます。  
*   2番目のスクリプト行は、その `img` `body` `slide-image` `imageDivId` 画像要素の ID として、そのクラスが割り当てられていることを示す、ブラウザータブのすぐ下に要素を追加します。  
*   3番目のスクリプト行は、ユーザーが画像の任意の場所を選択できるように、画像全体をカバーするイベントを追加し `click` ます。このイベントは、その画像がページから削除されます (その他はイベントリスナーとなります)。  

8. 選択したときに表示される画像を削除する機能を追加する  

これで、任意のページを参照して **拡張機能** アイコンを選択すると、次のようにポップアップメニューが表示されます。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="拡張アイコンを押した後に表示される l popup.htm":::
   拡張アイコンを押した後に表示される l popup.htm
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

ボタンを選択すると `Display` 、次の情報が表示されます。  画像上の任意の場所を選択する `stars.jpeg` と、その画像要素が削除され、タブページが元の表示に戻るまで折りたたまれます。  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="拡張アイコンを押した後に表示される l popup.htm"  
