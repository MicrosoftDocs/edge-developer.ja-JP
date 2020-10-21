---
description: ノードの表示、ノードの検索、ノードの編集、コンソールの参照ノード、ノードの変更の中断などについて説明します。
title: DOM の表示と変更を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8c0b544f2c4717a01d09c287f1167c81456a97f3
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125028"
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

このチュートリアルでは、DOM と HTML の違いを知っていることを前提としています。  説明については [、「付録: HTML と DOM の比較](#appendix-html-versus-the-dom) 」を参照してください。  

## DOM の例を開く  

1.  " `Control` \ (Windows, Linux \)" または " `Command` \ (macOS \)" を保持し、[ **DOM の例** ] を選んで新しいタブで開きます。  
    
    [DOM の例][GlitchDomExamples]  
    
## DOM ノードの表示  

[要素] パネルの DOM ツリーでは、DevTools で DOM に関連するすべてのアクティビティを行うことができます。  

### ノードを検査する  

特定の DOM ノードに関心がある場合は、[ **検査** ] を使うと、devtools をすばやく開いてそのノードを調べることができます。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **ノードの検査**] で、[ **Michelangelo** ] を右クリックし、[ **検査**] を選択します。  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       ノードを検査する  
    :::image-end:::  
    
    1.  DevTools の [ **要素** ] パネルが開きます。  `<li>Michelangelo</li>` が強調表示さ **れてい**ます。  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           ノードを強調表示する `Michelangelo`  
        :::image-end:::  
        
        1.  **Inspect** ![ ][ImageInspectIcon] Devtools の左上隅にある検査 (検査 \) アイコンをクリックします。  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               [ **検査** ] アイコン  
            :::image-end:::  
            
1.  [ **ノードの検査**] で、[ **東京** ] のテキストをクリックします。  これで、 `<li>Tokyo</li>` DOM ツリーで強調表示されるようになりました。  

ノードの [検査] は、ノードのスタイルを表示して変更するための最初の手順でもあります。  「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCssGetStarted]参照してください。  

### キーボードで DOM ツリー内を移動する  

DOM ツリーでノードを選択すると、DOM ツリーをキーボードで移動できます。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **DOM ツリーをキーボードで操作**] で、[ **Ringo** ] を右クリックし、[ **検査**] を選びます。  `<li>Ringo</li>` が選択されます。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       ノードを検査する `Ringo`  
    :::image-end:::  
    
    1.  `Up`方向キーを2回押します。  `<ul>`  がオンになっていることを確認します。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           ノードを検査する `ul`  
        :::image-end:::  
        
    1.  `Left`方向キーを押します。  `<ul>`リストが折りたたまれます。  
    1.  `Left`もう一度方向キーを押します。  ノードの親 `<ul>` が選択されます。  この場合は、 `<div>` ID を使用し `navigate-the-dom-tree-with-a-keyboard-1` ます。  
    1.  `Down`方向キーを2回押して、折りたたんだリストをもう一度選択し `<ul>` ます。  次のようになります。 `<ul>... </ul>`  
    1.  `Right`方向キーを押します。  リストが拡張されます。  

### スクロールして表示する  

