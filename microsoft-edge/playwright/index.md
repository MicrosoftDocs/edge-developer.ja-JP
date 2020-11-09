---
description: Microsoft Edge で Playwright を使用して自動化およびテストを行う
title: Playwright
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/06/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、開発者、ツール、オートメーション、テスト、再生ライト、ノード、javascript、npm
ms.openlocfilehash: 419d534b3757609528f05bac50ce55bad9dafec4
ms.sourcegitcommit: 5af0ba56a93871eb4890d1aa7c56c3524c2261de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2020
ms.locfileid: "11160174"
---
# <span data-ttu-id="d78f9-104">Playwright</span><span class="sxs-lookup"><span data-stu-id="d78f9-104">Playwright</span></span>  

<span data-ttu-id="d78f9-105">[Playwright][|::ref1::|Main]は、 [Chromium][ChromiumHome]、 [Firefox][FirefoxMain]、 [WebKit][|::ref2::|Main]を1つの API で自動化するための[Node.js][NodejsMain]ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="d78f9-105">[Playwright][|::ref1::|Main] is a [Node.js][NodejsMain] library to automate [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref2::|Main] with a single API.</span></span>  <span data-ttu-id="d78f9-106">Playwright は、緑色、機能、信頼性、および高速のクロスブラウザー web オートメーションを可能にするために構築されています。</span><span class="sxs-lookup"><span data-stu-id="d78f9-106">Playwright is built to enable cross-browser web automation that is ever-green, capable, reliable, and fast.</span></span>  <span data-ttu-id="d78f9-107">[Microsoft edge は、オープンソースの Chromium web プラットフォーム上に構築されて][MicrosoftBlogsWindowsExperience20181206]いるため、Playwright は microsoft edge を自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="d78f9-107">Since [Microsoft Edge is built on the open-source Chromium web platform][MicrosoftBlogsWindowsExperience20181206], Playwright is also able to automate Microsoft Edge.</span></span>  

<span data-ttu-id="d78f9-108">Playwright 既定では、 [ヘッドレスブラウザー][WikiHeadlessBrowser] が起動します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-108">Playwright launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="d78f9-109">ヘッドレスブラウザーでは UI が表示されないため、代わりにコマンドラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d78f9-109">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="d78f9-110">また、Microsoft Edge で完全 \ (非ヘッドレス) を実行するように Playwright を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d78f9-110">You may also configure Playwright to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="d78f9-111">既定では、Playwright をインストールすると、インストーラーが [Chromium][ChromiumHome]、 [Firefox][FirefoxMain]、および [WebKit][|::ref3::|Main]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d78f9-111">By default, when you install Playwright, the installer downloads [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref3::|Main].</span></span>  <span data-ttu-id="d78f9-112">Microsoft Edge \ (Chromium \) もインストールされている場合、Playwright は、Microsoft Edge で web サイトまたはアプリをテストするために1行のコード変更が必要になるだけです。</span><span class="sxs-lookup"><span data-stu-id="d78f9-112">If you have Microsoft Edge \(Chromium\) installed as well, Playwright just needs a one-line code change to test your website or app in Microsoft Edge.</span></span>  <span data-ttu-id="d78f9-113">Microsoft Edge \ (Chromium) をダウンロードするには、「 [Microsoft edge のダウンロード][MicrosoftEdgeDownload]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-113">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge][MicrosoftEdgeDownload].</span></span>  

## <span data-ttu-id="d78f9-114">Playwright のインストール</span><span class="sxs-lookup"><span data-stu-id="d78f9-114">Installing Playwright</span></span>  

<span data-ttu-id="d78f9-115">次のコマンドを使用して、web サイトまたはアプリをテストするために [Playwright][|::ref4::|Main] をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d78f9-115">Install [Playwright][|::ref4::|Main] to test your website or app with the following command.</span></span>  

```shell
npm i playwright
```  

## <span data-ttu-id="d78f9-116">Playwright で Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="d78f9-116">Launch Microsoft Edge with Playwright</span></span>  

