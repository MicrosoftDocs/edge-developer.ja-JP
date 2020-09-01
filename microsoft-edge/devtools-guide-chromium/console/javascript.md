---
title: 本体の JavaScript の実行を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7e91d9844b2926bc8302331c6b9d971922d27ea3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982262"
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







# 本体の JavaScript の実行を開始する   



この対話形式のチュートリアルでは、Microsoft Edge DevTools **コンソール**で JavaScript を実行する方法について説明します。  **コンソール**へのメッセージのログの記録方法の詳細については、「[ログメッセージの使用を開始][DevToolsConsoleLoggingMessages]する」を参照してください。  JavaScript コードを一時停止して一度に1行ずつ手順を実行する方法の詳細については、「 [Javascript のデバッグの概要][DevToolsJavascriptIndex]」を参照してください。  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="本体" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   **本体**  
:::image-end:::  

## 概要   

**本体**は[REPL][WikiReadEvalPrintLoop]であり、読み取り、評価、印刷、ループを意味します。  これは、入力した JavaScript を読み上げてコードを評価し、 [式][2alityExpressionsVersusStatements]の結果を出力した後、最初の手順にループします。  

## DevTools のセットアップ   

このチュートリアルは、デモを開き、すべてのワークフローを自分で試すことができるように設計されています。  実際にフォローすると、後でワークフローを覚える可能性が高くなります。

1.  `Control` + `Shift` + `J` 本体を開くには、\ (Windows \) または `Command` + `Option` + `J` \ ( **Console**macOS \) を押します。  
1.  `Control`[\ (Windows \)] または `Command` [\ (macOS \)] をクリックし、[**コンソール Javascript の例**] をクリックして新しいウィンドウで開きます。  
    
    *   [本体の Javascript の例][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="左側の本体の JavaScript のサンプルページと右側の DevTools" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       左側の本体の JavaScript のサンプルページと右側の DevTools  
    :::image-end:::  
    
## ページの JavaScript または DOM を表示して変更する   

ページの作成またはデバッグ時には、ページの外観や実行方法を変更するために、 **コンソール** でステートメントを実行すると便利なことがあります。  
    
1.  ボタンのテキストに注目してください。  
1.  コンソールに入力し、を `document.getElementById('hello').textContent = 'Hello, Console!'` 押して式を評価し**Console** `Enter` ます。  ボタン内のテキストがどのように変化するかに注目してください。  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="式を評価した後の本体の外観" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       式を評価した後の **本体** の外観  
    :::image-end:::  
    
    評価したコードの下に表示さ `"Hello, Console!"` れます。  REPL: read、evaluate、print、loop の4つの手順を取り消します。  コードを評価した後、REPL は式の結果を出力します。  そのため `"Hello, Console!"` 、評価の結果である必要があり `document.getElementById('hello').textContent = 'Hello, Console!'` ます。  
    
## ページに関連していない任意の JavaScript を実行します。   

場合によっては、コードをテストできる場所でコードプレイグラウンドを使用したり、使い慣れていない新しい JavaScript 機能を試したりすることができます。  このような種類の実験では、コンソールは最適な場所です。  

1.  `5 + 15`本体に入力し、を押して `Enter` 式を評価します。 本体によって、コードの下に式の結果が出力されます。  次の図では、式を評価した後に **コンソール** に結果が表示されます。  

1.  **コンソール**に次のコードを入力します。  テキストをコピーして貼り付けるのではなく、文字で入力してみてください。  
    
    ```javascript
    function add(a, b=20) { return a + b; }
    ```  
    
    構文に慣れていない場合は `b=20` 、「 [関数の引数に既定値を定義][Esma6DefaultParameterValues]する」を参照してください。  
    
1.  次に、定義した関数を実行します。  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="コードスニペットで式を評価した後にコンソールが表示される" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             コードスニペットで式を評価した後に **コンソール** が表示される  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` `45` `add` 2 番目の引数を指定せずに関数を呼び出した場合は、として評価され `b` ます。既定は、 `20` です。  

## 次のステップ   

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

DevTools では、実行中にスクリプトを一時停止できます。  一時停止中は、 **本体** を使ってその時点でのページの表示や変更を行うことができ `window` `DOM` ます。  ワークフローによって、強力なデバッグワークフローが実現されます。  インタラクティブなチュートリアルについては、「 [JavaScript のデバッグを開始][DevToolsJavascriptIndex]する」を参照してください。  

**コンソール**には、ページを操作しやすくするための便利な機能も用意されています。  次に、例を示します。  

*   `document.querySelector()`要素を選択する代わりに、「」と入力 `$()` します。  この構文は jQuery が示していますが、実際は jQuery ではありません。  これは、の別名にすぎ `document.querySelector()` ません。  
*   `debug(function)` 関数の最初の行に、効率的にブレークポイントを設定します。  
*   `keys(object)` 指定されたオブジェクトのキーを含む配列を返します。  

<!--See [Console Utilities API Reference][DevToolsConsoleUtilities] to explore all the convenience functions.  -->  

<!--todo: add console utilities api reference section when available  -->  

 



<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "コンソールでのメッセージの記録を開始する |Microsoft ドキュメント"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "コンソールリファレンス |Microsoft ドキュメント"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevToolsJavascriptIndex]: ../javascript/index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript の式とステートメント"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "既定のパラメーター値-拡張パラメーター処理-ECMAScript 6-新機能: 概要 & 比較"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "本体 Javascript の例 |故障"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "読み取り– eval – print loop-Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/javascript) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
