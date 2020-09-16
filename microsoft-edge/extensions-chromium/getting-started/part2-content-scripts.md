---
description: 拡張機能の概要パート2
title: コンテンツスクリプトを使用して、ページ本文タグの下に NASA 画像を動的に挿入する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 586f0427241e5f01b63a22ce204484dc5e8cf154
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015759"
---
# コンテンツスクリプトを使用して、ページ本文タグの下に NASA 画像を動的に挿入する  

<!--  
[Completed Extension Package Source for This Part][ArchiveExtensionGettingStartedPart2]  
-->  

## 概要  

パート2では、作成した星の画像を表示しないようにポップアップメニューを更新する方法について説明します。ただし、その画像をタイトルと標準の HTML ボタンで置き換えることができます。  このボタンは、選択すると、拡張機能に埋め込まれた星の画像をコンテンツページに渡します。  この画像は、アクティブなブラウザータブに挿入されます。  

*   このガイドで説明する拡張テクノロジ  
    *   拡張子に JavaScript ライブラリを挿入する  
    *   ブラウザーのタブへの拡張アセットの公開  
    *   既存のブラウザータブにコンテンツページを含める  
    *   コンテンツページでポップアップからのメッセージを聞き、返信する  

## ポップアップから画像を削除し、ボタンに置き換えます。  

まず、 `popup.html` タイトルとボタンを表示する、いくつかのまっすぐな前方のマークアップでファイルを更新します。  このボタンをすぐにプログラムでプログラムしますが、ここでは空の JavaScript ファイルへの参照を含め `popup.js` ます。  次に、更新 HTML を示します。  

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

拡張機能を更新して拡張機能起動アイコンを選ぶと、次のポップアップに表示される [表示] ボタンが表示されます。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="拡張アイコンを押した後に表示される l popup.htm":::
   拡張アイコンを押した後に表示される l popup.htm
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

## ブラウザータブの上部に画像を表示する方法が更新されました  

ボタンを追加した後は、次のタスクとして、 `images/stars.jpeg` アクティブなタブページの上部に画像ファイルを設定します。  

各タブページには固有のスレッドがあり、拡張には別個のスレッドがあることに注意してください。  そのため、まずコンテンツスクリプトを作成し、そのコンテンツスクリプトをタブページに挿入する必要があります。  この操作を行うと、タブページ上で実行されているコンテンツスクリプトにメッセージを送信する必要があります。コンテンツスクリプトは、表示する画像とその表示方法を示しています。  

## メッセージを送信するためのポップアップ JavaScript の作成  

最初に、まだ作成されて `popup/popup.js` いないコンテンツスクリプトにメッセージを送信するコードを作成して追加します。これにより、ブラウザータブに一時的に作成して挿入する必要があります。 そのためには、次のコードでは、 `onclick` ポップアップ表示ボタンにイベントを追加します。  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

`onclick`このイベントでは、現在のブラウザーのタブを確認する必要があります (開いているブラウザーが1つだけの場合は、それが1つであることを意味します)。  その後、そのタブが見つかったら、 `chrome.tabs.sendmessage` EXTENSION API を使ってそのタブにメッセージを送信します。  

このメッセージには、表示する画像の URL を含める必要があります。また、挿入した画像に割り当てる必要がある一意の ID を送信する必要があります。  コンテンツ挿入の JavaScript によって生成されるようにすることもできますが、後で明らかになる理由については、その一意の ID をここで生成 `popup.js` し、まだ作成されていないコンテンツスクリプトに渡します。  

更新されたファイルを次に示し `popup/popup.js` ます。  また、それ以降のセクションで必要な現在のタブ ID を渡すことはできません。  

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

## 任意のブラウザータブから星の .jpeg を作成することができます。  

このような場合は、前のセクションの `images/stars.jpeg` `chrome.extension.getURL` ように追加プレフィックスを指定せずに、相対 URL を渡す代わりに、CHROME 拡張 API を使用する必要があると考えられます。  このように、添付された画像によって返される追加のプレフィックスは、 `getUrl` 次のようになります。  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

