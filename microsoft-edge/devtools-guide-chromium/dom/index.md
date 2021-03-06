---
description: ノードの表示、ノードの検索、ノードの編集、コンソール内の参照ノードの表示方法、ノードの変更点の割り当てなど。
title: DOM の表示と変更の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bb2b733cfa3597c47f0a20de00e9c8b506e7c41c
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398330"
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

# <a name="get-started-with-viewing-and-changing-the-dom"></a>DOM の表示と変更の開始  

Microsoft Edge DevTools を使用してページの DOM を表示および変更する基本を学習するには、次の対話型チュートリアルを実行します。  

このチュートリアルでは、DOM と HTML の違いを知っている必要があります。  説明については [、「付録: HTML と DOM」](#appendix-html-versus-the-dom) に移動します。  

## <a name="open-dom-examples"></a>オープン DOM の例  

1.  `Control`\(Windows,Linux\) または `Command` \(macOS\) を保持し **、[DOM の例**] を選択して新しいタブを開きます。  
    
    [DOM の例][GlitchDomExamples]  
    
## <a name="view-dom-nodes"></a>DOM ノードの表示  

要素パネルの DOM ツリーは、DevTools で DOM 関連のすべてのアクティビティを実行する場所です。  

### <a name="inspect-a-node"></a>ノードの検査  

特定の DOM ノードに興味がある場合 **、Inspect** は DevTools を開いてそのノードを調査する高速な方法です。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **ノードの検査] で**、ミケランジェロを **右クリックし** 、[検査] を **選択します**。  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="ノードの検査" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       ノードの検査  
    :::image-end:::  
    
    1.  **DevTools**の Elements ツールが開きます。  `<li>Michelangelo</li>` は DOM ツリー で **強調表示されます**。  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="ミケランジェロ ノードを強調表示する" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           ノードを強調表示 `Michelangelo` する  
        :::image-end:::  
        
        1.  DevTools **の** 左上隅にある ![ [検査 ][ImageInspectIcon] \( Inspect \) ] アイコンを選択します。  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="[検査] アイコン" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               [ **検査]** アイコン  
            :::image-end:::  
            
1.  [ **ノードの検査] で**、[東京] テキスト **を選択** します。  これで `<li>Tokyo</li>` 、DOM ツリーで強調表示されます。  

ノードの検査は、ノードのスタイルを表示および変更する最初の手順です。  [CSS の [表示と変更の開始] に移動します][DevToolsCssGetStarted]。  

### <a name="navigate-the-dom-tree-with-a-keyboard"></a>キーボードを使用して DOM ツリーを移動する  

DOM ツリーでノードを選択したら、キーボードで DOM ツリーを移動できます。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **キーボードを使用して DOM ツリーを移動する]** で **、[Ringo]** を右クリックし、[検査] を **選択します**。  `<li>Ringo</li>` が DOM ツリーで選択されています。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="Ringo ノードの検査" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       ノードの `Ringo` 検査  
    :::image-end:::  
    
    1.  矢印キー `Up` を 2 回選択します。  `<ul>`  がオンになっていることを確認します。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="ul ノードの検査" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           ノードの `ul` 検査  
        :::image-end:::  
        
    1.  矢印キー `Left` を選択します。  リスト `<ul>` が折りたたむ。  
    1.  矢印キーを `Left` 再度選択します。  ノードの親 `<ul>` が選択されています。  この例では、ID `<div>` を使用します `navigate-the-dom-tree-with-a-keyboard-1` 。  
    1.  矢印キーを 2 回選択して、折りたたむだけのリスト `Down` `<ul>` を再選択します。  次のようになります。 `<ul>... </ul>`  
    1.  矢印キー `Right` を選択します。  リストが展開されます。  

### <a name="scroll-into-view"></a>ビューにスクロールする  

