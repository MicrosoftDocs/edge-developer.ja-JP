---
description: スクリーン リーダーのような支援技術を使用して Microsoft Edge DevTools をナビゲートするためのガイド。
title: 支援技術を使用して Microsoft Edge DevTools 内を移動する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d72c856e9136291e9255b3784aad7c6cd99f92fc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230811"
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

# 支援技術を使用して Microsoft Edge DevTools 内を移動する  

次の記事は、主にスクリーン リーダーのような支援技術に依存しているユーザーが [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain]にアクセスして使用するのに役立ちます。  [Microsoft Edge DevTools は][MicrosoftEdgeDevtoolsMain] 、Microsoft Edge ブラウザーに組み込まれています。  Web ページのアクセシビリティの向上に関連する DevTools 機能をお探しの場合は、「アクセシビリティ リファレンス」 [に移動してください][DevtoolsAccessibilityReference]。  

DevTools のアクセシビリティは、進行中の作業です。  一部のパネルやタブは、他のパネルやタブよりも支援技術に優れた機能を提供します。  このガイドでは、最もアクセスしやすいパネルについて説明し、途中で発生する可能性のある特定の問題について説明します。  

## 概要  

開始する前に、DevTools UI の構造に関する考え方を考えるのに役立ちます。  DevTools は、ARIA タブリストに編成された一連の [パネルに分かれています][W3CWaiAriaTablist]。  

次に、例を示します。  

*   要素 **パネル** では、[DOM ノードの表示と変更][DevtoolsDomIndexNavigateDomTreeKeyboard] または CSS を使用 [できます][DevtoolsCssIndex]。  
*   コンソール [パネルでは、JavaScript][DevtoolsConsoleIndex] ログとライブ編集オブジェクトを読み取りできます。  

各パネルのコンテンツ領域内には、ドキュメント内のタブやウィンドウと呼ばれるさまざまなツールが多数用意されています。  
たとえば、要素 **パネルには** 、イベント リスナー、アクセシビリティ ツリーなど、検査する追加のタブが含まれています。  タブとペインの違いは、少し任意です。  1 つの用語を確認する唯一の理由は、DevTools の公式ドキュメントの残りの部分との一貫性を維持する必要があります。  

## キーボード ショートカット  

The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheatsheet.  異なるパネルを探索する場合は、必ずブックマークを設定し、参照してください。  

## DevTools を開く  

To get started, navigate to [Open Microsoft Edge DevTools][DevtoolsOpen].  キーボード ショートカットまたはメニュー項目を使って DevTools を開く方法は多数あります。  

## パネル間を移動する  

### キーボードによる移動  

*   DevTools を開いた後 `Control` + `]` 、\(Windows,Linux\) または \(macOS\) を選択して、次のパネル `Command` + `]` にフォーカスを移動します。  
*   `Control` + `[` \(Windows,Linux\) または \(macOS\) を選択して、前の `Command` + `[` パネルにフォーカスを移動します。  
*   パネルの `Shift` + `Tab` [ARIA][W3CWaiAriaTablist]タブリストにフォーカスを移動し、方向キーを使ってパネルを変更することもできますが、前述のショートカットを使用する方が速い場合があります。  

**既知の問題**  

*   コンソール パネルやパフォーマンス**パネルなどの一**部のパネルでは、各パネルがアクティブ化されるとすぐにフォーカスがパネル コンテンツ領域に移動する場合があります。 ****  これにより、方向キーによる移動が困難になる場合があります。  
*   選択したパネルの名前が発表されますが、パネルのフォーカスされたコンテンツを読み取った後にのみ表示されます。  これにより、非常に簡単に見逃しがちな場合があります。  

### コマンド メニューで移動する  

特定のパネルにフォーカスを移動するには、コマンド メニュー [を使用します][DevtoolsCommandMenuIndex]。  

1.  DevTools を開いた後 `Control` + `Shift` + `P` 、\(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを**開きます**。  
    コマンド **メニューは** 、あいまい検索オートコンプリート コンボ ボックスです。  
1.  開くパネルの名前を入力し、キーボードで正しいオプションに `Down Arrow` 移動します。  
1.  コマンド `Enter` を実行する場合に選択します。  

次の操作を実行して、[要素] パネル **を開** きます。  

1.  コマンド メニュー **を開きます**。  
1.  次に `E` 入力します `L` 。  [ **パネル] >要素の表示** ] オプションが選択されています。  
1.  パネル `Enter` を開くコマンドを選択して実行します。  

この方法でパネルを開き、フォーカスをパネルのコンテンツに向かえます。  要素パネルの場合 **、** フォーカスは DOM ツリーに **移動します**。  

## 要素パネル  

### ページ上の要素を検査する  

