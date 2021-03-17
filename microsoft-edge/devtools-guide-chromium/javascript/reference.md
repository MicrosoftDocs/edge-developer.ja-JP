---
description: Microsoft Edge DevTools デバッグ機能の包括的なリファレンスで、新しいデバッグ ワークフローについて説明します。
title: JavaScript デバッグ リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2944e054a08a901d2e1752fa7c4e48ae110f5787
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439459"
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

# <a name="javascript-debugging-reference"></a><span data-ttu-id="ae3cb-104">JavaScript デバッグ リファレンス</span><span class="sxs-lookup"><span data-stu-id="ae3cb-104">JavaScript debugging reference</span></span>  

<span data-ttu-id="ae3cb-105">Microsoft Edge DevTools デバッグ機能の包括的な参照を使用して、新しいデバッグ ワークフローを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-105">Discover new debugging workflows with the following comprehensive reference of Microsoft Edge DevTools debugging features.</span></span>  

<span data-ttu-id="ae3cb-106">デバッグの基本については [、「Microsoft Edge DevTools][DevToolsJavascriptGetStarted]での JavaScript のデバッグの開始」に移動します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-106">To learn the basics of debugging, navigate to [Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted].</span></span>  

## <a name="pause-code-with-breakpoints"></a><span data-ttu-id="ae3cb-107">ブレークポイントを使用してコードを一時停止する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-107">Pause code with breakpoints</span></span>  

<span data-ttu-id="ae3cb-108">ブレークポイントを設定して、ランタイムの途中でコードを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-108">Set a breakpoint so that you are able to pause your code in the middle of the runtime.</span></span>  

