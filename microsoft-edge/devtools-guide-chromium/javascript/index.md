---
description: Microsoft Edge DevTools を使用して JavaScript のバグを見つけて修正する方法について説明します。
title: Microsoft Edge DevTools での JavaScript のデバッグの開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e146c6708f097b1ea8dc82f08be58f5aa5e52d1f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398442"
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
# <a name="get-started-with-debugging-javascript-in-microsoft-edge-devtools"></a><span data-ttu-id="99108-104">Microsoft Edge DevTools での JavaScript のデバッグの開始</span><span class="sxs-lookup"><span data-stu-id="99108-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="99108-105">この記事では、DevTools で JavaScript の問題をデバッグする基本的なワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="99108-105">This article teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <a name="step-1-reproduce-the-bug"></a><span data-ttu-id="99108-106">手順 1: バグを再現する</span><span class="sxs-lookup"><span data-stu-id="99108-106">Step 1: Reproduce the bug</span></span>  

<span data-ttu-id="99108-107">一貫してバグを再現する一連のアクションを見つけることは、常にデバッグの最初のステップです。</span><span class="sxs-lookup"><span data-stu-id="99108-107">Finding a series of actions that consistently reproduce a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="99108-108">[ **デモを開く] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="99108-108">Choose **Open Demo**.</span></span>  <span data-ttu-id="99108-109">`Control`\(Windows,Linux\) または \(macOS\) を保持し、新しいブラウザー タブで `Command` デモを開きます。</span><span class="sxs-lookup"><span data-stu-id="99108-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and open the demo in a new browser tab.</span></span>  
    
    [<span data-ttu-id="99108-110">Open Demo</span><span class="sxs-lookup"><span data-stu-id="99108-110">Open Demo</span></span>][OpenDebugJSDemo]  
    
1.  <span data-ttu-id="99108-111">[ `5` 数値 **1] テキスト ボックスに** 入力します。</span><span class="sxs-lookup"><span data-stu-id="99108-111">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="99108-112">[ `1` 数値 **2] テキスト ボックスに** 入力します。</span><span class="sxs-lookup"><span data-stu-id="99108-112">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="99108-113">[ **番号 1 の追加] と [番号 2] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="99108-113">Choose **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="99108-114">ボタンの下のラベルには、 と表示されます `5 + 1 = 51` 。</span><span class="sxs-lookup"><span data-stu-id="99108-114">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="99108-115">結果は 、 である必要があります `6` 。</span><span class="sxs-lookup"><span data-stu-id="99108-115">The result should be `6`.</span></span>  <span data-ttu-id="99108-116">次に、バグである追加エラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="99108-116">Next, fix the addition error that is the bug.</span></span>  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 の結果は 51 になりますが、6 である必要があります" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` <span data-ttu-id="99108-118">の結果 `51` が表示されますが、次の値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99108-118">results in `51`, but should be</span></span> `6`  
    :::image-end:::  
    
## <a name="step-2-get-familiar-with-the-sources-tool-ui"></a><span data-ttu-id="99108-119">手順 2: ソース ツール UI について理解する</span><span class="sxs-lookup"><span data-stu-id="99108-119">Step 2: Get familiar with the Sources tool UI</span></span>  

<span data-ttu-id="99108-120">DevTools には、タスクごとにさまざまなツールが提供されています。</span><span class="sxs-lookup"><span data-stu-id="99108-120">DevTools provides many different tools for different tasks.</span></span>  <span data-ttu-id="99108-121">さまざまなタスクには、CSS の変更、ページ読み込みパフォーマンスのプロファイリング、ネットワーク要求の監視が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99108-121">Different tasks include changing CSS, profiling page-load performance, and monitoring network requests.</span></span>  <span data-ttu-id="99108-122">ソース **ツールは** 、JavaScript をデバッグする場所です。</span><span class="sxs-lookup"><span data-stu-id="99108-122">The **Sources** tool is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="99108-123">DevTools**でコンソール**ツールを開く場合は `Control` + `Shift` + `J` 、[\(Windows,Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-123">To open the **Console** tool in DevTools, select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="コンソール ツール" lightbox="../media/javascript-console-empty.msft.png":::
       <span data-ttu-id="99108-125">コンソール**ツール**</span><span class="sxs-lookup"><span data-stu-id="99108-125">The **Console** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="99108-126">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="99108-126">Choose the **Sources** tool.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="ソース ツール" lightbox="../media/javascript-sources-sections.msft.png":::
       <span data-ttu-id="99108-128">ソース**ツール**</span><span class="sxs-lookup"><span data-stu-id="99108-128">The **Sources** tool</span></span>  
    :::image-end:::  
    
