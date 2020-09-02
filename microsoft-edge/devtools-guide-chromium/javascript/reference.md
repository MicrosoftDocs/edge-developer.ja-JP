---
title: JavaScript デバッグ リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a6ec2438457c81ed527154af30c9642d5c287d3c
ms.sourcegitcommit: 2fa65cca74c5214601900579c0ce9f946ad8a27e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10991214"
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

# <span data-ttu-id="9961b-103">JavaScript febugging リファレンス</span><span class="sxs-lookup"><span data-stu-id="9961b-103">JavaScript febugging reference</span></span>  

<span data-ttu-id="9961b-104">Microsoft Edge DevTools デバッグ機能の次の包括的なリファレンスで、新しいデバッグワークフローを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9961b-104">Discover new debugging workflows with the following comprehensive reference of Microsoft Edge DevTools debugging features.</span></span>  

<span data-ttu-id="9961b-105">デバッグの基礎については、「 [Microsoft Edge DevTools のデバッグ JavaScript の概要][DevToolsJavascriptGetStarted] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9961b-105">See [Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted] to learn the basics of debugging.</span></span>  

## <span data-ttu-id="9961b-106">ブレークポイントを使用したコードの一時停止</span><span class="sxs-lookup"><span data-stu-id="9961b-106">Pause code with breakpoints</span></span>  

<span data-ttu-id="9961b-107">ランタイムの途中でコードを一時停止できるようにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="9961b-107">Set a breakpoint so that you are able to pause your code in the middle of the runtime.</span></span>  

<span data-ttu-id="9961b-108">ブレークポイントを設定する方法については [、「ブレークポイントを使用したコードの一時停止][DevToolsJavascriptBreakpoints] 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9961b-108">See [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints] to learn how to set breakpoints.</span></span>  

## <span data-ttu-id="9961b-109">ステップ実行コード</span><span class="sxs-lookup"><span data-stu-id="9961b-109">Step through code</span></span>  

<span data-ttu-id="9961b-110">コードが一時停止されたら、1行ずつステップ実行し、制御フローとプロパティの値を調べます。</span><span class="sxs-lookup"><span data-stu-id="9961b-110">Once your code is paused, step through it, one line at a time, investigating control flow and property values along the way.</span></span>  

### <span data-ttu-id="9961b-111">コード行のステップ</span><span class="sxs-lookup"><span data-stu-id="9961b-111">Step over line of code</span></span>  

<span data-ttu-id="9961b-112">デバッグしている問題に関連しない関数を含むコード行で一時停止している場合は、 **ステップオーバー** \ ([ ![ ステップオーバー \]) ボタンをクリックして、 ][ImageStepOverIcon] この関数を実行せずに実行します。</span><span class="sxs-lookup"><span data-stu-id="9961b-112">When paused on a line of code containing a function that is not relevant to the problem you are debugging, click the **Step over** \(![Step over][ImageStepOverIcon]\) button to run the function without stepping into it.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="[ステップオーバー] を選ぶ" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   <span data-ttu-id="9961b-114">[**ステップオーバー** ] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="9961b-114">Select **Step over**</span></span>  
:::image-end:::  

<span data-ttu-id="9961b-115">たとえば、次のコードスニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="9961b-115">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name); // D
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name; // C
}
```  

<span data-ttu-id="9961b-116">はに一時停止 `A` しています。</span><span class="sxs-lookup"><span data-stu-id="9961b-116">You are paused on `A`.</span></span>  <span data-ttu-id="9961b-117">[ **ステップオーバー**] を押すことで、実行している関数のすべてのコードが実行され `B` `C` ます。</span><span class="sxs-lookup"><span data-stu-id="9961b-117">By pressing **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span></span>  <span data-ttu-id="9961b-118">次に、DevTools で一時停止 `D` します。</span><span class="sxs-lookup"><span data-stu-id="9961b-118">DevTools then pauses on `D`.</span></span>  

### <span data-ttu-id="9961b-119">コード行のステップ</span><span class="sxs-lookup"><span data-stu-id="9961b-119">Step into line of code</span></span>  

<span data-ttu-id="9961b-120">デバッグしている問題に関連する関数呼び出しが含まれているコード行で一時停止した場合、その機能をさらに調べるに **は、[** ( ![ ステップイン ][ImageStepIntoIcon] )] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9961b-120">When paused on a line of code containing a function call that is related to the problem you are debugging, click the **Step into** \(![Step into][ImageStepIntoIcon]\) button to investigate that function further.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="[ステップイン] を選ぶ" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   <span data-ttu-id="9961b-122">[**ステップイン**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="9961b-122">Select **Step into**</span></span>  
:::image-end:::  

<span data-ttu-id="9961b-123">たとえば、次のコードスニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="9961b-123">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name);
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name;
}
```  

