---
title: Microsoft Edge の DevTools を支援技術でナビゲートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5de27e46d20957a1be79f72cf36074291566e6e5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569112"
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



このガイドでは、スクリーンリーダーアクセスなどの支援技術に主に依存しているユーザーが、Microsoft Edge DevTools を使用できるようにすることを目的としています。  Microsoft Edge DevTools は、Microsoft Edge ブラウザーに組み込まれた web 開発者ツールのスイートです。  <!--See [Accessibility Reference][DevtoolsAccessibilityReference] if you are looking for DevTools features related to improving the accessibility of a web page.  -->

<!--todo: add edge devtools index section when available  -->  
<!--todo: add reference (Accessibility Reference) section when available  -->  

DevTools のアクセシビリティは、進行中の作業です。  一部のパネルとタブは、他の支援技術よりも機能が向上します。  このガイドでは、最もアクセシビリティの高いパネルと、そのような問題が発生する可能性のある特定の問題について説明します。  

## 概要   

開始する前に、DevTools UI がどのように構成されるかを、メンタルモデルで把握することができます。  DevTools は、 [ARIA `tablist` ][W3CWaiAriaTablist]に分類される一連のパネルに分かれています。  

次に、例を示します。  

*   [**要素**] パネルでは、DOM ノードの表示と変更、[CSS] [DevtoolsCssIndex] の表示と変更ができます。  
*   [**コンソール**パネル] の [DevtoolsConsoleIndex] では、JavaScript ログとライブ編集オブジェクトを読み取ることができます。  

<!--todo:  add dom nodes (dom nodes) section when available  -->  

各パネルの [コンテンツ] 領域には、さまざまなツールがあります。ドキュメント内のタブまたはウィンドウと呼ばれることがよくあります。  
たとえば、[**要素**] パネルには、イベントリスナー、アクセシビリティツリーなどを検査するための追加のタブが含まれています。  タブとウィンドウの区別は、任意の方法で行うことができます。  1つの用語が表示される唯一の理由は、公式な DevTools のドキュメントの残りの部分との一貫性を維持することです。  

## キーボード ショートカット   

[DevTools のショートカットキーリファレンス] [devtools キーボードショートカット] は、役に立ちます。  ブックマークを作成して、さまざまなパネルを見ながら確認してください。  

## DevTools を開く   

はじめに、[Microsoft Edge DevTools を開く]、[DevTools Open] の順に読みます。  開発ツールを開くには、キーボードショートカットまたはメニュー項目を使用する方法がいくつかあります。  

## パネル間を移動する   

### キーボードを使用して移動する   

*   Devtools を開いて、 `Control` + `]` 次のパネルにフォーカスするには、\ (Windows \) または `Command` + `]` \ (macOS \) を押します。  
*   `Control` + `[` 前のパネルにフォーカスするには、\ (Windows \) または `Command` + `[` \ (macOS \) を押します。  
*   また、 `Shift` + `Tab` パネルの[ `tablist` ARIA][W3CWaiAriaTablist]にフォーカスを移動したり、方向キーを使ってパネルを変更したりすることもできますが、前に説明したショートカットキーを使う方が速い場合もあります。  

#### 既知の問題   

*   **コンソール**や**パフォーマンス**パネルなどの一部のパネルでは、アクティブ化されるとすぐに、コンテンツ領域にフォーカスが移動する場合があります。  これにより、方向キーによる移動が困難になることがあります。  
*   選択したパネルの名前はアナウンスされますが、パネル内のフォーカスコンテンツを読み取った後にのみ表示されます。  これにより、簡単に見逃してしまう可能性があります。  

### [コマンドによる移動] メニュー   

特定のパネルにフォーカスを移動するには、[**コマンドメニュー] [Dev[コマンド] メニュー**インデックス] を使います。  

1.  Devtools を開いている状態で、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押して**コマンドメニュー**を開きます。  
    **コマンドメニュー**は、ファジー検索オートコンプリートのコンボボックスです。  
