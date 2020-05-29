---
title: コンソールでのメッセージの記録を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d3dbec41bc1e53b5e9001551c796e5a495dd331e
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601734"
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





# コンソールでのメッセージの記録を開始する   



この対話形式のチュートリアルでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]コンソールでメッセージの記録とフィルター処理を行う方法について説明します。  

> ##### 図 1  
> コンソールでのメッセージ  
> ![コンソールでのメッセージ][ImageLogExample]  

このチュートリアルは順番どおりに完了することを目的としています。  JavaScript を使用してページにインタラクティビティを追加する方法など、web 開発の基礎を理解していることを前提としています。  

## デモツールと DevTools をセットアップする   

このチュートリアルは、デモを開き、すべてのワークフローを自分で試すことができるように設計されています。  実際にフォローすると、後でワークフローを覚える可能性が高くなります。  

1.  `Control`[\ (Windows \)] または `Command` [\ (macOS \)] を押したまま、新しいタブで開くための**コンソールログの例**をクリックします。  
    
    [コンソールログの例][GlitchDevToolsConsoleLogExamples]
    
    <!-- > [!TIP]
    > Move the demo to a separate window.  
    > 
    > > ##### old Figure 2  
    > > The tutorial on the left, and the demo on the right  
    > > ![The tutorial on the left, and the demo on the right][ImageLogSetUp1]  -->
    
