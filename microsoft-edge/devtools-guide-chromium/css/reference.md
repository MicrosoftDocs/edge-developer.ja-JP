---
description: Microsoft Edge DevTools での CSS の表示と変更に関する新しいワークフローについてご確認ください。
title: CCS リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 83edc15549b4f8e668af99a4d95966736aaa0992
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "11204013"
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

# CCS リファレンス  

CSS の表示と変更に関連する Microsoft Edge DevTools 機能の次の包括的なリファレンスで、新しいワークフローについてご確認ください。  

基本的な説明については、「 [CSS の表示と変更の概要][DevToolsCSSGetStarted] 」を参照してください。  

## 要素を選択する  

DevTools の **要素** パネルでは、一度に1つの要素の CSS を表示したり、変更したりできます。  選択した要素が **DOM ツリー**で強調表示されます。  要素のスタイルが [ **スタイル** ] ウィンドウに表示されます。  チュートリアルについては、「 [要素の CSS を表示][DevToolsCSSGetStartedTutorial] する」をご覧ください。  

> [!NOTE]
> 次の図では、 `h1` **DOM ツリー** で強調表示されている要素が選択されています。  右側では、要素のスタイルが [ **スタイル** ] ウィンドウに表示されます。  左側では、要素はビューポートで強調表示されていますが、現在は **DOM ツリー**の上にマウスが置かれているためです。  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-h1.msft.png":::
   選択された要素の例  
:::image-end:::  

次の操作のいずれかを使用して、要素を選択します。  

*   ビューポートで、要素にマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **検査**] を選びます。  
*   Devtools で、[**要素の選択**] \ (要素を選択) を選択する ![ か、 ][ImageSelectAnElementIcon] `Control` + `Shift` + `C` \ (Windows、Linux \) または `Command` + `Shift` + `C` \ (macOS \) を選択し、ビューポートで要素を選択します。  
*   DevTools で、 **DOM ツリー**の要素を選択します。  
*   DevTools で、コンソールのようなクエリを実行し、 `document.querySelector('p')` その結果にポインターを置いてコンテキストメニューを開き (\ を右クリックし)、[**要素パネルで**表示] を選択します。 ****  

## CSS の表示  

### ルールが定義されている外部のスタイルシートを表示する  

[ **スタイル** ] ウィンドウで、CSS ルールの隣にあるリンクを選んで、ルールを定義する外部のスタイルシートを開きます。  

スタイルシートが縮小されている場合は、 [ファイルを読み][DevToolsJavascriptReferenceFormat]やすくするために移動します。  

> [!NOTE]
> 次の図では、選択する `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` と `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` 、 `.content h1:first-of-type` CSS ルールが定義されている [2 行目] に移動します。  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="ルールが定義されているスタイルシートの表示" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  ルールが定義されているスタイルシートの表示  
:::image-end:::  

### 実際に要素に適用されている CSS のみを表示する  

[ **スタイル** ] タブには、オーバーライドされた宣言など、要素に適用されるすべての規則が表示されます。  オーバーライドされた宣言に関心がない場合は、[ **計算** ] タブを使用して、実際に要素に適用されている CSS のみを表示します。  

