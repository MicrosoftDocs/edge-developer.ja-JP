---
title: Microsoft Edge の DevTools を支援技術でナビゲートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4bd910fabaab02a632bdc51ade29c5ad6502432a
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931197"
---
<!-- Copyright Rob Dodson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# Microsoft Edge の DevTools を支援技術でナビゲートする  

次の記事では、スクリーンリーダーアクセスなどの支援技術に主に依存しているユーザーを対象として、 [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain]を使用する方法について説明します。  [Microsoft Edge devtools][MicrosoftEdgeDevtoolsMain] は、microsoft edge ブラウザーに組み込まれた web 開発者ツールのスイートです。  Web ページのアクセシビリティを向上させるための DevTools 機能を探している場合は、「アクセシビリティに関する [リファレンス][DevtoolsAccessibilityReference]」を参照してください。  

DevTools のアクセシビリティは、進行中の作業です。  一部のパネルとタブは、他の支援技術よりも機能が向上します。  このガイドでは、最もアクセシビリティの高いパネルと、そのような問題が発生する可能性のある特定の問題について説明します。  

## 概要  

開始する前に、DevTools UI がどのように構成されるかを、メンタルモデルで把握することができます。  DevTools は、 [ARIA のタブリスト][W3CWaiAriaTablist]に整理された一連のパネルに分かれています。  

次に、例を示します。  

*   [ **要素** ] パネルでは、[DOM ノードの表示と変更]、[DevtoolsDomIndexNavigateDomTreeKeyboard]、または [ [CSS][DevtoolsCssIndex]] を使用できます。  
*   [コンソールパネル][DevtoolsConsoleIndex]では、JavaScript ログとライブ編集オブジェクトを読み取ることができます。  

各パネルの [コンテンツ] 領域には、さまざまなツールがあります。ドキュメント内のタブまたはウィンドウと呼ばれることがよくあります。  
たとえば、[ **要素** ] パネルには、イベントリスナー、アクセシビリティツリーなどを検査するための追加のタブが含まれています。  タブとウィンドウの区別は、任意の方法で行うことができます。  1つの用語が表示される唯一の理由は、公式な DevTools のドキュメントの残りの部分との一貫性を維持することです。  

## キーボード ショートカット  

[DevTools のショートカットキーリファレンス] [devtools キーボードショートカット] は、役に立ちます。  ブックマークを作成して、さまざまなパネルを見ながら確認してください。  

## DevTools を開く  

開始するには、「[Microsoft Edge DevTools を開く] [DevTools Open]」を参照してください。  開発ツールを開くには、キーボードショートカットまたはメニュー項目を使用する方法がいくつかあります。  

## パネル間を移動する  

### キーボードを使用して移動する  

*   Devtools が開いている状態で、[ `Control` + `]` \ (Windows \)] または [ `Command` + `]` \ (macOS \)] を選択して、次のパネルにフォーカスを移動します。  
*   `Control` + `[` 前のパネルにフォーカスするには、[\ (Windows \)] または [ `Command` + `[` \ (macOS \)] を選択します。  
*   また、 `Shift` + `Tab` パネルの[ARIA タブリスト][W3CWaiAriaTablist]にフォーカスを移動したり、方向キーを使ってパネルを変更したりすることもできますが、前に説明したショートカットキーを使用する方が高速である場合もあります。  

**既知の問題**  

*   **コンソール**や**パフォーマンス**パネルなどの一部のパネルでは、各パネルがアクティブになるとすぐに、パネルのコンテンツ領域にフォーカスが移動されることがあります。  これにより、方向キーによる移動が困難になることがあります。  
*   選択したパネルの名前はアナウンスされますが、パネル内のフォーカスコンテンツを読み取った後にのみ表示されます。  これにより、簡単に見逃してしまう可能性があります。  

### [コマンドによる移動] メニュー  

特定のパネルにフォーカスを移動するには、 [コマンドメニュー][DevtoolsCommandMenuIndex]を使用します。  