DOM ツリーを表示しているときに、現在ビューポート内にない DOM ノードに興味を持っていることがあります。  たとえば、ページの一番下までスクロールして、ページの上部にあるノードに関心を持っているとし `<h1>` ます。  **ビューをスクロール** すると、ビューポートをすばやく移動して、ノードを表示できます。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **スクロール**して表示] で、[ **Magritte** ] を右クリックし、[ **検査**] を選択します。  
1.  DOM の [例] ページの一番下までスクロールします。  
1.  `<li>Magritte</li>`それでも、ノードは DOM ツリーで選択されます。  表示されていない場合は、戻って、もう一度 [表示](#scroll-into-view) してみてください。  
1.  ノードを右クリック `<li>Magritte</li>` し、[ **ビューにスクロール**] を選択します。  ビューポートがスクロールして、 **Magritte** ノードが表示されることがあります。  [スクロールして**表示**する] オプションが表示されない場合は、「[付録: オプションが見つから](#appendix-missing-options)ない」を参照してください。
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **スクロールして表示する**  
    :::image-end:::  

### ノードを検索する  

DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。  

1.  カーソルを [ **要素** ] パネルにフォーカスします。  
1.  `Control` + `F` \ (Windows, Linux \) または `Command` + `F` \ (macOS \) を選択します。  検索バーは DOM ツリーの下部に表示されます。  
1.  「`The Moon is a Harsh Mistress`」と入力します。  DOM ツリーの最後の文が強調表示されています。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       検索バーでクエリを強調表示する  
    :::image-end:::  
    
上で説明したように、検索バーは CSS と XPath のセレクターもサポートしています。  

## DOM を編集する  

その場で DOM を編集して、それらの変更がページにどのように影響するかを確認できます。  

### コンテンツを編集する  

ノードのコンテンツを編集するには、DOM ツリーでコンテンツをダブルクリックします。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **コンテンツの編集**] で、[ **マイク** ] を右クリックし、[ **検査**] を選びます。  
    1.  DOM ツリーで、をダブルクリック `Michelle` します。  つまり、との間のテキストをダブルクリック `<li>` し `</li>` ます。  テキストが強調表示され、選択されていることが示されます。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           テキストを編集する  
        :::image-end:::  
        
    1.  [削除] を選択し、 `Michelle` 入力し `Leela` て、 `Enter` 変更内容を確認します。  DOM 内のテキストは、 **MicLeela le**から**Leela**に変更されます。  

### 属性を編集する  

属性を編集するには、属性の名前または値をダブルクリックします。  手順に従って、ノードに属性を追加する方法について説明します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **属性の編集**] で、[ **Howard** ] を右クリックし、[ **検査**] を選択します。  
1.  ダブルクリック `<li>` します。  テキストが強調表示され、ノードが選択されていることが示されます。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       ノードを編集する  
    :::image-end:::  
    
1.  方向キーを押して、スペースを追加し、 `Right` 「」と入力し `style="background-color:gold"` て、を選択し `Enter` ます。  ノードの背景色が金色に変わります。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       `style`ノードに属性を追加する  
    :::image-end:::  
    
### ノードの種類を編集する  

ノードの種類を編集するには、型をダブルクリックし、新しい型を入力します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **ノードの種類の編集**] で、[ **Hank** ] を右クリックし、[ **検査**] を選びます。  
    1.  ダブルクリック `<li>` します。  テキスト `li` が強調表示されます。  
    1.  を削除して、を入力し、 `li` `button` を選択し `Enter` ます。  `<li>`ノードがノードに変わり `<button>` ます。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           ノードの種類を変更する `button`  
        :::image-end:::  
        
### DOM ノードの順序を変更する  

ノードをドラッグして順序を変更します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **DOM ノードの並べ替え**] で、[ **Elvis Presley** ] を右クリックし、[ **検査**] を選びます。  
    
    > [!NOTE]
    > これは、リスト内の最後のアイテムです。  
    
    1.  DOM ツリーで、 `<li>Elvis Presley</li>` 一覧の一番上までドラッグします。  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           ノードを一覧の一番上にドラッグする  
        :::image-end:::  
        
### 強制状態  

ノードは、、、、、などの状態に保つことができ `:active` `:hover` `:focus` `:visited` `:focus-within` ます。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **状態の強制**] で、 **その中の閣下**をポイントします。  背景色がオレンジ色になります。  
    1.  **フライの閣下**を右クリックして、[**検査**] を選びます。  
    1.  右クリック `<li class="demo--hover">The Lord of the Flies</li>` して、[**状態の強制**  >  **: hover**] を選びます。  このオプションが表示されない場合は、「 [付録: オプション](#appendix-missing-options) を表示しない」を参照してください。  実際には、ノードの上にカーソルを置いていない場合でも、背景色はオレンジにとどまります。  

### ノードを非表示にする  

`H`ノードを非表示にする場合に選択します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **ノードを非表示にする**] で、[ **宛先の星** ] を右クリックし、[ **検査**] を選択します。  
    1.  キーを押し `H` ます。  ノードが非表示になっています。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           非表示になった後のノードが DOM ツリーのどのように見えるか  
        :::image-end:::  
        
    1.  キーを `H` もう一度押します。  ノードが再び表示されます。  

### ノードを削除する  

