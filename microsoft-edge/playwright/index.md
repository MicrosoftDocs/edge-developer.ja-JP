---
description: Playwright を使用して Microsoft Edge で自動化とテストを行う
title: Playwright
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/24/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, Web 開発, 開発者, ツール, 自動化, テスト, プレイライト, ノード, javascript, npm
ms.openlocfilehash: 5ce51864177731dd1bafb845466abb00cce1e0aa
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231084"
---
# <span data-ttu-id="ebf96-104">Playwright</span><span class="sxs-lookup"><span data-stu-id="ebf96-104">Playwright</span></span>  

<span data-ttu-id="ebf96-105">[Playwright][|::ref1::|Main]は[、Node.js][NodejsMain] API を使用して Chromium、Firefox、WebKit を自動化するための新しいライブラリです。 [][ChromiumHome] [][FirefoxMain] [][|::ref2::|Main]</span><span class="sxs-lookup"><span data-stu-id="ebf96-105">[Playwright][|::ref1::|Main] is a [Node.js][NodejsMain] library to automate [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref2::|Main] with a single API.</span></span>  <span data-ttu-id="ebf96-106">Playwright は、常に緑化され、機能し、信頼性が高く、高速なクロスブラウザー Web オートメーションを実現するために構築されています。</span><span class="sxs-lookup"><span data-stu-id="ebf96-106">Playwright is built to enable cross-browser web automation that is ever-green, capable, reliable, and fast.</span></span>  <span data-ttu-id="ebf96-107">[Microsoft Edge はオープン ソースの Chromium Web][MicrosoftBlogsWindowsExperience20181206]プラットフォームに基づいているので、Playwright は Microsoft Edge を自動化することも可能です。</span><span class="sxs-lookup"><span data-stu-id="ebf96-107">Since [Microsoft Edge is built on the open-source Chromium web platform][MicrosoftBlogsWindowsExperience20181206], Playwright is also able to automate Microsoft Edge.</span></span>  

<span data-ttu-id="ebf96-108">Playwright は、既定 [でヘッドレス ブラウザーを][WikiHeadlessBrowser] 起動します。</span><span class="sxs-lookup"><span data-stu-id="ebf96-108">Playwright launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="ebf96-109">ヘッドレス ブラウザーでは UI が表示されないので、代わりにコマンド ラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebf96-109">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="ebf96-110">また、Microsoft Edge を完全 \(ヘッドレス\) で実行する Playwright を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebf96-110">You may also configure Playwright to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="ebf96-111">既定では、Playwright をインストールすると、インストーラーは[Chromium、Firefox、][ChromiumHome][および WebKit をダウンロードします][|::ref3::|Main]。 [][FirefoxMain]</span><span class="sxs-lookup"><span data-stu-id="ebf96-111">By default, when you install Playwright, the installer downloads [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref3::|Main].</span></span>  <span data-ttu-id="ebf96-112">Microsoft Edge \(Chromium\) もインストールされている場合、Playwright は、Microsoft Edge で Web サイトまたはアプリをテストするために 1 行のコード変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="ebf96-112">If you have Microsoft Edge \(Chromium\) installed as well, Playwright just needs a one-line code change to test your website or app in Microsoft Edge.</span></span>  <span data-ttu-id="ebf96-113">Microsoft Edge \(Chromium\) をダウンロードするには [、Microsoft Edge のダウンロードに移動します][MicrosoftEdgeDownload]。</span><span class="sxs-lookup"><span data-stu-id="ebf96-113">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge][MicrosoftEdgeDownload].</span></span>  

## <span data-ttu-id="ebf96-114">Playwright のインストール</span><span class="sxs-lookup"><span data-stu-id="ebf96-114">Installing Playwright</span></span>  

<span data-ttu-id="ebf96-115">[Playwright をインストールし][|::ref4::|Main]、次のコマンドを使用して Web サイトまたはアプリをテストします。</span><span class="sxs-lookup"><span data-stu-id="ebf96-115">Install [Playwright][|::ref4::|Main] to test your website or app with the following command.</span></span>  

```shell
npm i playwright
```  

## <span data-ttu-id="ebf96-116">Playwright で Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="ebf96-116">Launch Microsoft Edge with Playwright</span></span>  

