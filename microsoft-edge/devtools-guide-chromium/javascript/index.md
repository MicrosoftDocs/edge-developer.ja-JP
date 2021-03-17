---
description: Microsoft Edge DevTools を使用して JavaScript のバグを見つけて修正する方法について説明します。
title: Microsoft Edge DevTools での JavaScript のデバッグの開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bbfb766bcc03e4c4fe0f975f1ecfccbef08084be
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439466"
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
# <a name="get-started-with-debugging-javascript-in-microsoft-edge-devtools"></a>Microsoft Edge DevTools での JavaScript のデバッグの開始  

この記事では、DevTools で JavaScript の問題をデバッグする基本的なワークフローについて説明します。  

## <a name="step-1-reproduce-the-bug"></a>手順 1: バグを再現する  

一貫してバグを再現する一連のアクションを見つけることは、常にデバッグの最初のステップです。  

1.  [ **デモを開く] を選択します**。  `Control`\(Windows,Linux\) または \(macOS\) を保持し、新しいブラウザー タブで `Command` デモを開きます。  
    
    [Open Demo][OpenDebugJSDemo]  
    
1.  [ `5` 数値 **1] テキスト ボックスに** 入力します。  
1.  [ `1` 数値 **2] テキスト ボックスに** 入力します。  
1.  [ **番号 1 の追加] と [番号 2] を選択します**。  ボタンの下のラベルには、 と表示されます `5 + 1 = 51` 。  結果は 、 である必要があります `6` 。  次に、バグである追加エラーを修正します。  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 の結果は 51 になりますが、6 である必要があります" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` の結果 `51` が表示されますが、次の値を使用する必要があります。 `6`  
    :::image-end:::  
    
## <a name="step-2-get-familiar-with-the-sources-tool-ui"></a>手順 2: ソース ツール UI について理解する  

DevTools には、タスクごとにさまざまなツールが提供されています。  さまざまなタスクには、CSS の変更、ページ読み込みパフォーマンスのプロファイリング、ネットワーク要求の監視が含まれます。  ソース **ツールは** 、JavaScript をデバッグする場所です。  

