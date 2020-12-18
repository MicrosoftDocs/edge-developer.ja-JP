---
description: インピッカーを使用して Microsoft Edge で自動化とテストを行う
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: Microsoft Edge, Web 開発, 開発者, ツール, 自動化, テスト
ms.openlocfilehash: 99d873a9b3988cb8a2827ecc9a69d574a196b037
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234382"
---
# Puppeteer の概要  

[Chromiueer][|::ref1::|Main]は[][NodejsMain][、DevTools プロトコル][GithubChromedevtoolsProtocol]を使用して Microsoft Edge \(Chromium\) を制御する高レベルの API を提供するノード ライブラリです。  既定では、ヘッドレス [ブラウザーが][WikiHeadlessBrowser] 起動します。  ヘッドレス ブラウザーでは UI が表示されないので、代わりにコマンド ラインを使用する必要があります。  また、Microsoft Edge を完全 \(非ヘッドレス\) で実行する場合もあります。  

既定では、Chromiueer をインストールすると、インストーラーは、Microsoft Edge も構築されているオープン ソース ブラウザー [である Chromium][ChromiumHome]の最新バージョン [をダウンロードします][MicrosoftBlogsWindowsExperience20181206]。  Microsoft Edge \(Chromium\) がインストールされている場合は [、core][PuppeteerApivscore]を使用できます。  `puppeteer-core` は、Microsoft Edge \(Chromium\) など、既存のブラウザー インストールを起動する、ライトウェイト バージョンの OfEr です。  Microsoft Edge \(Chromium\) をダウンロードするには [、Microsoft Edge Insider チャネルのダウンロードに移動します][MicrosoftedgeinsiderDownload]。  

## core のインストール  

次のいずれかのコマンド `puppeteer-core` を使用して、Web サイトまたはアプリに追加できます。  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## edgeeer-core を使用して Microsoft Edge を起動する  

> [!NOTE]
> `puppeteer-core` は Node v8.9.0 以降に依存します。  次の例では `async` / `await` 、Node v7.6.0 以降でのみサポートされている機能を使用しています。  コマンド `node -v` ラインから実行して、互換性のあるバージョンの Node.js。  

`puppeteer-core` WebDriver などの他のブラウザー テスト フレームワークのユーザーをよく [理解している必要があります][WebdriverChromiumMain]。  ブラウザーのインスタンスを作成し、ページを開き、そのページを 1 つの大きな API で操作します。  次のコード サンプルでは、Microsoft Edge \(Chromium\) を起動し、スクリーンショットに移動して、 `puppeteer-core` `https://www.microsoftedgeinsider.com` スクリーンショットを次のように保存します `example.png` 。  

次のコード スニペットをコピーし、名前を付けて保存します `example.js` 。  

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

`executablePath`Microsoft Edge \(Chromium\) のインストールをポイントするために変更します。  たとえば、macOS では `executablePath` 、Microsoft Edge Canary の設定が必要です `/Applications/Microsoft\ Edge\ Canary.app/` 。  To find the `executablePath` , navigate to and copy the Executable `edge://version` **path** on that page or install the [edge-paths][npmEdgePaths] package with one of the following commands.  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
次のコード サンプルでは [、edge-paths][npmEdgePaths] パッケージを使用して、OS 上の Microsoft Edge \(Chromium\) のインストールへのパスをプログラムで検索します。

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

最後に、設定 `executablePath: EDGE_PATH` します `example.js` 。  変更内容を保存するには、[保存] をクリックします。  

> [!NOTE]
> Microsoft Edge \(EdgeHTML\) does not work with `puppeteer-core` .  この例を引き [続き実行するには、Microsoft Edge Insider][MicrosoftedgeinsiderDownload] チャネルをインストールする必要があります。  

コマンド ライン `example.js` から実行します。  

```shell
node example.js
```  

`puppeteer-core` Microsoft Edge を起動し、Web ページに移動して `https://www.microsoftedgeinsider.com` 、スクリーンショットを保存します。  [page.setViewport() を使用してスクリーンショットのサイズをカスタマイズします][PuppeteerApipagesetviewport]。  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="このexample.pngによって生成されたファイルexample.js" lightbox="./media/puppeteer-example.png":::
   生成 `example.png` されたファイル `example.js`  
:::image-end:::  

これは、1 つの例にすがって、Automationeer と . `puppeteer-core`  に関する詳細と動作の詳細については、「リビター [」を参照してください][|::ref2::|Main]。  

## Microsoft Edge DevTools チームと連絡を取る  

Microsoft Edge 開発者チームは、多くの場合、1 人のユーザーと Microsoft Edge の使用に関するフィードバック `puppeteer-core` をお寄せください。  Microsoft Edge **DevTools**の [フィードバックの送信[][TwitterIntentTweetEdgedevtools]] アイコンを使用するか、@EdgeDevToolsをツイートして、Microsoft Edge チームに自分の意見を知らせる。  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
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

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft Docs"  
<!--  [WebdriverEdgehtmlMain]: ../edgehtml/webdriver/index.md "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools プロトコル ビューアー |GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge: オープン ソースコラボレーションによる Web の向上 |Microsoft Experience ブログ"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium プロジェクト"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "エッジ パス |npm"  

[PuppeteerMain]: https://pptr.dev "1997 年"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "と core |1997 年"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "page.setViewport(viewport) |1997 年"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools - ツイートを投稿する |Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
