---
description: Playwright を使用して、アプリケーションの自動化とテストをMicrosoft Edge
title: Playwright
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/24/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, Web 開発, 開発者, ツール, オートメーション, test, playwright, node, javascript, npm
ms.openlocfilehash: 5ce51864177731dd1bafb845466abb00cce1e0aa
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231084"
---
# <span data-ttu-id="90eed-104">Playwright</span><span class="sxs-lookup"><span data-stu-id="90eed-104">Playwright</span></span>  

<span data-ttu-id="90eed-105">[Playwright][|::ref1::|Main]は[、Node.js][NodejsMain] API [][ChromiumHome] [Chromium、Firefox、][FirefoxMain][および WebKit][|::ref2::|Main]を自動化するためのツール ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="90eed-105">[Playwright][|::ref1::|Main] is a [Node.js][NodejsMain] library to automate [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref2::|Main] with a single API.</span></span>  <span data-ttu-id="90eed-106">Playwright は、常にグリーンで、信頼性が高く、高速なブラウザー間の Web オートメーションを可能にするために構築されています。</span><span class="sxs-lookup"><span data-stu-id="90eed-106">Playwright is built to enable cross-browser web automation that is ever-green, capable, reliable, and fast.</span></span>  <span data-ttu-id="90eed-107">このMicrosoft Edge Web プラットフォーム上に構築[Chromium、Playwright][MicrosoftBlogsWindowsExperience20181206]はアプリケーションを自動化Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="90eed-107">Since [Microsoft Edge is built on the open-source Chromium web platform][MicrosoftBlogsWindowsExperience20181206], Playwright is also able to automate Microsoft Edge.</span></span>  

<span data-ttu-id="90eed-108">Playwright は、既定 [でヘッドレス ブラウザーを][WikiHeadlessBrowser] 起動します。</span><span class="sxs-lookup"><span data-stu-id="90eed-108">Playwright launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="90eed-109">ヘッドレス ブラウザーは UI を表示しないので、代わりにコマンド ラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90eed-109">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="90eed-110">また、完全な \(non-headless\) を実行する Playwright を構成Microsoft Edgeすることもできます。</span><span class="sxs-lookup"><span data-stu-id="90eed-110">You may also configure Playwright to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="90eed-111">既定では、Playwright をインストールすると、インストーラーは[][ChromiumHome]Chromium [Firefox、][FirefoxMain][および WebKit をダウンロードします][|::ref3::|Main]。</span><span class="sxs-lookup"><span data-stu-id="90eed-111">By default, when you install Playwright, the installer downloads [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref3::|Main].</span></span>  <span data-ttu-id="90eed-112">Microsoft Edge \(Chromium\) もインストールされている場合、Playwright は web サイトまたはアプリをテストするために 1 行のコード変更が必要Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="90eed-112">If you have Microsoft Edge \(Chromium\) installed as well, Playwright just needs a one-line code change to test your website or app in Microsoft Edge.</span></span>  <span data-ttu-id="90eed-113">\(Microsoft Edge\Chromium) をダウンロードするには、[ダウンロード] Microsoft Edge に[移動します][MicrosoftEdgeDownload]。</span><span class="sxs-lookup"><span data-stu-id="90eed-113">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge][MicrosoftEdgeDownload].</span></span>  

## <span data-ttu-id="90eed-114">Playwright のインストール</span><span class="sxs-lookup"><span data-stu-id="90eed-114">Installing Playwright</span></span>  

<span data-ttu-id="90eed-115">[Playwright をインストールして][|::ref4::|Main]、次のコマンドを使用して Web サイトまたはアプリをテストします。</span><span class="sxs-lookup"><span data-stu-id="90eed-115">Install [Playwright][|::ref4::|Main] to test your website or app with the following command.</span></span>  

```shell
npm i playwright
```  

## <span data-ttu-id="90eed-116">Playwright Microsoft Edgeを起動する</span><span class="sxs-lookup"><span data-stu-id="90eed-116">Launch Microsoft Edge with Playwright</span></span>  