`Delete`ノードを削除する場合に選択します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **ノードの削除**] で、[ **Foundation** ] を右クリックし、[ **検査**] を選びます。  
    1.  キーを押し `Delete` ます。  ノードが削除されます。  
    1.  `Control` + `Z` \ (Windows, Linux \) または `Command` + `Z` \ (macOS \) を選択します。  直前の操作が取り消され、ノードが再び表示されます。  

## コンソールのアクセスノード  

DevTools では、コンソールから DOM ノードにアクセスしたり、各デバイスへの JavaScript 参照を取得したりするためのショートカットキーをいくつか用意しています。  

### $0 で現在選択されているノードを参照する  

ノードを検査すると、 `== $0` ノードの横のテキストは、この変数を持つ本体でこのノードを参照できることを意味 `$0` します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **$0 で現在選択さ**れているノードを参照する] で、 **暗さの左側** を右クリックして [ **検査**] を選びます。  
    1.  キーを押して、 `Escape` 本体の引き出しを開きます。  
    1.  キーを入力 `$0` して、キーを押し `Enter` ます。  この式の結果は、の `$0` 評価を示して `<li>The Left Hand of Darkness</li>` います。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            本体の最初の式の結果 `$0` **Console**  
        :::image-end:::  
        
    1.  結果にマウスポインターを合わせます。  ビューポートで、ノードが強調表示されています。  
    1.  `<li>Dune</li>`DOM ツリー内をクリックし、 `$0` コンソールをもう一度入力して、 `Enter` もう一度選択します。  次に、の `$0` ようにに評価さ `<li>Dune</li>` れます。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           コンソールの2番目の `$0` 式の**Console**結果  
        :::image-end:::  
        
### グローバル変数として保存する  

何度もノードを参照する必要がある場合は、それをグローバル変数として保存します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **グローバル変数として保存**] で、 **大きいスリープ** を右クリックし、[ **検査**] を選択します。  
    1.  DOM ツリーを右クリックして、 `<li>The Big Sleep</li>` [ **グローバル変数として保存**] を選びます。  このオプションが表示されない場合は、「 [付録: オプション](#appendix-missing-options) を表示しない」を参照してください。  
    1.  `temp1`コンソールに入力して、を選択し `Enter` ます。  この式の結果は、変数がノードに評価されることを示します。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           式の結果 `temp1`  
        :::image-end:::  
        
### JS パスをコピーする  

自動テストで参照する必要がある場合は、JavaScript のパスをノードにコピーします。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **JS パスのコピー**] で、[ **兄弟 Karamazov** ] を右クリックし、[ **検査**] を選びます。  
    1.  DOM ツリーを右クリック `<li>The Brothers Karamazov</li>` して、[ **Copy**  >  **copy copy JS Path**] を選びます。  `document.querySelector()`ノードに解決される式がクリップボードにコピーされました。  
    1.  `Control` + `V` 式をコンソールに貼り付けるには、\ (Windows, Linux \) または `Command` + `V` \ (macOS \) を選択します。  
    1.  `Enter`式を評価する場合に選択します。
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           **JS パス**の式をコピーした結果  
        :::image-end:::  
        
## DOM の中断の変更  

DevTools を使うと、JavaScript が DOM を変更したときにページの JavaScript を一時停止することができます。  

### 属性の変更の中断  

ノードの任意の属性を変更する JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **属性の変更を中断**] で、[ **Sauerkraut** ] を右クリックし、[ **検査**] を選びます。  
    1.  DOM ツリーで右クリックし、[ `<li id="target">Sauerkraut</li>` 属性**の変更を中断**] を選び  >  **Attribute Modifications**ます。  このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **属性の変更の中断**  
        :::image-end:::  
        
    1.  次の手順では、ページのコードを一時停止するボタンをクリックするように指示されます。  ページが一時停止されると、ページをスクロールすることはできなくなります。  **Resume Script** ![ ][ImageResumeScriptIcon] ページを再びスクロールできるようにするには、[スクリプトの再開] (スクリプトの再開 \) を選択する必要があります。
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           スクリプトの実行を再開する場所  
        :::image-end:::  
        
    1.  上の [ **背景の設定** ] をクリックします。  これにより `style` 、ノードの属性がに設定され `background-color:thistle` ます。  DevTools はページを一時停止し、属性が変更されたコードを強調表示します。  
    1.  **Resume Script** ![ ][ImageResumeScriptIcon] 前に説明したように、[スクリプトの再開] を選びます。  
    
