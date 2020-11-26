---
description: Puppeteer を使用して Microsoft Edge を自動化およびテストする
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、開発、ツール、オートメーション、テスト
ms.openlocfilehash: e92a863f28c96157b4c7692bd88ba6884cbf8f52
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192234"
---
# Puppeteer  

[Puppeteer][|::ref1::|Main]は、 [devtools プロトコル][GithubChromedevtoolsProtocol]を使用して Microsoft Edge \ (Chromium \) を制御する高レベルの API を提供する[ノード][NodejsMain]ライブラリです。  Puppeteer は既定で [ヘッドレスブラウザー][WikiHeadlessBrowser] を起動します。  ヘッドレスブラウザーでは UI が表示されないため、代わりにコマンドラインを使用する必要があります。  また、Microsoft Edge で完全 \ (非ヘッドレス) を実行するように、Puppeteer を構成することもできます。  

既定では、Puppeteer をインストールすると、インストーラーは最新バージョンの [Chromium][ChromiumHome]をダウンロードします。これに [は、Microsoft Edge も構築さ][MicrosoftBlogsWindowsExperience20181206]れているオープンソースブラウザーを使用します。  Microsoft Edge \ (Chromium \) がインストールされている場合は、 [puppeteer][PuppeteerApivscore]を使うことができます。  `puppeteer-core` は、Microsoft Edge \ (Chromium \) など、既存のブラウザーインストールを起動する簡易バージョンの Puppeteer です。  Microsoft Edge \ (Chromium \) をダウンロードするには、「 [Microsoft Edge Insider チャネルのダウンロード][MicrosoftedgeinsiderDownload]」に移動します。  

## Puppeteer をインストールする-core  

`puppeteer-core`次のいずれかのコマンドを使用して、web サイトまたはアプリに追加することができます。  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## Puppeteer core で Microsoft Edge を起動する  

> [!NOTE]
> `puppeteer-core` Node v 8.9.0 以降に依存します。  次の例では、 `async` / `await` Node v 7.6.0 以降でのみサポートされています。  `node -v`コマンドラインから実行し、互換性のあるバージョンの Node.js があることを確認します。  

`puppeteer-core` [Webdriver][WebDriverEdgehtmlMain]などの他のブラウザーテストフレームワークのユーザーに慣れている必要があります。  ブラウザーのインスタンスを作成し、ページを開き、Puppeteer API で操作します。  次のコードサンプルでは、 `puppeteer-core` Microsoft Edge \ (Chromium \) を起動し、に移動し `https://www.microsoftedgeinsider.com` て、スクリーンショットをとして保存し `example.png` ます。  

次のコードスニペットをコピーして、として保存し `example.js` ます。  

```javascript
const puppeteer = require('puppeteer-core');

(async () => {
  const browser = await puppeteer.launch({
    executablePath: 'C:\\Program Files (x86)\\Microsoft\\Edge Dev\\Application\\msedge.exe'
  });
  const page = await browser.newPage();
  await page.goto('https://www.microsoftedgeinsider.com');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```  

`executablePath`Microsoft Edge \ (Chromium \) のインストールをポイントします。  たとえば、macOS では、 `executablePath` Microsoft Edge カナリアをに設定する必要があり `/Applications/Microsoft\ Edge\ Canary.app/` ます。  を見つけるに `executablePath` `edge://version` は、そのページの **実行可能ファイルのパス** に移動してコピーするか、次のいずれかのコマンドを使用して [エッジパス][npmEdgePaths] パッケージをインストールします。  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
次のコードサンプルでは、 [edge パス][npmEdgePaths] パッケージを使用して、オペレーティングシステムの Microsoft edge \ (Chromium) へのパスがプログラムによって検出されます。

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

最後に、を設定 `executablePath: EDGE_PATH` `example.js` します。  変更内容を保存するには、[保存] をクリックします。  

> [!NOTE]
> Microsoft Edge \ (EdgeHTML \) は、では使用できません `puppeteer-core` 。  この例の後で続行するには、 [Microsoft Edge Insider チャネル][MicrosoftedgeinsiderDownload] をインストールする必要があります。  

次に、 `example.js` コマンドラインから実行します。  

```shell
node example.js
```  

`puppeteer-core` Microsoft Edge を起動し、に移動 `https://www.microsoftedgeinsider.com` して、web ページのスクリーンショットを保存します。  スクリーン [ビューポート ()][PuppeteerApipagesetviewport]を使ってスクリーンショットのサイズをカスタマイズします。  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="example.js によって生成された example.png ファイル" lightbox="./media/puppeteer-example.png":::
   生成される `example.png` ファイル `example.js`  
:::image-end:::  

次の簡単な例では、Puppeteer とによって有効になるオートメーションとテストのシナリオを使用して `puppeteer-core` います。  Puppeteer とそのしくみの詳細については、 [Puppeteer][|::ref2::|Main]に移動してください。  

## Microsoft Edge DevTools チームと連絡を取る  

Microsoft Edge 開発者チームは、Puppeteer、、Microsoft Edge の使用についてのフィードバックをお寄せ `puppeteer-core` ください。  Microsoft edge の DevTools またはツイート[@EdgeDevTools][TwitterIntentTweetEdgedevtools]の [**フィードバックの送信**] アイコンを使用して、microsoft edge チームに自分の感想を伝えます。  


:::image type="complex" source="./devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="./devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!--## See also  

*   [WebDriver (Chromium)][WebdriverChromiumMain]  
*   [WebDriver (EdgeHTML)][WebdriverEdgehtmlMain]  
*   [Chrome DevTools Protocol Viewer on GitHub][GithubChromedevtoolsProtocol]  
*   [Microsoft Edge:  Making the web better through more open source collaboration on Microsoft Experience Blog][MicrosoftBlogsWindowsExperience20181206]  
*   [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload]  
*   [Chromium on The Chromium Projects][ChromiumHome]  
*   [Node.js][NodejsMain]  
*   [Puppeteer][PuppeteerMain]  
*   [puppeteer vs. puppeteer-core][PuppeteerApivscore]  
*   [page.setViewport() on Puppeteer][PuppeteerApipagesetviewport]  
*   [Headless browser on Wikipedia][WikiHeadlessBrowser]  -->  

<!-- links -->  

[WebdriverChromiumMain]: ./webdriver-chromium "WebDriver (Chromium) |Microsoft ドキュメント"  
[WebdriverEdgehtmlMain]: ./webdriver.md "WebDriver (EdgeHTML) |Microsoft ドキュメント"  

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools プロトコルビューアー |GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge: さまざまなオープンソースの共同作業で web の品質を向上させる |Microsoft エクスペリエンスブログ"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium プロジェクト"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "エッジパス |npm"  

[PuppeteerMain]: https://pptr.dev "Puppeteer"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "puppeteer と puppeteer-core |Puppeteer"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "ページの setViewport ポート (ビューポート) |Puppeteer"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools-投稿の投稿 |Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレスブラウザー |Wikipedia"  
