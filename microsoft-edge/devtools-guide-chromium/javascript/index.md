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
# <span data-ttu-id="34b68-104">Microsoft Edge DevTools での JavaScript のデバッグの開始</span><span class="sxs-lookup"><span data-stu-id="34b68-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="34b68-105">この記事では、DevTools で JavaScript の問題をデバッグする基本的なワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34b68-105">This article teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <span data-ttu-id="34b68-106">手順 1: バグを再現する</span><span class="sxs-lookup"><span data-stu-id="34b68-106">Step 1: Reproduce the bug</span></span>  

<span data-ttu-id="34b68-107">バグを一貫して再現する一連のアクションを見つけることは、常にデバッグの最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="34b68-107">Finding a series of actions that consistently reproduce a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="34b68-108">Open **Demo を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34b68-108">Choose **Open Demo**.</span></span>  <span data-ttu-id="34b68-109">`Control`\(Windows, Linux\) または \(macOS\) を保持し、新しいブラウザー `Command` タブでデモを開きます。</span><span class="sxs-lookup"><span data-stu-id="34b68-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and open the demo in a new browser tab.</span></span>  
    
    [<span data-ttu-id="34b68-110">Open Demo</span><span class="sxs-lookup"><span data-stu-id="34b68-110">Open Demo</span></span>][OpenDebugJSDemo]  
    
1.  <span data-ttu-id="34b68-111">[ `5` 数値 **1] テキスト ボックスに** 入力します。</span><span class="sxs-lookup"><span data-stu-id="34b68-111">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="34b68-112">[ `1` 数値 **2] テキスト ボックスに入力** します。</span><span class="sxs-lookup"><span data-stu-id="34b68-112">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="34b68-113">Choose **Add Number 1 and Number 2**.</span><span class="sxs-lookup"><span data-stu-id="34b68-113">Choose **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="34b68-114">ボタンの下のラベルは次のようになります `5 + 1 = 51` 。</span><span class="sxs-lookup"><span data-stu-id="34b68-114">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="34b68-115">結果は次の値になります `6` 。</span><span class="sxs-lookup"><span data-stu-id="34b68-115">The result should be `6`.</span></span>  <span data-ttu-id="34b68-116">次に、バグである追加エラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="34b68-116">Next, fix the addition error that is the bug.</span></span>  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 の場合、51 になりますが、6 になります。" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` <span data-ttu-id="34b68-118">の結果 `51` が表示されますが、次の値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-118">results in `51`, but should be</span></span> `6`  
    :::image-end:::  
    
## <span data-ttu-id="34b68-119">手順 2: ソース パネル UI を理解する</span><span class="sxs-lookup"><span data-stu-id="34b68-119">Step 2: Get familiar with the Sources panel UI</span></span>  

