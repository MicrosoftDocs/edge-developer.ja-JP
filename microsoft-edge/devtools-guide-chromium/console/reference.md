---
description: Microsoft Edge DevTools のコンソール UI に関連するすべての機能と動作に関する包括的なリファレンス。
title: コンソールリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d6fed1681e64f8f57c2e577017d623039a7b4152
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439368"
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

このページは、Microsoft Edge DevTools コンソールに関連する機能の参照です。  コンソールを使用してログに記録されたメッセージを表示し、JavaScript を実行する方法について既に理解している必要があります。  ない場合は、[コンソールでの [JavaScript][DevToolsConsoleJavascript] の実行の開始] および [コンソールでのログ メッセージの開始 [] に移動します][DevToolsConsoleLog]。  

関数の API 参照を探している場合は、[コンソール API リファレンス] `console.log()` [に移動します][DevToolsConsoleApi]。  次のような関数の参照については、「 `monitorEvents()` コンソール ユーティリティ API [リファレンス」に移動します][DevToolsConsoleUtilities]。  

## <a name="open-the-console"></a>コンソールを開く  

コンソールは **、上部ウィンドウ** の [ツールとして](#open-the-console-tool) 、またはドロワーで [ツールとして開く場合があります](#open-the-console-tool-in-the-drawer)。  

### <a name="open-the-console-tool"></a>コンソール ツールを開く  

`Control` + `Shift` + `J` \(Windows, Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="コンソール ツール" lightbox="../media/console-hello-console.msft.png":::
   コンソール**ツール**  
:::image-end:::  

コマンド メニューから**コンソール**ツールを[開][DevToolsCommandMenu]くには、入力を開始し、パネル バッジが横にある [コンソールの表示] `Console` **コマンド**を実行します。 ****  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="コンソール パネルを表示するコマンド" lightbox="../media/console-command-menu-show-console.msft.png":::
   コンソール ツールを表示 **する** コマンド  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a>ドロワーでコンソール ツールを開く  

`Escape` **[DevTools のカスタマイズと制御]** \( \) を選択 `...` または選択し、[コンソール ドロワー**の表示] を選択します**。  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="コンソール ドロワーの表示" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **コンソール ドロワーの表示**  
:::image-end:::  

[引き出し] が DevTools ウィンドウの下部に表示されます。コンソール ツール **が開** きます。  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="ドロワーのコンソール ツール" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   ドロ **ワー** のコンソール **ツール**  
:::image-end:::  

コマンド メニューから**コンソール ツール**を[開][DevToolsCommandMenu]くには、入力を開始し、その横にドロワー バッジがある [コンソールの表示] コマンド `Console` を実行します。 **** ****  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="ドロワーに **Console** ツールを表示するコマンド" lightbox="../media/console-command-menu-show-console.msft.png":::
   ドロワーにコンソール ツール **を** 表示する **コマンド**  
:::image-end:::  

### <a name="open-console-settings"></a>コンソールの設定を開く  

[ **コンソール設定]** \( ![ [コンソール設定] アイコン ](../media/settings-button-icon.msft.png) \) を選択します。  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="コンソール設定" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **コンソール設定**  
:::image-end:::  

以下のリンクでは、各設定について説明します。  

*   [**ネットワークを非表示にする**](#hide-network-messages)  
*   [**ログの保持**](#persist-messages-across-page-loads)  
*   [**選択したコンテキストのみ**](#filter-out-messages-from-different-contexts)  
*   [**グループ類似**](#disable-message-grouping)  
*   [**Log XmlHttpRequests**](#log-xhr-and-fetch-requests)  
*   [**熱心な評価**](#disable-eager-evaluation)  
*   [**履歴からのオートコンプリート**](#disable-autocomplete-from-history)  
    
### <a name="open-the-console-sidebar"></a>コンソール サイドバーを開く  

[Show **Console Sidebar** \( Show Console Sidebar \) ] を選択してサイドバーを表示します。これはフィルター処理 ![ ](../media/show-console-sidebar-icon.msft.png) に便利です。  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="コンソール サイドバー" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **コンソール** サイドバー  
:::image-end:::  

## <a name="view-messages"></a>メッセージの表示  

このセクションには、コンソールでのメッセージの表示方法を変更する機能が含まれます。  実践的なチュートリアルの場合は、[メッセージの表示] [に移動します][DevToolsConsoleViewMessages]。  

### <a name="disable-message-grouping"></a>メッセージのグループ化を無効にする  

[[コンソールの設定] を](#open-console-settings) 開き、[ **グループ]** を無効にして、コンソールの既定のメッセージ グループ化動作を無効にします。  たとえば、[ [ログ XHR] と [フェッチ要求] に移動します](#log-xhr-and-fetch-requests)。  

### <a name="log-xhr-and-fetch-requests"></a>ログ XHR 要求とフェッチ要求  

[[コンソールの設定]](#open-console-settings) を開き **、[ログ XMLHttpRequests]** を有効にして、発生したすべての要求を `XMLHttpRequest` コンソールに `Fetch` 記録します。  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="ログ XMLHttpRequest および Fetch 要求" lightbox="../media/console-xhr-fetch.msft.png":::
   ログ `XMLHttpRequest` と `Fetch` 要求  
:::image-end:::  
前の図のトップ メッセージには、コンソールの既定のグループ化動作が表示 **されます**。  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a>ページの読み込み中にメッセージを保持する  

既定では、新しいページを読み込むたびにコンソールがクリアされます。  ページの読み込み時にメッセージを保持するには、[ [コンソール設定] を開](#open-console-settings) き、[ログの保持] **チェック ボックスをオン** にします。  

### <a name="hide-network-messages"></a>ネットワーク メッセージを非表示にする  

既定では、ブラウザーはネットワーク メッセージをコンソールに記録 **します**。  次の図では、選択したメッセージはの HTTP 状態コードを表します `429` 。  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="コンソールの 429 メッセージ" lightbox="../media/console-show-network.msft.png":::
   コンソール `429` 内の **メッセージ**  
:::image-end:::  
ネットワーク メッセージを非表示にする方法:  

1.  [[コンソール設定] を開きます](#open-console-settings)。  
1.  [ネットワークの **非表示] チェック ボックスを** オンにします。  
    
## <a name="filter-messages"></a>フィルター メッセージ  

コンソールでメッセージをフィルター処理する方法は多数あります。  

### <a name="filter-out-browser-messages"></a>ブラウザー メッセージをフィルター処理する  

[コンソール サイドバーを開き](#open-the-console-sidebar) 、[ **ユーザー** メッセージ] を選択して、ページの JavaScript から送信されたメッセージのみを表示します。  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="ユーザー メッセージの表示" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   ユーザー メッセージの表示  
:::image-end:::  

### <a name="filter-by-log-level"></a>ログ レベルでフィルター処理する  

DevTools は、各 `console.*` メソッドに重大度レベルを割り当てる。  4 つのレベルがあります `Verbose` 。 `Info` `Warning` `Error`  たとえば、 `console.log()` グループ内 `Info` ですが、グループ `console.error()` 内 `Error` です。  コンソール [API リファレンスでは][DevToolsConsoleApi] 、該当する各メソッドの重大度レベルについて説明します。  ブラウザーがコンソールにログに記録するメッセージには、重大度レベルもあります。  興味がないメッセージのレベルは非表示にできます。  たとえば、メッセージにのみ関心がある場合は、 `Error` 他の 3 つのグループを非表示にできます。  

[ログ レベル **] ドロップダウンを** 選択して、メッセージ `Verbose` を有効または `Info` `Warning` 無効 `Error` にします。  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="[ログ レベル] ドロップダウン" lightbox="../media/console-log-level-default-levels.msft.png":::
   [ **ログ レベル]** ドロップダウン  
:::image-end:::  

コンソール サイドバーを開き、エラー、警告、情報、または詳細を選択**** して、**** ログ レベル**でフィルター**処理**することもできます**。 [](#open-the-console-sidebar)  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="サイドバーを使用して警告を表示する" lightbox="../media/console-sidebar-warnings.msft.png":::
   サイドバーを使用して警告を表示する  
:::image-end:::  

### <a name="filter-messages-by-url"></a>URL でメッセージをフィルター処理する  

URL `url:` の後に URL を入力して、その URL から送信されたメッセージのみを表示します。  DevTools と `url:` 入力すると、関連するすべての URL が表示されます。  ドメインも機能します。  たとえば、メッセージをログに記録する場合は、これら 2 つのスクリプトからのメッセージ `https://example.com/a.js` `https://example.com/b.js` `url:https://example.com` に集中できます。  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL フィルター" lightbox="../media/console-filter-text.msft.png":::
   URL フィルター  
:::image-end:::  

その `-url:` URL からメッセージを非表示にする場合は、入力します。  これは、負の URL フィルターと呼ばれる。  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="URL に一致するメッセージをすべて非表示にする負の https://b.wal.co URL フィルター" lightbox="../media/console-negative-filter-text.msft.png":::
   URL に一致するメッセージをすべて非表示にする負の `https://b.wal.co` URL フィルター
:::image-end:::  

単一の URL からのメッセージを表示[](#open-the-console-sidebar)するには、コンソール サイドバーを開き****、[ユーザー メッセージ] セクションを展開し、フォーカスするメッセージを含むスクリプトの URL を選択します。  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="ユーザーから送信されたメッセージを表示wp-ad.min.js" lightbox="../media/console-filter-text-specified.msft.png":::
   から来たメッセージを表示する `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a>さまざまなコンテキストからのメッセージをフィルター処理する  

ページに広告 \(ad\) が含まれるとします。  広告は a に埋め込まれているので、コンソールで多くの `<iframe>` メッセージを生成しています。  広告は別の[JavaScript](#select-javascript-context)コンテキストで実行されているので、メッセージを非表示にする方法の[](#open-console-settings)1 つは、[コンソール設定] を開き、[選択されたコンテキストのみ] チェック ボックスを**オンにします**。  

### <a name="filter-out-messages-that-do-not-match-a-regular-expression-pattern"></a>正規表現パターンに一致しないメッセージをフィルター処理する  

[フィルター] テキスト ボックスに正規表現を入力して、そのパターンに一致しないメッセージ `/[gm][ta][mi]/` をフィルター処理します。 ****  DevTools は、メッセージ テキストにパターンが見つかったか、メッセージがログに記録される原因となるスクリプトをチェックします。  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="正規表現に一致しないメッセージをフィルター処理する" lightbox="../media/console-filter-regex.msft.png":::
   正規表現に一致しないメッセージを `/[gm][ta][mi]/` フィルター処理する  
:::image-end:::  

## <a name="run-javascript"></a>JavaScript の実行  

このセクションでは、コンソールでの JavaScript の実行に関連する機能について説明します。  実践的なチュートリアルの場合は、[JavaScript の実行 [] に移動します][DevToolsConsoleOverviewJavascript]。  

### <a name="re-run-expressions-from-history"></a>履歴から式を再実行する  

コンソールで前に実行した JavaScript 式の履歴を循環するキー `Up Arrow` を選択します。  この式 `Enter` を再度実行する場合に選択します。  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a>Live Expression を使用して、リアルタイムで式の値を確認する  

コンソールで同じ JavaScript 式を繰り返し入力すると、Live 式の作成が簡単になる **場合があります**。  Live **Expression を使用すると** 、一度式を入力し、本体の上部にピン留めします。  式の値は、ほぼリアルタイムで更新されます。  [ライブ式 [を使用して JavaScript 式Real-Timeを監視する] に移動します][DevToolsConsoleLiveExpressions]。  

### <a name="disable-eager-evaluation"></a>一時的な評価を無効にする  

コンソールに JavaScript 式を入力すると、 **その** 式の戻り値のプレビューが表示されます。  [[コンソールの設定] を](#open-console-settings) 開き、[ **熱心な評価** ] チェック ボックスを無効にして、戻り値のプレビューをオフにします。  

### <a name="disable-autocomplete-from-history"></a>履歴からオートコンプリートを無効にする  

式を入力すると、コンソールのオートコンプリート ポップアップ ウィンドウに、前に実行した式が表示されます。  これらの式の先頭には、文字が付加 `>` されます。  [[コンソール設定] を](#open-console-settings) 開き、[ **履歴からオートコンプリート** ] チェック ボックスをオフにして、履歴からの式の表示を停止します。  

> [!NOTE]
> 次の図では、 `document.querySelector('a')` `document.querySelector('img')` 前に評価された式を示します。  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="オートコンプリート ポップアップに履歴の式が表示される" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   オートコンプリート ポップアップに履歴の式が表示される  
:::image-end:::  

### <a name="select-javascript-context"></a>JavaScript コンテキストの選択  

既定では **、JavaScript Context ドロップダウン**は**** top に設定され[][MDNBrowsingContext]、メイン ドキュメントの参照コンテキストを表します。  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="[JavaScript コンテキスト] ドロップダウン" lightbox="../media/console-dom-level-top.msft.png":::
   **[JavaScript コンテキスト] ドロップダウン**  
:::image-end:::  

ページに広告が埋め込まれているとします `<iframe>` 。  広告の DOM を調整するために JavaScript を実行する必要があります。  まず、[JavaScript コンテキスト] ドロップダウンから広告の参照コンテキスト **を選択する必要** があります。  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="別の JavaScript コンテキストを選択する" lightbox="../media/console-dom-level-multiple.msft.png":::
   別の JavaScript コンテキストを選択する  
:::image-end:::  

## <a name="clear-the-console"></a>コンソールをクリアする  

コンソールをクリアするには、次のワークフローを使用できます。  

*   [Clear **Console** \( ![ Clear Console ](../media/clear-console-button-icon.msft.png) \] )を選択します。  
*   メッセージにカーソルを置き、コンテキスト メニュー \(righ-click\) を開き、[コンソールのクリア] **を選択します**。  
*   コンソール `clear()` に入力 **し、 を** 選択します `Enter` 。  
*   Web `console.clear()` ページの JavaScript から実行します。  
*   コンソール `Control` + `L` がフォーカス**されている間**に選択します。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "[Microsoft Edge DevTools コマンド] メニューメニューを使用してコマンドを実行|Microsoft Docs"  
[DevToolsConsoleViewMessages]: ./index.md#viewing-logged-messages "ログに記録されたメッセージの表示 - コンソールの概要|Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevToolsConsoleOverviewJavascript]: ./index.md#running-javascript "JavaScript の実行 - コンソールの概要|Microsoft Docs"  
[DevToolsConsoleJavascript]: ./javascript.md "コンソール サーバーで JavaScript を実行する方法を|Microsoft Docs"  
[DevToolsConsoleLiveExpressions]: ./live-expressions.md "Live Expression を使用して JavaScript 式の値をリアルタイムで|Microsoft Docs"  
[DevToolsConsoleLog]: ./log.md "コンソール ウィンドウでメッセージをログに記録する方法を|Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "参照コンテキスト |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
