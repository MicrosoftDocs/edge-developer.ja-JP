---
title: JavaScript デバッグリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1d361bb39523e9b039500f46da54e60b82adbda6
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581741"
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







# <span data-ttu-id="14e7c-103">JavaScript デバッグリファレンス</span><span class="sxs-lookup"><span data-stu-id="14e7c-103">JavaScript Debugging Reference</span></span>   



<span data-ttu-id="14e7c-104">Microsoft Edge DevTools デバッグ機能の包括的なリファレンスで、新しいデバッグワークフローを見つけます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-104">Discover new debugging workflows with this comprehensive reference of Microsoft Edge DevTools debugging features.</span></span>  

<span data-ttu-id="14e7c-105">デバッグの基礎については、「 [Microsoft Edge DevTools のデバッグ JavaScript の概要][DevToolsJavascriptGetStarted]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e7c-105">See [Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted] to learn the basics of debugging.</span></span>  

## <span data-ttu-id="14e7c-106">ブレークポイントを使用したコードの一時停止</span><span class="sxs-lookup"><span data-stu-id="14e7c-106">Pause code with breakpoints</span></span>   

<span data-ttu-id="14e7c-107">ランタイムの途中でコードを一時停止できるようにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-107">Set a breakpoint so that you are able to pause your code in the middle of the runtime.</span></span>  

<span data-ttu-id="14e7c-108">ブレークポイントを設定する方法については[、「ブレークポイントを使用したコードの一時停止][DevToolsJavascriptBreakpoints]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14e7c-108">See [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints] to learn how to set breakpoints.</span></span>  

[DevToolsJavascriptBreakpoints]: breakpoints.md "Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法"  

## <span data-ttu-id="14e7c-110">ステップ実行コード</span><span class="sxs-lookup"><span data-stu-id="14e7c-110">Step through code</span></span>   

<span data-ttu-id="14e7c-111">コードが一時停止されたら、1行ずつステップ実行し、制御フローとプロパティの値を調べます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-111">Once your code is paused, step through it, one line at a time, investigating control flow and property values along the way.</span></span>  

### <span data-ttu-id="14e7c-112">コード行のステップ</span><span class="sxs-lookup"><span data-stu-id="14e7c-112">Step over line of code</span></span>   

<span data-ttu-id="14e7c-113">デバッグしている問題に関連しない関数が含まれているコード行で一時停止している場合は、**ステップオーバー**アイコンをクリックして ![ ][ImageStepOverIcon] 、この関数をステップ実行せずに実行します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-113">When paused on a line of code containing a function that is not relevant to the problem you are debugging, click on the **Step over** ![Step over][ImageStepOverIcon] icon to run the function without stepping into it.</span></span>  

> ##### <span data-ttu-id="14e7c-114">図 1</span><span class="sxs-lookup"><span data-stu-id="14e7c-114">Figure 1</span></span>  
> <span data-ttu-id="14e7c-115">**ステップオーバー**の選択</span><span class="sxs-lookup"><span data-stu-id="14e7c-115">Selecting **Step over**</span></span>  
> ![ステップオーバーの選択][ImageSelectingStepOver]  

<span data-ttu-id="14e7c-117">たとえば、次のコードをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-117">For example, suppose you are debugging the following code:</span></span>  

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

<span data-ttu-id="14e7c-118">はに一時停止 `A` しています。</span><span class="sxs-lookup"><span data-stu-id="14e7c-118">You are paused on `A`.</span></span>  <span data-ttu-id="14e7c-119">[**ステップオーバー**] を押すことで、実行している関数のすべてのコードが実行され `B` `C` ます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-119">By pressing **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span></span>  <span data-ttu-id="14e7c-120">次に、DevTools で一時停止 `D` します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-120">DevTools then pauses on `D`.</span></span>  

### <span data-ttu-id="14e7c-121">コード行のステップ</span><span class="sxs-lookup"><span data-stu-id="14e7c-121">Step into line of code</span></span>   

<span data-ttu-id="14e7c-122">デバッグしている問題に関連する関数呼び出しを含むコード行で一時停止している場合**は、[** ステップイン] アイコンをクリックし ![ て、 ][ImageStepIntoIcon] その機能をさらに調査します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-122">When paused on a line of code containing a function call that is related to the problem you are debugging, click on the **Step into** ![Step into][ImageStepIntoIcon] icon to investigate that function further.</span></span>  

