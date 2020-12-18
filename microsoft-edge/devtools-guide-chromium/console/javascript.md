---
description: コンソールで JavaScript を実行する方法について説明します。
title: コンソールでの JavaScript の実行を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ecd1a2fffb311990b6e743e99d038f1f2a519ee4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231091"
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

# コンソールでの JavaScript の実行を開始する  

この対話型のチュートリアルでは、Microsoft Edge DevTools コンソールで JavaScript を実行する方法を示 **します**。  コンソールにメッセージを記録する方法の詳細については****、「メッセージのログ記録の概要[」に移動します][DevToolsConsoleLoggingMessages]。  JavaScript コードを一時停止し、一度に 1 行ステップ実行する方法の詳細については [、「JavaScript][DevToolsJavascriptIndex]のデバッグの概要」に移動してください。  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="コンソール" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   **コンソール**  
:::image-end:::  

## 概要  

本体 **は** [REPL であり][WikiReadEvalPrintLoop]、読み取り、評価、印刷、ループを表します。  入力した JavaScript を読み取り、コードを評価し、式の結果を出力してから[][2alityExpressionsVersusStatements]、最初の手順に戻ります。  

## DevTools のセットアップ  

このチュートリアルは、デモを開いて、すべてのワークフローを自分で試用するように設計されています。  物理的に作業を行う場合は、後でワークフローを思い出す可能性が高い。

1.  `Control` + `Shift` + `J` \(Windows, Linux\) または `Command` + `Option` + `J` \(macOS\) を選択してコンソールを開**きます**。  
1.  `Control`\(Windows, Linux\) または `Command` \(macOS\) を保持し、[**コンソール Javascript の例**] を選択して新しいウィンドウで開きます。  
    
    *   [コンソール Javascript の例][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="左側のコンソール JavaScript の例ページと右側の DevTools" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       左側のコンソール JavaScript の例ページと右側の DevTools  
    :::image-end:::  
    
## ページの JavaScript または DOM を表示および変更する  

ページを作成またはデバッグする場合、ページの外観や実行方法を変更するために、**** コンソールでステートメントを実行すると便利な場合があります。  
    
1.  ボタン内のテキストに注意してください。  
1.  コンソール `document.getElementById('hello').textContent = 'Hello, Console!'` に入力 **し** 、式を評価 `Enter` するために選択します。  ボタン内のテキストがどのように変化するのか確認してください。  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="式を評価した後のコンソールの外観" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       式を **評価** した後のコンソールの外観  
    :::image-end:::  
    
    評価したコードの下に表示されます `"Hello, Console!"` 。  REPL の 4 つの手順 (読み取り、評価、印刷、ループ) を思い出してください。  コードを評価した後、REPL は式の結果を出力します。  そのため `"Hello, Console!"` 、評価の結果である必要があります `document.getElementById('hello').textContent = 'Hello, Console!'` 。  
    
## ページに関連しない任意の JavaScript を実行する  

場合によっては、コードをテストしたり、使い慣れた新しい JavaScript 機能を試したりできるコードのプレイグラウンドが必要な場合があります。  コンソール **は** 、これらの種類の実験に最適な場所です。  

1.  コンソール `5 + 15` に入力し、式を `Enter` 評価するために選択します。 コンソールは、コードの下の式の結果を出力します。  次の図では、式 **を評価** した後、コンソールに結果が表示されます。  

1.  コンソールに次のコードを **入力します**。  コピーして貼り付けするのではなく、文字で入力してみてください。  
    
    ```javascript
    function add(a, b=20)
    ```  
    
    構文に詳しい場合は、関数の引数の既定値を定義 `b=20` [します][Esma6DefaultParameterValues]。  
    
1.  次に、定義した関数を実行します。  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="コード スニペット内の式を評価した後にコンソールが表示される" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             コード **スニペット** 内の式を評価した後にコンソールが表示される  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` 2 番目の引数を指定せずに関数を呼び出した場合、既定値は `45` `add` `b` `20` .  

## 次のステップ  

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

DevTools では、実行中にスクリプトを一時停止できます。  一時停止している間は、コンソールを使用して****、その時点のページまたはページを表示および `window` `DOM` 変更できます。  ワークフローは、強力なデバッグ ワークフローを作成します。  対話型のチュートリアルでは [、JavaScript のデバッグの開始に移動します][DevToolsJavascriptIndex]。  

コンソール **には** 、ページの操作を容易にする便利な機能のセットもあります。  次に、例を示します。  

*   要素を選択するために入力 `document.querySelector()` するのではなく、次のように入力します `$()` 。  この構文は jQuery の影響を受けますが、実際には jQuery ではありません。  これは単なるエイリアスです `document.querySelector()` 。  
*   `debug(function)` 関数の最初の行にブレークポイントを効果的に設定します。  
*   `keys(object)` は、指定したオブジェクトのキーを含む配列を返します。  

便利な関数の詳細については、「コンソール ユーティリティ API リファレンス [」に移動してください][DevToolsConsoleUtilities]。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "コンソールでメッセージのログ記録を開始する |Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "コンソール リファレンス |Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevToolsJavascriptIndex]: ../javascript/index.md "Microsoft Edge DevTools での JavaScript のデバッグを開始する |Microsoft Docs"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript での式とステートメント"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "既定のパラメーター値 - 拡張パラメーター処理 - ECMAScript 6 — 新機能: 概要と&比較"  

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
