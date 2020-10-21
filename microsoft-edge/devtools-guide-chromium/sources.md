---
description: Microsoft Edge DevTools のソースパネルで、ファイルの表示と編集、スニペットの作成、JavaScript の作成、ワークスペースのセットアップを行います。
title: ソース パネルの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 971ee6e112daaba828a8b754b63eee73ea51e99e
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125329"
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
   limitations under the License.  -->

# ソース パネルの概要  

Microsoft Edge DevTools **ソース** パネルを使用して、次の操作を実行します。  

*   [ファイルを表示](#view-files)します。  
*   [CSS と JavaScript を編集](#edit-css-and-javascript)します。  
*   [JavaScript の **スニペット** を作成して保存](#create-save-and-run-snippets)します。これは、どのページでも実行できます。  **スニペット** は bookmarklets に似ています。  
*   [JavaScript をデバッグ](#debug-javascript)します。  
*   [ワークスペースをセットアップ](#set-up-a-workspace)して、devtools で行った変更がファイルシステムのコードに保存されるようにします。  
    
## ファイルの表示  

**ページ**ウィンドウを使用して、ページに読み込まれたすべてのリソースを表示します。

:::image type="complex" source="./media/sources-page-pane.msft.png" alt-text="ページウィンドウ" lightbox="./media/sources-page-pane.msft.png":::
   **ページ**ウィンドウ  
:::image-end:::  

**ページ**ウィンドウの構成:  
*   上の図のような最上位のレベルは、 `top` [HTML フレーム][W3CHtml4Frames]を表します。  `top`アクセスしたすべてのページで [検索] を選びます。  `top` メイン文書のフレームを表します。  
*   上の図のように、第2レベルは `docs.microsoft.com` [起点][HtmlstandardOrigin]を表します。  
*   第3レベルの第4レベルは、その起点から読み込まれたディレクトリとリソースを表します。  たとえば、前の図では、リソースへの完全なパス `devtools-guide-chromium` は `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  
    
**ページ**ウィンドウでファイルをクリックして、[**エディター** ] ウィンドウでコンテンツを表示します。  任意の種類のファイルを表示できます。  画像の場合、画像のプレビューが表示されます。  

:::image type="complex" source="./media/sources-editor-pane.msft.png" alt-text="ページウィンドウ" lightbox="./media/sources-editor-pane.msft.png":::
   [ `a4d10f71.index-docs.js` **エディター** ] ウィンドウでのコンテンツの表示  
:::image-end:::  

## CSS と JavaScript を編集する  

[ **エディター** ] ウィンドウを使って、CSS と JavaScript を編集します。  DevTools はページを更新して、新しいコードを実行します。  たとえば、次のようなスタイルルールを追加して CSS ファイルを編集するとします。

```css
.metadata.page-metadata {
    color: red;
}
```

この変更はすぐに有効になります。

:::image type="complex" source="./media/edit-css.msft.png" alt-text="ページウィンドウ" lightbox="./media/edit-css.msft.png":::
   [ **エディター** ] ウィンドウで [CSS の編集] を行うと、字幕のテキストの色が赤に変更されます。  
:::image-end:::  

CSS の変更は直ちに有効になります。保存する必要はありません。  JavaScript の変更を有効にするに `Control` + `S` は、\ (Windows、Linux \) または `Command` + `S` \ (macOS \) を選択します。  DevTools ではスクリプトは再実行されないため、関数内で行うことができるのは JavaScript の変更のみです。  たとえば、次の図では、"実行されない" という点に注意 `console.log('A')` `console.log('B')` してください。  DevTools を変更した後でスクリプト全体を再実行すると、テキストは `A` **本体**に記録されます。  

:::image type="complex" source="./media/edit-js.msft.png" alt-text="ページウィンドウ" lightbox="./media/edit-js.msft.png":::
   [ **エディター** ] ウィンドウでの JavaScript の編集  
:::image-end:::  

DevTools は、ページの読み込み時に CSS と JavaScript の変更を消去します。  ファイルシステムへの変更を保存する方法については、「 [ワークスペースを設定](#set-up-a-workspace) する」を参照してください。  

## スニペットの作成、保存、および実行  

スニペットは、任意のページで実行できるスクリプトです。  JQuery ライブラリをページに挿入するために、 **コンソール**に次のコードを繰り返し入力して、 **コンソール**から jquery コマンドを実行できるようにするとします。  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

代わりに、このコードを **スニペット** として保存し、ボタンをクリックするだけで、必要に応じて実行することができます。  DevTools は、 **スニペット** をファイルシステムに保存します。  

:::image type="complex" source="./media/snippet.msft.png" alt-text="ページウィンドウ" lightbox="./media/snippet.msft.png":::
   JQuery ライブラリをページに挿入する**スニペット**  
:::image-end:::  

**スニペット**を実行するには、次の操作を行います。

*   [ **スニペット** ] ウィンドウを使ってファイルを開き、[ **実行** ] ([ ![ 実行] ボタン) を選び ][ImageRunIcon] ます。  
*   **[コマンドメニュー][DevtoolsGuideChromiumCommandMenuIndex]** を開き、文字を削除し、スニペットの名前を入力して、 `>` `!` を選択し**Snippet** `Enter` ます。  
    
詳細については [、任意のページから「コードのスニペットを実行][DevtoolsGuideChromiumJavascriptSnippets] する」を参照してください。

## デバッグ JavaScript  

JavaScript を使って問題が発生した場所を推測するのではなく `console.log()` 、Microsoft Edge devtools デバッグツールの使用を検討してください。  一般的な考え方として、ブレークポイントを設定します。これは、コードの中で意図的に停止しています。その後、コードの実行時に1行ずつ手順を実行します。  コードをステップ実行するときに、現在定義されているすべてのプロパティと変数の値の表示と変更、 **コンソール**での JavaScript の実行などを行うことができます。

「 [デバッグ JavaScript の概要][DevtoolsGuideChromiumJavascriptIndex] 」に移動して、devtools でのデバッグの基礎を学びましょう。

:::image type="complex" source="./media/debugging.msft.png" alt-text="ページウィンドウ" lightbox="./media/debugging.msft.png":::
   デバッグ JavaScript  
:::image-end:::  

## ワークスペースを設定する  

既定では、[ **ソース** ] パネルでファイルを編集すると、ページを読み込むときにその変更が失われます。  **ワークスペース** を使用すると、devtools で行った変更をファイルシステムに保存することができます。  基本的に、DevTools はコードエディターとして使うことができます。

作業を開始するには、「 [ワークスペースでファイルを編集][DevtoolsGuideChromiumWorkspacesIndex] する」に移動します。

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRunIcon]: ./media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: ./command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevtoolsGuideChromiumJavascriptIndex]: ./javascript/index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要"  
[DevtoolsGuideChromiumJavascriptSnippets]: ./javascript/snippets.md "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。"  
[DevtoolsGuideChromiumWorkspacesIndex]: ./workspaces/index.md "ワークスペースを使用してファイルを編集する"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "オリジン-HTML 標準"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "フレーム |勧告"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/sources) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