DOM ツリーを表示すると、現在ビューポートに表示されていない DOM ノードに興味を持つ場合があります。  たとえば、ページの下部までスクロールし、ページの上部にあるノードに興味を `<h1>` 持ったとします。  **ビューにスクロールすると** 、ビューポートの位置をすばやく変更して、ノードを確認できます。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **表示にスクロール] で**、[Magritte] を **右クリックし、[** 検査] を **選択します**。  
1.  [DOM の例] ページの下部までスクロールします。  
1.  ノード `<li>Magritte</li>` は DOM ツリーで選択されている必要があります。  表示されていない場合は、[スクロールして表示 [] に戻り、](#scroll-into-view) 最初から開始します。  
1.  ノードにマウス `<li>Magritte</li>` ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[表示にスクロール] **を選択します**。  ビューポートがスクロールして **、Magritte ノードを確認** できます。  [付録 [: 表示にスクロール] オプション](#appendix-missing-options) を確認できない場合は、不足 **しているオプションに移動** します。
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="ビューにスクロールする" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **ビューにスクロールする**  
    :::image-end:::  

### <a name="search-for-nodes"></a>ノードの検索  

DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。  

1.  [要素] ツールにカーソル **を移動** します。  
1.  `Control` + `F` \(Windows, Linux\) または `Command` + `F` \(macOS\) を選択します。  DOM ツリーの下部に検索バーが開きます。  
1.  「`The Moon is a Harsh Mistress`」と入力します。  最後の文は DOM ツリーで強調表示されます。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="検索バーでクエリを強調表示する" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       検索バーでクエリを強調表示する  
    :::image-end:::  
    
前述のように、検索バーは CSS および XPath セレクターもサポートしています。  

## <a name="edit-the-dom"></a>DOM の編集  

その場合は、DOM を編集し、変更がページに与える影響を確認できます。  

### <a name="edit-content"></a>コンテンツの編集  

ノードのコンテンツを編集するには、DOM ツリー内のコンテンツをダブルクリックします。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [コンテンツ **の編集] で**、ミシェルを **右クリックし** 、[検査] を **選択します**。  
    1.  DOM ツリーで、をダブルクリックします `Michelle` 。  つまり、テキストの間をダブルクリックし、 `<li>` をクリックします `</li>` 。  テキストが強調表示され、選択されているテキストが示されます。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="テキストを編集する" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           テキストを編集する  
        :::image-end:::  
        
    1.  [削除 `Michelle` ] を `Leela` クリックし、次に選択 `Enter` して変更を確認します。  DOM のテキストがミシェルから**Leela に****変わります**。  

### <a name="edit-attributes"></a>属性の編集  

属性を編集するには、属性名または値をダブルクリックします。  指示に従って、ノードに属性を追加する方法について説明します。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [属性 **の編集]** で **、[Howard] を右クリックし、[** 検査] を **選択します**。  
1.  ダブルクリック `<li>` します。  テキストが強調表示され、ノードが選択されているかどうかを示します。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="ノードの編集" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       ノードの編集  
    :::image-end:::  
    
1.  矢印キー `Right` を選択し、スペースを追加し、型 `style="background-color:gold"` を入力して、を選択します `Enter` 。  ノードの背景色が金色に変わります。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="ノードに style 属性を追加する" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       ノードに `style` 属性を追加する  
    :::image-end:::  
    
### <a name="edit-node-type"></a>ノードの種類の編集  

ノードの種類を編集するには、その種類をダブルクリックし、新しい種類を入力します。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **ノードの種類の編集] で**、Hank を **右クリックし、[** 検査] を **選択します**。  
    1.  ダブルクリック `<li>` します。  テキストが `li` 強調表示されます。  
    1.  [削除 `li` ] をクリック `button` し、[入力] を選択します `Enter` 。  ノード `<li>` がノードに変更 `<button>` されます。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="ノードの種類をボタンに変更する" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           ノードの種類をに変更する `button`  
        :::image-end:::  
        
### <a name="reorder-dom-nodes"></a>DOM ノードの並べ替え  

ノードをドラッグして並べ替えます。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [DOM **ノードの並べ替え**] で **、Elvis Presley を右クリックし、[** 検査] を **選択します**。  
    
    > [!NOTE]
    > リスト内の最後のアイテムです。  
    
    1.  DOM ツリーで、リスト `<li>Elvis Presley</li>` の一番上にドラッグします。  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="ノードをリストの一番上にドラッグする" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           ノードをリストの一番上にドラッグする  
        :::image-end:::  
        
### <a name="force-state"></a>強制状態  

ノードを強制的に状態 (、 など) `:active` `:hover` `:focus` `:visited` に維持できます `:focus-within` 。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **強制状態] で**、[ハエ **の主] にマウス ポインターを移動します**。  背景色がオレンジ色になります。  
    1.  [ハ **エの主] にマウス ポインターを置き**、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
    1.  をポイント `<li class="demo--hover">The Lord of the Flies</li>` し、コンテキスト メニュー \(右クリック\) を開き、[**強制状態**:ホバー]  >  **を選択します**。  オプションが [表示されない場合は](#appendix-missing-options) 、[付録: 不足しているオプション] に移動します。  実際にノードの上をホバーしていない場合でも、背景色はオレンジ色のままです。  

### <a name="hide-a-node"></a>ノードを非表示にする  

ノード `H` を非表示にする場合に選択します。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **ノードを非表示にする] で**、[星の移動先] **を右クリックし、[** 検査] を **選択します**。  
    1.  キーを選択 `H` します。  ノードは非表示です。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="DOM ツリーが非表示にされた後のノードの外観" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           DOM ツリーが非表示にされた後のノードの外観  
        :::image-end:::  
        
    1.  もう一度 `H` キーを選択します。  ノードが再び表示されます。  

