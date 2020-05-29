---
title: ソースパネルの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c61d1bda030ce729b0b217b95a9143508d1f51f8
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601909"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License. -->






# ソースパネルの概要 



Microsoft Edge DevTools**ソース**パネルを使用して、次の操作を行います。

*   [ファイルを表示](#view-files)します。  
*   [CSS と JavaScript を編集](#edit-css-and-javascript)します。  
*   [JavaScript の**スニペット**を作成して保存](#create-save-and-run-snippets)します。これは、どのページでも実行できます。  **スニペット**は bookmarklets に似ています。  
*   [JavaScript をデバッグ](#debug-javascript)します。  
*   [ワークスペースをセットアップ](#set-up-a-workspace)して、devtools で行った変更がファイルシステムのコードに保存されるようにします。  

## ファイルの表示 

**ページ**ウィンドウを使用して、ページに読み込まれたすべてのリソースを表示します。

> ##### 図 1  
> **ページ**ウィンドウ  
> ![図 1: ページウィンドウ][ImageSourcesPagePane]  

**ページ**ウィンドウの構成:  
*   図1のような最上位レベルは、 `top` [HTML フレーム][W3CHtml4Frames]を[**Figure 1**](#figure-1)表します。  `top`アクセスしたすべてのページで [検索] を選びます。 `top` メイン文書のフレームを表します。  
*   第2レベルは、 `docs.microsoft.com` [**図 1**](#figure-1)のように、[原点][HtmlstandardOrigin]を表します。  
*   第3レベルの第4レベルは、その起点から読み込まれたディレクトリとリソースを表します。  たとえば、[**図 1**](#figure-1)では、次のようにリソースの完全なパス `devtools-guide-chromium` があります。 `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  

**ページ**ウィンドウでファイルをクリックして、[**エディター** ] ウィンドウでコンテンツを表示します。  任意の種類のファイルを表示できます。 画像の場合、画像のプレビューが表示されます。  

> ##### 図 2  
> [ `a4d10f71.index-docs.js` **エディター** ] ウィンドウでのコンテンツの表示  
> ![図 2.  A4d10f71 の内容をエディターウィンドウで表示する][ImageSourcesEditorPane]  

## CSS と JavaScript を編集する 

[**エディター** ] ウィンドウを使って、CSS と JavaScript を編集します。  DevTools はページを更新して、新しいコードを実行します。 たとえば、次のようなスタイルルールを追加して CSS ファイルを編集するとします。

```css
.metadata.page-metadata {
    color: red;
}
```

変更がすぐに反映されることがわかります。

> ##### 図 3  
> [**エディター** ] ウィンドウで CSS を編集して、字幕のテキストの色を赤に変更する  
> ![図 3.  [エディター] ウィンドウで CSS を編集して、字幕のテキストの色を赤に変更する][ImageEditCSS]  

CSS の変更は直ちに有効になります。保存する必要はありません。 JavaScript の変更を有効にするに `Control` + `S` は、\ (Windows \) または `Command` + `S` \ (macOS \) を押します。 DevTools ではスクリプトは再実行されないため、関数内で行うことができるのは JavaScript の変更のみです。  たとえば、[**図 4**](#figure-4)では、次のように動作しないことを確認し `console.log('A')` `console.log('B')` ます。 DevTools で変更を行った後でスクリプト全体を再実行すると、テキストは `A` **本体**に記録されます。  

> ##### 図 4  
> [**エディター** ] ウィンドウでの JavaScript の編集  
> ![図 4:  [エディター] ウィンドウでの JavaScript の編集][ImageEditJS]  

DevTools は、ページの読み込み時に CSS と JavaScript の変更を消去します。 ファイルシステムへの変更を保存する方法については、「[ワークスペースを設定](#set-up-a-workspace)する」を参照してください。  

## スニペットの作成、保存、および実行 

スニペットは、任意のページで実行できるスクリプトです。 JQuery ライブラリをページに挿入するために、**コンソール**に次のコードを繰り返し入力して、**コンソール**から jquery コマンドを実行できるようにするとします。  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

代わりに、このコードを**スニペット**として保存し、ボタンをクリックするだけで、必要に応じて実行することができます。  DevTools は、**スニペット**をファイルシステムに保存します。  

> ##### 図 5  
> JQuery ライブラリをページに挿入する**スニペット**  
> ![図 5:  JQuery ライブラリをページに挿入するスニペット][ImageSnippet]  

**スニペット**を実行するには、次の操作を行います。

*   [**スニペット**] ウィンドウでファイルを開き **、[** ![ 実行] ボタンをクリックし ][ImageRunIcon] ます。  
*   **[コマンドメニュー][DevtoolsGuideChromiumCommandMenuIndex]** を開き、文字を削除して、スニペットの名前を入力し、 `>` `!` enter キーを押し**Snippet** `Enter` ます。  

詳細については[、「任意のページからコードのスニペットを実行][DevtoolsGuideChromiumJavascriptSnippets]する」を参照してください。


## デバッグ JavaScript 

JavaScript を使って問題が発生した場所を推測するのではなく `console.log()` 、Microsoft Edge devtools デバッグツールの使用を検討してください。 一般的な考え方として、ブレークポイントを設定します。これは、コードの中で意図的に停止しています。その後、コードの実行時に1行ずつ手順を実行します。 コードをステップ実行するときに、現在定義されているすべてのプロパティと変数の値の表示と変更、**コンソール**での JavaScript の実行などを行うことができます。

「[デバッグ JavaScript の概要][DevtoolsGuideChromiumJavascriptIndex]」を参照して、devtools でのデバッグの基礎を学習してください。

> ##### 図 6  
> JavaScript のデバッグ  
> ![図 6.  JavaScript のデバッグ][ImageDebugging]  

## ワークスペースを設定する 

既定では、[**ソース**] パネルでファイルを編集すると、ページを読み込むときにその変更が失われます。  **ワークスペース**を使用すると、devtools で行った変更をファイルシステムに保存することができます。  これにより、基本的に、コードエディターとして DevTools を使うことができます。

始めるには、「[ワークスペースでファイルを編集][DevtoolsGuideChromiumWorkspacesIndex]する」を参照してください。

 



<!-- image links -->  

[ImageRunIcon]: /microsoft-edge/devtools-guide-chromium/media/run-snippet-icon.msft.png  

[ImageSourcesPagePane]: /microsoft-edge/devtools-guide-chromium/media/sources-page-pane.msft.png "図 1: ページウィンドウ"  
[ImageSourcesEditorPane]: /microsoft-edge/devtools-guide-chromium/media/sources-editor-pane.msft.png "図 2: a4d10f71 の内容をエディターウィンドウで表示する"  
[ImageEditCSS]: /microsoft-edge/devtools-guide-chromium/media/edit-css.msft.png "図 3: [エディター] ウィンドウで CSS を編集して、字幕のテキストの色を赤に変更する"  
[ImageEditJS]: /microsoft-edge/devtools-guide-chromium/media/edit-js.msft.png "図 4: [エディター] ウィンドウで JavaScript を編集する"  
[ImageSnippet]: /microsoft-edge/devtools-guide-chromium/media/snippet.msft.png "図 5: jQuery ライブラリをページに挿入するスニペット"  
[ImageDebugging]: /microsoft-edge/devtools-guide-chromium/media/debugging.msft.png "図 6: JavaScript のデバッグ"  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevtoolsGuideChromiumJavascriptIndex]: /microsoft-edge/devtools-guide-chromium/javascript/index "Microsoft Edge DevTools のデバッグ JavaScript の概要"  
[DevtoolsGuideChromiumJavascriptSnippets]: /microsoft-edge/devtools-guide-chromium/javascript/snippets "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。"  
[DevtoolsGuideChromiumWorkspacesIndex]: /microsoft-edge/devtools-guide-chromium/workspaces/index "ワークスペースを使用してファイルを編集する"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "オリジン-HTML 標準"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "フレーム |勧告"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/sources)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
