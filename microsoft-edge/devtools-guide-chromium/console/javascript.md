---
description: コンソールで JavaScript を実行する方法について説明します。
title: コンソールでの JavaScript の実行の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c1d6c393b6278f4622cf80576ccc8f9c70bdb6b5
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398820"
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

# <a name="get-started-with-running-javascript-in-the-console"></a>コンソールでの JavaScript の実行の開始  

この対話型チュートリアルでは、Microsoft Edge DevTools コンソールで JavaScript を実行する方法を示 **します**。  コンソールにメッセージをログに記録する方法の詳細については **、「** ログ メッセージの概要 [」に移動します][DevToolsConsoleLoggingMessages]。  JavaScript コードを一時停止し、一度に 1 行の手順を実行する方法の詳細については、「JavaScript のデバッグを開始する」 [に移動します][DevToolsJavascriptIndex]。  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="コンソール" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   **コンソール**  
:::image-end:::  

## <a name="overview"></a>概要  

コンソール **は** [REPL で、][WikiReadEvalPrintLoop]読み取り、評価、印刷、ループを表します。  入力した JavaScript を読み取り、コードを評価し、式の結果を出力し[][2alityExpressionsVersusStatements]、最初の手順に戻ります。  

## <a name="set-up-devtools"></a>DevTools のセットアップ  

このチュートリアルは、デモを開き、すべてのワークフローを自分で試す目的で設計されています。  物理的にフォローすると、後でワークフローを覚えておく可能性が高い。

1.  `Control` + `Shift` + `J` \(Windows,Linux\) または `Command` + `Option` + `J` \(macOS\) を選択してコンソールを開**きます**。  
1.  `Control`\(Windows,Linux\) または `Command` \(macOS\) を保持し、[**コンソール Javascript の例**] を選択して新しいウィンドウを開きます。  
    
    *   [コンソール Javascript の例][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="左側の [コンソール JavaScript の例] ページと右側の DevTools" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       左側の [コンソール JavaScript の例] ページと右側の DevTools  
    :::image-end:::  
    
## <a name="view-and-change-the-javascript-or-dom-of-the-page"></a>ページの JavaScript または DOM を表示および変更する  

ページを構築またはデバッグする場合、ページの外観や実行方法を変更するために、**** コンソールでステートメントを実行すると便利です。  
    
1.  ボタンのテキストに注意してください。  
1.  コンソール `document.getElementById('hello').textContent = 'Hello, Console!'` に入力 **し、** 式を `Enter` 評価するために選択します。  ボタン内のテキストがどのように変化するのか注意してください。  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="式の評価後のコンソールの外観" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       式の **評価** 後のコンソールの外観  
    :::image-end:::  
    
    `"Hello, Console!"`は、評価したコードの下に表示されます。  REPL の 4 つの手順(読み取り、評価、印刷、ループ)を覚えておいてください。  コードを評価した後、REPL は式の結果を出力します。  したがって `"Hello, Console!"` 、評価の結果である必要があります `document.getElementById('hello').textContent = 'Hello, Console!'` 。  
    
## <a name="run-arbitrary-javascript-that-is-not-related-to-the-page"></a>ページに関連しない任意の JavaScript を実行する  

場合によっては、コードをテストしたり、使い慣れしていない新しい JavaScript 機能を試したりできるコードプレイグラウンドが必要な場合があります。  コンソール **は** 、このような実験に最適な場所です。  

1.  コンソール `5 + 15` に入力し、式 `Enter` を評価するを選択します。 コンソールは、コードの下に式の結果を出力します。  次の図では **、式を** 評価した後、コンソールに結果が表示されます。  

1.  コンソールに次のコードを **入力します**。  コピー貼り付けではなく、文字別に入力してみてください。  
    
    ```javascript
    function add(a, b=20)
    ```  
    
    構文に慣れていない場合は、関数の引数の既定値 `b=20` [を][Esma6DefaultParameterValues]定義します。  
    
1.  次に、定義した関数を実行します。  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="コード スニペット内の式を評価した後にコンソールが表示される" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             コード **スニペット内** の式を評価した後にコンソールが表示される  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` 2 番目の `45` 引数を指定せずに関数を呼び出す場合、既定値は `add` `b` `20` .  

## <a name="next-steps"></a>次の手順  

<!--To explore more features related to running JavaScript in the **Console**, navigate to [Run JavaScript][DevToolsConsoleReference].  -->  

<!--todo: add console reference (run javascript) section when available  -->  

DevTools を使用すると、実行中にスクリプトを一時停止できます。  一時停止中に、コンソールを使用して、**** その時点でページまたはページを表示および `window` `DOM` 変更できます。  ワークフローは強力なデバッグ ワークフローになります。  対話型のチュートリアルでは、[JavaScript のデバッグの開始] [に移動します][DevToolsJavascriptIndex]。  

コンソール **には** 、ページの操作を容易にする一連の便利な機能もあります。  次に、例を示します。  

*   要素を選択するために入力 `document.querySelector()` するのではなく、と入力します `$()` 。  この構文は jQuery にインスパイアされますが、実際には jQuery ではありません。  これは単なるエイリアスです `document.querySelector()` 。  
*   `debug(function)` その関数の最初の行にブレークポイントを効果的に設定します。  
*   `keys(object)` 指定したオブジェクトのキーを含む配列を返します。  

便利な関数の詳細については、「コンソール ユーティリティ [API リファレンス」に移動します][DevToolsConsoleUtilities]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "コンソール ウィンドウでメッセージをログに記録する方法を|Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "コンソール参照|Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevToolsJavascriptIndex]: ../javascript/index.md "Microsoft Edge DevTools の JavaScript のデバッグの|Microsoft Docs"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript の式とステートメント"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "既定のパラメーター値 - 拡張パラメーター処理 - ECMAScript 6 - 新機能: 概要と&比較"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "コンソール Javascript の例 |Glitch"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "Read-eval-print ループ - Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/javascript) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