<span data-ttu-id="99108-129">ソース **ツール UI には** 3 つのパーツがあります。</span><span class="sxs-lookup"><span data-stu-id="99108-129">The **Sources** tool UI has three parts.</span></span>  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="ソース ツール UI の 3 つの部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   <span data-ttu-id="99108-131">ソース ツール UI の 3**つの部分**</span><span class="sxs-lookup"><span data-stu-id="99108-131">The 3 parts of the **Sources** tool UI</span></span>  
:::image-end:::  

1.  <span data-ttu-id="99108-132">[ **ファイル ナビゲーター]** パネル \(前の図のセクション 1\)。</span><span class="sxs-lookup"><span data-stu-id="99108-132">The **File Navigator** panel \(Section 1 in the previous figure\).</span></span>  <span data-ttu-id="99108-133">Web ページが要求するファイルは、ここに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="99108-133">Every file that the webpage requests is listed here.</span></span>  
1.  <span data-ttu-id="99108-134">[ **コード エディター]** パネル \(前の図のセクション 2\)。</span><span class="sxs-lookup"><span data-stu-id="99108-134">The **Code Editor** panel \(Section 2 in the previous figure\).</span></span>  <span data-ttu-id="99108-135">[ファイル ナビゲーター] ウィンドウで **ファイルを選択** すると、そのファイルの内容がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="99108-135">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span></span>  
1.  <span data-ttu-id="99108-136">JavaScript **デバッグ パネル** \(前の図のセクション 3\)。</span><span class="sxs-lookup"><span data-stu-id="99108-136">The **JavaScript Debugging** panel \(Section 3 in the previous figure\).</span></span>  <span data-ttu-id="99108-137">Web ページの JavaScript を検査するためのさまざまなツール。</span><span class="sxs-lookup"><span data-stu-id="99108-137">Various tools for inspecting the JavaScript for the webpage.</span></span>  <span data-ttu-id="99108-138">DevTools ウィンドウが広い場合、このウィンドウはコード エディター ウィンドウの右側 **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="99108-138">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span></span>  
    
## <a name="step-3-pause-the-code-with-a-breakpoint"></a><span data-ttu-id="99108-139">手順 3: ブレークポイントでコードを一時停止する</span><span class="sxs-lookup"><span data-stu-id="99108-139">Step 3: Pause the code with a breakpoint</span></span>  

<span data-ttu-id="99108-140">この種の問題をデバッグする一般的な方法は、コードに複数のステートメントを挿入し、スクリプトの実行時に値 `console.log()` を調べたい方法です。</span><span class="sxs-lookup"><span data-stu-id="99108-140">A common method for debugging this type of problem is to insert several `console.log()` statements into the code and then to inspect values as the script runs.</span></span>  <span data-ttu-id="99108-141">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="99108-141">For example:</span></span>  

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

<span data-ttu-id="99108-142">メソッド `console.log()` によってジョブが完了する可能性がありますが、 **ブレークポイントを使用** すると、実行速度が向上します。</span><span class="sxs-lookup"><span data-stu-id="99108-142">The `console.log()` method may get the job done, but **breakpoints** get it done faster.</span></span>  <span data-ttu-id="99108-143">ブレークポイントを使用すると、実行時の途中でコードを一時停止し、その時点ですべての値を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="99108-143">A breakpoint allows you to pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="99108-144">ブレークポイントには、メソッドに対して次のような利点 `console.log()` があります。</span><span class="sxs-lookup"><span data-stu-id="99108-144">Breakpoints have the following advantages over the `console.log()` method.</span></span>  

