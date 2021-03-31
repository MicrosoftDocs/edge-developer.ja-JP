---
description: Puppeteer を使用して Microsoft Edge で自動化とテストを行う
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, Web 開発, 開発者, ツール, オートメーション, テスト
ms.openlocfilehash: 068a2289b0e3bf8fffb49c771b83337abb79ea83
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398470"
---
# <a name="puppeteer-overview"></a><span data-ttu-id="e698b-104">Puppeteer の概要</span><span class="sxs-lookup"><span data-stu-id="e698b-104">Puppeteer overview</span></span>  

<span data-ttu-id="e698b-105">[Puppeteer][|::ref1::|Main]は[][NodejsMain][、DevTools][GithubChromedevtoolsProtocol]プロトコルを使用して Microsoft Edge \(Chromium\) を制御する高レベル API を提供するノード ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="e698b-105">[Puppeteer][|::ref1::|Main] is a [Node][NodejsMain] library that provides a high-level API to control Microsoft Edge \(Chromium\) using the [DevTools Protocol][GithubChromedevtoolsProtocol].</span></span>  <span data-ttu-id="e698b-106">Puppeteer は、既定 [でヘッドレス ブラウザーを][WikiHeadlessBrowser] 起動します。</span><span class="sxs-lookup"><span data-stu-id="e698b-106">Puppeteer launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="e698b-107">ヘッドレス ブラウザーは UI を表示しないので、代わりにコマンド ラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e698b-107">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="e698b-108">また、完全な \(non-headless\) Microsoft Edge を実行するために、Puppeteer を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e698b-108">You may also configure Puppeteer to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="e698b-109">既定では、Puppeteer をインストールすると、インストーラーは最近のバージョンの [Chromium][ChromiumHome] [、Microsoft Edge][MicrosoftBlogsWindowsExperience20181206]も基に構築されているオープン ソース ブラウザーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e698b-109">By default, when you install Puppeteer, the installer downloads a recent version of [Chromium][ChromiumHome], the open-source browser that [Microsoft Edge is also built upon][MicrosoftBlogsWindowsExperience20181206].</span></span>  <span data-ttu-id="e698b-110">Microsoft Edge \(Chromium\) がインストールされている場合は [、puppeteer-core を使用できます][PuppeteerApivscore]。</span><span class="sxs-lookup"><span data-stu-id="e698b-110">If you have Microsoft Edge \(Chromium\) installed, you may use [puppeteer-core][PuppeteerApivscore].</span></span>  `puppeteer-core` <span data-ttu-id="e698b-111">は、Microsoft Edge \(Chromium\) のような既存のブラウザー インストールを起動する、軽量バージョンの Puppeteer です。</span><span class="sxs-lookup"><span data-stu-id="e698b-111">is a lightweight version of Puppeteer that launches an existing browser installation, like Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="e698b-112">Microsoft Edge \(Chromium\) をダウンロードするには、[Microsoft Edge Insider チャネルのダウンロード [] に移動します][MicrosoftedgeinsiderDownload]。</span><span class="sxs-lookup"><span data-stu-id="e698b-112">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload].</span></span>  

## <a name="installing-puppeteer-core"></a><span data-ttu-id="e698b-113">puppeteer-core のインストール</span><span class="sxs-lookup"><span data-stu-id="e698b-113">Installing puppeteer-core</span></span>  

<span data-ttu-id="e698b-114">次のいずれかのコマンド `puppeteer-core` を使用して、Web サイトまたはアプリに追加できます。</span><span class="sxs-lookup"><span data-stu-id="e698b-114">You may add `puppeteer-core` to your website or app with one of the following commands.</span></span>  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## <a name="launch-microsoft-edge-with-puppeteer-core"></a><span data-ttu-id="e698b-115">パペットコアを使用して Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="e698b-115">Launch Microsoft Edge with puppeteer-core</span></span>  

> [!NOTE]
> `puppeteer-core` <span data-ttu-id="e698b-116">ノード v8.9.0 以降に依存します。</span><span class="sxs-lookup"><span data-stu-id="e698b-116">relies on Node v8.9.0 or later.</span></span>  <span data-ttu-id="e698b-117">次の例では `async` / `await` 、ノード v7.6.0 以降でのみサポートされているを使用します。</span><span class="sxs-lookup"><span data-stu-id="e698b-117">The example below uses `async`/`await` which is only supported in Node v7.6.0 or later.</span></span>  <span data-ttu-id="e698b-118">コマンド `node -v` ラインから実行して、互換性のあるバージョンのファイルを使用Node.js。</span><span class="sxs-lookup"><span data-stu-id="e698b-118">Run `node -v` from the command-line to ensure you have a compatible version of Node.js.</span></span>  

