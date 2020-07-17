---
title: '初心者向けの DevTools: CSS の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fba049a20a7b5f981130b4d9e60c37b07dc7e092
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882738"
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

これは、web 開発と Microsoft Edge DevTools の基礎について説明する一連のチュートリアルの2番目のチュートリアルです。  実際に自分の web サイトを構築することで、実践的なエクスペリエンスを実現できます。  この操作を行う前に、最初のチュートリアルを完了する必要はありません。  ここから開始できます。  [コードを設定](#set-up-your-code)すると、セットアップ方法が表示されます。  

> [!NOTE]
> このチュートリアルは、基本的な初心者向けに設計されており、 **web 開発の基礎**と、開発者向けの基本的なツールを使用した CSS の基本的な使い方に重点を置いています。  開発ツールにのみ重点を置いたチュートリアルが必要な場合は、「 [CSS の表示と変更の概要][DevtoolsCssIndex]」を参照してください。  

現在、サイトは次のように表示されます。  

> ##### 図 1  
> 現在のサイトの外観  
> ![現在のサイトの外観][ImageCssIntro1]  

チュートリアルを完了すると、次のようになります。  

> ##### 図 2  
> チュートリアルの最後にサイトがどのように表示されるか  
> ![チュートリアルの最後にサイトがどのように表示されるか][ImageCssIntro2]  

## 目標   

このチュートリアルを終了すると、次のことがわかります。  

*   CSS を使用して web ページのスタイルを適用する方法について説明します。  
*   Microsoft Edge DevTools を使って CSS を試す方法を説明します。  
*   CSS と CSS フレームワークの違い。  

実際の web サイトも用意されています。  

## 前提条件   

このチュートリアルを実行する前に、次の前提条件を完了してください。  

*   「 [Html と dom の概要][DevToolsBeginnersHtml]」をご覧になるか、このチュートリアルで説明していることと同じように HTML と dom を理解していることを確認してください。  
*   [Microsoft Edge][MicrosoftEdgeInsider] web ブラウザーをダウンロードします。  このチュートリアルでは、microsoft edge DevTools と呼ばれる web 開発ツールのセットを使用して、Microsoft Edge に組み込まれています。  

## コードを設定する   

サイトの作成を開始するには、コードを設定する必要があります。  

1.  **このシリーズの最初のチュートリアルを既に完了している場合は、このセクションをスキップしてください。  「 [HTML と DOM の使用を開始][DevToolsBeginnersHtml]する」のチュートリアルで説明したコードの使用を続けます。**  
1.  [ソースコード][GlitchCookedAmphibianIndex]を開きます。  ブラウザーのこのタブは、[**編集] タブ**と呼ばれます。  
    
    > ##### 図 3  
    > [編集] タブ  
    > ![[編集] タブ][ImageCssSetup1]  
    
1.  [**クック-水陸両用] を**クリックします。  メニューがポップアップ表示されます。  
    
    > ##### 図 4  
    > [プロジェクトのオプション] メニュー  
    > ![[プロジェクトのオプション] メニュー][ImageCssSetup2]  

1.  [ **Remix Project**] をクリックします。  エラー編集可能なプロジェクトのコピーを作成します。  
    
    > [!NOTE]
    > エラー新しいプロジェクトに対してランダムな名前を生成します。  
    
1.  [**表示**] をクリックして、**新しいウィンドウで**を選択します。  サイトのライブビューで別のタブが開きます。  ブラウザのこのタブは、「**ライブ」タブ**と呼ばれます。  
    
    > ##### 図 5  
    > [ライブ] タブ  
    > ![[ライブ] タブ][ImageCssSetup3]  

## CSS について   

**CSS**は、web ページのレイアウトとスタイルを決定するコンピューターの言語です。  たとえば、次のように罫線が付いた段落を次に示します。  

> ##### 図 6  
> CSS でスタイルが設定されています  
> ![CSS でスタイルが設定されています][ImageCssStyled]  

この段落を作成するために使用される HTML と CSS のコードは次のとおりです。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` おそらく、新しくなったようです。  その他の方法については、こちらをご覧ください。  表示されない場合は、このチュートリアルを実行する前に、「 [HTML と DOM での作業を開始][DevToolsBeginnersHtml]する」を完了してください。  

## インラインスタイルを追加する   

1つの要素にスタイルを適用する場合は、**インラインスタイル**を使います。  今すぐお試しください:  

1.  [編集] タブに戻り、[開く] をクリックし `index.html` ます。  
    
    > ##### 図 7  
    > `index.html`  
    > ![index.html][ImageCssInline1]  

1.  `style="background-color: aliceblue;"`にを追加 `<nav>` します。  以下のコードブロックでは、コードの4行目が変更する必要があるものです。  残りの部分は、新しいコードが適切な場所に配置されていることを確認できます。  
    
    ```html
    ...
        ...
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav style="background-color: aliceblue;">
                <ul>
                    <li><a href="/">Home</a></li>
                    ...
                ...
            ...
        ...
    ...
    ```  

1.  [**ライブ] タブ**に移動して変更を確認します。  セクションの背景 `<nav>` が青色になります。  
    
    > ##### 図 8  
    > ホームと連絡先のリンクの背景色が青になりました  
    > ![ホームと連絡先のリンクの背景色が青になりました][ImageCssInline2]  

## 内部のスタイルシートを使用して、1つのページでスタイルを再利用する   

以前は、次のような1つのタグにスタイルを適用したインラインスタイルが表示されていました `<p>` 。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`<p>`Web ページ上のすべての要素に同じようなスタイルを適用する必要がある場合はどうすればよいですか?  サイトのすべてのタグにコードをコピーして貼り付ける必要があり `<p>` ます。  これは多くの時間と労力を備えています。  編集を行う必要がある場合は、すべてのタグをもう一度変更する必要があります。  **内部のスタイルシート**を使用すると、複数の要素に適用されるように CSS を1回作成できます。  今すぐお試しください:  

1.  「ライブ」タブで「**コンタクト**」をクリックして、コンタクトページに移動します。  [**ホーム**] と [**連絡先**] のフォントを確認します。  
    
    > ##### 図 9  
    > [連絡先] ページ  
    > ![[連絡先] ページ][ImageCssInternal1]  

1.  [**エディター] タブ**で、に移動 `contact.html` します。  
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
    
1.  [**ライブ] タブ**に戻ります。  
1.  [**連絡先**] をクリックして、連絡先ページに戻ります。  [**ホーム**] と [**連絡先**] のフォントが変更されました。  
    
    > ##### 図 10  
    > 自宅と連絡先のリンクのフォントが変更されました  
    > ![自宅と連絡先のリンクのフォントが変更されました][ImageCssInternal2]  
    
### 内部のスタイルシートについて   

内部スタイルシートは**セレクター**を使ってスタイルを適用します。  セレクターは、1つ以上の HTML 要素に適用される可能性があるパターンです。  たとえば、上記のコードでは、次のようにします。  

```html
...
    ...
        ...
        <style>
            li a {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

`li a` は、"any を含む any" に変換するセレクターです `<li>` `<a>` 。  [**ホーム**] と [**連絡先**] のリンクは、このパターンと一致するため、ブラウザーによって変更されます。  

```html
...
    ...
        ...
            ...
                <li><a href="/">Home</a></li>
                <li><a href="/contact.html">Contact</a></li>
                ...
            ...
        ...
    ...
...
```  

`font-family: 'Courier New', Courier, serif` は**宣言**です。  宣言は、**プロパティ**と**値**の2つの部分で構成されます。  `font-family` はプロパティであり、 `'Courier New', Courier, serif` そのプロパティの値です。  このプロパティでは、要素のスタイルを変更する一般的な方法について説明します。値は、どのように変化するかを示します。  たとえば、次のような指示が表示されます。 `font-family: 'Courier New', Courier, serif` "パターンと一致する要素のフォント `li a` を設定 `'Courier New'` します。  そのフォントが利用できない場合は、を使用 `Courier` します。  利用できない場合は、 `serif` 「」を使用してください。  

### 複数のセレクターをルールセットに追加する   

以下に示すような CSS コードのブロックは、**ルールセット**と呼ばれています。  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

コンマを使用して、複数のセレクターをルールセットに追加します。  今すぐお試しください:  

1.  [**エディター] タブ**で、を開き `contact.html` ます。  
1.  `li a`種類 `, h1` の後。  

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

    これにより、ブラウザーは、 `<h1>` パターンと一致する要素のスタイルを適用する場合と同じ方法で要素のスタイルを適用し `li a` ます。  
    
1.  [**ライブ] タブ**に移動します。  
1.  **連絡先のリンクを**クリックして、連絡先ページに戻ります。  今すぐ**連絡してください。** ナビゲーションリンクと同じフォントに設定されています。  
    
    > ##### 図 11  
    > 「連絡してください」というテキスト 自宅と連絡先のリンクと同じフォントになりました  
    > ![「連絡」というテキストが表示されます。  自宅と連絡先のリンクと同じフォントになりました][ImageCssMultiple1]  

## DevTools を使って実験する   

引き続きマスタ web 開発に進んでいくと、CSS が複雑になる可能性があることがわかります。  CSS を作成し、1つの方法で表示することを想定していますが、ブラウザーではまったく異なるものがあります。  Microsoft Edge DevTools を使うと、簡単に変更を試すことができ、それらの変更がページにどのように影響するかをすぐに確認できます。  

### DevTools で既存の rulest に宣言を追加する   

既存の要素のスタイルに対して反復処理を行う場合は、既存のルールセットに宣言を追加します。  今すぐお試しください:  

1.  [**ホーム**] リンクを右クリックし、[**検査**] を選択します。  
    
    > ##### 図 12  
    > [ホーム] リンクを調べる  
    > ![[ホーム] リンクを調べる][ImageCssAdd1]  
    
    DevTools はページの横に表示されます。  [ホーム] リンクを表すコード `<a href="/">Home</a>` は、DOM ツリーで青色で強調表示されています。  これは[、「HTML と DOM の使用を開始][DevToolsBeginnersHtml]する」に精通している必要があります。  DOM ツリーの下にある [**スタイル**] タブには、 `font-family: 'Courier New', Courier, serif` 前に追加した宣言が表示され `contact.html` ます。  
    
    > ##### 図 13  
    > [スタイル] タブが DOM ツリーの下にある  
    > ![[スタイル] タブが DOM ツリーの下にある][ImageCssAdd2]  
    
    DevTools ウィンドウが広くなっている場合、[スタイル] タブは DOM ツリーの右側にあります。  
    
    > ##### 図 14  
    > [スタイル] タブは DOM ツリーの右側にあります。  
    > ![[スタイル] タブは DOM ツリーの右側にあります。][ImageCssAdd3]  
    
1.  新しい宣言を追加するには、下の空白をクリックし `font-family: 'Courier New', Courier, Serif` ます。  
    
    > ##### 図 15  
    > 新しい宣言を追加する  
    > ![新しい宣言を追加する][ImageCssAdd4]  
    
1.  入力 `color` して、キーを押し `Enter` ます。  入力時にオートコンプリート UI によってオプションが提示されます。  
    
    > ##### 図 16  
    > 入力 `color`  
    > ![入力時の色][ImageCssAdd5]  

1.  入力 `magenta` して、 `Enter` もう一度押します。  連絡先ページのすべてのテキストがマジェンタ色になりました。  
    
    > ##### 図 17  
    > 入力 `magenta`  
    > ![マゼンタの入力][ImageCssAdd6]  
    
### DevTools で宣言を編集する   

また、DevTools で既存の宣言を編集することもできます。  今すぐお試しください:  

1.  の横にあるマゼンタの正方形をクリックし `magenta` ます。  カラーピッカーがポップアップ表示されます。  
    
    > ##### 図18  
    > 色のパレット  
    > ![色のパレット][ImageCssEdit1]  
    
1.  カラーピッカーを使用して、フォントのテキストを好みの色に変更します。  
    
    > ##### 図19  
    > カラーピッカーを使用してフォントの色を紫色に変更する  
    > ![カラーピッカーを使用してフォントの色を紫色に変更する][ImageCssEdit2]  

### DevTools で新しいルールセットを追加する   

DevTools で新しいルールセットを追加することもできます。  今すぐお試しください:  

1.  [**新しいスタイルルール**] をクリックし ![ ][ImageNewStyleRuleIcon] **ます。** これは、cls の横にあります。  空のルールセットが `a` セレクターとして表示されます。  
    
    > ##### 図20  
    > 新しいルールを追加する  
    > ![新しいルールを追加する][ImageCssRule1]  
    
1.  置換後 `a` の文字列 `a:hover`  
    
    > ##### 図21  
    > 置換 `a` `a:hover`  
    > ![A を @ に置換する][ImageCssRule2]  
    
    `:hover` は**擬似クラス**です。  疑似クラスを使って、特殊な状態を入力するときに要素のスタイルを指定します。  たとえば、スタイルは、 `a:hover` 要素の上にマウスポインターを置いた場合にのみ有効になり `<a>` ます。  
    
1.  かっこの間をクリックして新しい宣言を追加します。  
1.  `background-color`宣言の名前を入力し、enter キーを押し `Enter` ます。  
    
    > ##### 図22  
    > 入力 `background-color`  
    > ![背景色の入力][ImageCssRule3]  
    
1.  `green`宣言の値を入力して、キーを押し `Enter` ます。  
    
    > ##### 図23  
    > 入力 `green`  
    > ![緑の入力][ImageCssRule4]  
    
1.  [**ホーム**] リンクの上にマウスポインターを置きます。  リンクの背景が緑色になります。  
    
    > ##### 図24  
    > ホームリンク上にマウスポインターを移動すると、緑色の背景が表示される  
    > ![ホームリンク上にマウスポインターを移動すると、緑色の背景が表示される][ImageCssRule5]  
    
## 外部のスタイルシートを含むページ間でスタイルを再利用する   

以前のバージョンでは、次のような内部スタイルシートが追加されました `contact.html` 。  

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

同じ方法でスタイルを適用する場合は、どうすればよい `index.html` ですか。  *数千個*のページがあって、それらすべてにそれらのスタイルを適用したい場合はどうすればよいですか?  この内部スタイルシートをコピーして、サイトのすべての web ページに貼り付ける必要があります。  **外部のスタイルシート**を使用すると、CSS を複数のページに適用することができます。  今すぐお試しください:  

1.  まず、[ライブ] タブをもう一度読み込んで、DevTools で行った変更を削除します。  
    
    > ##### 図25  
    >  ページを再読み込みした後、DevTools で行った変更は廃止されました  
    > ![ ページを再読み込みした後、DevTools で行った変更は廃止されました][ImageCssExternal01]  
    
1.  [**エディター] タブ**に戻り、を開き `contact.html` ます。  
    
    > ##### 図26  
    > `contact.html`  
    > ![contact.html][ImageCssExternal02]  
    
1.  およびを `<style>` `</style>` 含む、and を含むすべてのデータを削除し `<style>` `</style>` ます。  
    
    > ##### 図27  
    > スタイルタグが削除されました  
    > ![スタイルタグが削除されました][ImageCssExternal03]  
    
1.  `index.html`タグから移動して削除し `style="background-color: aliceblue;"` `<nav>` ます。  これで、以前にサイトに追加した CSS がすべて削除されました。  
    
    > ##### 図28  
    > インラインスタイルが nav 要素から削除されている  
    > ![インラインスタイルが nav 要素から削除されている][ImageCssExternal04]  

1.  [**新しいファイル**] をクリックします。  
    
    > ##### 図29  
    > [新しいファイル] ダイアログ  
    > ![[新しいファイル] ダイアログ][ImageCssExternal05]  
    
1.  置換 `cool-file.js` `style.css` 後、[**ファイルの追加**] をクリックします。  
    
    > ##### 図30  
    > 入力 `style.css`  
    > ![入力スタイル .css][ImageCssExternal06]  
    
1.  次のコードに貼り付け `style.css` ます。  
    
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
    
    > ##### 図31  
    > コードの追加 `style.css`  
    > ![スタイル .css へのコードの追加][ImageCssExternal07]  
    
    この時点では、外部のスタイルシートを作成しましたが、HTML ではまだ存在していることがわかりません。  
    
1.  [開く] `index.html` を選びます。  
1.  `<link rel="stylesheet" href="style.css">`HTML に追加します。  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <link rel="stylesheet" href="style.css">
        </head>
        ...
    ...
    ```  

    > ##### 図32  
    > リンク先 `style.css`  
    > ![スタイル .css へのリンク][ImageCssExternal08]  

1.  リンクも `contact.html` そこに移動して追加します。  
    
    > ##### 図33  
    > リンク先 `style.css` `contact.html`  
    > ![contact.html のスタイル .css へのリンク][ImageCssExternal09]  

1.  [**ライブ] タブ**に移動します。 これで、ホームページの最後のセクションと青色のナビゲーションセクションのフォントが変わりました。  
    
    > ##### 図34  
    > ホームページ  
    > ![ホームページ][ImageCssExternal10]  
    
1.  **連絡先**のリンクをクリックして、連絡先ページに移動します。  連絡先ページは、ホームページと同じ書式設定になっています。  
    
    > ##### 図35  
    > [連絡先] ページ  
    > ![[連絡先] ページ][ImageCssExternal11]  
    
## CSS フレームワークを使う   

**CSS フレームワーク**は、魅力的な web サイトを簡単に作成できる他の開発者によって構築されたスタイルのコレクションです。  独自のスタイルを定義する代わりに、フレームワークによって、ページ要素で使うことができるスタイルのコレクションを提供します。  

1.  次のコードをコピーします。  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  [編集] タブに移動し、コードを貼り付け `contact.html` ます。  
    
    > ##### 図36  
    > フレームワークへのリンク `contact.html`  
    > ![contact.html でのフレームワークへのリンク][ImageCssFramework1]  
    
1.  同様にコードを貼り付け `index.html` ます。  
    
    > ##### 図37  
    > フレームワークへのリンク `index.html`  
    > ![index.html でのフレームワークへのリンク][ImageCssFramework2]  
    
1.  [ライブ] タブに戻り、変更内容を確認します。  要素の背景色とフォントが同じであるのに、 `<nav>` `li a` 他の要素のフォントが変更されています。  
    
    > ##### 図38  
    > フレームワークによってホームページの一部のフォントが変更されている  
    > ![フレームワークによってホームページの一部のフォントが変更されている][ImageCssFramework3]  

### クラスを使用する   

最後のセクションでは、web ページにブートストラップを追加して、サイトの要素のフォントを変更しました。  CSS フレームワークを使うと、非常にわずかなコードでページに大きな変更を加えることができます。  ヘッダーを変更して、今すぐ試してみてください。  

1.  次のコードをコピーします。  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  このコードを `<header>` のタグに追加 `index.html` します。  
    
    > ##### 図39  
    > クラスの追加 `index.html`  
    > ![index.html でのクラスの追加][ImageCssJumbotron1]  
    
1.  コードを `<header>` タグに `contact.html` も追加します。  
    
    > ##### 図40  
    > クラスの追加 `contact.html`  
    > ![contact.html でのクラスの追加][ImageCssJumbotron2]  
    
1.  [ライブ] タブで変更内容を表示します。 ここでは、ヘッダーの周りに大きな灰色のボックスが表示されています。  
    
    > ##### 図41  
    > ヘッダーの周りに大きな灰色のボックスがあるようになりました  
    > ![ヘッダーの周りに大きな灰色のボックスがあるようになりました][ImageCssJumbotron3]  
    
### クラスについて   

クラスを使うと、スタイルのコレクションを任意の要素に割り当てることができます。  たとえば、 `class` `<header>` 次の `jumbotron` スタイルが適用されるようにタグの属性を設定します。  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

クラスの利点の1つは、目的の要素にスタイルを適用できることです。  たとえば、*一部*の要素の背景色を紫色に設定し、そのすべてではない場合を考え `<p>` ます。 *all*  クラスでスタイルを定義することができます。  

```css
.custom-background {
  background-color: purple;
}
```  

次に、スタイルを適用する要素のみにクラスを適用し `<p>` ます。  

```html
...
    ...
        ...
        <p>This won't be purple.</p>
        <p class="custom-background">This will be purple.</p>
        <p>This won't be purple.</p>
        <p class="custom-background">This will be purple.</p>
        ...
    ...
...
```  

### 要素の配置   

また、ブートストラップには要素を配置するためのクラスも用意されています。  今すぐお試しください:  

1.  [エディター] タブに戻り、を開き `index.html` ます。  
1.  `class="container-fluid"`タグに追加 `<body>` します。  
    
    > ##### 図42  
    > クラスの追加 `container-fluid`  
    > ![コンテナー-流体クラスの追加][ImageCssAlign1]  

1.  `<nav>`と `<main>` の要素を折り返し `<div class="row">` ます。  `</div>` `</main>` 新しいノートシールを正しく閉じるには、[指定の日時以降] をオンにしてください。  
    
    > ##### 図43  
    > 行の追加  
    > ![行の追加][ImageCssAlign2]  
    
1.  `class="col-3"` `<nav>` タグとタグに追加 `class="col-9"` `<main>` します。  
    
    > ##### 図44  
    > `col-3`クラスを追加 `col-9` する  
    > ![列3と列9のクラスを追加する][ImageCssAlign3]  
    
1.  [ライブ] タブで変更内容を表示します。  
    
    > ##### 図45  
    > これで、ナビゲーションコンテンツがメインコンテンツの左になりました  
    > ![これで、ナビゲーションコンテンツがメインコンテンツの左になりました][ImageCssAlign4]  
    
## 次のステップ   

お疲れさまでした。  これで完了です。  

*   Web 開発に適した方法は、さらに多くのサイトを構築することです。  問題を壊す心配は無用です。  今まで以上に便利な機能をご利用いただけます。  
*   Web ページのスタイル設定の詳細については、「 [CSS の概要][MDNCssFirstSteps]」をご覧ください。  
*   「CSS の[表示と変更の概要」チュートリアルの概要][DevtoolsCssIndex]については、「devtools を使ってページの css を試す方法」を参照してください。  

<!--- image links --->  

[ImageNewStyleRuleIcon]: /microsoft-edge/devtools-guide-chromium/media/new-style-rule-icon.msft.png  

[ImageCssIntro1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-intro1.msft.png "図 1: サイトが現在どのように見えるか"  
[ImageCssIntro2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-intro2.msft.png "図 2: チュートリアルの最後にサイトがどのように表示されるか"  
[ImageCssSetup1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup1.msft.png "図 3: [編集] タブ"  
[ImageCssSetup2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup2.msft.png "図 4: [プロジェクトのオプション] メニュー"  
[ImageCssSetup3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup3.msft.png "図 5: [ライブ] タブ"  
[ImageCssStyled]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-red_paragraph.msft.png "図 6: CSS でスタイルが適用されている"  
[ImageCssInline1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-inline1.msft.png "図 7: index.html"  
[ImageCssInline2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-inline2.msft.png "図 8: ホームと連絡先のリンクの背景色が青になりました"  
[ImageCssInternal1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-internal1.msft.png "図 9: 連絡先ページ"  
[ImageCssInternal2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-internal2.msft.png "図 10: ホームと連絡先のリンクのフォントが変更されている"  
[ImageCssMultiple1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-multiple1.msft.png "図 11: "連絡先" というテキストは、[ホーム] と [連絡先] のリンクと同じフォントになりました"  
[ImageCssAdd1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add1.msft.png "図 12: ホームリンクを調べる"  
[ImageCssAdd2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add2.msft.png "図 13: [スタイル] タブが DOM ツリーの下にある"  
[ImageCssAdd3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add3.msft.png "図 14: [スタイル] タブは DOM ツリーの右にあります。"  
[ImageCssAdd4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add4.msft.png "図 15: 新しい宣言を追加する"
[ImageCssAdd5]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add5.msft.png "図 16: 色を入力する"  
[ImageCssAdd6]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add6.msft.png "図 17: マゼンタを入力する"  
[ImageCssEdit1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-edit1.msft.png "図 18: 色のパレット"  
[ImageCssEdit2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-edit2.msft.png "図 19: カラーピッカーを使用してフォントの色を紫色に変更する"  
[ImageCssRule1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule1.msft.png "図 20: 新しいルールを追加する"  
[ImageCssRule2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule2.msft.png "図 21: a を「a」に置き換える"  
[ImageCssRule3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule3.msft.png "図 22: 背景色を入力する"  
[ImageCssRule4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule4.msft.png "図 23: 緑で入力する"  
[ImageCssRule5]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule5.msft.png "図 24: ホームリンクをポイントして、緑色の背景を表示する"  
[ImageCssExternal01]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external1.msft.png "図 25: ページを再読み込みした後に、DevTools で行った変更が廃止される"  
[ImageCssExternal02]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external2.msft.png "図 26: contact.html"  
[ImageCssExternal03]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external3.msft.png "図 27: スタイルタグが削除されている"  
[ImageCssExternal04]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external4.msft.png "図 28: インラインスタイルが nav 要素から削除されている"  
[ImageCssExternal05]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external5.msft.png "図 29: [新しいファイル] ダイアログボックス"  
[ImageCssExternal06]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external6.msft.png "図 30: css の入力"  
[ImageCssExternal07]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external7.msft.png "図 31: スタイルにコードを追加する"  
[ImageCssExternal08]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external8.msft.png "図 32: スタイル .css へのリンク"  
[ImageCssExternal09]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external9.msft.png "図 33: contact.html のスタイル .css へのリンク"  
[ImageCssExternal10]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external10.msft.png "図 34: ホームページ"  
[ImageCssExternal11]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external11.msft.png "図 35: 連絡先ページ"  
[ImageCssFramework1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework1.msft.png "図 36: contact.html でのフレームワークへのリンク"  
[ImageCssFramework2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework2.msft.png "図 37: index.html でのフレームワークへのリンク"  
[ImageCssFramework3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework3.msft.png "図 38: フレームワークによってホームページの一部のフォントが変更されている"  
[ImageCssJumbotron1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron1.msft.png "図 39: index.html でのクラスの追加"  
[ImageCssJumbotron2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron2.msft.png "図 40: contact.html でのクラスの追加"  
[ImageCssJumbotron3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron3.msft.png "図 41: ヘッダーの周りに大きな灰色のボックスがある"  
[ImageCssAlign1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align1.msft.png "図 42: コンテナーの流体クラスを追加する"  
[ImageCssAlign2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align2.msft.png "図 43: 行を追加する"  
[ImageCssAlign3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align3.msft.png "図 44: 列3と列9のクラスを追加する"  
[ImageCssAlign4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align4.msft.png "図 45: ナビゲーションコンテンツがメインコンテンツの左側にある"  

<!--- links  --->  

[DevToolsBeginnersHtml]: html.md "初心者向けの DevTools: HTML と DOM の使用を開始する"  
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更を始める"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html-クック-水陸両用機 |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS の最初のステップ |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/beginners/css)にあり、 [Katherine Jackson][KatherineJackson] \ (テクニカルライターインターン、Chrome devtools) によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
