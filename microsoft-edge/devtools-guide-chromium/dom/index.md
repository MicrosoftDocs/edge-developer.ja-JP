---
title: DOM の表示と変更を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4dee8b4e3ea927e72c0f98517f264b2c1d453013
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607448"
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





# DOM の表示と変更を開始する   



Microsoft Edge DevTools を使用して、ページの DOM を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。  

このチュートリアルでは、DOM と HTML の違いを知っていることを前提としています。  説明については[、「付録: HTML と DOM の比較](#appendix-html-versus-the-dom)」を参照してください。  

## DOM の例を開く  

1.  `Control`\ (Windows \) または `Command` \ (macOS \) を保持し、[ **DOM の例**] をクリックして新しいタブで開きます。  
    
    [DOM の例][GlitchDomExamples]  
    
## DOM ノードの表示   

[要素] パネルの DOM ツリーでは、DevTools で DOM に関連するすべてのアクティビティを行うことができます。  

### ノードを検査する   

特定の DOM ノードに関心がある場合は、[**検査**] を使うと、devtools をすばやく開いてそのノードを調べることができます。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**ノードの検査**] で、[ **Michelangelo** ] を右クリックし、[**検査**] を選択します。  
    
    > ##### 図 1  
    > ノードを検査する  
    > ![ノードを検査する][ImageInspectingNode]  
    
    1.  DevTools の [**要素**] パネルが開きます。  `<li>Michelangelo</li>` が強調表示さ**れてい**ます。  
        
        > ##### 図 2  
        > Michelangelo ノードの強調表示  
        > ![Michelangelo ノードの強調表示][ImageHighlightingMichelangeloNode]  
        
        1.  **Inspect** ![ ][ImageInspectIcon] Devtools の左上隅にある検査検査アイコンをクリックします。  
            
            > ##### 図 3  
            > [検査] アイコン  
            > ![[検査] アイコン][ImageInspect]  
            
1.  [**ノードの検査**] で、[**東京**] のテキストをクリックします。  これで、 `<li>Tokyo</li>` DOM ツリーで強調表示されるようになりました。  

ノードの [検査] は、ノードのスタイルを表示して変更するための最初の手順でもあります。  「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCssGetStarted]参照してください。  

### キーボードで DOM ツリー内を移動する   

DOM ツリーでノードを選択すると、DOM ツリーをキーボードで移動できます。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **DOM ツリーのキーボードでの操作**] で、[ **Ringo** ] を右クリックし、[**検査**] を選びます。  `<li>Ringo</li>` が選択されます。  
    
    > ##### 図 4  
    > Ringo ノードの検査  
    > ![Ringo ノードの検査][ImageInspectingRingoNode]  
    
    1.  `Up`方向キーを2回押します。  `<ul>`  がオンになっていることを確認します。  
        
        > ##### 図 5  
        > Ul ノードの検査  
        > ![Ul ノードの検査][ImageInspectingUlNode]  
        
    1.  `Left`方向キーを押します。  `<ul>`リストが折りたたまれます。  
    1.  `Left`もう一度方向キーを押します。  ノードの親 `<ul>` が選択されます。  この場合は、 `<div>` ID を使用し `navigate-the-dom-tree-with-a-keyboard-1` ます。  
    1.  `Down`方向キーを2回押して、折りたたんだリストをもう一度選択し `<ul>` ます。  次のようになります。 `<ul>... </ul>`  
    1.  `Right`方向キーを押します。  リストが拡張されます。  

### スクロールして表示する   