`puppeteer-core` <span data-ttu-id="e698b-119">WebDriver などの他のブラウザー テスト フレームワークのユーザーに [慣れ親しむ必要があります][WebdriverChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="e698b-119">should be familiar to users of other browser-testing-frameworks like [WebDriver][WebdriverChromiumMain].</span></span>  <span data-ttu-id="e698b-120">ブラウザーのインスタンスを作成し、ページを開き、そのインスタンスを Puppeteer API で操作します。</span><span class="sxs-lookup"><span data-stu-id="e698b-120">You create an instance of the browser, open a page, and then manipulate it with the Puppeteer API.</span></span>  <span data-ttu-id="e698b-121">次のコード サンプルでは、Microsoft Edge \(Chromium\) を起動し、に移動し、スクリーンショット `puppeteer-core` `https://www.microsoftedgeinsider.com` をとして保存します `example.png` 。</span><span class="sxs-lookup"><span data-stu-id="e698b-121">In the following code sample, `puppeteer-core` launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="e698b-122">次のコード スニペットをコピーし、として保存します `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="e698b-122">Copy the following code snippet and save it as `example.js`.</span></span>  

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

<span data-ttu-id="e698b-123">`executablePath`Microsoft Edge \(Chromium\) のインストールをポイントする変更。</span><span class="sxs-lookup"><span data-stu-id="e698b-123">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="e698b-124">たとえば、macOS では `executablePath` 、For Microsoft Edge Canary をに設定する必要があります `/Applications/Microsoft\ Edge\ Canary.app/` 。</span><span class="sxs-lookup"><span data-stu-id="e698b-124">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="e698b-125">を見つけるには、そのページの実行可能パスに移動してコピーするか、次のいずれかのコマンドを使用してエッジ パス パッケージ `executablePath` `edge://version` をインストールします。  [][npmEdgePaths]</span><span class="sxs-lookup"><span data-stu-id="e698b-125">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with one of the following commands.</span></span>  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
<span data-ttu-id="e698b-126">次のコード サンプルでは [、edge-paths][npmEdgePaths] パッケージを使用して、OS 上の Microsoft Edge \(Chromium\) のインストールへのパスをプログラムで検索します。</span><span class="sxs-lookup"><span data-stu-id="e698b-126">The code sample below uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

<span data-ttu-id="e698b-127">最後に、 に `executablePath: EDGE_PATH` 設定 `example.js` します。</span><span class="sxs-lookup"><span data-stu-id="e698b-127">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="e698b-128">変更内容を保存するには、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e698b-128">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="e698b-129">Microsoft Edge \(EdgeHTML\) は使用しません `puppeteer-core` 。</span><span class="sxs-lookup"><span data-stu-id="e698b-129">Microsoft Edge \(EdgeHTML\) does not work with `puppeteer-core`.</span></span>  <span data-ttu-id="e698b-130">この例に従って [続行するには、Microsoft Edge Insider][MicrosoftedgeinsiderDownload] チャネルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e698b-130">You must install the [Microsoft Edge Insider channels][MicrosoftedgeinsiderDownload] to continue following this example.</span></span>  

<span data-ttu-id="e698b-131">次に、コマンド `example.js` ラインから実行します。</span><span class="sxs-lookup"><span data-stu-id="e698b-131">Now, run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

`puppeteer-core` <span data-ttu-id="e698b-132">Microsoft Edge を起動し、Web ページの `https://www.microsoftedgeinsider.com` スクリーンショットに移動し、保存します。</span><span class="sxs-lookup"><span data-stu-id="e698b-132">launches Microsoft Edge, navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot of the webpage.</span></span>  <span data-ttu-id="e698b-133">[page.setViewport() を使用してスクリーンショットのサイズをカスタマイズします][PuppeteerApipagesetviewport]。</span><span class="sxs-lookup"><span data-stu-id="e698b-133">Customize the screenshot size with [page.setViewport()][PuppeteerApipagesetviewport].</span></span>  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="example.pngによって生成されたファイルexample.js" lightbox="./media/puppeteer-example.png":::
   <span data-ttu-id="e698b-135">によって `example.png` 生成されるファイル</span><span class="sxs-lookup"><span data-stu-id="e698b-135">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

<span data-ttu-id="e698b-136">これは、Puppeteer で有効になっているオートメーションとテストのシナリオの単純な例です `puppeteer-core` 。</span><span class="sxs-lookup"><span data-stu-id="e698b-136">This is just a simple example of the automation and testing scenarios enabled by Puppeteer and `puppeteer-core`.</span></span>  <span data-ttu-id="e698b-137">Puppeteer の詳細と動作の詳細については [、「Puppeteer」に移動します][|::ref2::|Main]。</span><span class="sxs-lookup"><span data-stu-id="e698b-137">For more information about Puppeteer and how it works, navigate to [Puppeteer][|::ref2::|Main].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e698b-138">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="e698b-138">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="e698b-139">Microsoft Edge Developer チームは、Puppeteer、および Microsoft Edge の使用に関するフィードバック `puppeteer-core` を熱心に聞きたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="e698b-139">The Microsoft Edge Developer team is eager to hear your feedback about using Puppeteer, `puppeteer-core`, and Microsoft Edge.</span></span>  <span data-ttu-id="e698b-140">Microsoft Edge **DevTools**の [フィードバックの送信[][TwitterIntentTweetEdgedevtools]] アイコンまたはツイート @EdgeDevToolsを使用して、Microsoft Edge チームに自分の考えをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="e698b-140">Use the **Send Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools] to let the Microsoft Edge team know what you think.</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="e698b-142">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="e698b-142">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (クロム) |Microsoft Docs"  
<!--  [WebdriverEdgehtmlMain]: ../edgehtml/webdriver/index.md "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

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