> ##### <span data-ttu-id="14e7c-123">図 2</span><span class="sxs-lookup"><span data-stu-id="14e7c-123">Figure 2</span></span>  
> <span data-ttu-id="14e7c-124">**ステップイン**の選択</span><span class="sxs-lookup"><span data-stu-id="14e7c-124">Selecting **Step into**</span></span>  
> ![ステップインの選択][ImageSelectingStepInto]  

<span data-ttu-id="14e7c-126">たとえば、次のコードをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-126">For example, suppose you are debugging the following code:</span></span>  

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

<span data-ttu-id="14e7c-127">はに一時停止 `A` しています。</span><span class="sxs-lookup"><span data-stu-id="14e7c-127">You are paused on `A`.</span></span>  <span data-ttu-id="14e7c-128">**ステップイン**を押すと、devtools はこのコード行を実行し、で一時停止し `B` ます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-128">By pressing **Step into**, DevTools runs this line of code, then pauses on `B`.</span></span>  

### <span data-ttu-id="14e7c-129">コード行のステップアウト</span><span class="sxs-lookup"><span data-stu-id="14e7c-129">Step out of line of code</span></span>   

<span data-ttu-id="14e7c-130">デバッグ中の問題に関連していない関数の内部で一時停止している場合は、 **[ステップアウト**] をクリックして ![ ][ImageStepOutIcon] 関数の残りのコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-130">When paused inside of a function that is not related to the problem you are debugging, click on the **Step out** ![Step out][ImageStepOutIcon] icon to run the rest of the code of the function.</span></span>  

> ##### <span data-ttu-id="14e7c-131">図 3</span><span class="sxs-lookup"><span data-stu-id="14e7c-131">Figure 3</span></span>  
> <span data-ttu-id="14e7c-132">**手順**を選択する</span><span class="sxs-lookup"><span data-stu-id="14e7c-132">Selecting **Step out**</span></span>  
> ![手順を選択する][ImageSelectingStepOut]  

<span data-ttu-id="14e7c-134">たとえば、次のコードをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-134">For example, suppose you are debugging the following code:</span></span>  

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

<span data-ttu-id="14e7c-135">はに一時停止 `A` しています。</span><span class="sxs-lookup"><span data-stu-id="14e7c-135">You are paused on `A`.</span></span>  <span data-ttu-id="14e7c-136">[**ステップアウト**] を押すと、devtools で残りのコードが実行 `getName()` され `B` ます。これは、この例では次のように `C` なります。</span><span class="sxs-lookup"><span data-stu-id="14e7c-136">By pressing **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span></span>  

### <span data-ttu-id="14e7c-137">特定の行までのすべてのコードを実行する</span><span class="sxs-lookup"><span data-stu-id="14e7c-137">Run all code up to a specific line</span></span>   

<span data-ttu-id="14e7c-138">Long 関数をデバッグする場合、デバッグしている問題に関連していないコードが多数存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14e7c-138">When debugging a long function, there may be a lot of code that is not related to the problem you are debugging.</span></span>  

<span data-ttu-id="14e7c-139">すべての行の手順を実行することもできますが、面倒なこともあります。</span><span class="sxs-lookup"><span data-stu-id="14e7c-139">You may choose to step through all the lines, but that is tedious.</span></span>  <span data-ttu-id="14e7c-140">目的の行にコード行のブレークポイントを設定してから、[**スクリプト実行**の再開 ![ スクリプト実行] アイコンをクリックすることもでき ][ImageResumeScriptExecutionIcon] ますが、もっと簡単な方法があります。</span><span class="sxs-lookup"><span data-stu-id="14e7c-140">You may choose to set a line-of-code breakpoint on the line in which you are interested and then click on the **Resume Script Execution** ![Resume Script Execution][ImageResumeScriptExecutionIcon] icon, but there is a faster way.</span></span>  

<span data-ttu-id="14e7c-141">目的のコード行を右クリックし、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-141">Right-click the line of code in which you are interested, and select **Continue to here**.</span></span>  <span data-ttu-id="14e7c-142">DevTools では、その時点までのすべてのコードが実行され、その行が一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-142">DevTools runs all of the code up to that point, and then pauses on that line.</span></span>  