### <a name="delete-a-node"></a>ノードの削除  

ノード `Delete` を削除する場合に選択します。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **ノードの削除] で、[Foundation]** を右クリック **し、[検査** ] を **選択します**。  
    1.  キーを選択 `Delete` します。  ノードが削除されます。  
    1.  `Control` + `Z` \(Windows, Linux\) または `Command` + `Z` \(macOS\) を選択します。  最後のアクションは元に戻され、ノードが再び表示されます。  

## <a name="access-nodes-in-the-console"></a>コンソールのノードにアクセスする  

DevTools には、コンソールから DOM ノードにアクセスしたり、各ノードへの JavaScript 参照を取得したりするために、いくつかのショートカットが用意されています。  

### <a name="reference-the-currently-selected-node-with-0"></a>現在選択されているノードを $0 で参照する  

ノードを検査する場合、ノードの横にあるテキストは、このノードを変数と一緒にコンソールで参照 `== $0` できる可能性を意味します `$0` 。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **現在選択されているノードを $0**で参照する] で、[ダークネスの左手] を右クリックし、[ **検査]** を選択 **します**。  
    1.  キーを `Escape` 選択してコンソール ドロワーを開きます。  
    1.  キー `$0` を入力して選択 `Enter` します。  式の結果は、 に `$0` 評価されます `<li>The Left Hand of Darkness</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="コンソールの最初の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            コンソールの最初の `$0` 式の **結果**  
        :::image-end:::  
        
    1.  結果にカーソルを合わせる。  ノードがビューポートで強調表示されます。  
    1.  DOM `<li>Dune</li>` ツリーで選択し、もう一 `$0` 度コンソールを入力してから、もう一度選択 `Enter` します。  次に `$0` 、に評価します `<li>Dune</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="コンソールの 2 番目の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           コンソールの 2 番目 `$0` の式の **結果**  
        :::image-end:::  
        
### <a name="store-as-global-variable"></a>グローバル変数として格納する  