*   <span data-ttu-id="99108-145">を使用して、ソース コードを手動で開き、関連するコードを検索し、ステートメントを挿入し、Web ページを更新してコンソールにメッセージを `console.log()` `console.log()` 表示する必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="99108-145">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then refresh the webpage to display the messages in the **Console**.</span></span>  <span data-ttu-id="99108-146">ブレークポイントを使用すると、コードの構造を知らなくても、関連するコードを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="99108-146">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="99108-147">ステートメントでは `console.log()` 、検査する各値を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99108-147">In your `console.log()` statements, you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="99108-148">ブレークポイントを使用すると、DevTools は、その時点ですべての変数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="99108-148">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="99108-149">コードに影響を与える変数が非表示で難読化されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="99108-149">Sometimes variables that affect your code are hidden and obfuscated.</span></span>  
    
<span data-ttu-id="99108-150">つまり、ブレークポイントは、メソッドよりも速くバグを見つけて修正するのに役立 `console.log()` ちます。</span><span class="sxs-lookup"><span data-stu-id="99108-150">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="99108-151">一歩下がってアプリの動作を考える場合は、[番号 1 の追加] ボタンと [番号 `5 + 1 = 51` `click` **2]** ボタンに関連付けられたイベント リスナーで、正しくない合計 \( \) が計算されるという教育的な推測を行う場合があります。</span><span class="sxs-lookup"><span data-stu-id="99108-151">If you step back and think about how the app works, you may make an educated guess that the incorrect sum \(`5 + 1 = 51`\) is computed in the `click` event listener associated with the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="99108-152">そのため、リスナーが実行される時間の周りにコードを一時停止する `click` 必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99108-152">So, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="99108-153">**イベント リスナー ブレークポイントを使用** すると、次の操作を正確に実行できます。</span><span class="sxs-lookup"><span data-stu-id="99108-153">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="99108-154">**[JavaScript デバッグ] ウィンドウで**、[イベント リスナー ブレークポイント] を**選択してセクション**を展開します。</span><span class="sxs-lookup"><span data-stu-id="99108-154">In the **JavaScript Debugging** pane, choose **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="99108-155">DevTools は、アニメーションやクリップボードなどの展開可能なイベント カテゴリの **一覧を** 表示 **します**。</span><span class="sxs-lookup"><span data-stu-id="99108-155">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="99108-156">[マウス] イベント**カテゴリの横**にある [展開]\( \*\*\*\* ![ [展開] アイコン ][ImageExpandIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-156">Next to the **Mouse** event category, choose **Expand** \(![Expand icon][ImageExpandIcon]\).</span></span>  <span data-ttu-id="99108-157">DevTools は、クリックやマウスダウンなどのマウス イベント**の一覧を\*\*\*\*表示します**。</span><span class="sxs-lookup"><span data-stu-id="99108-157">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="99108-158">各イベントには、その横にチェック ボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="99108-158">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="99108-159">[] をクリックするには、次のチェック ボックス **をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="99108-159">Choose the checkbox next to **click**.</span></span>  <span data-ttu-id="99108-160">DevTools は、イベント リスナーの実行時に自動的に `click` 一時停止する設定が行われます。</span><span class="sxs-lookup"><span data-stu-id="99108-160">DevTools is now set up to automatically pause when any `click` event listener runs.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="[次へ] をクリックするチェック ボックスをオンにします。" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       <span data-ttu-id="99108-162">[次へ] をクリックするチェック ボックスを **オンにします。**</span><span class="sxs-lookup"><span data-stu-id="99108-162">Choose the checkbox next to **click**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="99108-163">デモに戻り、[番号 1 の追加] と **[番号 2] を再度選択** します。</span><span class="sxs-lookup"><span data-stu-id="99108-163">Back on the demo, choose **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="99108-164">DevTools はデモを一時停止し、ソース ツールでコード行 **を強調表示** します。</span><span class="sxs-lookup"><span data-stu-id="99108-164">DevTools pauses the demo and highlights a line of code in the **Sources** tool.</span></span>  <span data-ttu-id="99108-165">DevTools は 16 行目で一時停止する必要があります `get-started.js` 。</span><span class="sxs-lookup"><span data-stu-id="99108-165">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="99108-166">別のコード行で一時停止する場合は、\*\*\*\* 正しい行で一時停止するまで 、[スクリプト実行の再開]\( Resume ![ Script Execution ][ImageResumeIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-166">If you pause on a different line of code, choose **Resume Script Execution** \(![Resume Script Execution][ImageResumeIcon]\) until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="99108-167">別の行で一時停止した場合は、訪問する Web ページごとにイベント リスナーを登録するブラウザー拡張機能 `click` があります。</span><span class="sxs-lookup"><span data-stu-id="99108-167">If you paused on a different line, you have a browser extension that registers a `click` event listener on every webpage that you visit.</span></span>  <span data-ttu-id="99108-168">拡張機能のリスナーで `click` 一時停止しています。</span><span class="sxs-lookup"><span data-stu-id="99108-168">You are paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="99108-169">InPrivate モードを使用して\*\*\*\*、すべての拡張機能を無効にするプライベートで参照する場合は、必要なコード行を毎回一時停止する場合があります。</span><span class="sxs-lookup"><span data-stu-id="99108-169">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="99108-170">**イベント リスナーのブレークポイント** は、DevTools で使用できる多くの種類のブレークポイントの 1 つにすら異なっています。</span><span class="sxs-lookup"><span data-stu-id="99108-170">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="99108-171">さまざまな種類を記憶して、さまざまなシナリオを可能な限り迅速にデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="99108-171">Memorize all the different types to help you debug different scenarios as quickly as possible.</span></span>  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <a name="step-4-step-through-the-code"></a><span data-ttu-id="99108-172">手順 4: コードをステップ実行する</span><span class="sxs-lookup"><span data-stu-id="99108-172">Step 4: Step through the code</span></span>  

<span data-ttu-id="99108-173">バグの一般的な原因の 1 つは、スクリプトが正しい順序で実行される場合です。</span><span class="sxs-lookup"><span data-stu-id="99108-173">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="99108-174">コードをステップ実行すると、コードのランタイムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="99108-174">Stepping through your code allows you to walk through the runtime of your code.</span></span>  <span data-ttu-id="99108-175">一度に 1 行を実行して、コードが予想とは異なる順序で実行されている場所を正確に把握するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="99108-175">You walk through one line at a time to help you figure out exactly where your code is running in a different order than you expect.</span></span>  <span data-ttu-id="99108-176">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="99108-176">Try it now:</span></span>  

1.  <span data-ttu-id="99108-177">[ **次の関数呼び出し** \( ![ Step over next function call \) を選択 ][ImageOverIcon] します。</span><span class="sxs-lookup"><span data-stu-id="99108-177">Choose **Step over next function call** \(![Step over next function call][ImageOverIcon]\).</span></span>  <span data-ttu-id="99108-178">DevTools は、ステップ インせずに次のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="99108-178">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="99108-179">DevTools は数行のコードをスキップします。</span><span class="sxs-lookup"><span data-stu-id="99108-179">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="99108-180">これは、false と評価されるので、ステートメントのコード ブロックが `inputsAreEmpty()` `if` 実行されないためです。</span><span class="sxs-lookup"><span data-stu-id="99108-180">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  
    
1.  <span data-ttu-id="99108-181">DevTools **の Sources** ツールで、[Step **to next** function call \( Step to next function call \) を選択して、関数のランタイムを一度に 1 行ステップ実行 ![ ][ImageIntoIcon] `updateLabel()` します。</span><span class="sxs-lookup"><span data-stu-id="99108-181">On the **Sources** tool of DevTools, choose **Step into next function call** \(![Step into next function call][ImageIntoIcon]\) to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  
    
<span data-ttu-id="99108-182">一度に 1 行を確認する方法は、コードをステップ実行する基本的な考え方です。</span><span class="sxs-lookup"><span data-stu-id="99108-182">Reviewing one line at a time is the basic idea of stepping through code.</span></span>  <span data-ttu-id="99108-183">でコードを確認すると `get-started.js` 、バグは関数のどこかにある可能性 `updateLabel()` があります。</span><span class="sxs-lookup"><span data-stu-id="99108-183">If you review the code in `get-started.js`, the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="99108-184">コードのすべての行をステップ実行するのではなく、別の種類のブレークポイントを使用して、バグの可能性がある場所に近いコードを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="99108-184">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <a name="step-5-set-a-line-of-code-breakpoint"></a><span data-ttu-id="99108-185">手順 5: コード行ブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="99108-185">Step 5: Set a line-of-code breakpoint</span></span>  

<span data-ttu-id="99108-186">コード行ブレークポイントは、最も一般的な種類のブレークポイントです。</span><span class="sxs-lookup"><span data-stu-id="99108-186">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="99108-187">一時停止する特定のコード行にアクセスする場合は、コード行ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="99108-187">When you get to the specific line of code you want to pause, use a line-of-code breakpoint.</span></span>  

1.  <span data-ttu-id="99108-188">次のコードの最後の行を確認します `updateLabel()` 。</span><span class="sxs-lookup"><span data-stu-id="99108-188">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="99108-189">左側には、この特定のコード行の番号が **34 と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="99108-189">On the left, the number of this particular line of code is displayed as **34**.</span></span>  <span data-ttu-id="99108-190">行 **34 を選択します**。</span><span class="sxs-lookup"><span data-stu-id="99108-190">Choose line **34**.</span></span>  <span data-ttu-id="99108-191">DevTools は 34 の左側に赤い **アイコンを表示します**。</span><span class="sxs-lookup"><span data-stu-id="99108-191">DevTools displays a red icon to the left of **34**.</span></span>  <span data-ttu-id="99108-192">赤いアイコンは、コード行ブレークポイントがこの行に含まれるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="99108-192">The red icon indicates that a line-of-code breakpoint is on this line.</span></span>  <span data-ttu-id="99108-193">DevTools は、このコード行を実行する前に常に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="99108-193">DevTools always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="99108-194">[スクリプト **実行の再開** \( ![ スクリプト実行の再開 ][ImageResumeIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-194">Choose **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  <span data-ttu-id="99108-195">スクリプトは、33 行目に達するまで実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="99108-195">The script continues to run until it reaches line 33.</span></span>  <span data-ttu-id="99108-196">31 行目、32 行目、および 33 行目では、DevTools は、各行の 、、およびセミコロンの右側の値 `addend1` `addend2` `sum` を出力します。</span><span class="sxs-lookup"><span data-stu-id="99108-196">On lines 31, 32, and 33, DevTools prints the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools が行 34 のコード行ブレークポイントで一時停止する" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       <span data-ttu-id="99108-198">DevTools が行 34 のコード行ブレークポイントで一時停止する</span><span class="sxs-lookup"><span data-stu-id="99108-198">DevTools pauses on the line-of-code breakpoint on line 34</span></span>  
    :::image-end:::  
    
## <a name="step-6-check-variable-values"></a><span data-ttu-id="99108-199">手順 6: 変数の値を確認する</span><span class="sxs-lookup"><span data-stu-id="99108-199">Step 6: Check variable values</span></span>  

<span data-ttu-id="99108-200">の値、 `addend1` および `addend2` 疑わしい `sum` 外観。</span><span class="sxs-lookup"><span data-stu-id="99108-200">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="99108-201">値は引用符で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="99108-201">The values are wrapped in quotes.</span></span>  <span data-ttu-id="99108-202">引用符は、値が文字列を意味します。これはバグの原因を説明する良い仮説です。</span><span class="sxs-lookup"><span data-stu-id="99108-202">The quotations mean that the value is a string, which is a good hypothesis to explain the cause of the bug.</span></span>  <span data-ttu-id="99108-203">状況に関する詳細を収集します。</span><span class="sxs-lookup"><span data-stu-id="99108-203">Gather more information about the situation.</span></span>  <span data-ttu-id="99108-204">DevTools には、変数値を調べる多くのツールが提供されています。</span><span class="sxs-lookup"><span data-stu-id="99108-204">DevTools provides many tools for examining variable values.</span></span>  

### <a name="method-1-the-scope-panel"></a><span data-ttu-id="99108-205">方法 1: [スコープ] パネル</span><span class="sxs-lookup"><span data-stu-id="99108-205">Method 1: The Scope panel</span></span>  

<span data-ttu-id="99108-206">コード行を一時停止すると、[スコープ]\*\*\*\* パネルに、現在定義されているローカル変数とグローバル変数と、各変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="99108-206">If you pause on a line of code, the **Scope** panel displays the local and global variables that are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="99108-207">また、必要に応じてクロージャ変数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="99108-207">It also displays closure variables, as applicable.</span></span>  <span data-ttu-id="99108-208">変数値をダブルクリックして編集します。</span><span class="sxs-lookup"><span data-stu-id="99108-208">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="99108-209">コード行を一時停止しない場合、[スコープ] **パネルは空** です。</span><span class="sxs-lookup"><span data-stu-id="99108-209">If you don't pause on a line of code, the **Scope** panel is empty.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="[スコープ] ウィンドウ" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   <span data-ttu-id="99108-211">[ **スコープ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="99108-211">The **Scope** pane</span></span>  
:::image-end:::  

### <a name="method-2-watch-expressions"></a><span data-ttu-id="99108-212">方法 2: ウォッチ式</span><span class="sxs-lookup"><span data-stu-id="99108-212">Method 2: Watch Expressions</span></span>  

<span data-ttu-id="99108-213">[ **ウォッチ式]** パネルでは、時間の間に変数の値を監視できます。</span><span class="sxs-lookup"><span data-stu-id="99108-213">The **Watch Expressions** panel lets you monitor the values of variables over time.</span></span>  <span data-ttu-id="99108-214">名前が示すように、 **ウォッチ式** は変数に限定されるのではありません。</span><span class="sxs-lookup"><span data-stu-id="99108-214">As the name implies, **Watch Expressions** aren't limited to variables.</span></span>  <span data-ttu-id="99108-215">任意の有効な JavaScript 式をウォッチ式に **格納できます**。</span><span class="sxs-lookup"><span data-stu-id="99108-215">You may store any valid JavaScript expression in a **Watch Expression**.</span></span>  <span data-ttu-id="99108-216">今すぐ試してみてください。</span><span class="sxs-lookup"><span data-stu-id="99108-216">Try it now.</span></span>  

1.  <span data-ttu-id="99108-217">[ウォッチ] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="99108-217">Choose the **Watch** panel.</span></span>  
1.  <span data-ttu-id="99108-218">[ **式の追加** \( ![ Add Expression ][ImageAddIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-218">Choose **Add Expression** \(![Add Expression][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="99108-219">「`typeof sum`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="99108-219">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="99108-220">`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-220">Select `Enter`.</span></span>  <span data-ttu-id="99108-221">DevTools が表示されます `typeof sum: "string"` 。</span><span class="sxs-lookup"><span data-stu-id="99108-221">DevTools shows `typeof sum: "string"`.</span></span>  <span data-ttu-id="99108-222">コロンの右側の値は、ウォッチ式の結果です。</span><span class="sxs-lookup"><span data-stu-id="99108-222">The value to the right of the colon is the result of your Watch Expression.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="99108-223">次の **図の [ウォッチ式** ] ウィンドウ \(右下\) に、[ `typeof sum` ウォッチ式] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="99108-223">In the **Watch Expression** pane \(bottom-right\) in the following figure, the `typeof sum` Watch Expression is displayed.</span></span>  <span data-ttu-id="99108-224">DevTools ウィンドウが大きい場合は、[ **ウォッチ式** ] ウィンドウが [イベント リスナー ブレークポイント] ウィンドウの右側に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="99108-224">If your DevTools window is large, the **Watch Expression** pane is on the right above the **Event Listener Breakpoints** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="[ウォッチ式] パネル" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   <span data-ttu-id="99108-226">[ **ウォッチ式]** パネル</span><span class="sxs-lookup"><span data-stu-id="99108-226">The **Watch Expression** panel</span></span>  
:::image-end:::  

<span data-ttu-id="99108-227">疑わしい場合 `sum` は、数値である必要がある場合に文字列として評価されます。</span><span class="sxs-lookup"><span data-stu-id="99108-227">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="99108-228">これで、確認された値の種類がバグの原因です。</span><span class="sxs-lookup"><span data-stu-id="99108-228">You now confirmed value type is the cause of the bug.</span></span>  

### <a name="method-3-the-console"></a><span data-ttu-id="99108-229">方法 3: コンソール</span><span class="sxs-lookup"><span data-stu-id="99108-229">Method 3: The Console</span></span>  

<span data-ttu-id="99108-230">コンソール **を** 使用すると、メッセージを表示できます。また、任意の JavaScript ステートメントを評価 `console.log()` するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="99108-230">The **Console** allows you to view `console.log()` messages and you may also use it to evaluate arbitrary JavaScript statements.</span></span>  <span data-ttu-id="99108-231">デバッグの場合は、コンソール **を使用して** 、潜在的な修正プログラムのバグをテストできます。</span><span class="sxs-lookup"><span data-stu-id="99108-231">For debugging, you may use the **Console** to test potential fixes for bugs.</span></span>  <span data-ttu-id="99108-232">今すぐ試してみてください。</span><span class="sxs-lookup"><span data-stu-id="99108-232">Try it now.</span></span>  

1.  <span data-ttu-id="99108-233">コンソール ツール **が閉** じている場合は、選択 `Escape` して開きます。</span><span class="sxs-lookup"><span data-stu-id="99108-233">If the **Console** tool is closed, select `Escape` to open it.</span></span>  <span data-ttu-id="99108-234">コンソール **ツール** は、DevTools ウィンドウの下部パネルで開きます。</span><span class="sxs-lookup"><span data-stu-id="99108-234">The **Console** tool opens in the lower panel of the DevTools window.</span></span>  
1.  <span data-ttu-id="99108-235">コンソールで **、と**入力します `parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="99108-235">In the **Console**, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="99108-236">ツールのステートメントは、スコープ内のコード行 `addend1` で `addend2` 一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="99108-236">The statement the tool is paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="99108-237">`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-237">Select `Enter`.</span></span>  <span data-ttu-id="99108-238">DevTools はステートメントと印刷を評価します。これは、デモで生成 `6` される結果です。</span><span class="sxs-lookup"><span data-stu-id="99108-238">DevTools evaluates the statement and prints `6`, which is the result you expect the demo to produce.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="parseInt(addend1) + parseInt(addend2) を評価した後のコンソール ツール" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       <span data-ttu-id="99108-240">評価 **後** のコンソール ツール</span><span class="sxs-lookup"><span data-stu-id="99108-240">The **Console** tool, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <a name="step-7-apply-a-fix"></a><span data-ttu-id="99108-241">手順 7: 修正プログラムを適用する</span><span class="sxs-lookup"><span data-stu-id="99108-241">Step 7: Apply a fix</span></span>  

<span data-ttu-id="99108-242">バグの修正プログラムを見つけた場合は、コードを編集し、デモを再実行して修正プログラムを試してください。</span><span class="sxs-lookup"><span data-stu-id="99108-242">If you find a fix for the bug, try out your fix by editing the code and rerunning the demo.</span></span>  <span data-ttu-id="99108-243">JavaScript コードは、DevTools UI 内で直接編集し、修正プログラムを適用できます。</span><span class="sxs-lookup"><span data-stu-id="99108-243">You may edit JavaScript code directly within the DevTools UI and apply the fix.</span></span>  <span data-ttu-id="99108-244">今すぐ試してみてください。</span><span class="sxs-lookup"><span data-stu-id="99108-244">Try it now.</span></span>  

1.  <span data-ttu-id="99108-245">[スクリプト **実行の再開** \( ![ スクリプト実行の再開 ][ImageResumeIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-245">Choose **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  
1.  <span data-ttu-id="99108-246">コード エディター **で、** 行 32 を 、 `var sum = addend1 + addend2` に置き換えます `var sum = parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="99108-246">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="99108-247">`Control` + `S` 変更を保存するには、\(Windows、Linux\) `Command` + `S` または \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-247">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="99108-248">[ **ブレークポイントを非アクティブ化** する]\( ![ [ブレークポイントを非アクティブ化 ][ImageDeactivateIcon] する]\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99108-248">Choose **Deactivate breakpoints** \(![Deactivate breakpoints][ImageDeactivateIcon]\).</span></span>  <span data-ttu-id="99108-249">オプションがアクティブな状態を示すために青に変更されます。</span><span class="sxs-lookup"><span data-stu-id="99108-249">It changes blue to indicate the option is active.</span></span>  <span data-ttu-id="99108-250">[ **ブレークポイントの非アクティブ化** ] が設定されている間、DevTools は設定したブレークポイントを無視します。</span><span class="sxs-lookup"><span data-stu-id="99108-250">While **Deactivate breakpoints** is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="99108-251">異なる値でデモを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="99108-251">Try out the demo with different values.</span></span>  <span data-ttu-id="99108-252">デモで正しく計算されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="99108-252">The demo now calculates correctly.</span></span>  
    
> [!CAUTION]
> <span data-ttu-id="99108-253">このワークフローは、ブラウザーで実行されているコードにのみ修正プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="99108-253">This workflow only applies a fix to the code that is running in your browser.</span></span>  <span data-ttu-id="99108-254">Web ページにアクセスするすべてのユーザーのコードは修正されない。</span><span class="sxs-lookup"><span data-stu-id="99108-254">It does not fix the code for all users that visit your webpage.</span></span>  <span data-ttu-id="99108-255">これを行うには、サーバー上のコードを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99108-255">To do that, you need to fix the code that is on your servers.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="99108-256">次のステップ</span><span class="sxs-lookup"><span data-stu-id="99108-256">Next steps</span></span>  

<span data-ttu-id="99108-257">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="99108-257">Congratulations!</span></span>  <span data-ttu-id="99108-258">JavaScript のデバッグ時に Microsoft Edge DevTools を利用する方法がわかっています。</span><span class="sxs-lookup"><span data-stu-id="99108-258">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="99108-259">この記事で学んだツールとメソッドは、数え切れないほどの時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="99108-259">The tools and methods you learned in this article may save you countless hours.</span></span>  

<span data-ttu-id="99108-260">この記事では、ブレークポイントを設定する 2 つの方法のみを教えています。</span><span class="sxs-lookup"><span data-stu-id="99108-260">This article only taught you two ways to set breakpoints.</span></span>  <span data-ttu-id="99108-261">DevTools は、次の設定を含む他の多くの方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="99108-261">DevTools offers many other ways including the following settings.</span></span>  

*   <span data-ttu-id="99108-262">指定した条件が true の場合にのみトリガーされる条件付きブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="99108-262">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="99108-263">キャッチまたはキャッチされていない例外のブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="99108-263">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="99108-264">要求された URL が指定した部分文字列と一致するときにトリガーされる XHR ブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="99108-264">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  
    
<span data-ttu-id="99108-265">各種類を使用する場合と方法の詳細については、「ブレークポイントを使用してコードを一時停止 [する」に移動します][DevtoolsJavscriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="99108-265">For more information about when and how to use each type, navigate to [Pause Your Code With Breakpoints][DevtoolsJavscriptBreakpoints].</span></span>  

<span data-ttu-id="99108-266">この記事では、いくつかのコード ステップコントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="99108-266">A couple of code stepping controls aren't explained in this article.</span></span>  <span data-ttu-id="99108-267">詳細については、「Step [over line of code」に移動します][DevtoolsJavascriptReferenceStepThroughCode]。</span><span class="sxs-lookup"><span data-stu-id="99108-267">For more information, navigate to [Step over line of code][DevtoolsJavascriptReferenceStepThroughCode].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="99108-268">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="99108-268">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: ../media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageIntoIcon]: ../media/step-into-icon.msft.png  
[ImageOverIcon]: ../media/step-over-icon.msft.png  
[ImageResumeIcon]: ../media/resume-script-run-icon.msft.png  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "Microsoft Edge DevTools アプリケーションでブレークポイントを使用してコードを一時停止する|Microsoft Docs"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "コードのステップスルー - JavaScript デバッグリファレンス |Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "Open Demo |Glitch"  

> [!NOTE]
> <span data-ttu-id="99108-272">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="99108-272">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="99108-273">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="99108-273">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="99108-275">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="99108-275">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
