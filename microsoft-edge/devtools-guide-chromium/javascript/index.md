---
title: Microsoft Edge DevTools のデバッグ JavaScript の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 06df1fd4d6457a3f02be85b95959bdc353865495
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581825"
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







# <span data-ttu-id="28dac-103">Microsoft Edge DevTools のデバッグ JavaScript の概要</span><span class="sxs-lookup"><span data-stu-id="28dac-103">Get Started with Debugging JavaScript in Microsoft Edge DevTools</span></span>   



<span data-ttu-id="28dac-104">このチュートリアルでは、DevTools で JavaScript の問題をデバッグするための基本的なワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="28dac-104">This tutorial teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <span data-ttu-id="28dac-105">手順 1: バグを再現する</span><span class="sxs-lookup"><span data-stu-id="28dac-105">Step 1: Reproduce the bug</span></span>   

<span data-ttu-id="28dac-106">常にバグを再現する一連のアクションを見つけることは、常にデバッグの最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="28dac-106">Finding a series of actions that consistently reproduces a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="28dac-107">[**デモを開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28dac-107">Click **Open Demo**.</span></span>  <span data-ttu-id="28dac-108">`Control`\ (Windows \) または `Command` \ (macOS \) を保持し、新しいタブでデモを開きます。</span><span class="sxs-lookup"><span data-stu-id="28dac-108">Hold `Control` \(Windows\) or `Command` \(macOS\) and open the demo in a new tab.</span></span>  

    <span data-ttu-id="28dac-109">[デモを開く][OpenDebugJSDemo]</span><span class="sxs-lookup"><span data-stu-id="28dac-109">[Open Demo][OpenDebugJSDemo]</span></span>  

1.  <span data-ttu-id="28dac-110">[ `5` **数値 1** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="28dac-110">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="28dac-111">[ `1` **数値 2** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="28dac-111">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="28dac-112">[**番号 1] と [番号2の追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="28dac-112">Click **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="28dac-113">ボタンの下にラベルが表示され `5 + 1 = 51` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-113">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="28dac-114">結果はになり `6` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-114">The result should be `6`.</span></span>  <span data-ttu-id="28dac-115">これは、修正する予定のバグです。</span><span class="sxs-lookup"><span data-stu-id="28dac-115">This is the bug you are going to fix.</span></span>  
    
    > ##### <span data-ttu-id="28dac-116">図 1</span><span class="sxs-lookup"><span data-stu-id="28dac-116">Figure 1</span></span>  
    > <span data-ttu-id="28dac-117">の結果 `5 + 1` はですが `51` 、</span><span class="sxs-lookup"><span data-stu-id="28dac-117">The result of `5 + 1` is `51`, but should be</span></span> `6`  
    > ![5 + 1 の結果は51ですが、6にする必要があります。][ImageJSBugs]  

## <span data-ttu-id="28dac-119">手順 2: ソースパネルの UI について理解する</span><span class="sxs-lookup"><span data-stu-id="28dac-119">Step 2: Get familiar with the Sources panel UI</span></span>   

<span data-ttu-id="28dac-120">DevTools には、CSS の変更、ページの読み込みパフォーマンスのプロファイリング、ネットワーク要求の監視など、さまざまなタスクに対応するさまざまなツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="28dac-120">DevTools provides a lot of different tools for different tasks, such as changing CSS, profiling page load performance, and monitoring network requests.</span></span>  <span data-ttu-id="28dac-121">[**ソース**] パネルでは、JavaScript をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="28dac-121">The **Sources** panel is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="28dac-122">`Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押して、devtools を開きます。</span><span class="sxs-lookup"><span data-stu-id="28dac-122">Open DevTools by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) .</span></span>  <span data-ttu-id="28dac-123">このショートカットは**コンソール**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="28dac-123">This shortcut opens the **Console** panel.</span></span>  
    
    > ##### <span data-ttu-id="28dac-124">図 2</span><span class="sxs-lookup"><span data-stu-id="28dac-124">Figure 2</span></span>  
    > <span data-ttu-id="28dac-125">**コンソール**パネル</span><span class="sxs-lookup"><span data-stu-id="28dac-125">The **Console** panel</span></span>  
    > ![コンソールパネル][ImageJSConsole]  

1.  <span data-ttu-id="28dac-127">[**ソース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="28dac-127">Click the **Sources** tab.</span></span>  
    
    > ##### <span data-ttu-id="28dac-128">図 3</span><span class="sxs-lookup"><span data-stu-id="28dac-128">Figure 3</span></span>  
    > <span data-ttu-id="28dac-129">[**ソース**] パネル</span><span class="sxs-lookup"><span data-stu-id="28dac-129">The **Sources** panel</span></span>  
    > ![[ソース] パネル][ImageJSSources]  

<span data-ttu-id="28dac-131">**ソース**パネルの UI には3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="28dac-131">The **Sources** panel UI has 3 parts:</span></span>  

> ##### <span data-ttu-id="28dac-132">図 4</span><span class="sxs-lookup"><span data-stu-id="28dac-132">Figure 4</span></span>  
> <span data-ttu-id="28dac-133">**ソース**パネルの UI の3つの部分</span><span class="sxs-lookup"><span data-stu-id="28dac-133">The 3 parts of the **Sources** panel UI</span></span>  
> ![ソースパネルの UI の3つの部分][ImageJSSourcesAnnotated]  

1.  <span data-ttu-id="28dac-135">**ファイルナビゲーター**ウィンドウ \ ([図 4](#figure-4)のセクション 1)</span><span class="sxs-lookup"><span data-stu-id="28dac-135">The **File Navigator** pane \(Section 1 in [Figure 4](#figure-4)\).</span></span>  <span data-ttu-id="28dac-136">ページが要求するすべてのファイルがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-136">Every file that the page requests is listed here.</span></span>  
1.  <span data-ttu-id="28dac-137">**コードエディター**ウィンドウ \ ([図 4](#figure-4)のセクション 2)</span><span class="sxs-lookup"><span data-stu-id="28dac-137">The **Code Editor** pane \(Section 2 in [Figure 4](#figure-4)\).</span></span>  <span data-ttu-id="28dac-138">[**ファイルナビゲーター** ] ウィンドウでファイルを選択すると、そのファイルの内容がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-138">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span></span>  
1.  <span data-ttu-id="28dac-139">**JavaScript のデバッグ**ウィンドウ ([図 4](#figure-4)のセクション 3)</span><span class="sxs-lookup"><span data-stu-id="28dac-139">The **JavaScript Debugging** pane \(Section 3 in [Figure 4](#figure-4)\).</span></span>  <span data-ttu-id="28dac-140">ページの JavaScript を調べるためのさまざまなツール。</span><span class="sxs-lookup"><span data-stu-id="28dac-140">Various tools for inspecting the JavaScript for the page.</span></span>  <span data-ttu-id="28dac-141">DevTools ウィンドウが広くなっている場合、このウィンドウは [**コードエディター** ] ウィンドウの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-141">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span></span>  

## <span data-ttu-id="28dac-142">手順 3: ブレークポイントでコードを一時停止する</span><span class="sxs-lookup"><span data-stu-id="28dac-142">Step 3: Pause the code with a breakpoint</span></span>   

<span data-ttu-id="28dac-143">このような問題をデバッグする一般的な方法は、スクリプトの実行時に値を検査するために、コードに大量のステートメントを挿入することです `console.log()` 。</span><span class="sxs-lookup"><span data-stu-id="28dac-143">A common method for debugging a problem like this is to insert a lot of `console.log()` statements into the code, in order to inspect values as the script runs.</span></span>  <span data-ttu-id="28dac-144">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="28dac-144">For example:</span></span>  

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

<span data-ttu-id="28dac-145">このメソッドではジョブが完了して `console.log()` いる可能性がありますが、**ブレークポイント**を使うと作業を高速化できます。</span><span class="sxs-lookup"><span data-stu-id="28dac-145">The `console.log()` method may get the job done, but **breakpoints** are able to get it done faster.</span></span>  <span data-ttu-id="28dac-146">ブレークポイントを使用すると、実行時にコードを一時停止し、その時点ですべての値を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="28dac-146">A breakpoint lets you pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="28dac-147">ブレークポイントには、この方法に関するいくつかの利点があり `console.log()` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-147">Breakpoints have a few advantages over the `console.log()` method:</span></span>  

*   <span data-ttu-id="28dac-148">では `console.log()` 、ソースコードを手動で開いて、関連するコードを見つけ、ステートメントを挿入して `console.log()` から、コンソールにメッセージを表示するためにページを再読み込みする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28dac-148">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then reload the page in order to see the messages in the Console.</span></span>  <span data-ttu-id="28dac-149">ブレークポイントを使用すると、コードがどのように構成されているかわからなくても、関連するコードを一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="28dac-149">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="28dac-150">ステートメントで、 `console.log()` 検査する各値を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28dac-150">In your `console.log()` statements you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="28dac-151">ブレークポイントを使用すると、DevTools によって、その時点でのすべての変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-151">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="28dac-152">場合によっては、認識していないコードに影響を与える変数が存在することもあります。</span><span class="sxs-lookup"><span data-stu-id="28dac-152">Sometimes there are variables affecting your code that you are not even aware of.</span></span>  

<span data-ttu-id="28dac-153">つまり、ブレークポイントは、メソッドよりも短時間でバグを見つけて修正するのに役立ち `console.log()` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-153">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="28dac-154">手順を実行して、アプリの動作について考えている場合は、 `5 + 1 = 51` `click` [ **1 と番号2を追加**] ボタンに関連付けられているイベントリスナーで、誤った sum () が計算されることを推測できます。</span><span class="sxs-lookup"><span data-stu-id="28dac-154">If you take a step back and think about how the app works, you are able to make an educated guess that the incorrect sum (`5 + 1 = 51`) gets computed in the `click` event listener that is associated to the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="28dac-155">そのため、おそらくリスナーが実行されている時間の前後にコードを一時停止する必要があり `click` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-155">Therefore, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="28dac-156">**イベントリスナーのブレークポイント**を使用すると、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="28dac-156">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="28dac-157">JavaScript の**デバッグ**ウィンドウで、[**イベントリスナーブレークポイント**] をクリックしてセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="28dac-157">In the **JavaScript Debugging** pane, click **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="28dac-158">DevTools は、**アニメーション**や**クリップボード**などの拡張可能なイベントカテゴリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="28dac-158">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="28dac-159">**マウス**イベントカテゴリの横にある [展開アイコン**の展開] をクリックし** ![ ][ImageExpandIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-159">Next to the **Mouse** event category, click **Expand** ![Expand icon][ImageExpandIcon].</span></span>  <span data-ttu-id="28dac-160">DevTools は、 **click** 、 **mousedown**などのマウスイベントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="28dac-160">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="28dac-161">各イベントの横にチェックボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="28dac-161">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="28dac-162">**[クリック**時] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="28dac-162">Check the **click** checkbox.</span></span>  <span data-ttu-id="28dac-163">DevTools は *、* イベントリスナーが実行されると自動的に一時停止するように設定されました `click` 。</span><span class="sxs-lookup"><span data-stu-id="28dac-163">DevTools is now set up to automatically pause when *any* `click` event listener runs.</span></span>  
    
    > ##### <span data-ttu-id="28dac-164">図 5</span><span class="sxs-lookup"><span data-stu-id="28dac-164">Figure 5</span></span>  
    > <span data-ttu-id="28dac-165">**[クリック**] チェックボックスが有効になっている</span><span class="sxs-lookup"><span data-stu-id="28dac-165">The **click** checkbox is enabled</span></span>  
    > ![[クリック] チェックボックスが有効になっている][ImageJSClickCheckbox]  
    
1.  <span data-ttu-id="28dac-167">デモに戻り、[**番号 1] と [番号 2**をもう一度追加する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28dac-167">Back on the demo, click **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="28dac-168">DevTools はデモを一時停止し、[**ソース**] パネルでコードの行を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="28dac-168">DevTools pauses the demo and highlights a line of code in the **Sources** panel.</span></span>  <span data-ttu-id="28dac-169">DevTools は、16行目で一時停止する必要があり `get-started.js` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-169">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="28dac-170">別のコード行を使用して一時停止した場合は、[**スクリプト実行の再開**] をクリックして、正しい行をポイントし ![ ][ImageResumeIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-170">If you pause on a different line of code, press **Resume Script Execution** ![Resume Script Execution][ImageResumeIcon] until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="28dac-171">別の行に一時停止している場合は、アクセスした `click` すべてのページにイベントリスナーが登録されているブラウザー拡張機能があります。</span><span class="sxs-lookup"><span data-stu-id="28dac-171">If you paused on a different line, you have a browser extension that registers a `click` event listener on every page that you visit.</span></span>  <span data-ttu-id="28dac-172">内線番号のリスナーで一時停止してい `click` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-172">You were paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="28dac-173">InPrivate モードを使って**プライベートで参照**している場合は、すべての拡張機能が無効になります。その場合は、必要なコード行を毎回一時停止することになります。</span><span class="sxs-lookup"><span data-stu-id="28dac-173">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="28dac-174">**イベントリスナーのブレークポイント**は、devtools で利用できる多くの種類のブレークポイントのうちの1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="28dac-174">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="28dac-175">各型は最終的に、できるだけ簡単にさまざまなシナリオをデバッグするのに役立ちますので、すべての種類を memorizing することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28dac-175">It is worth memorizing all the different types, because each type ultimately helps you debug different scenarios as quickly as possible.</span></span>  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <span data-ttu-id="28dac-176">手順 4: コードをステップ実行する</span><span class="sxs-lookup"><span data-stu-id="28dac-176">Step 4: Step through the code</span></span>   

<span data-ttu-id="28dac-177">バグの一般的な原因の1つとして、スクリプトが誤った順序で実行されることがあります。</span><span class="sxs-lookup"><span data-stu-id="28dac-177">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="28dac-178">コードをステップ実行することで、コードの実行を1行ずつ実行し、予期していた順序で実行されている位置を正確に把握することができます。</span><span class="sxs-lookup"><span data-stu-id="28dac-178">Stepping through your code enables you to walk through the runtime of your code, one line at a time, and figure out exactly where it is running in a different order than you expected.</span></span>  <span data-ttu-id="28dac-179">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="28dac-179">Try it now:</span></span>  

1.  <span data-ttu-id="28dac-180">[次の関数のステップ**オーバー** ] をクリックして ![ ][ImageOverIcon] 、次の関数の呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="28dac-180">Click **Step over next function call** ![Step over next function call][ImageOverIcon].</span></span>  <span data-ttu-id="28dac-181">DevTools では、次のコードをステップ実行せずに実行します。</span><span class="sxs-lookup"><span data-stu-id="28dac-181">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  

    > [!NOTE]
    > <span data-ttu-id="28dac-182">DevTools では、数行のコードをスキップします。</span><span class="sxs-lookup"><span data-stu-id="28dac-182">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="28dac-183">これは、 `inputsAreEmpty()` false として評価されるため、このステートメントのコードブロックは `if` 実行されません。</span><span class="sxs-lookup"><span data-stu-id="28dac-183">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  

1.  <span data-ttu-id="28dac-184">DevTools の**ソース**パネルで **、[次**の関数の呼び出し] をクリックし ![ て、 ][ImageIntoIcon] 関数の実行時に1行ずつ手順を実行し `updateLabel()` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-184">On the **Sources** panel of DevTools, click **Step into next function call** ![Step into next function call][ImageIntoIcon] to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  

<span data-ttu-id="28dac-185">これは、コードをステップ実行するための基本的な考え方です。</span><span class="sxs-lookup"><span data-stu-id="28dac-185">That is the basic idea of stepping through code.</span></span>  <span data-ttu-id="28dac-186">コードを見ると `get-started.js` 、バグが関数のどこかにあると考えられ `updateLabel()` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-186">If you look at the code in `get-started.js`, you see that the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="28dac-187">すべてのコード行をステップ実行するのではなく、別の種類のブレークポイントを使って、バグの可能性がある場所に近いコードを一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="28dac-187">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <span data-ttu-id="28dac-188">手順 5: コード行のブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="28dac-188">Step 5: Set a line-of-code breakpoint</span></span>   

<span data-ttu-id="28dac-189">行コードのブレークポイントは、最も一般的なブレークポイントの種類です。</span><span class="sxs-lookup"><span data-stu-id="28dac-189">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="28dac-190">一時停止する特定のコード行を取得したら、コード行のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="28dac-190">When you get the specific line of code that you want to pause on, use a line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="28dac-191">のコードの最後の行を確認し `updateLabel()` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-191">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="28dac-192">コードの左側に、この特定のコード行の行番号 ( **33**) が表示されています。</span><span class="sxs-lookup"><span data-stu-id="28dac-192">To the left of the code you see the line number of this particular line of code, which is **33**.</span></span>  <span data-ttu-id="28dac-193">[ **33**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28dac-193">Click on **33**.</span></span>  <span data-ttu-id="28dac-194">DevTools は、 **33**の左側に赤いアイコンを配置します。</span><span class="sxs-lookup"><span data-stu-id="28dac-194">DevTools puts a red icon to the left of **33**.</span></span>  <span data-ttu-id="28dac-195">これは、この行に行コードのブレークポイントがあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="28dac-195">This means that there is a line-of-code breakpoint on this line.</span></span>  <span data-ttu-id="28dac-196">DevTools は、このコード行が実行される前に常に一時停止されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="28dac-196">DevTools now always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="28dac-197">[**スクリプト実行の再開**] ![ スクリプト実行をクリックし ][ImageResumeIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-197">Click **Resume script execution** ![Resume script execution][ImageResumeIcon].</span></span>  <span data-ttu-id="28dac-198">スクリプトは、33行目に到達するまで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="28dac-198">The script continues running until it reaches line 33.</span></span>  <span data-ttu-id="28dac-199">[DevTools] は、30、31、および32の行で、 `addend1` `addend2` `sum` 各行のセミコロンの右にある、、、の値を出力します。</span><span class="sxs-lookup"><span data-stu-id="28dac-199">On lines 30, 31, and 32, DevTools prints out the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    > ##### <span data-ttu-id="28dac-200">図 6</span><span class="sxs-lookup"><span data-stu-id="28dac-200">Figure 6</span></span>  
    > <span data-ttu-id="28dac-201">DevTools は、32行目のコードの行のブレークポイントで一時停止します</span><span class="sxs-lookup"><span data-stu-id="28dac-201">DevTools pauses on the line-of-code breakpoint on line 32</span></span>  
    > ![DevTools は、32行目のコードの行のブレークポイントで一時停止します][ImageJSLineOfCodeBreakpoint]  

## <span data-ttu-id="28dac-203">手順 6: 変数の値を確認する</span><span class="sxs-lookup"><span data-stu-id="28dac-203">Step 6: Check variable values</span></span>   

<span data-ttu-id="28dac-204">[] の値、[ `addend1` `addend2` 疑わしい] と表示さ `sum` れます。</span><span class="sxs-lookup"><span data-stu-id="28dac-204">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="28dac-205">引用符で囲まれています。これは文字列であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="28dac-205">They are wrapped in quotes, which means that they are strings.</span></span>  <span data-ttu-id="28dac-206">これは、バグの原因を説明するための優れた仮説です。</span><span class="sxs-lookup"><span data-stu-id="28dac-206">This is a good hypothesis for the explaining the cause of the bug.</span></span>  <span data-ttu-id="28dac-207">次に、詳細情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="28dac-207">Now it is time to gather more information.</span></span>  <span data-ttu-id="28dac-208">DevTools には、可変値を検査するための多くのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="28dac-208">DevTools provides a lot of tools for examining variable values.</span></span>  

### <span data-ttu-id="28dac-209">方法 1: 範囲ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="28dac-209">Method 1: The Scope pane</span></span>   

<span data-ttu-id="28dac-210">コード行を一時停止すると、**スコープ**ウィンドウに、現在定義されているローカルとグローバル変数、および各変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-210">When you pause on a line of code, the **Scope** pane shows you what local and global variables are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="28dac-211">また、必要に応じて休業変数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-211">It also shows closure variables, when applicable.</span></span>  <span data-ttu-id="28dac-212">変数値をダブルクリックして編集します。</span><span class="sxs-lookup"><span data-stu-id="28dac-212">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="28dac-213">コード行で一時停止していない場合、**スコープ**ウィンドウは空です。</span><span class="sxs-lookup"><span data-stu-id="28dac-213">When you are not paused on a line of code, the **Scope** pane is empty.</span></span>  

> ##### <span data-ttu-id="28dac-214">図 7</span><span class="sxs-lookup"><span data-stu-id="28dac-214">Figure 7</span></span>  
> <span data-ttu-id="28dac-215">**スコープ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="28dac-215">The **Scope** pane</span></span>  
> ![スコープウィンドウ][ImageJSScope]  

### <span data-ttu-id="28dac-217">方法 2: 式をウォッチする</span><span class="sxs-lookup"><span data-stu-id="28dac-217">Method 2: Watch Expressions</span></span>   

<span data-ttu-id="28dac-218">[**式のウォッチ**] タブでは、時間の経過に伴う変数の値を監視できます。</span><span class="sxs-lookup"><span data-stu-id="28dac-218">The **Watch Expressions** tab lets you monitor the values of variables over time.</span></span>  <span data-ttu-id="28dac-219">名前が示すように、ウォッチ式は変数だけに限定されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="28dac-219">As the name implies, Watch Expressions are not just limited to variables.</span></span>  <span data-ttu-id="28dac-220">ウォッチ式には有効な JavaScript 式を格納することができます。</span><span class="sxs-lookup"><span data-stu-id="28dac-220">You are able to store any valid JavaScript expression in a Watch Expression.</span></span>  <span data-ttu-id="28dac-221">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="28dac-221">Try it now:</span></span>  

1.  <span data-ttu-id="28dac-222">[**ウォッチ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="28dac-222">Click the **Watch** tab.</span></span>  
1.  <span data-ttu-id="28dac-223">[**式** ![ の追加] ][ImageAddIcon] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28dac-223">Click **Add Expression** ![Add Expression][ImageAddIcon].</span></span>  
1.  <span data-ttu-id="28dac-224">「`typeof sum`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="28dac-224">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="28dac-225">キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-225">Press `Enter`.</span></span>  <span data-ttu-id="28dac-226">DevTools が表示さ `typeof sum: "string"` れます。</span><span class="sxs-lookup"><span data-stu-id="28dac-226">DevTools shows `typeof sum: "string"`.</span></span>  <span data-ttu-id="28dac-227">コロンの右側の値は、ウォッチ式の結果です。</span><span class="sxs-lookup"><span data-stu-id="28dac-227">The value to the right of the colon is the result of your Watch Expression.</span></span>  

> [!NOTE]
> <span data-ttu-id="28dac-228">[式のウォッチ] ウィンドウ ([図 8](#figure-8)の右下) で、 `typeof sum` ウォッチ式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-228">In the Watch Expression pane \(bottom-right\) in [Figure 8](#figure-8), the `typeof sum` Watch Expression is displayed.</span></span>  <span data-ttu-id="28dac-229">DevTools ウィンドウが大きい場合は、[ウォッチ式] ウィンドウは、**イベントリスナーの [ブレークポイント**] ウィンドウの右側にあります。</span><span class="sxs-lookup"><span data-stu-id="28dac-229">If your DevTools window is large, the Watch Expression pane is on the right above the **Event Listener Breakpoints** pane.</span></span>  

> ##### <span data-ttu-id="28dac-230">図 8</span><span class="sxs-lookup"><span data-stu-id="28dac-230">Figure 8</span></span>  
> <span data-ttu-id="28dac-231">ウォッチ式ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="28dac-231">The Watch Expression pane</span></span>  
> ![ウォッチ式ウィンドウ][ImageJSWatchExpression]  

<span data-ttu-id="28dac-233">疑わしいとして、 `sum` 数値の場合は文字列として評価されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-233">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="28dac-234">これがバグの原因であることが確認されました。</span><span class="sxs-lookup"><span data-stu-id="28dac-234">You have now confirmed that this is the cause of the bug.</span></span>  

### <span data-ttu-id="28dac-235">方法 3: 本体</span><span class="sxs-lookup"><span data-stu-id="28dac-235">Method 3: The Console</span></span>   

<span data-ttu-id="28dac-236">メッセージを表示するだけで `console.log()` なく、コンソールを使って任意の JavaScript ステートメントを評価することもできます。</span><span class="sxs-lookup"><span data-stu-id="28dac-236">In addition to viewing `console.log()` messages, you may also use the Console to evaluate arbitrary JavaScript statements.</span></span>  <span data-ttu-id="28dac-237">デバッグの観点から、本体を使ってバグの潜在的な解決をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="28dac-237">In terms of debugging, you may use the Console to test out potential fixes for bugs.</span></span>  <span data-ttu-id="28dac-238">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="28dac-238">Try it now:</span></span>  

1.  <span data-ttu-id="28dac-239">コンソールの引き出しを開いていない場合は、を押して `Escape` 開きます。</span><span class="sxs-lookup"><span data-stu-id="28dac-239">If you do not have the Console drawer open, press `Escape` to open it.</span></span>  <span data-ttu-id="28dac-240">これは、DevTools ウィンドウの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-240">It opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="28dac-241">コンソールで、と入力 `parseInt(addend1) + parseInt(addend2)` します。</span><span class="sxs-lookup"><span data-stu-id="28dac-241">In the Console, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="28dac-242">このステートメントは `addend1` 、および範囲内のコード行で一時停止しているために動作し `addend2` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-242">This statement works because you are paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="28dac-243">キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-243">Press `Enter`.</span></span>  <span data-ttu-id="28dac-244">DevTools は、ステートメントを評価して出力し `6` ます。これは、デモで生成される結果です。</span><span class="sxs-lookup"><span data-stu-id="28dac-244">DevTools evaluates the statement and prints out `6`, which is the result you expect the demo to produce.</span></span>  

> ##### <span data-ttu-id="28dac-245">図 9</span><span class="sxs-lookup"><span data-stu-id="28dac-245">Figure 9</span></span>  
> <span data-ttu-id="28dac-246">評価後の本体の引き出し</span><span class="sxs-lookup"><span data-stu-id="28dac-246">The Console drawer, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
> ![ParseInt (addend1) + parseInt (addend2) を評価した後の本体の引き出し][ImageJSConsoleEvaluated]  

## <span data-ttu-id="28dac-248">手順 7: 修正プログラムを適用する</span><span class="sxs-lookup"><span data-stu-id="28dac-248">Step 7: Apply a fix</span></span>   

<span data-ttu-id="28dac-249">バグの修正プログラムが見つかった場合は、コードを編集してデモを再実行して、修正を試してください。</span><span class="sxs-lookup"><span data-stu-id="28dac-249">If you find a fix for the bug, try out your fix by editing the code and re-running the demo.</span></span>  <span data-ttu-id="28dac-250">この修正プログラムを適用するには、DevTools を終了する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="28dac-250">You do not need to leave DevTools to apply the fix.</span></span>  <span data-ttu-id="28dac-251">DevTools UI では、JavaScript コードを直接編集できます。</span><span class="sxs-lookup"><span data-stu-id="28dac-251">You are able to edit JavaScript code directly within the DevTools UI.</span></span>  <span data-ttu-id="28dac-252">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="28dac-252">Try it now:</span></span>  

1.  <span data-ttu-id="28dac-253">[**スクリプト実行の再開**] ![ スクリプト実行をクリックし ][ImageResumeIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-253">Click **Resume script execution** ![Resume script execution][ImageResumeIcon].</span></span>  
1.  <span data-ttu-id="28dac-254">**コードエディター**で、行32、 `var sum = addend1 + addend2` をに置き換え `var sum = parseInt(addend1) + parseInt(addend2)` ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-254">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="28dac-255">`Control` + `S` \ (Windows \) または `Command` + `S` \ (macOS \) を押して、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="28dac-255">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="28dac-256">[**ブレークポイントの非**アクティブ化] をクリックし ![ ][ImageDeactivateIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="28dac-256">Click **Deactivate breakpoints** ![Deactivate breakpoints][ImageDeactivateIcon].</span></span>  <span data-ttu-id="28dac-257">これは青色に変わり、アクティブであることを示します。</span><span class="sxs-lookup"><span data-stu-id="28dac-257">It changes blue to indicate that it is active.</span></span>  <span data-ttu-id="28dac-258">この設定を行うと、設定したブレークポイントはすべて、DevTools によって無視されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-258">While this is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="28dac-259">さまざまな値を持つデモを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="28dac-259">Try out the demo with different values.</span></span>  <span data-ttu-id="28dac-260">デモが正しく計算されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="28dac-260">The demo now calculates correctly.</span></span>  

> [!CAUTION]
> <span data-ttu-id="28dac-261">このワークフローは、ブラウザーで実行されているコードにのみ修正プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="28dac-261">This workflow only applies a fix to the code that is running in your browser.</span></span>  <span data-ttu-id="28dac-262">ページにアクセスするすべてのユーザーのコードは修正されません。</span><span class="sxs-lookup"><span data-stu-id="28dac-262">It does not fix the code for all users that visit your page.</span></span>  <span data-ttu-id="28dac-263">そのためには、サーバー上のコードを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28dac-263">To do that, you need to fix the code that is on your servers.</span></span>  

## <span data-ttu-id="28dac-264">次のステップ</span><span class="sxs-lookup"><span data-stu-id="28dac-264">Next steps</span></span>   

<span data-ttu-id="28dac-265">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="28dac-265">Congratulations!</span></span>  <span data-ttu-id="28dac-266">これで、JavaScript のデバッグ時に Microsoft Edge DevTools を最大限に活用する方法がわかりました。</span><span class="sxs-lookup"><span data-stu-id="28dac-266">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="28dac-267">このチュートリアルで学んだツールと方法を使用すると、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="28dac-267">The tools and methods you learned in this tutorial may save you countless hours.</span></span>  

<span data-ttu-id="28dac-268">このチュートリアルでは、2つの方法でブレークポイントを設定する方法について説明しました。</span><span class="sxs-lookup"><span data-stu-id="28dac-268">This tutorial only showed you two ways to set breakpoints.</span></span>  <span data-ttu-id="28dac-269">DevTools には、次のようなさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="28dac-269">DevTools offers many other ways, including:</span></span>  

*   <span data-ttu-id="28dac-270">指定した条件が true の場合にのみトリガーされる条件付きブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="28dac-270">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="28dac-271">キャッチまたはキャッチされない例外のブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="28dac-271">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="28dac-272">指定した URL が指定した部分文字列と一致した場合にトリガーされる XHR ブレークポイント。</span><span class="sxs-lookup"><span data-stu-id="28dac-272">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  

<!-- See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

<!--There are a couple of code stepping controls that were not explained in this tutorial.  See [Step over line of code][JSReferenceStepping] to learn more.  -->  

 



<!-- image links -->  

[ImageAddIcon]: /microsoft-edge/devtools-guide-chromium/media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: /microsoft-edge/devtools-guide-chromium/media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: /microsoft-edge/devtools-guide-chromium/media/expand-icon.msft.png  
[ImageIntoIcon]: /microsoft-edge/devtools-guide-chromium/media/step-into-icon.msft.png  
[ImageOverIcon]: /microsoft-edge/devtools-guide-chromium/media/step-over-icon.msft.png  
[ImageResumeIcon]: /microsoft-edge/devtools-guide-chromium/media/resume-script-run-icon.msft.png  

[ImageJSBugs]: /microsoft-edge/devtools-guide-chromium/media/javascript-js-demo-bad.msft.png "図 1: 5 + 1 の結果は51ですが、6でなければなりません。"  
[ImageJSConsole]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-empty.msft.png "図 2: コンソールパネル"  
[ImageJSSources]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-sections.msft.png "図 3: [ソース] パネル"  
[ImageJSSourcesAnnotated]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-sections-annotated.msft.png "図 4: [ソース] パネル UI の3つの部分"  
[ImageJSClickCheckbox]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png "図 5: [クリック] チェックボックスが有効になっている"  
[ImageJSLineOfCodeBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused.msft.png "図 6: DevTools が行32のコードの行のブレークポイントで一時停止する"  
[ImageJSScope]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-scope.msft.png "図 7: スコープウィンドウ"  
[ImageJSWatchExpression]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-watch.msft.png "図 8: [ウォッチ式] ウィンドウ"  
[ImageJSConsoleEvaluated]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-console.msft.png "ParseInt (addend1) + parseInt (addend2) を評価した後の本体の引き出し"  

<!-- links -->  

<!--[JSBreakpoints]: breakpoints.md "JavaScript Breakpoints"  -->  
<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->
[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "デモを開く"  
<!--[JSReferenceStepping]: reference.md#stepping "Reference Stepping"  -->

> [!NOTE]
> <span data-ttu-id="28dac-283">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="28dac-283">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="28dac-284">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="28dac-284">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="28dac-286">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="28dac-286">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
