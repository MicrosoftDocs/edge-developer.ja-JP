---
description: コンテンツ スクリプトを使用してページ本文タグの下に NASA ピクチャを動的に挿入する
title: 拡張機能のチュートリアルを作成する パート 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, Web 開発, html, css, javascript, developer, extensions
ms.openlocfilehash: c5a17cbc55c6ccb42e06369474cd274d70742494
ms.sourcegitcommit: 31741a0c331816642ceafd20680bd3206c87c7bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "11579730"
---
# <a name="create-an-extension-tutorial-part-2"></a>拡張機能のチュートリアルを作成する パート 2  
  
[このパーツの拡張パッケージ ソースの完成][ArchiveExtensionGettingStartedPart2]    

## <a name="overview"></a>概要  

このチュートリアルでは、次の拡張テクノロジについて説明します。
*   JavaScript ライブラリを拡張機能に挿入する  
*   拡張機能のアセットをブラウザー タブに公開する  
*   既存のブラウザー タブにコンテンツ ページを含む  
*   コンテンツ ページでポップアップからのメッセージをリッスンして応答する  

ポップアップ メニューを更新して、静的星の画像をタイトルと標準の HTML ボタンに置き換える方法について説明します。  このボタンを選択すると、拡張機能に埋め込まれている星の画像がコンテンツ ページに渡されます。  そのイメージは、アクティブなブラウザー タブに挿入されます。詳細については、以下の手順に従います。

1.  ポップアップから画像を削除し、ボタンに置き換える  

まず、タイトルと `popup.html` ボタンを表示する簡単なマークアップでファイルを更新します。  このボタンをすぐにプログラムしますが、今のところ、空の JavaScript ファイルへの参照を含める必要があります `popup.js` 。  更新 HTML を次に示します。  

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

拡張機能を更新して開くと、ポップアップが表示ボタンで開きます。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.htmのアイコンを選択した後に l が表示される":::
   popup.htmのアイコンを選択した後に l が表示される
:::image-end:::

<!--![popup.html display after selecting the Extension icon][ImagePart2Popupdialog]  -->  

2.  ブラウザー タブの上部に画像を表示する更新戦略  

ボタンを追加した後、次のタスクは、アクティブなタブ ページの上部にイメージ ファイル `images/stars.jpeg` を表示することです。  

各タブ ページは、独自のスレッドで実行されます。 また、拡張機能は別のスレッドを使用します。  最初に、タブ ページに挿入されるコンテンツ スクリプトを作成します。  次に、ポップアップからタブ ページで実行されているコンテンツ スクリプトにメッセージを送信します。 コンテンツ スクリプトは、表示するイメージを記述するメッセージを受け取ります。  

3. メッセージを送信するポップアップ JavaScript を作成する  

最初に、まだ作成されていないコンテンツ スクリプトにメッセージを送信するコードを作成して追加します。このスクリプトでは、ブラウザー タブを一瞬作成して挿入 `popup/popup.js` する必要があります。 これを行うには、次のコードはポップアップ `onclick` 表示ボタンにイベントを追加します。  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

イベントで `onclick` 、現在のブラウザー タブを探します。 次に、拡張機能 `chrome.tabs.sendmessage` API を使用して、そのタブにメッセージを送信します。  

そのメッセージでは、表示するイメージの URL を含める必要があります。 また、挿入された画像に割り当てる一意の ID を送信します。  コンテンツ挿入 JavaScript で生成することもできますが、後で明らかな理由から、ここで一意の ID を生成し、まだ作成されていないコンテンツ スクリプトに渡します `popup.js` 。  

次のコード スニペットでは、更新されたコードの概要を示します `popup/popup.js` 。  また、この記事の後半で使用される現在のタブ ID を渡します。  

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

4. 任意のブラウザー タブから stars.jpeg を使用可能にする  

前のセクションのように余分なプレフィックスを付けずに相対 URL を渡すのではなく、クロム拡張機能 API を使用する必要がある理由は、おそらく疑問に `images/stars.jpeg` `chrome.extension.getURL` 思うかもしれません。  ところで、画像を添付して返される余分なプレフィックス `getUrl` は、次のようになります。  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

その理由は、要素の属性を使用してコンテンツ ページにイメージ `src` `img` を挿入しているからです。  コンテンツ ページは、拡張機能を実行しているスレッドと同じではない一意のスレッドで実行されています。  静的イメージ ファイルが正しく動作するには、静的イメージ ファイルを Web アセットとして公開する必要があります。  