1.  Devtools を開いて、[ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \ **Command Menu**)] を選択してコマンドメニューを開きます。  
    **コマンドメニュー**は、ファジー検索オートコンプリートのコンボボックスです。  
1.  開こうとしているパネルの名前を入力し、キーボードのを使用して `Down Arrow` 適切なオプションに移動します。  
1.  `Enter`コマンドを実行する場合に選択します。  

次の操作を実行して、[ **要素** ] パネルを開きます。  

1.  **コマンドメニュー**を開きます。  
1.  入力 `E` し `L` ます。  [要素の表示] オプションが選択されている **パネル >** ます。  
1.  パネルを開くコマンドを選択して `Enter` 実行します。  

この方法でパネルを開くと、フォーカスはパネルのコンテンツに移動します。  [ **要素** ] パネルの場合は、[ **DOM] ツリー**にフォーカスが移動します。  

## 要素パネル  

### ページ上の要素を検査する  

1.  スクリーンリーダーでカーソルを使って検査する要素に移動します。  
1.  要素のマウスを使って右クリックをシミュレートし、コンテキストメニューを開きます。  
1.  [ **検査** ] オプションを選びます。  これにより、[要素] パネルが開き、DOM ツリーの要素がフォーカスされます ([DevtoolsDomIndexViewDomNodes])。  

**DOM ツリー**は、 [ARIA ツリー][W3CWaiAriaTree]としてレイアウトされています。  例については、「[キーボードによる **DOM ツリー** 内の移動] [DevtoolsDomIndexNavigateDomTreeKeyboard]」をご覧ください。  

### DOM ツリーの要素のコードをコピーする  

1.  **DOM ツリー**のノードにフォーカスがある状態で、ノードをポイントし、コンテキストメニューを開きます (\ を右クリックします)。  
1.  [ **コピー** ] オプションを展開します。  
1.  [ **OuterHTML のコピー**] を選びます。  

**既知の問題**  

*   **OuterHTML をコピー** すると、現在のノードは選ばれず、親ノードが選択されることがよくあります。  ただし、要素の内容は、コピーされた outerHTML にも含まれている必要があります。  

### DOM ツリーの要素の属性を変更する  

*   **DOM ツリー**のノードにフォーカスがある状態で、それを選択し `Enter` て編集できるようにします。  
*   `Tab`属性値の間を移動する場合に選択します。  "スペース" という音声が空のテキスト入力の中にあり、新しい属性値を入力できます。  
*   `Control` + `Enter` `Command` + 変更を承諾して要素の内容全体を読み上げるには、[\ (Windows \)] または [ `Enter` \ (macOS \)] を選択します。  

**既知の問題**  

*   テキスト入力に入力すると、フィードバックは表示されません。  入力ミスをして方向キーを使用して入力を調べると、フィードバックも送信されません。  作業を確認する最も簡単な方法は、変更を承諾した後、要素全体をリッスンしてアナウンスすることです。  

### DOM ツリーの要素の HTML を編集する  

*   **DOM ツリー**のノードにフォーカスがある状態で、それを選択し `Enter` て編集できるようにします。  
*   `Tab`属性値の間を移動する場合に選択します。  たとえば、要素の名前が読み上げられた場合 `h2` は、テキスト入力の内部にあり、要素の型を変更することがあります。  
*   `Control` + `Enter` 変更を反映するには、[\ (Windows \)] または [ `Command` + `Enter` \ (macOS \)] を選択します。  

たとえば、「 `h3` `Control` + `Enter` \ (Windows \)」または「\ (macOS \)」と入力すると、 `Command` + `Enter` 要素の開始タグと終了タグが `h3` 変わります。  

## 要素パネルのタブ  

[ **要素** ] パネルには、要素に適用される CSS や、アクセシビリティツリーの関連する場所を調べるための追加のタブが含まれています。  

*   **DOM ツリー**のノードにフォーカスがある状態で、[ `Tab` **スタイル**] ウィンドウが選択されているという音声が聞こえるまで選択します。  
*   を使用して、 `Right Arrow` その他の使用できるタブを調べます。  

