---
description: JavaScript のバグを見つけてMicrosoft Edge DevTools を使用する方法について説明します。
title: DevTools での JavaScript のデバッグMicrosoft Edgeする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 90a979cebcb74a118cb1d8ce88d48c7ac64c7a6d
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564092"
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
# <a name="get-started-with-debugging-javascript-in-microsoft-edge-devtools"></a><span data-ttu-id="b3347-104">DevTools での JavaScript のデバッグMicrosoft Edgeする</span><span class="sxs-lookup"><span data-stu-id="b3347-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="b3347-105">この記事では、DevTools で JavaScript の問題をデバッグする基本的なワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3347-105">This article teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <a name="step-1-reproduce-the-bug"></a><span data-ttu-id="b3347-106">手順 1: バグを再現する</span><span class="sxs-lookup"><span data-stu-id="b3347-106">Step 1: Reproduce the bug</span></span>  

<span data-ttu-id="b3347-107">一貫してバグを再現する一連のアクションを見つけることは、常にデバッグの最初のステップです。</span><span class="sxs-lookup"><span data-stu-id="b3347-107">Finding a series of actions that consistently reproduce a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="b3347-108">次の [**デモを開く**] リンクを選択し、新しいタブで Web ページを開きます。 新しいタブでデモを開く場合は `Ctrl` 、\(Windows、 Linux\) または `Command` \(macOS\) を選択し、[デモを開く] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3347-108">Choose the following **Open Demo** link and open the webpage in a new tab.  To open the demo in a new tab, select and hold `Ctrl` \(Windows, Linux\) or `Command` \(macOS\), and then choose **Open Demo**.</span></span>  
    
    [<span data-ttu-id="b3347-109">Open Demo</span><span class="sxs-lookup"><span data-stu-id="b3347-109">Open Demo</span></span>][OpenDebugJSDemo]  
    
1.  <span data-ttu-id="b3347-110">[ `5` 数値 **1] テキスト ボックスに** 入力します。</span><span class="sxs-lookup"><span data-stu-id="b3347-110">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="b3347-111">[ `1` 数値 **2] テキスト ボックスに** 入力します。</span><span class="sxs-lookup"><span data-stu-id="b3347-111">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="b3347-112">[ **番号 1 の追加] と [番号 2] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3347-112">Choose **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="b3347-113">ボタンの下のラベルには、 と表示されます `5 + 1 = 51` 。</span><span class="sxs-lookup"><span data-stu-id="b3347-113">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="b3347-114">結果は 、 である必要があります `6` 。</span><span class="sxs-lookup"><span data-stu-id="b3347-114">The result should be `6`.</span></span>  <span data-ttu-id="b3347-115">次に、バグである追加エラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="b3347-115">Next, fix the addition error that is the bug.</span></span>  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="5 + 1 の結果は 51 になりますが、6 である必要があります" lightbox="../media/javascript-js-demo-bad.msft.png":::
       `5 + 1` <span data-ttu-id="b3347-117">の結果 `51` が表示されますが、次の値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-117">results in `51`, but should be</span></span> `6`  
    :::image-end:::  
    
## <a name="step-2-get-familiar-with-the-sources-tool-ui"></a><span data-ttu-id="b3347-118">手順 2: ソース ツール UI について理解する</span><span class="sxs-lookup"><span data-stu-id="b3347-118">Step 2: Get familiar with the Sources tool UI</span></span>  

<span data-ttu-id="b3347-119">DevTools には、タスクごとにさまざまなツールが提供されています。</span><span class="sxs-lookup"><span data-stu-id="b3347-119">DevTools provides many different tools for different tasks.</span></span>  <span data-ttu-id="b3347-120">さまざまなタスクには、CSS の変更、ページ読み込みパフォーマンスのプロファイリング、ネットワーク要求の監視が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3347-120">Different tasks include changing CSS, profiling page-load performance, and monitoring network requests.</span></span>  <span data-ttu-id="b3347-121">ソース **ツールは** 、JavaScript をデバッグする場所です。</span><span class="sxs-lookup"><span data-stu-id="b3347-121">The **Sources** tool is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="b3347-122">DevTools で**コンソール**ツールを開く場合は `Control` + `Shift` + `J` 、\(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-122">To open the **Console** tool in DevTools, select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="コンソール ツール" lightbox="../media/javascript-console-empty.msft.png":::
       <span data-ttu-id="b3347-124">コンソール**ツール**</span><span class="sxs-lookup"><span data-stu-id="b3347-124">The **Console** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b3347-125">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="b3347-125">Choose the **Sources** tool.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="ソース ツール" lightbox="../media/javascript-sources-sections.msft.png":::
       <span data-ttu-id="b3347-127">ソース**ツール**</span><span class="sxs-lookup"><span data-stu-id="b3347-127">The **Sources** tool</span></span>  
    :::image-end:::  
    