1.  開こうとしているパネルの名前を入力し、キーボードのを使用して `Down Arrow` 適切なオプションに移動します。  
1.  キーを押して `Enter` コマンドを実行します。  

たとえば、次のように**要素**パネルを開くには、次のようにします。  

1.  **コマンドメニュー**を開きます。  
1.  入力 `E` し `L` ます。  [要素の表示] オプションが選択されている**パネル >** ます。  
1.  キーを押して、 `Enter` パネルを開くコマンドを実行します。  

この方法でパネルを開くと、フォーカスはパネルのコンテンツに移動します。  [**要素**] パネルの場合は、[ **DOM] ツリー**にフォーカスが移動します。  

## 要素パネル   

### ページ上の要素を検査する   

1.  スクリーンリーダーでカーソルを使って検査する要素に移動します。  
1.  要素を右クリックして、コンテキストメニューを開きます。  
1.  [**検査**] オプションを選びます。  これにより、**要素**パネルが開き、 **DOM ツリー**で要素がフォーカスされます。  

<!--todo:  add dom nodes (elements pane) section when available  -->  

**DOM ツリー**は、 [ARIA `tree` ][W3CWaiAriaTree]としてレイアウトされています。  <!--See [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard] for an example.  -->  

<!--todo: add dom index navigation tree section then available  -->

### DOM ツリーの要素のコードをコピーする   

1.  **DOM ツリー**のノードにフォーカスがある状態で、右クリックのコンテキストメニューを開きます。  
1.  [**コピー** ] オプションを展開します。  
1.  [ **OuterHTML のコピー**] を選びます。  

#### 既知の問題   

*   **OuterHTML をコピー**すると、現在のノードは選ばれず、親ノードが選択されることがよくあります。  ただし、要素の内容は、コピーされた outerHTML にも含まれている必要があります。  

### DOM ツリーの要素の属性を変更する   

*   **DOM ツリー**のノードにフォーカスがある状態で、を押して、そのノードを `Enter` 編集可能にします。  
*   を押して `Tab` 、属性値の間を移動します。  "スペース" という音声が空のテキスト入力の中にあり、新しい属性値を入力できます。  
*   `Control` + `Enter` \ (Windows \) または `Command` + `Enter` \ (macOS \) を押すと、変更が反映され、要素の内容全体が読み上げられます。  

#### 既知の問題   

*   テキスト入力に入力すると、フィードバックは表示されません。  入力ミスをして方向キーを使用して入力を調べると、フィードバックも送信されません。  作業を確認する最も簡単な方法は、変更を承諾した後、要素全体をリッスンしてアナウンスすることです。  

### DOM ツリーの要素の HTML を編集する   

*   **DOM ツリー**のノードにフォーカスがある状態で、を押して、そのノードを `Enter` 編集可能にします。  
*   を押して `Tab` 、属性値の間を移動します。  たとえば、"h2" のように、要素の名前が読み上げられたときに、テキスト入力の内部にあり、要素の型を変更することがあります。  
*   `Control` + `Enter` 変更を反映するには、\ (Windows \) または `Command` + `Enter` \ (macOS \) を押します。  

たとえば、「 `h3` `Control` + `Enter` \ (Windows \)」または「\ (macOS \)」と入力すると、 `Command` + `Enter` 要素の開始タグと終了タグが変更され `h3` ます。  

## 要素パネルのタブ   

[**要素**] パネルには、要素に適用される CSS や、アクセシビリティツリーの関連する場所を調べるための追加のタブが含まれています。  

*   **DOM ツリー**のノードにフォーカスがある状態で、[ `Tab` **スタイル**] ウィンドウが選択されているという音声が聞こえるまで、キーを押します。  
*   を使用して、 `Right Arrow` その他の使用できるタブを調べます。  

**DOM ツリー**は、属性を持つ要素をフォーカス可能な `href` リンクに変換するため、[ `Tab` **スタイル**] ウィンドウに到達するために複数回押す必要がある場合があります。  

### 既知の問題   

[ **DOM ブレークポイント**] タブと [**プロパティ**] タブは、キーボードからアクセスできません。  