> ##### <span data-ttu-id="14e7c-143">図 4</span><span class="sxs-lookup"><span data-stu-id="14e7c-143">Figure 4</span></span>  
> <span data-ttu-id="14e7c-144">[**続行する] を**選ぶ</span><span class="sxs-lookup"><span data-stu-id="14e7c-144">Selecting **Continue to here**</span></span>  
> ![[続行する] を選ぶ][ImageSelectingContinueToHere]  

### <span data-ttu-id="14e7c-146">コールスタックの top 関数を再起動する</span><span class="sxs-lookup"><span data-stu-id="14e7c-146">Restart the top function of the call stack</span></span>   

<span data-ttu-id="14e7c-147">一時停止しているコード行で、[**通話スタック**] ウィンドウ内の任意の場所を右クリックし、[**フレームの再起動**] を選択して、呼び出し履歴の一番上の関数の1行目にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-147">While paused on a line of code, right-click anywhere in the **Call Stack** pane and select **Restart Frame** to pause on the first line of the top function in your call stack.</span></span>  <span data-ttu-id="14e7c-148">Top 関数は、最後に呼び出された関数です。</span><span class="sxs-lookup"><span data-stu-id="14e7c-148">The top function is the last function that was called.</span></span>  

<span data-ttu-id="14e7c-149">たとえば、次のコードをステップ実行しているとします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-149">For example, suppose you are stepping through the following code:</span></span>  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

<span data-ttu-id="14e7c-150">はに一時停止 `A` しています。</span><span class="sxs-lookup"><span data-stu-id="14e7c-150">You are paused on `A`.</span></span>  <span data-ttu-id="14e7c-151">[**フレームの再起動**] をクリックした後、 `B` ブレークポイントを設定したり、[**再開] スクリプト実行**を押したりしなくても、を一時停止しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e7c-151">After clicking **Restart Frame**, you should be paused on `B`, without ever setting a breakpoint or pressing **Resume script execution**.</span></span>  