> [!NOTE]
> <span data-ttu-id="d78f9-117">[Playwright][|::ref5::|Main] には Node.js バージョン10.17 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="d78f9-117">[Playwright][|::ref5::|Main] requires Node.js version 10.17 or above.</span></span> <span data-ttu-id="d78f9-118">`node -v`コマンドラインから実行し、互換性のあるバージョンの Node.js があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-118">Run `node -v` from the command line to ensure you have a compatible version of Node.js.</span></span>  <span data-ttu-id="d78f9-119">Chromium、Firefox、および WebKit のブラウザーバイナリは、Windows、macOS、Linux で動作します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-119">The browser binaries for Chromium, Firefox and WebKit work across Windows, macOS, and Linux.</span></span> <span data-ttu-id="d78f9-120">詳細については、「 [Playwright のシステム要件][PlaywrightSystemRequirements]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d78f9-120">For more information, navigate to [Playwright System Requirements][PlaywrightSystemRequirements].</span></span>  

<span data-ttu-id="d78f9-121">Playwright は、 [Webdriver][WebDriverChromiumMain] や [Puppeteer][PuppeteerMain]など、他のブラウザーテストフレームワークのユーザーに馴染みのあるものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d78f9-121">Playwright should be familiar to users of other browser-testing frameworks like [WebDriver][WebDriverChromiumMain] or [Puppeteer][PuppeteerMain].</span></span>  <span data-ttu-id="d78f9-122">ブラウザーのインスタンスを作成し、ページを開き、 [Playwright API][PlaywrightAPIReference]で操作します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-122">You create an instance of the browser, open a page, and then manipulate it with the [Playwright API][PlaywrightAPIReference].</span></span>  <span data-ttu-id="d78f9-123">次のコードスニペットでは、Playwright が Microsoft Edge \ (Chromium \) を起動し、に移動し `https://www.microsoft.com/edge` て、スクリーンショットをとして保存して `example.png` います。</span><span class="sxs-lookup"><span data-stu-id="d78f9-123">In the following code snippet, Playwright launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoft.com/edge`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="d78f9-124">次のコードスニペットをコピーして、として保存し `example.js` ます。</span><span class="sxs-lookup"><span data-stu-id="d78f9-124">Copy the following code snippet and save it as `example.js`.</span></span>  

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

<span data-ttu-id="d78f9-125">`executablePath`Microsoft Edge \ (Chromium \) のインストールをポイントします。</span><span class="sxs-lookup"><span data-stu-id="d78f9-125">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="d78f9-126">たとえば、macOS では、 `executablePath` Microsoft Edge カナリアをに設定する必要があり `/Applications/Microsoft\ Edge\ Canary.app/` ます。</span><span class="sxs-lookup"><span data-stu-id="d78f9-126">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="d78f9-127">を見つけるに `executablePath` `edge://version` は、そのページの **実行可能ファイルのパス** に移動してコピーするか、次のコマンドを使用して [エッジパス][npmEdgePaths] パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d78f9-127">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with the following command.</span></span>  

```shell
npm i edge-paths
```  

<span data-ttu-id="d78f9-128">次のコードスニペットでは、 [edge パス][npmEdgePaths] パッケージを使って、OS の Microsoft edge \ (Chromium \) のインストールへのパスをプログラムで検索しています。</span><span class="sxs-lookup"><span data-stu-id="d78f9-128">The following code snippet uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

<span data-ttu-id="d78f9-129">最後に、を設定 `executablePath: EDGE_PATH` `example.js` します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-129">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="d78f9-130">変更内容を保存するには、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d78f9-130">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="d78f9-131">Microsoft Edge \ (EdgeHTML \) は、Playwright では動作しません。</span><span class="sxs-lookup"><span data-stu-id="d78f9-131">Microsoft Edge \(EdgeHTML\) does not work with Playwright.</span></span>  <span data-ttu-id="d78f9-132">この例に従って続行するには、 [Microsoft Edge \ (Chromium \)][MicrosoftEdgeDownload] をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d78f9-132">You must install [Microsoft Edge \(Chromium\)][MicrosoftEdgeDownload] to continue following this example.</span></span>  

<span data-ttu-id="d78f9-133">次 `example.js` に、コマンドラインから実行します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-133">Now run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

