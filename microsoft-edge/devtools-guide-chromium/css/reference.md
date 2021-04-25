---
description: Microsoft Edge DevTools で CSS を表示および変更するための新しいワークフローについて説明します。
title: CCS リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bddbf14e73f5c29bfd4757c9cd6d255f419c331f
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519332"
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

# <a name="css-reference"></a>CCS リファレンス  

新しいワークフローについては、CSS の表示と変更に関連する Microsoft Edge DevTools 機能の包括的なリファレンスを参照してください。  

基本については、「CSS の表示と変更 [を開始する」に移動します][DevToolsCSSGetStarted]。  

## <a name="choose-an-element"></a>要素を選択する  

**DevTools**の Elements ツールを使用すると、一度に 1 つの要素の CSS を表示または変更できます。  選択した要素が DOM ツリーで **強調表示されます**。  要素のスタイルが [スタイル] ウィンドウ **に表示** されます。  チュートリアルでは、[要素の [CSS を表示する] に移動します][DevToolsCSSGetStartedTutorial]。  

> [!NOTE]
> 次の図では `h1` **、DOM** ツリーで強調表示されている要素が選択された要素です。  右側の要素のスタイルが [スタイル] ウィンドウに **表示** されます。  左側では、要素はビューポートで強調表示されますが、マウスが **現在 DOM**ツリーでマウスポインターを置くためです。  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="選択した要素の例" lightbox="../media/css-elements-styles-h1.msft.png":::
   選択した要素の例  
:::image-end:::  

要素を選択するには、次のいずれかのアクションを使用します。  

*   ビューポートで、要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。  
*   DevTools で、[要素を選択] \( Select **an** element \) を選択するか ![ ](../media/select-an-element-icon.msft.png) `Control` + `Shift` + `C` 、\(Windows、Linux\) または `Command` + `Shift` + `C` \(macOS\) を選択し、ビューポートで要素を選択します。  
*   DevTools で、DOM ツリーの要素を **選択します**。  
*   DevTools で、コンソールのようなクエリを実行し、結果にマウス ポインターを置き、コンテキスト メニュー `document.querySelector('p')` \(右クリック\) を開き、[要素] パネルで [表示] を**選択します**。 ****  

## <a name="view-css"></a>CSS の表示  

### <a name="view-the-external-stylesheet-where-a-rule-is-defined"></a>ルールが定義されている外部スタイルシートを表示する  

[スタイル **] ウィンドウ** で、CSS ルールの横にあるリンクを選択して、ルールを定義する外部スタイルシートを開きます。  スタイルシートは、[ソース] ツール **の [エディター** ] ウィンドウ **で開** きます。  

スタイルシートが minified の場合は、[エディター] ウィンドウの下部にある [ **書式]** ![ ](../media/format-icon.msft.png) \( Format \) ボタン **を選択** します。  詳細については、「ミニマリストの JavaScript ファイルをプリティプリントで再フォーマット [する」に移動します][DevToolsJavascriptReferenceFormat]。  

> [!NOTE]
> 次の図では、選択した後、CSS ルールが定義されている `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 行 2 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` `.content h1:first-of-type` に移動します。  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="ルールが定義されているスタイルシートの表示" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  ルールが定義されているスタイルシートの表示  
:::image-end:::  

### <a name="view-only-the-css-that-is-actually-applied-to-an-element"></a>要素に実際に適用される CSS のみを表示する  

[ **スタイル** ] パネルには、オーバーライドされた宣言を含む、要素に適用されるすべてのルールが表示されます。  オーバーライドされた宣言に興味がない場合は、[計算] パネル**** を使用して、要素に実際に適用されている CSS のみを表示します。  

