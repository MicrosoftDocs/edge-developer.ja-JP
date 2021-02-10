---
description: Microsoft Edge DevTools を使用して JavaScript のバグを見つけて修正する方法について説明します。
title: Microsoft Edge DevTools の JavaScript のデバッグの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/09/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b036fc87149d13446ab1bc05afc8fc8631d27c8d
ms.sourcegitcommit: e737277744dd25a7585c113eef22a2aa4d4c167f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "11325950"
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
# Microsoft Edge DevTools での JavaScript のデバッグの開始  

この記事では、DevTools で JavaScript の問題をデバッグする基本的なワークフローについて説明します。  

## 手順 1: バグを再現する  

バグを一貫して再現する一連のアクションを見つけることは、常にデバッグの最初の手順です。  

1.  Open **Demo を選択します**。  `Control`\(Windows, Linux\) または \(macOS\) を保持し、新しいブラウザー `Command` タブでデモを開きます。  
    
    [Open Demo][OpenDebugJSDemo]  
    
1.  [ `5` 数値 **1] テキスト ボックスに** 入力します。  
1.  [ `1` 数値 **2] テキスト ボックスに入力** します。  
1.  Choose **Add Number 1 and Number 2**.  ボタンの下のラベルは次のようになります `5 + 1 = 51` 。  結果は次の値になります `6` 。  次に、バグである追加エラーを修正します。  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 の場合、51 になりますが、6 になります。" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` の結果 `51` が表示されますが、次の値を使用する必要があります。 `6`  
    :::image-end:::  
    
## 手順 2: ソース パネル UI を理解する  

DevTools には、さまざまなタスクに対してさまざまなツールが提供されています。  CSS の変更、ページ読み込みパフォーマンスのプロファイリング、ネットワーク要求の監視など、さまざまなタスクがあります。  ソース **パネルで** JavaScript をデバッグします。  

1.  `Control` + `Shift` + `J` \(Windows,Linux\) または `Command` + `Option` + `J` \(macOS\) を押して DevTools を開きます。  このショートカットは、コンソール パネル **を開** きます。  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="コンソール パネル" lightbox="../media/javascript-console-empty.msft.png":::
       コンソール**** ツール  
    :::image-end:::  
    
1.  [ソース **] ツールを選択** します。  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="[ソース] パネル" lightbox="../media/javascript-sources-sections.msft.png":::
       [ **ソース]** パネル  
    :::image-end:::  
    
ソース パネル UI **には** 3 つのパーツがあります。  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="ソース パネル UI の 3 つの部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   ソース パネル UI の 3**つの部分**  
:::image-end:::  

1.  [ **ファイル ナビゲーター]** ウィンドウ \(前の図のセクション 1\)。  Web ページが要求するファイルは、ここに一覧表示されます。  
1.  コード **エディター ウィンドウ** \(前の図のセクション 2\)。  [ファイル ナビゲーター] ウィンドウ**** でファイルを選択すると、そのファイルの内容がここに表示されます。  
1.  JavaScript **デバッグ ウィンドウ** \(前の図のセクション 3\)。  Web ページの JavaScript を検査するためのさまざまなツール。  DevTools ウィンドウが幅の広い場合、このウィンドウはコード エディター ウィンドウの右側 **に表示** されます。  
    
## 手順 3: ブレークポイントのあるコードを一時停止する  

この種の問題をデバッグする一般的な方法は、コードに複数のステートメントを挿入し、スクリプトの実行中に値 `console.log()` を検査する方法です。  次に、例を示します。  

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

この `console.log()` メソッドはジョブを完了する可能性がありますが、 **ブレークポイントを** 使用すると処理が速くなります。  ブレークポイントを使用すると、実行時の途中でコードを一時停止し、その時点ですべての値を調べることができます。  ブレークポイントには、この方法に対していくつかの利点 `console.log()` があります。  

*   次に、ソース コードを手動で開き、関連するコードを検索し、ステートメントを挿入し、Web ページを更新してコンソールにメッセージを `console.log()` `console.log()` 表示する必要 **があります**。  ブレークポイントを使用すると、コードの構造を知らなくても、関連するコードを一時停止できます。  
*   ステートメント `console.log()` では、検査する各値を明示的に指定する必要があります。  ブレークポイントを使用すると、DevTools は、その時点のすべての変数の値を表示します。  コードに影響を与える変数が非表示で難読化されている場合があります。  
    
つまり、ブレークポイントは、メソッドよりも速くバグを見つけて修正するのに役立つ `console.log()` 場合があります。  

一歩下がってアプリの動作を考える場合は、[数値 1 と数値 2 の追加] ボタンに関連付けられているイベント リスナーで正しくない合計 `5 + 1 = 51` \( \) が計算されたと推測できます。 `click` ****  そのため、リスナーが実行される時間の周りにコードを一時停止する `click` 必要がある可能性があります。  **イベント リスナーのブレークポイントを** 使用すると、次の操作を正確に実行できます。  

