---
description: CSS の使用を開始する
title: '初心者向けの DevTools: CSS の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fe87b4f840c6d9dde3cdf6455700161ea8d8d31e
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993304"
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

# 初心者向けの DevTools: CSS の使用を開始する  

このチュートリアルでは、CSS を使用して web ページのスタイルを作成する方法について説明します。  また、Microsoft Edge DevTools を使用して CSS の変更を試す方法についても説明します。  

次の記事は、web 開発と Microsoft Edge DevTools の基礎について説明している一連のチュートリアルの2番目のチュートリアルです。  実際に自分の web サイトを構築することで、実践的なエクスペリエンスを実現できます。  2番目のチュートリアルに従う前に、最初のチュートリアルを完了する必要はありません。  [コードを設定](#set-up-your-code) すると、セットアップ方法が表示されます。  

> [!NOTE]
> このチュートリアルは、基本的な初心者向けに設計されており、 **web 開発の基礎** と、開発者向けの基本的なツールを使用した CSS の基本的な使い方に重点を置いています。  開発ツールにのみ重点を置いたチュートリアルが必要な場合は、「 [CSS の表示と変更の概要][DevtoolsCssIndex]」を参照してください。  

チュートリアルの最初に、サイトは次の図のようになります。  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="現在のサイトの外観" lightbox="../media/beginners-css-intro1.msft.png":::
   現在のサイトの外観  
:::image-end:::  

チュートリアルを完了したら、サイトは次の図のようになります。  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="チュートリアルの最後にサイトがどのように表示されるか" lightbox="../media/beginners-css-intro2.msft.png":::
   チュートリアルの最後にサイトがどのように表示されるか  
:::image-end:::  

## 目標  

以下の概念とタスクについて詳しく理解するには、このチュートリアルに従ってください。  

*   CSS を使用して web ページのスタイルを適用する方法について説明します。  
*   Microsoft Edge DevTools を使って CSS を試す方法を説明します。  
*   CSS と CSS フレームワークの違い。  

実際の web サイトを作成しています。  

## 前提条件  

このチュートリアルを実行する前に、次の前提条件を完了してください。  

*   [[Html と dom の使用を開始][DevtoolsBeginnersHtml]する] または [dom] の概要については、このチュートリアルで説明するように、HTML と dom について理解していることを確認してください。  
*   [Microsoft Edge][MicrosoftEdgeInsider] web ブラウザーをダウンロードします。  次のチュートリアルでは、microsoft edge DevTools と呼ばれる web 開発ツールのセットを使用して、Microsoft Edge に組み込まれています。  

## コードを設定する  

サイトを作成するには、最初に次の操作を実行してコードを設定する必要があります。  

> [!NOTE]
> 一連の最初のチュートリアルを既に完了している場合は、次のセクションに進んでください。  「 [HTML と DOM の使用を開始][DevtoolsBeginnersHtml]する」のチュートリアルで説明したコードの使用を続けます。  

1.  [ソースコード][GlitchCookedAmphibianIndex]を開きます。  ブラウザーの [フォーカス] タブは [ **編集] タブ**として参照されます。  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="[編集] タブ" lightbox="../media/beginners-css-setup1.msft.png":::
       [ **編集** ] タブ  
    :::image-end:::  
    
1.  [ **クック-水陸両用機**] を選びます。  メニューがポップアップ表示されます。  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text="[プロジェクトのオプション] メニュー" lightbox="../media/beginners-css-setup2.msft.png":::
       [プロジェクトのオプション] メニュー  
    :::image-end:::  

1.  [ **Remix Project**] を選びます。  エラー編集可能なプロジェクトのコピーを作成します。  
    
    > [!NOTE]
    > エラー新しいプロジェクトに対してランダムな名前を生成します。  
    
1.  [ **表示** ] を選択し、 **新しいウィンドウで**を選択します。  サイトのライブビューで別のタブが開きます。  ブラウザーの [フォーカス] タブは、[ **ライブ] タブ**として参照されます。  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="[ライブ] タブ" lightbox="../media/beginners-css-setup3.msft.png":::
       [ **ライブ] タブ**  
    :::image-end:::  

## CSS について  

**CSS** は、web ページのレイアウトとスタイルを決定するコンピューターの言語です。  次の図は、罫線が付いた段落を示しています。  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="テキストは CSS でスタイル設定されています" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   テキストは CSS でスタイル設定されています  
:::image-end:::  

次のコードスニペットは、前の図で段落を作成するために使用される HTML と CSS のコードです。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` おそらく、新しくなったようです。  その他の方法については、こちらをご覧ください。  表示されない場合は、次のセクションの手順を実行する前に、「 [HTML と DOM で作業を開始][DevtoolsBeginnersHtml] する」を完了してください。  

## インラインスタイルを追加する  

**インラインスタイル**を使って1つの要素にスタイルを適用するには、次の操作を実行します。  

1.  [編集] タブに戻り、[開く] をクリックし `index.html` ます。  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       [ `index.html` 編集] タブで開く  
    :::image-end:::  
    
1.  `style="background-color: aliceblue;"`にを追加 `<nav>` します。  以下のコードブロックでは、コードの4行目が変更する必要があるものです。  残りの部分はそのままで、新しいコードを適切な場所に配置することができます。  
    
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
    
1.  [ **ライブ] タブ** に移動して変更を確認します。  セクションの背景 `<nav>` が青色になります。  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text="ホームと連絡先のリンクの背景色が青になりました" lightbox="../media/beginners-css-inline2.msft.png":::
       **ホーム**と**連絡先**のリンクの背景色が青になりました  
    :::image-end:::  
    
## 内部のスタイルシートを使用して、1つのページでスタイルを再利用する  

前のコードスニペットでは、インラインスタイルは1つのタグにスタイルを適用していま `<p>` した。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`<p>`Web ページ上のすべての要素に同じようなスタイルを適用する必要がある場合はどうすればよいですか?  コードをコピーして、サイトのすべての1つのタグに貼り付ける必要があり `<p>` ます。  これは多くの時間と労力を備えています。  編集を行う必要がある場合は、すべてのタグをもう一度変更する必要があります。  複数の要素に適用されるように、 **内部のスタイルシート** を使用して CSS を1つ作成するには、次の操作を実行します。  

1.  「ライブ」タブで、「 **コンタクト** 」を選択して、コンタクトページに移動します。  [ **ホーム** ] と [ **連絡先**] のフォントを確認します。  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text="[連絡先] ページ" lightbox="../media/beginners-css-internal1.msft.png":::
       [連絡先] ページ  
    :::image-end:::  
    
1.  [ **エディター] タブ**で、に移動 `contact.html` します。  
1.  次のコードをに追加 `contact.html` します。  追加する必要があるのは、[で始まる] `<style>` と [末尾] の行 `</style>` だけです。  その他のコードは、新しいコードを配置する場所を知っているだけです。  
    
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
    
1.  [ **ライブ] タブ**に戻ります。  
1.  [ **連絡先** ] を選択して、連絡先ページに戻ります。  [ **ホーム** ] と [ **連絡先** ] のフォントが変更されました。  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="自宅と連絡先のリンクのフォントが変更されました" lightbox="../media/beginners-css-internal2.msft.png":::
       **自宅**と**連絡先**のリンクのフォントが変更されました  
    :::image-end:::  
    
### 内部のスタイルシートについて  

内部スタイルシートは **セレクター**を使ってスタイルを適用します。  セレクターは、1つ以上の HTML 要素に適用される可能性があるパターンです。  前のコードスニペットでは、次のスタイルが追加されています。  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` は、"要素を含むすべての要素" に変換するセレクターです `<li>` `<a>` 。  各タググループはパターンと一致するため、ブラウザーは **ホーム** と **連絡先** のリンクのフォントを変更します。  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` は **宣言**です。  宣言は、次の2つの部分で構成されます。  

:::row:::
   :::column span="1":::
      **プロパティー**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      プロパティでは、要素のスタイルを変更できる一般的な方法について説明します。  
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
      この値は、要素のスタイルを変更する方法を正確に記述します。  
   :::column-end:::
:::row-end:::  

たとえば、次のような指示が表示されます。 `font-family: 'Courier New', Courier, serif` "パターンと一致する要素のフォント `li a` を設定 `'Courier New'` します。  そのフォントが利用できない場合は、を使用 `Courier` します。  利用できない場合は、 `serif` 「」を使用します。  

### 複数のセレクターをルールセットに追加する  

以下に示すような CSS コードのブロックは、 **ルールセット**と呼ばれています。  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

コンマを使用して複数のセレクターをルールセットに追加するには、次の操作を実行します。  

1.  [ **エディター] タブ**で、を開き `contact.html` ます。  
1.  `li a`種類 `, h1` の後。  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    前のコードスニペットは、パターンと一致する要素のスタイルを示すのと同じように、ブラウザーに対して要素のスタイルを `<h1>` 適用し `li a` ます。  
    
1.  [ **ライブ] タブ**に移動します。  
1.  **連絡先のリンクを**選択して、連絡先ページに戻ります。  今すぐ **連絡してください。** ナビゲーションリンクと同じフォントに設定されています。  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="「連絡」というテキストが表示されます。  自宅と連絡先のリンクと同じフォントになりました" lightbox="../media/beginners-css-multiple1.msft.png":::
       「連絡」というテキストが表示されます **。** **自宅**と**連絡先**のリンクと同じフォントになりました  
    :::image-end:::  
    
## DevTools を使って実験する  

今後、web 開発の専門家になるために、引き続き、CSS が複雑になることがあります。  CSS を作成して、1つの方法で表示することも考えられますが、ブラウザーはまったく異なるものになります。  Microsoft Edge DevTools を使うと、簡単に変更を試すことができ、変更内容がページにどのように影響するかをすぐに確認できます。  

### DevTools で既存の rulest に宣言を追加する  

既存の要素のスタイルに対して反復処理を行うには、次の操作を実行し、既存のルールセットに宣言を追加します。  

1.  [ **ホーム** ] リンク上にマウスポインターを置いて、コンテキストメニュー \ (右クリック \) を開き、[ **検査**] を選びます。  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="[ホーム] リンクを検査する" lightbox="../media/beginners-css-add1.msft.png":::
       [ホーム] リンクを検査する  
    :::image-end:::  
    
    DevTools はページの横に表示されます。  [ホーム] リンクを表すコード `<a href="/">Home</a>` は、DOM ツリーで青色で強調表示されています。  コードスニペットとプレビューについては、「 [HTML と DOM の概要][DevtoolsBeginnersHtml]」をご覧ください。  
    
    :::row:::
       :::column span="":::
          次の図では、 `font-family: 'Courier New', Courier, serif` 以前に追加した宣言 `contact.html` が DOM ツリーの下にある [ **スタイル** ] タブに表示されています。  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text="[スタイル] タブが DOM ツリーの下にある" lightbox="../media/beginners-css-add2.msft.png":::
             [ **スタイル** ] タブが DOM ツリーの下にある  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          DevTools ウィンドウが広くなっている場合、[スタイル] タブは DOM ツリーの右側にあります。  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text="[スタイル] タブは DOM ツリーの右側にあります。" lightbox="../media/beginners-css-add3.msft.png":::
             [ **スタイル** ] タブは DOM ツリーの右側にあります。  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  新しい宣言を追加するには、下の空の行を選び `font-family: 'Courier New', Courier, Serif` ます。  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="新しい宣言を追加する" lightbox="../media/beginners-css-add4.msft.png":::
       新しい宣言を追加する  
    :::image-end:::  
    
1.  入力 `color` して、を選択し `Enter` ます。  入力時にオートコンプリート UI によってオプションが提示されます。  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="テキストの色" lightbox="../media/beginners-css-add5.msft.png":::
       型 `color`  
    :::image-end:::  
    
1.  入力 `magenta` して、を選択し `Enter` ます。  連絡先ページのすべてのテキストがマジェンタ色になりました。  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="「マゼンタ」と入力" lightbox="../media/beginners-css-add6.msft.png":::
       型 `magenta`  
    :::image-end:::  
    
### DevTools で宣言を編集する  

DevTools で既存の宣言を編集するには、次の操作を実行します。  

1.  の横にあるマゼンタの正方形を選び `magenta` ます。  カラーピッカーがポップアップ表示されます。  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="色のパレット" lightbox="../media/beginners-css-edit1.msft.png":::
       色のパレット  
    :::image-end:::  
    
1.  カラーピッカーを使用して、フォントのテキストを好みの色に変更します。  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="カラーピッカーを使用してフォントの色を紫色に変更する" lightbox="../media/beginners-css-edit2.msft.png":::
       カラーピッカーを使用してフォントの色を紫色に変更する  
    :::image-end:::  
    
### DevTools で新しいルールセットを追加する  

DevTools で新しいルールセットを追加するには、次の操作を実行します。  

1.  Cls の隣にある [**新しいスタイルルール**] \ ( ![ 新しいスタイルルール ][ImageNewStyleRuleIcon] ) **.cls**を選びます。  空のルールセットが `a` セレクターとして表示されます。  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="新しいルールを追加する" lightbox="../media/beginners-css-rule1.msft.png":::
       新しいルールを追加する  
    :::image-end:::  
    
1.  置換後 `a` の文字列 `a:hover`  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="を "a/a" に変更する" lightbox="../media/beginners-css-rule2.msft.png":::
       置換後 `a` の文字列 `a:hover`  
    :::image-end:::  
    
    `:hover` は **擬似クラス**です。  特殊な状態を入力する可能性のあるスタイル要素には、擬似クラスを使います。  たとえば、スタイルは、 `a:hover` 要素の上にマウスポインターを置いた場合にのみ有効になり `<a>` ます。  
    
1.  角かっこの間を選択して新しい宣言を追加します。  
1.  `background-color`宣言の名前を入力して、を選択し `Enter` ます。  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="背景色を入力する" lightbox="../media/beginners-css-rule3.msft.png":::
       型 `background-color`  
    :::image-end:::  
    
1.  `green`[宣言] の値を入力して、を選択し `Enter` ます。  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="「緑」と入力" lightbox="../media/beginners-css-rule4.msft.png":::
       型 `green`  
    :::image-end:::  
    
1.  [ **ホーム** ] リンクの上にマウスポインターを置きます。  リンクの背景が緑色になります。  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="[ホーム] リンクをポイントすると、緑色の背景が表示されます。" lightbox="../media/beginners-css-rule5.msft.png":::
       [ホーム] リンクをポイントすると、緑色の背景が表示されます。  
    :::image-end:::  
    
## 外部のスタイルシートを含むページ間でスタイルを再利用する  

前の手順では、次のコードスニペットを内部のスタイルシートとして追加しました `contact.html` 。  

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

同じ方法でスタイルを適用する場合は、どうすればよい `index.html` ですか。  スタイルを適用するには、多数のページが必要な場合はどうすればよいですか。  内部のスタイルシートをコピーして、サイトのすべての単一の web ページに貼り付ける必要があります。  CSS を一度作成して複数のページに適用できるように、 **外部のスタイルシート** を追加するには、次の操作を実行します。  

1.  まず、[ライブ] タブをもう一度読み込んで、DevTools で行った変更を削除します。  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" ページを更新すると、DevTools で行った変更は廃止されます。" lightbox="../media/beginners-css-external1.msft.png":::
        ページを更新すると、DevTools で行った変更は廃止されます。  
    :::image-end:::  
    
1.  [ **エディター] タブ** に戻り、を開き `contact.html` ます。  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       contact.html  
    :::image-end:::  
    
1.  およびを `<style>` `</style>` 含む、and を含むすべてのデータを削除し `<style>` `</style>` ます。  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="スタイルタグが削除されました" lightbox="../media/beginners-css-external3.msft.png":::
       スタイルタグが削除されました  
    :::image-end:::  
    
1.  `index.html`タグから移動して削除し `style="background-color: aliceblue;"` `<nav>` ます。  これで、以前にサイトに追加した CSS がすべて削除されました。  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="インラインスタイルが nav 要素から削除されている" lightbox="../media/beginners-css-external4.msft.png":::
       インラインスタイルが nav 要素から削除されている  
    :::image-end:::  
    
1.  [ **新しいファイル**] を選びます。  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="[新しいファイル] ダイアログ" lightbox="../media/beginners-css-external5.msft.png":::
       [新しいファイル] ダイアログ  
    :::image-end:::  
    
1.  [置換後 `cool-file.js` の文字列 `style.css` ] を選び、[ **ファイルの追加**] を選びます。  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="「スタイル .css」と入力します。" lightbox="../media/beginners-css-external6.msft.png":::
       型 `style.css`  
    :::image-end:::  
    
1.  次のコードスニペットをファイルに追加し `style.css` ます。  
    
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
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text=".Css にコードを追加する" lightbox="../media/beginners-css-external7.msft.png":::
       コードを追加 `style.css`  
    :::image-end:::  
    
    外部のスタイルシートが作成されていることを確認します。 HTML では、存在することは認識されません。  
    
1.  [開く] `index.html` を選びます。  
1.  `<link rel="stylesheet" href="style.css">`HTML に追加します。  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="スタイル .css へのリンク" lightbox="../media/beginners-css-external8.msft.png":::
       へのリンク `style.css`  
    :::image-end:::  
    
1.  ファイルを開き、 `contact.html` そこにリンクを追加します。  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="contact.html のスタイル .css へのリンク" lightbox="../media/beginners-css-external9.msft.png":::
       [リンク先] `style.css` `contact.html`  
    :::image-end:::  
    
1.  [ **ライブ] タブ**に移動します。 これで、ホームページの最後のセクションと青色のナビゲーションセクションのフォントが変わりました。  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="ホームページ" lightbox="../media/beginners-css-external10.msft.png":::
       ホームページ  
    :::image-end:::  
    
1.  [ **連絡先** ] リンクを選択して、連絡先ページに移動します。  連絡先ページは、ホームページと同じ書式設定になっています。  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="[連絡先] ページ" lightbox="../media/beginners-css-external11.msft.png":::
       [連絡先] ページ  
    :::image-end:::  
    
## CSS フレームワークを使う  

**CSS フレームワーク** は、魅力的な web サイトを簡単に作成できる他の開発者によって構築されたスタイルのコレクションです。  独自のスタイルを定義する代わりに、フレームワークによって、ページ要素で使うことができるスタイルのコレクションが提供されます。  

1.  次のコードをコピーします。  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  [編集] タブに移動し、コードを貼り付け `contact.html` ます。  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="contact.html のフレームワークへのリンク" lightbox="../media/beginners-css-framework1.msft.png":::
       フレームワークへのリンク `contact.html`  
    :::image-end:::  
    
1.  ファイルを開き、 `index.html` そこにコードを追加します。  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="index.html のフレームワークへのリンク" lightbox="../media/beginners-css-framework2.msft.png":::
       フレームワークへのリンク `index.html`  
    :::image-end:::  
    
1.  [ライブ] タブに戻り、変更内容を確認します。  要素の背景色 `<nav>` と要素のフォントは同じであるのに、 `<li>` 他の `<a>` 要素のフォントが変更されています。  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="フレームワークによって変更されたホームページのフォントの一部" lightbox="../media/beginners-css-framework3.msft.png":::
       フレームワークによって変更されたホームページのフォントの一部  
    :::image-end:::  
    
### クラスを使用する  

最後のセクションでは、web ページにブートストラップを追加して、サイトの要素のフォントを変更しました。  CSS フレームワークを使うと、わずかなコードでページに大きな変更を加えることができます。  ヘッダーを変更するには、次の操作を実行します。  

1.  次のコードスニペットをコピーします。  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  前のコードスニペットをタグに追加 `<header>` `index.html` します。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="index.html でクラスを追加する" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       クラスを追加する `index.html`  
    :::image-end:::  
    
1.  タグにコードを追加 `<header>` `contact.html` します。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="contact.html でクラスを追加する" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       クラスを追加する `contact.html`  
    :::image-end:::  
    
1.  [ライブ] タブで変更内容を表示します。 ヘッダーの周りに大きな灰色のボックスがあります。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="ヘッダーの周りに大きな灰色のボックスがあるようになりました" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       ヘッダーの周りに大きな灰色のボックスがあるようになりました  
    :::image-end:::  
    
### クラスについて  

クラスを使うと、スタイルのコレクションを任意の要素に割り当てることができます。  属性を設定した後で要素にいくつかのスタイルを適用するには、次のコードスニペットを使用し `<header>` `class` `jumbotron` ます。  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

クラスの1つの利点は、目的の要素にスタイルを適用できることです。  たとえば、一部の要素の背景色を紫色に設定し、すべての要素では設定しないとし `<p>` `<p>` ます。  クラスでスタイルを定義するには、次のコードスニペットを使用します。  

```css
.custom-background {
  background-color: purple;
}
```  

次に、スタイルを適用する要素のみにクラスを適用し `<p>` ます。  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### 要素の配置  

ブートストラップに対して次の操作を実行し、要素を配置するためのクラスを提供します。  

1.  [エディター] タブに戻り、を開き `index.html` ます。  
1.  `class="container-fluid"`タグに追加 `<body>` します。  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="コンテナー-流体クラスを追加する" lightbox="../media/beginners-css-align1.msft.png":::
       クラスを追加する `container-fluid`  
    :::image-end:::  
    
1.  `<nav>`と `<main>` の要素を折り返し `<div class="row">` ます。  `</div>` `</main>` 新しいノートシールを正しく閉じるには、[指定の日時以降] をオンにしてください。  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="行を追加する" lightbox="../media/beginners-css-align2.msft.png":::
       行を追加する  
    :::image-end:::  
    
1.  `class="col-3"` `<nav>` タグとタグに追加 `class="col-9"` `<main>` します。  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="列3と列9のクラスを追加する" lightbox="../media/beginners-css-align3.msft.png":::
       `col-3`クラスとクラスを追加する `col-9`  
    :::image-end:::  
    
1.  [ライブ] タブで変更内容を表示します。  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="これで、ナビゲーションコンテンツがメインコンテンツの左になりました" lightbox="../media/beginners-css-align4.msft.png":::
       これで、ナビゲーションコンテンツがメインコンテンツの左になりました  
    :::image-end:::  
    
## 次のステップ  

おめでとうございます。これで完了です。  

*   Web 開発に適した方法は、さらに多くのサイトを構築することです。  問題を壊す心配はありません。  今まで以上に楽しく、できる限り学習しましょう。  
*   Web ページのスタイル設定の詳細については、「 [CSS の概要][MDNCssFirstSteps]」を参照してください。  
*   DevTools を使ってページの CSS を試す方法の詳細については、「 [css の表示と変更の概要][DevtoolsCssIndex]」を参照してください。  

<!--- image links --->  

[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "初心者向けの DevTools: HTML と DOM の使用を開始する |Microsoft ドキュメント"  
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html-クック-水陸両用機 |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS の最初のステップ |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/beginners/css) にあり、 [Katherine Jackson][KatherineJackson] \ (テクニカルライターインターン、Chrome devtools) によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