DOM ツリーを表示しているときに、現在ビューポート内にない DOM ノードに興味を持っていることがあります。  たとえば、ページの一番下までスクロールして、ページの上部にあるノードに関心を持っているとし `<h1>` ます。  **ビューをスクロール**すると、ビューポートをすばやく移動して、ノードを表示できます。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**スクロール**して表示] で、[ **Magritte** ] を右クリックし、[**検査**] を選択します。  
1.  DOM の [例] ページの一番下までスクロールします。  
1.  `<li>Magritte</li>`それでも、ノードは DOM ツリーで選択されます。  表示されていない場合は、戻って、もう一度[表示](#scroll-into-view)してみてください。  
1.  ノードを右クリックし `<li>Magritte</li>` て、[**ビューにスクロール**] を選択します。  ビューポートがスクロールして、 **Magritte**ノードが表示されることがあります。  [スクロールして**表示**する] オプションが表示されない場合は、「[付録: オプションが見つから](#appendix-missing-options)ない」を参照してください。
    
    > ##### 図 6  
    > スクロールして表示する  
    > ![スクロールして表示する][ImageScrollView]  

### ノードを検索する   

DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。  

1.  カーソルを [**要素**] パネルにフォーカスします。  
1.  `Control` + `F` \ (Windows \) または `Command` + `F` \ (macOS \) を押します。  検索バーは DOM ツリーの下部に表示されます。  
1.  「`The Moon is a Harsh Mistress`」と入力します。  DOM ツリーの最後の文が強調表示されています。  
    
    > ##### 図 7  
    > 検索バーでクエリを強調表示する  
    > ![検索バーでクエリを強調表示する][ImageHighlightingQuerySearchBar]  
    
上で説明したように、検索バーは CSS と XPath のセレクターもサポートしています。  

## DOM を編集する   

その場で DOM を編集して、それらの変更がページにどのように影響するかを確認できます。  

### コンテンツを編集する   

ノードのコンテンツを編集するには、DOM ツリーでコンテンツをダブルクリックします。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**コンテンツの編集**] で [ **micん le** ] を右クリックし、[**検査**] を選びます。  
    1.  DOM ツリーで、をダブルクリック `Michelle` します。  つまり、との間のテキストをダブルクリック `<li>` し `</li>` ます。  テキストが強調表示され、選択されていることが示されます。  
        
        > ##### 図 8  
        > テキストを編集する  
        > ![テキストを編集する][ImageEditingText]  
        
    1.  を削除し `Michelle` て入力し、 `Leela` enter キーを押して `Enter` 変更を確定します。  DOM 内のテキストは、 **MicLeela le**から**Leela**に変更されます。  

### 属性を編集する   

属性を編集するには、属性の名前または値をダブルクリックします。  手順に従って、ノードに属性を追加する方法について説明します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**属性の編集**] で、[ **Howard** ] を右クリックし、[**検査**] を選択します。  

1.  ダブルクリック `<li>` します。  テキストが強調表示され、ノードが選択されていることが示されます。  
    
    > ##### 図 9  
    > ノードを編集する  
    > ![ノードを編集する][ImageEditingNode]  
    
1.  方向キーを押して、スペースを追加し、 `Right` 「」と入力して `style="background-color:gold"` 、キーを押し `Enter` ます。  ノードの背景色が金色に変わります。  
    
    > ##### 図 10  
    > ノードへのスタイル属性の追加  
    > ![ノードへのスタイル属性の追加][ImageAddingStyleAttributeNode]  
    
### ノードの種類を編集する   

ノードの種類を編集するには、型をダブルクリックし、新しい型を入力します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**ノードの種類の編集**] で、[ **Hank** ] を右クリックし、[**検査**] を選択します。  
    1.  ダブルクリック `<li>` します。  テキスト `li` が強調表示されます。  
    1.  を削除し `li` て、を入力し `button` `Enter` ます。  `<li>`ノードがノードに変わり `<button>` ます。  
        
        > ##### 図 11  
        > [ノードの種類の変更] ボタン  
        > ![[ノードの種類の変更] ボタン][ImageChangingNodeButton]  
        
### DOM ノードの順序を変更する   

ノードをドラッグして順序を変更します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **DOM ノードの順序**変更] で、[ **Elvis Presley** ] を右クリックし、[**検査**] を選びます。  
    
    > [!NOTE]
    > これは、リスト内の最後のアイテムです。  
    
    1.  DOM ツリーで、 `<li>Elvis Presley</li>` 一覧の一番上までドラッグします。  
        
        > ##### 図 12  
        > ノードを一覧の一番上にドラッグする  
        > ![ノードを一覧の一番上にドラッグする][ImageDraggingNodeTopList]  
        
### 強制状態   