1.  [要素を選択](#select-an-element)します。  
1.  [**要素**] パネルの [**計算**] タブに移動します。  

> [!NOTE]
> 横長の DevTools ウィンドウでは、[ **計算** ] タブは存在しません。  [ **計算** ] タブの内容は、[ **スタイル** ] タブに表示されます。  

継承されたプロパティは不透明です。  継承されたすべての値を表示するには、[ **すべて表示** ] チェックボックスをオンにします。  

> [!NOTE]
> 次の図では、[ **計算** ] タブに、現在選択されている要素に適用されている CSS プロパティが表示されて `h1` います。  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="[計算] タブ" lightbox="../media/css-elements-computed-h1.msft.png":::
   [ **計算** ] タブ  
:::image-end:::  

### CSS プロパティがアルファベット順に表示される  

[ **計算** ] タブを使用します。 「 [要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。  

### 継承した CSS プロパティを表示する  

[**計算**] タブの [**すべて表示**] チェックボックスをオンにします。 「[要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。  

### 要素のボックスモデルを表示する  

要素の [ボックスモデル][MDNBoxModel] を表示するには、[ **スタイル** ] タブに移動します。 DevTools ウィンドウが狭い場合、 **ボックスモデル** 図はタブの下部に表示されます。  

値を変更するには、値を選んで編集します。  

> [!NOTE]
> 次の図では、[**スタイル**] タブの**ボックスモデル**図は、現在選択されている要素のボックスモデルを示して `h1` います。  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="ボックスモデル図" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   **ボックスモデル**図  
:::image-end:::  

### 要素の CSS を検索してフィルター処理する  

[**スタイル**] および [**計算**] タブの [**フィルター** ] テキストボックスを使用して、特定の CSS プロパティまたは値を検索します。  

[ **計算** ] タブで継承されたプロパティも検索するには、[ **すべて表示** ] チェックボックスをオンにします。  

> [!NOTE]
> 次の図では、[ **スタイル** ] タブをフィルター処理して、検索クエリを含むルールのみを表示してい `color` ます。  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="[スタイル] タブをフィルター処理する" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   [ **スタイル** ] タブをフィルター処理する  
:::image-end:::  

> [!NOTE]
> 次の図では、[ **計算** ] タブをフィルター処理して、検索クエリを含む宣言のみが表示されるようにしてい `100%` ます。  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="計算されたタブをフィルター処理する" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   **計算**されたタブをフィルター処理する  
:::image-end:::  

### 擬似クラスの切り替え  

次の操作を実行して、、、、またはなどの擬似クラスを切り替え `:active` `:focus` `:hover` `:visited` ます。  

1.  [要素を選択](#select-an-element)します。  
1.  [ **要素** ] パネルで、[ **スタイル** ] タブに移動します。  
1.  [ **: Hov**] を選びます。  
1.  有効にする擬似クラスを確認します。  

> [!NOTE]
> 次の図では、 `:hover` 擬似クラスを切り替えます。  ビューポートで、宣言が要素に適用されていることを確認し `background-color: cornflowerblue` ます。これは、要素が実際にマウスをポイントしていない場合でも同様です。  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="切り替え: hover 擬似クラス" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   `:hover`擬似クラスの切り替え  
:::image-end:::  

インタラクティブなチュートリアルについては、「 [クラスに擬似状態を追加][DevToolsCSSGetStartedAddPseudoState]する」を参照してください。  

### 印刷モードでページを表示する  

印刷モードでページを表示するには、次の操作を実行します。  

1.  [コマンドメニューを開き][DevToolsCommandMenu]ます。  
1.  入力を開始し `Rendering` 、を選択し `Show Rendering` ます。  
1.  [ **CSS メディアのエミュレート** ] ドロップダウンで、[ **印刷**] を選びます。  

### [カバレッジ] タブで使用済みおよび未使用の CSS を表示する  

[カバレッジ] タブには、ページで実際に使用されている CSS が表示されます。  

1.  `Control` + `Shift` + `P` Devtools がフォーカスされているときに、[\ (Windows, Linux \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選びます。[コマンドメニューを開き][DevToolsCommandMenu]ます。  
1.  入力 `coverage` を開始し、[ **カバレッジの表示**] を選択します。  [カバー] タブが表示されます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="[コマンド] メニューから [カバレッジ] タブを開く" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             [**コマンド] メニュー**から [**カバレッジ**] タブを開く  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="[カバレッジ] タブ" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             [ **カバレッジ** ] タブ  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  [ **インストルメントの開始] を選択し、ページを更新** し ![ ます (インストルメント化を開始し、ページを更新し ][ImageRefreshIcon] ます)。  ページの更新と [カバレッジ] タブには、ブラウザーが読み込む各ファイルからの CSS (および JavaScript \) の使用量の概要が表示されます。  緑色は、使用されている CSS を表します。  赤は未使用の CSS を示します。  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="CSS (および JavaScript) が使用されていて未使用かどうかの概要" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       CSS (および JavaScript \) が使用されていて未使用である割合の概要  
    :::image-end:::  

1.  CSS ファイルを選択すると、使用する CSS の行ごとの詳細が表示されます。  
    
    > [!NOTE]
    > 次の図では、145 ~ 147、149から151の行 `b66bc881.site-ltr.css` は未使用であり、行163から166に使用されています。  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="使用されている、未使用の CSS の行単位の内訳" lightbox="../media/css-sources-css-coverage.msft.png":::
       使用されている、未使用の CSS の行単位の内訳  
    :::image-end:::  
    
### 印刷プレビューモードの強制  

「 [DevTools を印刷プレビューモードに強制][DevToolsCssPrintPreview]する」をご覧ください。  

## CSS を変更する  

<!-- todo s/CSS declaration/declaration/ -->  

### 要素に CSS 宣言を追加する  

宣言の順序は要素のスタイルに影響を及ぼし、さまざまな方法で宣言を追加するために、次の一覧を使用します。  

*   [インライン宣言を追加](#add-an-inline-declaration)します。  要素の HTML に属性を追加することと同じです `style` 。  
*   [スタイルルールに宣言を追加](#add-a-declaration-to-a-style-rule)します。  

**使用するワークフロー** ほとんどのシナリオでは、通常、インライン宣言ワークフローを使用します。  インライン宣言の内容が外部の宣言よりも高いため、インラインワークフローによって予期される要素で変更が有効になります。  特異性の詳細については、「 [Selector の種類][MDNSelectorTypes]に移動する」を参照してください。  

要素のスタイルをデバッグしていて、宣言がさまざまな場所で定義されている場合に何が起こるかを明確にテストする必要がある場合は、他のワークフローを使用します。  

#### インライン宣言を追加する  

インライン宣言を追加するには、次の操作を実行します。  

1.  [要素を選択](#select-an-element)します。  
1.  [**スタイル**] ウィンドウで、[スタイル] セクションのかっこを選択します **。**  カーソルがフォーカスされ、テキストの入力が可能になります。  
1.  プロパティ名を入力して、を選択し `Enter` ます。  
1.  そのプロパティの有効な値を入力して、を選択し `Enter` ます。  **DOM ツリー**で、 `style` 属性が要素に追加されていることを確認します。  

> [!NOTE]
> 次の図では、 `margin-top` と `background-color` プロパティが選択された要素に適用されています。  **DOM ツリー**で、宣言が要素の属性に反映されていることを確認し `style` ます。  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="インライン宣言を追加する" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   インライン宣言を追加する  
:::image-end:::  

#### スタイルルールに宣言を追加する  

既存のスタイルルールに宣言を追加するには、次の操作を実行します。  

1.  [要素を選択](#select-an-element)します。  
1.  [ **スタイル** ] ウィンドウで、宣言を追加するスタイルルールのかっこの間を選びます。  カーソルがフォーカスされ、テキストの入力が可能になります。  
1.  プロパティ名を入力して、を選択し `Enter` ます。  
1.  そのプロパティの有効な値を入力して、を選択し `Enter` ます。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="スタイルルールへの宣言の追加" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   `border-bottom-style:groove`スタイルルールに宣言を追加する  
:::image-end:::  

### 宣言の名前または値を変更する  

宣言の名前または値を選んで編集し、それを変更します。  すばやく値を増減するためのショートカットキーについては、「 [宣言の値を変更](#change-declaration-values-with-keyboard-shortcuts) する」を参照してください `0.1` `1` `10` `100` 。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="宣言の値を変更する" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   宣言の値を変更する `border-bottom-style`  
:::image-end:::  

### キーボードショートカットを使用して宣言の値を変更する  

宣言の値を編集しているときに、次のショートカットキーを使用して、指定した値だけ値をインクリメントすることができます。  

*   `Alt` + `Up` 増やすには、\ (Windows, Linux \) または `Option` + `Up` \ (macOS \) を選択し `0.1` ます。  
*   値を選択 `Up` する `1` か、 `0.1` 現在の値が and の間にある場合は、を選択し `-1` `1` ます。  
*   [増分] を選択し `Shift` + `Up` `10` ます。  
*   `Shift` + `Page Up` 値をインクリメントするには、\ (Windows, Linux \) または `Shift` + `Command` + `Up` \ (macOS \) `100` を選択します。  

減分も動作します。  `Up`上記で説明した各インスタンスをに置き換え `Down` ます。  

### 要素にクラスを追加する  

要素にクラスを追加するには、次の操作を実行します。  

1.  **DOM ツリー**で[要素を選択](#select-an-element)します。  
1.  **Cls**を選びます。  
1.  [ **Add New class** ] テキストボックスにクラスの名前を入力します。  
1.  を選択し `Enter` ます。  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="[要素クラス] ウィンドウ" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   [ **要素クラス** ] ウィンドウ  
:::image-end:::  

### クラスの切り替え  

要素のクラスを有効または無効にするには、次の操作を実行します。  

1.  **DOM ツリー**で[要素を選択](#select-an-element)します。  
1.  [ **要素クラス** ] ペインを開きます。  「 [要素にクラスを追加する」を](#add-a-class-to-an-element)ご覧ください。  [ **新しいクラスの追加** ] テキストボックスの下には、特定の要素に適用されるすべてのクラスが表示されます。  
1.  有効または無効にするクラスの横にあるチェックボックスをオンにします。  

### スタイルルールを追加する  

新しいスタイルルールを追加するには、次の操作を実行します。  

1.  [要素を選択](#select-an-element)します。  
1.  [ **新しいスタイルルール** ] ([ ![ 新しいスタイルルール]) を選び ][ImageNewStyleRuleIcon] ます。  DevTools は、 **要素のスタイル** ルールの下に新しいルールを挿入します。  

> [!NOTE]
> 次の図では、 `h1.devsite-page-title` **新しいスタイルルール**を選択すると、devtools でスタイルルールが追加されます。  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="新しいスタイルルールを追加する" lightbox="../media/css-elements-styles-style-new.msft.png":::
   新しいスタイルルールを追加する  
:::image-end:::  

#### ルールを追加するスタイルを選択する  

[新しいスタイルルールを追加](#add-a-style-rule)するときに、[**新しい**スタイルルール] (新しいスタイルルール) を選んで保持して、 ![ ][ImageNewStyleRuleIcon] スタイルルールを追加するスタイルを選択します。  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="スタイルシートを選択する" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   スタイルシートを選択する  
:::image-end:::  

#### 特定の場所にスタイルルールを追加する  

[ **スタイル** ] タブの特定の場所にスタイルルールを追加するには、次の操作を実行します。  

1.  新しいスタイルルールを追加する場所のすぐ上のスタイルルールにマウスポインターを置きます。  
1.  [[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [ **スタイルルールの挿入** ] を選択します (下に ![ スタイルルールを挿入し ][ImageNewStyleRuleIcon] ます)。  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="下にスタイルルールを挿入する" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **下にスタイルルールを挿入する**  
:::image-end:::  

### [その他の操作] ツールバーを表示する  

[ **その他の操作** ] ツールバーを使用すると、次の操作を実行できます。  

*   優先するスタイルルールのすぐ下にスタイルルールを挿入します。  
*   `background-color` `color` `box-shadow` `text-shadow` フォーカスされているスタイルルールに、、、、または宣言を追加します。  

[ **その他の操作** ] ツールバーを表示するには、次の操作を実行します。  

1.  [ **スタイル** ] タブで、スタイルルールの上にマウスポインターを置きます。  **** `...` [スタイルルール] セクションの右下にある [その他のアクション] \ (\) が公開されます。  
    
    > [!NOTE]
    > 次の図では、スタイルルールにマウスポインターを合わせる `.header-holder.has-default-focus` と、[スタイルルール] セクションの右下に [ **その他のアクション** ] が現れています。  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="その他のアクションを表示" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       **その他のアクション**を表示 \ ( `...` \)  
    :::image-end:::  
    
1.  上で**** `...` 説明した操作を表示するには、[その他のアクション] (\) をポイントします。  
    
    > [!NOTE]
    > [ **次のスタイルルールの挿入** アクションを実行すると、 **その他の操作**をマウスでポイントしたときに、次のように  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="[その他の操作] ツールバー" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       [ **その他の操作** ] ツールバー  
    :::image-end:::  
    
### 宣言を切り替える  

Folllwoing アクションを完了して \ (またはオフ) の1つの宣言を切り替えます。  

1.  [要素を選択](#select-an-element)します。  
1.  [ **スタイル** ] ウィンドウで、宣言を定義するルールの上にマウスポインターを置きます。  各宣言の横にチェックボックスが表示されます。  
1.  宣言の横にあるチェックボックスをオン (またはオフ) にします。  宣言をオフにすると、DevTools がその宣言を超えて、アクティブでなくなったことを示します。  

> [!NOTE]
> 次の図では、 `margin-top` 現在選択されている要素のプロパティがトグルオフになっています。  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="宣言を切り替える" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   宣言を切り替える  
:::image-end:::  

### 背景色の宣言を追加する  

要素に宣言を追加するには、次の操作を実行し `background-color` ます。  

1.  宣言を追加するスタイルルールの上にマウスポインターを置き `background-color` ます。  
1.  [[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [ **背景色の追加** ] を選択し ![ ます (背景色の追加アイコン ][ImageAddBackgroundColorIcon] \)。  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="背景色を追加する" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **背景色を追加する**  
:::image-end:::  

### 色の宣言を追加する  

要素に宣言を追加するには、次の操作を実行し `color` ます。  

1.  宣言を追加するスタイルルールの上にマウスポインターを置き `color` ます。  
1.  [[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [ **色の追加** ![ ] (色の追加アイコン ][ImageAddColorIcon] \) を選びます。  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="色を追加する" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **色を追加する**  
:::image-end:::  

### ボックスシャドウ宣言を追加する  

要素に宣言を追加するには、次の操作を実行し `box-shadow` ます。  

1.  宣言を追加するスタイルルールの上にマウスポインターを置き `box-shadow` ます。  
1.  [[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [ **Add Box shadow** ] ( ![ box shadow icon を追加) を選び ][ImageAddBoxShadowIcon] ます。  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="ボックスの影を追加する" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **ボックスの影を追加する**  
:::image-end:::  

### テキストシャドウの宣言を追加する  

要素に宣言を追加するには、次の操作を実行し `text-shadow` ます。  

1.  宣言を追加するスタイルルールの上にマウスポインターを置き `text-shadow` ます。  
1.  [[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [ **テキストの影** を追加 ![ ] を選び ][ImageAddTextShadowIcon] ます。  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="テキストの影を追加する" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **テキストの影を追加する**  
:::image-end:::  

### カラーピッカーを使用して色を変更する  

**カラーピッカー**は、変更と宣言のための GUI を提供し `color` `background-color` ます。  

次の操作を実行して、 **カラーピッカー**を開きます。  

1.  [要素を選択](#select-an-element)します。  
1.  [ **スタイル** ] タブで、変更する、 `color` `background-color` または同様の宣言を見つけます。  、、 `color` `background-color` または同様の値の左側に、色のプレビューである小さな四角形が表示されています。  
    
    > [!NOTE]
    > 次の図では、左側の小さな四角形 `rgba(0, 0, 0, 0.7)` がその色のプレビューです。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="色のプレビュー" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       色のプレビュー  
    :::image-end:::  
    
1.  プレビューを選択して、 **カラーピッカー**を開きます。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="色のパレット" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       **色のパレット**  
    :::image-end:::  
    
次の図と、 **カラーピッカー**の各 UI 要素のはを示します。  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="カラーピッカーの注釈" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   **カラーピッカー**の注釈  
:::image-end:::  

:::row:::
   :::column span="1":::
      件  
   :::column-end:::
   :::column span="1":::
      **明るい**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      両面  
   :::column-end:::
   :::column span="1":::
      **スポイト**  
   :::column-end:::
   :::column span="2":::
      詳細については、「 [スポイトを使用してページに色を](#sample-a-color-off-the-page-with-the-eyedropper)設定する」を参照してください。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      -  
   :::column-end:::
   :::column span="1":::
      **クリップボードにコピー**  
   :::column-end:::
   :::column span="2":::
      **表示値**をクリップボードにコピーします。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      4d  
   :::column-end:::
   :::column span="1":::
      **表示値**  
   :::column-end:::
   :::column span="2":::
      色の RGBA、HSLA、または16進表現。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      個  
   :::column-end:::
   :::column span="1":::
      **カラー パレット**  
   :::column-end:::
   :::column span="2":::
      四角形のいずれかを選んで、その四角形に色を変更します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      =  
   :::column-end:::
   :::column span="1":::
      **色相**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      日  
   :::column-end:::
   :::column span="1":::
      **Opacity**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      個  
   :::column-end:::
   :::column span="1":::
      **値の表示スイッチャー**  
   :::column-end:::
   :::column span="2":::
      現在の色の RGBA、HSLA、16進表現を切り替えます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ファイブ  
   :::column-end:::
   :::column span="1":::
      **カラーパレットスイッチャー**  
   :::column-end:::
   :::column span="2":::
      [マテリアルデザインパレット][MaterialDesignColorSystem]、カスタムパレット、またはページカラーパレットを切り替えます。  DevTools は、スタイルシートで検出された色に基づいてページカラーパレットを生成します。  
   :::column-end:::
:::row-end:::  

#### スポイトを使用してページの色を設定する  

**カラーピッカー**を開くと、**スポイト**( ![ スポイト ][ImageEyedropperIcon] ) がデフォルトでオンになります。  選択した色をページ上の別の色に変更するには、次の操作を実行します。  

1.  ビューポートのターゲットの色の上にマウスポインターを置きます。  
1.  [確認] を選びます。  
    
    > [!NOTE]
    > 次の図では、 **色のパレット** に現在の色の値が表示されてい `rgba(0,0,0,0.7)` ます。これは黒に近くなります。  特定の色を、選択した後にビューポートで現在強調表示されている黒のバージョンに変更する必要があります。  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="スポイトを使用する" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       スポイトを使用する  
    :::image-end:::  
    
<!--todo:  add the section on the Angle clock section for What's New 88.  -->  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddBackgroundColorIcon]: ../media/add-background-color-icon.msft.png  
[ImageAddBoxShadowIcon]: ../media/add-box-shadow-icon.msft.png  
[ImageAddColorIcon]: ../media/add-color-icon.msft.png  
[ImageAddTextShadowIcon]: ../media/add-text-shadow-icon.msft.png  
[ImageEyedropperIcon]: ../media/eyedropper-icon.msft.png  
[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageSelectAnElementIcon]: ../media/select-an-element-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevToolsCSSGetStarted]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class "クラスに擬似状態を追加する-CSS の表示と変更を開始する |Microsoft ドキュメント"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "要素の CSS を表示する-CSS の表示と変更の概要 |Microsoft ドキュメント"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "Microsoft Edge DevTools を印刷プレビューモードで強制する (CSS 印刷メディアの種類) |Microsoft ドキュメント"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#make-a-minified-file-readable "ファイルを読みやすくする-JavaScript のデバッグ参照 |Microsoft ドキュメント"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "カラーシステム-マテリアルデザイン"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "ボックスモデル |MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "セレクターの種類-特異性 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  