<span data-ttu-id="34b68-120">DevTools には、さまざまなタスクに対してさまざまなツールが提供されています。</span><span class="sxs-lookup"><span data-stu-id="34b68-120">DevTools provides many different tools for different tasks.</span></span>  <span data-ttu-id="34b68-121">CSS の変更、ページ読み込みパフォーマンスのプロファイリング、ネットワーク要求の監視など、さまざまなタスクがあります。</span><span class="sxs-lookup"><span data-stu-id="34b68-121">Different tasks include changing CSS, profiling page-load performance, and monitoring network requests.</span></span>  <span data-ttu-id="34b68-122">ソース **パネルで** JavaScript をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="34b68-122">The **Sources** panel is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="34b68-123">`Control` + `Shift` + `J` \(Windows,Linux\) または `Command` + `Option` + `J` \(macOS\) を押して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="34b68-123">Open DevTools by pressing `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="34b68-124">このショートカットは、コンソール パネル **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="34b68-124">This shortcut opens the **Console** panel.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="コンソール パネル" lightbox="../media/javascript-console-empty.msft.png":::
       <span data-ttu-id="34b68-126">コンソール\*\*\*\* ツール</span><span class="sxs-lookup"><span data-stu-id="34b68-126">The **Console** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="34b68-127">[ソース **] ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="34b68-127">Choose the **Sources** tool.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="[ソース] パネル" lightbox="../media/javascript-sources-sections.msft.png":::
       <span data-ttu-id="34b68-129">[ **ソース]** パネル</span><span class="sxs-lookup"><span data-stu-id="34b68-129">The **Sources** panel</span></span>  
    :::image-end:::  
    
<span data-ttu-id="34b68-130">ソース パネル UI **には** 3 つのパーツがあります。</span><span class="sxs-lookup"><span data-stu-id="34b68-130">The **Sources** panel UI has three parts.</span></span>  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="ソース パネル UI の 3 つの部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   <span data-ttu-id="34b68-132">ソース パネル UI の 3**つの部分**</span><span class="sxs-lookup"><span data-stu-id="34b68-132">The 3 parts of the **Sources** panel UI</span></span>  
:::image-end:::  

1.  <span data-ttu-id="34b68-133">[ **ファイル ナビゲーター]** ウィンドウ \(前の図のセクション 1\)。</span><span class="sxs-lookup"><span data-stu-id="34b68-133">The **File Navigator** pane \(Section 1 in the previous figure\).</span></span>  <span data-ttu-id="34b68-134">Web ページが要求するファイルは、ここに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-134">Every file that the webpage requests is listed here.</span></span>  
1.  <span data-ttu-id="34b68-135">コード **エディター ウィンドウ** \(前の図のセクション 2\)。</span><span class="sxs-lookup"><span data-stu-id="34b68-135">The **Code Editor** pane \(Section 2 in the previous figure\).</span></span>  <span data-ttu-id="34b68-136">[ファイル ナビゲーター] ウィンドウ\*\*\*\* でファイルを選択すると、そのファイルの内容がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-136">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span></span>  
1.  <span data-ttu-id="34b68-137">JavaScript **デバッグ ウィンドウ** \(前の図のセクション 3\)。</span><span class="sxs-lookup"><span data-stu-id="34b68-137">The **JavaScript Debugging** pane \(Section 3 in the previous figure\).</span></span>  <span data-ttu-id="34b68-138">Web ページの JavaScript を検査するためのさまざまなツール。</span><span class="sxs-lookup"><span data-stu-id="34b68-138">Various tools for inspecting the JavaScript for the webpage.</span></span>  <span data-ttu-id="34b68-139">DevTools ウィンドウが幅の広い場合、このウィンドウはコード エディター ウィンドウの右側 **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-139">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span></span>  
    
## <span data-ttu-id="34b68-140">手順 3: ブレークポイントのあるコードを一時停止する</span><span class="sxs-lookup"><span data-stu-id="34b68-140">Step 3: Pause the code with a breakpoint</span></span>  

<span data-ttu-id="34b68-141">この種の問題をデバッグする一般的な方法は、コードに複数のステートメントを挿入し、スクリプトの実行中に値 `console.log()` を検査する方法です。</span><span class="sxs-lookup"><span data-stu-id="34b68-141">A common method for debugging this type of problem is to insert several `console.log()` statements into the code and then to inspect values as the script runs.</span></span>  <span data-ttu-id="34b68-142">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="34b68-142">For example:</span></span>  

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

<span data-ttu-id="34b68-143">この `console.log()` メソッドはジョブを完了する可能性がありますが、 **ブレークポイントを** 使用すると処理が速くなります。</span><span class="sxs-lookup"><span data-stu-id="34b68-143">The `console.log()` method may get the job done, but **breakpoints** get it done faster.</span></span>  <span data-ttu-id="34b68-144">ブレークポイントを使用すると、実行時の途中でコードを一時停止し、その時点ですべての値を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="34b68-144">A breakpoint lets you pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="34b68-145">ブレークポイントには、この方法に対していくつかの利点 `console.log()` があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-145">Breakpoints have a few advantages over the `console.log()` method:</span></span>  

*   <span data-ttu-id="34b68-146">次に、ソース コードを手動で開き、関連するコードを検索し、ステートメントを挿入し、Web ページを更新してコンソールにメッセージを `console.log()` `console.log()` 表示する必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="34b68-146">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then refresh the webpage to display the messages in the **Console**.</span></span>  <span data-ttu-id="34b68-147">ブレークポイントを使用すると、コードの構造を知らなくても、関連するコードを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="34b68-147">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="34b68-148">ステートメント `console.log()` では、検査する各値を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-148">In your `console.log()` statements, you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="34b68-149">ブレークポイントを使用すると、DevTools は、その時点のすべての変数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="34b68-149">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="34b68-150">コードに影響を与える変数が非表示で難読化されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-150">Sometimes variables that affect your code are hidden and obfuscated.</span></span>  
    
<span data-ttu-id="34b68-151">つまり、ブレークポイントは、メソッドよりも速くバグを見つけて修正するのに役立つ `console.log()` 場合があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-151">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="34b68-152">一歩下がってアプリの動作を考える場合は、[数値 1 と数値 2 の追加] ボタンに関連付けられているイベント リスナーで正しくない合計 `5 + 1 = 51` \( \) が計算されたと推測できます。 `click` \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="34b68-152">If you step back and think about how the app works, you may make an educated guess that the incorrect sum \(`5 + 1 = 51`\) is computed in the `click` event listener associated with the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="34b68-153">そのため、リスナーが実行される時間の周りにコードを一時停止する `click` 必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-153">So, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="34b68-154">**イベント リスナーのブレークポイントを** 使用すると、次の操作を正確に実行できます。</span><span class="sxs-lookup"><span data-stu-id="34b68-154">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="34b68-155">**[JavaScript デバッグ] ウィンドウで**、[イベント リスナーの**ブレークポイント**] を選択してセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="34b68-155">In the **JavaScript Debugging** pane, choose **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="34b68-156">DevTools では、アニメーションやクリップボードなどの展開可能なイベント カテゴリの **一覧が** 表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="34b68-156">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="34b68-157">[マウス イベント] **カテゴリの** 横にある [ **展開]** \( [ ![ 展開] アイコン ][ImageExpandIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="34b68-157">Next to the **Mouse** event category, choose **Expand** \(![Expand icon][ImageExpandIcon]\).</span></span>  <span data-ttu-id="34b68-158">DevTools では、クリックやマウスダウンなどのマウス イベントの **一覧** が **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="34b68-158">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="34b68-159">各イベントの横にはチェック ボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="34b68-159">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="34b68-160">Choose the checkbox next to **click**.</span><span class="sxs-lookup"><span data-stu-id="34b68-160">Choose the checkbox next to **click**.</span></span>  <span data-ttu-id="34b68-161">DevTools は、イベント リスナーの実行時に自動的に一 `click` 時停止する設定にしました。</span><span class="sxs-lookup"><span data-stu-id="34b68-161">DevTools is now set up to automatically pause when any `click` event listener runs.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="次にクリックするチェックボックスを選択します。" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       <span data-ttu-id="34b68-163">次にクリックするチェックボックスを選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="34b68-163">Choose the checkbox next to **click**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="34b68-164">デモに戻り、[番号 1 と番号 2 の追加] を **再び選択** します。</span><span class="sxs-lookup"><span data-stu-id="34b68-164">Back on the demo, choose **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="34b68-165">DevTools はデモを一時停止し、[ソース] パネルでコード行 **を強調表示** します。</span><span class="sxs-lookup"><span data-stu-id="34b68-165">DevTools pauses the demo and highlights a line of code in the **Sources** panel.</span></span>  <span data-ttu-id="34b68-166">DevTools should pause on line 16 in `get-started.js` .</span><span class="sxs-lookup"><span data-stu-id="34b68-166">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="34b68-167">別のコード行で一時停止する場合は、スクリプト実行の再開 **\(** スクリプト実行の再開 \) を、正しい行で一時停止するまで ![ ][ImageResumeIcon] 押します。</span><span class="sxs-lookup"><span data-stu-id="34b68-167">If you pause on a different line of code, press **Resume Script Execution** \(![Resume Script Execution][ImageResumeIcon]\) until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="34b68-168">別の行で一時停止した場合は、アクセスする Web ページごとにイベント リスナーを登録するブラウザー拡張機能 `click` があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-168">If you paused on a different line, you have a browser extension that registers a `click` event listener on every webpage that you visit.</span></span>  <span data-ttu-id="34b68-169">拡張機能のリスナーで `click` 一時停止しました。</span><span class="sxs-lookup"><span data-stu-id="34b68-169">You were paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="34b68-170">InPrivate モードを使用して\*\*\*\* プライベートモードを参照すると、すべての拡張機能が無効になります。その場合は、毎回目的のコード行で一時停止している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-170">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="34b68-171">**イベント リスナーのブレークポイントは** 、DevTools で使用できる多くの種類のブレークポイントの 1 つにすすむ機能です。</span><span class="sxs-lookup"><span data-stu-id="34b68-171">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="34b68-172">さまざまな種類を記憶し、さまざまなシナリオを可能な限り迅速にデバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="34b68-172">Memorize all the different types to help you debug different scenarios as quickly as possible.</span></span>  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <span data-ttu-id="34b68-173">手順 4: コードをステップ実行する</span><span class="sxs-lookup"><span data-stu-id="34b68-173">Step 4: Step through the code</span></span>  

<span data-ttu-id="34b68-174">バグの一般的な原因の 1 つは、スクリプトが間違った順序で実行される場合です。</span><span class="sxs-lookup"><span data-stu-id="34b68-174">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="34b68-175">コードをステップ実行すると、コードの実行時を確認できます。</span><span class="sxs-lookup"><span data-stu-id="34b68-175">Stepping through your code allows you to walk through the runtime of your code.</span></span>  <span data-ttu-id="34b68-176">コードが予想とは異なる順序で実行されている場所を正確に把握するために、一度に 1 行を実行します。</span><span class="sxs-lookup"><span data-stu-id="34b68-176">You walk through one line at a time to help you figure out exactly where your code is running in a different order than you expect.</span></span>  <span data-ttu-id="34b68-177">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="34b68-177">Try it now:</span></span>  

1.  <span data-ttu-id="34b68-178">Choose **Step over next function call** \( Step over next function call ![ ][ImageOverIcon] \).</span><span class="sxs-lookup"><span data-stu-id="34b68-178">Choose **Step over next function call** \(![Step over next function call][ImageOverIcon]\).</span></span>  <span data-ttu-id="34b68-179">DevTools は、ステップ インせずに次のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="34b68-179">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="34b68-180">DevTools は数行のコードをスキップします。</span><span class="sxs-lookup"><span data-stu-id="34b68-180">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="34b68-181">これは、false `inputsAreEmpty()` と評価されるので、ステートメントのコード ブロックが `if` 実行されないためです。</span><span class="sxs-lookup"><span data-stu-id="34b68-181">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  
    
1.  <span data-ttu-id="34b68-182">DevTools の [ソース] パネル\*\*\*\* で、[次の関数呼び出し \( 次の関数呼び出し \ にステップ イン\*\*\*\* ![ ][ImageIntoIcon] ] `updateLabel()` を選択して、関数のランタイムを一度に 1 行ステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="34b68-182">On the **Sources** panel of DevTools, choose **Step into next function call** \(![Step into next function call][ImageIntoIcon]\) to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  
    
<span data-ttu-id="34b68-183">コードをステップ実行する基本的な考え方は、一度に 1 行を確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="34b68-183">Reviewing one line at a time is the basic idea of stepping through code.</span></span>  <span data-ttu-id="34b68-184">コードを見た場合、バグが関数のどこかにある `get-started.js` 可能性があります `updateLabel()` 。</span><span class="sxs-lookup"><span data-stu-id="34b68-184">If you look at the code in `get-started.js`, you see that the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="34b68-185">コードのすべての行をステップ実行するのではなく、別の種類のブレークポイントを使用して、バグの可能性がある場所に近いコードを一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="34b68-185">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <span data-ttu-id="34b68-186">手順 5: コード行のブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="34b68-186">Step 5: Set a line-of-code breakpoint</span></span>  

<span data-ttu-id="34b68-187">コード行のブレークポイントは、ブレークポイントの最も一般的な種類です。</span><span class="sxs-lookup"><span data-stu-id="34b68-187">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="34b68-188">一時停止する特定のコード行に達した場合は、コード行のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="34b68-188">When you get to the specific line of code you want to pause, use a line-of-code breakpoint.</span></span>  

1.  <span data-ttu-id="34b68-189">次のコードの最後の行を確認します `updateLabel()` 。</span><span class="sxs-lookup"><span data-stu-id="34b68-189">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="34b68-190">左側に、この特定のコード行の番号が **34 と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="34b68-190">On the left, the number of this particular line of code is displayed as **34**.</span></span>  <span data-ttu-id="34b68-191">行 **34 を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34b68-191">Choose line **34**.</span></span>  <span data-ttu-id="34b68-192">DevTools puts a red icon to the left of **34**.</span><span class="sxs-lookup"><span data-stu-id="34b68-192">DevTools puts a red icon to the left of **34**.</span></span>  <span data-ttu-id="34b68-193">赤いアイコンは、コード行のブレークポイントがこの行に設定されている状態を示します。</span><span class="sxs-lookup"><span data-stu-id="34b68-193">The red icon indicates that a line-of-code breakpoint is on this line.</span></span>  <span data-ttu-id="34b68-194">DevTools は、このコード行が実行される前に常に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="34b68-194">DevTools always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="34b68-195">Choose **Resume script execution** \( Resume script execution ![ ][ImageResumeIcon] \).</span><span class="sxs-lookup"><span data-stu-id="34b68-195">Choose **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  <span data-ttu-id="34b68-196">スクリプトは、33 行目に達するまで実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="34b68-196">The script continues running until it reaches line 33.</span></span>  <span data-ttu-id="34b68-197">31 行目、32 行目、および 33 行目では、DevTools は各行のセミコロンの値 、および右に値 `addend1` `addend2` `sum` を出力します。</span><span class="sxs-lookup"><span data-stu-id="34b68-197">On lines 31, 32, and 33, DevTools prints the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools は、34 行目のコード行のブレークポイントで一時停止します" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       <span data-ttu-id="34b68-199">DevTools は、34 行目のコード行のブレークポイントで一時停止します</span><span class="sxs-lookup"><span data-stu-id="34b68-199">DevTools pauses on the line-of-code breakpoint on line 34</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="34b68-200">手順 6: 変数値を確認する</span><span class="sxs-lookup"><span data-stu-id="34b68-200">Step 6: Check variable values</span></span>  

<span data-ttu-id="34b68-201">,, `addend1` and `addend2` look suspicious `sum` の値。</span><span class="sxs-lookup"><span data-stu-id="34b68-201">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="34b68-202">値は引用符で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="34b68-202">The values are wrapped in quotes.</span></span>  <span data-ttu-id="34b68-203">引用符は、値が文字列を意味します。これはバグの原因を説明する良い仮説です。</span><span class="sxs-lookup"><span data-stu-id="34b68-203">The quotations mean that the value is a string, which is a good hypothesis to explain the cause of the bug.</span></span>  <span data-ttu-id="34b68-204">状況に関する詳細を収集します。</span><span class="sxs-lookup"><span data-stu-id="34b68-204">Gather more information about the situation.</span></span>  <span data-ttu-id="34b68-205">DevTools には、変数値を調べするための多くのツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34b68-205">DevTools provides many tools for examining variable values.</span></span>  

### <span data-ttu-id="34b68-206">方法 1: [範囲] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="34b68-206">Method 1: The Scope pane</span></span>  

<span data-ttu-id="34b68-207">コード行で一時停止すると、[範囲]\*\*\*\* ウィンドウに、現在定義されているローカル変数とグローバル変数が各変数の値と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-207">If you pause on a line of code, the **Scope** pane displays the local and global variables that are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="34b68-208">また、必要に応じて、クローズ変数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-208">It also displays closure variables, as applicable.</span></span>  <span data-ttu-id="34b68-209">変数値をダブルクリックして編集します。</span><span class="sxs-lookup"><span data-stu-id="34b68-209">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="34b68-210">コード行で一時停止しない場合、[範囲] **ウィンドウは空** です。</span><span class="sxs-lookup"><span data-stu-id="34b68-210">If you don't pause on a line of code, the **Scope** pane is empty.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="[範囲] ウィンドウ" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   <span data-ttu-id="34b68-212">[ **範囲]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="34b68-212">The **Scope** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="34b68-213">方法 2: ウォッチ式</span><span class="sxs-lookup"><span data-stu-id="34b68-213">Method 2: Watch Expressions</span></span>  

<span data-ttu-id="34b68-214">[ **ウォッチ式]** ウィンドウでは、時間の中で変数の値を監視できます。</span><span class="sxs-lookup"><span data-stu-id="34b68-214">The **Watch Expressions** pane lets you monitor the values of variables over time.</span></span>  <span data-ttu-id="34b68-215">名前が示すように、 **ウォッチ式** は変数に限定されるのではありません。</span><span class="sxs-lookup"><span data-stu-id="34b68-215">As the name implies, **Watch Expressions** aren't limited to variables.</span></span>  <span data-ttu-id="34b68-216">ウォッチ式には、任意の有効な JavaScript 式を **格納できます**。</span><span class="sxs-lookup"><span data-stu-id="34b68-216">You may store any valid JavaScript expression in a **Watch Expression**.</span></span>  <span data-ttu-id="34b68-217">今すぐ試してみてください。</span><span class="sxs-lookup"><span data-stu-id="34b68-217">Try it now.</span></span>  

1.  <span data-ttu-id="34b68-218">[ウォッチ] **ウィンドウを選択** します。</span><span class="sxs-lookup"><span data-stu-id="34b68-218">Choose the **Watch** pane.</span></span>  
1.  <span data-ttu-id="34b68-219">式 **の追加** \( ![ 式の追加 ][ImageAddIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="34b68-219">Choose **Add Expression** \(![Add Expression][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="34b68-220">「`typeof sum`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="34b68-220">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="34b68-221">`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="34b68-221">Select `Enter`.</span></span>  <span data-ttu-id="34b68-222">DevTools shows `typeof sum: "string"` .</span><span class="sxs-lookup"><span data-stu-id="34b68-222">DevTools shows `typeof sum: "string"`.</span></span>  <span data-ttu-id="34b68-223">コロンの右側の値は、ウォッチ式の結果です。</span><span class="sxs-lookup"><span data-stu-id="34b68-223">The value to the right of the colon is the result of your Watch Expression.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="34b68-224">次の **図のウォッチ式** ウィンドウ \(右下\) にウォッチ `typeof sum` 式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-224">In the **Watch Expression** pane \(bottom-right\) in the following figure, the `typeof sum` Watch Expression is displayed.</span></span>  <span data-ttu-id="34b68-225">DevTools ウィンドウが大きい場合、[ **ウォッチ** 式] ウィンドウは [イベント リスナーのブレークポイント] ウィンドウの右側に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-225">If your DevTools window is large, the **Watch Expression** pane is on the right above the **Event Listener Breakpoints** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="ウォッチ式ウィンドウ" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   <span data-ttu-id="34b68-227">ウォッチ**式ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="34b68-227">The **Watch Expression** pane</span></span>  
:::image-end:::  