### ノード削除時の中断  

特定のノードが削除されたときに一時停止する場合は、ノード削除のブレークポイントを使用します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **ノード削除時の中断**] で、[ **Neuromancer** ] を右クリックし、[ **検査**] を選びます。  
    1.  DOM ツリーで右クリックし、[ `<li id="target">Neuromancer</li>` ノード**の削除時に中断**] を選択し  >  **Node Removal**ます。  このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。  
    1.  上の [ **削除** ] ボタンをクリックします。  DevTools はページを一時停止し、ノードの削除を引き起こしたコードを強調表示します。  
    1.  [ **スクリプトの再開** ] を選択し ![ ます (スクリプトを再開 ][ImageResumeScriptIcon] します)。  
    
### サブツリーの変更の中断  

ノードにサブツリーの変更のブレークポイントを配置すると、ノードの子孫が追加または削除されると、DevTools によってページが一時停止します。  

1.  [DOM の例を開き](#open-dom-examples)ます。  
1.  [ **サブツリーの変更の中断**] で、[詳細] の下に **ある炎を** 右クリックし、[ **検査**] を選びます。  
    1.  DOM ツリーで、上のノードである右クリックし、[ `<ul id="target">` `<li>A Fire Upon the Deep</li>` サブツリー**の**変更による中断] を選択し  >  **Subtree Modifications**ます。  このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。  
    1.  [ **子の追加**] を選びます。  ノードがリストに追加されたため、コードは一時停止し `<li>` ます。  
    1.  [ **スクリプトの再開** ] を選択し ![ ます (スクリプトを再開 ][ImageResumeScriptIcon] します)。  
    
## 次のステップ  

これは、DevTools の DOM 関連のほとんどの機能について説明しています。  残りの部分については、DOM ツリーのノードを右クリックし、このチュートリアルで説明していないその他のオプションを試してみることができます。  「 [要素パネルのショートカットキー][DevToolsShortcutsElements]」もご覧ください。  

[Microsoft Edge DevTools のホームページ][MicrosoftEdgeDevTools]をチェックして、devtools で実行できるその他の情報をすべて見つけてください。  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## 付録: HTML と DOM の比較  

以下のセクションでは、HTML と DOM の違いについて簡単に説明します。  

:::row:::
   :::column span="":::
      Web ブラウザーを使用してページを要求すると、サーバーは次のコードスニペットのような HTML を返します。  

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
   :::column-end:::
   :::column span="":::
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
   :::column-end:::
:::row-end:::  

ページのコンテンツを表す、このオブジェクトのツリーは DOM と呼ばれます。  

:::row:::
   :::column span="":::
      HTML と同じように見えますが、HTML の下部で参照されているスクリプトが次のコードスニペットを実行していることを考えてみてください。  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      このコードは、 `h1` ノードを削除し、別の `p` ノードを DOM に追加します。  これで、完全な DOM に次のリストが表示されるようになりました。  
      
      ```dom
      html
          head
              title
          body
              p
              script
              p
      ```  
   :::column-end:::
:::row-end:::  

ページの HTML が DOM とは異なるようになりました。  つまり、HTML は初期ページコンテンツを表し、DOM は現在のページコンテンツを表します。  JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。  

詳細について [は、「DOM の概要][MDNIntroductionToDOM] 」を参照してください。  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and choose **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## 付録: オプションが表示されない  

このチュートリアルで説明する多くの手順では、DOM ツリーのノードを右クリックし、ポップアップ表示されるコンテキストメニューからオプションを選択するように指示されています。  コンテキストメニューに [指定] オプションが表示されない場合は、ノードのテキストを右クリックしてみてください。  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   すべてのオプションが表示されない場合は、ここをクリックします。  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge \ (Chromium \) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCssGetStarted]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  
[DevToolsShortcutsElements]: ../shortcuts.md#elements-panel-keyboard-shortcuts "要素パネルのキーボードショートカット-Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM の例 |故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