1.  **[JavaScript デバッグ] ウィンドウで**、[イベント リスナーの**ブレークポイント**] を選択してセクションを展開します。  DevTools では、アニメーションやクリップボードなどの展開可能なイベント カテゴリの **一覧が** 表示 **されます**。  
1.  [マウス イベント] **カテゴリの** 横にある [ **展開]** \( [ ![ 展開] アイコン ][ImageExpandIcon] \) を選択します。  DevTools では、クリックやマウスダウンなどのマウス イベントの **一覧** が **表示されます**。  各イベントの横にはチェック ボックスがあります。  
1.  Choose the checkbox next to **click**.  DevTools は、イベント リスナーの実行時に自動的に一 `click` 時停止する設定にしました。  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="次にクリックするチェックボックスを選択します。" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       次にクリックするチェックボックスを選択 **します。**  
    :::image-end:::  
    
1.  デモに戻り、[番号 1 と番号 2 の追加] を **再び選択** します。  DevTools はデモを一時停止し、[ソース] パネルでコード行 **を強調表示** します。  DevTools should pause on line 16 in `get-started.js` .  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    別のコード行で一時停止する場合は、スクリプト実行の再開 **\(** スクリプト実行の再開 \) を、正しい行で一時停止するまで ![ ][ImageResumeIcon] 押します。  
    
    > [!NOTE]
    > 別の行で一時停止した場合は、アクセスする Web ページごとにイベント リスナーを登録するブラウザー拡張機能 `click` があります。  拡張機能のリスナーで `click` 一時停止しました。  InPrivate モードを使用して**** プライベートモードを参照すると、すべての拡張機能が無効になります。その場合は、毎回目的のコード行で一時停止している可能性があります。  

<!--todo: add inprivate section when available -->  

**イベント リスナーのブレークポイントは** 、DevTools で使用できる多くの種類のブレークポイントの 1 つにすすむ機能です。  さまざまな種類を記憶し、さまざまなシナリオを可能な限り迅速にデバッグするのに役立ちます。  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## 手順 4: コードをステップ実行する  

バグの一般的な原因の 1 つは、スクリプトが間違った順序で実行される場合です。  コードをステップ実行すると、コードの実行時を確認できます。  コードが予想とは異なる順序で実行されている場所を正確に把握するために、一度に 1 行を実行します。  今すぐお試しください:  

1.  Choose **Step over next function call** \( Step over next function call ![ ][ImageOverIcon] \).  DevTools は、ステップ インせずに次のコードを実行します。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > DevTools は数行のコードをスキップします。  これは、false `inputsAreEmpty()` と評価されるので、ステートメントのコード ブロックが `if` 実行されないためです。  
    
