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
# <span data-ttu-id="7a21e-104">Puppeteer</span><span class="sxs-lookup"><span data-stu-id="7a21e-104">Puppeteer</span></span>  

<span data-ttu-id="7a21e-105">[Puppeteer][|::ref1::|Main]は、 [devtools プロトコル][GithubChromedevtoolsProtocol]を使用して Microsoft Edge \ (Chromium \) を制御する高レベルの API を提供する[ノード][NodejsMain]ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="7a21e-105">[Puppeteer][|::ref1::|Main] is a [Node][NodejsMain] library that provides a high-level API to control Microsoft Edge \(Chromium\) using the [DevTools Protocol][GithubChromedevtoolsProtocol].</span></span>  <span data-ttu-id="7a21e-106">Puppeteer は既定で [ヘッドレスブラウザー][WikiHeadlessBrowser] を起動します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-106">Puppeteer launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="7a21e-107">ヘッドレスブラウザーでは UI が表示されないため、代わりにコマンドラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a21e-107">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="7a21e-108">また、Microsoft Edge で完全 \ (非ヘッドレス) を実行するように、Puppeteer を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7a21e-108">You may also configure Puppeteer to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="7a21e-109">既定では、Puppeteer をインストールすると、インストーラーは最新バージョンの [Chromium][ChromiumHome]をダウンロードします。これに [は、Microsoft Edge も構築さ][MicrosoftBlogsWindowsExperience20181206]れているオープンソースブラウザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-109">By default, when you install Puppeteer, the installer downloads a recent version of [Chromium][ChromiumHome], the open-source browser that [Microsoft Edge is also built upon][MicrosoftBlogsWindowsExperience20181206].</span></span>  <span data-ttu-id="7a21e-110">Microsoft Edge \ (Chromium \) がインストールされている場合は、 [puppeteer][PuppeteerApivscore]を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="7a21e-110">If you have Microsoft Edge \(Chromium\) installed, you may use [puppeteer-core][PuppeteerApivscore].</span></span>  `puppeteer-core` <span data-ttu-id="7a21e-111">は、Microsoft Edge \ (Chromium \) など、既存のブラウザーインストールを起動する簡易バージョンの Puppeteer です。</span><span class="sxs-lookup"><span data-stu-id="7a21e-111">is a lightweight version of Puppeteer that launches an existing browser installation, like Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="7a21e-112">Microsoft Edge \ (Chromium \) をダウンロードするには、「 [Microsoft Edge Insider チャネルのダウンロード][MicrosoftedgeinsiderDownload]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-112">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload].</span></span>  

## <span data-ttu-id="7a21e-113">Puppeteer をインストールする-core</span><span class="sxs-lookup"><span data-stu-id="7a21e-113">Installing puppeteer-core</span></span>  

<span data-ttu-id="7a21e-114">`puppeteer-core`次のいずれかのコマンドを使用して、web サイトまたはアプリに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7a21e-114">You may add `puppeteer-core` to your website or app with one of the following commands.</span></span>  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## <span data-ttu-id="7a21e-115">Puppeteer core で Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="7a21e-115">Launch Microsoft Edge with puppeteer-core</span></span>  

> [!NOTE]
> `puppeteer-core` <span data-ttu-id="7a21e-116">Node v 8.9.0 以降に依存します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-116">relies on Node v8.9.0 or later.</span></span>  <span data-ttu-id="7a21e-117">次の例では、 `async` / `await` Node v 7.6.0 以降でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7a21e-117">The example below uses `async`/`await` which is only supported in Node v7.6.0 or later.</span></span>  <span data-ttu-id="7a21e-118">`node -v`コマンドラインから実行し、互換性のあるバージョンの Node.js があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-118">Run `node -v` from the command-line to ensure you have a compatible version of Node.js.</span></span>  

`puppeteer-core` <span data-ttu-id="7a21e-119">[Webdriver][WebDriverEdgehtmlMain]などの他のブラウザーテストフレームワークのユーザーに慣れている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a21e-119">should be familiar to users of other browser-testing frameworks like [WebDriver][WebDriverEdgehtmlMain].</span></span>  <span data-ttu-id="7a21e-120">ブラウザーのインスタンスを作成し、ページを開き、Puppeteer API で操作します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-120">You create an instance of the browser, open a page, and then manipulate it with the Puppeteer API.</span></span>  <span data-ttu-id="7a21e-121">次のコードサンプルでは、 `puppeteer-core` Microsoft Edge \ (Chromium \) を起動し、に移動し `https://www.microsoftedgeinsider.com` て、スクリーンショットをとして保存し `example.png` ます。</span><span class="sxs-lookup"><span data-stu-id="7a21e-121">In the following code sample, `puppeteer-core` launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="7a21e-122">次のコードスニペットをコピーして、として保存し `example.js` ます。</span><span class="sxs-lookup"><span data-stu-id="7a21e-122">Copy the following code snippet and save it as `example.js`.</span></span>  

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