<span data-ttu-id="9961b-124">はに一時停止 `A` しています。</span><span class="sxs-lookup"><span data-stu-id="9961b-124">You are paused on `A`.</span></span>  <span data-ttu-id="9961b-125">**ステップイン**を押すと、devtools はこのコード行を実行し、で一時停止し `B` ます。</span><span class="sxs-lookup"><span data-stu-id="9961b-125">By pressing **Step into**, DevTools runs this line of code, then pauses on `B`.</span></span>  

### <span data-ttu-id="9961b-126">コード行のステップアウト</span><span class="sxs-lookup"><span data-stu-id="9961b-126">Step out of line of code</span></span>  

<span data-ttu-id="9961b-127">デバッグ中の問題に関連していない関数の内部で一時停止している場合は、[ **ステップアウト** \ ( ![ ステップアウト ][ImageStepOutIcon] )] ボタンをクリックして関数の残りのコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="9961b-127">When paused inside of a function that is not related to the problem you are debugging, click the **Step out** \(![Step out][ImageStepOutIcon]\) button to run the rest of the code of the function.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="[ステップアウト] を選ぶ" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   <span data-ttu-id="9961b-129">[**ステップアウト**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="9961b-129">Select **Step out**</span></span>  
:::image-end:::  

<span data-ttu-id="9961b-130">たとえば、次のコードスニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="9961b-130">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName();
    updateName(name); // C
}
function getName() {
    var name = app.first + ' ' + app.last; // A
    return name; // B
}
```  

<span data-ttu-id="9961b-131">はに一時停止 `A` しています。</span><span class="sxs-lookup"><span data-stu-id="9961b-131">You are paused on `A`.</span></span>  <span data-ttu-id="9961b-132">[ **ステップアウト**] を押すと、devtools で残りのコードが実行 `getName()` され `B` ます。これは、この例では次のように `C` なります。</span><span class="sxs-lookup"><span data-stu-id="9961b-132">By pressing **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span></span>  

### <span data-ttu-id="9961b-133">特定の行までのすべてのコードを実行する</span><span class="sxs-lookup"><span data-stu-id="9961b-133">Run all code up to a specific line</span></span>  

<span data-ttu-id="9961b-134">Long 関数をデバッグする場合、デバッグしている問題に関連していないコードが多数存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9961b-134">When debugging a long function, there may be a lot of code that is not related to the problem you are debugging.</span></span>  

<span data-ttu-id="9961b-135">すべての行の手順を実行することもできますが、面倒なこともあります。</span><span class="sxs-lookup"><span data-stu-id="9961b-135">You may choose to step through all the lines, but that is tedious.</span></span>  <span data-ttu-id="9961b-136">目的の行に行コードのブレークポイントを設定してから、[ **スクリプト実行の再開** ] (スクリプト実行の再開) ボタンをクリックすることもできますが、それ ![ よりも ][ImageResumeScriptExecutionIcon] 早い方法があります。</span><span class="sxs-lookup"><span data-stu-id="9961b-136">You may choose to set a line-of-code breakpoint on the line in which you are interested and then click the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button, but there is a faster way.</span></span>  

<span data-ttu-id="9961b-137">目的のコード行を右クリックし、[ **続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9961b-137">Right-click the line of code in which you are interested, and select **Continue to here**.</span></span>  <span data-ttu-id="9961b-138">DevTools では、その時点までのすべてのコードが実行され、その行が一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="9961b-138">DevTools runs all of the code up to that point, and then pauses on that line.</span></span>  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="[続行] を選択する" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   <span data-ttu-id="9961b-140">[**続行**] を選択する</span><span class="sxs-lookup"><span data-stu-id="9961b-140">Select **Continue to here**</span></span>  
:::image-end:::  

### <span data-ttu-id="9961b-141">コールスタックの top 関数を再起動する</span><span class="sxs-lookup"><span data-stu-id="9961b-141">Restart the top function of the call stack</span></span>  

<span data-ttu-id="9961b-142">一時停止しているコード行で、[ **通話スタック** ] ウィンドウ内の任意の場所を右クリックし、[ **フレームの再起動** ] を選択して、呼び出し履歴の一番上の関数の1行目にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="9961b-142">While paused on a line of code, right-click anywhere in the **Call Stack** pane and select **Restart Frame** to pause on the first line of the top function in your call stack.</span></span>  <span data-ttu-id="9961b-143">Top 関数は、最後に実行された関数です。</span><span class="sxs-lookup"><span data-stu-id="9961b-143">The top function is the last function that was run.</span></span>  

<span data-ttu-id="9961b-144">次のコードスニペットは、手順の例です。</span><span class="sxs-lookup"><span data-stu-id="9961b-144">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

<span data-ttu-id="9961b-145">はに一時停止 `A` しています。</span><span class="sxs-lookup"><span data-stu-id="9961b-145">You are paused on `A`.</span></span>  <span data-ttu-id="9961b-146">[ **フレームの再起動**] をクリックした後、 `B` ブレークポイントを設定したり、[ **再開] スクリプト実行**を押したりしなくても、を一時停止しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="9961b-146">After clicking **Restart Frame**, you should be paused on `B`, without ever setting a breakpoint or pressing **Resume script execution**.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="[フレームの再起動] を選ぶ" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   <span data-ttu-id="9961b-148">[**フレームの再起動**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="9961b-148">Select **Restart Frame**</span></span>  
:::image-end:::  

### <span data-ttu-id="9961b-149">スクリプトランタイムを再開する</span><span class="sxs-lookup"><span data-stu-id="9961b-149">Resume script runtime</span></span>  

<span data-ttu-id="9961b-150">スクリプトを一時停止した後でランタイムを継続するには、[ **スクリプト実行の再開** ] ([ ![ スクリプト実行の再開 ][ImageResumeScriptExecutionIcon] ]) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9961b-150">To continue the runtime after a pause of your script, click the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button.</span></span>  <span data-ttu-id="9961b-151">DevTools は、次のブレークポイント (存在する場合) までスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="9961b-151">DevTools runs the script up until the next breakpoint, if any.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="[スクリプト実行の再開] を選択する" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   <span data-ttu-id="9961b-153">[**スクリプト実行の再開**] を選択する</span><span class="sxs-lookup"><span data-stu-id="9961b-153">Select **Resume script execution**</span></span>  
:::image-end:::  

#### <span data-ttu-id="9961b-154">スクリプトの強制実行</span><span class="sxs-lookup"><span data-stu-id="9961b-154">Force script runtime</span></span>  

<span data-ttu-id="9961b-155">すべてのブレークポイントを無視してスクリプトを強制的に実行し続けるには、[**スクリプト**実行の再開] をクリックして、[スクリプト実行の強制実行] (スクリプト実行の ![ 強制) ボタンを選択し ][ImageResumeScriptExecutionIcon] **Force script execution** ![ ][ImageForceScriptExecutionIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="9961b-155">To ignore all breakpoints and force your script to resume running, click and hold the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button and then select the **Force script execution** \(![Force script execution][ImageForceScriptExecutionIcon]\) button.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="[スクリプト実行の強制] を選ぶ" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   <span data-ttu-id="9961b-157">[**スクリプト実行の強制**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="9961b-157">Select **Force script execution**</span></span>  
:::image-end:::  

### <span data-ttu-id="9961b-158">スレッドコンテキストの変更</span><span class="sxs-lookup"><span data-stu-id="9961b-158">Change thread context</span></span>  

<span data-ttu-id="9961b-159">Web ワーカーまたはサービスワーカーを操作するときに、[ **スレッド** ] ウィンドウに表示されているコンテキストをクリックして、そのコンテキストに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="9961b-159">When working with web workers or service workers, click on a context listed in the **Threads** pane to switch to that context.</span></span>  <span data-ttu-id="9961b-160">青い矢印のアイコンは、現在選択されているコンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="9961b-160">The blue arrow icon represents which context is currently selected.</span></span>  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="[スレッド] ウィンドウ" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   <span data-ttu-id="9961b-162">[ **スレッド** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9961b-162">The **Threads** pane</span></span>  
:::image-end:::  

<span data-ttu-id="9961b-163">たとえば、メインスクリプトとサービスワーカースクリプトの両方のブレークポイントで一時停止しているとします。</span><span class="sxs-lookup"><span data-stu-id="9961b-163">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span></span>  <span data-ttu-id="9961b-164">サービスワーカーコンテキストのローカルプロパティとグローバルプロパティを表示する必要があるが、[ **ソース** ] パネルにはメインスクリプトコンテキストが表示されています。</span><span class="sxs-lookup"><span data-stu-id="9961b-164">You want to view the local and global properties for the service worker context, but the **Sources** panel is showing the main script context.</span></span>  <span data-ttu-id="9961b-165">[ **スレッド** ] ウィンドウで service worker エントリをクリックすると、そのコンテキストに切り替えることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="9961b-165">By clicking on the service worker entry in the **Threads** pane, you should be able to switch to that context.</span></span>  

## <span data-ttu-id="9961b-166">ローカル、クロージャ、グローバルプロパティの表示と編集</span><span class="sxs-lookup"><span data-stu-id="9961b-166">View and edit local, closure, and global properties</span></span>  

<span data-ttu-id="9961b-167">コード行で一時停止している間に、 **スコープ** ウィンドウを使って、ローカル、クロージャ、グローバルスコープのプロパティと変数の値を表示および編集します。</span><span class="sxs-lookup"><span data-stu-id="9961b-167">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span></span>  

*   <span data-ttu-id="9961b-168">プロパティ値をダブルクリックして変更します。</span><span class="sxs-lookup"><span data-stu-id="9961b-168">Double-click a property value to change it.</span></span>  
*   <span data-ttu-id="9961b-169">列挙可能でないプロパティは灰色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="9961b-169">Non-enumerable properties are greyed out.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="スコープウィンドウ" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   <span data-ttu-id="9961b-171">**スコープ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9961b-171">The **Scope** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="9961b-172">現在の通話履歴を表示する</span><span class="sxs-lookup"><span data-stu-id="9961b-172">View the current call stack</span></span>  

<span data-ttu-id="9961b-173">一時停止しているコード行では、[ **通話スタック** ] ウィンドウを使って、この時点までの呼び出し履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9961b-173">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span></span>  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

<span data-ttu-id="9961b-174">エントリをクリックすると、その関数が呼び出されたコード行にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="9961b-174">Click on an entry to jump to the line of code where that function was called.</span></span>  <span data-ttu-id="9961b-175">青色の矢印アイコンは、現在の DevTools が現在強調表示されている関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="9961b-175">The blue arrow icon represents which function DevTools is currently highlighting.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="[通話スタック] ウィンドウ" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   <span data-ttu-id="9961b-177">[ **通話スタック** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9961b-177">The **Call Stack** pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="9961b-178">コード行で一時停止していない場合、[ **呼び出し履歴** ] ウィンドウは空です。</span><span class="sxs-lookup"><span data-stu-id="9961b-178">When not paused on a line of code, the **Call Stack** pane is empty.</span></span>  

### <span data-ttu-id="9961b-179">スタックトレースのコピー</span><span class="sxs-lookup"><span data-stu-id="9961b-179">Copy stack trace</span></span>  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

<span data-ttu-id="9961b-180">[ **通話スタック** ] ウィンドウ内の任意の場所を右クリックし、[ **スタックトレースのコピー** ] を選択して、現在の呼び出し履歴をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9961b-180">Right-click anywhere in the **Call Stack** pane and select **Copy stack trace** to copy the current call stack to the clipboard.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="[スタックトレースのコピー] を選ぶ" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   <span data-ttu-id="9961b-182">[**スタックトレースのコピー** ] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="9961b-182">Select **Copy Stack Trace**</span></span>  
:::image-end:::  

<span data-ttu-id="9961b-183">次のコードスニペットは、出力の例です。</span><span class="sxs-lookup"><span data-stu-id="9961b-183">The following code snippet is an example of the output.</span></span>  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onClick (get-started.js:15)
```  