**DOM ツリー**は、属性を持つ要素をフォーカス可能な `href` リンクに変換するため、[ `Tab` **スタイル**] ウィンドウに移動するには、複数回選択する必要がある場合があります。  

**既知の問題**  

[ **DOM ブレークポイント** ] タブと [ **プロパティ** ] タブは、キーボードからアクセスできません。  

### スタイルウィンドウ  

[ **スタイル** ] ウィンドウでは、フィルター処理のスタイルのコントロール、要素の状態の切り替え ([ [アクティブ][MDNActive] ] と [ [フォーカス][MDNFocus]] など)、[クラスの切り替え]、[新しいクラスの追加] を参照します。  また、 **DOM ツリー**でフォーカスが置かれている要素に現在適用されているスタイルを調査し、変更するための強力なスタイル検査ツールも用意されています。  

[ **スタイル** ] ウィンドウについて理解するための重要な概念は、現在選択されているノードのスタイルのみが **DOM ツリー**に表示されることです。  たとえば、ノードのスタイルの検査が終了したのに、ノードのスタイルを確認したいとし `<header>` `<footer>` ます。  そのためには、最初に `<footer>` **DOM ツリー**でノードを選択する必要があります。  「ワークフロー [検査](#inspect-an-element-on-the-page) 」を使用して、ノードの近く (フッター \ などのリンクなど) にあるノードを検査します。これにより、 `footer` **DOM ツリー**がフォーカスされます。次に、キーボードを使用して目的のノードに移動します。  

#### [スタイル] ウィンドウ内の移動  

すべてのスタイルツールは、1つの方法で、または別の方法で [ **スタイル** ] ウィンドウに戻るため、最初にこのツールの専門家になることをお勧めします。  

*   [ **スタイル** ] ウィンドウにフォーカスがある状態で、 `Tab` フォーカスを移動してコンテンツを検索するには、を選択します。  
*   `Tab`最初のスタイルがアクティブになるまで選択します。  スクリーンリーダーを使用している場合、この最初のスタイルはとしてアナウンスされ `element.style {}` ます。  
*   選択 `Down Arrow` すると、スタイルの一覧が目的の順に移動します。  スクリーンリーダーは、CSS ファイルの名前、スタイルが表示される行番号、スタイルの名前の順に、各スタイルを読み上げます。  たとえば、`main.css:233 .card__img {}` と記述します。  
*   `Enter`スタイルを詳しく調べるには、を選択します。  スタイル名の編集可能なバージョンからフォーカスを開始します。  
*   `Tab`各 CSS プロパティの編集可能なバージョンと対応する値の間を移動する場合に選択します。  各スタイルブロックの末尾には、CSS プロパティを追加するために使用できる空白の編集可能なテキストフィールドがあります。  
*   引き続き選択し `Tab` てスタイルの一覧を移動するか、を選択して `Escape` モードを終了し、方向キーを使用して移動することができます。  

その他のショートカットについては、「[スタイル] ウィンドウのキーボードリファレンス] [DevtoolsShortcutsStylesPaneKeyboard]」を参照してください。  

**既知の問題**  

*   編集可能テキストフィールド **を使用** すると、スタイルのリスト内を移動することはできなくなります。  

#### 要素の状態を切り替える  

要素の状態を切り替えるには、次のようにし `:active` `:focus` ます。  

1.  [ **スタイル** ] ウィンドウに移動し `Tab` 、[ **要素の状態の切り替え** ] ボタンにフォーカスが移動するまで選択します。  
1.  `Enter`要素の状態のコレクションを展開する場合に選択します。  要素の状態は、チェックボックスのグループとして表示されます。  
1.  `Tab`最初の状態にフォーカスが置かれるまで選択し `:active` ます。  
1.  `Space`有効にする場合に選択します。  DOM ツリーで現在選択されている要素にスタイルが設定されている場合 `:active` は、それが適用されます。  
1.  保留 `Tab` にして、利用可能なすべての状態を調べます。  