ノードは、、、、、などの状態に保つことができ `:active` `:hover` `:focus` `:visited` `:focus-within` ます。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**状態の強制**] で、**その中の閣下**をポイントします。  背景色がオレンジ色になります。  
    1.  **フライの閣下**を右クリックして、[**検査**] を選びます。  
    1.  右クリック `<li class="demo--hover">The Lord of the Flies</li>` し、[**状態の強制**  >  **: hover**] を選びます。  このオプションが表示されない場合は、「[付録: オプション](#appendix-missing-options)を表示しない」を参照してください。  実際には、ノードの上にカーソルを置いていない場合でも、背景色はオレンジにとどまります。  

### ノードを非表示にする   

を押すと `H` 、ノードが非表示になります。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**ノードを非表示にする**] で、[**宛先] の星**を右クリックし、[**検査**] を選択します。  
    1.  キーを押し `H` ます。  ノードが非表示になっています。  
        
        > ##### 図 13  
        > 非表示になった後のノードが DOM ツリーのどのように見えるか  
        > ![非表示になった後のノードが DOM ツリーのどのように見えるか][ImageNodeDomTreeAfterHidden]  
        
    1.  キーを `H` もう一度押します。  ノードが再び表示されます。  

### ノードを削除する   

を押して `Delete` ノードを削除します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**ノードの削除**] で、[ **Foundation** ] を右クリックし、[**検査**] を選択します。  
    1.  キーを押し `Delete` ます。  ノードが削除されます。  
    1.  `Control` + `Z` \ (Windows \) または `Command` + `Z` \ (macOS \) を押します。  直前の操作が取り消され、ノードが再び表示されます。  

## コンソールのアクセスノード   

DevTools では、コンソールから DOM ノードにアクセスしたり、各デバイスへの JavaScript 参照を取得したりするためのショートカットキーをいくつか用意しています。  

### $0 で現在選択されているノードを参照する   

ノードを検査すると、 `== $0` ノードの横のテキストは、この変数を持つ本体でこのノードを参照できることを意味 `$0` します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **$0 で現在選択さ**れているノードを参照する] で、**暗さの左側**を右クリックして [**検査**] を選びます。  
    1.  キーを押して、 `Escape` 本体の引き出しを開きます。  
    1.  キーを入力 `$0` して、キーを押し `Enter` ます。  この式の結果は、の `$0` 評価を示して `<li>The Left Hand of Darkness</li>` います。  
        
        > ##### 図 14  
        > 本体の最初の式の結果 `$0`  
        > ![本体の最初の $0 式の結果][ImageFirstConsole]  
        
    1.  結果にマウスポインターを合わせます。  ビューポートで、ノードが強調表示されています。  
    1.  `<li>Dune</li>`DOM ツリー内をクリックし、 `$0` コンソールをもう一度入力して、 `Enter` もう一度押します。  次に、の `$0` ようにに評価さ `<li>Dune</li>` れます。  
        
        > ##### 図 15  
        > 本体の2番目の式の結果、本体の2番目の `$0` $0 式の結果が返されます。 ![][ImageSecondConsole]  
        
### グローバル変数として保存する   

何度もノードを参照する必要がある場合は、それをグローバル変数として保存します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**グローバル変数として保存**] で、**大きなスリープ状態**を右クリックし、[**検査**] を選択します。  
    1.  DOM ツリーを右クリック `<li>The Big Sleep</li>` して、[**グローバル変数として保存**] を選びます。  このオプションが表示されない場合は、「[付録: オプション](#appendix-missing-options)を表示しない」を参照してください。  
    1.  `temp1`コンソールに入力して、キーを押し `Enter` ます。  この式の結果は、変数がノードに評価されることを示します。  
        
        > ##### 図 16  
        > Temp1 式の結果  
        > ![Temp1 式の結果][ImageResultTemp1]  
        
### JS パスをコピーする   

自動テストで参照する必要がある場合は、JavaScript のパスをノードにコピーします。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **JS パスのコピー**] で、**兄弟 Karamazov**を右クリックして [**検査**] を選びます。  
    1.  DOM ツリーを右クリック `<li>The Brothers Karamazov</li>` して、[ **Copy**  >  **コピーコピー JS Path**] を選びます。  `document.querySelector()`ノードに解決される式がクリップボードにコピーされました。  
    1.  `Control` + `V` 式をコンソールに貼り付けるには、\ (Windows \) または `Command` + `V` \ (macOS \) を押します。  
    1.  を押して `Enter` 式を評価します。
        
        > ##### 図 17  
        > JS パスの式をコピーした結果  
        > ![JS パスの式をコピーした結果][ImageResultCopyJSPath]  
        
## DOM の中断の変更   

DevTools を使うと、JavaScript が DOM を変更したときにページの JavaScript を一時停止することができます。  

