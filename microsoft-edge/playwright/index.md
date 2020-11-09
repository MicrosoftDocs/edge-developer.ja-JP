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
# Playwright  

[Playwright][|::ref1::|Main]は、 [Chromium][ChromiumHome]、 [Firefox][FirefoxMain]、 [WebKit][|::ref2::|Main]を1つの API で自動化するための[Node.js][NodejsMain]ライブラリです。  Playwright は、緑色、機能、信頼性、および高速のクロスブラウザー web オートメーションを可能にするために構築されています。  [Microsoft edge は、オープンソースの Chromium web プラットフォーム上に構築されて][MicrosoftBlogsWindowsExperience20181206]いるため、Playwright は microsoft edge を自動化することもできます。  

Playwright 既定では、 [ヘッドレスブラウザー][WikiHeadlessBrowser] が起動します。  ヘッドレスブラウザーでは UI が表示されないため、代わりにコマンドラインを使用する必要があります。  また、Microsoft Edge で完全 \ (非ヘッドレス) を実行するように Playwright を構成することもできます。  

既定では、Playwright をインストールすると、インストーラーが [Chromium][ChromiumHome]、 [Firefox][FirefoxMain]、および [WebKit][|::ref3::|Main]をダウンロードします。  Microsoft Edge \ (Chromium \) もインストールされている場合、Playwright は、Microsoft Edge で web サイトまたはアプリをテストするために1行のコード変更が必要になるだけです。  Microsoft Edge \ (Chromium) をダウンロードするには、「 [Microsoft edge のダウンロード][MicrosoftEdgeDownload]」に移動します。  

## Playwright のインストール  

次のコマンドを使用して、web サイトまたはアプリをテストするために [Playwright][|::ref4::|Main] をインストールします。  

```shell
npm i playwright
```  

## Playwright で Microsoft Edge を起動する  

> [!NOTE]
> [Playwright][|::ref5::|Main] には Node.js バージョン10.17 以降が必要です。 `node -v`コマンドラインから実行し、互換性のあるバージョンの Node.js があることを確認します。  Chromium、Firefox、および WebKit のブラウザーバイナリは、Windows、macOS、Linux で動作します。 詳細については、「 [Playwright のシステム要件][PlaywrightSystemRequirements]」を参照してください。  

Playwright は、 [Webdriver][WebDriverChromiumMain] や [Puppeteer][PuppeteerMain]など、他のブラウザーテストフレームワークのユーザーに馴染みのあるものにする必要があります。  ブラウザーのインスタンスを作成し、ページを開き、 [Playwright API][PlaywrightAPIReference]で操作します。  次のコードスニペットでは、Playwright が Microsoft Edge \ (Chromium \) を起動し、に移動し `https://www.microsoft.com/edge` て、スクリーンショットをとして保存して `example.png` います。  

次のコードスニペットをコピーして、として保存し `example.js` ます。  

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

`executablePath`Microsoft Edge \ (Chromium \) のインストールをポイントします。  たとえば、macOS では、 `executablePath` Microsoft Edge カナリアをに設定する必要があり `/Applications/Microsoft\ Edge\ Canary.app/` ます。  を見つけるに `executablePath` `edge://version` は、そのページの **実行可能ファイルのパス** に移動してコピーするか、次のコマンドを使用して [エッジパス][npmEdgePaths] パッケージをインストールします。  

```shell
npm i edge-paths
```  

次のコードスニペットでは、 [edge パス][npmEdgePaths] パッケージを使って、OS の Microsoft edge \ (Chromium \) のインストールへのパスをプログラムで検索しています。  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

最後に、を設定 `executablePath: EDGE_PATH` `example.js` します。  変更内容を保存するには、[保存] をクリックします。  

> [!NOTE]
> Microsoft Edge \ (EdgeHTML \) は、Playwright では動作しません。  この例に従って続行するには、 [Microsoft Edge \ (Chromium \)][MicrosoftEdgeDownload] をインストールする必要があります。  

次 `example.js` に、コマンドラインから実行します。  

```shell
node example.js
```  

Playwright Microsoft Edge を起動し、 `https://www.microsoft.com/edge` ページに移動して、ページのスクリーンショットを保存します。  ページサイズをカスタマイズするには、 [setViewportSize ()][PlaywrightAPIPageSetViewport]を使用します。  

:::image type="complex" source="../media/playwright-example.png" alt-text="example.js によって生成された example.png ファイル" lightbox="../media/playwright-example.png":::
    生成される `example.png` ファイル `example.js`  
:::image-end:::  

`example.js` ここでは、Playwright によって有効になるオートメーションとテストのシナリオを簡単にデモンストレーションします。  複数の web ブラウザーでスクリーンショットを撮るには、次のコードを変更します。  

*   Chromium  `await chromium.launch()`  
*   Firefox  `await firefox.launch()`  
*   WebKit  `await webkit.launch()`  

Playwright の詳細については、 [Playwright の web サイト][|::ref6::|Main]を参照してください。  GitHub の  [Playwright リポジトリ][PlaywrightRepo] をご覧ください。  プレイライトを使って web サイトまたはアプリの自動化とテストを行ってフィードバックを共有するには、 [問題をファイル][PlaywrightRepoNewIssue]します。  

## Microsoft Edge DevTools チームと連絡を取る  

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