<span data-ttu-id="b3347-128">ソース **ツール UI には** 3 つのパーツがあります。</span><span class="sxs-lookup"><span data-stu-id="b3347-128">The **Sources** tool UI has three parts.</span></span>  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="ソース ツール UI の 3 つの部分" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   <span data-ttu-id="b3347-130">ソース ツール UI の 3**つの部分**</span><span class="sxs-lookup"><span data-stu-id="b3347-130">The 3 parts of the **Sources** tool UI</span></span>  
:::image-end:::  

1.  <span data-ttu-id="b3347-131">ナビゲーター **ウィンドウ** \(前の図のセクション 1\)。</span><span class="sxs-lookup"><span data-stu-id="b3347-131">The **Navigator** pane \(Section 1 in the previous figure\).</span></span>  <span data-ttu-id="b3347-132">Web ページが要求するファイルは、ここに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-132">Every file that the webpage requests is listed here.</span></span>  
1.  <span data-ttu-id="b3347-133">[ **エディター]** ウィンドウ \(前の図のセクション 2\)。</span><span class="sxs-lookup"><span data-stu-id="b3347-133">The **Editor** pane \(Section 2 in the previous figure\).</span></span>  <span data-ttu-id="b3347-134">[ナビゲーター] ウィンドウでファイル **を選択** すると、このウィンドウにファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-134">After you choose a file in the **Navigator** pane, this pane displays the contents of the file.</span></span>  
1.  <span data-ttu-id="b3347-135">デバッガー **ウィンドウ** \(前の図のセクション 3\)。</span><span class="sxs-lookup"><span data-stu-id="b3347-135">The **Debugger** pane \(Section 3 in the previous figure\).</span></span>  <span data-ttu-id="b3347-136">このウィンドウには、Web ページの JavaScript を検査するためのツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-136">This pane provides tools for inspecting the JavaScript for the webpage.</span></span>  <span data-ttu-id="b3347-137">DevTools ウィンドウが広い場合、このウィンドウはエディター ウィンドウの右側に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-137">If your DevTools window is wide, this pane is displayed to the right of the **Editor** pane.</span></span>  
    
## <a name="step-3-pause-the-code-with-a-breakpoint"></a><span data-ttu-id="b3347-138">手順 3: ブレークポイントでコードを一時停止する</span><span class="sxs-lookup"><span data-stu-id="b3347-138">Step 3: Pause the code with a breakpoint</span></span>  

<span data-ttu-id="b3347-139">この種の問題をデバッグする一般的な方法は、コードに複数のステートメントを挿入し、スクリプトの実行時に値 `console.log()` を調べたい方法です。</span><span class="sxs-lookup"><span data-stu-id="b3347-139">A common method for debugging this type of problem is to insert several `console.log()` statements into the code and then to inspect values as the script runs.</span></span>  <span data-ttu-id="b3347-140">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b3347-140">For example:</span></span>  

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

<span data-ttu-id="b3347-141">メソッド `console.log()` によってジョブが完了する可能性がありますが、 **ブレークポイントを使用** すると、実行速度が向上します。</span><span class="sxs-lookup"><span data-stu-id="b3347-141">The `console.log()` method may get the job done, but **breakpoints** get it done faster.</span></span>  <span data-ttu-id="b3347-142">ブレークポイントを使用すると、実行時の途中でコードを一時停止し、その時点ですべての値を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="b3347-142">A breakpoint allows you to pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="b3347-143">ブレークポイントには、メソッドに対して次のような利点 `console.log()` があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-143">Breakpoints have the following advantages over the `console.log()` method.</span></span>  

