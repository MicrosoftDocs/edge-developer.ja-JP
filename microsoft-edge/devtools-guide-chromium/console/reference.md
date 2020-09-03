---
description: Microsoft Edge DevTools のコンソール UI に関連するすべての機能と動作に関する包括的な参照。
title: 本体のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6a79031e6efbc4b83b83685f32e060a6268dbb2a
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993143"
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





# 本体のリファレンス   



このページでは、Microsoft Edge DevTools コンソールに関連する機能のリファレンスを示します。  ログに記録されたメッセージを表示して JavaScript を実行するには、既にコンソールを使用していることを前提としています。  表示されない場合は、「 [コンソールでの JavaScript の実行を開始する][DevToolsConsoleJavascript] 」を参照してください。 [コンソールでのメッセージの記録を開始][DevToolsConsoleLog]します。  

API 参照を検索する場合は、 `console.log()` 「 [コンソール API リファレンス][DevToolsConsoleApi]」をご覧ください。  次のような関数のリファレンスについ `monitorEvents()` ては、「 [コンソールユーティリティ API リファレンス][DevToolsConsoleUtilities]」をご覧ください。  

## 本体を開く   

コンソールは、引き出しの [パネル](#open-the-console-panel) または [タブ](#open-the-console-tab-in-the-drawer)として開くことができます。  

### コンソールパネルを開く   

`Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="コンソールパネル" lightbox="../media/console-hello-console.msft.png":::
   **コンソール**パネル  
:::image-end:::  

[コマンドメニュー][DevToolsCommandMenu]からコンソールパネルを開くには、入力を開始してから `Console` 、その横にある**パネル**バッジのある [**コンソールの表示**] コマンドを実行します。  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="コンソールパネルを表示するコマンド" lightbox="../media/console-command-menu-show-console.msft.png":::
   **コンソール**パネルを表示するコマンド  
:::image-end:::  

### ドロワーで [コンソール] タブを開く   

[ `Escape` **カスタマイズと制御** ] を押します。 [(\)] をクリックして、[ `...` **コンソールドローワの表示**] を選択します。  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="コンソールのドローワを表示" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **コンソールのドローワを表示**  
:::image-end:::  

[ **コンソール** ] タブを開いた状態で、[devtools] ウィンドウの下部に引き出しがポップアップ表示されます。  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="ドローワの [コンソール] タブ" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   **ドローワ**の [**コンソール**] タブ  
:::image-end:::  

[コマンドメニュー][DevToolsCommandMenu]から [コンソール] タブを開くには、入力を開始してから `Console` 、横にある**ドローワ**バッジが付いている [ **console を表示**] コマンドを実行します。  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="[コンソール] タブをドローワに表示するコマンド" lightbox="../media/console-command-menu-show-console.msft.png":::
   [**コンソール**] タブを**ドローワ**に表示するコマンド  
:::image-end:::  

### コンソールの設定を開く   

[ **コンソールの設定** ] ( ![ コンソール ][ImageSettingsButtonIcon] の設定) をクリックします。  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="本体の設定" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **本体の設定**  
:::image-end:::  

以下のリンクでは、各設定について説明します。  

*   [**ネットワークの非表示**](#hide-network-messages)  
*   [**ログを保存する**](#persist-messages-across-page-loads)  
*   [**選択されたコンテキストのみ**](#filter-out-messages-from-different-contexts)  
*   [**類似グループ**](#disable-message-grouping)  
*   [**ログ XmlHttpRequests**](#log-xhr-and-fetch-requests)  
*   [**一括評価**](#disable-eager-evaluation)  
*   [**履歴からのオートコンプリート**](#disable-autocomplete-from-history)  
    
### コンソールサイドバーを開く   

[ **コンソールサイドバーの表示** ] ![ ][ImageShowConsoleSidebarIcon] をクリックすると、サイドバーが表示され、フィルター処理に役立ちます。  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="本体のサイドバー" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **本体** 記事  
:::image-end:::  

## メッセージを表示する   

このセクションには、コンソールでのメッセージの表示方法を変更する機能が含まれています。  実践的なチュートリアルについては、「 [メッセージを表示][DevToolsConsoleViewMessages] する」をご覧ください。  

### メッセージのグループ化を無効にする   

コンソールの[[設定](#open-console-settings)] を開いて、**同様のグループ**を無効にして、コンソールの既定のメッセージグループ化動作を無効にします。  例については [、「XHR をログに記録する要求を取得](#log-xhr-and-fetch-requests) する」を参照してください。  

### XHR と Fetch 要求をログに記録する   

[[コンソールの設定](#open-console-settings)] を開いて、**ログ XMLHttpRequests**を有効にして、発生した場合に、すべて `XMLHttpRequest` の要求と本体の要求をログに記録し `Fetch` ます。  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="XMLHttpRequest と Fetch 要求をログに記録する" lightbox="../media/console-xhr-fetch.msft.png":::
   ログ `XMLHttpRequest` と `Fetch` 要求  
:::image-end:::  
前の図の上部のメッセージには、 **本体**の既定のグループ化動作が表示されます。  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### ページの読み込み中にメッセージを保持する   

既定では、新しいページを読み込むたびに本体がクリアされます。  ページの読み込み中にメッセージを保持するには、[ [コンソールの設定](#open-console-settings) ] を開き、[ **ログの保持** ] チェックボックスをオンにします。  

### ネットワークメッセージを非表示にする   

既定では、ブラウザーはネットワークメッセージを **コンソール**に記録します。  次の図では、選択されたメッセージは、の HTTP 状態コードを表して `429` います。  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="コンソールの429メッセージ" lightbox="../media/console-show-network.msft.png":::
   `429`**本体**のメッセージ  
:::image-end:::  
ネットワークメッセージを非表示にするには:  

1.  [[コンソールの設定](#open-console-settings)] を開きます。  
1.  [ **ネットワークを非表示** にする] チェックボックスをオンにします。  
    
## メッセージをフィルター処理する   

コンソールでメッセージをフィルター処理するには、さまざまな方法があります。  

### ブラウザーメッセージをフィルターで除外する   

[コンソールのサイドバーを開き](#open-the-console-sidebar) 、[ **ユーザーメッセージ** ] をクリックして、そのページの JavaScript から送信されたメッセージのみを表示します。  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="ユーザーメッセージを表示する" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   ユーザーメッセージを表示する  
:::image-end:::  

### ログレベルでフィルター処理する   

DevTools `console.*` は、各メソッドに重大度レベルを割り当てます。  4つのレベルがあります。、、、 `Verbose` `Info` `Warning` 、 `Error` です。  たとえば、 `console.log()` はグループ内にありますが、 `Info` `console.error()` はグループ内にあり `Error` ます。  [コンソール API リファレンス][DevToolsConsoleApi]では、適用可能な各メソッドの重大度レベルについて説明します。  ブラウザーが本体に記録するすべてのメッセージには、重要度のレベルもあります。  目的のメッセージのレベルをすべて非表示にすることができます。  たとえば、メッセージだけを知りたい場合は、 `Error` 他の3つのグループを非表示にすることができます。  

[ **ログレベル** ] ドロップダウンをクリックして、 `Verbose` `Info` `Warning` またはメッセージを有効または無効にし `Error` ます。  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="[ログレベル] ドロップダウン" lightbox="../media/console-log-level-default-levels.msft.png":::
   [ **ログレベル** ] ドロップダウン  
:::image-end:::  

また、 [コンソールサイドバーを開い](#open-the-console-sidebar) て、[ **エラー**]、[ **警告**]、[ **情報**]、または [ **詳細**] をクリックして、ログレベルでフィルター処理することもできます。  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="サイドバーを使用して警告を表示する" lightbox="../media/console-sidebar-warnings.msft.png":::
   サイドバーを使用して警告を表示する  
:::image-end:::  

### URL でメッセージをフィルター処理する   

その URL を入力すると、その URL に由来する `url:` メッセージのみが表示されます。  「Devtools」と入力すると、 `url:` 関連するすべての url が表示されます。  ドメインも機能します。  たとえば、 `https://example.com/a.js` `https://example.com/b.js` メッセージがログに記録されている場合は、 `url:https://example.com` これら2つのスクリプトからのメッセージに集中することができます。  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL フィルター" lightbox="../media/console-filter-text.msft.png":::
   URL フィルター  
:::image-end:::  

`-url:`その URL からのメッセージを非表示にするように入力します。  これは、否定 URL フィルターと呼ばれます。  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="Url に一致するすべてのメッセージを非表示にする負の URL フィルター https://b.wal.co" lightbox="../media/console-negative-filter-text.msft.png":::
   Url に一致するすべてのメッセージを非表示にする負の URL フィルター `https://b.wal.co`
:::image-end:::  

[コンソールサイドバーを開い](#open-the-console-sidebar)て、[**ユーザーメッセージ**] セクションを展開し、フォーカスを移動するメッセージを含むスクリプトの url をクリックして、1つの url からのメッセージを表示することもできます。  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="wp-ad.min.js から送信されたメッセージを表示する" lightbox="../media/console-filter-text-specified.msft.png":::
   送信元のメッセージを表示する `wp-ad.min.js`  
:::image-end:::  

### さまざまなコンテキストからのメッセージをフィルター処理する   

ページに広告 \ (広告 \) があるものとします。  広告がに埋め込まれていて、 `<iframe>` 本体に大量のメッセージが生成されています。  広告は別の [JavaScript コンテキスト](#select-javascript-context)で実行されているため、メッセージを非表示にする方法の1つとして、 [コンソール設定を開い](#open-console-settings) て、 **選択したコンテキストのみ** のチェックボックスを有効にする方法があります。  

### 正規表現パターンに一致しないメッセージをフィルターで除外する   

[ `/[gm][ta][mi]/` **フィルター** ] テキストボックスに、そのパターンに一致しないすべてのメッセージをフィルター処理するための正規表現を入力します。  DevTools は、メッセージテキストまたはメッセージの記録を引き起こしたスクリプトで、パターンが検出されたかどうかを確認します。  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="Regex の式と一致しないメッセージをすべてフィルターで除外する" lightbox="../media/console-filter-regex.msft.png":::
   Regex の式に一致しないメッセージをすべてフィルターで除外する `/[gm][ta][mi]/`  
:::image-end:::  

## JavaScript の実行   

このセクションには、本体での JavaScript の実行に関連する機能が含まれています。  実践的なチュートリアルについては、「 [JavaScript を実行][DevToolsConsoleOverviewJavascript] する」を参照してください。  

### 履歴からの式の再実行   

キーを押して、 `Up Arrow` コンソールで前に実行した JavaScript 式の履歴を順に切り替えます。  を押して `Enter` その式を再実行します。  

### ライブ式を使用して、式の値をリアルタイムで見る   

コンソールで同じ JavaScript 式を繰り返し入力したことがわかった場合は、 **ライブ式**の作成が簡単になることがあります。  **ライブ式**で式を1回入力し、本体の先頭に固定します。  この式の値は、ほぼリアルタイムで更新されます。  詳しく [は、「ライブ式を使って JavaScript の式値をリアルタイムで見る][DevToolsConsoleLiveExpressions]」をご覧ください。  

### 一括評価を無効にする   

本体に JavaScript の式を入力すると、その式の戻り値のプレビュー **が表示さ** れます。  [[本体の設定](#open-console-settings)] を開き、[先行の**評価**] チェックボックスをオフにして戻り値のプレビューをオフにします。  

### 履歴からオートコンプリートを無効にする   

式を入力すると、本体の [オートコンプリート] ポップアップウィンドウに、前に実行した式が表示されます。  これらの式は文字で先頭に付けられ `>` ます。  [[コンソールの設定](#open-console-settings)] を開いて、[履歴の**オートコンプリート**] チェックボックスをオフにして、履歴からの式の表示を停止します。  

> [!NOTE]
> 次の図で `document.querySelector('a')` は、 `document.querySelector('img')` 前に評価された式を示します。  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="オートコンプリートのポップアップには、履歴の式が表示される" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   オートコンプリートのポップアップには、履歴の式が表示される  
:::image-end:::  

### JavaScript のコンテキストを選ぶ   

既定では、 **JavaScript コンテキスト** のドロップダウンは [ **先頭**] に設定されています。これは、メインドキュメントの [閲覧コンテキスト][MDNBrowsingContext] を表します。  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="JavaScript コンテキストのドロップダウン" lightbox="../media/console-dom-level-top.msft.png":::
   **JavaScript コンテキスト**のドロップダウン  
:::image-end:::  

ページに広告が埋め込まれていると `<iframe>` します。  広告の DOM を調整するために JavaScript を実行します。  まず、 **JavaScript のコンテキスト** ドロップダウンから広告の閲覧コンテキストを選択する必要があります。  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="別の JavaScript コンテキストを選択する" lightbox="../media/console-dom-level-multiple.msft.png":::
   別の JavaScript コンテキストを選択する  
:::image-end:::  

## 本体をクリアする   

次のいずれかのワークフローを使用して本体をクリアすることができます。  

*   [ **コンソールのクリア** ] ( ![ コンソール ][ImageClearConsoleIcon] のクリア) をクリックします。  
*   メッセージを右クリックし、[ **コンソールのクリア**] を選択します。  
*   `clear()`コンソールに入力して、キーを押し `Enter` ます。  
*   `console.clear()`Web ページの JavaScript から通話を発信します。  
*   `Control` + `L` コンソールがフォーカスされているときにを押します。  
    
<!--
 

  
-->  

<!-- image links -->  

[ImageClearConsoleIcon]: ../media/clear-console-button-icon.msft.png  
[ImageSettingsButtonIcon]: ../media/settings-button-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevToolsConsoleViewMessages]: ./index.md#viewing-logged-messages "ログメッセージの表示-本体の概要 |Microsoft ドキュメント"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft ドキュメント"  
[DevToolsConsoleOverviewJavascript]: ./index.md#running-javascript "JavaScript の実行-本体の概要 |Microsoft ドキュメント"  
[DevToolsConsoleJavascript]: ./javascript.md "本体の JavaScript の実行を開始する |Microsoft ドキュメント"  
[DevToolsConsoleLiveExpressions]: ./live-expressions.md "ライブ式を使用して JavaScript の式値をリアルタイムで見る |Microsoft ドキュメント"  
[DevToolsConsoleLog]: ./log.md "コンソールでのメッセージの記録を開始する |Microsoft ドキュメント"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "ブラウジングコンテキスト |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