ファイルに別のエントリを追加 `manifest.json` して、イメージがすべてのブラウザー タブで使用できると宣言します。  このエントリは、次の \(コンテンツ スクリプト宣言を追加するときに、以下の完全なファイルに表示されます `manifest.json` \)。  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

これで、現在アクティブなタブ ページに埋め込まれているコンテンツ ページにメッセージを送信するコードをファイルに記述しましたが、そのコンテンツ ページは作成および挿入されません `popup.js` 。  今すぐ行います。  

5.  コンテンツと web manifest.jsに対するユーザー 設定を更新する  

を含 `manifest.json` む更新され `content-scripts` 、 `web_accessible_resources` 次のようになります。  

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

追加したセクションはです `content_scripts` 。  属性 `matches` はに設定されています。つまり、各タブが読み込まれると、すべてのファイルがすべてのブラウザー タブ ページ `<all_urls>` `content_scripts` に挿入されます。  挿入できるファイルの種類は JavaScript と CSS です。  また、追加しました `libjquery.min.js` 。  セクションの上部に記載されているダウンロードから、そのファイルを含めできます。  

6. jQuery を追加し、関連付けられたスレッドについて理解する  

挿入するコンテンツ スクリプトで、jQuery \( \) の使用を `$` 計画します。  jQuery の minified バージョンを追加し、拡張機能パッケージに . `lib\jquery.min.js`  これらのコンテンツ スクリプトは個々のサンドボックスで実行されます。つまり、ページに挿入された jQuery はコンテンツ `popup.js` と共有されません。  

ブラウザー タブが読み込まれた Web ページで JavaScript を実行している場合でも、挿入されたコンテンツにはアクセスできません。  挿入された JavaScript には、そのブラウザー タブに読み込まれた実際の DOM へのアクセス権があります。  

7. コンテンツ スクリプト メッセージ リスナーの追加  

セクションに `content-scripts\content.js` 基づいてすべてのブラウザー タブ ページに挿入されるファイルを次に示 `manifest.json` `content-scripts` します。  

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

上記の JavaScript では、Extension API メソッドを使用して登録 `listener` `chrome.runtime.onMessage.addListener` する必要があります。  このリスナーは、前述の Extension API メソッドで送信したメッセージ `popup.js` のようなメッセージ `chrome.tabs.sendMessage` を待機します。  

メソッドの最初のパラメーターは、最初のパラメーターである要求が渡されるメッセージの詳細を持つ `addListener` 関数です。  メソッドを使用する場合は、最初のパラメーターの属性は、 `popup.js` `sendMessage` および `url` `imageDivId` です。  

イベントがリスナーによって処理される場合、最初のパラメーターである関数が実行されます。  その関数の最初のパラメーターは、 によって割り当てられた属性を持つオブジェクトです `sendMessage` 。  この関数は、単に 3 つの jQuery スクリプト行を処理します。  

*   最初のスクリプト行は、要素にクラスとして割り当てる必要があるセクションを DOM ヘッダーに動的 **\<style\>** `slide-image` に挿入 `img` します。  
*   2 番目のスクリプト行は、クラスが割り当てられているブラウザー タブのすぐ下に、そのイメージ要素の ID として要素 `img` `body` `slide-image` `imageDivId` を追加します。  
*   3 番目のスクリプト行は、イメージ全体をカバーするイベントを追加し、ユーザーはイメージの任意の場所を選択でき、そのイメージはページ \(と共にイベント リスナー\) から削除されます `click` 。  

8. 選択した場合に表示される画像を削除する機能を追加する  

これで、任意のページを参照して [拡張機能****] アイコンを選択すると、ポップアップ メニューが次のように表示されます。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.htmのアイコンを選択した後に l が表示される":::
   popup.htmのアイコンを選択した後に l が表示される
:::image-end:::

<!--![popup.html display after selecting the Extension icon][ImagePart2Popupdialog]  -->  

ボタンを選択すると `Display` 、以下の情報が表示されます。  イメージ上の任意の場所を選択すると、その image 要素が削除され、タブ ページが元の位置に `stars.jpeg` 折りたたまれます。  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="ブラウザーに表示される画像":::
   ブラウザーに表示される画像
:::image-end:::

拡張機能アイコンのポップアップからメッセージを正常に送信する拡張機能を作成し、ブラウザー タブでコンテンツとして実行されている JavaScript を動的に挿入しました。 挿入されたコンテンツは、静的な星の jpeg を表示するイメージ要素を設定します。  

<!-- image links -->  


<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part2/extension-getting-started-part2 "完成した拡張パッケージ ソース |Microsoft Docs"  
