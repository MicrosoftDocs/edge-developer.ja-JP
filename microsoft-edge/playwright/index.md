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
# Playwright  

[Playwright][|::ref1::|Main]は[、Node.js][NodejsMain] API [][ChromiumHome] [Chromium、Firefox、][FirefoxMain][および WebKit][|::ref2::|Main]を自動化するためのツール ライブラリです。  Playwright は、常にグリーンで、信頼性が高く、高速なブラウザー間の Web オートメーションを可能にするために構築されています。  このMicrosoft Edge Web プラットフォーム上に構築[Chromium、Playwright][MicrosoftBlogsWindowsExperience20181206]はアプリケーションを自動化Microsoft Edge。  

Playwright は、既定 [でヘッドレス ブラウザーを][WikiHeadlessBrowser] 起動します。  ヘッドレス ブラウザーは UI を表示しないので、代わりにコマンド ラインを使用する必要があります。  また、完全な \(non-headless\) を実行する Playwright を構成Microsoft Edgeすることもできます。  

既定では、Playwright をインストールすると、インストーラーは[][ChromiumHome]Chromium [Firefox、][FirefoxMain][および WebKit をダウンロードします][|::ref3::|Main]。  Microsoft Edge \(Chromium\) もインストールされている場合、Playwright は web サイトまたはアプリをテストするために 1 行のコード変更が必要Microsoft Edge。  \(Microsoft Edge\Chromium) をダウンロードするには、[ダウンロード] Microsoft Edge に[移動します][MicrosoftEdgeDownload]。  

## Playwright のインストール  

[Playwright をインストールして][|::ref4::|Main]、次のコマンドを使用して Web サイトまたはアプリをテストします。  

```shell
npm i playwright
```  

## Playwright Microsoft Edgeを起動する  

> [!NOTE]
> [Playwright には][|::ref5::|Main] 、Node.jsバージョン 10.17 以上が必要です。 コマンド `node -v` ラインから実行して、互換性のあるバージョンのファイルを使用Node.js。  WebKit、Firefox、WebKit Chromiumのブラウザー バイナリは、Windows macOS、Linux 全体で動作します。 詳細については [、「Playwright System Requirements」に移動します][PlaywrightSystemRequirements]。  

Playwright は [、WebDriver][WebDriverChromiumMain] や Puppeteer などの他のブラウザー テスト フレームワークのユーザーに精通 [している必要があります][PuppeteerMain]。  ブラウザーのインスタンスを作成し、ページを開き [、Playwright API][PlaywrightAPIReference]で操作します。  次のコード スニペットでは、Playwright は \(Chromium\) のMicrosoft Edgeを起動し、に移動し、スクリーンショットを `https://www.microsoft.com/edge` として保存します `example.png` 。  

次のコード スニペットをコピーし、として保存します `example.js` 。  

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

`executablePath`\(Chromium\) のインストールをポイントMicrosoft Edge変更します。  たとえば、macOS では `executablePath` 、Canary の for Microsoft Edgeに設定する必要があります `/Applications/Microsoft\ Edge\ Canary.app/` 。  を見つけるには、そのページの実行可能パスに移動してコピーするか、次のコマンドを使用してエッジ パス `executablePath` `edge://version` パッケージをインストールします。 **** [][npmEdgePaths]  

```shell
npm i edge-paths
```  

次のコード スニペットでは、[エッジ パス][npmEdgePaths]パッケージを使用して、OS 上の Microsoft Edge \(Chromium\) のインストールへのパスをプログラムで検索します。  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

最後に、 に `executablePath: EDGE_PATH` 設定 `example.js` します。  変更内容を保存するには、[保存] をクリックします。  

> [!NOTE]
> Microsoft Edge \(EdgeHTML\) は Playwright では動作しません。  この例に従[ってMicrosoft Edge \(Chromium\)][MicrosoftEdgeDownload]をインストールする必要があります。  

コマンド ライン `example.js` から実行します。  

```shell
node example.js
```  

Playwright は、Microsoft Edgeを起動し、ページに移動 `https://www.microsoft.com/edge` し、スクリーンショットを保存します。  [page.setViewportSize() を使用してページ サイズをカスタマイズできます][PlaywrightAPIPageSetViewport]。  

:::image type="complex" source="../media/playwright-example.png" alt-text="example.pngによって生成されたファイルexample.js" lightbox="../media/playwright-example.png":::
    によって `example.png` 生成されるファイル `example.js`  
:::image-end:::  

`example.js` は、Playwright が有効にしているオートメーションとテストのシナリオの簡単なデモンストレーションです。  複数の Web ブラウザーでスクリーンショットを撮る場合は、次のコードを変更します。  

*   Chromium  `await chromium.launch()`  
*   Firefox  `await firefox.launch()`  
*   WebKit  `await webkit.launch()`  

Playwright の詳細については [、Playwright Web サイトに移動します][|::ref6::|Main]。  詳細は[、「Playwright repo on the playwright repo」][PlaywrightRepo]をGitHub。  Playwright で Web サイトまたはアプリの自動化とテストに関するフィードバックを共有するには、 [問題をファイルします][PlaywrightRepoNewIssue]。  

## Microsoft Edge DevTools チームと連絡を取る  

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
