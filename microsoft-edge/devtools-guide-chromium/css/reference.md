---
title: CCS リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4f0370b83d8c939476a1ed378dbdf750101c9527
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843971"
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



CSS の表示と変更に関連する Microsoft Edge DevTools 機能の包括的な参照で、新しいワークフローを見つけます。  

基本的な説明については、「 [CSS の表示と変更の概要][DevToolsCSSGetStarted]」を参照してください。  

## 要素を選択する   

DevTools の**要素**パネルでは、一度に1つの要素の CSS を表示したり、変更したりできます。  選択した要素が**DOM ツリー**で強調表示されます。  要素のスタイルが [**スタイル**] ウィンドウに表示されます。  チュートリアルについては、「[要素の CSS を表示][DevToolsCSSGetStartedTutorial]する」をご覧ください。  

> [!NOTE]
> [図 1](#figure-1)では、 `h1` **DOM ツリー**で強調表示されている要素が選択されています。  右側では、要素のスタイルが [**スタイル**] ウィンドウに表示されます。  左側では、要素はビューポートで強調表示されていますが、現在は**DOM ツリー**の上にマウスが置かれているためです。  

> ##### 図 1  
> 選択された要素の例  
> ![選択された要素の例][ImageSelectedElement]  

要素を選ぶには、さまざまな方法があります。  

*   ビューポートで要素を右クリックし、[**検査**] を選択します。  
*   Devtools で、[**要素の選択**] をクリックし、 ![ 要素を選択する ][ImageSelectAnElementIcon] か、 `Control` + `Shift` + `C` \ (Windows \) または `Command` + `Shift` + `C` \ (macOS \) を押して、ビューポート内の要素をクリックします。  
*   DevTools で、 **DOM ツリー**の要素をクリックします。  
*   DevTools で、コンソールのようなクエリを実行し、 `document.querySelector('p')` 結果を右クリックして、[**要素パネルで**表示] を選択します。 **Console**  

## CSS の表示   

### ルールが定義されている外部のスタイルシートを表示する   

[**スタイル**] ウィンドウで、CSS ルールの隣にあるリンクをクリックして、ルールを定義する外部のスタイルシートを開きます。  

スタイルシートが縮小されている場合は、「縮小版の[ファイルを読みやすくする][DevToolsJavascriptReferenceFormat]」を参照してください。  

> [!NOTE]
> [図 2](#figure-2)では、をクリックすると `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` 、CSS ルールが定義されているの2行目に移動し `.content h1:first-of-type` ます。  

> ##### 図 2  
> ルールが定義されているスタイルシートの表示  
> ![ルールが定義されているスタイルシートの表示][ImageViewRuleStylesheet]  

### 実際に要素に適用されている CSS のみを表示する   

[**スタイル**] タブには、オーバーライドされた宣言など、要素に適用されるすべての規則が表示されます。  オーバーライドされた宣言に関心がない場合は、[**計算**] タブを使用して、実際に要素に適用されている CSS のみを表示します。  

1.  [要素を選択](#select-an-element)します。  
1.  [**要素**] パネルの [**計算**] タブに移動します。  

> [!NOTE]
> 横長の DevTools ウィンドウでは、[**計算**] タブは存在しません。  [**計算**] タブの内容は、[**スタイル**] タブに表示されます。  

継承されたプロパティは不透明です。  継承されたすべての値を表示するには、[**すべて表示**] チェックボックスをオンにします。  

> [!NOTE]
> [図 3](#figure-3)では、[**計算**] タブには、現在選択されている要素に適用されている CSS プロパティが表示され `h1` ます。  

> ##### 図 3  
> [**計算**] タブ  
> ![[計算] タブ][ImageComputedTab]  

### CSS プロパティがアルファベット順に表示される   

[**計算**] タブを使用します。 「[要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。  

### 継承した CSS プロパティを表示する   

[**計算**] タブの [**すべて表示**] チェックボックスをオンにします。 「[要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。  

### 要素のボックスモデルを表示する   

要素の[ボックスモデル][MDNBoxModel]を表示するには、[**スタイル**] タブに移動します。 DevTools ウィンドウが狭い場合、**ボックスモデル**図はタブの下部に表示されます。  

値を変更するには、その値をダブルクリックします。  

> [!NOTE]
> [図 4](#figure-4)では、[**スタイル**] タブの**ボックスモデル**図は、現在選択されている要素のボックスモデルを示して `h1` います。  

> ##### 図 4  
> **ボックスモデル**図  
> ![ボックスモデル図][ImageBoxModel]  

### 要素の CSS を検索してフィルター処理する   

[**スタイル**] および [**計算**] タブの [**フィルター** ] テキストボックスを使用して、特定の CSS プロパティまたは値を検索します。  

[**計算**] タブで継承されたプロパティも検索するには、[**すべて表示**] チェックボックスをオンにします。  

> [!NOTE]
> [図 5](#figure-5)では、[**スタイル**] タブをフィルター処理して、検索クエリを含むルールのみを表示し `color` ます。  

> ##### 図 5  
> [**スタイル**] タブのフィルター処理  
> ![[スタイル] タブのフィルター処理][ImageStylesFilter]  

> [!NOTE]
> [図 6](#figure-6)では、[**計算**] タブにフィルターが適用され、検索クエリを含む宣言のみが表示され `100%` ます。  

> ##### 図 6  
> **計算**されたタブのフィルター処理  
> ![計算されたタブのフィルター処理][ImageComputerFilter]  

### 擬似クラスの切り替え   

擬似クラスを、、、、またはのように切り替えるに `:active` `:focus` は、次の操作を `:hover` `:visited` 行います。  

1.  [要素を選択](#select-an-element)します。  
1.  [**要素**] パネルで、[**スタイル**] タブに移動します。  
1.  [ **: Hov**] をクリックします。  
1.  有効にする擬似クラスを確認します。  

> [!NOTE]
> [図 7](#figure-7)で、 `:hover` 擬似クラスを切り替えます。  ビューポートで、宣言が要素に適用されていることを確認し `background-color: cornflowerblue` ます。これは、要素が実際にマウスをポイントしていない場合でも同様です。  

> ##### 図 7  
> `:hover`擬似クラスの切り替え  
> ![: Hover 擬似クラスの切り替え][ImagePseudoClass]  

インタラクティブなチュートリアルについては、「[クラスに疑似状態を追加する][DevToolsCSSGetStartedAddPseudoState]」をご覧ください。 

### 印刷モードでページを表示する   

印刷モードでページを表示するには、次の操作を行います。  
1.  [コマンドメニューを開き][DevToolsCommandMenu]ます。  
1.  入力を開始し `Rendering` 、を選択し `Show Rendering` ます。  
1.  [ **CSS メディアのエミュレート**] ドロップダウンで、[**印刷**] を選びます。  

### [カバレッジ] タブで使用済みおよび未使用の CSS を表示する   

[カバレッジ] タブには、ページで実際に使用されている CSS が表示されます。  

1.  `Control` + `Shift` + `P` `Command` + `Shift` + `P` コマンドメニューを開くには、devtools がフォーカスされている状態で、\ (Windows \) または \ (macOS \) を押します。  
1.  入力 `coverage` を開始し、[**カバレッジの表示**] を選択します。  [カバー] タブが表示されます。  
    
    > ##### 図 8  
    > [コマンド] メニューから [カバレッジ] タブを開く  
    > ![[コマンド] メニューから [カバレッジ] タブを開く][ImageCommandMenu]  
    
    > ##### 図 9  
    > [カバレッジ] タブ  
    > ![[カバレッジ] タブ][ImageCoverageEmpty]  
    
1.  [インストルメント化の開始] をクリックし **、ページを更新**して ![ インストルメントの範囲を開始し、ページを更新し ][ImageRefreshIcon] ます。  ページの更新と [カバレッジ] タブには、ブラウザーが読み込む各ファイルからの CSS (および JavaScript \) の使用量の概要が表示されます。  緑色は、使用されている CSS を表します。  赤は未使用の CSS を示します。  
    
    > ##### 図 10  
    > CSS (および JavaScript) が使用されていて未使用かどうかの概要  
    > ![CSS (および JavaScript) が使用されていて未使用かどうかの概要][ImageCoverageOverview]  

1.  CSS ファイルをクリックすると、使用する CSS の1行ずつの分解が表示されます。  
    
    > [!NOTE]
    > [図 11](#figure-11)では、145から147、149から151まで `b66bc881.site-ltr.css` は使用されていませんが、行163から166に使用されています。  
    
    > ##### 図 11  
    > 使用されている、未使用の CSS の行単位の内訳  
    > ![使用されている、未使用の CSS の行単位の内訳][ImageCoverageDetail]  
    
### 印刷プレビューモードの強制   

「 [DevTools を印刷プレビューモードに強制][DevToolsCssPrintPreview]する」をご覧ください。  

## CSS を変更する   

<!-- todo s/CSS declaration/declaration/ -->  

### 要素に CSS 宣言を追加する   

宣言の順序は要素のスタイルに影響を与えるため、宣言をさまざまな方法で追加することができます。  

*   [インライン宣言を追加](#add-an-inline-declaration)します。  要素の HTML に属性を追加することと同じです `style` 。  
*   [スタイルルールに宣言を追加](#add-a-declaration-to-a-style-rule)します。  

**使用するワークフロー** ほとんどのシナリオでは、通常、インライン宣言ワークフローを使用します。  インライン宣言は外部の宣言よりも高いため、インラインワークフローによって、変更が予期したとおりに要素に反映されるようになります。  詳細については、「[セレクターの種類][MDNSelectorTypes]」を参照してください。  

要素のスタイルをデバッグしていて、宣言がさまざまな場所で定義されている場合に何が起こるかを明確にテストする必要がある場合は、他のワークフローを使用します。  

#### インライン宣言を追加する   

インライン宣言を追加するには、次の操作を行います。  

1.  [要素を選択](#select-an-element)します。  
1.  [**スタイル**] ウィンドウで、[**スタイル**] セクションのかっこの間をクリックします。  カーソルがフォーカスされ、テキストの入力が可能になります。  
1.  プロパティ名を入力し、キーを押し `Enter` ます。  
1.  そのプロパティに有効な値を入力して、キーを押し `Enter` ます。  **DOM ツリー**で、 `style` 属性が要素に追加されていることを確認します。  

> [!NOTE]
> [図 12](#figure-12)では、 `margin-top` 選択した `background-color` 要素に and プロパティが適用されています。  **DOM ツリー**で、宣言が要素の属性に反映されていることを確認し `style` ます。  

> ##### 図 12  
> インライン宣言の追加  
> ![インライン宣言の追加][ImageInlineDeclarations]  

#### スタイルルールに宣言を追加する   

既存のスタイルルールに宣言を追加するには、次の操作を行います。  

1.  [要素を選択](#select-an-element)します。  
1.  [**スタイル**] ウィンドウで、宣言を追加するスタイルルールのかっこの間をクリックします。  カーソルがフォーカスされ、テキストの入力が可能になります。  
1.  プロパティ名を入力し、キーを押し `Enter` ます。  
1.  そのプロパティに有効な値を入力して、キーを押し `Enter` ます。  

> ##### 図 13  
> `border-bottom-style:groove`スタイルルールへの宣言の追加  
> ![スタイルルールへの宣言の追加][ImageAddDeclarationExistingRule]  

### 宣言の名前または値を変更する   

宣言の名前または値をダブルクリックして変更します。  すばやく値を増減するためのショートカットキーについては、「[宣言の値を変更](#change-declaration-values-with-keyboard-shortcuts)する」を参照してください `0.1` `1` `10` `100` 。  

> ##### 図 14  
> の値を変更する `border-bottom-style`  
> ![宣言の値を変更する][ImageAddDeclarationExistingRule2]  

### キーボードショートカットを使用して宣言の値を変更する   

宣言の値を編集しているときに、次のショートカットキーを使用して、値を固定金額でインクリメントできます。  

*   [ `Alt` + `Up` \ (Windows \)] または [ `Option` + `Up` \ (macOS \)] を押して、増分 `0.1` します。  
*   キーを押して、 `Up` 値をから `1` 、または現在の値の間の範囲に変更し `0.1` `-1` `1` ます。  
*   を押し `Shift` + `Up` てインクリメント `10` します。  
*   `Shift` + `Page Up` \ (Windows \) または `Shift` + `Command` + `Up` \ (macOS \) キーを押して、値を増やし `100` ます。  

減分も動作します。  `Up`上記で説明した各インスタンスをに置き換え `Down` ます。  

### 要素にクラスを追加する   

要素にクラスを追加するには、次の操作を行います。  

1.  **DOM ツリー**で[要素を選択](#select-an-element)します。  
1.  [ **Cls**] をクリックします。  
1.  [ **Add New class** ] テキストボックスにクラスの名前を入力します。  
1.  キーを押し `Enter` ます。  

> ##### 図 15  
> [**要素クラス**] ウィンドウ  
> ![[要素クラス] ウィンドウ][ImageElementClasses]  

### クラスの切り替え   

要素のクラスを有効または無効にするには、次の操作を行います。  

1.  **DOM ツリー**で[要素を選択](#select-an-element)します。  
1.  [**要素クラス**] ペインを開きます。  「[要素にクラスを追加する」を](#add-a-class-to-an-element)ご覧ください。  [**新しいクラスの追加**] テキストボックスの下には、この要素に適用されているすべてのクラスが表示されます。  
1.  有効または無効にするクラスの横にあるチェックボックスをオンにします。  

### スタイルルールを追加する   

新しいスタイルルールを追加するには、次の操作を行います。  

1.  [要素を選択](#select-an-element)します。  
1.  [**新しいスタイルルール**] をクリックし ![ ][ImageNewStyleRuleIcon] ます。  DevTools は、**要素のスタイル**ルールの下に新しいルールを挿入します。  

> [!NOTE]
> [図 16](#figure-16)では、 `h1.devsite-page-title` [**新しいスタイルルール**] をクリックした後でスタイルルールが追加されます。  

> ##### 図 16  
> 新しいスタイルルールを追加する  
> ![新しいスタイルルールを追加する][ImageStyleRule]  

#### ルールを追加するスタイルを選択する   

[新しいスタイルルールを追加](#add-a-style-rule)するときに、[**新しい**スタイルルール] をクリックしたままにして、 ![ ][ImageNewStyleRuleIcon] スタイルルールを追加するスタイルを選択します。  

> ##### 図 17  
> スタイルシートの選択  
> ![スタイルシートの選択][ImageChooseStylesheet]  

#### 特定の場所にスタイルルールを追加する   

[**スタイル**] タブの特定の場所にスタイルルールを追加するには、次の操作を行います。  

1.  新しいスタイルルールを追加する場所のすぐ上のスタイルルールにマウスポインターを置きます。  
1.  [[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [スタイルルールの挿入] の下にある [**スタイルルール**の挿入] をクリックし ![ ][ImageNewStyleRuleIcon] ます。  

> ##### 図18  
> **下にスタイルルールを挿入する**  
> ![下にスタイルルールを挿入する][ImageInsertStyleRuleBelow]  

### [その他の操作] ツールバーを表示する   

[**その他のアクション**] ツールバーでは、次の操作を実行できます  

*   優先するスタイルルールのすぐ下にスタイルルールを挿入します。  
*   `background-color` `color` `box-shadow` `text-shadow` フォーカスされているスタイルルールに、、、、または宣言を追加します。  

[**その他の操作**] ツールバーを表示するには:  

1.  [**スタイル**] タブで、スタイルルールの上にマウスポインターを置きます。  **その他の操作** `...`[スタイルルール] セクションの右下に公開されます。  
    
    > [!NOTE]
    > [図 19](#figure-19)では、スタイルルールにマウスポインター `.header-holder.has-default-focus` を合わせると、[スタイルルール] セクションの右下に [**その他のアクション**] が現れます。  
    
    > ##### 図19  
    > **その他のアクション**を見つける  
    > ![その他のアクションを見つける][ImageRevealMore]  
    
1.  他の**アクション**をマウスでポイント `...` すると、上記のアクションが表示されます。  
    
    > [!NOTE]
    > [**次のスタイルルールの挿入**アクションを実行すると、**その他の操作**をマウスでポイントしたときに、次のように  
    
    > ##### 図20  
    > [**その他の操作**] ツールバー  
    > ![[その他の操作] ツールバー][ImageInsertStyleRuleBelow2]  
    
### 宣言を切り替える   

1つの宣言のオンとオフを切り替えるには、次の操作を行います。  

1.  [要素を選択](#select-an-element)します。  
1.  [**スタイル**] ウィンドウで、宣言を定義するルールの上にマウスポインターを置きます。  各宣言の横にチェックボックスが表示されます。  
1.  宣言の横にあるチェックボックスをオンまたはオフにします。  宣言をオフにすると、DevTools がその宣言を超えて、アクティブでなくなったことを示します。  

> [!NOTE]
> [図 21](#figure-21)では、 `margin-top` 現在選択されている要素のプロパティがトグルオフになっています。  

> ##### 図21  
> 宣言の切り替え  
> ![宣言の切り替え][ImageToggleDeclaration]  

### 背景色の宣言を追加する   

要素に宣言を追加するには、 `background-color` 次の操作を行います。  

1.  宣言を追加するスタイルルールの上にマウスポインターを置き `background-color` ます。  
1.  [[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [**背景**色の追加] をクリックし ![ ][ImageAddBackgroundColorIcon] ます。  

> ##### 図22  
> **背景色を追加する**  
> ![背景色を追加する][ImageAddBackgroundColor]  

### 色の宣言を追加する   

要素に宣言を追加するには、 `color` 次の操作を行います。  

1.  宣言を追加するスタイルルールの上にマウスポインターを置き `color` ます。  
1.  [[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [**色の追加]** をクリックし ![ ][ImageAddColorIcon] ます。  

> ##### 図23  
> **色を追加する**  
> ![色を追加する][ImageAddColor]  

### ボックスシャドウ宣言を追加する   

要素に宣言を追加するには、 `box-shadow` 次の操作を行います。  

1.  宣言を追加するスタイルルールの上にマウスポインターを置き `box-shadow` ます。  
1.  [[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [**追加ボックスシャドウ**の追加] をクリックし ![ ][ImageAddBoxShadowIcon] ます。  

> ##### 図24  
> **ボックスの影を追加する**  
> ![ボックスの影を追加する][ImageAddBoxShadow]  

### テキストシャドウの宣言を追加する   

要素に宣言を追加するには、 `text-shadow` 次の操作を行います。  

1.  宣言を追加するスタイルルールの上にマウスポインターを置き `text-shadow` ます。  
1.  [[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。  
1.  [**テキストの影**を追加する] をクリックし ![ ][ImageAddTextShadowIcon] ます。  

> ##### 図25  
> **テキストの影を追加する**  
> ![テキストの影を追加する][ImageAddTextShadow]  

### カラーピッカーを使用して色を変更する   

**カラーピッカー**は、変更と宣言のための GUI を提供し `color` `background-color` ます。  

**カラーピッカー**を開くには、次の操作を行います。  

1.  [要素を選択](#select-an-element)します。  
1.  [**スタイル**] タブで、変更する、 `color` `background-color` または同様の宣言を見つけます。  、、 `color` `background-color` または同様の値の左側に、色のプレビューである小さな四角形が表示されています。  
    
    > [!NOTE]
    > [図 26](#figure-26)では、左側の小さな四角形 `rgba(0, 0, 0, 0.7)` はその色のプレビューです。  
    
    > ##### 図26  
    > 色のプレビュー  
    > ![色のプレビュー][ImageColorPreview]  
    
1.  プレビューをクリックして、**カラーピッカー**を開きます。  
    
    > ##### 図27  
    > **色のパレット**  
    > ![色のパレット][ImageColorPicker]  
    
次に、**色のパレット**の各 UI 要素について説明します。  

> ##### 図28  
> カラーピッカーの注釈  
> ![カラーピッカーの注釈][ImageColorPickerAnnotated]  

1.  **網掛け**。  
1.  **スポイト**。  スポイトを使用して[ページの色を設定する方法を](#sample-a-color-off-the-page-with-the-eyedropper)参照してください。  
1.  **クリップボードにコピー**します。  **表示値**をクリップボードにコピーします。  
1.  **表示値**。  色の RGBA、HSLA、または16進表現。  
1.  **カラーパレット**。  これらの四角形のいずれかをクリックして、その四角形の色を変更します。  
1.  **色相**。  
1.  **Opacity**。  
1.  **値スイッチャーを表示**します。  現在の色の RGBA、HSLA、16進表現を切り替えます。  
1.  **カラーパレットスイッチャー**。  [マテリアルデザインパレット][MaterialDesignColorSystem]、カスタムパレット、またはページカラーパレットを切り替えます。  DevTools は、スタイルシートで検出された色に基づいてページカラーパレットを生成します。  

#### スポイトを使用してページの色を設定する   

**カラーピッカー**を開くと、**スポイト** ![ スポイト ][ImageEyedropperIcon] がデフォルトでオンになります。  選択した色をページ上の別の色に変更するには、次の操作を行います。  

1.  ビューポートのターゲットの色の上にマウスポインターを置きます。  
1.  クリックして確認します。  
    
    > [!NOTE]
    > [図 29](#figure-29)では、**色のパレット**に現在の色の値が表示されてい `rgba(0,0,0,0.7)` ます。これは黒に近い値です。  この色は、黒がクリックされたときにビューポートで現在強調表示されている黒に変更する必要があります。  
    
    > ##### 図29  
    > スポイトを使用する  
    > ![スポイトを使用する][ImageUsingEyedropper]  
    
 



<!-- image links -->  

[ImageAddBackgroundColorIcon]: /microsoft-edge/devtools-guide-chromium/media/add-background-color-icon.msft.png  
[ImageAddBoxShadowIcon]: /microsoft-edge/devtools-guide-chromium/media/add-box-shadow-icon.msft.png  
[ImageAddColorIcon]: /microsoft-edge/devtools-guide-chromium/media/add-color-icon.msft.png  
[ImageAddTextShadowIcon]: /microsoft-edge/devtools-guide-chromium/media/add-text-shadow-icon.msft.png  
[ImageEyedropperIcon]: /microsoft-edge/devtools-guide-chromium/media/eyedropper-icon.msft.png  
[ImageNewStyleRuleIcon]: /microsoft-edge/devtools-guide-chromium/media/new-style-rule-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  
[ImageSelectAnElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-an-element-icon.msft.png  

[ImageSelectedElement]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1.msft.png "図 1: 選択した要素の例"  
[ImageViewRuleStylesheet]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1-highlight.msft.png "図 2: ルールが定義されているスタイルシートの表示"  
[ImageComputedTab]: /microsoft-edge/devtools-guide-chromium/media/css-elements-computed-h1.msft.png "図 3: 計算されたタブ"  
[ImageBoxModel]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1-2.msft.png "図 4: ボックスモデル図"  
[ImageStylesFilter]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-filter-color.msft.png "図 5: [スタイル] タブのフィルター処理"  
[ImageComputerFilter]: /microsoft-edge/devtools-guide-chromium/media/css-elements-computed-filter-100.msft.png "図 6: 計算されたタブのフィルター処理"  
[ImagePseudoClass]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-hov-hover.msft.png "図 7: ホバー擬似クラスの切り替え"  
[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-coverage.msft.png "図 8: [コマンド] メニューから [カバレッジ] タブを開く"  
[ImageCoverageEmpty]: /microsoft-edge/devtools-guide-chromium/media/css-console-qs-coverage-empty.msft.png "図 9: [カバレッジ] タブ"  
[ImageCoverageOverview]: /microsoft-edge/devtools-guide-chromium/media/css-console-qs-coverage-run.msft.png "図 10: 使用されている CSS (および JavaScript) の概要"  
[ImageCoverageDetail]: /microsoft-edge/devtools-guide-chromium/media/css-sources-css-coverage.msft.png "図 11: 使用されている CSS と未使用の CSS の行単位の内訳"  
[ImageInlineDeclarations]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-margin-top-background-color.msft.png "図 12: インライン宣言の追加"  
[ImageAddDeclarationExistingRule]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-border-bottom-style.msft.png "図 13: スタイルルールへの宣言の追加"  
[ImageAddDeclarationExistingRule2]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-border-bottom-style-dropdown.msft.png "図 14: 宣言の値を変更する"  
[ImageElementClasses]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-filter-classes.msft.png "図 15: [要素クラス] ウィンドウ"  
[ImageStyleRule]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-style-new.msft.png "図 16: 新しいスタイルルールを追加する"  
[ImageChooseStylesheet]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-style-new-select-exisiting.msft.png "図 17: スタイルシートの選択"  
[ImageInsertStyleRuleBelow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-insert-style-rule-below.msft.png "図 18: スタイルルールを下に挿入する"  
[ImageRevealMore]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-new-rule-styles.msft.png "図 19: その他の操作を確認する"  
[ImageInsertStyleRuleBelow2]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png "図 20: [その他の操作] ツールバー"  
[ImageToggleDeclaration]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-deactivated.msft.png "図 21: 宣言の切り替え"  
[ImageAddBackgroundColor]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-background-color.msft.png "図 22: 背景色を追加する"  
[ImageAddColor]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-color.msft.png "図 23: 色を追加する"  
[ImageAddBoxShadow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-box-shadow.msft.png "図 24: ボックスの影を追加する"  
[ImageAddTextShadow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-text-shadow.msft.png "図 25: テキストの影を追加する"  
[ImageColorPreview]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-overlay-color-box.msft.png "図 26: 色のプレビュー"  
[ImageColorPicker]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-color-picker.msft.png "図 27: 色のパレット"  
[ImageColorPickerAnnotated]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-color-picker-annotated.msft.png "図 28: カラーピッカーの注釈"  
[ImageUsingEyedropper]: /microsoft-edge/devtools-guide-chromium/media/css-color-picker-eye-dropper.msft.png "図 29: スポイトを使用する"  

<!-- links -->  

[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevToolsCSSGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を始める"  
[DevToolsCSSGetStartedAddPseudoState]: /microsoft-edge/devtools-guide-chromium/css/index#add-a-pseudostate-to-a-class "クラスに疑似状態を追加する-CSS の表示と変更の概要"  
[DevToolsCSSGetStartedTutorial]: /microsoft-edge/devtools-guide-chromium/css/index#view-the-css-for-an-element "要素の CSS を表示する-CSS の表示と変更の概要"  
[DevToolsCssPrintPreview]: /microsoft-edge/devtools-guide-chromium/css/print-preview "Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する"  
[DevToolsJavascriptReferenceFormat]: /microsoft-edge/devtools-guide-chromium/javascript/reference#make-a-minified-file-readable "指定したミニファイルを読みやすくします。 JavaScript のデバッグ参照"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "カラーシステム-マテリアルデザイン"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "ボックスモデル |MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "セレクターの種類-特異性 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/css/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
