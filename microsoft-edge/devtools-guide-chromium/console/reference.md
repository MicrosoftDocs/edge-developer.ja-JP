---
description: DevTools のコンソール UI のすべての機能と動作に関するMicrosoft Edge参照。
title: コンソールリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: adc3f6c33d6e1a2f6c7db8336c5ab803e76c3307
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483272"
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
# <a name="console-reference"></a>コンソールリファレンス  

この記事は、DevTools コンソールに関連する機能Microsoft Edgeです。  コンソールを使用してログに記録されたメッセージを表示し、JavaScript を実行する方法について既に理解している必要があります。  表示されない場合は、[コンソールで [JavaScript][DevtoolsConsoleConsoleJavascript] を実行する方法を開始する] および [コンソールでのメッセージのログ記録の [開始] に移動します][DevtoolsConsoleConsoleLog]。  

関数の API 参照を探している場合は、[コンソール API リファレンス] `console.log()` [に移動します][DevToolsConsoleApi]。  次のような関数の参照については、「 `monitorEvents()` コンソール ユーティリティ API [リファレンス」に移動します][DevToolsConsoleUtilities]。  

## <a name="open-the-console"></a>コンソールを開く  

コンソールは **、上部ウィンドウ** の [ツールとして](#open-the-console-tool) 、またはドロワーで [ツールとして開く場合があります](#open-the-console-tool-in-the-drawer)。  

### <a name="open-the-console-tool"></a>コンソール ツールを開く  

`Control` + `Shift` + `J` \(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="コンソール ツール" lightbox="../media/console-hello-console.msft.png":::
   コンソール**ツール**  
:::image-end:::  

コマンド メニューから**コンソール ツール**を[開][DevtoolsCommandMenuIndex]くには、パネル バッジが横にある [コンソールの表示] コマンドを入力して `Console` 実行します。 **** ****  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="コマンドを実行してコンソール ツールを表示する" lightbox="../media/console-command-menu-show-console.msft.png":::
   コマンドを実行してコンソール ツール **を表示** する  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a>ドロワーでコンソール ツールを開く  

`Esc` **[DevTools \(** \) のカスタマイズと制御] を選択 `...` または選択し、[コンソール ドロワー**の表示] を選択します**。  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="コンソール ドロワーの表示" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **コンソール ドロワーの表示**  
:::image-end:::  

[引き出し] が DevTools ウィンドウの下部に表示されます。コンソール ツール **が開** きます。  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="ドロワーのコンソール ツール" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   ドロ **ワー** のコンソール **ツール**  
:::image-end:::  

[コマンド]**メニューから [** コンソール] ツールを[開][DevtoolsCommandMenuIndex]き、その横に [引き出し] バッジがある [コンソールの表示] コマンド `Console` を入力して実行します。 **** ****  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="コマンドを実行して、ドロワーに **Console** ツールを表示する" lightbox="../media/console-command-menu-show-console.msft.png":::
   コマンドを実行して、ドロワー **にコンソール** ツールを表示 **する**  
:::image-end:::  

### <a name="open-console-settings"></a>Open Console 設定  

[**コンソール] メニュー設定**\( ![ [コンソール] 設定 ](../media/settings-button-icon.msft.png) \) ボタンを選択します。  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="コンソール 設定" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **コンソール 設定**  
:::image-end:::  

次のリンクでは、各設定について説明します。  

*   [ネットワークを非表示にする](#hide-network-messages)  
*   [ログを保持する](#persist-messages-across-page-loads)  
*   [選択したコンテキストのみ](#filter-out-messages-from-different-contexts)  
*   [類似のグループ](#turn-off-message-grouping)  
*   [ログ XMLHttpRequests](#log-xhr-and-fetch-requests)  
*   [熱心な評価](#turn-off-eager-evaluation)  
*   [履歴からのオートコンプリート](#turn-off-autocomplete-from-history)  
<!--*   Evaluate triggers user activation  -->  
    
### <a name="open-the-console-sidebar"></a>コンソール サイドバーを開く  

サイドバーを表示 **するには、[コンソール サイドバー**を **表示する** ]を選択します。(Show ![ console sidebar ](../media/show-console-sidebar-icon.msft.png) \)。  サイドバー **はフィルター** 処理に役立ちます。  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="コンソール サイドバー" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **コンソール サイドバー**  
:::image-end:::  

## <a name="view-messages"></a>メッセージの表示  

このセクションには、コンソールでのメッセージの表示方法を変更する機能が含まれます。  実践的なチュートリアルの場合は、[メッセージの表示] [に移動します][DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage]。  

### <a name="turn-off-message-grouping"></a>メッセージのグループ化をオフにする  

コンソールの既定のメッセージ グループ化動作をオフ**** にするには[](#open-console-settings)、[コンソール] ウィンドウを開設定[類似グループ] の横にあるチェック ボックスを**オンにします**。  たとえば、[ [ログ XHR] と [フェッチ要求] に移動します](#log-xhr-and-fetch-requests)。  

### <a name="log-xhr-and-fetch-requests"></a>ログ XHR 要求とフェッチ要求  

すべての要求と要求をコンソールに記録するには、[コンソール] ウィンドウを開き設定 `XMLHttpRequest` `Fetch` **[ログ XMLHttpRequests]** の[横](#open-console-settings)**** にあるチェック ボックスをオンにします。  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="ログ XMLHttpRequest および Fetch 要求" lightbox="../media/console-xhr-fetch.msft.png":::
   ログ `XMLHttpRequest` と `Fetch` 要求  
:::image-end:::  

前の図のトップ メッセージには、コンソールの既定のグループ化動作が表示 **されます**。  <!--  In the following figure, the same log is displayed after you [turn off message grouping](#turn-off-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a>ページの読み込み中にメッセージを保持する  

新しい Web ページを読み込むと、既定のアクションによってコンソールがクリア **されます**。  ページの読み込み時にメッセージを保持するには、[コンソール] 設定を開き、[ログの保持] の[横](#open-console-settings)にあるチェック ボックス**をオンにします**。  

### <a name="hide-network-messages"></a>ネットワーク メッセージを非表示にする  

既定のアクションは、Microsoft Edgeメッセージをコンソールにログに記録**します**。  次の図では、選択したメッセージはの HTTP 状態コードを表します `429` 。  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="コンソールの 429 メッセージ" lightbox="../media/console-show-network.msft.png":::
   コンソール `429` 内の **メッセージ**  
:::image-end:::  

ネットワーク メッセージを非表示にするには、次の操作を実行します。  

1.  [コンソール を開設定。](#open-console-settings)  
1.  [ネットワークの非表示] の横にある **チェック ボックスをオンにします**。  
    
## <a name="filter-messages"></a>フィルター メッセージ  

コンソールでメッセージをフィルター処理する多くの方法 **があります**。  

### <a name="filter-out-browser-messages"></a>ブラウザー メッセージをフィルター処理する  

[コンソール サイドバーを開き](#open-the-console-sidebar)**、[# ユーザー**メッセージ] を選択して、Web ページの JavaScript から送信されたメッセージのみを表示します。  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="ユーザー メッセージの表示" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   ユーザー メッセージの表示  
:::image-end:::  

### <a name="filter-by-log-level"></a>ログ レベルでフィルター処理する  

DevTools は、各メソッド `console.*` に 4 つの重大度レベルの 1 つを割り当てる。  

*   `Error`  
*   `Info`  
*   `Verbose`  
*   `Warning`  
    
たとえば、 `console.log()` グループ内ですが `Info` 、 `console.error()` グループ内 `Error` にあるとします。  コンソール [API リファレンスでは][DevToolsConsoleApi] 、該当する各メソッドの重大度レベルについて説明します。  ブラウザーがコンソールにログに記録するメッセージには、重大度レベルもあります。  興味がないメッセージのレベルは非表示にできます。  たとえば、メッセージにのみ関心がある場合は、他の 3 つの `Error` グループを非表示にできます。  

メッセージをフィルター処理するには、[ログ レベル] **ドロップダウン** を選択し、[ `Verbose` 、 、 、 ] `Info` `Warning` を選択します `Error` 。  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="[ログ レベル] ドロップダウン" lightbox="../media/console-log-level-default-levels.msft.png":::
   [ **ログ レベル]** ドロップダウン  
:::image-end:::  

ログ レベルを使用してフィルター処理するには、コンソール[サイドバー](#open-the-console-sidebar)を開**** き、[エラー]、[**警告****]、[情報**]、または [詳細] の順に**選択します**。  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="サイドバーを使用して警告を表示する" lightbox="../media/console-sidebar-warnings.msft.png":::
   サイドバーを使用して警告を表示する  
:::image-end:::  

### <a name="filter-messages-by-url"></a>URL でメッセージをフィルター処理する  

URL `url:` の後に URL を入力して、その URL から送信されたメッセージのみを表示します。  入力後 `url:` 、DevTools は関連するすべての URL を表示します。  ドメインも機能します。  たとえば、メッセージをログに記録する場合は、これら 2 つのスクリプトの `https://example.com/a.js` `https://example.com/b.js` `url:https://example.com` メッセージに集中できます。  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL フィルター" lightbox="../media/console-filter-text.msft.png":::
   URL フィルター  
:::image-end:::  

URL からメッセージを非表示にする場合は `-url:` 、「.  これは、負の URL フィルターです。  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="URL に一致するメッセージをすべて非表示にする負の https://b.wal.co URL フィルター" lightbox="../media/console-negative-filter-text.msft.png":::
   URL に一致するメッセージをすべて非表示にする負の `https://b.wal.co` URL フィルター
:::image-end:::  

1 つの URL からのメッセージを表示するには、次のアクションを実行します。  

1.  [コンソール サイドバーを開きます](#open-the-console-sidebar)。  
1.  [# **ユーザー メッセージ] セクションを** 展開します。  
1.  フォーカスするメッセージを含むスクリプトの URL を選択します。  
    
:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="ユーザーから送信されたメッセージを表示wp-ad.min.js" lightbox="../media/console-filter-text-specified.msft.png":::
   から来たメッセージを表示する `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a>さまざまなコンテキストからのメッセージをフィルター処理する  

Web ページに広告 \(ad\) が含まれるとします。  広告はコンソールに埋め込まれている `<iframe>` ので、コンソールに多数のメッセージが生成 **されます**。  広告が別の[JavaScript](#choose-javascript-context)コンテキストで実行されている場合、メッセージを非表示にする[1](#open-console-settings)つの方法として、[コンソール 設定] を開き、[選択されたコンテキストのみ] の横にあるチェック ボックスを**オンにします**。  

### <a name="filter-out-messages-that-dont-match-a-regular-expression-pattern"></a>正規表現パターンに一致しないメッセージをフィルター処理する  

[フィルター] テキスト ボックスに正規表現を入力して、そのパターンに一致しないメッセージを `/[gm][ta][mi]/` フィルター処理します。 ****  DevTools は、メッセージ テキストにパターンが見つかったか、メッセージがログに記録される原因となるスクリプトをチェックします。  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="正規表現と一致しないメッセージをフィルター処理する" lightbox="../media/console-filter-regex.msft.png":::
   正規表現に一致しないメッセージを `/[gm][ta][mi]/` フィルター処理する  
:::image-end:::  

## <a name="run-javascript"></a>JavaScript の実行  

このセクションでは、コンソールでの JavaScript の実行に関連する機能について説明 **します**。  実践的なチュートリアルの場合は、[JavaScript の実行 [] に移動します][DevtoolsConsoleConsoleJavascript]。  

### <a name="rerun-expressions-from-history"></a>履歴から式を再実行する  

コンソール `Up Arrow` で前に実行した JavaScript 式の履歴を循環する場合に選択 **します**。  この式 `Enter` を再度実行する場合に選択します。  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a>Live Expression を使用して、式の値をリアルタイムで確認する  

コンソールで同じ JavaScript 式を繰り**** 返し入力すると、Live 式の作成が簡単になる**場合があります**。  Live **Expression を使用**すると、式を 1 回入力し、本体の上部にピン留め **します**。  式の値は、ほぼリアルタイムで更新されます。  [ライブ式 [を使用して JavaScript 式Real-Timeを監視する] に移動します][DevToolsConsoleLiveExpressions]。  

### <a name="turn-off-eager-evaluation"></a>熱心な評価をオフにする  

**熱心な評価** では、コンソールに JavaScript 式を入力すると、戻り値のプレビューが表示 **されます**。  戻り値のプレビューをオフにするには、次のアクションを実行します。  

1.  [コンソール を開設定。](#open-console-settings)  
1.  [熱心な評価] の横にある **チェック ボックスをオフにします**。  
    
### <a name="turn-off-autocomplete-from-history"></a>履歴からオートコンプリートをオフにする  

式を入力すると、コンソールのオートコンプリート ポップアップ ウィンドウに、前**** に実行した式が表示されます。  式には、文字があらかじめ付 `>` けされています。  履歴からの式の表示を停止するには[](#open-console-settings)、[コンソール] 設定を開き、[履歴からオートコンプリート] チェック ボックスの横にあるチェック ボックス**をオフ**にします。  

> [!NOTE]
> 次の図では、 `document.querySelector('a')` `document.querySelector('img')` 前に評価された式を示します。  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="オートコンプリートのポップアップ メニューには、履歴の式が表示されます。" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   オートコンプリートのポップアップ メニューには、履歴の式が表示されます。  
:::image-end:::  

### <a name="choose-javascript-context"></a>JavaScript コンテキストの選択  

**JavaScript Context**ドロップダウンの既定のオプションは**top**で、[][MdnDocsGlossaryBrowsingContext]メイン Web ページの閲覧コンテキストを表します。  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="[JavaScript コンテキスト] ドロップダウン" lightbox="../media/console-dom-level-top.msft.png":::
   **[JavaScript コンテキスト] ドロップダウン**  
:::image-end:::  

Web ページに広告が埋め込まれているとします `<iframe>` 。  JavaScript を実行して広告の DOM を調整する場合。  最初に、[JavaScript コンテキスト] ドロップダウンから広告の参照 **コンテキストを選択** します。  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="別の JavaScript コンテキストを選択する" lightbox="../media/console-dom-level-multiple.msft.png":::
   別の JavaScript コンテキストを選択する  
:::image-end:::  

## <a name="clear-the-console"></a>コンソールをクリアする  

コンソールをクリア **するには**、次のワークフローを完了します。  

*   [Clear **Console** \( ![ Clear Console ](../media/clear-console-button-icon.msft.png) \) ] ボタンを選択します。  
*   メッセージにカーソルを置き、コンテキスト メニュー \(右クリック\) を開き、[コンソールのクリア] **を選択します**。  
*   コンソール `clear()` に入力 **し、 を** 選択します `Enter` 。  
*   Web `console.clear()` ページの JavaScript から実行します。  
*   コンソール `Control` + `L` がフォーカス**されている間**に選択します。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "コンソール ツール でメッセージをログに記録|Microsoft Docs"  
[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "JavaScript 環境としてのコンソール |Microsoft Docs"  
[DevtoolsConsoleIndex]: .index.md "コンソール ウィンドウを使用|Microsoft Docs"  
[DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage]: ./index.md#inspect-and-filter-information-on-the-current-webpage "現在の Web ページ の情報を検査してフィルター処理|Microsoft Docs"  
[DevtoolsConsoleLiveExpressions]: ./live-expressions.md "Live 式を使用して JavaScript の変更を監視|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "[DevTools コマンド] メニューの [Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  

[MdnDocsGlossaryBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "参照コンテキスト |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