> [!NOTE]
> <span data-ttu-id="ebf96-117">[Playwright では、Node.js][|::ref5::|Main] バージョン 10.17 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="ebf96-117">[Playwright][|::ref5::|Main] requires Node.js version 10.17 or above.</span></span> <span data-ttu-id="ebf96-118">コマンド `node -v` ラインから実行して、互換性のあるバージョンの Node.js。</span><span class="sxs-lookup"><span data-stu-id="ebf96-118">Run `node -v` from the command line to ensure you have a compatible version of Node.js.</span></span>  <span data-ttu-id="ebf96-119">Chromium、Firefox、WebKit のブラウザー バイナリは、Windows、macOS、Linux で動作します。</span><span class="sxs-lookup"><span data-stu-id="ebf96-119">The browser binaries for Chromium, Firefox and WebKit work across Windows, macOS, and Linux.</span></span> <span data-ttu-id="ebf96-120">詳細については [、「Playwright System Requirements」に移動してください][PlaywrightSystemRequirements]。</span><span class="sxs-lookup"><span data-stu-id="ebf96-120">For more information, navigate to [Playwright System Requirements][PlaywrightSystemRequirements].</span></span>  

<span data-ttu-id="ebf96-121">Playwright は [、WebDriver][WebDriverChromiumMain] や Browsereer などの他のブラウザー テスト フレームワークのユーザーをよく理解 [している必要があります][PuppeteerMain]。</span><span class="sxs-lookup"><span data-stu-id="ebf96-121">Playwright should be familiar to users of other browser-testing frameworks like [WebDriver][WebDriverChromiumMain] or [Puppeteer][PuppeteerMain].</span></span>  <span data-ttu-id="ebf96-122">ブラウザーのインスタンスを作成し、ページを開き [、Playwright API を使用して操作します][PlaywrightAPIReference]。</span><span class="sxs-lookup"><span data-stu-id="ebf96-122">You create an instance of the browser, open a page, and then manipulate it with the [Playwright API][PlaywrightAPIReference].</span></span>  <span data-ttu-id="ebf96-123">次のコード スニペットでは、Playwright は Microsoft Edge \(Chromium\) を起動し、スクリーンショットに移動して保存 `https://www.microsoft.com/edge` します `example.png` 。</span><span class="sxs-lookup"><span data-stu-id="ebf96-123">In the following code snippet, Playwright launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoft.com/edge`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="ebf96-124">次のコード スニペットをコピーし、名前を付けて保存します `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="ebf96-124">Copy the following code snippet and save it as `example.js`.</span></span>  

```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch({
    executablePath: 'C:\\Program Files (x86)\\Microsoft\\Edge Dev\\Application\\msedge.exe'
  });
  const page = await browser.newPage();
  await page.goto('https://www.microsoft.com/edge');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```  

<span data-ttu-id="ebf96-125">`executablePath`Microsoft Edge \(Chromium\) のインストールをポイントするために変更します。</span><span class="sxs-lookup"><span data-stu-id="ebf96-125">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="ebf96-126">たとえば、macOS では `executablePath` 、Microsoft Edge Canary の設定が必要です `/Applications/Microsoft\ Edge\ Canary.app/` 。</span><span class="sxs-lookup"><span data-stu-id="ebf96-126">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="ebf96-127">To find the `executablePath` , navigate to and copy the Executable `edge://version` **path** on that page or install the [edge-paths][npmEdgePaths] package with the following command.</span><span class="sxs-lookup"><span data-stu-id="ebf96-127">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with the following command.</span></span>  

```shell
npm i edge-paths
```  

<span data-ttu-id="ebf96-128">次のコード スニペットでは、 [エッジ パス][npmEdgePaths] パッケージを使用して、OS 上の Microsoft Edge \(Chromium\) のインストールへのパスをプログラムによって検索します。</span><span class="sxs-lookup"><span data-stu-id="ebf96-128">The following code snippet uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

<span data-ttu-id="ebf96-129">最後に、設定 `executablePath: EDGE_PATH` します `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="ebf96-129">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="ebf96-130">変更内容を保存するには、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ebf96-130">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="ebf96-131">Microsoft Edge \(EdgeHTML\) は、Playwright では動作しません。</span><span class="sxs-lookup"><span data-stu-id="ebf96-131">Microsoft Edge \(EdgeHTML\) does not work with Playwright.</span></span>  <span data-ttu-id="ebf96-132">この例を引 [き続き実行するには、Microsoft Edge \(Chromium\)][MicrosoftEdgeDownload] をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebf96-132">You must install [Microsoft Edge \(Chromium\)][MicrosoftEdgeDownload] to continue following this example.</span></span>  

<span data-ttu-id="ebf96-133">コマンド ライン `example.js` から実行します。</span><span class="sxs-lookup"><span data-stu-id="ebf96-133">Now run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

<span data-ttu-id="ebf96-134">Playwright は Microsoft Edge を起動し、ページに移動して、ページ `https://www.microsoft.com/edge` のスクリーンショットを保存します。</span><span class="sxs-lookup"><span data-stu-id="ebf96-134">Playwright launches Microsoft Edge, navigates to `https://www.microsoft.com/edge`, and saves a screenshot of the page.</span></span>  <span data-ttu-id="ebf96-135">[page.setViewportSize() を使用してページ サイズをカスタマイズできます][PlaywrightAPIPageSetViewport]。</span><span class="sxs-lookup"><span data-stu-id="ebf96-135">You may customize the page size with [page.setViewportSize()][PlaywrightAPIPageSetViewport].</span></span>  