1.  [要素を選択します](#choose-an-element)。  
1.  [要素] **ツールの [** 計算] パネル **に移動** します。  

> [!NOTE]
> ワイドな DevTools ウィンドウでは、[ **計算] パネル** は存在しません。  [計算] パネル **の内容** が [スタイル] パネル **に表示** されます。  

継承されたプロパティは不透明です。  継承された値を表示するには、[すべて表示] **チェック ボックスを** オンにします。  

> [!NOTE]
> 次の図では、[計算] **パネル** に、現在選択されている要素に適用されている CSS プロパティが表示 `h1` されます。  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="[計算] パネル" lightbox="../media/css-elements-computed-h1.msft.png":::
   [ **計算]** パネル  
:::image-end:::  

### <a name="view-css-properties-in-alphabetical-order"></a>CSS プロパティをアルファベット順に表示する  

[計算 **] パネルを使用** します。  [要素 [に実際に適用される CSS のみを表示する] に移動します](#view-only-the-css-that-is-actually-applied-to-an-element)。  

### <a name="view-inherited-css-properties"></a>継承された CSS プロパティの表示  

[計算] **パネルの** [すべて表示 **] チェック ボックスをオン** にします。  [要素 [に実際に適用される CSS のみを表示する] に移動します](#view-only-the-css-that-is-actually-applied-to-an-element)。  

### <a name="view-the-box-model-for-an-element"></a>要素のボックス モデルを表示する  

要素の [ボックス モデルを表示][MDNBoxModel] するには、[スタイル] パネル **に移動** します。  DevTools ウィンドウが狭い場合、 **ボックス モデル** 図はパネルの下部に表示されます。  

値を変更するには、値を選択して編集します。  

> [!NOTE]
> 次の図では、[スタイル **]** パネルのボックス モデル **図に、** 現在選択されている要素のボックス モデルが表示 `h1` されています。  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="Box モデル図" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   Box**モデル図**  
:::image-end:::  

### <a name="search-and-filter-the-css-of-an-element"></a>要素の CSS を検索してフィルター処理する  

[スタイル]**パネルと**[計算****] パネル**の [** フィルター] テキスト ボックスを使用して、特定の CSS プロパティまたは値を検索します。  

[計算] パネルで継承されたプロパティも **検索** するには、[すべて表示] **チェック ボックスをオン** にします。  

> [!NOTE]
> 次の図では **、[スタイル]** パネルがフィルター処理され、検索クエリを含むルールだけが表示されます `color` 。  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="[スタイル] パネルをフィルター処理する" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   [スタイル] **パネルをフィルター** 処理する  
:::image-end:::  

> [!NOTE]
> 次の図では、[ **計算** ] パネルがフィルター処理され、検索クエリを含む宣言だけが表示されます `100%` 。  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="[計算] パネルをフィルター処理する" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   [計算 **] パネルをフィルター** 処理する  
:::image-end:::  

### <a name="toggle-a-pseudo-class"></a>疑似クラスの切り替え  

次のアクションを実行して、など、擬似クラス `:active` `:focus` `:hover` を切り替える `:visited` 。  

1.  [要素を選択します](#choose-an-element)。  
1.  [要素] **ツール** で、[スタイル] パネル **に移動** します。  
1.  **[:hov] を選択します**。  
1.  有効にする擬似クラスを確認します。  

> [!NOTE]
> 次の図では、擬似クラス `:hover` を切り替える。  ビューポートで、要素が実際にホバーされていない場合でも、宣言が要素に適用されている `background-color: cornflowerblue` のを確認します。  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text=":hover 擬似クラスを切り替える" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   擬似クラス `:hover` を切り替える  
:::image-end:::  

対話型チュートリアルの場合は、[クラスに擬似 [状態を追加する] に移動します][DevToolsCSSGetStartedAddPseudoState]。  

### <a name="view-a-page-in-print-mode"></a>印刷モードでページを表示する  

印刷モードでページを表示するには、次の操作を実行します。  

1.  [コマンド メニューを開きます][DevToolsCommandMenu]。  
1.  入力を開始 `Rendering` して選択します `Show Rendering` 。  
1.  [CSS **メディアのエミュレート] ドロップダウンで** 、[印刷] を **選択します**。  

### <a name="view-used-and-unused-css-with-the-coverage-tool"></a>カバレッジ ツールを使用して、使用されている CSS と未使用の CSS を表示する  

[ **カバレッジ]** ツールには、ページが実際に使用する CSS が表示されます。  

1.  `Control` + `Shift` + `P` DevTools がフォーカスされている間 `Command` + `Shift` + `P` に \(Windows、Linux\) または \(macOS\) を選択してコマンド[メニューを開きます][DevToolsCommandMenu]。  
1.  入力を開始し `coverage` 、[カバレッジの **表示] を選択します**。  [ **カバレッジ]** ツールが表示されます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="コマンド メニューからカバレッジ ツールを開く" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             コマンド メニュー **からカバレッジ** ツールを **開く**  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="カバレッジ ツール" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             カバレッジ**ツール**  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  [ **インストルメントカバレッジの開始] を選択し、** ページ \( インストルメントカバレッジの開始とページの更新 ![ \) を更新 ](../media/refresh-icon.msft.png) します。  ページが更新され、カバレッジ ツール **は** 、ブラウザーが読み込む各ファイルから使用される CSS \(および JavaScript\) の量の概要を示します。  緑色は、使用されている CSS を表します。  赤は未使用の CSS を表します。  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="CSS (および JavaScript) の使用と未使用の量の概要" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       CSS \(and JavaScript\) の使用と使用の概要  
    :::image-end:::  

1.  使用する CSS の行の内訳を表示するには、CSS ファイルを選択します。  
    
    > [!NOTE]
    > 次の図では、145 行から 147 行、149 行から 151 行が使用されているのに対し、 `b66bc881.site-ltr.css` 行 163 ~ 166 は使用されます。  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="使用されている CSS と未使用の CSS の行別の内訳" lightbox="../media/css-sources-css-coverage.msft.png":::
       使用されている CSS と未使用の CSS の行別の内訳  
    :::image-end:::  
    
### <a name="force-print-preview-mode"></a>印刷プレビュー モードの強制  

[[DevTools を印刷プレビュー モードにする] に移動します][DevToolsCssPrintPreview]。  

## <a name="change-css"></a>CSS を変更する  

<!-- todo s/CSS declaration/declaration/ -->  

### <a name="add-a-css-declaration-to-an-element"></a>要素に CSS 宣言を追加する  

宣言の順序は、要素のスタイルに影響します。次の一覧を使用して、さまざまな方法で宣言を追加できます。  

*   [インライン宣言を追加します](#add-an-inline-declaration)。  要素の HTML `style` に属性を追加するのと同じです。  
*   [スタイル ルールに宣言を追加します](#add-a-declaration-to-a-style-rule)。  

**どのワークフローを使用する必要がありますか?** ほとんどのシナリオでは、インライン宣言ワークフローを使用する必要があります。  インライン宣言は外部の宣言よりも高い固有性を持つので、インライン ワークフローによって、予期される要素で変更が確実に有効になります。  詳細については、「セレクターの種類」 [に移動します][MDNSelectorTypes]。  

要素のスタイルをデバッグする場合に、宣言が異なる場所で定義されている場合の処理を具体的にテストする必要がある場合は、他のワークフローを使用します。  

#### <a name="add-an-inline-declaration"></a>インライン宣言の追加  

インライン宣言を追加するには、次のアクションを実行します。  

1.  [要素を選択します](#choose-an-element)。  
1.  [スタイル **] ウィンドウ** で、element.style セクションの角かっこ **を選択** します。  カーソルの焦点が合い、テキストを入力できます。  
1.  プロパティ名を入力して選択します `Enter` 。  
1.  そのプロパティの有効な値を入力し、を選択します `Enter` 。  DOM ツリー **で、** 属性が `style` 要素に追加されたと確認します。  

> [!NOTE]
> 次の図では、選択 `margin-top` した `background-color` 要素にプロパティとプロパティが適用されています。  DOM ツリー **で** 、宣言が要素の属性に反映 `style` されるのを確認します。  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="インライン宣言の追加" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   インライン宣言の追加  
:::image-end:::  

#### <a name="add-a-declaration-to-a-style-rule"></a>スタイル ルールに宣言を追加する  

既存のスタイル ルールに宣言を追加するには、次のアクションを実行します。  

1.  [要素を選択します](#choose-an-element)。  
1.  [スタイル **] ウィンドウ** で、宣言を追加するスタイル ルールのかっこを選択します。  カーソルの焦点が合い、テキストを入力できます。  
1.  プロパティ名を入力して選択します `Enter` 。  
1.  そのプロパティの有効な値を入力し、を選択します `Enter` 。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="スタイル ルールへの宣言の追加" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   スタイル ルール `border-bottom-style:groove` に宣言を追加する  
:::image-end:::  

### <a name="change-a-declaration-name-or-value"></a>宣言の名前または値を変更する  

宣言の名前または値を選択して編集し、変更します。  値を 、または単位で迅速にインクリメントまたはデクリメントするショートカットについては、キーボード ショートカットを使用して宣言値を変更 `0.1` `1` `10` `100` [するに移動します](#change-declaration-values-with-keyboard-shortcuts)。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="宣言の値の変更" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   宣言の値を変更 `border-bottom-style` する  
:::image-end:::  

### <a name="change-declaration-values-with-keyboard-shortcuts"></a>キーボード ショートカットを使用して宣言値を変更する  

宣言の値を編集する場合は、次のキーボード ショートカットを使用して、値を特定の量ずつ増やします。  

*   `Alt` + `Up` \(Windows,Linux\) または `Option` + `Up` \(macOS\) を選択して増分します `0.1` 。  
*   現在 `Up` の値がとの `1` 間の場合、またはによって値を `0.1` 変更する場合に `-1` 選択します `1` 。  
*   によって `Shift` + `Up` 増分する場合に選択します `10` 。  
*   `Shift` + `Page Up` \(Windows,Linux\) または `Shift` + `Command` + `Up` \(macOS\) を選択して値をインクリメントします `100` 。  

デクレメントも機能します。  上記の各インスタンスを `Up` . `Down`  

### <a name="add-a-class-to-an-element"></a>要素にクラスを追加する  

要素にクラスを追加するには、次のアクションを実行します。  

1.  [DOM ツリーで要素](#choose-an-element)**を選択します**。  
1.  **[.cls] を選択します**。  
1.  [新しいクラスの追加] テキスト ボックスにクラス **の名前を** 入力します。  
1.  `Enter` を選択します。  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="[要素クラス] ウィンドウ" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   [ **要素クラス]** ウィンドウ  
:::image-end:::  

### <a name="toggle-a-class"></a>クラスを切り替える  

次のアクションを実行して、要素のクラスを有効または無効にします。  

1.  [DOM ツリーで要素](#choose-an-element)**を選択します**。  
1.  [要素クラス **] ウィンドウを開** きます。  [要素に [クラスを追加する] に移動します](#add-a-class-to-an-element)。  [新しい **クラスの追加]** テキスト ボックスの下には、特定の要素に適用されるクラスすべてが表示されます。  
1.  オンまたはオフにするクラスの横にあるチェック ボックスをオンまたはオフに切り替えます。  

### <a name="add-a-style-rule"></a>スタイル ルールの追加  

新しいスタイル ルールを追加するには、次のアクションを実行します。  

1.  [要素を選択します](#choose-an-element)。  
1.  [ **新しいスタイル ルール** \( ![ 新しいスタイル ルール ](../media/new-style-rule-icon.msft.png) \] を選択します)。  DevTools は、element.style ルールの下に新 **しいルールを挿入** します。  

> [!NOTE]
> 次の図では、[新しいスタイル ルール] を選択した後に、 `h1.devsite-page-title` スタイル ルール **が追加されます**。  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="新しいスタイル ルールを追加する" lightbox="../media/css-elements-styles-style-new.msft.png":::
   新しいスタイル ルールを追加する  
:::image-end:::  

#### <a name="choose-which-stylesheet-to-add-a-rule-to"></a>ルールを追加するスタイルシートを選択する  

新 [しいスタイル ルールを追加する場合](#add-a-style-rule)は、新しいスタイル ルール \( New Style **Rule** \) を選択して保持し、スタイル ルールを追加するスタイルシート ![ ](../media/new-style-rule-icon.msft.png) を選択します。  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="スタイルシートを選択する" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   スタイルシートを選択する  
:::image-end:::  

#### <a name="add-a-style-rule-to-a-specific-location"></a>特定の場所にスタイル ルールを追加する  

[スタイル] パネルの特定の場所にスタイル ルールを追加するには、次のアクション **を実行** します。  

1.  新しいスタイル ルールを追加するスタイル ルールの上にマウス ポインターを移動します。  
1.  [[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。  
1.  [下 **にスタイル ルールを挿入]** を選択します。\( [スタイル ルール ![ の下に挿入] アイコン ](../media/new-style-rule-icon.msft.png) \)。  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="下のスタイル ルールの挿入" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **下のスタイル ルールの挿入**  
:::image-end:::  

### <a name="reveal-the-more-actions-toolbar"></a>[その他の操作] ツールバーを表示する  

[ **その他の操作]** ツールバーでは、次の操作を実行できます。  

*   フォーカスするスタイル ルールの直下にスタイル ルールを挿入します。  
*   フォーカスしている `background-color` スタイル ルールに 、または `color` `box-shadow` `text-shadow` 宣言を追加します。  

次のアクションを実行して、[その他の操作] **ツールバーを表示** します。  

1.  [スタイル **] パネル** で、スタイル ルールをポイントします。  **その他の** アクション \( \) は、スタイル ルール セクションの右下 `...` に表示されます。  
    
    > [!NOTE]
    > 次の図では、スタイル ルールにカーソルを合わせると、[その他のアクション] が [スタイル ルール] セクションの右下 `.header-holder.has-default-focus` に表示されます。 ****  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="その他のアクションを表示する" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       他 **のアクションを表示** する \( `...` \)  
    :::image-end:::  
    
1.  上記のアクション **を表示するには** 、 `...` その他のアクション \( \) にカーソルを合わせる。  
    
    > [!NOTE]
    > [ **スタイル ルールの下に挿入]** アクションは、[その他のアクション] にカーソルを合わせると **表示されます**。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="[その他の操作] ツールバー" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       [ **その他の操作]** ツールバー  
    :::image-end:::  
    
### <a name="toggle-a-declaration"></a>宣言を切り替える  

folllwoing アクションを完了して、\(または off\) の 1 つの宣言を切り替えます。  

1.  [要素を選択します](#choose-an-element)。  
1.  [スタイル **] ウィンドウ** で、宣言を定義するルールをポイントします。  各宣言の横にチェック ボックスが表示されます。  
1.  宣言の横にあるチェックボックスを \(または uncheck\) にチェックします。  宣言のチェックを外した場合、DevTools は宣言をクロスアウトして、アクティブでなくなったと示します。  

> [!NOTE]
> 次の図では、現在 `margin-top` 選択されている要素のプロパティがオフに切り替えされています。  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="宣言を切り替える" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   宣言を切り替える  
:::image-end:::  

### <a name="add-a-background-color-declaration"></a>背景色の宣言を追加する  

要素に宣言を追加するには、次 `background-color` のアクションを実行します。  

1.  宣言を追加するスタイル ルールにカーソルを `background-color` 合わせる。  
1.  [[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。  
1.  [ **背景色の追加** ]\( ![ [背景色の追加] アイコン ](../media/add-background-color-icon.msft.png) \) を選択します。  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="背景色の追加" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **背景色の追加**  
:::image-end:::  

### <a name="add-a-color-declaration"></a>色の宣言を追加する  

要素に宣言を追加するには、次 `color` のアクションを実行します。  

1.  宣言を追加するスタイル ルールにカーソルを `color` 合わせる。  
1.  [[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。  
1.  [ **色の追加** ] \( ![ [色の追加] ](../media/add-color-icon.msft.png) アイコン \) を選択します。  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="色の追加" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **色の追加**  
:::image-end:::  

### <a name="add-a-box-shadow-declaration"></a>ボックス シャドウ宣言を追加する  

要素に宣言を追加するには、次 `box-shadow` のアクションを実行します。  

1.  宣言を追加するスタイル ルールにカーソルを `box-shadow` 合わせる。  
1.  [[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。  
1.  [Add **Box Shadow** \( ![ Add Box Shadow icon ](../media/add-box-shadow-icon.msft.png) \] )を選択します。  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="ボックス シャドウの追加" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **ボックス シャドウの追加**  
:::image-end:::  

### <a name="add-a-text-shadow-declaration"></a>テキスト シャドウ宣言を追加する  

要素に宣言を追加するには、次 `text-shadow` のアクションを実行します。  

1.  宣言を追加するスタイル ルールにカーソルを `text-shadow` 合わせる。  
1.  [[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。  
1.  [テキスト **シャドウの追加** ]\( ![ [テキスト シャドウの追加] アイコン ](../media/add-text-shadow-icon.msft.png) \) を選択します。  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="テキスト シャドウの追加" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **テキスト シャドウの追加**  
:::image-end:::  

### <a name="change-colors-with-the-color-picker"></a>カラー ピッカーを使用して色を変更する  

Color **Picker は** 、変更と宣言のための GUI `color` `background-color` を提供します。  

次のアクションを実行して、カラー ピッカー **を開きます**。  

1.  [要素を選択します](#choose-an-element)。  
1.  [スタイル **] パネル** で、変更する `color` 、 `background-color` 、または類似の宣言を探します。  、 、または類似の値の左側には、色のプレビューである小さな `color` `background-color` 四角形があります。  
    
    > [!NOTE]
    > 次の図では、左側の小さい四角形 `rgba(0, 0, 0, 0.7)` は、その色のプレビューです。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="色のプレビュー" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       色のプレビュー  
    :::image-end:::  
    
1.  プレビューを選択してカラー ピッカー **を開きます**。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="カラー ピッカー" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       カラー **ピッカー**  
    :::image-end:::  
    
カラー ピッカーの各 UI 要素の次の図と一覧の **descries を示します**。  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="注釈付きカラー ピッカー" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   [ **カラー ピッカー]**(注釈付き)  
:::image-end:::  

:::row:::
   :::column span="1":::
      1  
   :::column-end:::
   :::column span="1":::
      **網掛け**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      2  
   :::column-end:::
   :::column span="1":::
      **スポイト**  
   :::column-end:::
   :::column span="2":::
      詳細については、[スポイトを使用してページから色をサンプリング [する] に移動します](#sample-a-color-off-the-page-with-the-eyedropper)。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      3  
   :::column-end:::
   :::column span="1":::
      **クリップボードにコピー**  
   :::column-end:::
   :::column span="2":::
      表示値 **をクリップボード** にコピーします。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      4  
   :::column-end:::
   :::column span="1":::
      **表示値**  
   :::column-end:::
   :::column span="2":::
      色の RGBA、HSLA、または 16 進表記。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      5  
   :::column-end:::
   :::column span="1":::
      **カラー パレット**  
   :::column-end:::
   :::column span="2":::
      1 つの四角形を選択して、その四角形に色を変更します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      6  
   :::column-end:::
   :::column span="1":::
      **Hue**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      7  
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
      8  
   :::column-end:::
   :::column span="1":::
      **値切り替え機能の表示**  
   :::column-end:::
   :::column span="2":::
      現在の色の RGBA、HSLA、および 16 進表記を切り替える。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      9  
   :::column-end:::
   :::column span="1":::
      **カラー パレット スイッチラー**  
   :::column-end:::
   :::column span="2":::
      マテリアル デザイン パレット [、カスタム パレット][MaterialDesignColorSystem]、またはページカラー パレットを切り替えます。  DevTools は、スタイルシートで見つけた色に基づいてページ カラー パレットを生成します。  
   :::column-end:::
:::row-end:::  

#### <a name="sample-a-color-off-the-page-with-the-eyedropper"></a>スポイトを使用してページ外の色をサンプリングする  

カラー ピッカー **を開く場合**、 **既定では** [スポイト]\( ![ ](../media/eyedropper-icon.msft.png) Eyedropper \) がオンになっています。  次のアクションを実行して、選択した色をページの他の色に変更します。  

1.  ビューポートのターゲットの色にカーソルを合わせる。  
1.  確認を選択します。  
    
    > [!NOTE]
    > 次の図では、 **カラー ピッカーは** 現在の色の値を示しています `rgba(0,0,0,0.7)` 。これは黒に近い値です。  特定の色は、選択後にビューポートで現在強調表示されている黒のバージョンに変更する必要があります。  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="スポイトの使用" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       スポイトの使用  
    :::image-end:::  
    
<!--todo:  add the section on the Angle clock section for What's New 88.  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行|Microsoft Docs"  
[DevToolsCSSGetStarted]: ../css/index.md "CSS の表示と変更の開始|Microsoft Docs"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class "クラスに擬似状態を追加する - CSS の表示と変更の開始|Microsoft Docs"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "要素の CSS を表示する - CSS の表示と変更の開始|Microsoft Docs"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "Microsoft Edge DevTools を印刷プレビュー モード (CSS 印刷メディアの種類) に強制|Microsoft Docs"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#reformat-a-minified-javascript-file-with-pretty-print "ミニマ化された JavaScript ファイルをプリティプリントで再フォーマットする - デバッガー ファイルを使用|Microsoft Docs"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "カラー システム - マテリアル デザイン"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "ボックス モデルの|MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "セレクターの種類 - 固有|MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  