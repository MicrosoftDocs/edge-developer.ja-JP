---
description: 開発者ツール内のコンソール ツールMicrosoft Edge紹介します。
title: コンソールの使用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3f2f8c01a9bc9c4f40158f0959ba5b60e03bfb80
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483219"
---
# <a name="use-the-console"></a>コンソールの使用  

**DevTools**のコンソール ツールは、いくつかのタスクを実行するのに役立ちます。  次の一覧には、いくつかのタスクが含まれています。  

*   現在のプロジェクトで何かが機能しない理由を確認し、 [問題を追跡します][DevtoolsConsoleConsoleDebugJavascript]。  
*   [ブラウザーの Web プロジェクトに関する][DevtoolsConsoleConsoleFilters] 情報をログ メッセージとして取得します。  
*   [デバッグの][DevtoolsConsoleConsoleLog] 目的でスクリプトに情報をログインします。  
*   [REPL 環境で JavaScript][DevtoolsConsoleConsoleJavascript] 式を [使用してみてください][WikiReadEvalPrintLoop] 。  
*   [JavaScript を使用してブラウザーで Web][DevtoolsConsoleConsoleDomInteraction] プロジェクトを操作します。  
    
コンソール **は、** 他のツールと一緒に使うのに最適なコンパニオン ツールです。  コンソール **は、JavaScript** を使用して現在の Web ページの機能のスクリプト作成、検査、操作を行う強力な方法を提供します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-intro-console-main.msft.png" alt-text="上部パネルでコンソール ツールを開く" lightbox="../media/console-intro-console-main.msft.png":::
         上部 **パネル** でコンソール ツールを開く  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-intro-console-panel.msft.png" alt-text="下部パネルのコンソールで、[要素] ツールを開きます。" lightbox="../media/console-intro-console-panel.msft.png":::
         **下部** パネルのコンソールで、[要素] **ツールを開** きます。  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

