---
title: コンソールでのメッセージの記録を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c2cf868e6daaf9dd45c7acc90a71c2154261b9c3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982694"
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



この対話形式のチュートリアルでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] コンソールでメッセージの記録とフィルター処理を行う方法について説明します。  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="コンソールでのメッセージ" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   **コンソール**でのメッセージ  
:::image-end:::  

このチュートリアルは順番どおりに完了することを目的としています。  JavaScript を使用してページにインタラクティビティを追加する方法など、web 開発の基礎を理解していることを前提としています。  

## デモツールと DevTools をセットアップする   

このチュートリアルは、デモを開き、すべてのワークフローを自分で試すことができるように設計されています。  実際にフォローすると、後でワークフローを覚える可能性が高くなります。  

1.  `Control`[\ (Windows \)] または `Command` [\ (macOS \)] を押したまま、新しいタブで開くための**コンソールログの例**をクリックします。  
    
    [コンソールログの例][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  デモにフォーカスを置いて、 `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押すと、devtools を開くことができます。  既定では、DevTools がデモの右側に表示されます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="デモの右側に DevTools が開きます。" lightbox="../media/console-example-devtools-right-console.msft.png":::
             デモの右側に DevTools が開きます。  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [ウィンドウの下部に DevTools をドッキング][DevToolsCustomizePlacement]します。  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="デモの下部にドッキングされた DevTools" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             デモの下部にドッキングされた DevTools  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > [DevTools を別のウィンドウにドッキング解除][DevToolsCustomizePlacement]します。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="別のウィンドウに表示されるブラウザー" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             別のウィンドウに表示されるブラウザー  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [DevTools を別のウィンドウにドッキング解除][DevToolsCustomizePlacement]します。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="別のウィンドウでアンドックされる DevTools" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             別のウィンドウでアンドックされる DevTools  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## JavaScript から記録されたメッセージを表示する   

本体に表示されるほとんどのメッセージは、ページの JavaScript を作成した web 開発者から提供されます。  このセクションの目標は、コンソールに表示される可能性のあるさまざまなメッセージの種類について説明し、各メッセージの種類を自分の JavaScript から自分でログに記録する方法について説明します。  

1.  デモの [ **ログ情報** ] ボタンをクリックします。  `Hello, Console!` コンソールにログインします。
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="ログ情報をクリックした後の本体" lightbox="../media/console-log-info.msft.png":::
       **ログ情報**をクリックした後の**本体**  
    :::image-end:::  
    
1.  コンソールのメッセージの横にある `Hello, Console!` [ **log.js: 2**] をクリックします。  [ソース] パネルが開き、メッセージがコンソールに記録される原因となったコード行が強調表示されます。  ページの JavaScript の実行時にメッセージが記録されました `console.log('Hello, Console!')` 。
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="[log.js] をクリックすると、[ソース] パネルが開きます。2" lightbox="../media/console-sources-logjs.msft.png":::
       [DevTools] をクリックすると、[ **ソース** ] パネルが開きます。 `log.js:2`  
    :::image-end:::  
    
1.  次のいずれかのワークフローを使用して、 **コンソール** に移動します。  
    
    *   [ **コンソール** ] タブをクリックします。  
    *   `Control` + `[` `Command` + `[` コンソールパネルがフォーカスされるまで、\ (Windows \) または \ (macOS \) キーを押します。  
    *   [コマンドメニューを開き][DevToolsCommandMenu]、入力を開始して `Console` 、[ **コンソールパネルを表示** ] コマンドを選択し、を押し `Enter` ます。  
    
1.  デモの [ **ログの警告** ] をクリックします。  `Abandon Hope All Ye Who Enter` コンソールにログインします。  次のように書式設定されたメッセージは警告です。  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="[ログ警告] をクリックした後の本体" lightbox="../media/console-log-warning.msft.png":::
       [**ログ警告**] をクリックした後の**本体**  
    :::image-end:::  
    
    > [!TIP]
    > メッセージが特定の方法でログに記録される原因となったコードを表示する場合は、スクリプト (\ など) をクリックして、 `log.js:12` メッセージの書式設定を引き起こしたコードを表示します。  

1.  **Expand** ![ の前にある展開 \ (展開 ][ImageExpandIcon] \) アイコンをクリックし `Abandon Hope All Ye Who Enter` ます。  DevTools は、呼び出しにつながる [スタックトレース][WikiStackTrace] を示します。  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="スタックトレース" lightbox="../media/console-log-warning-expanded.msft.png":::
       スタックトレース  
    :::image-end:::  
    
    スタックトレースでは、という名前の関数が呼び出されたことが通知され `logWarning` ます。これは、という名前の関数が呼び出され `quoteDante` ます。  つまり、最初に発生した通話はスタックトレースの一番下にあります。  スタックトレースの記録は、いつでも呼び出すことができ `console.trace()` ます。  

1.  [ **ログエラー**] をクリックします。  次のエラーメッセージが記録されます。 `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="エラーメッセージ" lightbox="../media/console-log-error.msft.png":::
       エラーメッセージ  
    :::image-end:::  
    
1.  [ **Log Table**] をクリックします。  有名なアーティストについての表が本体に記録されます。  
    
    > [!NOTE]
    > `birthday`列は1つの行にのみ設定されます。  コードを確認して、その理由を確認します。
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="コンソールの表" lightbox="../media/console-log-table.msft.png":::
       **コンソール**の表  
    :::image-end:::  
    
1.  [ **Log Group**] をクリックします。  4つの有名、犯罪 turtles の名前はラベルの下にグループ化されてい `Adolescent Irradiated Espionage Tortoises` ます。  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="コンソールのメッセージのグループ" lightbox="../media/console-log-group.msft.png":::
       **コンソール**のメッセージのグループ  
    :::image-end:::  
    
1.  [ **Custom Custom**] をクリックします。  赤い境界線の付いたメッセージと青色の背景が本体に記録されます。  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="コンソールでのカスタム書式設定を含むメッセージ" lightbox="../media/console-log-custom.msft.png":::
       **コンソール**でのカスタム書式設定を含むメッセージ  
    :::image-end:::  
    
ここでの主なアイデアは、JavaScript からコンソールにメッセージを記録するときに、メソッドの1つを使うことです `console` 。  各メソッドは、異なる形式のメッセージを表示します。  

このセクションで説明されている方法よりも、さらに多くの方法があります。  このチュートリアルでは、残りのメソッドについて説明します。  

## ブラウザーでログに記録されたメッセージを表示する   

ブラウザーでも、コンソールにメッセージが記録されます。  これは通常、ページに問題がある場合に発生します。  

1.  [ **原因 404**] をクリックします。  `404`ページの JavaScript が存在しないファイルを取得しようとしたため、ブラウザーは、HTTP 状態コード (ネットワークエラー) をログに記録します。  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="本体の404エラー" lightbox="../media/console-cause-404.msft.png":::
       `404`**本体**のエラー  
    :::image-end:::  
    
1.  [ **原因エラー**] をクリックします。  `TypeError`JavaScript が存在しない DOM ノードを更新しようとしているため、ブラウザーは不明なログを記録します。  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="本体の TypeError" lightbox="../media/console-cause-error.msft.png":::
       `TypeError`**コンソール**の A  
    :::image-end:::  
    
1.  [ **ログレベル** ] ドロップダウンをクリックし、[ **詳細** ] オプションが無効になっている場合はそれを有効にします。  フィルター処理の詳細については、次のセクションを参照してください。  次のメッセージが表示されるようにするには、これを行う必要があります。  
    
    > [!NOTE]
    > [既定のレベル] ドロップダウンが無効になっている場合は、 **コンソール** サイドバーを閉じる必要がある場合があります。  **コンソール**サイドバーの詳細については、以下の「メッセージソースでフィルター処理する」を参照してください。
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="詳細ログレベルを有効にする" lightbox="../media/console-cause-error-log-levels.msft.png":::
       詳細ログレベルを有効にする  
    :::image-end:::  
    
1.  [ **原因違反**] をクリックします。  ページが数秒間応答しなくなった後、ブラウザーで本体にメッセージが記録され `[Violation] 'click' handler took 3000ms` ます。  正確な期間は異なる場合があります。  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="本体の違反" lightbox="../media/console-cause-violation.msft.png":::
       **本体**の違反  
    :::image-end:::  
    
## メッセージをフィルター処理する   

一部のページでは、コンソールにメッセージがあふれて表示されます。  DevTools には、現在のタスクに関連しないメッセージをフィルター処理するさまざまな方法が用意されています。  

### ログレベルでフィルター処理する   

各 `console` メソッドには、、、、 `Verbose` `Info` `Warning` またはなどの重大度レベルが割り当てられます `Error` 。  たとえば、はレベルのメッセージです。のように、 `console.log()` `Info` レベルのメッセージです `console.error()` `Error` 。  

1.  [ **ログレベル** ] ドロップダウンをクリックして **エラー**を無効にします。  横にチェックマークが表示されなくなった場合、レベルは無効になります。  レベルのメッセージが表示さ `Error` れなくなります。  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="コンソールでエラーレベルのメッセージを無効にする" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       **コンソール**でエラーレベルのメッセージを無効にする  
    :::image-end:::  
    
1.  [ **ログレベル** ] ドロップダウンをもう一度クリックし、 **エラー**を再度有効にします。  レベルのメッセージが再び表示さ `Error` れます。  

### テキストでフィルター処理する   

正確な文字列を含むメッセージのみを表示する場合は、その文字列を [ **フィルター** ] テキストボックスに入力します。  

1.  `Dave`[**フィルター** ] テキストボックスに入力します。  文字列を含まないすべてのメッセージ `Dave` は非表示になります。  また、ラベルが表示される場合もあり `Adolescent Irradiated Espionage Tortoises` ます。  これはバグです。  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="Dave が含まれていないメッセージをフィルターで除外する" lightbox="../media/console-all-messages-text-filter.msft.png":::
       含まれていないメッセージをフィルターで除外する `Dave`  
    :::image-end:::  
    
1.  `Dave`[**フィルター** ] テキストボックスから削除します。  すべてのメッセージが再び表示されます。  

### 正規表現によるフィルター   

特定の文字列ではなく、テキストのパターンを含むすべてのメッセージを表示する場合は、 [正規表現][MDNRegularExpressions]を使用します。  

1.  `/^[AH]/`[**フィルター** ] テキストボックスに入力します。  このパターンを [RegExr][|::ref1::|Main] に入力して、実行内容の説明を入力します。  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="パターンに一致しないメッセージをフィルターで除外する" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       パターンに一致しないメッセージをフィルターで除外する `/^[AH]/`  
    :::image-end:::  
    
1.  `/^[AH]/`[**フィルター** ] テキストボックスから削除します。  すべてのメッセージが再び表示されます。  

### メッセージソース別にフィルターを適用する   

特定の URL のメッセージのみを表示するには、 **サイドバー**を使用します。  

1.  [ **コンソールサイドバーの表示** ] をクリックします ([ ![ コンソールサイドバーを表示] をクリック ][ImageShowConsoleSidebarIcon] します)。  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="サイドバー" lightbox="../media/console-sidebar-all-messages.msft.png":::
       サイドバー  
    :::image-end:::  
    
1.  メッセージ数の隣にある **展開** \ ( ![ 展開 ][ImageExpandIcon] \) アイコンをクリックします。  次の図は、メッセージの数が **13 のメッセージ**であることを示しています。  **サイドバー**には、メッセージが記録される原因となった url の一覧が表示されます。  たとえば、11個のメッセージが発生しました `log.js` 。  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="サイドバーでのメッセージのソースの表示" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       サイドバーでのメッセージのソースの表示  
    :::image-end:::  
    
### ユーザーメッセージでフィルターを適用する   

以前は、[ **ログ情報**] をクリックしたときに、 `console.log('Hello, Console!')` メッセージをコンソールにログするためのスクリプトが呼び出されます。  このような JavaScript から記録されるメッセージは、「 **ユーザメッセージ**」と呼ばれます。  これに対して、[ **原因 404**] をクリックすると、 `Error` 要求されたリソースが見つからなかったことを示すレベルのメッセージがブラウザーでログに記録されます。  そのようなメッセージは、 **ブラウザーメッセージ**とみなされます。  **サイドバー**を使用して、ブラウザーメッセージをフィルター処理し、ユーザーメッセージのみを表示します。  

1.  [ **9 ユーザーメッセージ**] をクリックします。  ブラウザーのメッセージが非表示になります。  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="ブラウザーメッセージのフィルター処理" lightbox="../media/console-sidebar-user-messages.msft.png":::
       ブラウザーメッセージのフィルター処理  
    :::image-end:::  
    
1.  [ **13** 個のメッセージ] をクリックすると、再びすべてのメッセージが表示されます。  

## 他のパネルと共に本体を使用する   

スタイルを編集していても、コンソールログの何かをすばやく確認する必要がある場合はどうすればよいですか。 引き出しを使用します。  

1.  [ **要素** ] タブをクリックします。  
1.  キーを押し `Escape` ます。  **ドロワー**の [コンソール] タブが開きます。  このチュートリアルで使用しているコンソールパネルのすべての機能が含まれています。  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="ドローワの [コンソール] タブ" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         **ドローワ**の [**コンソール**] タブ  
    :::image-end:::  
    
<!--## Next steps  -->

<!--
*   See [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   See [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   See [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

<!--
 


-->  

<!-- image links -->  

[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge \ (Chromium \) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更する |Microsoft ドキュメント"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft ドキュメント"  
[DevToolsConsoleReference]: ./reference.md "コンソールリファレンス |Microsoft ドキュメント"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "メッセージの記録を開始する |故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正規表現 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "スタックトレース-Wikipedia"  


> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/log) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