1.  DevTools の [ソース] パネル**** で、[次の関数呼び出し \( 次の関数呼び出し \ にステップ イン**** ![ ][ImageIntoIcon] ] `updateLabel()` を選択して、関数のランタイムを一度に 1 行ステップ実行します。  
    
コードをステップ実行する基本的な考え方は、一度に 1 行を確認する方法です。  コードを見た場合、バグが関数のどこかにある `get-started.js` 可能性があります `updateLabel()` 。  コードのすべての行をステップ実行するのではなく、別の種類のブレークポイントを使用して、バグの可能性がある場所に近いコードを一時停止することができます。  

## 手順 5: コード行のブレークポイントを設定する  

コード行のブレークポイントは、ブレークポイントの最も一般的な種類です。  一時停止する特定のコード行に達した場合は、コード行のブレークポイントを使用します。  

1.  次のコードの最後の行を確認します `updateLabel()` 。  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  左側に、この特定のコード行の番号が **34 と表示されます**。  行 **34 を選択します**。  DevTools puts a red icon to the left of **34**.  赤いアイコンは、コード行のブレークポイントがこの行に設定されている状態を示します。  DevTools は、このコード行が実行される前に常に一時停止します。  
1.  Choose **Resume script execution** \( Resume script execution ![ ][ImageResumeIcon] \).  スクリプトは、33 行目に達するまで実行を続行します。  31 行目、32 行目、および 33 行目では、DevTools は各行のセミコロンの値 、および右に値 `addend1` `addend2` `sum` を出力します。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools は、34 行目のコード行のブレークポイントで一時停止します" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       DevTools は、34 行目のコード行のブレークポイントで一時停止します  
    :::image-end:::  
    
## 手順 6: 変数値を確認する  

,, `addend1` and `addend2` look suspicious `sum` の値。  値は引用符で囲まれます。  引用符は、値が文字列を意味します。これはバグの原因を説明する良い仮説です。  状況に関する詳細を収集します。  DevTools には、変数値を調べするための多くのツールが含まれています。  

### 方法 1: [範囲] ウィンドウ  

コード行で一時停止すると、[範囲]**** ウィンドウに、現在定義されているローカル変数とグローバル変数が各変数の値と共に表示されます。  また、必要に応じて、クローズ変数も表示されます。  変数値をダブルクリックして編集します。  コード行で一時停止しない場合、[範囲] **ウィンドウは空** です。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="[範囲] ウィンドウ" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   [ **範囲]** ウィンドウ  
:::image-end:::  

### 方法 2: ウォッチ式  

[ **ウォッチ式]** ウィンドウでは、時間の中で変数の値を監視できます。  名前が示すように、 **ウォッチ式** は変数に限定されるのではありません。  ウォッチ式には、任意の有効な JavaScript 式を **格納できます**。  今すぐ試してみてください。  

1.  [ウォッチ] **ウィンドウを選択** します。  
1.  式 **の追加** \( ![ 式の追加 ][ImageAddIcon] \) を選択します。  
1.  「`typeof sum`」と入力します。  
1.  `Enter` を選択します。  DevTools shows `typeof sum: "string"` .  コロンの右側の値は、ウォッチ式の結果です。  
    
> [!NOTE]
> 次の **図のウォッチ式** ウィンドウ \(右下\) にウォッチ `typeof sum` 式が表示されます。  DevTools ウィンドウが大きい場合、[ **ウォッチ** 式] ウィンドウは [イベント リスナーのブレークポイント] ウィンドウの右側に **表示** されます。  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="ウォッチ式ウィンドウ" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   ウォッチ**式ウィンドウ**  
:::image-end:::  

疑わしい場合 `sum` 、数値である必要があるときに、文字列として評価されています。  これで、値の種類がバグの原因として確認されました。  

### 方法 3: コンソール  

コンソール **を** 使用すると、メッセージを表示できます。また、任意の JavaScript ステートメントを評価 `console.log()` するために使用することもできます。  デバッグの場合は、コンソール **を使用して** 、バグに関する潜在的な修正プログラムをテストできます。  今すぐ試してみてください。  

1.  コンソール ドロ **ワーが** 閉じている場合は、それを `Escape` 選択して開きます。  コンソール **ドロ** ワーが DevTools ウィンドウの下部パネルに開きます。  
1.  コンソールで **、「.」と**入力します `parseInt(addend1) + parseInt(addend2)` 。  ツールのステートメントは、範囲内のコード行 `addend1` `addend2` で一時停止されます。  
1.  `Enter` を選択します。  DevTools はステートメントを評価して印刷します。これは、デモが生成 `6` すると予想される結果です。  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="parseInt(addend1) + parseInt(addend2) を評価した後のコンソール ドロワー" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       評価 **後** のコンソール ドロワー `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## 手順 7: 修正プログラムを適用する  

バグの修正プログラムが見つけた場合は、コードを編集してデモを再実行して修正プログラムを試してください。  DevTools UI 内で JavaScript コードを直接編集し、修正プログラムを適用することができます。  今すぐ試してみてください。  

1.  Choose **Resume script execution** \( Resume script execution ![ ][ImageResumeIcon] \).  
1.  コード エディター **で、行**32 を次の行 `var sum = addend1 + addend2` に置き換えます `var sum = parseInt(addend1) + parseInt(addend2)` 。  
1.  `Control` + `S` \(Windows,Linux\) または `Command` + `S` \(macOS\) を選択して変更を保存します。  
1.  Choose **Deactivate breakpoints** \( ![ Deactivate breakpoints ][ImageDeactivateIcon] \).  オプションがアクティブな状態を示すために青に変更されます。  Deactivate **ブレークポイントが** 設定されている間、DevTools は設定したブレークポイントを無視します。  
1.  さまざまな値を使ってデモを試してみてください。  デモが正しく計算されるようになりました。  
    
> [!CAUTION]
> このワークフローは、ブラウザーで実行されているコードにのみ修正プログラムを適用します。  Web ページにアクセスするユーザー全員のコードが修正されるという問題はありません。  これを行うには、サーバー上のコードを修正する必要があります。  

## 次のステップ  

お疲れさまでした。  これで、JavaScript をデバッグするときに Microsoft Edge DevTools を有効に利用する方法がわかっています。  この記事で学習したツールとメソッドを使用すると、数え切れないほど時間が節約される場合があります。  

この記事では、ブレークポイントを設定する 2 つの方法についてのみ取り上しました。  DevTools には、次の設定を含む多くの方法があります。  

*   指定した条件が true の場合にのみトリガーされる条件付きブレークポイント。  
*   キャッチまたはキャッチされていない例外に対するブレークポイント。  
*   要求された URL が指定した部分文字列と一致するときにトリガーされる XHR ブレークポイント。  
    
各種類を使用する場合と方法の詳細については、「ブレークポイントでコードを一時停止 [する」に移動します][DevtoolsJavscriptBreakpoints]。  

この記事では、いくつかのコード ステップ実行コントロールについて説明します。  詳細については、「ステップ オーバー コード [」に移動してください][DevtoolsJavascriptReferenceStepThroughCode]。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: ../media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageIntoIcon]: ../media/step-into-icon.msft.png  
[ImageOverIcon]: ../media/step-over-icon.msft.png  
[ImageResumeIcon]: ../media/resume-script-run-icon.msft.png  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "Microsoft Edge DevTools アプリケーションでブレークポイントを設定してコードを一時停止する|Microsoft Docs"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "コードのステップ実行 - JavaScript デバッグ リファレンス |Microsoft Docs"

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