1.  スクリーン リーダーでカーソルを使用して、検査する要素に移動します。  
1.  要素上でマウスを使用して右クリックをシミュレートし、コンテキスト メニューを開きます。  
1.  [検査] **オプションを選択** します。  This [opens the Elements panel and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].  

DOM**ツリーは**[、ARIA ツリーとしてレイアウトされます][W3CWaiAriaTree]。  たとえば、[Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard] に移動します。  

### DOM ツリー内の要素のコードをコピーする  

1.  **DOM**ツリー内のノードにフォーカスがある状態で、ノードをポイントし、コンテキスト メニュー \(右クリック\) を開きます。  
1.  [コピー] **オプションを展開** します。  
1.  Choose **Copy outerHTML**.  

**既知の問題**  

*   **多くの場合、outerHTML** をコピーすると現在のノードは選択されないので、代わりに親ノードが選択されます。  ただし、要素の内容はコピーされた outerHTML 内に残っている必要があります。  

### DOM ツリー内の要素の属性を変更する  

*   **DOM**ツリー内のノードにフォーカスがある場合は、編集 `Enter` 可能にします。  
*   属性値 `Tab` 間を移動する場合に選択します。  「space」という言葉が聞こえ、空のテキスト入力の中に入り、新しい属性値を入力できます。  
*   `Control` + `Enter` \(Windows,Linux\) または `Command` + \(macOS\) を選択して変更を受け入れ、要素の内容全体 `Enter` を聞く。  

**既知の問題**  

*   テキスト入力を入力すると、フィードバックは表示されます。  入力ミスを行い、方向キーを使って入力を確認すると、フィードバックも表示されます。  作業を確認する最も簡単な方法は、変更を受け入れてから、要素全体が発表されるのをリッスンする方法です。  

### DOM ツリー内の要素の HTML を編集する  

*   **DOM**ツリー内のノードにフォーカスがある場合は、編集 `Enter` 可能にします。  
*   属性値 `Tab` 間を移動する場合に選択します。  たとえば、要素の名前が聞こえると、テキスト入力の内部にいて、要素の種類が `h2` 変更される可能性があります。  
*   `Control` + `Enter` \(Windows, Linux\) または `Command` + `Enter` \(macOS\) を選択して変更を受け入れる。  

たとえば `h3` `Control` + `Enter` 、\(Windows,Linux\) または `Command` + `Enter` \(macOS\) を入力して選択すると、要素の開始タグと終了タグが `h3` 変更されます。  

## 要素パネルのタブ  

要素 **パネル** には、要素に適用された CSS やアクセシビリティ ツリー内の関連する場所など、項目を検査する追加のタブが含まれています。  

*   **DOM**ツリーのノードにフォーカスがある場合は、[スタイル] ウィンドウが選択されている `Tab` という聞**こえる**まで選択します。  
*   その他の `Right Arrow` 利用可能なタブを表示するには、次のコマンドを使用します。  

**DOM ツリーは**属性を持つ要素をフォーカス可能なリンクに変換します。そのため、[スタイル] ウィンドウに到達するには、複数選択 `href` `Tab` する**必要があります**。  

**既知の問題**  

**DOM の [ブレークポイント]** タブと **[プロパティ]** タブは、キーボードからアクセスすることはできません。  

### [スタイル] ウィンドウ  

[スタイル **]** ウィンドウで、スタイルのフィルター処理、要素の状態 [\(:active][MDNActive] や [:focus][MDNFocus]\など) の切り替え、クラスの切り替え、新しいクラスの追加を行うコントロールを検索します。  DOM ツリーにフォーカスしている要素に現在適用されているスタイルを調査および変更するための強力なスタイル検査ツール **も用意されています**。  