<span data-ttu-id="34b68-228">疑わしい場合 `sum` 、数値である必要があるときに、文字列として評価されています。</span><span class="sxs-lookup"><span data-stu-id="34b68-228">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="34b68-229">これで、値の種類がバグの原因として確認されました。</span><span class="sxs-lookup"><span data-stu-id="34b68-229">You now confirmed value type is the cause of the bug.</span></span>  

### <span data-ttu-id="34b68-230">方法 3: コンソール</span><span class="sxs-lookup"><span data-stu-id="34b68-230">Method 3: The Console</span></span>  

<span data-ttu-id="34b68-231">コンソール **を** 使用すると、メッセージを表示できます。また、任意の JavaScript ステートメントを評価 `console.log()` するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="34b68-231">The **Console** allows you to view `console.log()` messages and you may also use it to evaluate arbitrary JavaScript statements.</span></span>  <span data-ttu-id="34b68-232">デバッグの場合は、コンソール **を使用して** 、バグに関する潜在的な修正プログラムをテストできます。</span><span class="sxs-lookup"><span data-stu-id="34b68-232">For debugging, you may use the **Console** to test potential fixes for bugs.</span></span>  <span data-ttu-id="34b68-233">今すぐ試してみてください。</span><span class="sxs-lookup"><span data-stu-id="34b68-233">Try it now.</span></span>  