> [!NOTE]
> <span data-ttu-id="90eed-117">[Playwright には][|::ref5::|Main] 、Node.jsバージョン 10.17 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="90eed-117">[Playwright][|::ref5::|Main] requires Node.js version 10.17 or above.</span></span> <span data-ttu-id="90eed-118">コマンド `node -v` ラインから実行して、互換性のあるバージョンのファイルを使用Node.js。</span><span class="sxs-lookup"><span data-stu-id="90eed-118">Run `node -v` from the command line to ensure you have a compatible version of Node.js.</span></span>  <span data-ttu-id="90eed-119">WebKit、Firefox、WebKit Chromiumのブラウザー バイナリは、Windows macOS、Linux 全体で動作します。</span><span class="sxs-lookup"><span data-stu-id="90eed-119">The browser binaries for Chromium, Firefox and WebKit work across Windows, macOS, and Linux.</span></span> <span data-ttu-id="90eed-120">詳細については [、「Playwright System Requirements」に移動します][PlaywrightSystemRequirements]。</span><span class="sxs-lookup"><span data-stu-id="90eed-120">For more information, navigate to [Playwright System Requirements][PlaywrightSystemRequirements].</span></span>  

<span data-ttu-id="90eed-121">Playwright は [、WebDriver][WebDriverChromiumMain] や Puppeteer などの他のブラウザー テスト フレームワークのユーザーに精通 [している必要があります][PuppeteerMain]。</span><span class="sxs-lookup"><span data-stu-id="90eed-121">Playwright should be familiar to users of other browser-testing frameworks like [WebDriver][WebDriverChromiumMain] or [Puppeteer][PuppeteerMain].</span></span>  <span data-ttu-id="90eed-122">ブラウザーのインスタンスを作成し、ページを開き [、Playwright API][PlaywrightAPIReference]で操作します。</span><span class="sxs-lookup"><span data-stu-id="90eed-122">You create an instance of the browser, open a page, and then manipulate it with the [Playwright API][PlaywrightAPIReference].</span></span>  <span data-ttu-id="90eed-123">次のコード スニペットでは、Playwright は \(Chromium\) のMicrosoft Edgeを起動し、に移動し、スクリーンショットを `https://www.microsoft.com/edge` として保存します `example.png` 。</span><span class="sxs-lookup"><span data-stu-id="90eed-123">In the following code snippet, Playwright launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoft.com/edge`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="90eed-124">次のコード スニペットをコピーし、として保存します `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="90eed-124">Copy the following code snippet and save it as `example.js`.</span></span>  

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

<span data-ttu-id="90eed-125">`executablePath`\(Chromium\) のインストールをポイントMicrosoft Edge変更します。</span><span class="sxs-lookup"><span data-stu-id="90eed-125">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="90eed-126">たとえば、macOS では `executablePath` 、Canary の for Microsoft Edgeに設定する必要があります `/Applications/Microsoft\ Edge\ Canary.app/` 。</span><span class="sxs-lookup"><span data-stu-id="90eed-126">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="90eed-127">を見つけるには、そのページの実行可能パスに移動してコピーするか、次のコマンドを使用してエッジ パス `executablePath` `edge://version` パッケージをインストールします。 \*\*\*\* [][npmEdgePaths]</span><span class="sxs-lookup"><span data-stu-id="90eed-127">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with the following command.</span></span>  

```shell
npm i edge-paths
```  

<span data-ttu-id="90eed-128">次のコード スニペットでは、[エッジ パス][npmEdgePaths]パッケージを使用して、OS 上の Microsoft Edge \(Chromium\) のインストールへのパスをプログラムで検索します。</span><span class="sxs-lookup"><span data-stu-id="90eed-128">The following code snippet uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

<span data-ttu-id="90eed-129">最後に、 に `executablePath: EDGE_PATH` 設定 `example.js` します。</span><span class="sxs-lookup"><span data-stu-id="90eed-129">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="90eed-130">変更内容を保存するには、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90eed-130">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="90eed-131">Microsoft Edge \(EdgeHTML\) は Playwright では動作しません。</span><span class="sxs-lookup"><span data-stu-id="90eed-131">Microsoft Edge \(EdgeHTML\) does not work with Playwright.</span></span>  <span data-ttu-id="90eed-132">この例に従[ってMicrosoft Edge \(Chromium\)][MicrosoftEdgeDownload]をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90eed-132">You must install [Microsoft Edge \(Chromium\)][MicrosoftEdgeDownload] to continue following this example.</span></span>  

<span data-ttu-id="90eed-133">コマンド ライン `example.js` から実行します。</span><span class="sxs-lookup"><span data-stu-id="90eed-133">Now run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