#### 既存のクラスを追加する  

**トグル要素の状態**ボタンの横にあるのは、[**要素クラス**] ボタンです。  フォーカスを移動するには、を選択し `Tab` て選択し `Enter` ます。  フォーカスは、[ **Add New Class**] というラベルの編集テキストフィールドに移動します。  

[ **要素クラス** ] ボタンは、主に既存のクラスを要素に追加するために使用されます。  たとえば、スタイルシートに、という名前のヘルパークラスが含まれている場合、[ `.clearfix` `.` テキストの編集] フィールドの内側を選択して候補の一覧を表示し、を使用して候補を検索することができ `Down Arrow` `.clearfix` ます。  または、クラス名を自分で入力し、それを選択し `Enter` て適用します。  

#### 新しいスタイルルールを追加する  

[ **要素クラス** ] ボタンの横には、 **新しい [スタイルルール** ] ボタンがあります。  フォーカスを移動するには、を選択し `Tab` て選択し `Enter` ます。  フォーカスは、スタイル検査内の編集可能なテキストフィールドに移動します。  フィールドの最初のテキストのコンテンツは、 **DOM ツリー**で選択された要素のタグ名です。  
このフィールドに任意のクラス名を入力して、CSS プロパティを割り当てることができ `Tab` ます。  

### [計算] タブ  

[ **計算** ] タブにフォーカスがある状態で、 `Tab` フォーカスを移動してコンテンツを検索するには、を選択します。  [ **計算** ] タブでは、要素に実際に適用される CSS プロパティを調査するためのコントロールが用意されています。  

<!--todo: add computed tab section when available  -->  

#### 計算されたスタイルをすべて調べる  

`Tab`計算されたスタイルのコレクションに到達するまで選択します。  これらは [ARIA ツリー][W3CWaiAriaTree]として表示されます。  Listbox を展開すると、計算されたスタイルを適用している CSS セレクターが示されます。  これらのセレクターは、特異性によって整理されます。  スクリーンリーダーは、計算値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、セレクターの行番号を通知します。  

**既知の問題**  

*   **フィルター**テキストフィールドを使用する場合、スタイルを検査することはできなくなります。  

### [イベントリスナー] タブ  

[ **要素** ] パネルで、[ **イベントリスナー** ] タブを使って、要素に適用されているイベントリスナーを調べることができます。 [ **スタイル** ] ウィンドウにフォーカスがある状態で、を選択して [ `Right Arrow` **イベントリスナー** ] タブに移動します。  

#### イベントリスナーを調べる  

イベントリスナーは、 [ARIA ツリー][W3CWaiAriaTree]として表示されます。  方向キーを使用して移動することができます。  スクリーンリーダーは、イベントリスナーがアタッチされている DOM オブジェクトの名前に加えて、イベントリスナーが定義されているファイル名と行番号を通知します。  

### アクセシビリティウィンドウ  

[ **アクセシビリティ** ] ウィンドウにフォーカスがある状態で、 `Tab` フォーカスを移動してコンテンツを検索するには、を選択します。  [ [アクセシビリティ] ウィンドウ][DevtoolsAccessibilityReference] には、アクセシビリティツリー、要素に適用される ARIA 属性、計算されたアクセシビリティプロパティを調べるためのコントロールがあります。  

#### アクセシビリティツリー  

**アクセシビリティツリー**は、それぞれが DOM の要素に対応する[ARIA ツリー][W3CWaiAriaTree]として表示され `treeitem` ます。  ツリーは、選んだノードの計算された役割を通知します。  などの一般的な要素 `div` `span` は、ツリーの "genericcontainer" としてアナウンスされます。  方向キーを使用してツリーを走査し、親子関係を調べます。  

**既知の問題**  