1.  DevTools**でコンソール**ツールを開く場合は `Control` + `Shift` + `J` 、[\(Windows,Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="コンソール ツール" lightbox="../media/javascript-console-empty.msft.png":::
       コンソール**ツール**  
    :::image-end:::  
    
1.  [ソース] **ツールを選択** します。  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="ソース ツール" lightbox="../media/javascript-sources-sections.msft.png":::
       ソース**ツール**  
    :::image-end:::  
    
ソース **ツール UI には** 3 つのパーツがあります。  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="ソース ツール UI の 3 つの部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   ソース ツール UI の 3**つの部分**  
:::image-end:::  

1.  [ **ファイル ナビゲーター]** パネル \(前の図のセクション 1\)。  Web ページが要求するファイルは、ここに一覧表示されます。  
1.  [ **コード エディター]** パネル \(前の図のセクション 2\)。  [ファイル ナビゲーター] ウィンドウで **ファイルを選択** すると、そのファイルの内容がここに表示されます。  
1.  JavaScript **デバッグ パネル** \(前の図のセクション 3\)。  Web ページの JavaScript を検査するためのさまざまなツール。  DevTools ウィンドウが広い場合、このウィンドウはコード エディター ウィンドウの右側 **に表示** されます。  
    
## <a name="step-3-pause-the-code-with-a-breakpoint"></a>手順 3: ブレークポイントでコードを一時停止する  

この種の問題をデバッグする一般的な方法は、コードに複数のステートメントを挿入し、スクリプトの実行時に値 `console.log()` を調べたい方法です。  次に、例を示します。  

```javascript
function updateLabel() {
    var addend1 = getNumber1();
    console.log('addend1:', addend1);
    var addend2 = getNumber2();
    console.log('addend2:', addend2);
    var sum = addend1 + addend2;
    console.log('sum:', sum);
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
}
```  

メソッド `console.log()` によってジョブが完了する可能性がありますが、 **ブレークポイントを使用** すると、実行速度が向上します。  ブレークポイントを使用すると、実行時の途中でコードを一時停止し、その時点ですべての値を調べることができます。  ブレークポイントには、メソッドに対して次のような利点 `console.log()` があります。  

*   を使用して、ソース コードを手動で開き、関連するコードを検索し、ステートメントを挿入し、Web ページを更新してコンソールにメッセージを `console.log()` `console.log()` 表示する必要 **があります**。  ブレークポイントを使用すると、コードの構造を知らなくても、関連するコードを一時停止できます。  
*   ステートメントでは `console.log()` 、検査する各値を明示的に指定する必要があります。  ブレークポイントを使用すると、DevTools は、その時点ですべての変数の値を表示します。  コードに影響を与える変数が非表示で難読化されている場合があります。  
    
つまり、ブレークポイントは、メソッドよりも速くバグを見つけて修正するのに役立 `console.log()` ちます。  

一歩下がってアプリの動作を考える場合は、[番号 1 の追加] ボタンと [番号 `5 + 1 = 51` `click` **2]** ボタンに関連付けられたイベント リスナーで、正しくない合計 \( \) が計算されるという教育的な推測を行う場合があります。  そのため、リスナーが実行される時間の周りにコードを一時停止する `click` 必要がある可能性があります。  **イベント リスナー ブレークポイントを使用** すると、次の操作を正確に実行できます。  

1.  **[JavaScript デバッグ] ウィンドウで**、[イベント リスナー ブレークポイント] を**選択してセクション**を展開します。  DevTools は、アニメーションやクリップボードなどの展開可能なイベント カテゴリの **一覧を** 表示 **します**。  
1.  [マウス] イベント**カテゴリの横**にある [展開]\( **** ![ [展開] アイコン ](../media/expand-icon.msft.png) \) を選択します。  DevTools は、クリックやマウスダウンなどのマウス イベント**の一覧を****表示します**。  各イベントには、その横にチェック ボックスがあります。  
1.  [] をクリックするには、次のチェック ボックス **をオンにします**。  DevTools は、イベント リスナーの実行時に自動的に `click` 一時停止する設定が行われます。  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="[次へ] をクリックするチェック ボックスをオンにします。" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       [次へ] をクリックするチェック ボックスを **オンにします。**  
    :::image-end:::  
    
1.  デモに戻り、[番号 1 の追加] と **[番号 2] を再度選択** します。  DevTools はデモを一時停止し、ソース ツールでコード行 **を強調表示** します。  DevTools は 16 行目で一時停止する必要があります `get-started.js` 。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    別のコード行で一時停止する場合は、**** 正しい行で一時停止するまで 、[スクリプト実行の再開]\( Resume ![ Script Execution ](../media/resume-script-run-icon.msft.png) \) を選択します。  
    
    > [!NOTE]
    > 別の行で一時停止した場合は、訪問する Web ページごとにイベント リスナーを登録するブラウザー拡張機能 `click` があります。  拡張機能のリスナーで `click` 一時停止しています。  InPrivate モードを使用して****、すべての拡張機能を無効にするプライベートで参照する場合は、必要なコード行を毎回一時停止する場合があります。  

<!--todo: add inprivate section when available -->  

**イベント リスナーのブレークポイント** は、DevTools で使用できる多くの種類のブレークポイントの 1 つにすら異なっています。  さまざまな種類を記憶して、さまざまなシナリオを可能な限り迅速にデバッグできます。  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <a name="step-4-step-through-the-code"></a>手順 4: コードをステップ実行する  

バグの一般的な原因の 1 つは、スクリプトが正しい順序で実行される場合です。  コードをステップ実行すると、コードのランタイムを実行できます。  一度に 1 行を実行して、コードが予想とは異なる順序で実行されている場所を正確に把握するのに役立ちます。  今すぐお試しください:  

1.  [ **次の関数呼び出し** \( ![ Step over next function call \) を選択 ](../media/step-over-icon.msft.png) します。  DevTools は、ステップ インせずに次のコードを実行します。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > DevTools は数行のコードをスキップします。  これは、false と評価されるので、ステートメントのコード ブロックが `inputsAreEmpty()` `if` 実行されないためです。  
    
1.  DevTools **の Sources** ツールで、[Step **to next** function call \( Step to next function call \) を選択して、関数のランタイムを一度に 1 行ステップ実行 ![ ](../media/step-into-icon.msft.png) `updateLabel()` します。  
    
一度に 1 行を確認する方法は、コードをステップ実行する基本的な考え方です。  でコードを確認すると `get-started.js` 、バグは関数のどこかにある可能性 `updateLabel()` があります。  コードのすべての行をステップ実行するのではなく、別の種類のブレークポイントを使用して、バグの可能性がある場所に近いコードを一時停止できます。  

## <a name="step-5-set-a-line-of-code-breakpoint"></a>手順 5: コード行ブレークポイントを設定する  

コード行ブレークポイントは、最も一般的な種類のブレークポイントです。  一時停止する特定のコード行にアクセスする場合は、コード行ブレークポイントを使用します。  

1.  次のコードの最後の行を確認します `updateLabel()` 。  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  左側には、この特定のコード行の番号が **34 と表示されます**。  行 **34 を選択します**。  DevTools は 34 の左側に赤い **アイコンを表示します**。  赤いアイコンは、コード行ブレークポイントがこの行に含まれるかどうかを示します。  DevTools は、このコード行を実行する前に常に一時停止します。  
1.  [スクリプト **実行の再開** \( ![ スクリプト実行の再開 ](../media/resume-script-run-icon.msft.png) \) を選択します。  スクリプトは、33 行目に達するまで実行を続行します。  31 行目、32 行目、および 33 行目では、DevTools は、各行の 、、およびセミコロンの右側の値 `addend1` `addend2` `sum` を出力します。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools が行 34 のコード行ブレークポイントで一時停止する" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       DevTools が行 34 のコード行ブレークポイントで一時停止する  
    :::image-end:::  
    
## <a name="step-6-check-variable-values"></a>手順 6: 変数の値を確認する  

の値、 `addend1` および `addend2` 疑わしい `sum` 外観。  値は引用符で囲まれます。  引用符は、値が文字列を意味します。これはバグの原因を説明する良い仮説です。  状況に関する詳細を収集します。  DevTools には、変数値を調べる多くのツールが提供されています。  

### <a name="method-1-the-scope-panel"></a>方法 1: [スコープ] パネル  

コード行を一時停止すると、[スコープ]**** パネルに、現在定義されているローカル変数とグローバル変数と、各変数の値が表示されます。  また、必要に応じてクロージャ変数も表示されます。  変数値をダブルクリックして編集します。  コード行を一時停止しない場合、[スコープ] **パネルは空** です。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="[スコープ] ウィンドウ" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   [ **スコープ]** ウィンドウ  
:::image-end:::  

### <a name="method-2-watch-expressions"></a>方法 2: ウォッチ式  

[ **ウォッチ式]** パネルでは、時間の間に変数の値を監視できます。  名前が示すように、 **ウォッチ式** は変数に限定されるのではありません。  任意の有効な JavaScript 式をウォッチ式に **格納できます**。  今すぐ試してみてください。  

1.  [ウォッチ] **パネルを選択** します。  
1.  [ **式の追加** \( ![ Add Expression ](../media/add-expression-icon.msft.png) \) を選択します。  
1.  「`typeof sum`」と入力します。  
1.  `Enter` を選択します。  DevTools が表示されます `typeof sum: "string"` 。  コロンの右側の値は、ウォッチ式の結果です。  
    
> [!NOTE]
> 次の **図の [ウォッチ式** ] ウィンドウ \(右下\) に、[ `typeof sum` ウォッチ式] が表示されます。  DevTools ウィンドウが大きい場合は、[ **ウォッチ式** ] ウィンドウが [イベント リスナー ブレークポイント] ウィンドウの右側に **表示** されます。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="[ウォッチ式] パネル" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   [ **ウォッチ式]** パネル  
:::image-end:::  

疑わしい場合 `sum` は、数値である必要がある場合に文字列として評価されます。  これで、確認された値の種類がバグの原因です。  

### <a name="method-3-the-console"></a>方法 3: コンソール  

コンソール **を** 使用すると、メッセージを表示できます。また、任意の JavaScript ステートメントを評価 `console.log()` するために使用することもできます。  デバッグの場合は、コンソール **を使用して** 、潜在的な修正プログラムのバグをテストできます。  今すぐ試してみてください。  

1.  コンソール ツール **が閉** じている場合は、選択 `Escape` して開きます。  コンソール **ツール** は、DevTools ウィンドウの下部パネルで開きます。  
1.  コンソールで **、と**入力します `parseInt(addend1) + parseInt(addend2)` 。  ツールのステートメントは、スコープ内のコード行 `addend1` で `addend2` 一時停止されます。  
1.  `Enter` を選択します。  DevTools はステートメントと印刷を評価します。これは、デモで生成 `6` される結果です。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="parseInt(addend1) + parseInt(addend2) を評価した後のコンソール ツール" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       評価 **後** のコンソール ツール `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <a name="step-7-apply-a-fix"></a>手順 7: 修正プログラムを適用する  

バグの修正プログラムを見つけた場合は、コードを編集し、デモを再実行して修正プログラムを試してください。  JavaScript コードは、DevTools UI 内で直接編集し、修正プログラムを適用できます。  今すぐ試してみてください。  

1.  [スクリプト **実行の再開** \( ![ スクリプト実行の再開 ](../media/resume-script-run-icon.msft.png) \) を選択します。  
1.  コード エディター **で、** 行 32 を 、 `var sum = addend1 + addend2` に置き換えます `var sum = parseInt(addend1) + parseInt(addend2)` 。  
1.  `Control` + `S` 変更を保存するには、\(Windows、Linux\) `Command` + `S` または \(macOS\) を選択します。  
1.  [ **ブレークポイントを非アクティブ化** する]\( ![ [ブレークポイントを非アクティブ化 ](../media/deactivate-breakpoints-button-icon.msft.png) する]\) を選択します。  オプションがアクティブな状態を示すために青に変更されます。  [ **ブレークポイントの非アクティブ化** ] が設定されている間、DevTools は設定したブレークポイントを無視します。  
1.  異なる値でデモを試してみてください。  デモで正しく計算されるようになりました。  
    
> [!CAUTION]
> このワークフローは、ブラウザーで実行されているコードにのみ修正プログラムを適用します。  Web ページにアクセスするすべてのユーザーのコードは修正されない。  これを行うには、サーバー上のコードを修正する必要があります。  

## <a name="next-steps"></a>次のステップ  

お疲れさまでした。  JavaScript のデバッグ時に Microsoft Edge DevTools を利用する方法がわかっています。  この記事で学んだツールとメソッドは、数え切れないほどの時間を節約できます。  

この記事では、ブレークポイントを設定する 2 つの方法のみを教えています。  DevTools は、次の設定を含む他の多くの方法を提供します。  

*   指定した条件が true の場合にのみトリガーされる条件付きブレークポイント。  
*   キャッチまたはキャッチされていない例外のブレークポイント。  
*   要求された URL が指定した部分文字列と一致するときにトリガーされる XHR ブレークポイント。  
    
各種類を使用する場合と方法の詳細については、「ブレークポイントを使用してコードを一時停止 [する」に移動します][DevtoolsJavscriptBreakpoints]。  

この記事では、いくつかのコード ステップコントロールについて説明します。  詳細については、「Step [over line of code」に移動します][DevtoolsJavascriptReferenceStepThroughCode]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "Microsoft Edge DevTools アプリケーションでブレークポイントを使用してコードを一時停止する|Microsoft Docs"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "コードのステップスルー - JavaScript デバッグリファレンス |Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "Open Demo |Glitch"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