<span data-ttu-id="90eed-134">Playwright は、Microsoft Edgeを起動し、ページに移動 `https://www.microsoft.com/edge` し、スクリーンショットを保存します。</span><span class="sxs-lookup"><span data-stu-id="90eed-134">Playwright launches Microsoft Edge, navigates to `https://www.microsoft.com/edge`, and saves a screenshot of the page.</span></span>  <span data-ttu-id="90eed-135">[page.setViewportSize() を使用してページ サイズをカスタマイズできます][PlaywrightAPIPageSetViewport]。</span><span class="sxs-lookup"><span data-stu-id="90eed-135">You may customize the page size with [page.setViewportSize()][PlaywrightAPIPageSetViewport].</span></span>  

:::image type="complex" source="../media/playwright-example.png" alt-text="example.pngによって生成されたファイルexample.js" lightbox="../media/playwright-example.png":::
    <span data-ttu-id="90eed-137">によって `example.png` 生成されるファイル</span><span class="sxs-lookup"><span data-stu-id="90eed-137">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

`example.js` <span data-ttu-id="90eed-138">は、Playwright が有効にしているオートメーションとテストのシナリオの簡単なデモンストレーションです。</span><span class="sxs-lookup"><span data-stu-id="90eed-138">is just a simple demonstration of the automation and testing scenarios enabled by Playwright.</span></span>  <span data-ttu-id="90eed-139">複数の Web ブラウザーでスクリーンショットを撮る場合は、次のコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="90eed-139">To take screenshots in multiple web browsers, change the following code.</span></span>  

*   <span data-ttu-id="90eed-140">Chromium</span><span class="sxs-lookup"><span data-stu-id="90eed-140">Chromium</span></span>  `await chromium.launch()`  
*   <span data-ttu-id="90eed-141">Firefox</span><span class="sxs-lookup"><span data-stu-id="90eed-141">Firefox</span></span>  `await firefox.launch()`  
*   <span data-ttu-id="90eed-142">WebKit</span><span class="sxs-lookup"><span data-stu-id="90eed-142">WebKit</span></span>  `await webkit.launch()`  

<span data-ttu-id="90eed-143">Playwright の詳細については [、Playwright Web サイトに移動します][|::ref6::|Main]。</span><span class="sxs-lookup"><span data-stu-id="90eed-143">For more information about Playwright, navigate to the [Playwright website][|::ref6::|Main].</span></span>  <span data-ttu-id="90eed-144">詳細は[、「Playwright repo on the playwright repo」][PlaywrightRepo]をGitHub。</span><span class="sxs-lookup"><span data-stu-id="90eed-144">Check out the  [Playwright repo][PlaywrightRepo] on GitHub.</span></span>  <span data-ttu-id="90eed-145">Playwright で Web サイトまたはアプリの自動化とテストに関するフィードバックを共有するには、 [問題をファイルします][PlaywrightRepoNewIssue]。</span><span class="sxs-lookup"><span data-stu-id="90eed-145">To share your feedback on automating and testing your website or app with Playwright, [file an issue][PlaywrightRepoNewIssue].</span></span>  

## <span data-ttu-id="90eed-146">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="90eed-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<!-- links -->  

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft Docs"  
[PuppeteerMain]: ../puppeteer/index.md "パペット|Microsoft Docs"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge: より多くのオープンソースのコラボレーション を通じて Web をより良く|Microsoft Experience Blog"  

[MicrosoftEdgeDownload]: https://microsoft.com/edge "ダウンロード Microsoft Edge"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |The Chromium プロジェクト"  

[FirefoxMain]: https://www.mozilla.org/firefox "Mozilla Firefox"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "edge-paths |npm"  

[PlaywrightMain]: https://playwright.dev "Playwright"  
[PlaywrightAPIReference]: https://playwright.dev#?path=docs/api.md "Playwright API リファレンス"  
[PlaywrightAPIPageSetViewport]: https://playwright.dev#?path=docs%2Fapi.md&q=pagesetviewportsizeviewportsize "page.setViewportSize(viewportSize) |Playwright API リファレンス"    
[PlaywrightSystemRequirements]: https://playwright.dev#?path=docs/intro.md&q=system-requirements "Playwright のシステム要件"  

[PlaywrightRepo]: https://github.com/microsoft/playwright "Playwright |GitHub"  
[PlaywrightRepoNewIssue]: https://github.com/microsoft/playwright/issues/new/choose "Playwright repo |GitHub"  

[WebKitMain]: https://webkit.org "WebKit"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