1.  デモにフォーカスを置いて、 `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押すと、devtools を開くことができます。  既定では、DevTools がデモの右側に表示されます。  
    
    > ##### 図 2  
    > デモの右側に DevTools が開きます。  
    > ![開発ツール] がデモの右側に表示されます。[ImageDevToolsRight]  
    
    > [!TIP]
    > [ウィンドウの下部に DevTools をドッキングするか、別のウィンドウに][DevToolsCustomizePlacement]ドッキングします。  
    
    > ##### 図 3  
    > デモの下部にドッキングされた DevTools  
    > ![デモの下部にドッキングされた DevTools][Imagedevツールボトム]  
    
    > ##### 図 4  
    > 別のウィンドウに表示されるブラウザー  
    > ![別のウィンドウで表示する][ImageDevToolsSeparateBrowse]  
    
    > ##### 図 5  
    > 別のウィンドウでアンドックされる DevTools  
    > ![DevTools (別のウィンドウでドッキングされる)][ImageDevToolsSeparateDevTools]  
    
## JavaScript から記録されたメッセージを表示する   

本体に表示されるほとんどのメッセージは、ページの JavaScript を作成した web 開発者から提供されます。  このセクションの目標は、コンソールに表示される可能性のあるさまざまなメッセージの種類について説明し、各メッセージの種類を自分の JavaScript から自分でログに記録する方法について説明します。  

1.  デモの [**ログ情報**] ボタンをクリックします。  `Hello, Console!` コンソールにログインします。
    
    > ##### 図 6  
    > **ログ情報**をクリックした後の本体  
    > ![Log Info] をクリックした後のコンソール[ImageLogInfo]  
    
1.  コンソールのメッセージの横にある `Hello, Console!` **「.log: 2**」をクリックします。  [ソース] パネルが開き、メッセージがコンソールに記録される原因となったコード行が強調表示されます。  ページの JavaScript の実行時にメッセージが記録されました `console.log('Hello, Console!')` 。
    
    > ##### 図 7  
    > [DevTools] をクリックすると、[ソース] パネルが開きます **。 .js: 2**  
    > ![DevTools] をクリックすると、[ソース] パネルが開きます。 [2][ImageSourceLog]  
    
1.  次のいずれかのワークフローを使用して、コンソールに移動します。  
    
    *   [**コンソール**] タブをクリックします。  
    *   `Control` + `[` `Command` + `[` コンソールパネルがフォーカスされるまで、\ (Windows \) または \ (macOS \) キーを押します。  
    *   [コマンドメニューを開き][DevToolsCommandMenu]、入力を開始して `Console` 、[**コンソールパネルを表示**] コマンドを選択し、を押し `Enter` ます。  
    
1.  デモの [**ログの警告**] をクリックします。  `Abandon Hope All Ye Who Enter` コンソールにログインします。  次のように書式設定されたメッセージは警告です。  
    
    > ##### 図 8  
    > [**ログの警告**] をクリックした後の本体  
    > ![ログの警告] をクリックした後のコンソール[Imageconの Elogwarning]  
    
    > [!TIP]
    > メッセージが特定の方法でログに記録される原因となったコードを表示する場合は、スクリプト (\ など) をクリックして、 `log.js:12` メッセージの書式設定を引き起こしたコードを表示します。  

1.  **Expand** ![ の前にある展開展開アイコンをクリックし ][ImageExpandIcon] `Abandon Hope All Ye Who Enter` ます。  DevTools は、呼び出しにつながる[スタックトレース][WikiStackTrace]を示します。  
    
    > ##### 図 9  
    > スタックトレース  
    > ![スタックトレース][ImageStackTrace]  
    
    スタックトレースでは、という名前の関数が呼び出されたことが通知され `logWarning` ます。これは、という名前の関数が呼び出され `quoteDante` ます。  つまり、最初に発生した通話はスタックトレースの一番下にあります。  スタックトレースの記録は、いつでも呼び出すことができ `console.trace()` ます。  

1.  [**ログエラー**] をクリックします。  次のエラーメッセージが記録されます。 `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    > ##### 図 10  
    > エラーメッセージ  
    > ![エラーメッセージ][ImageLogError]  
    
1.  [ **Log Table**] をクリックします。  有名なアーティストについての表が本体に記録されます。  
    
    > [!NOTE]
    > `birthday`列は1つの行にのみ設定されます。  その理由については、コードを確認してください。
    
    > ##### 図 11  
    > コンソールの表  
    > ![コンソール内のテーブル][Imageconetable]  
    
1.  [ **Log Group**] をクリックします。  4つの有名、犯罪 turtles の名前はラベルの下にグループ化されてい `Adolescent Irradiated Espionage Tortoises` ます。  
    
    > ##### 図 12  
    > コンソールのメッセージのグループ  
    > ![コンソールのメッセージグループ][Imageconeloggroup]  
    
1.  [ **Custom Custom**] をクリックします。  赤い境界線の付いたメッセージと青色の背景が本体に記録されます。  
    
    > ##### 図 13  
    > コンソールでのカスタム書式設定を含むメッセージ  
    > ![コンソールでのカスタム書式設定付きメッセージ][Imageconの Elogcustom書式]  
    
ここでの主なアイデアは、JavaScript からコンソールにメッセージを記録するときに、メソッドの1つを使うことです `console` 。  各メソッドは、異なる形式のメッセージを表示します。  

このセクションで説明されている方法よりも、さらに多くの方法があります。  このチュートリアルでは、残りのメソッドについて説明します。  

## ブラウザーでログに記録されたメッセージを表示する   

ブラウザーでも、コンソールにメッセージが記録されます。  これは通常、ページに問題がある場合に発生します。  

1.  [**原因 404**] をクリックします。  `404`ページの JavaScript が存在しないファイルを取得しようとしたため、ブラウザーはネットワークエラーをログに記録します。  
    
    > ##### 図 14  
    > 本体の404エラー  
    > ![コンソールの404エラー][Imageconの Elogerror]  
    
1.  [**原因エラー**] をクリックします。  `TypeError`JavaScript が存在しない DOM ノードを更新しようとしているため、ブラウザーは不明なログを記録します。  
    
    > ##### 図 15  
    > 本体の TypeError  
    > !(コンソールの TypeError)[Imageconelogtypeerror]  
    
1.  [**ログレベル**] ドロップダウンをクリックし、[**詳細**] オプションが無効になっている場合はそれを有効にします。  フィルター処理の詳細については、次のセクションを参照してください。  次のメッセージが表示されるようにするには、これを行う必要があります。  
    
    > ##### 図 16  
    > **詳細**ログレベルを有効にする  
    > ![詳細ログレベルを有効にします][ImageVerboseLogLevel]  
    
1.  [**原因違反**] をクリックします。  ページが数秒間応答しなくなった後、ブラウザーで本体にメッセージが記録され `[Violation] 'click' handler took 3000ms` ます。  正確な期間は異なる場合があります。  
    
    > ##### 図 17  
    > 本体の違反  
    > ![コンソールの違反][Imageconの Elog違反]  
    
## メッセージをフィルター処理する   

一部のページでは、コンソールにメッセージがあふれて表示されます。  DevTools には、現在のタスクに関連しないメッセージをフィルター処理するさまざまな方法が用意されています。  

### ログレベルでフィルター処理する   

各 `console` メソッドには、、、、 `Verbose` `Info` `Warning` またはなどの重大度レベルが割り当てられます `Error` 。  たとえば、はレベルのメッセージです。のように、 `console.log()` `Info` レベルのメッセージです `console.error()` `Error` 。  

1.  [**ログレベル**] ドロップダウンをクリックして**エラー**を無効にします。  横にチェックマークが表示されなくなった場合、レベルは無効になります。  レベルのメッセージが表示さ `Error` れなくなります。  
    
    > ##### 図18  
    > `Error`コンソールでのメッセージレベルの無効化  
    > ![エラーレベルメッセージをコンソールで無効にする][Imageconの Edisabeconlogerror]  
    
1.  [**ログレベル**] ドロップダウンをもう一度クリックし、**エラー**を再度有効にします。  レベルのメッセージが再び表示さ `Error` れます。  

### テキストでフィルター処理する   

正確な文字列を含むメッセージのみを表示する場合は、その文字列を [**フィルター** ] テキストボックスに入力します。  

1.  `Dave`[**フィルター** ] テキストボックスに入力します。  文字列を含まないすべてのメッセージ `Dave` は非表示になります。  また、ラベルが表示される場合もあり `Adolescent Irradiated Espionage Tortoises` ます。  これはバグです。  
    
    > ##### 図19  
    > 含まれていないメッセージをフィルターで除外する `Dave`  
    > ![Dave に含まれていないメッセージをフィルター処理する][ImageLogTextFiltering]  
    
1.  `Dave`[**フィルター** ] テキストボックスから削除します。  すべてのメッセージが再び表示されます。  

### 正規表現によるフィルター   

特定の文字列ではなく、テキストのパターンを含むすべてのメッセージを表示する場合は、[正規表現][MDNRegularExpressions]を使用します。  

1.  `/^[AH]/`[**フィルター** ] テキストボックスに入力します。  このパターンを[RegExr][|::ref1::|Main]に入力して、実行内容の説明を入力します。  
    
    > ##### 図20  
    > パターンに一致しないメッセージをフィルターで除外する `/^[AH]/`  
    > ![パターンに一致しないメッセージをフィルター処理する][ImageLogRegExFiltering]  
    
1.  `/^[AH]/`[**フィルター** ] テキストボックスから削除します。  すべてのメッセージが再び表示されます。  

### メッセージソース別にフィルターを適用する   

特定の URL のメッセージのみを表示するには、**サイドバー**を使用します。  

1.  [**コンソールサイドバーの表示**] をクリックして ![ 、コンソールサイドバーを表示し ][ImageShowConsoleSidebarIcon] ます。  
    
    > ##### 図21  
    > サイドバー  
    > ![サイドバー][Imagecones$ Ide バー]  
    
1.  メッセージ数の横に**ある展開展開** ![ アイコンをクリックし ][ImageExpandIcon] ます。  [図 21](#figure-21)では、メッセージの数が13個の**メッセージ**として表示されています。  **サイドバー**には、メッセージが記録される原因となった url の一覧が表示されます。  たとえば、11個のメッセージが発生しました `log.js` 。  
    
    > ##### 図22  
    > サイドバーでのメッセージのソースの表示  
    > ![サイドバーでのメッセージのソースの表示][Imagecones$ Ide バー Logsource]  
    
### ユーザーメッセージでフィルターを適用する   

以前は、[**ログ情報**] をクリックしたときに、 `console.log('Hello, Console!')` メッセージをコンソールにログするためのスクリプトが呼び出されます。  このような JavaScript から記録されるメッセージは、「**ユーザメッセージ**」と呼ばれます。  これに対して、[**原因 404**] をクリックすると、 `Error` 要求されたリソースが見つからなかったことを示すレベルのメッセージがブラウザーでログに記録されます。  そのようなメッセージは、**ブラウザーメッセージ**とみなされます。  **サイドバー**を使用して、ブラウザーメッセージをフィルター処理し、ユーザーメッセージのみを表示します。  

1.  [ **9 ユーザーメッセージ**] をクリックします。  ブラウザーのメッセージが非表示になります。  
    
    > ##### 図23  
    > ブラウザーメッセージのフィルター処理  
    > ![ブラウザーメッセージのフィルター処理][Imageconの Elogbrowserfiltering]  
    
1.  [ **13**個のメッセージ] をクリックすると、再びすべてのメッセージが表示されます。  

## 他のパネルと共に本体を使用する   

スタイルを編集していても、コンソールログの何かをすばやく確認する必要がある場合はどうすればよいですか。 引き出しを使用します。  

1.  [**要素**] タブをクリックします。  
1.  キーを押し `Escape` ます。  **ドロワー**の [コンソール] タブが開きます。  このチュートリアルで使用しているコンソールパネルのすべての機能が含まれています。  
    
    > ##### 図24  
    > ドローワの [コンソール] タブ  
    > ![ドローワ] の [コンソール] タブ[ImageDrawerConsole]  
    
<!--## Next steps  -->

<!--
*   See [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   See [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   See [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

 



<!-- image links -->  

[ImageExpandIcon]: /microsoft-edge/devtools-guide-chromium/media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: /microsoft-edge/devtools-guide-chromium/media/show-console-sidebar-icon.msft.png  

[ImageLogExample]: /microsoft-edge/devtools-guide-chromium/media/console-ars-technica-console-onload.msft.png "図 1: 本体のメッセージ"  
<!--[ImageLogSetUp1]: /microsoft-edge/devtools-guide-chromium/media/log-set-up-1.msft.png "old Figure 2: The tutorial on the left, and the demo on the right"  -->  
[Imagedevtools Right]:/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-right-console.msft.png "図 2: DevTools がデモの右側に表示されます"  
[Imagedevtools Bottom]:/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-bottom-console.msft.png "図 3: デモツールの下部にドッキングされた DevTools」  
[ImageDevToolsSeparateBrowse]:/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-separate-console-browse.msft.png "図 4: 別のウィンドウに表示されるブラウザー"  
[ImageDevToolsSeparateDevTools]:/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-separate-console-devtools.msft.png "図 5: DevTools が別のウィンドウでアンドックされる  
[ImageLogInfo]:/microsoft-edge/devtools-guide-chromium/media/console-log-info.msft.png "図 6: ログ情報をクリックした後のコンソール  
[ImageSourceLog]:/microsoft-edge/devtools-guide-chromium/media/console-sources-logjs.msft.png "図 7: DevTools [ソース] パネルを開くには、[ログの作成] をクリックします。 2"  
[Imageconの Elogwarning]:/microsoft-edge/devtools-guide-chromium/media/console-log-warning.msft.png "図 8: ログ警告のクリック後のコンソール  
[ImageStackTrace]:/microsoft-edge/devtools-guide-chromium/media/console-log-warning-expanded.msft.png "図 9: スタックトレース"  
[ImageLogError]:/microsoft-edge/devtools-guide-chromium/media/console-log-error.msft.png "図 10: エラーメッセージ"  
[ImageConsoleTable]:/microsoft-edge/devtools-guide-chromium/media/console-log-table.msft.png "図 11: 本体の表"  
[ImageConsoleLogGroup]:/microsoft-edge/devtools-guide-chromium/media/console-log-group.msft.png "図 12: 本体のメッセージのグループ"  
[Imagecon/microsoft-edge/devtools-guide-chromium/media/console-log-custom.msft.png Elogcustomcustom書式]: "図 13: 本体にユーザー設定の書式設定が表示されたメッセージ"  
[Imagecon/microsoft-edge/devtools-guide-chromium/media/console-cause-404.msft.png Elogerror]: "図 14: 本体の404エラー  
[Imagecon/microsoft-edge/devtools-guide-chromium/media/console-cause-error.msft.png Elogtypeerror]: "Figure 15: 本体の TypeError"  
[ImageVerboseLogLevel]:/microsoft-edge/devtools-guide-chromium/media/console-cause-error-log-levels.msft.png "図 16: 詳細ログレベルを有効にする"  
[Imagecon/microsoft-edge/devtools-guide-chromium/media/console-cause-violation.msft.png Elog違反]: "Figure 17: 本体の違反"  
[Imagecon/microsoft-edge/devtools-guide-chromium/media/console-cause-violation-log-levels.msft.png Edisabeconlogerror]: "図 18: 本体のエラーレベルのメッセージを無効にする"  
[ImageLogTextFiltering]:/microsoft-edge/devtools-guide-chromium/media/console-all-messages-text-filter.msft.png "図 19: Dave" が含まれていないメッセージをフィルターで除外する  
[ImageLogRegExFiltering]:/microsoft-edge/devtools-guide-chromium/media/console-all-messages-regex-filter.msft.png "図 20: パターンに一致しないメッセージをフィルターで除外する"  
[Imagecones$ Ide バー]:/microsoft-edge/devtools-guide-chromium/media/console-sidebar-all-messages.msft.png "図 21: サイドバー"  
[Imagecones$ Ide Barlogsource]:/microsoft-edge/devtools-guide-chromium/media/console-sidebar-expanded-all-messages.msft.png "図 22: サイドバーにメッセージのソースを表示します。  
[Imagecon/microsoft-edge/devtools-guide-chromium/media/console-sidebar-user-messages.msft.png Elogbrowserfiltering]: "図 23: ブラウザーメッセージをフィルター処理する"  
[ImageDrawerConsole]:/microsoft-edge/devtools-guide-chromium/media/console-elements-drawer-console-sidebar-all-messages.msft.png "Figure 24: ドローワの [コンソール] タブ  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge \ (Chromium) 開発者ツール"  
[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "本体の API リファレンス"  
[DevToolsConsoleReference]: /microsoft-edge/devtools-guide-chromium/console/reference "本体のリファレンス"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "メッセージの記録を開始する |故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正規表現 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "スタックトレース-Wikipedia"  


> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/log)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