その理由は、要素の属性を使用して `src` コンテンツページに画像を挿入するためです `img` 。  コンテンツページは、拡張機能を実行しているスレッドとは異なる固有のスレッドで実行されています。  静的な画像ファイルを正常に動作させるには、web アセットとして公開する必要があります。  

そのためには、ファイルに別のエントリを追加する必要があり `manifest.json` ます。  どのブラウザータブからでもアクセスできるようにイメージを宣言する必要があります。 このエントリは次のようになります (コンテンツスクリプトの宣言を追加するときは、以下の完全なファイルで確認してください `manifest.json` \)。  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

`popup.js`現在のアクティブなタブページに埋め込まれたコンテンツページにメッセージを送信するためのコードをファイルに書き込みましたが、そのコンテンツページを作成して挿入していません。  これを実行します。  

## コンテンツと web アクセスの manifest.jsを更新する  

And を含む更新は次のように `manifest.json` `content-scripts` `web_accessible_resources` なります。  

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

追加したセクションは `content_scripts` です。  この属性が設定されて `matches` `<all_urls>` いる場合、 **content_scripts** セクションに含まれるすべてのファイルが、読み込まれるたびにすべてのブラウザータブページに挿入されることを意味します。  ここに挿入できるファイルの種類は、javascript と css です。  も追加されました `libjquery.min.js` 。  このセクションの一番上に記載されているダウンロードからそのような情報を含めることができます。  

## JQuery の追加と関連するスレッドの理解  

挿入するコンテンツスクリプトで、jQuery \ (\) の使用を計画し `$` ます。  JQuery の縮小版を追加し、内線番号をとして追加しました `lib\jquery.min.js` 。  これらのコンテンツスクリプトは、並べ替えの個別のサンドボックスで実行されます。つまり、ページに挿入された jQuery は `popup.js` コンテンツと共有されません。  

読み込まれた web ページ上の JavaScript がブラウザータブで実行されている場合でも、挿入されたコンテンツにはアクセスできないことに注意してください。  挿入された JavaScript は、そのブラウザータブに読み込まれている実際の DOM にアクセスするだけです。  

## コンテンツスクリプトメッセージリスナーの追加  

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

*   最初に、 **\<style\>** クラスとして要素に割り当てる必要があるセクションが DOM ヘッダーに動的に挿入され `slide-image` `img` ます。  
*   2番目の例では、 `img` ブラウザーのタブのすぐ下に、そのクラスが割り当てられている `body` クラスと `slide-image` 、 `imageDivId` そのイメージ要素の ID として要素が追加されます。  
*   3番目は、画像全体をカバーするイベントを追加し `click` ます。これにより、ユーザーは画像上の任意の場所を選ぶことができ、その画像はページから (イベントリスナー \ と共に) 削除されます。  

## 選択時に表示されている画像を削除する機能の追加  

これで、任意のページを参照して **拡張機能** アイコンを選択すると、次のようにポップアップメニューが表示されます。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="拡張アイコンを押した後に表示される l popup.htm":::
   拡張アイコンを押した後に表示される l popup.htm
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

ボタンを選択すると `Display` 、次の情報が表示されます。  画像上の任意の場所を選択する `stars.jpeg` と、その画像要素が削除され、タブページが元の表示に戻るまで折りたたまれます。  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="ブラウザーに表示されている画像":::
   ブラウザーに表示されている画像
:::image-end:::

<!--![The image showing in browser][ImagePart2Showingimage]  -->  

これで、[ブラウザー] タブのコンテンツとして動的に挿入された JavaScript に、拡張子アイコンのポップアップからメッセージを正常に送信できる拡張機能が作成されました。 このように挿入されたコンテンツは、静止した星 jpeg を表示するためにイメージ要素を設定します。  

<!-- image links -->  

<!--[ImagePart2Popupdialog]: ./media/part2-popupdialog.png "popup.html display after pressing the Extension icon"  -->  
<!--[ImagePart2Showingimage]: ./media/part2-showingimage.png "The image showing in browser"  -->

<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: ./extension-source/extension-getting-started-part2.zip "このパーツの完成した拡張パッケージソース |Microsoft ドキュメント"  