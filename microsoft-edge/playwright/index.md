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
# Playwright  

[Playwright][|::ref1::|Main]は[、Node.js][NodejsMain] API を使用して Chromium、Firefox、WebKit を自動化するための新しいライブラリです。 [][ChromiumHome] [][FirefoxMain] [][|::ref2::|Main]  Playwright は、常に緑化され、機能し、信頼性が高く、高速なクロスブラウザー Web オートメーションを実現するために構築されています。  [Microsoft Edge はオープン ソースの Chromium Web][MicrosoftBlogsWindowsExperience20181206]プラットフォームに基づいているので、Playwright は Microsoft Edge を自動化することも可能です。  

Playwright は、既定 [でヘッドレス ブラウザーを][WikiHeadlessBrowser] 起動します。  ヘッドレス ブラウザーでは UI が表示されないので、代わりにコマンド ラインを使用する必要があります。  また、Microsoft Edge を完全 \(ヘッドレス\) で実行する Playwright を構成することもできます。  

既定では、Playwright をインストールすると、インストーラーは[Chromium、Firefox、][ChromiumHome][および WebKit をダウンロードします][|::ref3::|Main]。 [][FirefoxMain]  Microsoft Edge \(Chromium\) もインストールされている場合、Playwright は、Microsoft Edge で Web サイトまたはアプリをテストするために 1 行のコード変更が必要です。  Microsoft Edge \(Chromium\) をダウンロードするには [、Microsoft Edge のダウンロードに移動します][MicrosoftEdgeDownload]。  

## Playwright のインストール  

[Playwright をインストールし][|::ref4::|Main]、次のコマンドを使用して Web サイトまたはアプリをテストします。  

```shell
npm i playwright
```  

## Playwright で Microsoft Edge を起動する  

> [!NOTE]
> [Playwright では、Node.js][|::ref5::|Main] バージョン 10.17 以上が必要です。 コマンド `node -v` ラインから実行して、互換性のあるバージョンの Node.js。  Chromium、Firefox、WebKit のブラウザー バイナリは、Windows、macOS、Linux で動作します。 詳細については [、「Playwright System Requirements」に移動してください][PlaywrightSystemRequirements]。  

Playwright は [、WebDriver][WebDriverChromiumMain] や Browsereer などの他のブラウザー テスト フレームワークのユーザーをよく理解 [している必要があります][PuppeteerMain]。  ブラウザーのインスタンスを作成し、ページを開き [、Playwright API を使用して操作します][PlaywrightAPIReference]。  次のコード スニペットでは、Playwright は Microsoft Edge \(Chromium\) を起動し、スクリーンショットに移動して保存 `https://www.microsoft.com/edge` します `example.png` 。  

次のコード スニペットをコピーし、名前を付けて保存します `example.js` 。  

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

`executablePath`Microsoft Edge \(Chromium\) のインストールをポイントするために変更します。  たとえば、macOS では `executablePath` 、Microsoft Edge Canary の設定が必要です `/Applications/Microsoft\ Edge\ Canary.app/` 。  To find the `executablePath` , navigate to and copy the Executable `edge://version` **path** on that page or install the [edge-paths][npmEdgePaths] package with the following command.  

```shell
npm i edge-paths
```  

次のコード スニペットでは、 [エッジ パス][npmEdgePaths] パッケージを使用して、OS 上の Microsoft Edge \(Chromium\) のインストールへのパスをプログラムによって検索します。  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

最後に、設定 `executablePath: EDGE_PATH` します `example.js` 。  変更内容を保存するには、[保存] をクリックします。  

> [!NOTE]
> Microsoft Edge \(EdgeHTML\) は、Playwright では動作しません。  この例を引 [き続き実行するには、Microsoft Edge \(Chromium\)][MicrosoftEdgeDownload] をインストールする必要があります。  

コマンド ライン `example.js` から実行します。  

```shell
node example.js
```  

Playwright は Microsoft Edge を起動し、ページに移動して、ページ `https://www.microsoft.com/edge` のスクリーンショットを保存します。  [page.setViewportSize() を使用してページ サイズをカスタマイズできます][PlaywrightAPIPageSetViewport]。  

:::image type="complex" source="../media/playwright-example.png" alt-text="このexample.pngによって生成されたファイルexample.js" lightbox="../media/playwright-example.png":::
    生成 `example.png` されたファイル `example.js`  
:::image-end:::  

`example.js` は、Playwright によって実現される自動化およびテスト シナリオの簡単なデモンストレーションです。  複数の Web ブラウザーでスクリーンショットを撮る場合は、次のコードを変更します。  

*   Chromium  `await chromium.launch()`  
*   Firefox  `await firefox.launch()`  
*   WebKit  `await webkit.launch()`  

Playwright の詳細については、Playwright [Web サイトに移動してください][|::ref6::|Main]。  GitHub  [で Playwright リポジトリ][PlaywrightRepo] を確認します。  Playwright で Web サイトまたはアプリの自動化とテストに関するフィードバックを共有するには、問題 [を解決してください][PlaywrightRepoNewIssue]。  

## Microsoft Edge DevTools チームと連絡を取る  

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