1.  <span data-ttu-id="34b68-234">コンソール ドロ **ワーが** 閉じている場合は、それを `Escape` 選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="34b68-234">If the **Console** drawer is closed, select `Escape` to open it.</span></span>  <span data-ttu-id="34b68-235">コンソール **ドロ** ワーが DevTools ウィンドウの下部パネルに開きます。</span><span class="sxs-lookup"><span data-stu-id="34b68-235">The **Console** drawer opens in the lower panel of the DevTools window.</span></span>  
1.  <span data-ttu-id="34b68-236">コンソールで **、「.」と**入力します `parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="34b68-236">In the **Console**, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="34b68-237">ツールのステートメントは、範囲内のコード行 `addend1` `addend2` で一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-237">The statement the tool is paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="34b68-238">`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="34b68-238">Select `Enter`.</span></span>  <span data-ttu-id="34b68-239">DevTools はステートメントを評価して印刷します。これは、デモが生成 `6` すると予想される結果です。</span><span class="sxs-lookup"><span data-stu-id="34b68-239">DevTools evaluates the statement and prints `6`, which is the result you expect the demo to produce.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="parseInt(addend1) + parseInt(addend2) を評価した後のコンソール ドロワー" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       <span data-ttu-id="34b68-241">評価 **後** のコンソール ドロワー</span><span class="sxs-lookup"><span data-stu-id="34b68-241">The **Console** drawer, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <span data-ttu-id="34b68-242">手順 7: 修正プログラムを適用する</span><span class="sxs-lookup"><span data-stu-id="34b68-242">Step 7: Apply a fix</span></span>  