### スタイルウィンドウ   

[**スタイル**] ウィンドウでは、フィルター処理のスタイル、要素の状態の切り替え ( [`:active`][MDNActive] および [`:focus`][MDNFocus] \)、クラスの切り替え、新しいクラスの追加などのコントロールを検索します。  また、 **DOM ツリー**でフォーカスが置かれている要素に現在適用されているスタイルを調査し、変更するための強力なスタイル検査ツールも用意されています。  

[**スタイル**] ウィンドウについて理解するための重要な概念は、現在選択されているノードのスタイルのみが**DOM ツリー**に表示されることです。  たとえば、ノードのスタイルの検査が終了したのに、ノードのスタイルを確認したいとし `<header>` `<footer>` ます。  そのためには、最初に `<footer>` **DOM ツリー**でノードを選択する必要があります。  「ワークフロー[検査](#inspect-an-element-on-the-page)」を使用して、ノードの近く (フッター \ などのリンクなど) にあるノードを検査します。これにより、 `footer` **DOM ツリー**がフォーカスされます。次に、キーボードを使用して目的のノードに移動します。  

#### [スタイル] ウィンドウ内の移動   

すべてのスタイルツールは、1つの方法で、または別**のスタイルのペインに**接続しているため、最初にこのツールをマスターすることをお勧めします。  

*   [**スタイル**] ウィンドウにフォーカスがある状態で、を押してフォーカスを移動し、内容を確認し `Tab` ます。  
*   `Tab`最初のスタイルがアクティブになるまで、キーを押します。  スクリーンリーダーを使用している場合、この最初のスタイルは "element. style" としてアナウンスされ {} ます。  
*   を押して `Down Arrow` 、スタイルの一覧を目的の順に移動します。  スクリーンリーダーは、CSS ファイルの名前、スタイルが表示される行番号、スタイルの名前の順に、各スタイルを読み上げます。  例: "main .css: 233. card__img {} "  
*   を押して `Enter` 、スタイルを詳しく調べます。  スタイル名の編集可能なバージョンからフォーカスを開始します。  
*   `Tab`各 CSS プロパティの編集可能なバージョンとそれに対応する値の間を移動するには、を押します。  各スタイルブロックの末尾には、CSS プロパティを追加するために使用できる空白の編集可能なテキストフィールドがあります。  
*   キーを押しながら `Tab` スタイルの一覧内を移動するか、またはキーを押して `Escape` このモードを終了し、方向キーを使用して移動することができます。  

その他のショートカットについては、[[スタイル] ウィンドウのキーボードリファレンス] [DevtoolsShortcutsStylesPaneKeyboard] を読んでください。  

##### 既知の問題   

*   編集可能テキストフィールド**を使用**すると、スタイルのリスト内を移動することはできなくなります。  

#### 要素の状態を切り替える   

要素の状態を切り替えるには、次のようにし `:active` `:focus` ます。  

1.  [**スタイル**] ウィンドウに移動し `Tab` 、[**要素の状態の切り替え**] ボタンがフォーカスされるまで押します。  
1.  を押して `Enter` 、要素の状態のコレクションを展開します。  要素の状態は、チェックボックスのグループとして表示されます。  
1.  `Tab`1 つ目の状態にフォーカスが置かれるまで、キーを押し `:active` ます。  
1.  を押して `Space` 有効にします。  DOM ツリーで現在選択されている要素にスタイルが設定されている場合 `:active` は、それが適用されます。  
1.  引き続きキー `Tab` を押して、利用可能なすべての状態を調査します。  

#### 既存のクラスを追加する   

**トグル要素の状態**ボタンの横にあるのは、[**要素クラス**] ボタンです。  [次へ] を押してフォーカスを移動し `Tab` `Enter` ます。  フォーカスは、[ **Add New Class**] というラベルの編集テキストフィールドに移動します。  

[**要素クラス**] ボタンは、主に既存のクラスを要素に追加するために使用されます。  たとえば、スタイルシートに、という名前のヘルパークラスが含まれている場合は、[ `.clearfix` `.` テキストの編集] フィールドの内側を押して候補の一覧を表示し、を使用して `Down Arrow` 候補を検索し `.clearfix` ます。  または、クラス名を自分で入力して、を押して `Enter` 適用します。  

#### 新しいスタイルルールを追加する   

[**要素クラス**] ボタンの横には、**新しい [スタイルルール**] ボタンがあります。  キーを押してフォーカスを移動し `Tab` `Enter` ます。  フォーカスは、スタイル検査内の編集可能なテキストフィールドに移動します。  フィールドの最初のテキストのコンテンツは、 **DOM ツリー**で選択された要素のタグ名です。  
このフィールドに任意のクラス名を入力し、を押して `Tab` CSS プロパティを割り当てることができます。  

### [計算] タブ   

[**計算**] タブにフォーカスがある状態で、を押してフォーカスを移動し、内容を確認し `Tab` ます。  [**計算**] タブでは、要素に実際に適用される CSS プロパティを調査するためのコントロールが用意されています。  

<!--todo: add computed tab section when available  -->  

#### 計算されたスタイルをすべて調べる   

`Tab`計算されたスタイルのコレクションに到達するまで、キーを押します。  これらは[ARIA `tree` ][W3CWaiAriaTree]として表示されます。  Listbox を展開すると、計算されたスタイルを適用している CSS セレクターが示されます。  これらのセレクターは、特異性によって整理されます。  スクリーンリーダーは、計算値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、セレクターの行番号を通知します。  

#### 既知の問題   

*   **フィルター**テキストフィールドを使用する場合、スタイルを検査することはできなくなります。  

### [イベントリスナー] タブ   

[**要素**] パネルで、[**イベントリスナー** ] タブを使って、要素に適用されているイベントリスナーを調べることができます。 [**スタイル**] ウィンドウにフォーカスがある状態で、を押して [ `Right Arrow` **イベントリスナー** ] タブに移動します。  

#### イベントリスナーを調べる   

イベントリスナーは[ARIA `tree` ][W3CWaiAriaTree]として表示されます。  方向キーを使用して移動することができます。  スクリーンリーダーは、イベントリスナーがアタッチされている DOM オブジェクトの名前に加えて、イベントリスナーが定義されているファイル名と行番号を通知します。  

### アクセシビリティウィンドウ   

[**アクセシビリティ**] ウィンドウにフォーカスがある状態で、を押してフォーカスを移動し、内容を確認し `Tab` ます。  [**アクセシビリティ**] ウィンドウ内には、アクセシビリティツリー、要素に適用される ARIA 属性、および計算されたアクセシビリティプロパティを調べるためのコントロールがあります。  

<!--todo: add reference (Accessibility pane) section when available  -->  

#### アクセシビリティツリー   

**アクセシビリティツリー**は[ARIA `tree` ][W3CWaiAriaTree]として表示され、それぞれが `treeitem` DOM 内の要素に対応しています。  ツリーは、選んだノードの計算された役割を通知します。  などの一般的な要素 `div` `span` は、ツリーの "genericcontainer" としてアナウンスされます。  方向キーを使用してツリーを走査し、親子関係を調べます。  

#### 既知の問題   

*   **アクセシビリティ**ウィンドウで使用される[ARIA `tree` ][W3CWaiAriaTree]の種類は、VoiceOver のような macOS のスクリーンリーダーでは Microsoft Edge で適切に公開されない場合があります。  この問題の進捗状況について通知を受け取るには、 [Chromium の問題 #868480][ChromiumIssues868480]をサブスクライブしてください。  
*   各**Aria 属性**と計算された**プロパティ**のセクションは[aria `tree` ][W3CWaiAriaTree]としてマークされていますが、現在はフォーカス管理がないため、キーボード操作はできません。  

## 監査パネル   

**監査**パネルでは、パフォーマンス、アクセシビリティ、SEO、その他のカテゴリの多くに関連する一般的な問題をチェックするために、サイトに対して一連のテストを実行する必要があります。  

### 監査を構成して実行する   

1.  **監査**パネルを最初に開いたときに、フォームの最後にある [**監査の実行**] ボタンにフォーカスが置かれます。  既定では、シミュレートされた3G 接続でモバイルエミュレーションを使用して、すべてのカテゴリの監査を実行するようにフォームが構成されています。  
1.  `Shift` + `Tab` 監査設定を変更するには、[参照] モードを使うか、もう一度移動します。  
1.  監査を実行する準備ができたら、[**監査の実行**] ボタンに戻り、enter キーを押し `Enter` ます。  
1.  フォーカスが **[キャンセル**] ボタンでモーダルウィンドウに移動し、監査を終了することができます。  監査が実行され、ページが複数回更新されると、一連の考えが何度も発生する可能性があります。  

#### 既知の問題   

*   構成フォームのセクションは、現在、要素でマークアップされていません `fieldset` 。  各セクションに関連付けられているコントロールを確認するために、参照モードで移動した方が簡単な場合があります。  
*   監査の実行が完了しても、現在のところ、またはライブリージョンのお知らせはありません。  通常、30秒ほどかかります。その後、結果に移動することができます。  検索結果を表示するには、参照モードを使用する方法が最も簡単です。  

### 監査レポート内を移動する   

監査レポートは、各監査カテゴリに対応するセクションに整理されます。  レポートが開き、各カテゴリのスコアの一覧が表示されます。  これらのスコアは、関連するセクションにスキップするために使用できるリンクでもあります。  各セクション内には `details` 、成功または失敗の監査に関連する情報が含まれている拡張可能な要素があります。  既定では、失敗した監査のみが表示されます。  各セクションは、 `details` 成功したすべての監査を含む最終要素で終わります。  

新しい監査を実行するには、を使用して `Shift` + `Tab` レポートを終了し、[**監査の実行**] ボタンを探します。  

## フィードバック   

*   DevTools バグレポートまたは[Chromium Issue Tracker][MonorailChromiumIssues]への機能要求を送信します。  
*   このドキュメントに関連するフィードバックを[GitHub][GithubEdgeDeveloperNewIssue]に送信します。  

<!-- image links -->  

<!-- links -->  

<!--[DevtoolsAccessibilityReference]: reference.md "Accessibility Reference"  -->  
<!--[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "The Accessibility pane - Accessibility Reference"  -->  

<!--[MicrosoftEdgeDevtoolsIndex]: ../index.md "Microsoft Edge DevTools"  -->  
[Dev[コマンド] メニューインデックス]:...[コマンドの実行] [Microsoft Edge ツール] のコマンドメニューを使用してコマンドを実行する  
[Dev| Consoleindex]:...md "コンソールの概要"  
[DevtoolsCssIndex]:.../css/index.md "CSS の表示と変更の概要"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get Started With Viewing And Changing The DOM"  -->  
<!--[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "Navigate the DOM Tree with a keyboard - Get Started With Viewing And Changing The DOM"  -->
[DevtoolsOpen]:../open.md "Microsoft Edge DevTools を開く"  
[Dev[キーボードショートカット]:.../shortcuts.md "Microsoft Edge DevTools のキーボードショートカット"  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts.md # styles-ウィンドウ-キーボードショートカット "[スタイル] ウィンドウのキーボードショートカット-Microsoft Edge DevTools のキーボードショートカット"  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "問題 868480-ARIA ツリーを Mac アクセシビリティの表として公開する"  
[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新しい問題-Microsoft のドキュメント/エッジ-開発者 |GitHub"  
[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ": active |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ": フォーカス |MDN"  
[MonorailChromiumIssues]: https://crbug.com "問題-chromium"  
[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (役割)-アクセシビリティの高いリッチインターネットアプリケーション (WAI-ARIA 使った-ARIA) 1.1 |勧告"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "tree (役割)-アクセシビリティの高いリッチインターネットアプリケーション (WAI-ARIA 使った-ARIA) 1.1 |勧告"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation)にあり、[渡 Dodson][RobDodson]によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
