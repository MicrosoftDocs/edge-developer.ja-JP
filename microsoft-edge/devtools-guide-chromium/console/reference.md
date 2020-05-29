---
title: 本体のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bd2a610b48905c6651663d490b9c9f1a0a8c7674
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601787"
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



このページでは、Microsoft Edge DevTools コンソールに関連する機能のリファレンスを示します。  ログに記録されたメッセージを表示して JavaScript を実行するには、既にコンソールを使用していることを前提としています。  表示されない場合は、「[コンソールでの JavaScript の実行を開始する][DevToolsConsoleJavascript]」を参照してください。[コンソールでのメッセージの記録を開始][DevToolsConsoleLog]します。  

API 参照を検索する場合は、 `console.log()` 「[コンソール API リファレンス][DevToolsConsoleApi]」をご覧ください。  `monitorEvents()`「[コンソールユーティリティ API リファレンス][DevToolsConsoleUtilities]」などの関数のリファレンスについては、こちらを参照してください。  

## 本体を開く   

コンソールは、引き出しの[パネル](#open-the-console-panel)または[タブ](#open-the-console-tab-in-the-drawer)として開くことができます。  

### コンソールパネルを開く   

`Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。  

> ##### 図 1  
> コンソールパネル  
> ![コンソールパネル][ImageConsolePanel]  

[コマンドメニュー][DevToolsCommandMenu]からコンソールパネルを開くには、入力を開始してから `Console` 、その横にある**パネル**バッジのある [**コンソールの表示**] コマンドを実行します。  

> ##### 図 2  
> コンソールパネルを表示するためのコマンド  
> ![コンソールパネルを表示するためのコマンド][ImageCommandShowConsole]  

### ドロワーで [コンソール] タブを開く   

[ `Escape` **カスタマイズと制御**] をクリックして、[ `...` **コンソールドローワの表示**] を選択します。  

> ##### 図 3  
> コンソールのドローワを表示  
> ![コンソールのドローワを表示][ImageShowConsoleDrawer]  

[**コンソール**] タブを開いた状態で、[devtools] ウィンドウの下部に引き出しがポップアップ表示されます。  

> ##### 図 4  
> ドローワの [コンソール] タブ  
> ![ドローワの [コンソール] タブ][ImageDrawerConsole]  

[コマンドメニュー][DevToolsCommandMenu]から [コンソール] タブを開くには、入力を開始してから `Console` 、横にある**ドローワ**バッジが付いている [ **console を表示**] コマンドを実行します。  

> ##### 図 5  
> ドロワーの [コンソール] タブを表示するためのコマンド  
> ![ドロワーの [コンソール] タブを表示するためのコマンド][ImageShowDrawerCommand]  

### コンソールの設定を開く   

[**本体の設定**] ![ コンソール設定をクリックし ][ImageSettingsButtonIcon] ます。  

> ##### 図 6  
> 本体の設定  
> ![本体の設定][ImageConsoleSettings]  

以下のリンクでは、各設定について説明します。  

*   [**ネットワークの非表示**](#hide-network-messages)  
*   [**ログを保存する**](#persist-messages-across-page-loads)  
*   [**選択されたコンテキストのみ**](#filter-out-messages-from-different-contexts)  
*   [**類似グループ**](#disable-message-grouping)  
*   [**ログ XmlHttpRequests**](#log-xhr-and-fetch-requests)  
*   [**一括評価**](#disable-eager-evaluation)  
*   [**履歴からのオートコンプリート**](#disable-autocomplete-from-history)  

### コンソールサイドバーを開く   

[**コンソールサイドバーの表示**] ![ をクリックすると ][ImageShowConsoleSidebarIcon] 、サイドバーが表示され、フィルター処理に役立ちます。  

> ##### 図 7  
> 本体のサイドバー  
> ![本体のサイドバー][ImageConsoleSidebar]  

## メッセージを表示する   

このセクションには、コンソールでのメッセージの表示方法を変更する機能が含まれています。  実践的なチュートリアルについては、「[メッセージを表示][DevToolsConsoleViewMessages]する」をご覧ください。  

### メッセージのグループ化を無効にする   

コンソールの[[設定](#open-console-settings)] を開いて、**同様のグループ**を無効にして、コンソールの既定のメッセージグループ化動作を無効にします。  例については[、「XHR をログに記録する要求を取得](#log-xhr-and-fetch-requests)する」を参照してください。  

### XHR と Fetch 要求をログに記録する   

[[コンソールの設定](#open-console-settings)] を開いて、**ログ XMLHttpRequests**を有効にして、発生した場合に、すべて `XMLHttpRequest` の要求と本体の要求をログに記録し `Fetch` ます。  

> ##### 図 8  
> ログ `XMLHttpRequest` と `Fetch` 要求  
> ![XMLHttpRequest とフェッチ要求のログ記録][ImageXhrGrouped]  

[図 8](#figure-8)の上位のメッセージは、本体の既定のグループ化動作を示しています。  <!--  [Figure 9](#figure-9) shows how the same log looks after [disabling message grouping](#disable-message-grouping).  -->  

<!--

> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> ![How the logged XMLHttpRequest and Fetch requests look after ungrouping][ImageXhrUngrouped]  

-->

<!--todo: add example for ungrouping console items  -->  

### ページの読み込み中にメッセージを保持する   

既定では、新しいページを読み込むたびに本体がクリアされます。  ページの読み込み中にメッセージを保持するには、[[コンソールの設定](#open-console-settings)] を開き、[**ログの保持**] チェックボックスをオンにします。  

### ネットワークメッセージを非表示にする   

既定では、ブラウザーはネットワークメッセージを**コンソール**に記録します。  たとえば、[図 9](#figure-9)で選んだメッセージは、の状態コードを表し `429` ます。  

> ##### 図 9  
> コンソールの429メッセージ  
> ![コンソールの429メッセージ][Image429Message]  

ネットワークメッセージを非表示にするには:  

1.  [[コンソールの設定](#open-console-settings)] を開きます。  
1.  [**ネットワークを非表示**にする] チェックボックスをオンにします。  

## メッセージをフィルター処理する   

コンソールでメッセージをフィルター処理するには、さまざまな方法があります。  

### ブラウザーメッセージをフィルターで除外する   

[コンソールのサイドバーを開き](#open-the-console-sidebar)、[**ユーザーメッセージ**] をクリックして、そのページの JavaScript から送信されたメッセージのみを表示します。  

> ##### 図 10  
> ユーザーメッセージの表示  
> ![ユーザーメッセージの表示][ImageUserMessages]  

### ログレベルでフィルター処理する   

DevTools `console.*` は、各メソッドに重大度レベルを割り当てます。  4つのレベルがあります。、、、 `Verbose` `Info` `Warning` 、 `Error` です。  たとえば、 `console.log()` はグループ内にありますが、 `Info` `console.error()` はグループ内にあり `Error` ます。  [コンソール API リファレンス][DevToolsConsoleApi]では、適用可能な各メソッドの重大度レベルについて説明します。  ブラウザーが本体に記録するすべてのメッセージには、重要度のレベルもあります。  目的のメッセージのレベルをすべて非表示にすることができます。  たとえば、メッセージだけを知りたい場合は、 `Error` 他の3つのグループを非表示にすることができます。  

[**ログレベル**] ドロップダウンをクリックして、 `Verbose` `Info` `Warning` またはメッセージを有効または無効にし `Error` ます。  

> ##### 図 11  
> [**ログレベル**] ドロップダウン  
> ![ログレベル] ドロップダウンリスト[ImageLogLevels]  

また、[コンソールサイドバーを開い](#open-the-console-sidebar)て、[**エラー**]、[**警告**]、[**情報**]、または [**詳細**] をクリックして、ログレベルでフィルター処理することもできます。  

> ##### 図 12  
> サイドバーを使用して警告を表示する  
> ![サイドバーを使って警告を表示][ImageSidebarWarnings]  

### URL でメッセージをフィルター処理する   

その URL を入力すると、その URL に由来する `url:` メッセージのみが表示されます。  「Devtools」と入力すると、 `url:` 関連するすべての url が表示されます。  ドメインも機能します。  たとえば、 `https://example.com/a.js` `https://example.com/b.js` メッセージがログに記録されている場合は、 `url:https://example.com` これら2つのスクリプトからのメッセージに集中することができます。  

> ##### 図 13  
> URL フィルター  
> ![URL フィルター][ImageUrlFilter]  

`-url:`その URL からのメッセージを非表示にするように入力します。  これは、否定 URL フィルターと呼ばれます。  

> ##### 図 14  
> URL に一致するすべてのメッセージを非表示にする負の URL フィルター `https://b.wal.co`  
> ![URL に一致するすべてのメッセージを非表示にする負の URL フィルター https://b.wal.co ][ImageNegativeUrlFilter1]  

[コンソールサイドバーを開い](#open-the-console-sidebar)て、[**ユーザーメッセージ**] セクションを展開し、フォーカスを移動するメッセージを含むスクリプトの url をクリックして、1つの url からのメッセージを表示することもできます。  

> ##### 図 15  
> 送信元のメッセージを表示する `wp-ad.min.js`  
> ![Wp-ad からのメッセージを表示する][ImageNegativeUrlFilter2]  

### さまざまなコンテキストからのメッセージをフィルター処理する   

ページに広告 \ (広告 \) があるものとします。  広告がに埋め込まれていて、 `<iframe>` 本体に大量のメッセージが生成されています。  広告は別の[JavaScript コンテキスト](#select-javascript-context)で実行されているため、メッセージを非表示にする方法の1つとして、[コンソール設定を開い](#open-console-settings)て、**選択したコンテキストのみ**のチェックボックスを有効にする方法があります。  

### 正規表現パターンに一致しないメッセージをフィルターで除外する   

[ `/[gm][ta][mi]/` **フィルター** ] テキストボックスに、そのパターンに一致しないすべてのメッセージをフィルター処理するための正規表現を入力します。  DevTools は、メッセージテキストまたはメッセージの記録を引き起こしたスクリプトで、パターンが検出されたかどうかを確認します。  

> ##### 図 16  
> 一致しないメッセージをフィルターで除外する `/[gm][ta][mi]/`  
> ![Regex の式と一致しないメッセージをフィルター処理する][ImageRegExFilter]  

## JavaScript を実行する   

このセクションには、本体での JavaScript の実行に関連する機能が含まれています。  実践的なチュートリアルについては、「 [JavaScript を実行][DevToolsConsoleOverviewJavascript]する」を参照してください。  

### 履歴からの式の再実行   

キーを押して、 `Up Arrow` コンソールで前に実行した JavaScript 式の履歴を順に切り替えます。  を押して `Enter` その式を再実行します。  

### ライブ式を使用して、式の値をリアルタイムで見る   

コンソールで同じ JavaScript 式を繰り返し入力したことがわかった場合は、**ライブ式**の作成が簡単になることがあります。  **ライブ式**で式を1回入力し、本体の先頭に固定します。  この式の値は、ほぼリアルタイムで更新されます。  詳しく[は、「ライブ式を使って JavaScript の式値をリアルタイムで見る][DevToolsConsoleLiveExpressions]」をご覧ください。  

### 一括評価を無効にする   

本体に JavaScript の式を入力すると、その式の戻り値のプレビュー**が表示さ**れます。  [[本体の設定](#open-console-settings)] を開き、[先行の**評価**] チェックボックスをオフにして戻り値のプレビューをオフにします。  

### 履歴からオートコンプリートを無効にする   

式を入力すると、本体の [オートコンプリート] ポップアップウィンドウに、前に実行した式が表示されます。  これらの式は文字で先頭に付けられ `>` ます。  [[コンソールの設定](#open-console-settings)] を開いて、[履歴の**オートコンプリート**] チェックボックスをオフにして、履歴からの式の表示を停止します。  

> [!NOTE]
> [図 17](#figure-17)で、 `document.querySelector('a')` `document.querySelector('img')` 前に評価した式を示します。  

> ##### 図 17  
> 履歴の式が表示されたオートコンプリートのポップアップ  
> ![履歴の式を表示するオートコンプリート] ポップアップ[Imagehistory オートコンプリート]  

### JavaScript のコンテキストを選ぶ   

既定では、 **JavaScript コンテキスト**のドロップダウンは [**先頭**] に設定されています。これは、メインドキュメントの[閲覧コンテキスト][MDNBrowsingContext]を表します。  

> ##### 図18  
> **JavaScript コンテキスト**のドロップダウン  
> ![JavaScript コンテキスト] ドロップダウン[ImageJavascriptContext]  

ページに広告が埋め込まれていると `<iframe>` します。  広告の DOM を調整するために JavaScript を実行します。  まず、 **JavaScript のコンテキスト**ドロップダウンから広告の閲覧コンテキストを選択する必要があります。  

> ##### 図19  
> 別の JavaScript コンテキストの選択  
> ![別の JavaScript コンテキストの選択][ImageSelectContext]  

## 本体をクリアする   

次のいずれかのワークフローを使用して本体をクリアすることができます。  

*   [**本体** ![ のクリア] ][ImageClearConsoleIcon] をクリックします。  
*   メッセージを右クリックし、[**コンソールのクリア**] を選択します。  
*   `clear()`コンソールに入力して、キーを押し `Enter` ます。  
*   `console.clear()`Web ページの JavaScript から通話を発信します。  
*   `Control` + `L` コンソールがフォーカスされているときにを押します。  

 



<!-- image links -->  

[ImageClearConsoleIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-console-button-icon.msft.png  
[ImageSettingsButtonIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-button-icon.msft.png  
[ImageShowConsoleSidebarIcon]: /microsoft-edge/devtools-guide-chromium/media/show-console-sidebar-icon.msft.png  

[ImageConsolePanel]: /microsoft-edge/devtools-guide-chromium/media/console-hello-console.msft.png "図 1: コンソールパネル"  
[ImageCommandShowConsole]: /microsoft-edge/devtools-guide-chromium/media/console-command-menu-show-console.msft.png "図 2: コンソールパネルを表示するためのコマンド"  
[ImageShowConsoleDrawer]: /microsoft-edge/devtools-guide-chromium/media/console-elements-customize-control-devtools-show-console-drawer.msft.png "図 3: 本体のドローワの表示"  
[ImageDrawerConsole]: /microsoft-edge/devtools-guide-chromium/media/console-elements-console-drawer-hello-world.msft.png "図 4: ドローワの [コンソール] タブ"  
[ImageShowDrawerCommand]: /microsoft-edge/devtools-guide-chromium/media/console-command-menu-show-console.msft.png "図 5: ドローワの [コンソール] タブを表示するためのコマンド"  
[ImageConsoleSettings]: /microsoft-edge/devtools-guide-chromium/media/console-settings-group-similar-empty.msft.png "図 6: 本体の設定"  
[ImageConsoleSidebar]: /microsoft-edge/devtools-guide-chromium/media/console-sidebar-drawer-empty.msft.png "図 7: 本体のサイドバー"  
[ImageXhrGrouped]: /microsoft-edge/devtools-guide-chromium/media/console-xhr-fetch.msft.png "図 8: XMLHttpRequest 要求とフェッチ要求のログ記録"  
<!--[ImageXhrUngrouped]: /microsoft-edge/devtools-guide-chromium/media/console-xhr-fetch-all.msft.png "Figure old 9: How the logged XMLHttpRequest and Fetch requests look after ungrouping"  -->  
[Image429Message]:/microsoft-edge/devtools-guide-chromium/media/console-show-network.msft.png "図 9: 本体の429メッセージ  
[ImageUserMessages]:/microsoft-edge/devtools-guide-chromium/media/console-sidebar-drawer-user-messages.msft.png "図 10: ユーザーメッセージの表示"  
[ImageLogLevels]:/microsoft-edge/devtools-guide-chromium/media/console-log-level-default-levels.msft.png "図 11: ログレベルのドロップダウン  
[ImageSidebarWarnings]:/microsoft-edge/devtools-guide-chromium/media/console-sidebar-warnings.msft.png "図 12: サイドバーを使って警告を表示する」を参照してください。  
[ImageUrlFilter]:/microsoft-edge/devtools-guide-chromium/media/console-filter-text.msft.png "図 13: URL フィルター"  
[ImageNegativeUrlFilter1]:/microsoft-edge/devtools-guide-chromium/media/console-negative-filter-text.msft.png "図 14: URL に一致するすべてのメッセージを非表示にする負 https://b.wal.co の url フィルター  
[ImageNegativeUrlFilter2]:/microsoft-edge/devtools-guide-chromium/media/console-filter-text-specified.msft.png "図 15: wp-ad から送信されたメッセージを表示する  
[Imager/microsoft-edge/devtools-guide-chromium/media/console-filter-regex.msft.png Exfilter]: "図 16: regex の式と一致しないメッセージをフィルターで除外する"  
[Imagehistory オートコンプリート]:/microsoft-edge/devtools-guide-chromium/media/console-filter-text-autofilter-history.msft.png "図 17: 履歴の式を表示するオートコンプリートポップアップ  
[ImageJavascriptContext]:/microsoft-edge/devtools-guide-chromium/media/console-dom-level-top.msft.png "図 18: JavaScript のコンテキストのドロップダウン  
[ImageSelectContext]:/microsoft-edge/devtools-guide-chromium/media/console-dom-level-multiple.msft.png "図 19: 別の JavaScript コンテキストの選択"  

<!-- links -->  

[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevToolsConsoleViewMessages]: /microsoft-edge/devtools-guide-chromium/console/index#viewing-logged-messages "ログメッセージの表示-コンソールの概要"  
[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "本体の API リファレンス"  
[DevToolsConsoleOverviewJavascript]: /microsoft-edge/devtools-guide-chromium/console/index#running-javascript "JavaScript の実行-本体の概要"  
[DevToolsConsoleJavascript]: /microsoft-edge/devtools-guide-chromium/console/javascript "本体の JavaScript の実行を開始する"  
[DevToolsConsoleLiveExpressions]: /microsoft-edge/devtools-guide-chromium/console/live-expressions "ライブ式を使って JavaScript の式値をリアルタイムで見る"  
[DevToolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "コンソールでのメッセージの記録を開始する"  
[DevToolsConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "コンソールユーティリティ API リファレンス"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "ブラウジングコンテキスト |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