### 属性の変更の中断   

ノードの任意の属性を変更する JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**属性の変更を中断**] で、[ **Sauerkraut** ] を右クリックし、[**検査**] を選びます。  
    1.  DOM ツリーで右クリック `<li id="target">Sauerkraut</li>` し、[属性**の変更を中断**] を選択し  >  **Attribute Modifications**ます。  このオプションが表示されない場合は、「[付録: 省略](#appendix-missing-options)可能なオプション」を参照してください。
        
        > ##### 図18  
        > 属性の変更の中断  
        > ![属性の変更の中断][ImageBreakAttributeModification]  
        
    1.  次の手順では、ページのコードを一時停止するボタンをクリックするように指示されます。  ページが一時停止されると、ページをスクロールすることはできなくなります。  **Resume Script** ![ ][ImageResumeScriptIcon] ページを再び表示できるようにするには、[スクリプト再開スクリプトの再開] をクリックする必要があります。
        
        > ##### 図19  
        > スクリプトの実行を再開する場所  
        > ![スクリプトの実行を再開する場所][ImageResumeScript]  
        
    1.  上の [**背景の設定**] をクリックします。  これにより `style` 、ノードの属性がに設定され `background-color:thistle` ます。  DevTools はページを一時停止し、属性が変更されたコードを強調表示します。  
    1.  **Resume Script** ![ ][ImageResumeScriptIcon] 前に説明したように、[スクリプト再開スクリプト] をクリックします。  
    
### ノード削除時の中断   

特定のノードが削除されたときに一時停止する場合は、ノード削除のブレークポイントを使用します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**ノード削除時の中断**] で、[ **Neuromancer** ] を右クリックし、[**検査**] を選びます。  
    1.  DOM ツリーで右クリック `<li id="target">Neuromancer</li>` し、[ノード**の削除時に中断**] を選択し  >  **Node Removal**ます。  このオプションが表示されない場合は、「[付録: 省略](#appendix-missing-options)可能なオプション」を参照してください。  
    1.  上の [**削除**] ボタンをクリックします。  DevTools はページを一時停止し、ノードの削除を引き起こしたコードを強調表示します。  
    1.  [**スクリプト** ![ 再開スクリプトの再開] をクリックし ][ImageResumeScriptIcon] ます。  
    
### サブツリーの変更の中断   

ノードにサブツリーの変更のブレークポイントを配置すると、ノードの子孫が追加または削除されると、DevTools によってページが一時停止します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [**サブツリーの変更の中断**] で、[**詳細] の炎**を右クリックして [**検査**] を選びます。  
    1.  DOM ツリーで、上のノードである右クリック `<ul id="target">` `<li>A Fire Upon the Deep</li>` し、[サブツリーの変更を**中断**] を選択し  >  **Subtree Modifications**ます。  このオプションが表示されない場合は、「[付録: 省略](#appendix-missing-options)可能なオプション」を参照してください。  
    1.  [**子の追加**] をクリックします。  ノードがリストに追加されたため、コードは一時停止し `<li>` ます。  
    1.  [**スクリプト** ![ 再開スクリプトの再開] をクリックし ][ImageResumeScriptIcon] ます。  
    
## 次のステップ   

これは、DevTools の DOM 関連のほとんどの機能について説明しています。  残りの部分については、DOM ツリーのノードを右クリックし、このチュートリアルで説明していないその他のオプションを試してみることができます。  「[要素パネルのショートカットキー][DevToolsShortcutsElements]」もご覧ください。  

[Microsoft Edge DevTools のホームページ][MicrosoftEdgeDevTools]をチェックして、devtools で実行できるその他の情報をすべて見つけてください。  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  



## 付録: HTML と DOM の比較   

このセクションでは、HTML と DOM の違いについて簡単に説明します。  

Web ブラウザーを使ってページを要求すると、サーバーは次のような HTML を返します。  

```html
<!doctype html>
<html>
  <head>
    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>
    <p>This is a hypertext document on the World Wide Web.</p>
    <script src="/script.js" async></script>
  </body>
</html>
```  

ブラウザーは HTML を解析し、次のようなオブジェクトのツリーを作成します。  

```dom
html
  head
    title
  body
    h1
    p
    script
```  

ページのコンテンツを表す、このオブジェクトのツリーは DOM と呼ばれます。  HTML と同じように見えますが、HTML の下部で参照されているスクリプトが次のコードを実行したとします。  

```javascript
const h1 = document.querySelector('h1');
h1.parentElement.removeChild(h1);
const p = document.createElement('p');
p.textContent = 'Wildcard!';
document.body.appendChild(p);
```  

このコードは、 `h1` ノードを削除し、別の `p` ノードを DOM に追加します。  完全な DOM は、次のようになります。  

```dom
html
  head
    title
  body
    p
    script
    p
```  

ページの HTML が DOM とは異なるようになりました。  つまり、HTML は初期ページコンテンツを表し、DOM は現在のページコンテンツを表します。  JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。  

詳細について[は、「DOM の概要][MDNIntroductionToDOM]」を参照してください。  

<!--
## Appendix: Scroll into view   

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and select **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    > ##### Figure 19  
    > Scroll into view  
    > ![Scroll into view][ImageScrollView]  
    -->  

## 付録: オプションが表示されない   

このチュートリアルで説明する多くの手順では、DOM ツリーのノードを右クリックし、ポップアップ表示されるコンテキストメニューからオプションを選択するように指示されています。  コンテキストメニューに [指定] オプションが表示されない場合は、ノードのテキストを右クリックしてみてください。  

> ##### 図20  
> すべてのオプションが表示されない場合は、ここをクリックします。  
> ![すべてのオプションが表示されない場合は、ここをクリックします。][ImageNotSeeingAllOptions]  

<!-- image links -->  

[ImageInspectIcon]: /microsoft-edge/devtools-guide-chromium/media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: /microsoft-edge/devtools-guide-chromium/media/resume-script-icon.msft.png  

[ImageInspectingNode]: /microsoft-edge/devtools-guide-chromium/media/dom-glitch-dom-examples-michelangelo-inspect.msft.png "図 1: ノードを検査する"  
[ImageHighlightingMichelangeloNode]: /microsoft-edge/devtools-guide-chromium/media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png "図 2: Michelangelo ノードの強調表示"  
[ImageInspect]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-select-element-page-inspect.msft.png "図 3: [検査] アイコン"  
[ImageInspectingRingoNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png "図 4: Ringo ノードを調べる"  
[ImageInspectingUlNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png "図 5: ul ノードの検査"  
[ImageScrollView]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png "図 6: スクロールして表示する"  
[ImageHighlightingQuerySearchBar]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-search-nodes-highlight.msft.png "図 7: 検索バーでクエリを強調表示する"  
[ImageEditingText]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-content.msft.png "図 8: テキストを編集する"  
[ImageEditingNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-attributes-highlighted.msft.png "図 9: ノードを編集する"  
[ImageAddingStyleAttributeNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-attributes-inline-css.msft.png "図 10: スタイル属性をノードに追加する"  
[ImageChangingNodeButton]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-node-type-button.msft.png "図 11: ノードの種類をボタンに変更する"  
[ImageDraggingNodeTopList]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-reorder-dom-nodes.msft.png "図 12: ノードを一覧の一番上にドラッグする"  
[ImageNodeDomTreeAfterHidden]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-hide-a-node.msft.png "図 13: 非表示になった後のノードが DOM ツリーでどのように見えるか"  
[ImageFirstConsole]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png "図 14: 本体の最初の $0 の式の結果"  
[ImageSecondConsole]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png "図 15: 本体の2つ目の $0 式の結果"  
[ImageResultTemp1]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png "図 16: temp1 式の結果"  
[ImageResultCopyJSPath]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png "図 17: コピーされた JS パス式の結果"  
[ImageBreakAttributeModification]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png "図 18: 属性の変更時の中断"  
[ImageResumeScript]: /microsoft-edge/devtools-guide-chromium/media/dom-break-attribute-modifications-sources-paused-on.msft.png "図 19: スクリプトの実行を再開する場所"  
[ImageNotSeeingAllOptions]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-right-click-right-side.msft.png "図 20: すべてのオプションが表示されていない場合は、ここをクリックします。"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge \ (Chromium) 開発者ツール"  
[DevToolsCssGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を始める"  
[DevToolsShortcutsElements]: /microsoft-edge/devtools-guide-chromium/shortcuts#elements-panel-keyboard-shortcuts "要素パネルのキーボードショートカット-Microsoft Edge DevTools のショートカットキー"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM の例 |故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome devtools & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