ノードを何度も参照する必要がある場合は、グローバル変数として格納します。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [**グローバル変数として格納]** で****、[ビッグ スリープ] をポイントし、コンテキスト メニュー \(右クリック\) を開き、[検査] を選択**します**。  
    1.  DOM ツリー `<li>The Big Sleep</li>` でマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[グローバル変数として **保存] を選択します**。  オプションが [表示されない場合は](#appendix-missing-options) 、[付録: 不足しているオプション] に移動します。  
    1.  コンソール `temp1` に入力し、[] を選択します `Enter` 。  式の結果は、変数がノードに評価されます。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 式の結果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           式の `temp1` 結果  
        :::image-end:::  
        
### <a name="copy-js-path"></a>JS パスのコピー  

自動化されたテストで JavaScript パスを参照する必要がある場合は、ノードに JavaScript パスをコピーします。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [JS **パスのコピー]** で、兄弟 **Karamazov**にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
    1.  DOM ツリー `<li>The Brothers Karamazov</li>` でマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[コピー JS パス]****  >  **を選択します**。  ノード `document.querySelector()` に解決される式がクリップボードにコピーされています。  
    1.  `Control` + `V` \(Windows,Linux\) または \(macOS\) を選択して、式をコンソール `Command` + `V` に貼り付けます。  
    1.  式 `Enter` を評価する場合に選択します。
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="Copy JS Path 式の結果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           Copy JS **Path** 式の結果  
        :::image-end:::  
        
## <a name="break-on-dom-changes"></a>DOM の変更に対するブレーク  

DevTools を使用すると、JavaScript が DOM を変更するときにページの JavaScript を一時停止できます。  

### <a name="break-on-attribute-modifications"></a>属性の変更時のブレーク  

ノードの属性が変更される JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **属性の変更時にブレーク]** で **、Sauerkraut を右クリックし、[** 検査] を **選択します**。  
    1.  DOM ツリーで、マウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[属性の変更時にブレーク `<li id="target">Sauerkraut</li>` **]**  >  **を選択します**。  オプションが [表示されない場合は](#appendix-missing-options) 、[付録: 不足しているオプション] に移動します。
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="属性の変更時のブレーク" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **属性の変更時のブレーク**  
        :::image-end:::  
        
    1.  次の手順では、ページのコードを一時停止するボタンを選択するように指示されます。  ページが一時停止すると、ページをスクロールできなくなりました。  ページを再 **びスクロール可能** にするには、[スクリプトの再開] ![ \( Resume Script ][ImageResumeScriptIcon] \) を選択する必要があります。
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="スクリプトの実行を再開する場所" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           スクリプトの実行を再開する場所  
        :::image-end:::  
        
    1.  上の [ **背景の設定]** ボタンを選択します。  これにより、ノード `style` の属性がに設定されます `background-color:thistle` 。  DevTools はページを一時停止し、属性が変更されたコードを強調表示します。  
    1.  前述 **したように、[スクリプトの再開** ]\( ![ Resume Script ][ImageResumeScriptIcon] \)を選択します。  
    
### <a name="break-on-node-removal"></a>ノードの削除時のブレーク  

特定のノードを削除するときに一時停止する場合は、ノード削除ブレークポイントを使用します。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **ノードの削除時にブレーク]** で、[ニューロマンサー] を **右クリックし、[** 検査] を **選択します**。  
    1.  DOM ツリーで、マウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[ノードの削除] を `<li id="target">Neuromancer</li>` ****  >  **選択します**。  オプションが [表示されない場合は](#appendix-missing-options) 、[付録: 不足しているオプション] に移動します。  
    1.  上の [ **削除]** ボタンを選択します。  DevTools はページを一時停止し、ノードを削除したコードを強調表示します。  
    1.  [ **スクリプトの再開** \( ![ Resume Script ][ImageResumeScriptIcon] \) ] を選択します。  
    
### <a name="break-on-subtree-modifications"></a>サブツリーの変更時のブレーク  

サブツリー変更ブレークポイントをノードに置いた後、ノードの子孫が追加または削除されると、DevTools はページを一時停止します。  

1.  [DOM の例を開きます](#open-dom-examples)。  
1.  [ **サブツリーの変更時にブレーク] で**、[深部の火] を右クリック **し、[** 検査] を **選択します**。  
    1.  DOM ツリーで、上のノードにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[サブツリーの変更時にブレーク] `<ul id="target">` `<li>A Fire Upon the Deep</li>` ****  >  **を選択します**。  オプションが表示されない場合は、[付録: 不足 [しているオプション] に移動します](#appendix-missing-options)。  
    1.  [子 **の追加] を選択します**。  ノードがリストに追加された `<li>` ため、コードは一時停止します。  
    1.  [ **スクリプトの再開** \( ![ Resume Script ][ImageResumeScriptIcon] \) ] を選択します。  
    
## <a name="next-steps"></a>次の手順  

これは、DevTools の DOM 関連の機能のほとんどをカバーしています。  他の機能を見つけるには、DOM ツリーのノードをホバーし、コンテキスト メニュー \(右クリック\) を開き、このチュートリアルで説明していない他のオプションを試します。  [要素] [パネルのキーボード ショートカットに移動します][DevToolsShortcutsElements]。  

[Microsoft Edge DevTools][MicrosoftEdgeDevTools]のホームページを参照して、DevTools で実行できるその他の操作について説明します。  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <a name="appendix-html-versus-the-dom"></a>付録: HTML と DOM の比較  

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
      現時点では HTML と同じように見えますが、HTML の下部で参照されるスクリプトで次のコード スニペットが実行されるとします。  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      そのコードはノードを削除 `h1` し、DOM に `p` 別のノードを追加します。  これで、完全な DOM に次の一覧が表示されます。  
      
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
1.  Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.  Your viewport scrolls back up so that the **Magritte** node is displayed.  If you the **Scroll into view** option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <a name="appendix-missing-options"></a>付録: 不足しているオプション  

このチュートリアルの手順の多くは、DOM ツリーのノードにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、ポップアップするコンテキスト メニューからオプションを選択するように指示します。  コンテキスト メニューの指定したオプションが表示されない場合は、ノード のテキストから離れて、コンテキスト メニュー \(右クリック\) を開きます。  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="すべてのオプションが表示されない場合の選択先" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   すべてのオプションが表示されない場合の選択先  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \(Chromium\) Developer Tools |Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "CSS の表示と変更の開始|Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-tool-keyboard-shortcuts "要素ツールのキーボード ショートカット - Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (クロム) DevTools DOM の例 |Glitch"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要|MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
