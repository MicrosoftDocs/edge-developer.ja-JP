---
description: Puppeteer を使用して Microsoft Edge を自動化およびテストする
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、開発、ツール、オートメーション、テスト
ms.openlocfilehash: ccca46426a006651a417a22e54c8b528834b5f81
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844013"
---
# <span data-ttu-id="b4f8d-104">Puppeteer</span><span class="sxs-lookup"><span data-stu-id="b4f8d-104">Puppeteer</span></span>  

<span data-ttu-id="b4f8d-105">[Puppeteer][|::ref1::|Main]は、 [devtools プロトコル][GithubChromedevtoolsProtocol]を介して Microsoft Edge \ (Chromium \) を制御する高レベルの API を提供する[ノード][NodejsMain]ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-105">[Puppeteer][|::ref1::|Main] is a [Node][NodejsMain] library which provides a high-level API to control Microsoft Edge \(Chromium\) over the [DevTools Protocol][GithubChromedevtoolsProtocol].</span></span>  <span data-ttu-id="b4f8d-106">Puppeteer は既定で[ヘッドレス][WikiHeadlessBrowser]を実行します。これは、UI が表示されず、コマンドラインを使う必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-106">Puppeteer runs [headless][WikiHeadlessBrowser] by default, which means that you do not see a UI, and instead must use the command-line.</span></span>  <span data-ttu-id="b4f8d-107">また、Microsoft Edge または Chromium の完全な \ (非ヘッドレス) を実行するように Puppeteer を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-107">You may also configure Puppeteer to run full \(non-headless\) Microsoft Edge or Chromium as well.</span></span>  

<span data-ttu-id="b4f8d-108">既定では、Puppeteer をインストールすると、インストーラーは最新バージョンの[Chromium][ChromiumHome]をダウンロードします。これに[は、Microsoft Edge も構築さ][MicrosoftBlogsWindowsExperience20181206]れているオープンソースブラウザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-108">By default, when you install Puppeteer, the installer downloads a recent version of [Chromium][ChromiumHome], the open-source browser that [Microsoft Edge is also built upon][MicrosoftBlogsWindowsExperience20181206].</span></span>  <span data-ttu-id="b4f8d-109">Microsoft Edge \ (Chromium \) がインストールされている場合は、 [puppeteer][PuppeteerApivscore]を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-109">If you have Microsoft Edge \(Chromium\) installed, you may use [puppeteer-core][PuppeteerApivscore].</span></span>  `puppeteer-core` <span data-ttu-id="b4f8d-110">は、Microsoft Edge \ (Chromium \) など、既存のブラウザーインストールを起動する簡易バージョンの Puppeteer です。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-110">is a lightweight version of Puppeteer that launches an existing browser installation, like Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="b4f8d-111">Microsoft Edge \ (Chromium) をダウンロードするには、「 [Microsoft Edge Insider チャネルをダウンロード][MicrosoftedgeinsiderDownload]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-111">To download Microsoft Edge \(Chromium\), see [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload].</span></span>

## <span data-ttu-id="b4f8d-112">Puppeteer をインストールする-core</span><span class="sxs-lookup"><span data-stu-id="b4f8d-112">Installing puppeteer-core</span></span>  

<span data-ttu-id="b4f8d-113">`puppeteer-core`次のいずれかのコマンドを使用して、web サイトまたはアプリに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-113">You may add `puppeteer-core` to your website or app with one of the following commands.</span></span>  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## <span data-ttu-id="b4f8d-114">Puppeteer core で Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="b4f8d-114">Launch Microsoft Edge with puppeteer-core</span></span>  