## <span data-ttu-id="9961b-184">スクリプトまたはスクリプトのパターンを無視する</span><span class="sxs-lookup"><span data-stu-id="9961b-184">Ignore a script or pattern of scripts</span></span>  

<span data-ttu-id="9961b-185">デバッグ中にそのスクリプトを無視する場合は、スクリプトをライブラリコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="9961b-185">Mark a script as Library code when you want to ignore that script while debugging.</span></span>  <span data-ttu-id="9961b-186">ライブラリコードとしてマークされている場合、スクリプトは [ **呼び出し履歴** ] ウィンドウで隠されており、コードのステップ実行時にスクリプトの関数にはステップインしません。</span><span class="sxs-lookup"><span data-stu-id="9961b-186">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span></span>  

<span data-ttu-id="9961b-187">次のコードスニペットは、手順の例です。</span><span class="sxs-lookup"><span data-stu-id="9961b-187">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` <span data-ttu-id="9961b-188">は、信頼できるサードパーティのライブラリです。</span><span class="sxs-lookup"><span data-stu-id="9961b-188">is a third-party library that you trust.</span></span>  <span data-ttu-id="9961b-189">デバッグ中の問題がサードパーティのライブラリに関連していないことがわかっている場合は、スクリプトを **ライブラリコード**としてマークすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9961b-189">If you are confident that the problem you are debugging is not related to the third-party library, then it makes sense to mark the script as **Library code**.</span></span>  

### <span data-ttu-id="9961b-190">[エディター] ウィンドウからスクリプトをライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="9961b-190">Mark a script as Library code from the Editor pane</span></span>  

<span data-ttu-id="9961b-191">[**エディター** ] ウィンドウからスクリプトを**ライブラリコード**としてマークするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9961b-191">Complete the following actions to mark a script as **Library code** from the **Editor** pane.</span></span>  

1.  <span data-ttu-id="9961b-192">ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9961b-192">Open the file.</span></span>  
1.  <span data-ttu-id="9961b-193">任意の場所を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9961b-193">Right-click anywhere.</span></span>  
1.  <span data-ttu-id="9961b-194">[ **Library code としてマーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9961b-194">Select **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="[エディター] ウィンドウからスクリプトをライブラリコードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       <span data-ttu-id="9961b-196">[**エディター** ] ウィンドウからスクリプトを**ライブラリコード**としてマークする</span><span class="sxs-lookup"><span data-stu-id="9961b-196">Mark a script as **Library code** from the **Editor** pane</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="9961b-197">[呼び出し履歴] ウィンドウからスクリプトをライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="9961b-197">Mark a script as Library code from the Call Stack pane</span></span>  

<span data-ttu-id="9961b-198">[**呼び出し履歴**] ウィンドウからスクリプトを**ライブラリコード**としてマークするための、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9961b-198">Compelte the folliwng actions to mark a script as **Library code** from the **Call Stack** pane.</span></span>  

1.  <span data-ttu-id="9961b-199">スクリプトから関数を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9961b-199">Right-click on a function from the script.</span></span>  
1.  <span data-ttu-id="9961b-200">[ **Library code としてマーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9961b-200">Select **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="[呼び出し履歴] ウィンドウからスクリプトをライブラリコードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       <span data-ttu-id="9961b-202">[**呼び出し履歴**] ウィンドウからスクリプトを**ライブラリコード**としてマークする</span><span class="sxs-lookup"><span data-stu-id="9961b-202">Mark a script as **Library code** from the **Call Stack** pane</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="9961b-203">設定からスクリプトをライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="9961b-203">Mark a script as Library code from Settings</span></span>  

<span data-ttu-id="9961b-204">1つのスクリプトまたはスクリプトのパターンを **設定**からマークするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9961b-204">Complete the following actions to mark a single script or pattern of scripts from **Settings**.</span></span>  

1.  <span data-ttu-id="9961b-205">[ [設定][DevToolsCustomize]] を開きます。</span><span class="sxs-lookup"><span data-stu-id="9961b-205">Open [Settings][DevToolsCustomize].</span></span>  
1.  <span data-ttu-id="9961b-206">[ **ライブラリコード** ] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="9961b-206">Go to the **Library code** tab.</span></span>  
1.  <span data-ttu-id="9961b-207">[ **パターンの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9961b-207">Click **Add pattern**.</span></span>  
1.  <span data-ttu-id="9961b-208">**ライブラリコード**としてマークするスクリプト名またはスクリプト名の regex パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="9961b-208">Enter the script name or a regex pattern of script names to mark as **Library code**.</span></span>  
1.  <span data-ttu-id="9961b-209">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9961b-209">Click **Add**.</span></span>  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="設定からスクリプトをライブラリコードとしてマークする" lightbox="../media/javascript-framework-library-code.msft.png":::
       <span data-ttu-id="9961b-211">**設定**からスクリプトを**ライブラリコード**としてマークする</span><span class="sxs-lookup"><span data-stu-id="9961b-211">Mark a script as **Library code** from **Settings**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9961b-212">任意のページからデバッグコードのスニペットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9961b-212">Run snippets of debug code from any page</span></span>   

<span data-ttu-id="9961b-213">本体で同じデバッグコードを繰り返し実行していることがわかった場合は、スニペットを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9961b-213">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span></span>  <span data-ttu-id="9961b-214">スニペットは、DevTools 内で作成、保存、実行するランタイムスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="9961b-214">Snippets are runtime scripts that you author, store, and run within DevTools.</span></span>  

<span data-ttu-id="9961b-215">詳細については [、「任意のページからコードのスニペットを実行][DevToolsJavascriptSnippets] する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9961b-215">See [Run Snippets of Code From Any Page][DevToolsJavascriptSnippets] to learn more.</span></span>  

## <span data-ttu-id="9961b-216">カスタム JavaScript 式の値を見る</span><span class="sxs-lookup"><span data-stu-id="9961b-216">Watch the values of custom JavaScript expressions</span></span>  

<span data-ttu-id="9961b-217">**ウォッチ**ウィンドウを使用して、カスタム式の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="9961b-217">Use the **Watch** pane to watch the values of custom expressions.</span></span>  <span data-ttu-id="9961b-218">有効な JavaScript 式を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="9961b-218">You may watch any valid JavaScript expression.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="ウォッチウィンドウ" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   <span data-ttu-id="9961b-220">**ウォッチ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9961b-220">The **Watch** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="9961b-221">**Add Expression** ![ 新しいウォッチ式を作成するには、[式の追加 \ (式の追加 \ ][ImageAddExpressionIcon] )] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9961b-221">Click the **Add Expression** \(![Add Expression][ImageAddExpressionIcon]\) button to create a new watch expression.</span></span>  
*   <span data-ttu-id="9961b-222">**Refresh** ![ ][ImageRefreshIcon] すべての既存の式の値を更新するには、[更新] (更新) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9961b-222">Click the **Refresh** \(![Refresh][ImageRefreshIcon]\) button to refresh the values of all existing expressions.</span></span>  <span data-ttu-id="9961b-223">値は、コードをステップ実行して自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="9961b-223">Values automatically refresh while stepping through code.</span></span>  
*   <span data-ttu-id="9961b-224">式の上にマウスポインターを移動し、[ **式の削除** \ (式 \ の ![ 削除)] ボタンをクリックし ][ImageDeleteExpressionIcon] て削除します。</span><span class="sxs-lookup"><span data-stu-id="9961b-224">Hover over an expression and click the **Delete Expression** \(![Delete Expression][ImageDeleteExpressionIcon]\) button to delete it.</span></span>  

## <span data-ttu-id="9961b-225">ファイルを読みやすくする</span><span class="sxs-lookup"><span data-stu-id="9961b-225">Make a minified file readable</span></span>  

<span data-ttu-id="9961b-226">[\] (書式 \) ボタンをクリックして、 **表示** ![ ][ImageFormatIcon] したファイルを人間が読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="9961b-226">Click the **Format** \(![Format][ImageFormatIcon]\) button to make a minified file human-readable.</span></span>  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="[書式] ボタン" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   <span data-ttu-id="9961b-228">[ **書式** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="9961b-228">The **Format** button</span></span>  
:::image-end:::  

## <span data-ttu-id="9961b-229">スクリプトを編集する</span><span class="sxs-lookup"><span data-stu-id="9961b-229">Edit a script</span></span>   

<span data-ttu-id="9961b-230">バグを修正する場合、多くの場合、JavaScript コードに加えられた変更をいくつかテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9961b-230">When fixing a bug, you often want to test out some changes to your JavaScript code.</span></span>  <span data-ttu-id="9961b-231">外部のエディターまたは IDE で変更を行ってから、ページを再読み込みする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9961b-231">You do not need to make the changes in an external editor or IDE and then reload the page.</span></span>  <span data-ttu-id="9961b-232">作成したスクリプトは、DevTools で編集できます。</span><span class="sxs-lookup"><span data-stu-id="9961b-232">You may edit your script in DevTools.</span></span>  

<span data-ttu-id="9961b-233">スクリプトを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9961b-233">Complete the following actions to edit a script.</span></span>  

1.  <span data-ttu-id="9961b-234">[**ソース**] パネルの [**エディター** ] ウィンドウでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9961b-234">Open the file in the **Editor** pane of the **Sources** panel.</span></span>  
1.  <span data-ttu-id="9961b-235">[ **エディター** ] ウィンドウで変更します。</span><span class="sxs-lookup"><span data-stu-id="9961b-235">Make your changes in the **Editor** pane.</span></span>  
1.  <span data-ttu-id="9961b-236">`Ctrl` + `S` 保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="9961b-236">Press `Ctrl`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  <span data-ttu-id="9961b-237">DevTools は、JS ファイル全体を Microsoft Edge の JavaScript エンジンに更新します。</span><span class="sxs-lookup"><span data-stu-id="9961b-237">DevTools patches the entire JS file into the JavaScript engine of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="[エディター] ウィンドウ" lightbox="../media/javascript-sources-html-minified.msft.png":::
       <span data-ttu-id="9961b-239">[ **エディター** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9961b-239">The **Editor** pane</span></span>  
    :::image-end:::  
     
## <span data-ttu-id="9961b-240">JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="9961b-240">Disable JavaScript</span></span>   

<span data-ttu-id="9961b-241">「 [Microsoft Edge DevTools で JavaScript を無効にする」を][DevToolsJavascriptDisable]参照してください。</span><span class="sxs-lookup"><span data-stu-id="9961b-241">See [Disable JavaScript with Microsoft Edge DevTools][DevToolsJavascriptDisable].</span></span>  

## <span data-ttu-id="9961b-242">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="9961b-242">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageStepOverIcon]: ../media/step-over-icon.msft.png  
[ImageStepIntoIcon]: ../media/step-into-icon.msft.png  
[ImageStepOutIcon]: ../media/step-out-icon.msft.png  
[ImageResumeScriptExecutionIcon]: ../media/resume-script-run-icon.msft.png  
[ImageForceScriptExecutionIcon]: ../media/force-script-run-icon.msft.png  
[ImageAddExpressionIcon]: ../media/add-expression-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageDeleteExpressionIcon]: ../media/delete-expression-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法 |Microsoft ドキュメント"  
[DevToolsJavascriptDisable]: ./disable.md "Microsoft Edge DevTools で JavaScript を無効にする |Microsoft ドキュメント"  
[DevToolsJavascriptGetStarted]: ./index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要 |Microsoft ドキュメント"  
[DevToolsJavascriptSnippets]: ./snippets.md "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。Microsoft ドキュメント"  
[DevToolsCustomize]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  

> [!NOTE]
> <span data-ttu-id="9961b-248">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9961b-248">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9961b-249">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="9961b-249">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9961b-251">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9961b-251">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
