---
description: Microsoft Edge DevTools のソースパネルで、ファイルの表示と編集、スニペットの作成、JavaScript のデバッグ、ワークスペースのセット アップを行います。
title: ソース パネルの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 開発, f12 ツール, devtools
ms.openlocfilehash: 971ee6e112daaba828a8b754b63eee73ea51e99e
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: HT
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

*   [ファイルを表示](#view-files)。  
*   [CSS と JavaScript を編集](#edit-css-and-javascript)。  
*   [JavaScript の **スニペット** を作成して保存](#create-save-and-run-snippets)。これは、どのページでも実行できます。  **スニペット** は bookmarklets に似ています。  
*   [JavaScript をデバッグ](#debug-javascript)。  
*   [ワークスペースをセット アップ](#set-up-a-workspace)して、DevTools で行った変更がファイル システムのコードに保存されるようにします。  
    
## ファイルの表示  

**ページ**ウィンドウを使用して、ページに読み込まれたすべてのリソースを表示します。

:::image type="complex" source="./media/sources-page-pane.msft.png" alt-text="ページウィンドウ" lightbox="./media/sources-page-pane.msft.png":::
   **ページ**ウィンドウ  
:::image-end:::  

**ページ**ウィンドウの構成:  
*   `top`上の図のような最上位のレベルは、[HTML フレーム][W3CHtml4Frames]を表します。  `top`アクセスしたすべてのページで [検索]します。  `top` メイン文書のフレームを表します。  
*   `docs.microsoft.com`上の図のように、第 2 レベルは [起点][HtmlstandardOrigin]を表します。  
*   第 3 レベル、第 4 レベルとそれ以降は、その起点から読み込まれたディレクトリとリソースを表します。  たとえば、前の図では、リソースへの完全なパス `devtools-guide-chromium` は `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  
    
**ページ**ウィンドウでファイルをクリックして、[**エディター**] ウィンドウでコンテンツを表示します。  任意の種類のファイルを表示できます。  画像の場合、画像のプレビューが表示されます。  

:::image type="complex" source="./media/sources-editor-pane.msft.png" alt-text="[エディター] ウィンドウで [a4d10f71.index-docs.js] の内容を表示する" lightbox="./media/sources-editor-pane.msft.png":::
   [ **エディター** ] ウィンドウで `a4d10f71.index-docs.js` のコンテンツを表示する  
:::image-end:::  

## CSS と JavaScript を編集する  

[ **エディター** ] ウィンドウを使って、CSS と JavaScript を編集します。  DevTools はページを更新して、新しいコードを実行します。  たとえば、次のようなスタイル ルールを追加して CSS ファイルを編集するとします。

```css
.metadata.page-metadata {
    color: red;
}
```

この変更はすぐに有効になります。

:::image type="complex" source="./media/edit-css.msft.png" alt-text="[エディター] ウィンドウでCSS の編集を行うと、字幕のテキストの色が赤に変更されます。" lightbox="./media/edit-css.msft.png":::
   [ **エディター** ] ウィンドウで [CSS の編集] を行うと、字幕のテキストの色が赤に変更されます。  
:::image-end:::  

CSS の変更は直ちに有効になります。保存する必要はありません。  JavaScript の変更を有効にするには`Control`+`S` [\(Windows, Linux\)] または`Command`+`S` [\(macOS\)] を選択します。  DevTools ではスクリプトは再実行されないため、 JavaScript の変更で有効にできるのは、関数内で行う変更のみです。  たとえば、次の図でどのような場合に `console.log('A')`実行されないか、それに対して `console.log('B')` 実行されるかに注意してください。  DevTools を変更した後でスクリプト全体を再実行すると、テキストは `A` **本体**に記録されます。  

:::image type="complex" source="./media/edit-js.msft.png" alt-text="[エディター] ウィンドウでの JavaScript の編集" lightbox="./media/edit-js.msft.png":::
   [ **エディター** ] ウィンドウでの JavaScript の編集  
:::image-end:::  

DevTools は、ページの再読み込み時に CSS と JavaScript の変更を消去します。  ファイル システムへの変更を保存する方法については、「 [ワークスペースのセット アップ](#set-up-a-workspace)」へ移動して参照してください。  

## スニペットの作成、保存、および実行  

スニペットは、任意のページで実行できるスクリプトです。  JQuery ライブラリをページに挿入するために、 **コンソール**に次のコードを繰り返し入力して、 **コンソール**から jQuery コマンドを実行できるようにするとします。  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

代わりに、このコードを **スニペット** として保存すれば、ボタンを 1、2 回クリックするだけで、必要に応じて実行することができます。  DevTools は、 **スニペット** をファイル システムに保存します。  

:::image type="complex" source="./media/snippet.msft.png" alt-text="JQuery ライブラリをページに挿入するスニペット" lightbox="./media/snippet.msft.png":::
   JQuery ライブラリをページに挿入する**スニペット**  
:::image-end:::  

**スニペット**を実行するには、次の操作を行います。

*   [**スニペット**] ウィンドウを使ってファイルを開き、[**実行** \(![ボタンの実行][ImageRunIcon]\)] を選びます。  
*   **[コマンドメニュー][DevtoolsGuideChromiumCommandMenuIndex]** を開き、`>` 文字、種類`!`を削除し、**スニペット**の名前を入力して、`Enter` を選択します。  
    
詳細については「[任意のページからコードのスニペットを実行][DevtoolsGuideChromiumJavascriptSnippets]」へ移動して参照してください。

## JavaScript のデバッグ   

`console.log()` を使って JavaScript に問題が発生した場所を推測するのではなく、Microsoft Edge DevTools デバッグ ツールの使用を検討してください。  一般的な考え方として、ブレーク ポイントを設定します。これは、コードの中で意図的に停止する場所です。その後、コードの実行時に 1 行ずつ手順を実行します。  コードを手順毎に実行するときに、現在定義されているすべてのプロパティと変数の値の表示と変更、 **コンソール**での JavaScript の実行などを行うことができます。

「[JavaScript のデバッグの概要][DevtoolsGuideChromiumJavascriptIndex]」に移動して、DevTools でのデバッグの基礎を学びます。

:::image type="complex" source="./media/debugging.msft.png" alt-text="JavaScript のデバッグ " lightbox="./media/debugging.msft.png":::
   JavaScript のデバッグ   
:::image-end:::  

## ワークスペースを設定する  

既定では、[**ソース**] パネルでファイルを編集すると、ページを再読み込みするときにその変更が失われます。  **ワークスペース** を使用すると、DevTools で行った変更をファイル システムに保存することができます。  基本的に、DevTools はコード エディターとして使うことができます。

作業を開始するには、「[ワークスペースでファイルを編集][DevtoolsGuideChromiumWorkspacesIndex]」に移動します。

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRunIcon]: ./media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: ./command-menu/index.md "Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する"  
[DevtoolsGuideChromiumJavascriptIndex]: ./javascript/index.md "Microsoft Edge DevTools の JavaScript のデバッグの概要"  
[DevtoolsGuideChromiumJavascriptSnippets]: ./javascript/snippets.md "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。"  
[DevtoolsGuideChromiumWorkspacesIndex]: ./workspaces/index.md "ワークスペースを使用してファイルを編集する"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "オリジン-HTML 標準"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "フレーム |W3C"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/sources) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