<span data-ttu-id="7a21e-123">`executablePath`Microsoft Edge \ (Chromium \) のインストールをポイントします。</span><span class="sxs-lookup"><span data-stu-id="7a21e-123">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="7a21e-124">たとえば、macOS では、 `executablePath` Microsoft Edge カナリアをに設定する必要があり `/Applications/Microsoft\ Edge\ Canary.app/` ます。</span><span class="sxs-lookup"><span data-stu-id="7a21e-124">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="7a21e-125">を見つけるに `executablePath` `edge://version` は、そのページの **実行可能ファイルのパス** に移動してコピーするか、次のいずれかのコマンドを使用して [エッジパス][npmEdgePaths] パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a21e-125">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with one of the following commands.</span></span>  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
<span data-ttu-id="7a21e-126">次のコードサンプルでは、 [edge パス][npmEdgePaths] パッケージを使用して、オペレーティングシステムの Microsoft edge \ (Chromium) へのパスがプログラムによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="7a21e-126">The code sample below uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

<span data-ttu-id="7a21e-127">最後に、を設定 `executablePath: EDGE_PATH` `example.js` します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-127">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="7a21e-128">変更内容を保存するには、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a21e-128">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="7a21e-129">Microsoft Edge \ (EdgeHTML \) は、では使用できません `puppeteer-core` 。</span><span class="sxs-lookup"><span data-stu-id="7a21e-129">Microsoft Edge \(EdgeHTML\) does not work with `puppeteer-core`.</span></span>  <span data-ttu-id="7a21e-130">この例の後で続行するには、 [Microsoft Edge Insider チャネル][MicrosoftedgeinsiderDownload] をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a21e-130">You must install the [Microsoft Edge Insider channels][MicrosoftedgeinsiderDownload] to continue following this example.</span></span>  

<span data-ttu-id="7a21e-131">次に、 `example.js` コマンドラインから実行します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-131">Now, run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

`puppeteer-core` <span data-ttu-id="7a21e-132">Microsoft Edge を起動し、に移動 `https://www.microsoftedgeinsider.com` して、web ページのスクリーンショットを保存します。</span><span class="sxs-lookup"><span data-stu-id="7a21e-132">launches Microsoft Edge, navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot of the webpage.</span></span>  <span data-ttu-id="7a21e-133">スクリーン [ビューポート ()][PuppeteerApipagesetviewport]を使ってスクリーンショットのサイズをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="7a21e-133">Customize the screenshot size with [page.setViewport()][PuppeteerApipagesetviewport].</span></span>  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="example.js によって生成された example.png ファイル" lightbox="./media/puppeteer-example.png":::
   <span data-ttu-id="7a21e-135">生成される `example.png` ファイル</span><span class="sxs-lookup"><span data-stu-id="7a21e-135">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

<span data-ttu-id="7a21e-136">次の簡単な例では、Puppeteer とによって有効になるオートメーションとテストのシナリオを使用して `puppeteer-core` います。</span><span class="sxs-lookup"><span data-stu-id="7a21e-136">The following simple example uses automation and testing scenarios enabled by Puppeteer and `puppeteer-core`.</span></span>  <span data-ttu-id="7a21e-137">Puppeteer とそのしくみの詳細については、 [Puppeteer][|::ref2::|Main]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="7a21e-137">For more information about Puppeteer and how it works, navigate to [Puppeteer][|::ref2::|Main].</span></span>  

## <span data-ttu-id="7a21e-138">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="7a21e-138">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="7a21e-139">Microsoft Edge 開発者チームは、Puppeteer、、Microsoft Edge の使用についてのフィードバックをお寄せ `puppeteer-core` ください。</span><span class="sxs-lookup"><span data-stu-id="7a21e-139">The Microsoft Edge Developer team is eager to hear your feedback about using Puppeteer, `puppeteer-core`, and Microsoft Edge.</span></span>  <span data-ttu-id="7a21e-140">Microsoft edge の DevTools またはツイート[@EdgeDevTools][TwitterIntentTweetEdgedevtools]の [**フィードバックの送信**] アイコンを使用して、microsoft edge チームに自分の感想を伝えます。</span><span class="sxs-lookup"><span data-stu-id="7a21e-140">Use the **Send Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools] to let the Microsoft Edge team know what you think.</span></span>  


:::image type="complex" source="./devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="./devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="7a21e-142">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="7a21e-142">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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