<span data-ttu-id="34b68-243">バグの修正プログラムが見つけた場合は、コードを編集してデモを再実行して修正プログラムを試してください。</span><span class="sxs-lookup"><span data-stu-id="34b68-243">If you find a fix for the bug, try out your fix by editing the code and rerunning the demo.</span></span>  <span data-ttu-id="34b68-244">DevTools UI 内で JavaScript コードを直接編集し、修正プログラムを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="34b68-244">You may edit JavaScript code directly within the DevTools UI and apply the fix.</span></span>  <span data-ttu-id="34b68-245">今すぐ試してみてください。</span><span class="sxs-lookup"><span data-stu-id="34b68-245">Try it now.</span></span>  

1.  <span data-ttu-id="34b68-246">Choose **Resume script execution** \( Resume script execution ![ ][ImageResumeIcon] \).</span><span class="sxs-lookup"><span data-stu-id="34b68-246">Choose **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  
1.  <span data-ttu-id="34b68-247">コード エディター **で、行**32 を次の行 `var sum = addend1 + addend2` に置き換えます `var sum = parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="34b68-247">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="34b68-248">`Control` + `S` \(Windows,Linux\) または `Command` + `S` \(macOS\) を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="34b68-248">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="34b68-249">Choose **Deactivate breakpoints** \( ![ Deactivate breakpoints ][ImageDeactivateIcon] \).</span><span class="sxs-lookup"><span data-stu-id="34b68-249">Choose **Deactivate breakpoints** \(![Deactivate breakpoints][ImageDeactivateIcon]\).</span></span>  <span data-ttu-id="34b68-250">オプションがアクティブな状態を示すために青に変更されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-250">It changes blue to indicate the option is active.</span></span>  <span data-ttu-id="34b68-251">Deactivate **ブレークポイントが** 設定されている間、DevTools は設定したブレークポイントを無視します。</span><span class="sxs-lookup"><span data-stu-id="34b68-251">While **Deactivate breakpoints** is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="34b68-252">さまざまな値を使ってデモを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="34b68-252">Try out the demo with different values.</span></span>  <span data-ttu-id="34b68-253">デモが正しく計算されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="34b68-253">The demo now calculates correctly.</span></span>  
    
> [!CAUTION]
> <span data-ttu-id="34b68-254">このワークフローは、ブラウザーで実行されているコードにのみ修正プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="34b68-254">This workflow only applies a fix to the code that is running in your browser.</span></span>  <span data-ttu-id="34b68-255">Web ページにアクセスするユーザー全員のコードが修正されるという問題はありません。</span><span class="sxs-lookup"><span data-stu-id="34b68-255">It does not fix the code for all users that visit your webpage.</span></span>  <span data-ttu-id="34b68-256">これを行うには、サーバー上のコードを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-256">To do that, you need to fix the code that is on your servers.</span></span>  

## <span data-ttu-id="34b68-257">次のステップ</span><span class="sxs-lookup"><span data-stu-id="34b68-257">Next steps</span></span>  

<span data-ttu-id="34b68-258">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="34b68-258">Congratulations!</span></span>  <span data-ttu-id="34b68-259">これで、JavaScript をデバッグするときに Microsoft Edge DevTools を有効に利用する方法がわかっています。</span><span class="sxs-lookup"><span data-stu-id="34b68-259">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="34b68-260">この記事で学習したツールとメソッドを使用すると、数え切れないほど時間が節約される場合があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-260">The tools and methods you learned in this article may save you countless hours.</span></span>  

<span data-ttu-id="34b68-261">この記事では、ブレークポイントを設定する 2 つの方法についてのみ取り上しました。</span><span class="sxs-lookup"><span data-stu-id="34b68-261">This article only taught you two ways to set breakpoints.</span></span>  <span data-ttu-id="34b68-262">DevTools には、次の設定を含む多くの方法があります。</span><span class="sxs-lookup"><span data-stu-id="34b68-262">DevTools offers many other ways including the following settings.</span></span>  

*   <span data-ttu-id="34b68-263">指定した条件が true の場合にのみトリガーされる条件付きブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="34b68-263">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="34b68-264">キャッチまたはキャッチされていない例外に対するブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="34b68-264">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="34b68-265">要求された URL が指定した部分文字列と一致するときにトリガーされる XHR ブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="34b68-265">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  
    
<span data-ttu-id="34b68-266">各種類を使用する場合と方法の詳細については、「ブレークポイントでコードを一時停止 [する」に移動します][DevtoolsJavscriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="34b68-266">For more information about when and how to use each type, navigate to [Pause Your Code With Breakpoints][DevtoolsJavscriptBreakpoints].</span></span>  

<span data-ttu-id="34b68-267">この記事では、いくつかのコード ステップ実行コントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34b68-267">A couple of code stepping controls aren't explained in this article.</span></span>  <span data-ttu-id="34b68-268">詳細については、「ステップ オーバー コード [」に移動してください][DevtoolsJavascriptReferenceStepThroughCode]。</span><span class="sxs-lookup"><span data-stu-id="34b68-268">For more information, navigate to [Step over line of code][DevtoolsJavascriptReferenceStepThroughCode].</span></span>  

## <span data-ttu-id="34b68-269">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="34b68-269">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="34b68-273">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="34b68-273">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="34b68-274">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="34b68-274">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="34b68-276">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="34b68-276">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
