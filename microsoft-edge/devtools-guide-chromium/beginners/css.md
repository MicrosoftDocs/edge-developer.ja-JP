---
description: はじめに CSS の使用
title: '初級者向け DevTools: CSS の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools
ms.openlocfilehash: 6f34cfa8610848505c8aa795c4fab16e5d2a98ed
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564645"
---
<!-- Copyright Katherine Jackson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="devtools-for-beginners-get-started-with-css"></a>初級者向け DevTools: CSS の使用を開始する  

このチュートリアルでは、CSS を使用して Web ページのスタイルを設定する方法について説明します。  また、DevTools を使用して CSS Microsoft Edgeを試す方法も説明します。  

次の記事は、Web 開発と DevTools の基本を説明する一連のチュートリアルの 2 番目Microsoft Edgeです。  実際に独自の Web サイトを構築することで、実践的なエクスペリエンスを得る。  2 番目のチュートリアルに従う前に、最初のチュートリアルを完了する必要はもうない。  [コードを設定すると、](#set-up-your-code) セットアップ方法が示されます。  

> [!NOTE]
> このチュートリアルは、完全な初心者向けの設計で **、Web** 開発の基本と DevTools を使用して CSS を実験する基本の両方に焦点を当てしています。  DevTools にのみ焦点を当てたチュートリアルが必要な場合は、[CSS の表示と変更はじめに[に移動します][DevtoolsCssIndex]。  

チュートリアルの冒頭で、サイトは次の図のようになります。  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="サイトの現在の外観" lightbox="../media/beginners-css-intro1.msft.png":::
   サイトの現在の外観  
:::image-end:::  

チュートリアルを完了すると、サイトは次の図のようになります。  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="チュートリアルの最後のサイトの外観" lightbox="../media/beginners-css-intro2.msft.png":::
   チュートリアルの最後のサイトの外観  
:::image-end:::  

## <a name="goals"></a>目標  

このチュートリアルに従って、以下の概念とタスクについて理解してください。  

*   CSS を使用して Web ページのスタイルを設定する方法。  
*   DevTools をMicrosoft Edge CSS を試す方法。  
*   CSS フレームワークと CSS フレームワークの違い。  

実際の Web サイトを作成しています。  

## <a name="prerequisites"></a>前提条件  

このチュートリアルを試す前に、次の前提条件を満たしてください。  

*   [HTML はじめに DOM][DevtoolsBeginnersHtml]を使用して説明を完了するか、HTML と DOM について理解し、そのチュートリアルで教えられたものに似たものにしてください。  
*   Web ブラウザー [Microsoft Edge][MicrosoftEdgeInsider]ダウンロードします。  次のチュートリアルでは、開発ツールに組み込Microsoft Edge DevTools と呼ばれる一連の web 開発ツールをMicrosoft Edge。  

## <a name="set-up-your-code"></a>コードを設定する  

サイトを作成するには、まず次のアクションを実行してコードを設定する必要があります。  

> [!NOTE]
> シリーズの最初のチュートリアルを既に完了している場合は、次のセクションに進んでください。  最後のチュートリアルのコードを引き続き使用して[、HTML はじめに DOM を使用します][DevtoolsBeginnersHtml]。  

1.  ソース コード [を開きます][GlitchCookedAmphibianIndex]。  ブラウザーのフォーカス内タブは、編集タブとして **参照されます**。  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="[編集] タブ" lightbox="../media/beginners-css-setup1.msft.png":::
       [ **編集]** タブ  
    :::image-end:::  
    
1.  調理 **された両生類を選択します**。  メニューがポップアップします。  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text="[Project オプション] メニュー" lightbox="../media/beginners-css-setup2.msft.png":::
       [Project オプション] メニュー  
    :::image-end:::  

1.  **[Remix Project] を選択します**。  Glitch は、編集できるプロジェクトのコピーを作成します。  
    
    > [!NOTE]
    > Glitch は、新しいプロジェクトのランダムな名前を生成します。  
    
1.  [表示 **] を** 選択し、[ **新しいウィンドウ] を選択します**。  別のタブが開き、サイトのライブ ビューが表示されます。  ブラウザーのフォーカス内タブは、ライブ タブとして **参照されます**。  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="[ライブ] タブ" lightbox="../media/beginners-css-setup3.msft.png":::
       [ライブ **] タブ**  
    :::image-end:::  

## <a name="understand-css"></a>CSS について  

**CSS** は、Web ページのレイアウトとスタイルを決定するコンピューター言語です。  次の図は、罫線を持つ段落です。  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="テキストは CSS でスタイル設定されています" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   テキストは CSS でスタイル設定されています  
:::image-end:::  

次のコード スニペットは、前の図の段落を作成するために使用される HTML コードと CSS コードです。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` おそらく、新しく見えます。  残りの部分は見慣れたものに見える必要があります。  指定しない場合は、はじめに[を実行][DevtoolsBeginnersHtml]する前に HTML と DOM を使用して設定を完了してください。  

## <a name="add-inline-styles"></a>インライン スタイルの追加  

インライン スタイルを使用して 1 つの **要素に** スタイルを適用するには、次のアクションを実行します。  

1.  編集タブに戻り、開きます `index.html` 。  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       編集 `index.html` タブで開く  
    :::image-end:::  
    
1.  に `style="background-color: aliceblue;"` 追加します `<nav>` 。  次のコード ブロックでは、4 行目のコードを変更する必要があります。  残りはただそこにあるので、新しいコードを適切な場所に配置することができます。  
    
    ```html
    <header>
        <p>Welcome to my site!</p>
    </header>
    <nav style="background-color: aliceblue;">
        <ul>
            <li><a href="/">Home</a></li>
            ...
        ...
    ...
    ```  
    
1.  変更を表示するには、ライブ タブに **移動します**。 これで、セクションの `<nav>` 背景が青になります。  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text="[ホーム] リンクと [連絡先] リンクの背景の背景色が青色に変更されました" lightbox="../media/beginners-css-inline2.msft.png":::
       [ホーム] リンクと [連絡先]**リンクの背景****の背景色**が青色に変更されました  
    :::image-end:::  
    
## <a name="re-use-styles-on-a-single-page-with-internal-stylesheets"></a>内部スタイルシートを使用して 1 つのページでスタイルを再使用する  

前のコード スニペットでは、インライン スタイルが 1 つのタグにスタイルを適用 `<p>` しました。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

Web ページのすべての要素を同じスタイルにしたい `<p>` 場合は、どうしますか?  サイト上のすべてのタグにコードをコピーして貼り `<p>` 付ける必要があります。  これは多くの時間と労力です。  また、編集が必要な場合は、すべてのタグを再度変更する必要があります。  次のアクションを実行して、 **内部** スタイルシートを使用して CSS を 1 回書き込み、複数の要素に適用します。  

1.  [ライブ] タブで、[連絡先] **を選択** して連絡先ページに移動します。  ホームと連絡先の **フォントに** 注意 **してください**。  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text="[連絡先] ページ" lightbox="../media/beginners-css-internal1.msft.png":::
       [連絡先] ページ  
    :::image-end:::  
    
1.  エディター タブ **で、** を開きます `contact.html` 。  
1.  に次のコードを追加します `contact.html` 。  最初から終わる行は、追加 `<style>` `</style>` する必要がある行です。  もう 1 つのコードはただそこにあるので、新しいコードをどこに置くのか分かっている。  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <style>
                li a {
                  font-family: 'Courier New', Courier, Serif;
                }
            </style>
            ...
        </head>
        ...
    ...
    ```  
    
1.  [ライブ] タブに **戻る**。  
1.  [連絡先 **] を** 選択して、連絡先ページに戻ります。  ホームと連絡先**のフォント****が**変更されました。  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="ホーム リンクと連絡先リンクのフォントが変更されました" lightbox="../media/beginners-css-internal2.msft.png":::
       ホーム リンクと**連絡先リンクの****フォント**が変更されました  
    :::image-end:::  
    
### <a name="understand-internal-stylesheets"></a>内部スタイルシートについて  

内部スタイルシートは、セレクターを使用してスタイル **を適用します**。  セレクターは、1 つ以上の HTML 要素に適用できるパターンです。  前のコード スニペットでは、次のスタイルが追加されました。  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` は、"要素を含む任意の `<li>` 要素" に変換されるセレクター `<a>` です。  各タグ グループがパターンと**** 一致**** する場合、ブラウザーはホーム リンクと連絡先リンクのフォントを変更します。  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` は 宣言 **です**。  宣言は、次の 2 つの部分で構成されます。  

:::row:::
   :::column span="1":::
      **プロパティ**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      プロパティは、要素のスタイルを変更できる一般的な方法について説明します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **value**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      この値は、要素のスタイルがどのように変更されるのかを正確に示します。  
   :::column-end:::
:::row-end:::  

たとえば、ブラウザーに次の指示を与えます。"パターンに一致する要素のフォント `font-family: 'Courier New', Courier, serif` をに設定 `li a` します `'Courier New'` 。  そのフォントが使用できない場合は、 を使用します `Courier` 。  使用できない場合は、 `serif` を使用します。  

### <a name="add-multiple-selectors-to-a-ruleset"></a>ルール セットに複数のセレクターを追加する  

次のコード スニペットのような CSS コードのブロックをルール セットと **呼ぶ**。  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

コンマを使用して複数のセレクターをルール セットに追加するには、次のアクションを実行します。  

1.  エディター タブ **で、** を開きます `contact.html` 。  
1.  After `li a` type `, h1` .  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    前のコード スニペットは、パターンに一致する要素のスタイルを設定するのと同じ方法で要素のスタイルを設定 `<h1>` するブラウザーに指示します `li a` 。  
    
1.  [ライブ] タブ **に移動します**。  
1.  [連絡先] **リンクを** 選択して、連絡先ページに戻ります。  今、 **お問い合わせください!** ナビゲーション リンクと同じフォントを持つ。  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="テキスト [お問い合わせ]  ホームリンクと連絡先リンクと同じフォントが表示される" lightbox="../media/beginners-css-multiple1.msft.png":::
       テキスト [ **お問い合わせ]** ホームリンクと連絡先リンクと同 **じ** フォント **が表示** される  
    :::image-end:::  
    
## <a name="experiment-with-devtools"></a>DevTools の実験  

Web 開発の専門家になるための旅を続ける中で、CSS は難しいと思うかもしれません。  一部の CSS を記述し、1 つの方法で表示すると予想できますが、ブラウザーは完全に異なる動作をします。  Microsoft EdgeDevTools を使用すると、変更を簡単に試し、変更がページに与える影響をすぐに表示できます。  

### <a name="add-a-declaration-to-an-existing-rulest-in-devtools"></a>DevTools の既存のルールに宣言を追加する  

次のアクションを実行して、既存の要素のスタイルを反復処理し、既存のルール セットに宣言を追加します。  

1.  [ホーム] リンク **をポイント** し、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="[ホーム] リンクの検査" lightbox="../media/beginners-css-add1.msft.png":::
       [ホーム] リンクの検査  
    :::image-end:::  
    
    DevTools がページと一緒に開きます。  [ホーム] リンクを表すコードは `<a href="/">Home</a>` 、DOM ツリーで青色で強調表示されます。  コード スニペットとプレビューは、HTML と DOM はじめに[からよく知られている必要があります][DevtoolsBeginnersHtml]。  
    
    :::row:::
       :::column span="":::
          次の図では、以前に追加した宣言が DOM ツリーの下の [スタイル] タブ `font-family: 'Courier New', Courier, serif` `contact.html` に表示されます。 ****  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text="[スタイル] タブは DOM ツリーの下にあります" lightbox="../media/beginners-css-add2.msft.png":::
             [ **スタイル]** タブは DOM ツリーの下にあります  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          DevTools ウィンドウが広い場合、[スタイル] タブは DOM ツリーの右側にあります。  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text="[スタイル] タブは DOM ツリーの右側にあります。" lightbox="../media/beginners-css-add3.msft.png":::
             [ **スタイル]** タブは DOM ツリーの右側にあります。  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  新しい宣言を追加するには `font-family: 'Courier New', Courier, Serif` 、下の空の行を選択します。  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="新しい宣言を追加する" lightbox="../media/beginners-css-add4.msft.png":::
       新しい宣言を追加する  
    :::image-end:::  
    
1.  `color` を入力して、`Enter` を選択します。  オートコンプリート UI は、入力時にオプションを提案します。  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="型の色" lightbox="../media/beginners-css-add5.msft.png":::
       型 `color`  
    :::image-end:::  
    
1.  `magenta` を入力して、`Enter` を選択します。  連絡先ページのすべてのテキストが magenta です。  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="タイプ magenta" lightbox="../media/beginners-css-add6.msft.png":::
       型 `magenta`  
    :::image-end:::  
    
### <a name="edit-a-declaration-in-devtools"></a>DevTools で宣言を編集する  

DevTools で既存の宣言を編集するには、次のアクションを実行します。  

1.  の横にあるマゼンタの四角形を選択します `magenta` 。  カラー ピッカーがポップアップします。  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="カラー ピッカー" lightbox="../media/beginners-css-edit1.msft.png":::
       カラー ピッカー  
    :::image-end:::  
    
1.  カラー ピッカーを使用して、フォント テキストを好きな色に変更します。  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="Color Picker を使用してフォントの色を紫に変更する" lightbox="../media/beginners-css-edit2.msft.png":::
       Color Picker を使用してフォントの色を紫に変更する  
    :::image-end:::  
    
### <a name="add-a-new-ruleset-in-devtools"></a>DevTools に新しいルールセットを追加する  

DevTools に新しいルールセットを追加するには、次のアクションを実行します。  

1.  .cls **の横にある** [新しいスタイル ルール \( 新しいスタイル ルール ![ ](../media/new-style-rule-icon.msft.png) **\) を選択します**。  セレクターとして空のルール セット `a` が表示されます。  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="新しいルールを追加する" lightbox="../media/beginners-css-rule1.msft.png":::
       新しいルールを追加する  
    :::image-end:::  
    
1.  に `a` 置き換える `a:hover` 。  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="a を a:hover に置き換える" lightbox="../media/beginners-css-rule2.msft.png":::
       に置き `a` 換える `a:hover`  
    :::image-end:::  
    
    `:hover` は **擬似 クラス です**。  特殊な状態に入る可能性があるスタイル要素には、擬似クラスを使用します。  たとえば、スタイル `a:hover` は要素の上にカーソルを置く場合にのみ有効 `<a>` になります。  
    
1.  かっこの中から選択して、新しい宣言を追加します。  
1.  宣言 `background-color` 名を入力し、を選択します `Enter` 。  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="背景色を入力する" lightbox="../media/beginners-css-rule3.msft.png":::
       型 `background-color`  
    :::image-end:::  
    
1.  宣言 `green` 値を入力し、を選択します `Enter` 。  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="緑と入力します" lightbox="../media/beginners-css-rule4.msft.png":::
       型 `green`  
    :::image-end:::  
    
1.  [ホーム] リンクの上にマウス **ポインターを移動** します。  リンクの背景が緑色に変わります。  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="[ホーム] リンクにカーソルを合わせると、緑色の背景が表示されます。" lightbox="../media/beginners-css-rule5.msft.png":::
       [ホーム] リンクにカーソルを合わせると、緑色の背景が表示されます。  
    :::image-end:::  
    
## <a name="re-use-styles-across-pages-with-external-stylesheets"></a>外部スタイルシートを使用してページ間でスタイルを再使用する  

前の手順では、次のコード スニペットを内部スタイルシートとして追加しました `contact.html` 。  

```html
...
    ...
        ...
        <style>
            li a, h1 {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

同じスタイルにしたい `index.html` 場合は、  スタイルを適用するページ数が多い場合は、どうしますか?  内部スタイルシートをコピーして、サイト上のすべての Web ページに貼り付ける必要があります。  次のアクションを実行して外部スタイルシート **を** 追加し、CSS を 1 回書き込み、複数のページに適用できます。  

1.  まず、ライブ タブを更新して、DevTools で行った変更を削除します。  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" ページを更新すると、DevTools で行われた変更はなくなりました" lightbox="../media/beginners-css-external1.msft.png":::
        ページを更新すると、DevTools で行われた変更はなくなりました  
    :::image-end:::  
    
1.  [エディター] タブに **戻り、開** きます `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       contact.html  
    :::image-end:::  
    
1.  の間、および `<style>` `</style>` 、 を含むすべてを `<style>` 削除します `</style>` 。  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="スタイル タグが削除されました" lightbox="../media/beginners-css-external3.msft.png":::
       スタイル タグが削除されました  
    :::image-end:::  
    
1.  タグ `index.html` を開 `style="background-color: aliceblue;"` いて削除 `<nav>` します。  これで、以前にサイトに追加した CSS のすべてが削除されました。  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="インライン スタイルが nav 要素から削除されました" lightbox="../media/beginners-css-external4.msft.png":::
       インライン スタイルが nav 要素から削除されました  
    :::image-end:::  
    
1.  [新 **しいファイル] を選択します**。  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="新しいファイル ダイアログ" lightbox="../media/beginners-css-external5.msft.png":::
       新しいファイル ダイアログ  
    :::image-end:::  
    
1.  に `cool-file.js` 置き換 `style.css` え、[ファイルの追加 **] を選択します**。  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="type style.css" lightbox="../media/beginners-css-external6.msft.png":::
       型 `style.css`  
    :::image-end:::  
    
1.  次のコード スニペットをファイルに追加 `style.css` します。  
    
    ```css
    li a, h1 {
      font-family: 'Courier New', Courier, Serif;
    }
    a:hover {
      background-color: green;
    }
    nav {
      background-color: aliceblue;
    }
    ```  
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text="style.css にコードを追加する" lightbox="../media/beginners-css-external7.msft.png":::
       コードを追加する `style.css`  
    :::image-end:::  
    
    外部スタイルシートが作成されている必要があります。 HTML が存在することを認識しません。  
    
1.  を `index.html` 開きます。  
1.  `<link rel="stylesheet" href="style.css">`HTML に追加します。  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="style.css へのリンク" lightbox="../media/beginners-css-external8.msft.png":::
       リンク先 `style.css`  
    :::image-end:::  
    
1.  ファイルを `contact.html` 開き、そこにリンクを追加します。  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="l の style.css へのリンクcontact.htmします。" lightbox="../media/beginners-css-external9.msft.png":::
       への `style.css` リンク `contact.html`  
    :::image-end:::  
    
1.  [ライブ] タブ **に移動します**。 ホーム ページには、最後のセクションと青いナビゲーション セクションのフォントが同じになります。  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="ホーム ページ" lightbox="../media/beginners-css-external10.msft.png":::
       ホーム ページ  
    :::image-end:::  
    
1.  [連絡先] **リンクを** 選択して、連絡先ページに移動します。  連絡先ページの書式はホーム ページと同じです。  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="連絡先ページ" lightbox="../media/beginners-css-external11.msft.png":::
       連絡先ページ  
    :::image-end:::  
    
## <a name="use-a-css-framework"></a>CSS フレームワークの使用  

**CSS フレームワークは、** 他の開発者によって構築されたスタイルのコレクションで、魅力的な Web サイトを簡単に作成できます。  フレームワークは、自分でスタイルを定義する代わりに、ページ要素で使用できるスタイルのコレクションを提供します。  

1.  次のコードをコピーします。  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  編集タブを開き、コードをに貼り付けます `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="l のフレームワークへのリンクcontact.htmします。" lightbox="../media/beginners-css-framework1.msft.png":::
       のフレームワークへのリンク `contact.html`  
    :::image-end:::  
    
1.  ファイルを `index.html` 開き、そこにコードを追加します。  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="l のフレームワークへのリンクindex.htmします。" lightbox="../media/beginners-css-framework2.msft.png":::
       のフレームワークへのリンク `index.html`  
    :::image-end:::  
    
1.  [ライブ] タブに戻り、変更を表示します。  要素の背景色と要素のフォントは同じですが、他の要素のフォント `<nav>` `<li>` `<a>` は変更されています。  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="フレームワークのためにホーム ページのフォントの一部が変更されました" lightbox="../media/beginners-css-framework3.msft.png":::
       フレームワークのためにホーム ページのフォントの一部が変更されました  
    :::image-end:::  
    
### <a name="use-a-class"></a>クラスを使用する  

最後のセクションでは、ブートストラップを Web ページに追加し、サイトの一部の要素のフォントを変更しました。  CSS フレームワークは、コードが非常に少ないページに大きな変更を加えるのに役立ちます。  ヘッダーを変更するには、次のアクションを実行します。  

1.  次のコード スニペットをコピーします。  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  前のコード スニペットをタグに `<header>` 追加します `index.html` 。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="l のクラスをindex.htmする" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       にクラスを追加する `index.html`  
    :::image-end:::  
    
1.  でタグにコード `<header>` を追加します `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="l のクラスをcontact.htmする" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       にクラスを追加する `contact.html`  
    :::image-end:::  
    
1.  [ライブ] タブで変更を表示します。 ヘッダーの周りに大きな灰色のボックスがあります。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="ヘッダーの周囲に大きな灰色のボックスが表示される" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       ヘッダーの周囲に大きな灰色のボックスが表示される  
    :::image-end:::  
    
### <a name="understand-classes"></a>クラスについて  

クラスを使用すると、スタイルのコレクションを任意の要素に割り当てできます。  属性をに設定した後、要素にいくつかのスタイルを適用するには、次の `<header>` コード `class` スニペットを使用します `jumbotron` 。  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

クラスの利点の 1 つは、必要な要素にスタイルを適用できる方法です。  たとえば、一部の要素の背景色を紫に設定するとしますが、すべての要素 `<p>` には設定 `<p>` できないとします。  クラスのスタイルを定義するには、次のコード スニペットを使用します。  

```css
.custom-background {
  background-color: purple;
}
```  

次に、スタイルを設定する `<p>` 要素にのみクラスを適用します。  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <a name="align-elements"></a>要素を整列する  

次のアクションを実行して、要素を整列するクラスをブートストラップして提供します。  

1.  [エディター] タブに戻り、開きます `index.html` 。  
1.  タグ `class="container-fluid"` に追加 `<body>` します。  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="コンテナー流体クラスを追加する" lightbox="../media/beginners-css-align1.msft.png":::
       クラスを追加 `container-fluid` する  
    :::image-end:::  
    
1.  and 要素 `<nav>` を `<main>` 折り返します `<div class="row">` 。  新しいタグを `</div>` 適切に `</main>` 閉じるには、必ず後に置く必要があります。  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="行の追加" lightbox="../media/beginners-css-align2.msft.png":::
       行の追加  
    :::image-end:::  
    
1.  タグ `class="col-3"` と `<nav>` タグ `class="col-9"` に追加 `<main>` します。  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="col-3 クラスと col-9 クラスを追加する" lightbox="../media/beginners-css-align3.msft.png":::
       and クラス `col-3` を `col-9` 追加する  
    :::image-end:::  
    
1.  [ライブ] タブで変更を表示します。  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="ナビゲーション コンテンツがメイン コンテンツの左側に表示される" lightbox="../media/beginners-css-align4.msft.png":::
       ナビゲーション コンテンツがメイン コンテンツの左側に表示される  
    :::image-end:::  
    
## <a name="next-steps"></a>次の手順  

おめでとうございます。完了です。  

*   Web 開発を向上する最善の方法は、より多くのサイトを構築する方法です。  壊れる心配はありません。  ただ、楽しみを持って、道に沿って可能な限り多くを学ぶ。  
*   Web ページのスタイル設定の詳細については、「CSS の概要 [」に移動します][MDNCssFirstSteps]。  
*   DevTools を使用してページの CSS を試す方法の詳細については、「CSS の表示と変更」はじめにに[移動します][DevtoolsCssIndex]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "初級向け DevTools: HTML と DOM の使用を開始する | Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "はじめにCSS の表示と変更を使用|Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html - 調理された両生類|Glitch"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS の最初の手順|MDN"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/beginners/css) つかり、キャ [サ][KatherineJackson] リン・ジャクソン \(Technical Writer Intern, Chrome DevTools\) によって作成されました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors  