:::image type="complex" source="../media/playwright-example.png" alt-text="このexample.pngによって生成されたファイルexample.js" lightbox="../media/playwright-example.png":::
    <span data-ttu-id="ebf96-137">生成 `example.png` されたファイル</span><span class="sxs-lookup"><span data-stu-id="ebf96-137">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

`example.js` <span data-ttu-id="ebf96-138">は、Playwright によって実現される自動化およびテスト シナリオの簡単なデモンストレーションです。</span><span class="sxs-lookup"><span data-stu-id="ebf96-138">is just a simple demonstration of the automation and testing scenarios enabled by Playwright.</span></span>  <span data-ttu-id="ebf96-139">複数の Web ブラウザーでスクリーンショットを撮る場合は、次のコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="ebf96-139">To take screenshots in multiple web browsers, change the following code.</span></span>  

*   <span data-ttu-id="ebf96-140">Chromium</span><span class="sxs-lookup"><span data-stu-id="ebf96-140">Chromium</span></span>  `await chromium.launch()`  
*   <span data-ttu-id="ebf96-141">Firefox</span><span class="sxs-lookup"><span data-stu-id="ebf96-141">Firefox</span></span>  `await firefox.launch()`  
*   <span data-ttu-id="ebf96-142">WebKit</span><span class="sxs-lookup"><span data-stu-id="ebf96-142">WebKit</span></span>  `await webkit.launch()`  

<span data-ttu-id="ebf96-143">Playwright の詳細については、Playwright [Web サイトに移動してください][|::ref6::|Main]。</span><span class="sxs-lookup"><span data-stu-id="ebf96-143">For more information about Playwright, navigate to the [Playwright website][|::ref6::|Main].</span></span>  <span data-ttu-id="ebf96-144">GitHub  [で Playwright リポジトリ][PlaywrightRepo] を確認します。</span><span class="sxs-lookup"><span data-stu-id="ebf96-144">Check out the  [Playwright repo][PlaywrightRepo] on GitHub.</span></span>  <span data-ttu-id="ebf96-145">Playwright で Web サイトまたはアプリの自動化とテストに関するフィードバックを共有するには、問題 [を解決してください][PlaywrightRepoNewIssue]。</span><span class="sxs-lookup"><span data-stu-id="ebf96-145">To share your feedback on automating and testing your website or app with Playwright, [file an issue][PlaywrightRepoNewIssue].</span></span>  

## <span data-ttu-id="ebf96-146">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="ebf96-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<!-- links -->  

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft Docs"  
[PuppeteerMain]: ../puppeteer/index.md "サーティファー |Microsoft Docs"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge: オープン ソースコラボレーションによる Web の向上 |Microsoft Experience ブログ"  

[MicrosoftEdgeDownload]: https://microsoft.com/edge "Microsoft Edge のダウンロード"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium プロジェクト"  

[FirefoxMain]: https://www.mozilla.org/firefox "Mozilla Firefox"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "edge-paths |npm"  

[PlaywrightMain]: https://playwright.dev "Playwright"  
[PlaywrightAPIReference]: https://playwright.dev#?path=docs/api.md "Playwright API リファレンス"  
[PlaywrightAPIPageSetViewport]: https://playwright.dev#?path=docs%2Fapi.md&q=pagesetviewportsizeviewportsize "page.setViewportSize(viewportSize) |Playwright API リファレンス"    
[PlaywrightSystemRequirements]: https://playwright.dev#?path=docs/intro.md&q=system-requirements "プレイライト システムの要件"  

[PlaywrightRepo]: https://github.com/microsoft/playwright "Playwright |GitHub"  
[PlaywrightRepoNewIssue]: https://github.com/microsoft/playwright/issues/new/choose "Playwright repo の新しい問題 |GitHub"  

[WebKitMain]: https://webkit.org "WebKit"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
