---
description: Puppeteer を使用して Microsoft Edge で自動化とテストを行う
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, Web 開発, 開発者, ツール, オートメーション, テスト
ms.openlocfilehash: 89a4dad3319f8e61f27487973509a8ee5ac23b6a
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480168"
---
# <a name="puppeteer-overview"></a>Puppeteer の概要  

[Puppeteer][|::ref1::|Main]は[][NodejsMain][、DevTools][GithubChromedevtoolsProtocol]プロトコルを使用して Microsoft Edge \(Chromium\) を制御する高レベル API を提供するノード ライブラリです。  Puppeteer は、既定 [でヘッドレス ブラウザーを][WikiHeadlessBrowser] 起動します。  ヘッドレス ブラウザーは UI を表示しないので、代わりにコマンド ラインを使用する必要があります。  また、完全な \(non-headless\) Microsoft Edge を実行するために、Puppeteer を構成することもできます。  

既定では、Puppeteer をインストールすると、インストーラーは最近のバージョンの [Chromium][ChromiumHome] [、Microsoft Edge][MicrosoftBlogsWindowsExperience20181206]も基に構築されているオープン ソース ブラウザーをダウンロードします。  Microsoft Edge \(Chromium\) がインストールされている場合は [、puppeteer-core を使用できます][PuppeteerApivscore]。  `puppeteer-core` は、Microsoft Edge \(Chromium\) のような既存のブラウザー インストールを起動する、軽量バージョンの Puppeteer です。  Microsoft Edge \(Chromium\) をダウンロードするには、[Microsoft Edge Insider チャネルのダウンロード [] に移動します][MicrosoftedgeinsiderDownload]。  

## <a name="installing-puppeteer-core"></a>puppeteer-core のインストール  

次のいずれかのコマンド `puppeteer-core` を使用して、Web サイトまたはアプリに追加できます。  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## <a name="launch-microsoft-edge-with-puppeteer-core"></a>パペットコアを使用して Microsoft Edge を起動する  

> [!NOTE]
> `puppeteer-core` ノード v8.9.0 以降に依存します。  次の例では `async` / `await` 、ノード v7.6.0 以降でのみサポートされているを使用します。  コマンド `node -v` ラインから実行して、互換性のあるバージョンのファイルを使用Node.js。  

`puppeteer-core` WebDriver などの他のブラウザー テスト フレームワークのユーザーに [慣れ親しむ必要があります][WebdriverChromiumMain]。  ブラウザーのインスタンスを作成し、ページを開き、そのインスタンスを Puppeteer API で操作します。  次のコード サンプルでは、Microsoft Edge \(Chromium\) を起動し、に移動し、スクリーンショット `puppeteer-core` `https://www.microsoftedgeinsider.com` をとして保存します `example.png` 。  

次のコード スニペットをコピーし、として保存します `example.js` 。  

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

`executablePath`Microsoft Edge \(Chromium\) のインストールをポイントする変更。  たとえば、macOS では `executablePath` 、For Microsoft Edge Canary をに設定する必要があります `/Applications/Microsoft\ Edge\ Canary.app/` 。  を見つけるには、そのページの実行可能パスに移動してコピーするか、次のいずれかのコマンドを使用してエッジ パス パッケージ `executablePath` `edge://version` をインストールします。 **** [][npmEdgePaths]  

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

最後に、 に `executablePath: EDGE_PATH` 設定 `example.js` します。  変更内容を保存するには、[保存] をクリックします。  

> [!NOTE]
> Microsoft Edge \(EdgeHTML\) は使用しません `puppeteer-core` 。  この例に従って [続行するには、Microsoft Edge Insider][MicrosoftedgeinsiderDownload] チャネルをインストールする必要があります。  

次に、コマンド `example.js` ラインから実行します。  

```shell
node example.js
```  

`puppeteer-core` Microsoft Edge を起動し、Web ページの `https://www.microsoftedgeinsider.com` スクリーンショットに移動し、保存します。  [page.setViewport() を使用してスクリーンショットのサイズをカスタマイズします][PuppeteerApipagesetviewport]。  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="example.pngによって生成されたファイルexample.js" lightbox="./media/puppeteer-example.png":::
   によって `example.png` 生成されるファイル `example.js`  
:::image-end:::  

これは、Puppeteer で有効になっているオートメーションとテストのシナリオの単純な例です `puppeteer-core` 。  Puppeteer の詳細と動作の詳細については [、「Puppeteer」に移動します][|::ref2::|Main]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

Microsoft Edge Developer チームは、Puppeteer、および Microsoft Edge の使用に関するフィードバック `puppeteer-core` を熱心に聞きたいと考えています。  Microsoft Edge **DevTools**の [フィードバックの送信[][TwitterIntentTweetEdgedevtools]] アイコンまたはツイート @EdgeDevToolsを使用して、Microsoft Edge チームに自分の考えをお知らせします。  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!--## See also  

*   [WebDriver (Chromium)][WebdriverChromiumMain]  
*   [WebDriver (EdgeHTML)][ArchiveMicrosoftEdgeLegacyDeveloperWebdriverIndex]  
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

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (クロム) |Microsoft Docs"  

<!--  [ArchiveMicrosoftEdgeLegacyDeveloperWebdriverIndex]: /archive/microsoft-edge/legacy/developer/webdriver/index "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools プロトコル ビューアー |GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge: より多くのオープン ソースの共同作業を通じて、web をより良く|Microsoft Experience Blog"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[ChromiumHome]: https://www.chromium.org/Home "クロム|クロム プロジェクト"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "エッジ パス |npm"  

[PuppeteerMain]: https://pptr.dev "パペット"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "パペットとパペットコアの|パペット"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "page.setViewport(viewport) |パペット"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools - ツイートを投稿|Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