> [!NOTE]
> `puppeteer-core` <span data-ttu-id="b4f8d-115">Node v 8.9.0 以降に依存します。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-115">relies on Node v8.9.0 or later.</span></span>  <span data-ttu-id="b4f8d-116">次の例では、 `async` / `await` Node v 7.6.0 以降でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-116">The example below uses `async`/`await` which is only supported in Node v7.6.0 or later.</span></span>  <span data-ttu-id="b4f8d-117">`node -v`コマンドラインから実行し、互換性のあるバージョンの Node.js があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-117">Run `node -v` from the command-line to ensure you have a compatible version of Node.js.</span></span>  

`puppeteer-core` <span data-ttu-id="b4f8d-118">web[ドライバー][WebDriverEdgehtmlMain]など、他のブラウザーのテストフレームワークのユーザーに慣れている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-118">should be familiar to users of other browser-testing-frameworks like [WebDriver][WebDriverEdgehtmlMain].</span></span>  <span data-ttu-id="b4f8d-119">ブラウザーのインスタンスを作成し、ページを開き、Puppeteer API で操作します。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-119">You create an instance of the browser, open a page, and then manipulate it with the Puppeteer API.</span></span>  <span data-ttu-id="b4f8d-120">次のコードサンプルでは、 `puppeteer-core` Microsoft Edge \ (Chromium \) を起動し、に移動し `https://www.microsoftedgeinsider.com` て、スクリーンショットをとして保存し `example.png` ます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-120">In the following code sample, `puppeteer-core` launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="b4f8d-121">以下のコードサンプルをコピーして、として保存し `example.js` ます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-121">Copy the code sample below and save it as `example.js`.</span></span>  

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

<span data-ttu-id="b4f8d-122">`executablePath`Microsoft Edge \ (Chromium \) のインストールをポイントします。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-122">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="b4f8d-123">たとえば、macOS では、 `executablePath` Microsoft Edge カナリアをに設定する必要があり `/Applications/Microsoft\ Edge\ Canary.app/` ます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-123">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="b4f8d-124">を見つけるに `executablePath` `edge://version` は、そのページの**実行可能ファイルのパス**に移動してコピーするか、次のいずれかのコマンドを使用して[エッジパス][npmEdgePaths]パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-124">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with one of the following commands.</span></span>  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
<span data-ttu-id="b4f8d-125">次のコードサンプルでは、 [edge パス][npmEdgePaths]パッケージを使用して、オペレーティングシステムの Microsoft edge \ (Chromium) へのパスがプログラムによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-125">The code sample below uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

<span data-ttu-id="b4f8d-126">最後に、を設定 `executablePath: EDGE_PATH` `example.js` します。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-126">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="b4f8d-127">変更内容を保存するには、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-127">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="b4f8d-128">Microsoft Edge \ (EdgeHTML \) は、では使用できません `puppeteer-core` 。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-128">Microsoft Edge \(EdgeHTML\) does not work with `puppeteer-core`.</span></span>  <span data-ttu-id="b4f8d-129">この例の後で続行するには、 [Microsoft Edge Insider チャネル][MicrosoftedgeinsiderDownload]をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-129">You must install the [Microsoft Edge Insider channels][MicrosoftedgeinsiderDownload] to continue following this example.</span></span>  

<span data-ttu-id="b4f8d-130">それで `example.js` は、コマンドラインから実行します。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-130">Now run `example.js` from the command-line.</span></span>  

```shell
node example.js
```  

`puppeteer-core` <span data-ttu-id="b4f8d-131">Microsoft Edge を起動し、 `https://www.microsoftedgeinsider.com` ページの 800px x 600px のスクリーンショットに移動して保存します。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-131">launches Microsoft Edge, navigates to `https://www.microsoftedgeinsider.com` and saves an 800px x 600px screenshot of the page.</span></span>  <span data-ttu-id="b4f8d-132">ページサイズは、 [page のビューポート ()][PuppeteerApipagesetviewport]でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-132">You are able to customize the page size with [page.setViewport()][PuppeteerApipagesetviewport].</span></span>  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="example.js によって生成された example.png ファイル":::
   <span data-ttu-id="b4f8d-134">図 1: 次の方法で作成された `example.png` ファイル</span><span class="sxs-lookup"><span data-stu-id="b4f8d-134">Figure 1:  The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