<span data-ttu-id="d78f9-134">Playwright Microsoft Edge を起動し、 `https://www.microsoft.com/edge` ページに移動して、ページのスクリーンショットを保存します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-134">Playwright launches Microsoft Edge, navigates to `https://www.microsoft.com/edge`, and saves a screenshot of the page.</span></span>  <span data-ttu-id="d78f9-135">ページサイズをカスタマイズするには、 [setViewportSize ()][PlaywrightAPIPageSetViewport]を使用します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-135">You may customize the page size with [page.setViewportSize()][PlaywrightAPIPageSetViewport].</span></span>  

:::image type="complex" source="../media/playwright-example.png" alt-text="example.js によって生成された example.png ファイル" lightbox="../media/playwright-example.png":::
    <span data-ttu-id="d78f9-137">生成される `example.png` ファイル</span><span class="sxs-lookup"><span data-stu-id="d78f9-137">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

`example.js` <span data-ttu-id="d78f9-138">ここでは、Playwright によって有効になるオートメーションとテストのシナリオを簡単にデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="d78f9-138">is just a simple demonstration of the automation and testing scenarios enabled by Playwright.</span></span>  <span data-ttu-id="d78f9-139">複数の web ブラウザーでスクリーンショットを撮るには、次のコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-139">To take screenshots in multiple web browsers, change the following code.</span></span>  

*   <span data-ttu-id="d78f9-140">Chromium</span><span class="sxs-lookup"><span data-stu-id="d78f9-140">Chromium</span></span>  `await chromium.launch()`  
*   <span data-ttu-id="d78f9-141">Firefox</span><span class="sxs-lookup"><span data-stu-id="d78f9-141">Firefox</span></span>  `await firefox.launch()`  
*   <span data-ttu-id="d78f9-142">WebKit</span><span class="sxs-lookup"><span data-stu-id="d78f9-142">WebKit</span></span>  `await webkit.launch()`  

<span data-ttu-id="d78f9-143">Playwright の詳細については、 [Playwright の web サイト][|::ref6::|Main]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d78f9-143">For more information about Playwright, navigate to the [Playwright website][|::ref6::|Main].</span></span>  <span data-ttu-id="d78f9-144">GitHub の  [Playwright リポジトリ][PlaywrightRepo] をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d78f9-144">Check out the  [Playwright repo][PlaywrightRepo] on GitHub.</span></span>  <span data-ttu-id="d78f9-145">プレイライトを使って web サイトまたはアプリの自動化とテストを行ってフィードバックを共有するには、 [問題をファイル][PlaywrightRepoNewIssue]します。</span><span class="sxs-lookup"><span data-stu-id="d78f9-145">To share your feedback on automating and testing your website or app with Playwright, [file an issue][PlaywrightRepoNewIssue].</span></span>  

## <span data-ttu-id="d78f9-146">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="d78f9-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<!-- links -->  

[WebdriverChromiumMain]: ../webdriver-chromium.md "WebDriver (Chromium) |Microsoft ドキュメント"  
[PuppeteerMain]: ../puppeteer.md "Puppeteer |Microsoft ドキュメント"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge: さまざまなオープンソースの共同作業で web の品質を向上させる |Microsoft エクスペリエンスブログ"  

[MicrosoftEdgeDownload]: https://microsoft.com/edge "Microsoft Edge をダウンロードする"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium プロジェクト"  

[FirefoxMain]: https://www.mozilla.org/firefox "Mozilla Firefox"

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "edge-パス |npm"

[PlaywrightMain]: https://playwright.dev "Playwright"  
[PlaywrightAPIReference]: https://playwright.dev#?path=docs/api.md "Playwright API リファレンス"  
[PlaywrightAPIPageSetViewport]: https://playwright.dev#?path=docs%2Fapi.md&q=pagesetviewportsizeviewportsize "setViewportSize (viewportSize) |Playwright API リファレンス"    
[PlaywrightSystemRequirements]: https://playwright.dev#?path=docs/intro.md&q=system-requirements "Playwright システム要件"  

[PlaywrightRepo]: https://github.com/microsoft/playwright "Playwright |GitHub"  
[PlaywrightRepoNewIssue]: https://github.com/microsoft/playwright/issues/new/choose "Playwright リポジトリでの新しい問題 |GitHub"  

[WebKitMain]: https://webkit.org "WebKit"

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレスブラウザー |Wikipedia"  