*   **アクセシビリティ**ウィンドウで使用される[ARIA ツリー][W3CWaiAriaTree]の種類は、VoiceOver のような macOS のスクリーンリーダーでは Microsoft Edge で適切に公開されないことがあります。  この問題の進捗状況について通知を受け取るには、 [Chromium の問題 #868480][ChromiumIssues868480] をサブスクライブしてください。  
*   Aria の各 **属性** と計算された **プロパティ** のセクションは [aria ツリー][W3CWaiAriaTree]としてマークされますが、現在はフォーカス管理がなく、キーボード操作ができません。  

## 監査パネル  

**監査**パネルでは、パフォーマンス、アクセシビリティ、SEO、その他のカテゴリの多くに関連する一般的な問題をチェックするために、サイトに対して一連のテストを実行する必要があります。  

### 監査を構成して実行する  

1.  **監査**パネルを最初に開いたときに、フォームの最後にある [**監査の実行**] ボタンにフォーカスが置かれます。  既定では、シミュレートされた3G 接続でモバイルエミュレーションを使用して、すべてのカテゴリの監査を実行するようにフォームが構成されています。  
1.  `Shift` + `Tab` 監査設定を変更するには、[参照] モードを使うか、もう一度移動します。  
1.  監査を実行する準備ができたら、[ **監査の実行** ] ボタンに戻り、を選択し `Enter` ます。  
1.  フォーカスが **[キャンセル** ] ボタンでモーダルウィンドウに移動し、監査を終了することができます。  監査が実行され、ページが複数回更新されると、一連の考えが何度も発生する可能性があります。  

**既知の問題**  

*   構成フォームのセクションは、現在、要素でマークアップされていません `fieldset` 。  各セクションに関連付けられているコントロールを確認するために、参照モードで移動した方が簡単な場合があります。  
*   監査の実行が完了しても、現在のところ、またはライブリージョンのお知らせはありません。  通常、30秒ほどかかります。その後、結果に移動することができます。  検索結果を表示するには、参照モードを使用する方法が最も簡単です。  

### 監査レポート内を移動する  

監査レポートは、各監査カテゴリに対応するセクションに整理されます。  レポートが開き、各カテゴリのスコアの一覧が表示されます。  これらのスコアは、関連するセクションにスキップするために使用できるリンクでもあります。  各セクション内には `details` 、成功または失敗の監査に関連する情報が含まれている拡張可能な要素があります。  既定では、失敗した監査のみが表示されます。  各セクションは、 `details` 成功したすべての監査を含む最終要素で終わります。  

新しい監査を実行するには、を使用して `Shift` + `Tab` レポートを終了し、[**監査の実行**] ボタンを探します。  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "アクセシビリティリファレンス |Microsoft ドキュメント"  
<!--[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "The Accessibility pane - Accessibility Reference | Microsoft Docs"  -->  

[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevtoolsConsoleIndex]: ../console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ..[dom/index¥ md # view-dom-ノードの表示]: DOM ノードの表示と変更を開始します。Microsoft ドキュメント "  
[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom# md #-------------------------------------------------------------Microsoft ドキュメント "  
[DevtoolsOpen]:../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント "  
[Dev[キーボードショートカット]:.../shortcuts.md "Microsoft Edge DevTools のショートカットキー |Microsoft ドキュメント "  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts.md # styles-ウィンドウ-キーボードショートカット "[スタイル] ウィンドウのキーボードショートカット-Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント "  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "問題 868480-ARIA ツリーを Mac アクセシビリティの表として公開する"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新しい問題-Microsoft のドキュメント/エッジ-開発者 |GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ": active |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ": フォーカス |MDN"  

[MonorailChromiumIssues]: https://crbug.com "問題-chromium"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (役割)-アクセシビリティの高いリッチインターネットアプリケーション (WAI-ARIA 使った-ARIA) 1.1 |勧告"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "tree (役割)-アクセシビリティの高いリッチインターネットアプリケーション (WAI-ARIA 使った-ARIA) 1.1 |勧告"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) にあり、 [渡 Dodson][RobDodson] によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