> ##### <span data-ttu-id="14e7c-152">図 5</span><span class="sxs-lookup"><span data-stu-id="14e7c-152">Figure 5</span></span>  
> <span data-ttu-id="14e7c-153">[**フレームの再起動**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="14e7c-153">Selecting **Restart Frame**</span></span>  
> ![[フレームの再起動] を選ぶ][ImageSelectingRestartFrame]  

### <span data-ttu-id="14e7c-155">スクリプトランタイムを再開する</span><span class="sxs-lookup"><span data-stu-id="14e7c-155">Resume script runtime</span></span>   

<span data-ttu-id="14e7c-156">スクリプトを一時停止した後で実行を継続するには、[**スクリプト**実行の再開 ![ スクリプト実行] アイコンをクリックし ][ImageResumeScriptExecutionIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-156">To continue the runtime after a pause of your script, click on the **Resume Script Execution** ![Resume Script Execution][ImageResumeScriptExecutionIcon] icon.</span></span>  <span data-ttu-id="14e7c-157">DevTools は、次のブレークポイント (存在する場合) までスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-157">DevTools runs the script up until the next breakpoint, if any.</span></span>  

> ##### <span data-ttu-id="14e7c-158">図 6</span><span class="sxs-lookup"><span data-stu-id="14e7c-158">Figure 6</span></span>  
> <span data-ttu-id="14e7c-159">[**スクリプト実行の再開**] の選択</span><span class="sxs-lookup"><span data-stu-id="14e7c-159">Selecting **Resume script execution**</span></span>  
> ![[スクリプト実行の再開] の選択][ImageSelectingResumeScriptExecution]  

#### <span data-ttu-id="14e7c-161">スクリプトの強制実行</span><span class="sxs-lookup"><span data-stu-id="14e7c-161">Force script runtime</span></span>   

<span data-ttu-id="14e7c-162">すべてのブレークポイントを無視してスクリプトを強制的に実行し続けるには、[**スクリプト**実行の再開スクリプト実行] アイコンをクリックして、[スクリプト実行の強制実行] ![ ][ImageResumeScriptExecutionIcon] を選択し**Force script execution** ![ ][ImageForceScriptExecutionIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-162">To ignore all breakpoints and force your script to resume running, click and hold the **Resume Script Execution** ![Resume Script Execution][ImageResumeScriptExecutionIcon] icon and then select **Force script execution** ![Force script execution][ImageForceScriptExecutionIcon].</span></span>  

> ##### <span data-ttu-id="14e7c-163">図 7</span><span class="sxs-lookup"><span data-stu-id="14e7c-163">Figure 7</span></span>  
> <span data-ttu-id="14e7c-164">[**スクリプト実行の強制**] の選択</span><span class="sxs-lookup"><span data-stu-id="14e7c-164">Selecting **Force script execution**</span></span>  
> ![[スクリプト実行の強制] の選択][ImageSelectingForceScriptExecution]  

### <span data-ttu-id="14e7c-166">スレッドコンテキストの変更</span><span class="sxs-lookup"><span data-stu-id="14e7c-166">Change thread context</span></span>   

<span data-ttu-id="14e7c-167">Web ワーカーまたはサービスワーカーを操作するときに、[**スレッド**] ウィンドウに表示されているコンテキストをクリックして、そのコンテキストに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-167">When working with web workers or service workers, click on a context listed in the **Threads** pane to switch to that context.</span></span>  <span data-ttu-id="14e7c-168">青い矢印のアイコンは、現在選択されているコンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-168">The blue arrow icon represents which context is currently selected.</span></span>  

> ##### <span data-ttu-id="14e7c-169">図 8</span><span class="sxs-lookup"><span data-stu-id="14e7c-169">Figure 8</span></span>  
> <span data-ttu-id="14e7c-170">[**スレッド**] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="14e7c-170">The **Threads** pane</span></span>  
> ![[スレッド] ウィンドウ][ImageThreadsPane]  

<span data-ttu-id="14e7c-172">たとえば、メインスクリプトとサービスワーカースクリプトの両方のブレークポイントで一時停止しているとします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-172">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span></span>  <span data-ttu-id="14e7c-173">サービスワーカーコンテキストのローカルプロパティとグローバルプロパティを表示する必要があるが、[**ソース**] パネルにはメインスクリプトコンテキストが表示されています。</span><span class="sxs-lookup"><span data-stu-id="14e7c-173">You want to view the local and global properties for the service worker context, but the **Sources** panel is showing the main script context.</span></span>  <span data-ttu-id="14e7c-174">[**スレッド**] ウィンドウで service worker エントリをクリックすると、そのコンテキストに切り替えることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="14e7c-174">By clicking on the service worker entry in the **Threads** pane, you should be able to switch to that context.</span></span>  

## <span data-ttu-id="14e7c-175">ローカル、クロージャ、グローバルプロパティの表示と編集</span><span class="sxs-lookup"><span data-stu-id="14e7c-175">View and edit local, closure, and global properties</span></span>   

<span data-ttu-id="14e7c-176">コード行で一時停止している間に、**スコープ**ウィンドウを使って、ローカル、クロージャ、グローバルスコープのプロパティと変数の値を表示および編集します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-176">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span></span>  

*   <span data-ttu-id="14e7c-177">プロパティ値をダブルクリックして変更します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-177">Double-click a property value to change it.</span></span>  
*   <span data-ttu-id="14e7c-178">列挙可能でないプロパティは灰色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-178">Non-enumerable properties are greyed out.</span></span>  

> ##### <span data-ttu-id="14e7c-179">図 9</span><span class="sxs-lookup"><span data-stu-id="14e7c-179">Figure 9</span></span>  
> <span data-ttu-id="14e7c-180">**スコープ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="14e7c-180">The **Scope** pane</span></span>  
> ![スコープウィンドウ][ImageScopePane]  

## <span data-ttu-id="14e7c-182">現在の通話履歴を表示する</span><span class="sxs-lookup"><span data-stu-id="14e7c-182">View the current call stack</span></span>   

<span data-ttu-id="14e7c-183">一時停止しているコード行では、[**通話スタック**] ウィンドウを使って、この時点までの呼び出し履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-183">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span></span>  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

<span data-ttu-id="14e7c-184">エントリをクリックすると、その関数が呼び出されたコード行にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-184">Click on an entry to jump to the line of code where that function was called.</span></span>  <span data-ttu-id="14e7c-185">青色の矢印アイコンは、現在の DevTools が現在強調表示されている関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="14e7c-185">The blue arrow icon represents which function DevTools is currently highlighting.</span></span>  

> ##### <span data-ttu-id="14e7c-186">図 10</span><span class="sxs-lookup"><span data-stu-id="14e7c-186">Figure 10</span></span>  
> <span data-ttu-id="14e7c-187">[**通話スタック**] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="14e7c-187">The **Call Stack** pane</span></span>  
> ![[通話スタック] ウィンドウ][ImageCallStackPane]  

> [!NOTE]
> <span data-ttu-id="14e7c-189">コード行で一時停止していない場合、[**呼び出し履歴**] ウィンドウは空です。</span><span class="sxs-lookup"><span data-stu-id="14e7c-189">When not paused on a line of code, the **Call Stack** pane is empty.</span></span>  

### <span data-ttu-id="14e7c-190">スタックトレースのコピー</span><span class="sxs-lookup"><span data-stu-id="14e7c-190">Copy stack trace</span></span>   

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

<span data-ttu-id="14e7c-191">[**通話スタック**] ウィンドウ内の任意の場所を右クリックし、[**スタックトレースのコピー** ] を選択して、現在の呼び出し履歴をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-191">Right-click anywhere in the **Call Stack** pane and select **Copy stack trace** to copy the current call stack to the clipboard.</span></span>  

> ##### <span data-ttu-id="14e7c-192">図 11</span><span class="sxs-lookup"><span data-stu-id="14e7c-192">Figure 11</span></span>  
> <span data-ttu-id="14e7c-193">**コピースタックトレース**の選択</span><span class="sxs-lookup"><span data-stu-id="14e7c-193">Selecting **Copy Stack Trace**</span></span>  
> ![コピースタックトレースの選択][ImageSelectingCopyStackTrace]  

<span data-ttu-id="14e7c-195">出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-195">Below is an example of the output:</span></span>  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onClick (get-started.js:15)
```  

## <span data-ttu-id="14e7c-196">スクリプトまたはスクリプトのパターンを無視する</span><span class="sxs-lookup"><span data-stu-id="14e7c-196">Ignore a script or pattern of scripts</span></span>  

<span data-ttu-id="14e7c-197">デバッグ中にそのスクリプトを無視する場合は、スクリプトをライブラリコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-197">Mark a script as Library code when you want to ignore that script while debugging.</span></span>  <span data-ttu-id="14e7c-198">ライブラリコードとしてマークされている場合、スクリプトは [**呼び出し履歴**] ウィンドウで隠されており、コードのステップ実行時にスクリプトの関数にはステップインしません。</span><span class="sxs-lookup"><span data-stu-id="14e7c-198">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span></span>  

<span data-ttu-id="14e7c-199">たとえば、次のコードをステップ実行しているとします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-199">For example, suppose you are stepping through this code:</span></span>  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` <span data-ttu-id="14e7c-200">は、信頼できるサードパーティのライブラリです。</span><span class="sxs-lookup"><span data-stu-id="14e7c-200">is a third-party library that you trust.</span></span>  <span data-ttu-id="14e7c-201">デバッグ中の問題がサードパーティのライブラリに関連していないことがわかっている場合は、スクリプトを**ライブラリコード**としてマークすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-201">If you are confident that the problem you are debugging is not related to the third-party library, then it makes sense to mark the script as **Library code**.</span></span>  

### <span data-ttu-id="14e7c-202">[エディター] ウィンドウからスクリプトをライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="14e7c-202">Mark a script as Library code from the Editor pane</span></span>  

<span data-ttu-id="14e7c-203">スクリプトを**エディター**ウィンドウから**ライブラリコード**としてマークするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="14e7c-203">To mark a script as **Library code** from the **Editor** pane:</span></span>  

1.  <span data-ttu-id="14e7c-204">ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-204">Open the file.</span></span>  
1.  <span data-ttu-id="14e7c-205">任意の場所を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-205">Right-click anywhere.</span></span>  
1.  <span data-ttu-id="14e7c-206">[ **Library code としてマーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-206">Select **Mark as Library code**.</span></span>  

> ##### <span data-ttu-id="14e7c-207">図 12</span><span class="sxs-lookup"><span data-stu-id="14e7c-207">Figure 12</span></span>  
> <span data-ttu-id="14e7c-208">**エディター**ウィンドウからスクリプトを**ライブラリコード**としてマークする</span><span class="sxs-lookup"><span data-stu-id="14e7c-208">Marking a script as **Library code** from the **Editor** pane</span></span>  
> ![エディターウィンドウからスクリプトをライブラリコードとしてマークする][ImageMarkEditorPane]  

### <span data-ttu-id="14e7c-210">[呼び出し履歴] ウィンドウからスクリプトをライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="14e7c-210">Mark a script as Library code from the Call Stack pane</span></span>  

<span data-ttu-id="14e7c-211">**呼び出し履歴**ウィンドウからスクリプトを**ライブラリコード**としてマークするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="14e7c-211">To mark a script as **Library code** from the **Call Stack** pane:</span></span>  

1.  <span data-ttu-id="14e7c-212">スクリプトから関数を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-212">Right-click on a function from the script.</span></span>  
1.  <span data-ttu-id="14e7c-213">[ **Library code としてマーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-213">Select **Mark as Library code**.</span></span>  

> ##### <span data-ttu-id="14e7c-214">図 13</span><span class="sxs-lookup"><span data-stu-id="14e7c-214">Figure 13</span></span>  
> <span data-ttu-id="14e7c-215">**呼び出し履歴**ウィンドウからスクリプトを**ライブラリコード**としてマークする</span><span class="sxs-lookup"><span data-stu-id="14e7c-215">Marking a script as **Library code** from the **Call Stack** pane</span></span>  
> ![呼び出し履歴ウィンドウからスクリプトをライブラリコードとしてマークする][ImageMarkCallStackPane]  

### <span data-ttu-id="14e7c-217">設定からスクリプトをライブラリコードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="14e7c-217">Mark a script as Library code from Settings</span></span>  

<span data-ttu-id="14e7c-218">1つのスクリプトまたはスクリプトのパターンを設定からマークするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="14e7c-218">To mark a single script or pattern of scripts from Settings:</span></span>  

1.  <span data-ttu-id="14e7c-219">[[設定][DevToolsCustomize]] を開きます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-219">Open [Settings][DevToolsCustomize].</span></span>  
1.  <span data-ttu-id="14e7c-220">[**ライブラリコード**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-220">Go to the **Library code** tab.</span></span>  
1.  <span data-ttu-id="14e7c-221">[**パターンの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-221">Click **Add pattern**.</span></span>  
1.  <span data-ttu-id="14e7c-222">**ライブラリコード**としてマークするスクリプト名またはスクリプト名の regex パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-222">Enter the script name or a regex pattern of script names to mark as **Library code**.</span></span>  
1.  <span data-ttu-id="14e7c-223">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-223">Click **Add**.</span></span>  

> ##### <span data-ttu-id="14e7c-224">図 14</span><span class="sxs-lookup"><span data-stu-id="14e7c-224">Figure 14</span></span>  
> <span data-ttu-id="14e7c-225">設定からスクリプトを**ライブラリコード**としてマークする</span><span class="sxs-lookup"><span data-stu-id="14e7c-225">Marking a script as **Library code** from Settings</span></span>  
> ![設定からスクリプトをライブラリコードとしてマークする][ImageMarkScriptSettings]  

## <span data-ttu-id="14e7c-227">任意のページからデバッグコードのスニペットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-227">Run snippets of debug code from any page</span></span>   

<span data-ttu-id="14e7c-228">本体で同じデバッグコードを繰り返し実行していることがわかった場合は、スニペットを検討してください。</span><span class="sxs-lookup"><span data-stu-id="14e7c-228">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span></span>  <span data-ttu-id="14e7c-229">スニペットは、DevTools 内で作成、保存、実行するランタイムスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="14e7c-229">Snippets are runtime scripts that you author, store, and run within DevTools.</span></span>  

<span data-ttu-id="14e7c-230">詳細については[、「任意のページからコードのスニペットを実行][DevToolsJavascriptSnippets]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e7c-230">See [Run Snippets of Code From Any Page][DevToolsJavascriptSnippets] to learn more.</span></span>  

## <span data-ttu-id="14e7c-231">カスタム JavaScript 式の値を見る</span><span class="sxs-lookup"><span data-stu-id="14e7c-231">Watch the values of custom JavaScript expressions</span></span>   

<span data-ttu-id="14e7c-232">**ウォッチ**ウィンドウを使用して、カスタム式の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-232">Use the **Watch** pane to watch the values of custom expressions.</span></span>  <span data-ttu-id="14e7c-233">有効な JavaScript 式を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-233">You may watch any valid JavaScript expression.</span></span>  

> ##### <span data-ttu-id="14e7c-234">図 15</span><span class="sxs-lookup"><span data-stu-id="14e7c-234">Figure 15</span></span>  
> <span data-ttu-id="14e7c-235">**ウォッチ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="14e7c-235">The **Watch** pane</span></span>  
> ![ウォッチウィンドウ][ImageWatchPane]  

*   <span data-ttu-id="14e7c-237">**Add Expression** ![ 新しいウォッチ式を作成するには、[式の追加 ][ImageAddExpressionIcon] ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-237">Click on the **Add Expression** ![Add Expression][ImageAddExpressionIcon] icon to create a new watch expression.</span></span>  
*   <span data-ttu-id="14e7c-238">[更新更新] をクリックし**て、** ![ ][ImageRefreshIcon] すべての既存の式の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-238">Click on the **Refresh** ![Refresh][ImageRefreshIcon] icon to refresh the values of all existing expressions.</span></span>  <span data-ttu-id="14e7c-239">値は、コードをステップ実行して自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-239">Values automatically refresh while stepping through code.</span></span>  
*   <span data-ttu-id="14e7c-240">式の上にマウスポインターを置いて、[**式**の削除] を削除し ![ ][ImageDeleteExpressionIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-240">Hover over an expression and click on the **Delete Expression** ![Delete Expression][ImageDeleteExpressionIcon] icon to delete it.</span></span>  

## <span data-ttu-id="14e7c-241">ファイルを読みやすくする</span><span class="sxs-lookup"><span data-stu-id="14e7c-241">Make a minified file readable</span></span>   

<span data-ttu-id="14e7c-242">[書式の**書式**設定] アイコンをクリックして、 ![ 表示 ][ImageFormatIcon] したファイルを手動で読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="14e7c-242">Click on the **Format** ![Format][ImageFormatIcon] icon to make a minified file human-readable.</span></span>  

> ##### <span data-ttu-id="14e7c-243">図 16</span><span class="sxs-lookup"><span data-stu-id="14e7c-243">Figure 16</span></span>  
> <span data-ttu-id="14e7c-244">[**書式**] ボタン</span><span class="sxs-lookup"><span data-stu-id="14e7c-244">The **Format** button</span></span>  
> ![[書式] ボタン][ImageFormat]  

## <span data-ttu-id="14e7c-246">スクリプトを編集する</span><span class="sxs-lookup"><span data-stu-id="14e7c-246">Edit a script</span></span>   

<span data-ttu-id="14e7c-247">バグを修正する場合、多くの場合、JavaScript コードに加えられた変更をいくつかテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e7c-247">When fixing a bug, you often want to test out some changes to your JavaScript code.</span></span>  <span data-ttu-id="14e7c-248">外部のエディターまたは IDE で変更を行ってから、ページを再読み込みする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14e7c-248">You do not need to make the changes in an external editor or IDE and then reload the page.</span></span>  <span data-ttu-id="14e7c-249">作成したスクリプトは、DevTools で編集できます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-249">You may edit your script in DevTools.</span></span>  

<span data-ttu-id="14e7c-250">スクリプトを編集するには:</span><span class="sxs-lookup"><span data-stu-id="14e7c-250">To edit a script:</span></span>  

1.  <span data-ttu-id="14e7c-251">[**ソース**] パネルの [**エディター** ] ウィンドウでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-251">Open the file in the **Editor** pane of the **Sources** panel.</span></span>  
1.  <span data-ttu-id="14e7c-252">[**エディター** ] ウィンドウで変更します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-252">Make your changes in the **Editor** pane.</span></span>  
1.  <span data-ttu-id="14e7c-253">`Ctrl` + `S` 保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-253">Press `Ctrl`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  <span data-ttu-id="14e7c-254">DevTools は、JS ファイル全体を Microsoft Edge の JavaScript エンジンに更新します。</span><span class="sxs-lookup"><span data-stu-id="14e7c-254">DevTools patches the entire JS file into the JavaScript engine of Microsoft Edge.</span></span>  

> ##### <span data-ttu-id="14e7c-255">図 17</span><span class="sxs-lookup"><span data-stu-id="14e7c-255">Figure 17</span></span>  
> <span data-ttu-id="14e7c-256">[**エディター** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="14e7c-256">The **Editor** pane</span></span>  
> ![[エディター] ウィンドウ][ImageEditorPane]  

## <span data-ttu-id="14e7c-258">JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="14e7c-258">Disable JavaScript</span></span>   

<span data-ttu-id="14e7c-259">「 [Microsoft Edge DevTools で JavaScript を無効にする」を][DevToolsJavascriptDisable]参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e7c-259">See [Disable JavaScript With Microsoft Edge DevTools][DevToolsJavascriptDisable].</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageStepOverIcon]: /microsoft-edge/devtools-guide-chromium/media/step-over-icon.msft.png  
[ImageStepIntoIcon]: /microsoft-edge/devtools-guide-chromium/media/step-into-icon.msft.png  
[ImageStepOutIcon]: /microsoft-edge/devtools-guide-chromium/media/step-out-icon.msft.png  
[ImageResumeScriptExecutionIcon]: /microsoft-edge/devtools-guide-chromium/media/resume-script-run-icon.msft.png  
[ImageForceScriptExecutionIcon]: /microsoft-edge/devtools-guide-chromium/media/force-script-run-icon.msft.png  
[ImageAddExpressionIcon]: /microsoft-edge/devtools-guide-chromium/media/add-expression-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  
[ImageDeleteExpressionIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-expression-icon.msft.png  
[ImageFormatIcon]: /microsoft-edge/devtools-guide-chromium/media/format-icon.msft.png  

[ImageSelectingStepOver]: /microsoft-edge/devtools-guide-chromium/media/javascript-source-page-debugger-step-over-next-function-call.msft.png "図 1: ステップオーバーの選択"  
[ImageSelectingStepInto]: /microsoft-edge/devtools-guide-chromium/media/javascript-source-page-debugger-step-into-next-function-call.msft.png "図 2: 手順を選択する"  
[ImageSelectingStepOut]: /microsoft-edge/devtools-guide-chromium/media/javascript-source-page-debugger-step-out-of-current-function.msft.png "図 3: 手順を選択する"  
[ImageSelectingContinueToHere]: /microsoft-edge/devtools-guide-chromium/media/javascript-source-page-continue-to-here.msft.png "図 4: [続行] を選択する"  
[ImageSelectingRestartFrame]: /microsoft-edge/devtools-guide-chromium/media/javascript-source-page-debugger-restart-frame.msft.png "図 5: [フレームの再起動] の選択"  
[ImageSelectingResumeScriptExecution]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-get-started-js-resume-script-runtime.msft.png "図 6: スクリプト実行の再開の選択"  
[ImageSelectingForceScriptExecution]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-get-started-js-force-script-runtime.msft.png "図 7: [スクリプト実行の強制] の選択"  
[ImageThreadsPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-main-min-js-threads.msft.png "図 8: [スレッド] ウィンドウ"  
[ImageScopePane]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-get-started-js-scope.msft.png "図 9: スコープウィンドウ"  
[ImageCallStackPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png "図 10: [通話スタック] ウィンドウ"  
[ImageSelectingCopyStackTrace]: /microsoft-edge/devtools-guide-chromium/media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png "図 11: コピースタックトレースの選択"  
[ImageMarkEditorPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png "図 12: エディターウィンドウからスクリプトをライブラリコードとしてマークする"  
[ImageMarkCallStackPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png "図 13: [呼び出し履歴] ウィンドウからスクリプトをライブラリコードとしてマークする"  
[ImageMarkScriptSettings]: /microsoft-edge/devtools-guide-chromium/media/javascript-framework-library-code.msft.png "図 14: 設定からスクリプトをライブラリコードとしてマークする"  
[ImageWatchPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-get-started-js-watch.msft.png "図 15: [ウォッチ] ウィンドウ"  
[ImageFormat]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-html-non-minified.msft.png "図 16: [書式] ボタン"  
[ImageEditorPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-html-minified.msft.png "図 17: [エディター] ウィンドウ"  

<!-- links -->  

[DevToolsJavascriptDisable]: disable.md "Microsoft Edge DevTools で JavaScript を無効にする"  
[DevToolsJavascriptGetStarted]: index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要"  
[DevToolsJavascriptSnippets]: snippets.md "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。"  

[DevToolsCustomize]: ../customize/index.md "Microsoft Edge DevTools をカスタマイズする"  

> [!NOTE]
> <span data-ttu-id="14e7c-281">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="14e7c-281">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="14e7c-282">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="14e7c-282">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="14e7c-284">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="14e7c-284">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