<span data-ttu-id="ae3cb-109">ブレークポイントを設定する方法については、「ブレークポイントを使用してコード [を一時停止する」に移動します][DevToolsJavascriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-109">To learn how to set breakpoints, navigate to [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

## <a name="step-through-code"></a><span data-ttu-id="ae3cb-110">コードのステップスルー</span><span class="sxs-lookup"><span data-stu-id="ae3cb-110">Step through code</span></span>  

<span data-ttu-id="ae3cb-111">コードを一時停止したら、一度に 1 行に 1 行の手順を実行し、その途中で制御フローとプロパティ値を調査します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-111">Once your code is paused, step through it, one line at a time, investigating control flow and property values along the way.</span></span>  

### <a name="step-over-line-of-code"></a><span data-ttu-id="ae3cb-112">一行のコードをステップ オーバーする</span><span class="sxs-lookup"><span data-stu-id="ae3cb-112">Step over line of code</span></span>  

<span data-ttu-id="ae3cb-113">デバッグ中の問題に関係のない関数を含むコード行で一時停止した場合は、[Step **over** \( ![ Step over \) ] ボタンを選択して、ステップ インせずに関数を実行します。 ](../media/step-over-icon.msft.png)</span><span class="sxs-lookup"><span data-stu-id="ae3cb-113">When paused on a line of code containing a function that is not relevant to the problem you are debugging, choose the **Step over** \(![Step over](../media/step-over-icon.msft.png)\) button to run the function without stepping into it.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="[ステップ オーバー] を選択する" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   <span data-ttu-id="ae3cb-115">[ステップ **オーバー] を選択する**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-115">Choose **Step over**</span></span>  
:::image-end:::  

<span data-ttu-id="ae3cb-116">たとえば、次のコード スニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-116">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="ae3cb-117">一時停止中です `A` 。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-117">You are paused on `A`.</span></span>  <span data-ttu-id="ae3cb-118">[ステップ オーバー **] を選択した**後、DevTools は、ステップ オーバーする関数内のすべてのコードを実行します。つまり `B` 、 `C` です。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-118">After you choose **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span></span>  <span data-ttu-id="ae3cb-119">DevTools は次に一時停止します `D` 。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-119">DevTools then pauses on `D`.</span></span>  

### <a name="step-into-line-of-code"></a><span data-ttu-id="ae3cb-120">コード行へのステップ</span><span class="sxs-lookup"><span data-stu-id="ae3cb-120">Step into line of code</span></span>  

<span data-ttu-id="ae3cb-121">デバッグ中の問題に関連する関数呼び出しを含むコード行で一時停止した場合は、[\( Step **to** ![ \) ] ボタンを選択して、その関数をさらに調査します ](../media/step-into-icon.msft.png) 。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-121">When paused on a line of code containing a function call that is related to the problem you are debugging, choose the **Step into** \(![Step into](../media/step-into-icon.msft.png)\) button to investigate that function further.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="[ステップ の実行] を選択します。" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   <span data-ttu-id="ae3cb-123">[ステップ **の実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-123">Choose **Step into**</span></span>  
:::image-end:::  

<span data-ttu-id="ae3cb-124">たとえば、次のコード スニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-124">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="ae3cb-125">一時停止中です `A` 。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-125">You are paused on `A`.</span></span>  <span data-ttu-id="ae3cb-126">[ステップ イン **] を選択すると**、DevTools はコード行を実行し、次に一時停止します `B` 。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-126">After you choose **Step into**, DevTools runs this line of code, then pauses on `B`.</span></span>  

### <a name="step-out-of-line-of-code"></a><span data-ttu-id="ae3cb-127">コード行からステップアウトする</span><span class="sxs-lookup"><span data-stu-id="ae3cb-127">Step out of line of code</span></span>  

<span data-ttu-id="ae3cb-128">デバッグ中の問題に関連しない関数の内部で一時停止した場合は、[ステップ アウト] \( Step **out** \) ボタンを選択して、関数の残りのコードを ![ ](../media/step-out-icon.msft.png) 実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-128">When paused inside of a function that is not related to the problem you are debugging, choose the **Step out** \(![Step out](../media/step-out-icon.msft.png)\) button to run the rest of the code of the function.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="[ステップ アウト] を選択する" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   <span data-ttu-id="ae3cb-130">[ステップ **アウト] を選択する**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-130">Choose **Step out**</span></span>  
:::image-end:::  

<span data-ttu-id="ae3cb-131">たとえば、次のコード スニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-131">For example, suppose you are debugging the following code snippet.</span></span>  

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

<span data-ttu-id="ae3cb-132">一時停止中です `A` 。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-132">You are paused on `A`.</span></span>  <span data-ttu-id="ae3cb-133">[ステップ アウト **] を選択**すると、DevTools はコードの残りの部分を実行します 。これは、この例に示すだけで、次に `getName()` `B` 一時停止します `C` 。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-133">After you choose **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span></span>  

### <a name="run-all-code-up-to-a-specific-line"></a><span data-ttu-id="ae3cb-134">特定の行まですべてのコードを実行する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-134">Run all code up to a specific line</span></span>  

<span data-ttu-id="ae3cb-135">長い関数をデバッグする場合、デバッグ中の問題とは関係ないコードが多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-135">When debugging a long function, there may be a lot of code that is not related to the problem you are debugging.</span></span>  

<span data-ttu-id="ae3cb-136">すべての行をステップスルーすることを選択できますが、これは時間のかかっています。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-136">You may choose to step through all the lines, but that is tedious.</span></span>  <span data-ttu-id="ae3cb-137">必要な行にコード行ブレークポイントを設定し、[スクリプト実行の再開 **\(** スクリプト実行の再開 ![ \)] ボタンを選択することもできますが、より高速な方法 ](../media/resume-script-run-icon.msft.png) があります。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-137">You may choose to set a line-of-code breakpoint on the line in which you are interested and then choose the **Resume Script Execution** \(![Resume Script Execution](../media/resume-script-run-icon.msft.png)\) button, but there is a faster way.</span></span>  

<span data-ttu-id="ae3cb-138">目的のコード行にカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[続行] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-138">Hover on the line of code in which you are interested, open the contextual menu \(right-click\), and choose **Continue to here**.</span></span>  <span data-ttu-id="ae3cb-139">DevTools は、その時点まですべてのコードを実行し、その行で一時停止します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-139">DevTools runs all of the code up to that point, and then pauses on that line.</span></span>  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="[次へ] を選択します。" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   <span data-ttu-id="ae3cb-141">[次 **へ] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-141">Choose **Continue to here**</span></span>  
:::image-end:::  

### <a name="restart-the-top-function-of-the-call-stack"></a><span data-ttu-id="ae3cb-142">呼び出し履歴のトップ関数を再起動する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-142">Restart the top function of the call stack</span></span>  

<span data-ttu-id="ae3cb-143">呼び出し履歴内のトップ関数の最初の行で一時停止し、コード行で一時停止している間は、[通話履歴\*\*\*\*] ウィンドウの任意の場所にマウス ポインターを移動し、コンテキスト\*\*\*\* メニュー \(右クリック\) を開き、[フレームの再起動] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-143">To pause on the first line of the top function in your call stack, while paused on a line of code, hover anywhere in the **Call Stack** pane, open the contextual menu \(right-click\), and choose **Restart Frame**.</span></span>  <span data-ttu-id="ae3cb-144">トップ関数は、最後に実行された関数です。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-144">The top function is the last function that was run.</span></span>  

<span data-ttu-id="ae3cb-145">次のコード スニペットは、手順を実行する例です。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-145">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

<span data-ttu-id="ae3cb-146">一時停止中です `A` 。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-146">You are paused on `A`.</span></span>  <span data-ttu-id="ae3cb-147">[フレームの **再起動]** を選択した後は、ブレークポイントを設定したり、[スクリプトの実行の再開] を選択したりせずに、一 `B` **時停止する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-147">After choosing **Restart Frame**, you should be paused on `B`, without ever setting a breakpoint or choosing **Resume script execution**.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="[フレームの再起動] を選択する" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   <span data-ttu-id="ae3cb-149">[フレーム **の再起動] を選択する**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-149">Choose **Restart Frame**</span></span>  
:::image-end:::  

### <a name="resume-script-runtime"></a><span data-ttu-id="ae3cb-150">スクリプト ランタイムの再開</span><span class="sxs-lookup"><span data-stu-id="ae3cb-150">Resume script runtime</span></span>  

<span data-ttu-id="ae3cb-151">スクリプトの一時停止後にランタイムを続行するには、[スクリプトの実行の再開 \( Resume Script **Execution** ![ ](../media/resume-script-run-icon.msft.png) \) ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-151">To continue the runtime after a pause of your script, choose the **Resume Script Execution** \(![Resume Script Execution](../media/resume-script-run-icon.msft.png)\) button.</span></span>  <span data-ttu-id="ae3cb-152">DevTools は、次のブレークポイントがある場合は、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-152">DevTools runs the script up until the next breakpoint, if any.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="[スクリプトの実行の再開] を選択します。" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   <span data-ttu-id="ae3cb-154">[スクリプト **の実行の再開] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-154">Choose **Resume script execution**</span></span>  
:::image-end:::  

#### <a name="force-script-runtime"></a><span data-ttu-id="ae3cb-155">強制スクリプト ランタイム</span><span class="sxs-lookup"><span data-stu-id="ae3cb-155">Force script runtime</span></span>  

<span data-ttu-id="ae3cb-156">すべてのブレークポイントを無視してスクリプトの実行を強制的に再開するには、[スクリプトの実行を**再開する**]\( スクリプト実行の再開 \) ボタンを選択し、スクリプトの実行を強制する \( 強制スクリプト実行 ![ ](../media/resume-script-run-icon.msft.png) \*\*\*\* ![ ](../media/force-script-run-icon.msft.png) \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-156">To ignore all breakpoints and force your script to resume running, choose and hold the **Resume Script Execution** \(![Resume Script Execution](../media/resume-script-run-icon.msft.png)\) button and then choose the **Force script execution** \(![Force script execution](../media/force-script-run-icon.msft.png)\) button.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="[スクリプトの実行を強制する] を選択する" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   <span data-ttu-id="ae3cb-158">[スクリプト **の実行を強制する] を選択する**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-158">Choose **Force script execution**</span></span>  
:::image-end:::  

### <a name="change-thread-context"></a><span data-ttu-id="ae3cb-159">スレッド コンテキストの変更</span><span class="sxs-lookup"><span data-stu-id="ae3cb-159">Change thread context</span></span>  

<span data-ttu-id="ae3cb-160">Web ワーカーまたはサービス ワーカーを操作する場合は、[スレッド] ウィンドウに表示\*\*\*\* されているコンテキストを選択して、そのコンテキストに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-160">When working with web workers or service workers, choose on a context listed in the **Threads** pane to switch to that context.</span></span>  <span data-ttu-id="ae3cb-161">青い矢印アイコンは、現在選択されているコンテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-161">The blue arrow icon represents which context is currently selected.</span></span>  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="[スレッド] ウィンドウ" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   <span data-ttu-id="ae3cb-163">[ **スレッド]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="ae3cb-163">The **Threads** pane</span></span>  
:::image-end:::  

<span data-ttu-id="ae3cb-164">たとえば、メイン スクリプトとサービス ワーカー スクリプトの両方のブレークポイントで一時停止したとします。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-164">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span></span>  <span data-ttu-id="ae3cb-165">サービス ワーカー コンテキストのローカル プロパティとグローバル プロパティを表示する場合\*\*\*\* は、[ソース] パネルにメイン スクリプト コンテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-165">You want to view the local and global properties for the service worker context, but the **Sources** panel is showing the main script context.</span></span>  <span data-ttu-id="ae3cb-166">[スレッド] ウィンドウでサービス ワーカー\*\*\*\* エントリを選択すると、そのコンテキストに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-166">By choosing on the service worker entry in the **Threads** pane, you should be able to switch to that context.</span></span>  

## <a name="view-and-edit-local-closure-and-global-properties"></a><span data-ttu-id="ae3cb-167">ローカル、クロージャ、およびグローバル プロパティの表示と編集</span><span class="sxs-lookup"><span data-stu-id="ae3cb-167">View and edit local, closure, and global properties</span></span>  

<span data-ttu-id="ae3cb-168">コード行で一時停止中に、[スコープ]\*\*\*\* ウィンドウを使用して、ローカル スコープ、クロージャ スコープ、およびグローバル スコープ内のプロパティと変数の値を表示および編集します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-168">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span></span>  

*   <span data-ttu-id="ae3cb-169">プロパティ値をダブルクリックして変更します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-169">Double-click a property value to change it.</span></span>  
*   <span data-ttu-id="ae3cb-170">列挙できないプロパティは灰色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-170">Non-enumerable properties are greyed out.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="[スコープ] ウィンドウ" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   <span data-ttu-id="ae3cb-172">[ **スコープ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="ae3cb-172">The **Scope** pane</span></span>  
:::image-end:::  

## <a name="view-the-current-call-stack"></a><span data-ttu-id="ae3cb-173">現在の呼び出し履歴を表示する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-173">View the current call stack</span></span>  

<span data-ttu-id="ae3cb-174">コード行で一時停止中に、[呼び出\*\*\*\* し履歴] ウィンドウを使用して、この時点に移動した通話履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-174">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span></span>  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

<span data-ttu-id="ae3cb-175">その関数が呼び出されたコード行にジャンプするエントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-175">Choose an entry to jump to the line of code where that function was called.</span></span>  <span data-ttu-id="ae3cb-176">青い矢印アイコンは、DevTools が現在強調表示している関数を表します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-176">The blue arrow icon represents which function DevTools is currently highlighting.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="[通話履歴] ウィンドウ" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   <span data-ttu-id="ae3cb-178">[ **通話履歴]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="ae3cb-178">The **Call Stack** pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="ae3cb-179">コード行で一時停止しない場合、[呼び出 **し履歴]** ウィンドウは空です。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-179">When not paused on a line of code, the **Call Stack** pane is empty.</span></span>  

### <a name="copy-stack-trace"></a><span data-ttu-id="ae3cb-180">スタック トレースのコピー</span><span class="sxs-lookup"><span data-stu-id="ae3cb-180">Copy stack trace</span></span>  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

<span data-ttu-id="ae3cb-181">現在の呼び出し履歴をクリップボードにコピーするには、[通話履歴\*\*\*\*] ウィンドウの任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[スタック トレースのコピー] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-181">to copy the current call stack to the clipboard, hover anywhere in the **Call Stack** pane, open the contextual menu \(right-click\), and choose **Copy stack trace**.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="[スタック トレースのコピー] を選択する" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   <span data-ttu-id="ae3cb-183">[スタック **トレースのコピー] を選択する**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-183">Choose **Copy Stack Trace**</span></span>  
:::image-end:::  

<span data-ttu-id="ae3cb-184">次のコード スニペットは、出力の例です。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-184">The following code snippet is an example of the output.</span></span>  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onChoose (get-started.js:15)
```  

## <a name="ignore-a-script-or-pattern-of-scripts"></a><span data-ttu-id="ae3cb-185">スクリプトまたはスクリプトのパターンを無視する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-185">Ignore a script or pattern of scripts</span></span>  

<span data-ttu-id="ae3cb-186">デバッグ中にスクリプトを無視する場合は、スクリプトをライブラリ コードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-186">Mark a script as Library code when you want to ignore that script while debugging.</span></span>  <span data-ttu-id="ae3cb-187">ライブラリ コードとしてマークされている場合、スクリプトは [呼び\*\*\*\* 出し履歴] ウィンドウで見えなされ、コードをステップ実行するときにスクリプトの機能にステップ インする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-187">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span></span>  

<span data-ttu-id="ae3cb-188">次のコード スニペットは、手順を実行する例です。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-188">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` <span data-ttu-id="ae3cb-189">は、信頼できるサード パーティ製のライブラリです。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-189">is a third-party library that you trust.</span></span>  <span data-ttu-id="ae3cb-190">デバッグ中の問題がサード パーティ製ライブラリに関連していないと確信している場合は、スクリプトをライブラリ コードとしてマークする方 **が理にかなっています**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-190">If you are confident that the problem you are debugging is not related to the third-party library, then it makes sense to mark the script as **Library code**.</span></span>  

### <a name="mark-a-script-as-library-code-from-the-editor-pane"></a><span data-ttu-id="ae3cb-191">エディター ウィンドウからスクリプトをライブラリ コードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="ae3cb-191">Mark a script as Library code from the Editor pane</span></span>  

<span data-ttu-id="ae3cb-192">次のアクションを実行して、[エディター] ウィンドウから **スクリプトをライブラリ コード** として **マーク** します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-192">Complete the following actions to mark a script as **Library code** from the **Editor** pane.</span></span>  

1.  <span data-ttu-id="ae3cb-193">ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-193">Open the file.</span></span>  
1.  <span data-ttu-id="ae3cb-194">任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-194">Hover anywhere and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="ae3cb-195">[ **ライブラリ コードとしてマーク] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-195">Choose **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="エディター ウィンドウからスクリプトをライブラリ コードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       <span data-ttu-id="ae3cb-197">エディター ウィンドウからスクリプト **をライブラリ コード** として **マーク** する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-197">Mark a script as **Library code** from the **Editor** pane</span></span>  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-the-call-stack-pane"></a><span data-ttu-id="ae3cb-198">[呼び出し履歴] ウィンドウからスクリプトをライブラリ コードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="ae3cb-198">Mark a script as Library code from the Call Stack pane</span></span>  

<span data-ttu-id="ae3cb-199">次のアクションを実行して、[呼び出し履歴] ウィンドウから **スクリプトをライブラリ** コード **としてマーク** します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-199">Complete the following actions to mark a script as **Library code** from the **Call Stack** pane.</span></span>  

1.  <span data-ttu-id="ae3cb-200">スクリプトから関数にカーソルを移動し、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-200">Hover on a function from the script and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="ae3cb-201">[ **ライブラリ コードとしてマーク] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-201">Choose **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="[呼び出し履歴] ウィンドウからスクリプトをライブラリ コードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       <span data-ttu-id="ae3cb-203">[呼び出し履歴] **ウィンドウからスクリプトを** ライブラリ **コードとしてマーク** する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-203">Mark a script as **Library code** from the **Call Stack** pane</span></span>  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-settings"></a><span data-ttu-id="ae3cb-204">設定からスクリプトをライブラリ コードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="ae3cb-204">Mark a script as Library code from Settings</span></span>  

<span data-ttu-id="ae3cb-205">設定からスクリプトの 1 つのスクリプトまたはパターンをマークするには、次のアクションを **実行します**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-205">Complete the following actions to mark a single script or pattern of scripts from **Settings**.</span></span>  

1.  <span data-ttu-id="ae3cb-206">[設定 [] を開きます][DevToolsCustomize]。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-206">Open [Settings][DevToolsCustomize].</span></span>  
1.  <span data-ttu-id="ae3cb-207">[ライブラリ コード **] 設定に移動** します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-207">Navigate to the **Library code** setting.</span></span>  
1.  <span data-ttu-id="ae3cb-208">[パターン **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-208">Choose **Add pattern**.</span></span>  
1.  <span data-ttu-id="ae3cb-209">ライブラリ コードとしてマークするスクリプト名またはスクリプト名の正規表現パターンを **入力します**。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-209">Enter the script name or a regex pattern of script names to mark as **Library code**.</span></span>  
1.  <span data-ttu-id="ae3cb-210">**追加** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-210">Choose **Add**.</span></span>  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="設定からスクリプトをライブラリ コードとしてマークする" lightbox="../media/javascript-framework-library-code.msft.png":::
       <span data-ttu-id="ae3cb-212">設定からスクリプトを **ライブラリ コードとして** マーク **する**</span><span class="sxs-lookup"><span data-stu-id="ae3cb-212">Mark a script as **Library code** from **Settings**</span></span>  
    :::image-end:::  
    
## <a name="run-snippets-of-debug-code-from-any-page"></a><span data-ttu-id="ae3cb-213">任意のページからデバッグ コードのスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-213">Run snippets of debug code from any page</span></span>  

<span data-ttu-id="ae3cb-214">コンソールで同じデバッグ コードを実行している場合は、スニペットを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-214">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span></span>  <span data-ttu-id="ae3cb-215">スニペットは、DevTools 内で作成、保存、および実行するランタイム スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-215">Snippets are runtime scripts that you author, store, and run within DevTools.</span></span>  

<span data-ttu-id="ae3cb-216">詳細については、「任意のページから [コードのスニペットを実行する」に移動します][DevToolsJavascriptSnippets]。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-216">To learn more, navigate to [Run Snippets of Code From Any Page][DevToolsJavascriptSnippets].</span></span>  

## <a name="watch-the-values-of-custom-javascript-expressions"></a><span data-ttu-id="ae3cb-217">カスタム JavaScript 式の値を確認する</span><span class="sxs-lookup"><span data-stu-id="ae3cb-217">Watch the values of custom JavaScript expressions</span></span>  

<span data-ttu-id="ae3cb-218">[ウォッチ **] ウィンドウを** 使用して、カスタム式の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-218">Use the **Watch** pane to watch the values of custom expressions.</span></span>  <span data-ttu-id="ae3cb-219">有効な JavaScript 式を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-219">You may watch any valid JavaScript expression.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="[ウォッチ] ウィンドウ" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   <span data-ttu-id="ae3cb-221">[ **ウォッチ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="ae3cb-221">The **Watch** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="ae3cb-222">[式 **の追加** \( Add Expression \) ] ボタンを ![ ](../media/add-expression-icon.msft.png) 選択して、新しいウォッチ式を作成します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-222">Choose the **Add Expression** \(![Add Expression](../media/add-expression-icon.msft.png)\) button to create a new watch expression.</span></span>  
*   <span data-ttu-id="ae3cb-223">[\( **Refresh** ![ ](../media/refresh-icon.msft.png) \) ] ボタンを選択して、既存のすべての式の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-223">Choose the **Refresh** \(![Refresh](../media/refresh-icon.msft.png)\) button to refresh the values of all existing expressions.</span></span>  <span data-ttu-id="ae3cb-224">コードをステップ実行すると、値が自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-224">Values automatically refresh while stepping through code.</span></span>  
*   <span data-ttu-id="ae3cb-225">式にカーソルを合わせると、式の **削除** \( ![ 式 ](../media/delete-expression-icon.msft.png) の削除 \) ボタンを選択して削除します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-225">Hover on an expression and choose the **Delete Expression** \(![Delete Expression](../media/delete-expression-icon.msft.png)\) button to delete it.</span></span>  

## <a name="make-a-minified-file-readable"></a><span data-ttu-id="ae3cb-226">ファイルを読み取り可能にする</span><span class="sxs-lookup"><span data-stu-id="ae3cb-226">Make a minified file readable</span></span>  

<span data-ttu-id="ae3cb-227">[Format \*\*\*\* \( Format \) ] ボタンを選択して、ファイルを人間が読み取り可能 ![ ](../media/format-icon.msft.png) にします。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-227">Choose the **Format** \(![Format](../media/format-icon.msft.png)\) button to make a minified file human-readable.</span></span>  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="[書式] ボタン" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   <span data-ttu-id="ae3cb-229">[ **書式]** ボタン</span><span class="sxs-lookup"><span data-stu-id="ae3cb-229">The **Format** button</span></span>  
:::image-end:::  

## <a name="edit-a-script"></a><span data-ttu-id="ae3cb-230">スクリプトの編集</span><span class="sxs-lookup"><span data-stu-id="ae3cb-230">Edit a script</span></span>  

<span data-ttu-id="ae3cb-231">バグを修正する場合は、JavaScript コードに対する変更をテストする必要が生じがちです。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-231">When fixing a bug, you often want to test out some changes to your JavaScript code.</span></span>  <span data-ttu-id="ae3cb-232">外部エディターまたは IDE で変更を加え、ページを更新する必要はない。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-232">You do not need to make the changes in an external editor or IDE and then refresh the page.</span></span>  <span data-ttu-id="ae3cb-233">DevTools でスクリプトを編集できます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-233">You may edit your script in DevTools.</span></span>  

<span data-ttu-id="ae3cb-234">スクリプトを編集するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-234">Complete the following actions to edit a script.</span></span>  

1.  <span data-ttu-id="ae3cb-235">[ソース] パネルの **[エディター** ] ウィンドウで **ファイルを開** きます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-235">Open the file in the **Editor** pane of the **Sources** panel.</span></span>  
1.  <span data-ttu-id="ae3cb-236">[エディター] ウィンドウで変更 **を行** います。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-236">Make your changes in the **Editor** pane.</span></span>  
1.  <span data-ttu-id="ae3cb-237">`Ctrl` + `S` \(Windows, Linux\) または `Command` + `S` \(macOS\) を選択して保存します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-237">Select `Ctrl`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  <span data-ttu-id="ae3cb-238">DevTools は、JS ファイル全体を Microsoft Edge の JavaScript エンジンにパッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-238">DevTools patches the entire JS file into the JavaScript engine of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="[エディター] ウィンドウ" lightbox="../media/javascript-sources-html-minified.msft.png":::
       <span data-ttu-id="ae3cb-240">[ **エディター]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="ae3cb-240">The **Editor** pane</span></span>  
    :::image-end:::  
     
## <a name="disable-javascript"></a><span data-ttu-id="ae3cb-241">JavaScript を無効にする</span><span class="sxs-lookup"><span data-stu-id="ae3cb-241">Disable JavaScript</span></span>  

<span data-ttu-id="ae3cb-242">[Microsoft Edge [DevTools を使用して JavaScript を無効にする] に移動します][DevToolsJavascriptDisable]。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-242">Navigate to [Disable JavaScript with Microsoft Edge DevTools][DevToolsJavascriptDisable].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="ae3cb-243">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="ae3cb-243">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "Microsoft Edge DevTools アプリケーションでブレークポイントを使用してコードを一時停止する|Microsoft Docs"  
[DevToolsJavascriptDisable]: ./disable.md "Microsoft Edge DevTools を使用して JavaScript を無効|Microsoft Docs"  
[DevToolsJavascriptGetStarted]: ./index.md "Microsoft Edge DevTools の JavaScript のデバッグの|Microsoft Docs"  
[DevToolsJavascriptSnippets]: ./snippets.md "Microsoft Edge DevTools を使用して任意のページで JavaScript のスニペットを実行|Microsoft Docs"  
[DevToolsCustomize]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ |Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="ae3cb-249">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-249">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ae3cb-250">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-250">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ae3cb-252">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ae3cb-252">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
