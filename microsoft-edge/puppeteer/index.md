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
# <span data-ttu-id="2b898-104">Puppeteer の概要</span><span class="sxs-lookup"><span data-stu-id="2b898-104">Puppeteer overview</span></span>  

<span data-ttu-id="2b898-105">[Chromiueer][|::ref1::|Main]は[][NodejsMain][、DevTools プロトコル][GithubChromedevtoolsProtocol]を使用して Microsoft Edge \(Chromium\) を制御する高レベルの API を提供するノード ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="2b898-105">[Puppeteer][|::ref1::|Main] is a [Node][NodejsMain] library that provides a high-level API to control Microsoft Edge \(Chromium\) using the [DevTools Protocol][GithubChromedevtoolsProtocol].</span></span>  <span data-ttu-id="2b898-106">既定では、ヘッドレス [ブラウザーが][WikiHeadlessBrowser] 起動します。</span><span class="sxs-lookup"><span data-stu-id="2b898-106">Puppeteer launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="2b898-107">ヘッドレス ブラウザーでは UI が表示されないので、代わりにコマンド ラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b898-107">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="2b898-108">また、Microsoft Edge を完全 \(非ヘッドレス\) で実行する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2b898-108">You may also configure Puppeteer to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="2b898-109">既定では、Chromiueer をインストールすると、インストーラーは、Microsoft Edge も構築されているオープン ソース ブラウザー [である Chromium][ChromiumHome]の最新バージョン [をダウンロードします][MicrosoftBlogsWindowsExperience20181206]。</span><span class="sxs-lookup"><span data-stu-id="2b898-109">By default, when you install Puppeteer, the installer downloads a recent version of [Chromium][ChromiumHome], the open-source browser that [Microsoft Edge is also built upon][MicrosoftBlogsWindowsExperience20181206].</span></span>  <span data-ttu-id="2b898-110">Microsoft Edge \(Chromium\) がインストールされている場合は [、core][PuppeteerApivscore]を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b898-110">If you have Microsoft Edge \(Chromium\) installed, you may use [puppeteer-core][PuppeteerApivscore].</span></span>  `puppeteer-core` <span data-ttu-id="2b898-111">は、Microsoft Edge \(Chromium\) など、既存のブラウザー インストールを起動する、ライトウェイト バージョンの OfEr です。</span><span class="sxs-lookup"><span data-stu-id="2b898-111">is a lightweight version of Puppeteer that launches an existing browser installation, like Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="2b898-112">Microsoft Edge \(Chromium\) をダウンロードするには [、Microsoft Edge Insider チャネルのダウンロードに移動します][MicrosoftedgeinsiderDownload]。</span><span class="sxs-lookup"><span data-stu-id="2b898-112">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload].</span></span>  

## <span data-ttu-id="2b898-113">core のインストール</span><span class="sxs-lookup"><span data-stu-id="2b898-113">Installing puppeteer-core</span></span>  

<span data-ttu-id="2b898-114">次のいずれかのコマンド `puppeteer-core` を使用して、Web サイトまたはアプリに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2b898-114">You may add `puppeteer-core` to your website or app with one of the following commands.</span></span>  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## <span data-ttu-id="2b898-115">edgeeer-core を使用して Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="2b898-115">Launch Microsoft Edge with puppeteer-core</span></span>  

> [!NOTE]
> `puppeteer-core` <span data-ttu-id="2b898-116">は Node v8.9.0 以降に依存します。</span><span class="sxs-lookup"><span data-stu-id="2b898-116">relies on Node v8.9.0 or later.</span></span>  <span data-ttu-id="2b898-117">次の例では `async` / `await` 、Node v7.6.0 以降でのみサポートされている機能を使用しています。</span><span class="sxs-lookup"><span data-stu-id="2b898-117">The example below uses `async`/`await` which is only supported in Node v7.6.0 or later.</span></span>  <span data-ttu-id="2b898-118">コマンド `node -v` ラインから実行して、互換性のあるバージョンの Node.js。</span><span class="sxs-lookup"><span data-stu-id="2b898-118">Run `node -v` from the command-line to ensure you have a compatible version of Node.js.</span></span>  

