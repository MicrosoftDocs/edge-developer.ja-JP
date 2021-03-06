---
description: コンソールにメッセージを記録する方法について説明します。
title: コンソールでのメッセージのログ記録の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e2ea1a8327dd2a591e067b69198c4509b2abcb2d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399170"
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

# <a name="get-started-with-logging-messages-in-the-console"></a>コンソールでのメッセージのログ記録の開始  

この対話型チュートリアルでは、Microsoft Edge DevTools コンソールでメッセージをログに記録して [フィルター処理する方法を示][MicrosoftEdgeDevTools] します。  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="コンソール内のメッセージ" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   コンソール内の **メッセージ**  
:::image-end:::  

このチュートリアルは、順番に完了することを意図しています。  JavaScript を使用してページに対話機能を追加する方法など、Web 開発の基本を理解している必要があります。  

## <a name="set-up-the-demo-and-devtools"></a>デモと DevTools のセットアップ  

このチュートリアルは、デモを開き、すべてのワークフローを自分で試しに行くことができる設計です。  物理的にフォローすると、後でワークフローを覚えておく可能性が高い。  

1.  `Control`\(Windows,Linux\) または \(macOS\) を保持し、[コンソール ログの例] を選択して新しい `Command` タブを開きます。 ****  
    
    [コンソール ログの例][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  デモをフォーカスし `Control` + `Shift` + `J` 、[\(Windows, Linux\) ] または `Command` + `Option` + `J` [\(macOS\) を選択して DevTools を開きます。  既定では、デモの右側に DevTools が開きます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="デモの右側に DevTools が開きます" lightbox="../media/console-example-devtools-right-console.msft.png":::
             デモの右側に DevTools が開きます  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [ウィンドウの下部に DevTools をドッキングします][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="デモの下部にドッキングされた DevTools" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             デモの下部にドッキングされた DevTools  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > [DevTools を別のウィンドウにドッキング解除します][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="別のウィンドウのブラウザー" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             別のウィンドウのブラウザー  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [DevTools を別のウィンドウにドッキング解除します][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="DevTools が別のウィンドウでドッキングされていない" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             DevTools が別のウィンドウでドッキングされていない  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="view-messages-logged-from-javascript"></a>JavaScript からログに記録されたメッセージを表示する  

コンソールに表示されるほとんどの **メッセージは、** ページの JavaScript を作成した Web 開発者から送信されます。  このセクションの目的は、コンソールで確認する可能性が高いさまざまなメッセージの種類を紹介し、各**** メッセージの種類を自分の JavaScript から自分でログに記録する方法を説明します。  

1.  デモで **[ログ情報** ] ボタンを選択します。  `Hello, Console!` コンソールにログに記録されます。
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="[ログ情報] を選択した後のコンソール" lightbox="../media/console-log-info.msft.png":::
       [ **ログ情報** ] を選択した **後のコンソール**  
    :::image-end:::  
    
1.  コンソールのメッセージ `Hello, Console!` の横にある ** [log.js:2] を選択します**。  [ソース] パネルが開き、メッセージがコンソールにログに記録される原因となるコード行が強調表示されます。  ページの JavaScript が実行されたときにメッセージがログに記録されます `console.log('Hello, Console!')` 。
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="DevTools は、[ソース] を選択した後に [ソース] ツールlog.js開きます。2" lightbox="../media/console-sources-logjs.msft.png":::
       DevTools は、選択 **した後に** [ソース] ツールを開きます。 `log.js:2`  
    :::image-end:::  
    
1.  次のワークフローを **使用** してコンソールに戻します。  
    
    *   [コンソール] **ツールを選択** します。  
    *   コンソール `Control` + `[` ツールがフォーカスされるまで 、[\(Windows,Linux\) または `Command` + `[` **** \(macOS\) を選択します。  
    *   [[コマンド] メニューを開][DevToolsCommandMenu]き、[ `Console` コンソール パネルの表示] コマンドを **選択** し、[] を選択します `Enter` 。  
    
1.  デモで **[ログの警告** ] ボタンを選択します。  `Abandon Hope All Ye Who Enter` コンソールにログに記録 **されます**。  このような形式のメッセージは警告です。  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="[ログ警告] を選択した後のコンソール" lightbox="../media/console-log-warning.msft.png":::
       [ **ログ警告** ] を選択した **後のコンソール**  
    :::image-end:::  
    
    > [!TIP]
    > メッセージが特定の方法でログに記録される原因となったコードを表示する場合は、スクリプト \(\など) を選択して、メッセージが書式設定される原因となったコードを表示します。 `log.js:12`  

1.  の前 **にある** [\( ![ ][ImageExpandIcon] Expand \) ] アイコンを選択します `Abandon Hope All Ye Who Enter` 。  DevTools は、呼 [び出しに至る][WikiStackTrace] スタック トレースを表示します。  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="スタック トレース" lightbox="../media/console-log-warning-expanded.msft.png":::
       スタック トレース  
    :::image-end:::  
    
    スタック トレースでは、という名前の関数が実行され、次に `logWarning` という名前の関数が実行されます `quoteDante` 。  つまり、最初に発生した要求は、スタック トレースの下部に表示されます。  実行中にスタック トレースをいつでもログに記録できます `console.trace()` 。  

1.  [ログ **エラー] を選択します**。  次のエラー メッセージがログに記録されます。 `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="エラー メッセージ" lightbox="../media/console-log-error.msft.png":::
       エラー メッセージ  
    :::image-end:::  
    
1.  [ログ **テーブル] を選択します**。  有名なアーティストに関するテーブルがコンソールに記録 **されます**。  
    
    > [!NOTE]
    > 列 `birthday` には、1 行のデータしか入力されません。  コードを確認して、その理由を確認します。
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="コンソール内のテーブル" lightbox="../media/console-log-table.msft.png":::
       コンソール内の **テーブル**  
    :::image-end:::  
    
1.  [ログ **グループ] を選択します**。  4 つの有名な犯罪と戦うカメの名前は、ラベルの下にグループ化 `Adolescent Irradiated Espionage Tortoises` されています。  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="コンソール内のメッセージのグループ" lightbox="../media/console-log-group.msft.png":::
       コンソール内のメッセージの **グループ**  
    :::image-end:::  
    
1.  [Log **Custom] を選択します**。  赤い枠線と青い背景を持つメッセージがコンソールに記録されます。  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="コンソールのカスタム書式を含むメッセージ" lightbox="../media/console-log-custom.msft.png":::
       コンソールのカスタム書式を含む **メッセージ**  
    :::image-end:::  
    
ここでの主な考え方は、JavaScript からコンソールにメッセージをログに記録する場合は、メソッドの 1 つを `console` 使用する方法です。  各メソッドは、メッセージの形式を異なります。  

このセクションで説明した方法よりもさらに多くのメソッドがあります。  このチュートリアルでは、残りのメソッドを確認する方法を示します。  

## <a name="view-messages-logged-by-the-browser"></a>ブラウザーによってログに記録されたメッセージを表示する  

ブラウザーはメッセージもコンソールにログに記録します。  これは通常、ページに問題がある場合に発生します。  

1.  [ **原因 404] を選択します**。  ページの JavaScript が存在しないファイルをフェッチしようとしたため、ブラウザーはネットワーク エラーの HTTP 状態コード `404` をログに記録します。  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="コンソールの 404 エラー" lightbox="../media/console-cause-404.msft.png":::
       コンソール `404` の **エラー**  
    :::image-end:::  
    
1.  [エラー **の原因] を選択します**。  JavaScript が存在しない DOM ノードを更新しようとしているため、ブラウザーは未キャッチ `TypeError` のログを記録します。  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="コンソールの TypeError" lightbox="../media/console-cause-error.msft.png":::
       コンソール `TypeError` の **A**  
    :::image-end:::  
    
1.  [ログ レベル **] ドロップダウンを** 選択し、無効 **になっている場合は [詳細** ] オプションを有効にします。  フィルター処理の詳細については、次のセクションで説明します。  これを行って、ログに記録する次のメッセージが表示されるのを確認する必要があります。  
    
    > [!NOTE]
    > [既定のレベル] ドロップダウンが無効になっている場合は、コンソール サイドバーを閉じる **必要があります** 。  コンソール サイドバーの詳細については、以下のメッセージ ソースで **フィルター処理** します。
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="詳細ログ レベルの有効化" lightbox="../media/console-cause-error-log-levels.msft.png":::
       詳細ログ レベルの有効化  
    :::image-end:::  
    
1.  [原因 **違反] を選択します**。  ページが数秒応答しなくなると、ブラウザーはメッセージをコンソール `[Violation] 'click' handler took 3000ms` に記録します。  正確な期間は異なる場合があります。  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="コンソールでの違反" lightbox="../media/console-cause-violation.msft.png":::
       コンソールでの **違反**  
    :::image-end:::  
    
## <a name="filter-messages"></a>フィルター メッセージ  

一部の Web ページでは、コンソールに **メッセージ** が殺到します。  DevTools には、タスクに関連しないメッセージをフィルター処理するさまざまな方法があります。  

### <a name="filter-by-log-level"></a>ログ レベルでフィルター処理する  

各 `console` メソッドには、重大度レベル 、または `Verbose` `Info` `Warning` が割り当てられます `Error` 。  たとえば `console.log()` 、-level `Info` メッセージですが、-level `console.error()` `Error` メッセージです。  

1.  [ログ レベル **] ドロップダウンを選択** し、[エラー] を **無効にします**。  レベルの横にチェックマークが表示されなくなった場合、レベルは無効になります。  `Error`-level メッセージは消えます。  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="コンソールでエラー レベルのメッセージを無効にする" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       コンソールでエラー レベルのメッセージを無効 **にする**  
    :::image-end:::  
    
1.  [ログ レベル **] ドロップダウンを再度** 選択し、[エラー] を再度 **有効にしてください**。  -level `Error` メッセージが再表示されます。  

### <a name="filter-by-text"></a>テキストによるフィルター  

正確な文字列を含むメッセージのみを表示する場合は、その文字列を [フィルター] テキスト ボックス **に** 入力します。  

1.  `Dave` を **フィルター処理** テキスト ボックスに入力します。  文字列を含めないメッセージはすべて `Dave` 非表示になります。  また、ラベルを確認 `Adolescent Irradiated Espionage Tortoises` できます。  これはバグです。  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="Dave を含むメッセージをフィルター処理する" lightbox="../media/console-all-messages-text-filter.msft.png":::
       含めないメッセージをフィルター処理する `Dave`  
    :::image-end:::  
    
1.  [フィルター `Dave` ] テキスト **ボックスから** 削除します。  すべてのメッセージが再表示されます。  

### <a name="filter-by-regular-expression"></a>正規表現によるフィルター  

特定の文字列ではなく、テキストのパターンを含むすべてのメッセージを表示する場合は、正規表現を [使用します][MDNRegularExpressions]。  

1.  `/^[AH]/` を **フィルター処理** テキスト ボックスに入力します。  パターンを [RegExr に入力][|::ref1::|Main] して、実行内容を説明します。  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="パターンに一致しないメッセージをフィルター処理する" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       パターンに一致しないメッセージをフィルター処理する `/^[AH]/`  
    :::image-end:::  
    
1.  [フィルター `/^[AH]/` ] テキスト **ボックスから** 削除します。  すべてのメッセージが再び表示されます。  

### <a name="filter-by-message-source"></a>メッセージ ソースによるフィルター  

特定の URL からのメッセージのみを表示する場合は、サイドバー を使用 **します**。  

1.  [ **コンソールサイドバーを表示する** ]を選択します ![ 。[コンソールサイドバーを表示 ][ImageShowConsoleSidebarIcon] する]を選択します。  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="サイドバー" lightbox="../media/console-sidebar-all-messages.msft.png":::
       サイドバー  
    :::image-end:::  
    
1.  メッセージ数 **の** 横にある ![ ][ImageExpandIcon] [\( Expand \) ] アイコンを選択します。  次の図では、メッセージの数は **13 メッセージとして示されています**。  サイドバー **には** 、メッセージがログに記録される原因となる URL の一覧が表示されます。  たとえば `log.js` 、11 件のメッセージが発生しました。  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="サイドバーでメッセージのソースを表示する" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       サイドバーでメッセージのソースを表示する  
    :::image-end:::  
    
### <a name="filter-by-user-messages"></a>ユーザー メッセージでフィルター処理する  

以前は、[ログ情報] **を選択**すると、コンソールにメッセージをログに記録するためにという `console.log('Hello, Console!')` 名前のスクリプトが表示されます。  このような JavaScript からログに記録されたメッセージは、ユーザー メッセージという **名前です**。  これに対し、[原因 **404]** を選択すると、要求されたリソースが見つからないことを示す -level メッセージが `Error` ブラウザーに記録されます。  そのメッセージはブラウザー メッセージ **と見なされます**。  サイドバーを **使用してブラウザー** メッセージをフィルター処理し、ユーザー メッセージのみを表示します。  

1.  **[9 ユーザー メッセージ] を選択します**。  ブラウザー メッセージは非表示です。  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="ブラウザー メッセージのフィルター処理" lightbox="../media/console-sidebar-user-messages.msft.png":::
       ブラウザー メッセージのフィルター処理  
    :::image-end:::  
    
1.  **[13 メッセージ] を選択**して、すべてのメッセージを再び表示します。  

## <a name="use-the-console-alongside-any-other-tools"></a>他のツールと一緒にコンソールを使用する  

スタイルを編集しているが、コンソール ログで何かをすぐに確認する必要がある場合は、[引き出しを使用] を使用します。  

1.  [要素] **ツールを選択** します。  
1.  `Escape` を選択します。  ドロ **ワーの** コンソール ツール **が開** きます。  このチュートリアルで使用しているコンソール パネルのすべての機能があります。  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="ドロワーのコンソール ツール" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         ドロ **ワー** のコンソール **ツール**  
    :::image-end:::  
    
## <a name="see-also"></a>関連項目  

*   コンソール **UI** に関連するその他の機能とワークフローを確認するには、[コンソール リファレンス] [に移動します][DevToolsConsoleApi]。  
*   「JavaScript からログに記録されたメッセージを表示する」で説明されているメソッドの詳細と、この記事で説明していない他のメソッドについては、「 `console` コンソール API リファレンス」[](#view-messages-logged-from-javascript) `console` [に移動します][DevToolsConsoleReference]。  
<!--*   Navigate to [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  
     
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \(Chromium\) 開発者向け|Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md "[Microsoft Edge DevTools コマンド] メニューメニューを使用してコマンドを実行|Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更 | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md "コンソール参照|Microsoft Docs"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "メッセージのログ記録の開始|Glitch"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正規表現|MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "スタック トレース - Wikipedia"  
> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/log) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