[スタイル] ウィンドウについて理解**** する重要な概念は、DOM ツリーで現在選択されているノードのスタイルのみを**表示する点です**。  たとえば、ノードのスタイルの検査が完了し、ノードのスタイルを確認 `<header>` すると `<footer>` します。  これを行うには、まず DOM ツリーでノード `<footer>` を選択する **必要があります**。  [Inspect](#inspect-an-element-on-the-page)ワークフローを使用すると、DOM ツリーに焦点を当てたノード `footer` \(フッター\内のリンクなど) の一般的な近くに位置するノードを検査**** し、キーボードを使用して目的の正確なノードに移動する方が速い場合があります。  

#### [スタイル] ウィンドウ内を移動する  

すべてのスタイル ツールは何かの方法で [スタイル] ウィンドウ**** に接続し、最初にこのツールの専門家になるのが理にかなっています。  

*   [スタイル] ウィンドウに **フォーカスがある** 場合は、フォーカス `Tab` を内側に移動してコンテンツを探します。  
*   最初 `Tab` のスタイルがアクティブになるまで選択します。  スクリーン リーダーを使用している場合、この最初のスタイルは次のように発表されます `element.style {}` 。  
*   スタイル `Down Arrow` の一覧を特定の順序で移動する場合に選択します。  スクリーン リーダーは、CSS ファイルの名前、スタイルが表示される行番号、およびスタイルの名前で始まる各スタイルをアナウンスします。  たとえば、`main.css:233 .card__img {}` と記述します。  
*   スタイル `Enter` を詳細に検査する場合に選択します。  フォーカスは、編集可能なバージョンのスタイル名から始まります。  
*   各 `Tab` CSS プロパティの編集可能なバージョンと対応する値の間を移動する場合に選択します。  各スタイル ブロックの最後には、追加の CSS プロパティを追加するために使用できる空の編集可能なテキスト フィールドがあります。  
*   引き続きスタイルの一覧内を移動するか、モードを終了して方向キーによる移動に `Tab` `Escape` 戻る場合があります。  

その他のショートカットについては、[Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard] に移動します。  

**既知の問題**  

*   [フィルター] **編集可能な** テキスト フィールドを使用すると、スタイルの一覧を移動できなくなりました。  

#### Toggle 要素の状態  

要素の状態を切り替えるには、次のように `:active` します `:focus` 。  

1.  [スタイル] ウィンドウ **に移動** し、[要素の状態の切り替え] ボタンに `Tab` フォーカスが移動 **するまで** 選択します。  
1.  要素 `Enter` の状態のコレクションを展開するために選択します。  要素の状態は、チェック ボックスのグループとして表示されます。  
1.  最初 `Tab` の状態がフォーカスを持 `:active` つまで選択します。  
1.  有効 `Space` にする場合に選択します。  DOM ツリーで現在選択されている要素にスタイルがある場合 `:active` は、適用されます。  
1.  保持 `Tab` して、使用可能なすべての状態を確認します。  

#### 既存のクラスを追加する  

[要素の状態 **の切り替え]** ボタンの隣には、[ **要素クラス] ボタン** があります。  フォーカスを移動するには、選択して `Tab` 選択します `Enter` 。  フォーカスは、[新しいクラスの追加] というラベルの付いた **編集テキスト フィールドに移動します**。  

[ **要素クラス]** ボタンは、主に既存のクラスを要素に追加するために使用されます。  たとえば、スタイルシートに名前が付いたヘルパー クラスが含まれている場合は、編集テキスト フィールド内で選択してクラスの候補リストを表示し、その提案を検索するために使用 `.clearfix` `.` `Down Arrow` `.clearfix` できます。  または、自分でクラス名を入力し、適用 `Enter` を選択します。  

#### 新しいスタイル ルールを追加する  

[要素クラス **] ボタンの隣** には、[新しいスタイル **ルール] ボタン** があります。  フォーカスを移動するには、選択して `Tab` 選択します `Enter` 。  フォーカスは、スタイルインスペクター内の編集可能なテキスト フィールドに移動します。  フィールドの最初のテキスト コンテンツは **、DOM**ツリーで選択されている要素のタグ名です。  
このフィールドには任意のクラス名を入力し、CSS プロパティを割り当 `Tab` てる場合に選択できます。  

### [計算] タブ  

[計算] タブに **フォーカスがある** 場合は、フォーカス `Tab` を内側に移動してコンテンツを探索します。  [ **計算] タブには** 、特定の順序で要素に実際に適用される CSS プロパティを確認するコントロールがあります。  

<!--todo: add computed tab section when available  -->  

#### 計算されたスタイルを探索する  

計算 `Tab` されたスタイルのコレクションに到達するまで選択します。  これらは ARIA ツリー [として表示されます][W3CWaiAriaTree]。  リスト ボックスを展開すると、計算されたスタイルを適用している CSS セレクターが表示されます。  これらのセレクターは、特定性ごとに整理されています。  スクリーン リーダーは、計算された値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、セレクターの行番号をアナウンスします。  

**既知の問題**  

*   [フィルター] テキスト **フィールドを** 使用すると、スタイルを検査できなくなりました。  

### [イベント リスナー] タブ  

[要素] **パネルから** 、[イベント リスナー] タブを使用して、要素に適用されているイベント リスナー **を検査** できます。 [スタイル] ウィンドウに **フォーカス** がある場合は、[イベント リスナー] `Right Arrow` タブ **に移動します** 。  

#### イベント リスナーの探索  

イベント リスナーは [、ARIA ツリーとして表示されます][W3CWaiAriaTree]。  方向キーを使って移動できます。  スクリーン リーダーは、イベント リスナーがアタッチされている DOM オブジェクトの名前、およびイベント リスナーが定義されているファイル名と行番号を読み上げます。  

### [アクセシビリティ] ウィンドウ  

[アクセシビリティ] ウィンドウに **フォーカスがある** 場合は、フォーカスを内側に移動してコンテンツ `Tab` を探します。  [ [アクセシビリティ] ウィンドウ][DevtoolsAccessibilityReference] には、アクセシビリティ ツリー、要素に適用される ARIA 属性、および計算されたアクセシビリティ プロパティを探索するコントロールがあります。  

#### アクセシビリティ ツリー  

アクセシビリティ **ツリーは** [ARIA][W3CWaiAriaTree] ツリーとして表示され、各ツリーは DOM 内の `treeitem` 要素に対応します。  ツリーは、選択したノードの計算された役割をアナウンスします。  ツリーで `div` `span` "GenericContainer" のような一般的な要素が発表されます。  方向キーを使ってツリーをスキャンし、親子関係を探索します。  

**既知の問題**  

*   [アクセシビリティ] ウィンドウで使用される****[ARIA][W3CWaiAriaTree]ツリーの種類が、VoiceOver のような macOS スクリーン リーダー用の Microsoft Edge で適切に公開されていない可能性があります。  Chromium の [問題を購読#868480、][ChromiumIssues868480] この問題の進行状況を知らせる必要があります。  
*   **ARIA 属性**と計算プロパティ**** の各セクションは[、ARIA][W3CWaiAriaTree]ツリーとしてマーク付けされますが、それぞれが現在フォーカス管理を持っているのではなく、キーボード操作可能ではありません。  

## 監査パネル  

監査 **パネルでは** 、サイトに対して一連のテストを実行して、パフォーマンス、アクセシビリティ、SEO、その他の多くのカテゴリに関連する一般的な問題を確認する必要があります。  

### 監査を構成して実行する  

1.  監査パネル**が最初**に開かれると、フォームの最後にある [**** 監査の実行] ボタンにフォーカスが移動します。  既定では、シミュレートされた 3G 接続でモバイル エミュレーションを使用して、すべてのカテゴリの監査を実行するようにフォームが構成されます。  
1.  参照 `Shift` + `Tab` モードを使用するか、戻って監査設定を変更します。  
1.  監査を実行する準備ができたら、[監査の実行] ボタンに戻 **り、選択** します `Enter` 。  
1.  フォーカスがモーダル ウィンドウに移動し、[ **キャンセル** ] ボタンが表示され、監査を終了できます。  監査が実行され、ページが複数回更新されると、一連の耳コンが聞こえる場合があります。  

**既知の問題**  

*   構成フォームの異なるセクションは、現在、要素でマーク付け `fieldset` されていない。  参照モードで移動して、各セクションに関連付けられているコントロールを特定する方が簡単な場合があります。  
*   監査の実行が完了した場合、earcon やライブ リージョンのアナウンスはありません。  通常は約 30 秒かかるので、結果に移動できる必要があります。  参照モードを使用するのが、結果を得る最も簡単な方法です。  

### 監査レポート内を移動する  

監査レポートは、各監査カテゴリに対応するセクションに整理されています。  レポートが開き、各カテゴリのスコアの一覧が表示されます。  これらのスコアは、関連するセクションにスキップするために使用できるリンクです。  各セクション内には展開可能な要素があります。この要素には、合格または失敗した監査 `details` に関連する情報が含まれます。  既定では、失敗した監査だけが表示されます。  各セクションの最後には、渡された監査のすべてが含まれる最終的 `details` な要素が含まれる必要があります。  

新しい監査を実行するには、レポートを終了し、[監査の実行] ボタン `Shift` + `Tab` **を探**します。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "アクセシビリティ リファレンス |Microsoft Docs"  
[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "アクセシビリティ ウィンドウ - アクセシビリティ リファレンス |Microsoft Docs"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する |Microsoft Docs"  
[DevtoolsConsoleIndex]: ../console/index.md "コンソールの概要 | Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更を開始する |Microsoft Docs"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md#view-dom-nodes "DOM ノードの表示 - DOM の表示と変更を開始する |Microsoft Docs"  
[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "Navigate the DOM Tree with a keyboard - Get started with viewing and changing the DOM |Microsoft Docs"  
[DevtoolsOpen]: ../open/index.md "Open Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts/index.md#styles-pane-keyboard-shortcuts "Styles pane keyboard shortcuts - Microsoft Edge DevTools Keyboard Shortcuts |Microsoft Docs"  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "問題 868480 - Mac アクセシビリティで ARIA ツリーをテーブルとして公開する"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新しい問題 - MicrosoftDocs/edge-developer |GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ":active |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ":focus |MDN"  

[MonorailChromiumIssues]: https://crbug.com "問題 - chromium - モノラルレール"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (役割) - Accessible Rich Internet Applications (RIA-ARIA) 1.1 |W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "ツリー (役割) - Accessible Rich Internet Applications (RIA-ARIA) 1.1 |W3C"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) つかり [、Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