コンソールを直接開く最も速**い方法**は `Control` + `Shift` + `J` 、\(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択する方法です。  

## <a name="error-reports-and-console"></a>エラー レポートとコンソール  

**コンソール** は、JavaScript と接続エラーが報告される既定の場所です。  エラーが発生した場合は、DevTools**** の [設定] アイコンの横にボタンが表示され、エラーと警告の数が表示されます。  コンソールを開き、問題 **を表示するには** 、それを選択します。  詳細については、「コンソールで報告された [デバッグ エラー」に移動します][DevtoolsConsoleConsoleDebugJavascript]。  

:::image type="complex" source="../media/console-debug-displays-error.msft.png" alt-text="DevTools は、コンソールでエラーに関する詳細情報を提供します。" lightbox="../media/console-debug-displays-error.msft.png":::
   DevTools は、コンソールでエラーに関する詳細情報を提供 **します。**  
:::image-end:::  

## <a name="inspect-and-filter-information-on-the-current-webpage"></a>現在の Web ページの情報を検査してフィルター処理する  

Web ページで DevTools を開いた場合、コンソールにログに記録された情報が表示される可能性 **があります**。  重要な情報を特定する必要がある場合、情報の量が問題になります。  アクションが必要な重要な情報を表示するには、DevTools [の Issues][DevtoolsIssuesIndex] ツールを使用します。  ノイズの多くが残っているので、コンソールの自動ログとフィルターのオプションについて知[][DevtoolsConsoleConsoleFilters]ってよい考え**です**。  

:::image type="complex" source="../media/console-intro-noise.msft.png" alt-text="メッセージの完全なコンソールを持つ DevTools" lightbox="../media/console-intro-noise.msft.png":::
   メッセージの完全な **コンソールを持つ** DevTools  
:::image-end:::  

## <a name="log-information-to-display-in-the-console"></a>コンソールに表示するログ情報  

コンソールの最も一般的な **使用例は** 、メソッドまたは他の同様の方法を使用してスクリプトから情報 `console.log()` をログに記録します。  これを試す場合は、次のアクションを実行します。  

1.  コンソールを**開く**場合は `Control` + `Shift` + `J` 、\(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  
1.  [コンソール メッセージ [の例: ログ、情報][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml]、エラー、警告] に移動するか、コンソールで次のコード スニペットをコピーして実行 **します**。  
    
    ```javascript
    console.log('This is a log message');
    console.info('This is some information'); 
    console.error('This is an error');
    console.warn('This is a warning');
    console.log(document.body.getBoundingClientRect());
    console.table(document.body.getBoundingClientRect());
    let technologies = ["HTML", "CSS", "SVG", "ECMAScript"];
    console.groupCollapsed('Technolgies');
    technologies.forEach(tech => {console.info(tech);})
    console.groupEnd('Technolgies');
    ```  
    
1.  コンソール **に結果** が表示されます。  
    
    :::image type="complex" source="../media/console-intro-logging.msft.png" alt-text="デモ コードによって引き起こされたメッセージの完全なコンソール" lightbox="../media/console-intro-logging.msft.png":::
       **デモ** コードによって引き起こされたメッセージの完全なコンソール  
    :::image-end:::  
    
コンソールを使用する場合は、多くの便利な方法を使用 **できます**。  詳細については、「コンソール ツールでメッセージ [をログに記録する」に移動します][DevtoolsConsoleConsoleLog]。  

## <a name="try-your-javascript-live-in-the-console"></a>コンソールで JavaScript をライブで試す  

コンソール **は** 、情報をログに記録する場所ではない。  コンソール **は** [REPL 環境][WikiReadEvalPrintLoop] です。  コンソールに JavaScript を記述 **すると、コード**はすぐに実行されます。  いくつかの新しい JavaScript 機能をテストしたり、簡単な計算を行う場合に役立つ場合があります。  また、オートコンプリート、構文の強調表示、履歴など、最新の編集環境で必要なすべての機能を取得できます。  これを試す場合は、次のアクションを実行します。  

1.  [コンソール] に **移動します**。  
1.  「`2 + 2`」と入力します。  
    
コンソール **は、** 次の行 `4` に結果を表示します。  この **熱心な評価** 機能は、コードで間違いを犯していないとデバッグして確認する場合に役立ちます。  

:::image type="complex" source="../media/console-javascript-eager-evaluation.msft.png" alt-text="コンソールには、入力時に 2 + 2 ライブの結果が表示されます。" lightbox="../media/console-javascript-eager-evaluation.msft.png":::
   コンソール **は、** 入力時に `2 + 2` ライブの結果を表示します。  
:::image-end:::  

コンソールで JavaScript 式を **実行し、** 必要に応じて結果を表示するには、 を選択します `Enter` 。  次に、コンソールで実行する次の JavaScript コードを記述 **できます**。  

:::image type="complex" source="../media/console-javascript-several-expressions.msft.png" alt-text="複数行の JavaScript コードを連続して実行する" lightbox="../media/console-javascript-several-expressions.msft.png":::
   複数行の JavaScript コードを連続して実行する  
:::image-end:::  

既定では、JavaScript コードを 1 行で実行します。  行を実行するには、JavaScript を入力してから、 を選択します `Enter` 。  単一行の制限を回避するには、代わりに `Shift` + `Enter` を選択します `Enter` 。  他のコマンド ライン エクスペリエンスと同様に、以前の JavaScript コマンドにアクセスするには、 を選択します `Arrow-Up` 。  コンソールのオートコンプリート機能 **は、不** 慣れなメソッドについて学ぶのに最適な方法です。  これを試す場合は、次のアクションを実行します。  

1.  コンソールを **開きます**。  
1.  「`doc`」と入力します。  
1.  ドロップダウン `document` メニューから選択します。  
1.  キーを `tab` 選択して選択します。  
1.  「`.bo`」と入力します。  
1.  を `tab` 選択して取得します `document.body` 。  
1.  現在の Web ページの本文で使用できるプロパティとメソッドの完全な一覧を表示するには、別の値 `.` を入力します。  
    
コンソールを操作する方法の詳細については **、「JavaScript**環境として [コンソール」に移動します][DevtoolsConsoleConsoleJavascript]。  

:::image type="complex" source="../media/console-javascript-autocomplete.msft.png" alt-text="JavaScript 式のコンソールオートコンプリート" lightbox="../media/console-javascript-autocomplete.msft.png":::
   JavaScript**式の**コンソールオートコンプリート  
:::image-end:::  

## <a name="interact-with-the-current-webpage-in-the-browser"></a>ブラウザーで現在の Web ページを操作する  

コンソール **は** 、ブラウザーの [Window][MdnDocsWebApiWindow] オブジェクトにアクセスできます。  現在の Web ページを操作するスクリプトを作成できます。  これを試す場合は、次のアクションを実行します。  

1.  コンソールを **開きます**。  
1.  次のコード スニペットをコピーして貼り付けます。  
    
    ```javascript
    document.querySelector('h1').innerHTML
    ```  
    
:::image type="complex" source="../media/console-intro-reading-DOM.msft.png" alt-text="トップ 見出し (h1) コンテンツを DOM からコピーし、コンソールに表示する" lightbox="../media/console-intro-reading-DOM.msft.png":::
   DOM からトップ 見出し \( \) コンテンツをコピーし `h1` 、コンソールに表示 **する**  
:::image-end:::  

Web ページからの読み取りだけでなく、変更することもできます。  これを試す場合は、次のアクションを実行します。  

1.  コンソールを **開きます**。  
1.  次のコード スニペットをコピーして貼り付けます。  
    
    ```javascript
    document.querySelector('h1').innerHTML = 'Rocking the Console';
    ```  
    
:::image type="complex" source="../media/console-intro-wrtiting-DOM.msft.png" alt-text="コンソールで DOM にテキストを書き込む" lightbox="../media/console-intro-wrtiting-DOM.msft.png":::
   コンソールで DOM にテキストを書 **き込む**  
:::image-end:::  

Web ページのメイン見出しを [コンソールの **ロック] に変更しました**。  コンソール **ユーティリティ メソッド** を使用すると、現在の Web ページに簡単にアクセスして操作できます。  詳細については、「コンソール ユーティリティ [API リファレンス」に移動します][DevtoolsConsoleUtilities]。  たとえば、現在の Web ページ内のすべてのリンクの周囲に緑の枠線を追加するには、次の操作を実行します。  

1.  コンソールを **開きます**。  
1.  次のコード スニペットをコピーして貼り付けます。  
    
    ```javascript
    $$('a').forEach(a => a.style.border='1px solid lime');
    ```  
    

:::image type="complex" source="../media/console-intro-changing-styles.msft.png" alt-text="コンソールを使用して要素の選択を操作する" lightbox="../media/console-intro-changing-styles.msft.png":::
    コンソールを使用して要素の選択を操作 **する**  
:::image-end:::  

DOM の操作の詳細については、「コンソールを使用して DOM を操作する [」に移動します][DevtoolsConsoleConsoleDomInteraction]。  

## <a name="learn-more-about-console"></a>コンソールの詳細  

コンソールの詳細については、「**コンソール**リファレンス」、「[コンソール ユーティリティ API][DevtoolsConsoleUtilities]リファレンス」、および「コンソール API[リファレンス」に移動します][DevtoolsConsoleApi]。 [][DevtoolsConsoleReference]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleConsoleDebugJavascript]: ./console-debug-javascript.md "コンソール ウィンドウで報告されたデバッグ エラー|Microsoft Docs"  
[DevtoolsConsoleConsoleDomInteraction]: ./console-dom-interaction.md "コンソールを使用して DOM ファイルを操作|Microsoft Docs" 
[DevtoolsConsoleConsoleFilters]: ./console-filters.md "Filter Console メッセージ |Microsoft Docs"  
[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "JavaScript 環境としてのコンソール |Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "コンソール ツール でメッセージをログに記録|Microsoft Docs"  
[DevtoolsConsoleReference]: ./reference.md "コンソール参照|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[DevtoolsIssuesIndex]: ../issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-demo.html "コンソール メッセージの例: ログ、情報、エラー、警告の|GitHub"  

[MdnDocsWebApiWindow]: https://developer.mozilla.org/docs/Web/API/Window "ウィンドウ |MDN"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval-print ループ |Wikipedia"  