*   <span data-ttu-id="b3347-144">を使用して、ソース コードを手動で開き、関連するコードを検索し、ステートメントを挿入し、Web ページを更新してコンソールにメッセージを `console.log()` `console.log()` 表示する必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="b3347-144">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then refresh the webpage to display the messages in the **Console**.</span></span>  <span data-ttu-id="b3347-145">ブレークポイントを使用すると、コードの構造を知らなくても、関連するコードを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="b3347-145">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="b3347-146">ステートメントでは `console.log()` 、検査する各値を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-146">In your `console.log()` statements, you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="b3347-147">ブレークポイントを使用すると、DevTools は、その時点ですべての変数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="b3347-147">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="b3347-148">コードに影響を与える変数が非表示で難読化されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-148">Sometimes variables that affect your code are hidden and obfuscated.</span></span>  
    
<span data-ttu-id="b3347-149">つまり、ブレークポイントは、メソッドよりも速くバグを見つけて修正するのに役立 `console.log()` ちます。</span><span class="sxs-lookup"><span data-stu-id="b3347-149">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="b3347-150">一歩下がってアプリの動作を考える場合は、[番号 1 の追加] ボタンと [番号 `5 + 1 = 51` `click` **2]** ボタンに関連付けられたイベント リスナーで、正しくない合計 \( \) が計算されるという教育的な推測を行う場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-150">If you step back and think about how the app works, you may make an educated guess that the incorrect sum \(`5 + 1 = 51`\) is computed in the `click` event listener associated with the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="b3347-151">そのため、リスナーが実行される時間の周りにコードを一時停止する `click` 必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-151">So, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="b3347-152">**イベント リスナー ブレークポイントを使用** すると、次の操作を正確に実行できます。</span><span class="sxs-lookup"><span data-stu-id="b3347-152">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="b3347-153">[デバッガー **] ウィンドウで** 、[イベント リスナー ブレークポイント] **を選択して** セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="b3347-153">In the **Debugger** pane, choose **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="b3347-154">DevTools は、アニメーションやクリップボードなどの展開可能なイベント カテゴリの **一覧を** 表示 **します**。</span><span class="sxs-lookup"><span data-stu-id="b3347-154">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="b3347-155">[マウス] イベント**カテゴリの横**にある [展開]\( \*\*\*\* ![ [展開] アイコン ](../media/expand-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-155">Next to the **Mouse** event category, choose **Expand** \(![Expand icon](../media/expand-icon.msft.png)\).</span></span>  <span data-ttu-id="b3347-156">DevTools は、クリックやマウスダウンなどのマウス イベント**の一覧を\*\*\*\*表示します**。</span><span class="sxs-lookup"><span data-stu-id="b3347-156">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="b3347-157">各イベントには、その横にチェック ボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="b3347-157">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="b3347-158">[] をクリックするには、次のチェック ボックス **をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="b3347-158">Choose the checkbox next to **click**.</span></span>  <span data-ttu-id="b3347-159">DevTools は、イベント リスナーの実行時に自動的に `click` 一時停止する設定が行われます。</span><span class="sxs-lookup"><span data-stu-id="b3347-159">DevTools is now set up to automatically pause when any `click` event listener runs.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="[次へ] をクリックするチェック ボックスをオンにします。" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       <span data-ttu-id="b3347-161">[次へ] をクリックするチェック ボックスを **オンにします。**</span><span class="sxs-lookup"><span data-stu-id="b3347-161">Choose the checkbox next to **click**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b3347-162">デモに戻り、[番号 1 の追加] と **[番号 2] を再度選択** します。</span><span class="sxs-lookup"><span data-stu-id="b3347-162">Back on the demo, choose **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="b3347-163">DevTools はデモを一時停止し、ソース ツールでコード行 **を強調表示** します。</span><span class="sxs-lookup"><span data-stu-id="b3347-163">DevTools pauses the demo and highlights a line of code in the **Sources** tool.</span></span>  <span data-ttu-id="b3347-164">DevTools は 16 行目で一時停止する必要があります `get-started.js` 。</span><span class="sxs-lookup"><span data-stu-id="b3347-164">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="b3347-165">別のコード行で一時停止する場合は、\*\*\*\* 正しい行で一時停止するまで 、[スクリプト実行の再開]\( Resume ![ Script Execution ](../media/resume-script-run-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-165">If you pause on a different line of code, choose **Resume Script Execution** \(![Resume Script Execution](../media/resume-script-run-icon.msft.png)\) until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b3347-166">別の行で一時停止した場合は、訪問する Web ページごとにイベント リスナーを登録するブラウザー拡張機能 `click` があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-166">If you paused on a different line, you have a browser extension that registers a `click` event listener on every webpage that you visit.</span></span>  <span data-ttu-id="b3347-167">拡張機能のリスナーで `click` 一時停止しています。</span><span class="sxs-lookup"><span data-stu-id="b3347-167">You are paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="b3347-168">InPrivate モードを使用して\*\*\*\*、すべての拡張機能を無効にするプライベートで参照する場合は、必要なコード行を毎回一時停止する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-168">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="b3347-169">**イベント リスナーのブレークポイント** は、DevTools で使用できる多くの種類のブレークポイントの 1 つにすら異なっています。</span><span class="sxs-lookup"><span data-stu-id="b3347-169">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="b3347-170">さまざまな種類を記憶して、さまざまなシナリオを可能な限り迅速にデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="b3347-170">Memorize all the different types to help you debug different scenarios as quickly as possible.</span></span>  <!--  To learn when and how to use each type, navigate to [Pause your code with breakpoints][JSBreakpoints].  -->  

## <a name="step-4-step-through-the-code"></a><span data-ttu-id="b3347-171">手順 4: コードをステップ実行する</span><span class="sxs-lookup"><span data-stu-id="b3347-171">Step 4: Step through the code</span></span>  

<span data-ttu-id="b3347-172">バグの一般的な原因の 1 つは、スクリプトが正しい順序で実行される場合です。</span><span class="sxs-lookup"><span data-stu-id="b3347-172">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="b3347-173">コードをステップ実行すると、コードのランタイムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b3347-173">Stepping through your code allows you to walk through the runtime of your code.</span></span>  <span data-ttu-id="b3347-174">一度に 1 行を実行して、コードが予想とは異なる順序で実行されている場所を正確に把握するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b3347-174">You walk through one line at a time to help you figure out exactly where your code is running in a different order than you expect.</span></span>  <span data-ttu-id="b3347-175">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="b3347-175">Try it now:</span></span>  

1.  <span data-ttu-id="b3347-176">[ **次の関数呼び出し** \( ![ Step over next function call \) を選択 ](../media/step-over-icon.msft.png) します。</span><span class="sxs-lookup"><span data-stu-id="b3347-176">Choose **Step over next function call** \(![Step over next function call](../media/step-over-icon.msft.png)\).</span></span>  <span data-ttu-id="b3347-177">DevTools は、ステップ インせずに次のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3347-177">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="b3347-178">DevTools は数行のコードをスキップします。</span><span class="sxs-lookup"><span data-stu-id="b3347-178">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="b3347-179">これは、false と評価されるので、ステートメントのコード ブロックが `inputsAreEmpty()` `if` 実行されないためです。</span><span class="sxs-lookup"><span data-stu-id="b3347-179">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  
    
1.  <span data-ttu-id="b3347-180">DevTools **の Sources** ツールで、[Step **to next** function call \( Step to next function call \) を選択して、関数のランタイムを一度に 1 行ステップ実行 ![ ](../media/step-into-icon.msft.png) `updateLabel()` します。</span><span class="sxs-lookup"><span data-stu-id="b3347-180">On the **Sources** tool of DevTools, choose **Step into next function call** \(![Step into next function call](../media/step-into-icon.msft.png)\) to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  
    
<span data-ttu-id="b3347-181">一度に 1 行を確認する方法は、コードをステップ実行する基本的な考え方です。</span><span class="sxs-lookup"><span data-stu-id="b3347-181">Reviewing one line at a time is the basic idea of stepping through code.</span></span>  <span data-ttu-id="b3347-182">でコードを確認すると `get-started.js` 、バグは関数のどこかにある可能性 `updateLabel()` があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-182">If you review the code in `get-started.js`, the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="b3347-183">コードのすべての行をステップ実行するのではなく、別の種類のブレークポイントを使用して、バグの可能性がある場所に近いコードを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="b3347-183">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <a name="step-5-set-a-line-of-code-breakpoint"></a><span data-ttu-id="b3347-184">手順 5: コード行ブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="b3347-184">Step 5: Set a line-of-code breakpoint</span></span>  

<span data-ttu-id="b3347-185">コード行ブレークポイントは、最も一般的な種類のブレークポイントです。</span><span class="sxs-lookup"><span data-stu-id="b3347-185">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="b3347-186">一時停止する特定のコード行にアクセスする場合は、コード行ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3347-186">When you get to the specific line of code you want to pause, use a line-of-code breakpoint.</span></span>  

1.  <span data-ttu-id="b3347-187">次のコードの最後の行を確認します `updateLabel()` 。</span><span class="sxs-lookup"><span data-stu-id="b3347-187">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="b3347-188">左側には、この特定のコード行の番号が **34 と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="b3347-188">On the left, the number of this particular line of code is displayed as **34**.</span></span>  <span data-ttu-id="b3347-189">行 **34 を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3347-189">Choose line **34**.</span></span>  <span data-ttu-id="b3347-190">DevTools は 34 の左側に赤い **アイコンを表示します**。</span><span class="sxs-lookup"><span data-stu-id="b3347-190">DevTools displays a red icon to the left of **34**.</span></span>  <span data-ttu-id="b3347-191">赤いアイコンは、コード行ブレークポイントがこの行に含まれるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b3347-191">The red icon indicates that a line-of-code breakpoint is on this line.</span></span>  <span data-ttu-id="b3347-192">DevTools は、このコード行を実行する前に常に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="b3347-192">DevTools always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="b3347-193">[スクリプト **実行の再開** \( ![ スクリプト実行の再開 ](../media/resume-script-run-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-193">Choose **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\).</span></span>  <span data-ttu-id="b3347-194">スクリプトは、33 行目に達するまで実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="b3347-194">The script continues to run until it reaches line 33.</span></span>  <span data-ttu-id="b3347-195">31 行目、32 行目、および 33 行目では、DevTools は、各行の 、、およびセミコロンの右側の値 `addend1` `addend2` `sum` を出力します。</span><span class="sxs-lookup"><span data-stu-id="b3347-195">On lines 31, 32, and 33, DevTools prints the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="DevTools が行 34 のコード行ブレークポイントで一時停止する" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       <span data-ttu-id="b3347-197">DevTools が行 34 のコード行ブレークポイントで一時停止する</span><span class="sxs-lookup"><span data-stu-id="b3347-197">DevTools pauses on the line-of-code breakpoint on line 34</span></span>  
    :::image-end:::  
    
## <a name="step-6-check-variable-values"></a><span data-ttu-id="b3347-198">手順 6: 変数の値を確認する</span><span class="sxs-lookup"><span data-stu-id="b3347-198">Step 6: Check variable values</span></span>  

<span data-ttu-id="b3347-199">の値、 `addend1` および `addend2` 疑わしい `sum` 外観。</span><span class="sxs-lookup"><span data-stu-id="b3347-199">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="b3347-200">値は引用符で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="b3347-200">The values are wrapped in quotes.</span></span>  <span data-ttu-id="b3347-201">引用符は、値が文字列を意味します。これはバグの原因を説明する良い仮説です。</span><span class="sxs-lookup"><span data-stu-id="b3347-201">The quotations mean that the value is a string, which is a good hypothesis to explain the cause of the bug.</span></span>  <span data-ttu-id="b3347-202">状況に関する詳細を収集します。</span><span class="sxs-lookup"><span data-stu-id="b3347-202">Gather more information about the situation.</span></span>  <span data-ttu-id="b3347-203">DevTools には、変数値を調べる多くのツールが提供されています。</span><span class="sxs-lookup"><span data-stu-id="b3347-203">DevTools provides many tools for examining variable values.</span></span>  

### <a name="method-1-the-scope-pane"></a><span data-ttu-id="b3347-204">方法 1: [スコープ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b3347-204">Method 1: The Scope pane</span></span>  

<span data-ttu-id="b3347-205">コード行を一時停止すると、[スコープ]\*\*\*\* ウィンドウに、現在定義されているローカル変数とグローバル変数と、各変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-205">If you pause on a line of code, the **Scope** pane displays the local and global variables that are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="b3347-206">また、必要に応じてクロージャ変数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-206">It also displays closure variables, as applicable.</span></span>  <span data-ttu-id="b3347-207">変数値をダブルクリックして編集します。</span><span class="sxs-lookup"><span data-stu-id="b3347-207">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="b3347-208">コード行で一時停止しない場合、[スコープ] ウィンドウ **は** 空です。</span><span class="sxs-lookup"><span data-stu-id="b3347-208">If you don't pause on a line of code, the **Scope** pane is empty.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="[スコープ] ウィンドウ" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   <span data-ttu-id="b3347-210">[ **スコープ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b3347-210">The **Scope** pane</span></span>  
:::image-end:::  

### <a name="method-2-watch-expressions"></a><span data-ttu-id="b3347-211">方法 2: ウォッチ式</span><span class="sxs-lookup"><span data-stu-id="b3347-211">Method 2: Watch Expressions</span></span>  

<span data-ttu-id="b3347-212">[ **ウォッチ** ] ウィンドウでは、変数 (など) または式 ( `sum` など) の値を監視できます `typeof sum` 。</span><span class="sxs-lookup"><span data-stu-id="b3347-212">The **Watch** pane allows you to monitor the values of variables (such as `sum`) or expressions (such as `typeof sum`).</span></span>  <span data-ttu-id="b3347-213">有効な JavaScript 式はウォッチ式に格納できます。</span><span class="sxs-lookup"><span data-stu-id="b3347-213">You may store any valid JavaScript expression in a Watch Expression.</span></span>  

1.  <span data-ttu-id="b3347-214">[ウォッチ] **ウィンドウを選択** します。</span><span class="sxs-lookup"><span data-stu-id="b3347-214">Choose the **Watch** pane.</span></span>  
1.  <span data-ttu-id="b3347-215">[ **ウォッチ式の追加** ] \( ![ Add watch expression ](../media/add-expression-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-215">Choose **Add watch expression** \(![Add watch expression](../media/add-expression-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="b3347-216">「`typeof sum`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b3347-216">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="b3347-217">`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-217">Select `Enter`.</span></span>  <span data-ttu-id="b3347-218">DevTools が表示されます `typeof sum: "string"` 。</span><span class="sxs-lookup"><span data-stu-id="b3347-218">DevTools displays `typeof sum: "string"`.</span></span>  <span data-ttu-id="b3347-219">コロンの右側の値は、ウォッチ式の結果です。</span><span class="sxs-lookup"><span data-stu-id="b3347-219">The value to the right of the colon is the result of your Watch Expression.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="b3347-220">次の図では、 `typeof sum` ウォッチ式が [ウォッチ] ウィンドウに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-220">In the following figure, the `typeof sum` Watch Expression is displayed in the **Watch** pane.</span></span>  <span data-ttu-id="b3347-221">DevTools ウィンドウが広い場合は\*\*\*\*、[デバッガー] ウィンドウ内\*\*\*\* に [ウォッチ] ウィンドウが表示され、右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-221">If your DevTools window is wide, the **Watch** pane is displayed within the **Debugger** pane, which then appears on the right.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="[ウォッチ] ウィンドウ" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   <span data-ttu-id="b3347-223">[ **ウォッチ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b3347-223">The **Watch** pane</span></span>  
:::image-end:::  

<span data-ttu-id="b3347-224">疑わしい場合 `sum` は、数値である必要がある場合に文字列として評価されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-224">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="b3347-225">これで、確認された値の種類がバグの原因です。</span><span class="sxs-lookup"><span data-stu-id="b3347-225">You now confirmed value type is the cause of the bug.</span></span>  

### <a name="method-3-the-console"></a><span data-ttu-id="b3347-226">方法 3: コンソール</span><span class="sxs-lookup"><span data-stu-id="b3347-226">Method 3: The Console</span></span>  

<span data-ttu-id="b3347-227">コンソール **を使用** すると、出力を `console.log()` 表示できます。</span><span class="sxs-lookup"><span data-stu-id="b3347-227">The **Console** allows you to view `console.log()` output.</span></span>  <span data-ttu-id="b3347-228">また、コンソール **を使用して** 、デバッガーがコード ステートメントで一時停止している間に任意の JavaScript ステートメントを評価することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3347-228">You can also use the **Console** to evaluate arbitrary JavaScript statements while the debugger is paused at a code statement.</span></span>  <span data-ttu-id="b3347-229">デバッグの場合は、コンソールを使用 **して** 、潜在的な修正プログラムのバグをテストできます。</span><span class="sxs-lookup"><span data-stu-id="b3347-229">For debugging, you can use the **Console** to test potential fixes for bugs.</span></span>

1.  <span data-ttu-id="b3347-230">コンソール ツール **が閉** じている場合は、選択 `Esc` して開きます。</span><span class="sxs-lookup"><span data-stu-id="b3347-230">If the **Console** tool is closed, select `Esc` to open it.</span></span>  <span data-ttu-id="b3347-231">コンソール **ツール** は、DevTools ウィンドウの下部ウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="b3347-231">The **Console** tool opens in the lower pane of the DevTools window.</span></span>  
1.  <span data-ttu-id="b3347-232">コンソールで **、と**入力します `parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="b3347-232">In the **Console**, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="b3347-233">ツールのステートメントは、スコープ内のコード行 `addend1` で `addend2` 一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-233">The statement the tool is paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="b3347-234">`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-234">Select `Enter`.</span></span>  <span data-ttu-id="b3347-235">DevTools はステートメントと印刷を評価します。これは、デモで生成 `6` される結果です。</span><span class="sxs-lookup"><span data-stu-id="b3347-235">DevTools evaluates the statement and prints `6`, which is the result you expect the demo to produce.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="parseInt(addend1) + parseInt(addend2) を評価した後のコンソール ツール" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       <span data-ttu-id="b3347-237">評価 **後** のコンソール ツール</span><span class="sxs-lookup"><span data-stu-id="b3347-237">The **Console** tool, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <a name="step-7-apply-a-fix"></a><span data-ttu-id="b3347-238">手順 7: 修正プログラムを適用する</span><span class="sxs-lookup"><span data-stu-id="b3347-238">Step 7: Apply a fix</span></span>  

<span data-ttu-id="b3347-239">バグの修正の可能性を特定しました。</span><span class="sxs-lookup"><span data-stu-id="b3347-239">We've identified a possible fix for the bug.</span></span>  <span data-ttu-id="b3347-240">次に、DevTools UI 内で JavaScript コードを直接編集し、次のようにデモを再実行して修正プログラムをテストします。</span><span class="sxs-lookup"><span data-stu-id="b3347-240">Next, edit the JavaScript code directly within the DevTools UI and then rerun the demo to test the fix, as follows.</span></span>

1.  <span data-ttu-id="b3347-241">[スクリプト **実行の再開** \( ![ スクリプト実行の再開 ](../media/resume-script-run-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-241">Choose **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="b3347-242">[エディター **] ウィンドウで** 、行をに置き換 `var sum = addend1 + addend2` えます `var sum = parseInt(addend1) + parseInt(addend2)` 。</span><span class="sxs-lookup"><span data-stu-id="b3347-242">In the **Editor** pane, replace the line `var sum = addend1 + addend2` with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="b3347-243">`Control` + `S` \(Windows Linux\) または `Command` + `S` \(macOS\) を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="b3347-243">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="b3347-244">[ **ブレークポイントを非アクティブ化** する]\( ![ [ブレークポイントを非アクティブ化 ](../media/deactivate-breakpoints-button-icon.msft.png) する]\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3347-244">Choose **Deactivate breakpoints** \(![Deactivate breakpoints](../media/deactivate-breakpoints-button-icon.msft.png)\).</span></span>  <span data-ttu-id="b3347-245">オプションがアクティブな状態を示すために青に変更されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-245">It changes blue to indicate the option is active.</span></span>  <span data-ttu-id="b3347-246">[ **ブレークポイントの非アクティブ化** ] が設定されている間、DevTools は設定したブレークポイントを無視します。</span><span class="sxs-lookup"><span data-stu-id="b3347-246">While **Deactivate breakpoints** is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="b3347-247">異なる値でデモを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="b3347-247">Try out the demo with different values.</span></span>  <span data-ttu-id="b3347-248">デモで正しく計算されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b3347-248">The demo now calculates correctly.</span></span>  
    
> [!CAUTION]
> <span data-ttu-id="b3347-249">このワークフローは、サーバーから送信されたコードのローカル コピーにのみ修正プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="b3347-249">This workflow only applies a fix to a local copy of the code sent from the server.</span></span>  <span data-ttu-id="b3347-250">プロジェクトをデバッグする場合、修正プログラムを特定した後でも、ローカル ソース コードを編集してから固定コードをサーバーに再展開するなどの修正プログラムをサーバー上のコードに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3347-250">When debugging your project, after you identify the fix, you still need to apply that fix to the code on the server, such as by editing your local source code and then re-deploying your fixed code to the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3347-251">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b3347-251">Next steps</span></span>  

<span data-ttu-id="b3347-252">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="b3347-252">Congratulations!</span></span>  <span data-ttu-id="b3347-253">JavaScript のデバッグ時に DevTools をMicrosoft Edgeする方法がわかっています。</span><span class="sxs-lookup"><span data-stu-id="b3347-253">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="b3347-254">この記事で学んだツールとメソッドは、数え切れないほどの時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="b3347-254">The tools and methods you learned in this article may save you countless hours.</span></span>  

<span data-ttu-id="b3347-255">この記事では、ブレークポイントを設定する 2 つの方法を示しました。</span><span class="sxs-lookup"><span data-stu-id="b3347-255">This article showed two ways to set breakpoints.</span></span>  <span data-ttu-id="b3347-256">DevTools には、次のような特定の条件が満たされた場合にコードを一時停止するブレークポイントを設定する方法も用意されています。</span><span class="sxs-lookup"><span data-stu-id="b3347-256">DevTools also provides ways to set breakpoints to pause your code when certain conditions are met, such as:</span></span>

*   <span data-ttu-id="b3347-257">指定した条件が true の場合にのみトリガーされる条件付きブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="b3347-257">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="b3347-258">キャッチまたはキャッチされていない例外のブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="b3347-258">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="b3347-259">要求された URL が指定した部分文字列と一致するときにトリガーされる XHR ブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="b3347-259">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  
    
<span data-ttu-id="b3347-260">各型を使用する場合と方法の詳細については、「ブレークポイントを使用してコードを一時停止 [する」に移動します][DevToolsJavscriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="b3347-260">For more information about when and how to use each type, navigate to [Pause your code with breakpoints][DevToolsJavscriptBreakpoints].</span></span>  

<span data-ttu-id="b3347-261">この記事では、いくつかのコード ステップコントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3347-261">A couple of code stepping controls aren't explained in this article.</span></span>  <span data-ttu-id="b3347-262">詳細については、「デバッガー機能を使用 [する][DevToolsJavascriptReferenceStepThroughCode] 」の記事の「Step over line of code」に移動します。</span><span class="sxs-lookup"><span data-stu-id="b3347-262">For more information, navigate to [Step over line of code][DevToolsJavascriptReferenceStepThroughCode] in the "Use the debugger features" article.</span></span>

### <a name="see-also"></a><span data-ttu-id="b3347-263">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3347-263">See also</span></span>

*   <span data-ttu-id="b3347-264">[デバッガー機能を使用する][DevToolsJavascriptReference] - ソース ツールでデバッガーの UI を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3347-264">[Use the debugger features][DevToolsJavascriptReference] - Using the UI of the debugger in the Sources tool.</span></span>
*   <span data-ttu-id="b3347-265">[ソース ツールの概要][DevToolsSourcesIndex] - JavaScript デバッガーとコード エディターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3347-265">[Sources tool overview][DevToolsSourcesIndex] - Introduces the JavaScript debugger and code editor.</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b3347-266">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="b3347-266">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptReference]: ./reference.md "デバッガー機能を使用|Microsoft Docs"  
[DevToolsSourcesIndex]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
[DevToolsJavscriptBreakpoints]: ./breakpoints.md "DevTools アプリケーションでブレークポイントを使用してコードMicrosoft Edgeする|Microsoft Docs"
[DevToolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "コードのステップスルー - デバッガー機能を使用|Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "Open Demo |Glitch"  

> [!NOTE]
> <span data-ttu-id="b3347-272">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3347-272">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b3347-273">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="b3347-273">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b3347-275">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b3347-275">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