`puppeteer-core` <span data-ttu-id="2b898-119">WebDriver などの他のブラウザー テスト フレームワークのユーザーをよく [理解している必要があります][WebdriverChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="2b898-119">should be familiar to users of other browser-testing-frameworks like [WebDriver][WebdriverChromiumMain].</span></span>  <span data-ttu-id="2b898-120">ブラウザーのインスタンスを作成し、ページを開き、そのページを 1 つの大きな API で操作します。</span><span class="sxs-lookup"><span data-stu-id="2b898-120">You create an instance of the browser, open a page, and then manipulate it with the Puppeteer API.</span></span>  <span data-ttu-id="2b898-121">次のコード サンプルでは、Microsoft Edge \(Chromium\) を起動し、スクリーンショットに移動して、 `puppeteer-core` `https://www.microsoftedgeinsider.com` スクリーンショットを次のように保存します `example.png` 。</span><span class="sxs-lookup"><span data-stu-id="2b898-121">In the following code sample, `puppeteer-core` launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="2b898-122">次のコード スニペットをコピーし、名前を付けて保存します `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="2b898-122">Copy the following code snippet and save it as `example.js`.</span></span>  

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

<span data-ttu-id="2b898-123">`executablePath`Microsoft Edge \(Chromium\) のインストールをポイントするために変更します。</span><span class="sxs-lookup"><span data-stu-id="2b898-123">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="2b898-124">たとえば、macOS では `executablePath` 、Microsoft Edge Canary の設定が必要です `/Applications/Microsoft\ Edge\ Canary.app/` 。</span><span class="sxs-lookup"><span data-stu-id="2b898-124">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="2b898-125">To find the `executablePath` , navigate to and copy the Executable `edge://version` **path** on that page or install the [edge-paths][npmEdgePaths] package with one of the following commands.</span><span class="sxs-lookup"><span data-stu-id="2b898-125">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with one of the following commands.</span></span>  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
<span data-ttu-id="2b898-126">次のコード サンプルでは [、edge-paths][npmEdgePaths] パッケージを使用して、OS 上の Microsoft Edge \(Chromium\) のインストールへのパスをプログラムで検索します。</span><span class="sxs-lookup"><span data-stu-id="2b898-126">The code sample below uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

<span data-ttu-id="2b898-127">最後に、設定 `executablePath: EDGE_PATH` します `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="2b898-127">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="2b898-128">変更内容を保存するには、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b898-128">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="2b898-129">Microsoft Edge \(EdgeHTML\) does not work with `puppeteer-core` .</span><span class="sxs-lookup"><span data-stu-id="2b898-129">Microsoft Edge \(EdgeHTML\) does not work with `puppeteer-core`.</span></span>  <span data-ttu-id="2b898-130">この例を引き [続き実行するには、Microsoft Edge Insider][MicrosoftedgeinsiderDownload] チャネルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b898-130">You must install the [Microsoft Edge Insider channels][MicrosoftedgeinsiderDownload] to continue following this example.</span></span>  

<span data-ttu-id="2b898-131">コマンド ライン `example.js` から実行します。</span><span class="sxs-lookup"><span data-stu-id="2b898-131">Now, run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

`puppeteer-core` <span data-ttu-id="2b898-132">Microsoft Edge を起動し、Web ページに移動して `https://www.microsoftedgeinsider.com` 、スクリーンショットを保存します。</span><span class="sxs-lookup"><span data-stu-id="2b898-132">launches Microsoft Edge, navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot of the webpage.</span></span>  <span data-ttu-id="2b898-133">[page.setViewport() を使用してスクリーンショットのサイズをカスタマイズします][PuppeteerApipagesetviewport]。</span><span class="sxs-lookup"><span data-stu-id="2b898-133">Customize the screenshot size with [page.setViewport()][PuppeteerApipagesetviewport].</span></span>  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="このexample.pngによって生成されたファイルexample.js" lightbox="./media/puppeteer-example.png":::
   <span data-ttu-id="2b898-135">生成 `example.png` されたファイル</span><span class="sxs-lookup"><span data-stu-id="2b898-135">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

<span data-ttu-id="2b898-136">これは、1 つの例にすがって、Automationeer と . `puppeteer-core`</span><span class="sxs-lookup"><span data-stu-id="2b898-136">This is just a simple example of the automation and testing scenarios enabled by Puppeteer and `puppeteer-core`.</span></span>  <span data-ttu-id="2b898-137">に関する詳細と動作の詳細については、「リビター [」を参照してください][|::ref2::|Main]。</span><span class="sxs-lookup"><span data-stu-id="2b898-137">For more information about Puppeteer and how it works, see [Puppeteer][|::ref2::|Main].</span></span>  

## <span data-ttu-id="2b898-138">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="2b898-138">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="2b898-139">Microsoft Edge 開発者チームは、多くの場合、1 人のユーザーと Microsoft Edge の使用に関するフィードバック `puppeteer-core` をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="2b898-139">The Microsoft Edge Developer team is eager to hear your feedback about using Puppeteer, `puppeteer-core`, and Microsoft Edge.</span></span>  <span data-ttu-id="2b898-140">Microsoft Edge **DevTools**の [フィードバックの送信[][TwitterIntentTweetEdgedevtools]] アイコンを使用するか、@EdgeDevToolsをツイートして、Microsoft Edge チームに自分の意見を知らせる。</span><span class="sxs-lookup"><span data-stu-id="2b898-140">Use the **Send Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools] to let the Microsoft Edge team know what you think.</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="2b898-142">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="2b898-142">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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