<!--  
> ##### Figure 1  
> The `example.png` file produced by `example.js`  
> ![The example.png file produced by example.js](./media/puppeteer-example.png)  
-->  

<span data-ttu-id="b4f8d-135">これは、Puppeteer とによって有効になるオートメーションとテストのシナリオの簡単な例にすぎ `puppeteer-core` ません。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-135">This is just a simple example of the automation and testing scenarios enabled by Puppeteer and `puppeteer-core`.</span></span>  <span data-ttu-id="b4f8d-136">Puppeteer とそのしくみの詳細については、「 [Puppeteer][|::ref2::|Main]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-136">For more information about Puppeteer and how it works, see [Puppeteer][|::ref2::|Main].</span></span>  

## <span data-ttu-id="b4f8d-137">フィードバックの送信</span><span class="sxs-lookup"><span data-stu-id="b4f8d-137">Send Feedback</span></span>  

<span data-ttu-id="b4f8d-138">エッジ開発者チームは、Puppeteer、、および Microsoft Edge の使用についてのフィードバックをお寄せ `puppeteer-core` ください。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-138">The Edge Developer team is eager to hear your feedback about using Puppeteer, `puppeteer-core`, and Microsoft Edge.</span></span>  <span data-ttu-id="b4f8d-139">Microsoft edge の DevTools またはツイート[@EdgeDevTools][TwitterIntentTweetEdgedevtools]の [**フィードバックの送信**] アイコンを使用して、microsoft edge チームに自分の感想を伝えます。</span><span class="sxs-lookup"><span data-stu-id="b4f8d-139">Use the **Send Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools] to let the Microsoft Edge team know what you think.</span></span>  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン":::
   <span data-ttu-id="b4f8d-141">図 2: Microsoft Edge DevTools の**フィードバック**アイコン</span><span class="sxs-lookup"><span data-stu-id="b4f8d-141">Figure 2:  The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
> ##### Figure 2  
> The **Feedback** icon in the Microsoft Edge DevTools  
> ![The Feedback icon in the Microsoft Edge DevTools](./devtools-guide-chromium/media/devtools-feedback.png)  
-->  

<!--## See also  

*   [WebDriver (Chromium)][WebdriverChromiumMain]  
*   [WebDriver (EdgeHTML)][WebdriverEdgehtmlMain]  
*   [Chrome DevTools Protocol Viewer on GitHub][GithubChromedevtoolsProtocol]  
*   [Microsoft Edge: Making the web better through more open source collaboration on Microsoft Experience Blog][MicrosoftBlogsWindowsExperience20181206]  
*   [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload]  
*   [Chromium on The Chromium Projects][ChromiumHome]  
*   [Node.js][NodejsMain]  
*   [Puppeteer][PuppeteerMain]  
*   [puppeteer vs. puppeteer-core][PuppeteerApivscore]  
*   [page.setViewport() on Puppeteer][PuppeteerApipagesetviewport]  
*   [Headless browser on Wikipedia][WikiHeadlessBrowser]  -->  

<!-- image links -->  

<!-- links -->  

[WebdriverChromiumMain]: ./webdriver-chromium.md "WebDriver (Chromium)"  
[WebdriverEdgehtmlMain]: ./webdriver.md "WebDriver (EdgeHTML)"  

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools プロトコルビューアー |GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge: オープンソースのコラボレーションを通じて web をより適切に作成する |Microsoft エクスペリエンスブログ"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium プロジェクト"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "npm |エッジパス"

[PuppeteerMain]: https://pptr.dev "Puppeteer"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "puppeteer と puppeteer-core |Puppeteer"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "ページの setViewport ポート (ビューポート) |Puppeteer"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools-投稿の投稿 |Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレスブラウザー |Wikipedia"  
