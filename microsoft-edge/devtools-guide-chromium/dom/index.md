---
description: ノードの表示方法、ノードの検索方法、ノードの編集方法、コンソール内の参照ノードの表示方法、ノードの変更時のブレーク方法などについて説明します。
title: DOM の表示と変更を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5b12b984aed7e35ce11dd45e8bc33f5d5fd454f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231105"
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

これらの対話型チュートリアルを実行して、Microsoft Edge DevTools を使用してページの DOM を表示および変更する方法の基本について説明します。  

このチュートリアルでは、DOM と HTML の違いを知っている必要があります。  説明については [、「付録: HTML と DOM」](#appendix-html-versus-the-dom) に移動します。  

## DOM を開く例  

1.  `Control`\(Windows, Linux\) または `Command` \(macOS\) を保持し **、[DOM の**例] を選択して新しいタブで開きます。  
    
    [DOM の例][GlitchDomExamples]  
    
## DOM ノードの表示  

要素パネルの DOM ツリーは、DevTools で DOM 関連のすべてのアクティビティを実行する場所です。  

### ノードを検査する  

特定の DOM ノードに関心がある場合 **、Inspect** は DevTools を開いてそのノードを調査する高速な方法です。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [ **ノードの検査] で、Michel** **michel** を右クリックして [検査] を **選択します**。  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       ノードを検査する  
    :::image-end:::  
    
    1.  DevTools **の要素** パネルが開きます。  `<li>Michelangelo</li>` が DOM ツリーで **強調表示されます**。  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="Michel michel ノードを強調表示する" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           ノードを強調表示 `Michelangelo` する  
        :::image-end:::  
        
        1.  DevTools **の左上隅** にある Inspect ![ \( Inspect ][ImageInspectIcon] \) アイコンをクリックします。  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="[検査] アイコン" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               [ **検査]** アイコン  
            :::image-end:::  
            
1.  [ **ノードの検査] で**、[東京] テキスト **をクリック** します。  これで `<li>Tokyo</li>` 、DOM ツリーで強調表示されます。  

ノードを検査する手順は、ノードのスタイルを表示および変更する最初の手順です。  CSS の [表示と変更の開始に移動します][DevToolsCssGetStarted]。  

### キーボードを使用して DOM ツリー内を移動する  

DOM ツリーでノードを選択したら、キーボードを使用して DOM ツリー内を移動できます。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [ **キーボードを使用して DOM ツリーを移動する]** で **、[Ringo]** を右クリックして [検査] を選択 **します**。  `<li>Ringo</li>` が DOM ツリーで選択されています。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="[リング] ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       ノードを検査 `Ringo` する  
    :::image-end:::  
    
    1.  方向キー `Up` を 2 回押します。  `<ul>`  がオンになっていることを確認します。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="ul ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           ノードを検査 `ul` する  
        :::image-end:::  
        
    1.  方向キー `Left` を押します。  リスト `<ul>` が折りたたむ。  
    1.  もう一度 `Left` 方向キーを押します。  ノードの親 `<ul>` が選択されます。  この場合、ID `<div>` は次の ID です `navigate-the-dom-tree-with-a-keyboard-1` 。  
    1.  折りたたみしたリストを再選択するには、方向キーを `Down` 2 `<ul>` 回押します。  次のようになります。 `<ul>... </ul>`  
    1.  方向キー `Right` を押します。  リストが展開されます。  

### スクロールして表示  

DOM ツリーを表示するときに、現在ビューポートに含されていない DOM ノードに興味がある場合があります。  たとえば、ページの一番下までスクロールし、ページの上部にあるノードに関心を持った `<h1>` とします。  **ビュー内にスクロール** すると、ビューポートをすばやく再配置して、ノードを確認できます。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [ **表示] にスクロールし**、[Magritte] を **右** クリックして [検査] を **選択します**。  
1.  DOM の [例] ページの下部までスクロールします。  
1.  ノード `<li>Magritte</li>` は、DOM ツリーで引き続き選択する必要があります。  表示されていない場合は、[スクロールして表示 [] に戻り、最初](#scroll-into-view) から最初から実行します。  
1.  ノードをポイントし、コンテキスト メニュー \(右クリック\) を開き、[スクロールして表示 `<li>Magritte</li>` **] を選択します**。  ビューポートが上にスクロールして **、Magritte ノードを確認** できます。  [付録 [: 表示にスクロール]](#appendix-missing-options) オプションを確認できない場合は、[付録: 不足しているオプション] **に移動** します。
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="スクロールして表示" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **スクロールして表示**  
    :::image-end:::  

### ノードの検索  

DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。  

1.  [要素] パネルにカーソル **を移動** します。  
1.  `Control` + `F` \(Windows,Linux\) または `Command` + `F` \(macOS\) を選択します。  DOM ツリーの下部に検索バーが開きます。  
1.  「`The Moon is a Harsh Mistress`」と入力します。  DOM ツリーで最後の文が強調表示されます。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="検索バーでクエリを強調表示する" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       検索バーでクエリを強調表示する  
    :::image-end:::  
    
前述のように、検索バーは CSS セレクターと XPath セレクターもサポートしています。  

## DOM を編集する  

オンザフライで DOM を編集し、変更がページに与える影響を確認できます。  

### コンテンツを編集する  

ノードのコンテンツを編集するには、DOM ツリー内のコンテンツをダブルクリックします。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [コンテンツ **の編集]** で **、Michelle** を右クリックして [検査] を **選択します**。  
    1.  DOM ツリーで、ダブルクリックします `Michelle` 。  つまり、次の間にあるテキストを `<li>` ダブルクリックします `</li>` 。  テキストが強調表示され、選択されている状態が示されます。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="テキストを編集する" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           テキストを編集する  
        :::image-end:::  
        
    1.  [ `Michelle` 削除] を `Leela` 入力し、変更 `Enter` の確認を選択します。  DOM 内のテキストが **Michelle** から **Leela に変更されます**。  

### 属性の編集  

属性を編集するには、属性の名前または値をダブルクリックします。  指示に従って、ノードに属性を追加する方法について説明します。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [ **属性の編集]** で **[Howard]** を右クリックし、[検査] を **選択します**。  
1.  ダブルクリック `<li>` します。  テキストが強調表示され、ノードが選択されています。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="ノードを編集する" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       ノードを編集する  
    :::image-end:::  
    
1.  方向キー `Right` を押し、スペースを追加し、入力 `style="background-color:gold"` して、選択します `Enter` 。  ノードの背景色がゴールドに変更されます。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="ノードに style 属性を追加する" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       ノード `style` に属性を追加する  
    :::image-end:::  
    
### ノードの種類の編集  

ノードの種類を編集するには、種類をダブルクリックし、新しい種類を入力します。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [**ノードの種類の編集] で****、[Hank]** を右クリックして [検査] を**選択します**。  
    1.  ダブルクリック `<li>` します。  テキストが `li` 強調表示されます。  
    1.  Delete `li` , type , then select `button` `Enter` .  ノード `<li>` がノードに変更 `<button>` されます。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="ノードの種類をボタンに変更する" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           ノードの種類を次に変更します。 `button`  
        :::image-end:::  
        
### DOM ノードを並べ替える  

ノードをドラッグして並べ替えます。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [DOM **ノードの並べ替え**] で **、Elvis Presley** を右クリックして [検査] を選択 **します**。  
    
    > [!NOTE]
    > リスト内の最後のアイテムです。  
    
    1.  DOM ツリーで、リスト `<li>Elvis Presley</li>` の一番上にドラッグします。  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="ノードをリストの一番上にドラッグします。" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           ノードをリストの一番上にドラッグします。  
        :::image-end:::  
        
### 強制状態  

ノードを強制的に状態 (、 など) `:active` `:hover` `:focus` `:visited` に維持することができます `:focus-within` 。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [ **強制] 状態の**下で **、[Flies の指定] の上にマウス ポインターを移動します**。  背景色はオレンジ色になります。  
    1.  **[Flies の指定] を右クリックし、[検査]** を**選択します**。  
    1.  右クリックし、 `<li class="demo--hover">The Lord of the Flies</li>` 強制状態****  >  **:hover を選択します**。  オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。  実際にノードの上にカーソルを置いなくても、背景色はオレンジ色のままです。  

### ノードを非表示にする  

ノード `H` を非表示にする場合に選択します。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [ **ノードを非表示にする] で**、[星の宛先] を右クリック **し** 、[検査] を選択 **します**。  
    1.  キーを押 `H` します。  ノードは非表示です。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="DOM ツリーが非表示にされた後のノードの外観" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           DOM ツリーが非表示にされた後のノードの外観  
        :::image-end:::  
        
    1.  もう一度 `H` キーを押します。  ノードが再び表示されます。  

### ノードを削除する  

ノード `Delete` を削除する場合に選択します。  

1.  [DOM を開く例](#open-dom-examples)  
1.  Under **Delete a Node,** right-choose **Foundation** and choose **Inspect**.  
    1.  キーを押 `Delete` します。  ノードが削除されます。  
    1.  `Control` + `Z` \(Windows,Linux\) または `Command` + `Z` \(macOS\) を選択します。  最後の操作が取り消され、ノードが再び表示されます。  

## コンソール内のアクセス ノード  

DevTools には、コンソールから DOM ノードにアクセスしたり、各ノードへの JavaScript 参照を取得したりするために、いくつかのショートカットが用意されています。  

### 現在選択されているノードを $0 で参照する  

ノードを検査する場合、ノードの横のテキストは、コンソールでこのノードを変数と一緒 `== $0` に参照できる可能性を意味します `$0` 。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [Reference **the currently-selected node with $0] ($0**で現在選択されているノードを参照する) の下で **、[The Left Hand of The Left Hand of The Darkness]** を右クリックし **、[Inspect]**(検査) を選択します。  
    1.  キーを押 `Escape` してコンソール ドロワーを開きます。  
    1.  キー `$0` を入力して押 `Enter` します。  式の結果は、次の値 `$0` に評価されます `<li>The Left Hand of Darkness</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="コンソール内の最初の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            コンソール内の最初の `$0` 式の **結果**  
        :::image-end:::  
        
    1.  結果の上にカーソルを移動します。  ノードはビューポートで強調表示されます。  
    1.  `<li>Dune</li>`DOM ツリーをクリックし、コンソール `$0` にもう一度入力して、もう一度選択 `Enter` します。  次に、 `$0` 次の値に評価されます `<li>Dune</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="コンソール内の 2 番目の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           コンソール内の 2 `$0` 番目の式の **結果**  
        :::image-end:::  
        
### グローバル変数として格納する  

ノードを何度も参照する必要がある場合は、グローバル変数として保存します。  

1.  [DOM を開く例](#open-dom-examples)  
1.  Under **Store as global variable,** right-choose the Big **Sleep** and choose **Inspect**.  
    1.  DOM ツリーを `<li>The Big Sleep</li>` 右クリックし、[グローバル変数として **保存] を選択します**。  オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。  
    1.  コンソール `temp1` に入力し、次に選択します `Enter` 。  式の結果は、変数がノードに評価されるのを示します。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 式の結果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           式の `temp1` 結果  
        :::image-end:::  
        
### JS パスをコピーする  

自動化されたテストで参照する必要がある場合は、JavaScript パスをノードにコピーします。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [JS **パスのコピー] の**下で **、[The 多くのMazov]** を右クリックし、[検査] を **選択します**。  
    1.  DOM ツリーを `<li>The Brothers Karamazov</li>` 右クリックし、[コピー **** JS パス]  >  **を選択します**。  ノード `document.querySelector()` に解決される式がクリップボードにコピーされています。  
    1.  `Control` + `V` \(Windows,Linux\) または \(macOS\) を選択して、式をコンソール `Command` + `V` に貼り付けます。  
    1.  式 `Enter` を評価するために選択します。
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="JS パスのコピー式の結果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           JS パスの **コピー式の** 結果  
        :::image-end:::  
        
## DOM の変更時にブレーク  

DevTools を使用すると、JavaScript が DOM を変更するときにページの JavaScript を一時停止できます。  

### 属性の変更に対するブレーク  

ノードの属性が変更される JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [Break **on attribute modifications] (属性の変更時**に Break) で、右クリックして **[Inspect]** を選択 **します**。  
    1.  DOM ツリーで右クリックし、[属性の変更 `<li id="target">Sauerkraut</li>` **時にブレーク オン**  >  **] を選択します**。  オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="属性の変更に対するブレーク" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **属性の変更を行う**  
        :::image-end:::  
        
    1.  次の手順では、ページのコードを一時停止するボタンをクリックするように指示されます。  ページを一時停止すると、ページをスクロールできなくなりました。  ページを再 **びスクロール可能に** するには、Resume Script \( Resume Script \) を選択 ![ ][ImageResumeScriptIcon] する必要があります。
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="スクリプトの実行を再開する場所" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           スクリプトの実行を再開する場所  
        :::image-end:::  
        
    1.  上の [ **背景の設定]** ボタンをクリックします。  これにより、ノード `style` の属性が設定されます `background-color:thistle` 。  DevTools はページを一時停止し、属性の変更を引き起こしたコードを強調表示します。  
    1.  前述 **のように、[Resume Script** \( ![ Resume Script ][ImageResumeScriptIcon] \] (スクリプトの再開 \ ) を選択します。  
    
### ノードの削除時にブレーク  

特定のノードが削除された場合に一時停止する場合は、ノード削除のブレークポイントを使用します。  

1.  [DOM を開く例](#open-dom-examples)  
1.  [ **ノードの削除時にブレーク] で、[** ニューロマン **サー** ] を右クリックし、[検査] を **選択します**。  
    1.  DOM ツリーで右クリックし、[ノード削除時に `<li id="target">Neuromancer</li>` **ブレーク]**  >  **を選択します**。  オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。  
    1.  上の [ **削除]** ボタンをクリックします。  DevTools はページを一時停止し、ノードを削除したコードを強調表示します。  
    1.  [ **スクリプトの再開\** ( ![ スクリプトの履歴書 \ ) を ][ImageResumeScriptIcon] 選択します。  
    
### サブツリーの変更時にブレークする  

ノードにサブツリー変更ブレークポイントを設定すると、ノードの子孫が追加または削除されると、DevTools はページを一時停止します。  

1.  [DOM を開く例](#open-dom-examples)  
1.  Under **Break on Subtree Modifications,** right-choose **A Fire On the Deep** and choose **Inspect**.  
    1.  DOM ツリーで、上のノードである右クリックし、[サブツリーの変更時にブレーク `<ul id="target">` `<li>A Fire Upon the Deep</li>` **]**  >  **を選択します**。  オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。  
    1.  [子 **の追加] を選択します**。  ノードがリストに追加 `<li>` されたため、コードは一時停止します。  
    1.  [ **スクリプトの再開\** ( ![ スクリプトの履歴書 \ ) を ][ImageResumeScriptIcon] 選択します。  
    
## 次のステップ  

DevTools の DOM 関連機能のほとんどについて説明します。  DOM ツリーでノードを右クリックし、このチュートリアルでは説明していない他のオプションを試して、残りのノードを検出できます。  要素パネル [のキーボード ショートカットに移動します][DevToolsShortcutsElements]。  

[Microsoft Edge DevTools ホームページを参照して、DevTools][MicrosoftEdgeDevTools]で実行できるその他の操作について説明します。  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## 付録: HTML と DOM  

次のセクションでは、HTML と DOM の違いについて簡単に説明します。  

:::row:::
   :::column span="":::
      Web ブラウザーを使用してページを要求すると、サーバーは次のコード スニペットのような HTML を返します。  

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
      ブラウザーは HTML を解析し、次のリストのようなオブジェクトのツリーを作成します。  
      
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

ページのコンテンツを表すオブジェクトまたはノードのこのツリーを DOM と呼ぶ。  

:::row:::
   :::column span="":::
      現時点では HTML と同じように見えますが、HTML の下部で参照されるスクリプトが次のコード スニペットを実行するとします。  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      このコードはノードを削除 `h1` し、DOM に `p` 別のノードを追加します。  これで、DOM の完全な一覧が表示されます。  
      
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

ページの HTML が DOM と異なっています。  つまり、HTML は初期ページ コンテンツを表し、DOM は現在のページ コンテンツを表します。  JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。  

詳細については [、「DOM の概要」][MDNIntroductionToDOM] に移動します。  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and choose **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## 付録: 不足しているオプション  

このチュートリアルの手順の多くは、DOM ツリー内のノードを右クリックし、ポップアップ表示されるコンテキスト メニューからオプションを選択するように指示します。  コンテキスト メニューの指定されたオプションが表示されない場合は、ノードのテキストから右クリックしてみてください。  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="すべてのオプションが表示されない場合の選択先" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   すべてのオプションが表示されない場合の選択先  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \(Chromium\) Developer Tools |Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "CSS の表示と変更を開始する |Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-panel-keyboard-shortcuts "要素パネルのキーボード ショートカット - Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM の例 |Glitch"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
