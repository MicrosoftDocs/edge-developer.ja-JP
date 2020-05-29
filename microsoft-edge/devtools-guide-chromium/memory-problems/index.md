---
title: メモリの問題を解決する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 738ef5fe682633f3100345c922ff12c3c27a7166
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611763"
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





# <span data-ttu-id="9c797-103">メモリの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="9c797-103">Fix Memory Problems</span></span>   



<span data-ttu-id="9c797-104">Microsoft Edge と DevTools を使って、ページのパフォーマンスに影響するメモリの問題を見つける方法について説明します。これには、メモリリーク、メモリの膨張、ガベージコレクションの頻度などがあります。</span><span class="sxs-lookup"><span data-stu-id="9c797-104">Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.</span></span>  

### <span data-ttu-id="9c797-105">まとめ</span><span class="sxs-lookup"><span data-stu-id="9c797-105">Summary</span></span>  

*   <span data-ttu-id="9c797-106">Microsoft Edge Browser のタスクマネージャーで現在ページで使用されているメモリの量を確認します。</span><span class="sxs-lookup"><span data-stu-id="9c797-106">Find out how much memory your page is currently using with the Microsoft Edge Browser Task Manager.</span></span>  
*   <span data-ttu-id="9c797-107">メモリ使用量を時間の経過と共に**メモリ**パネルでビジュアル化します。</span><span class="sxs-lookup"><span data-stu-id="9c797-107">Visualize memory usage over time with the **Memory** panel.</span></span>  
*   <span data-ttu-id="9c797-108">**ヒープスナップショット**を使用して、デタッチされた DOM ツリー (メモリリークの一般的な原因) を特定します。</span><span class="sxs-lookup"><span data-stu-id="9c797-108">Identify detached DOM trees \(a common cause of memory leaks\) with **Heap snapshot**.</span></span>  
*   <span data-ttu-id="9c797-109">新しいメモリが JavaScript ヒープ \ (JS ヒープ) に割り当てられている場合は、**タイムラインの割り当てインストルメンテーション**で確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c797-109">Find out when new memory is being allocated in your JavaScript heap \(JS heap\) with **Allocation instrumentation on timeline**.</span></span>  

## <span data-ttu-id="9c797-110">概要</span><span class="sxs-lookup"><span data-stu-id="9c797-110">Overview</span></span>  

<span data-ttu-id="9c797-111">**鉄道**のパフォーマンスモデルの精神においては、パフォーマンスの取り組みの焦点をユーザーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-111">In the spirit of the **RAIL** performance model, the focus of your performance efforts should be your users.</span></span>  

<!--todo: add RAIL section when available  -->  

<span data-ttu-id="9c797-112">メモリの問題は、ユーザーによって気が付きされることが多いために重要です。</span><span class="sxs-lookup"><span data-stu-id="9c797-112">Memory issues are important because they are often perceivable by users.</span></span>  <span data-ttu-id="9c797-113">次の方法で、メモリの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-113">Users may perceive memory issues in the following ways:</span></span>  

*   <span data-ttu-id="9c797-114">**ページのパフォーマンスが時間の経過と共に悪化**します。</span><span class="sxs-lookup"><span data-stu-id="9c797-114">**The performance of a page gets progressively worse over time**.</span></span>  <span data-ttu-id="9c797-115">これは、メモリリークの症状である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-115">This is possibly a symptom of a memory leak.</span></span>  <span data-ttu-id="9c797-116">メモリリークは、ページ内のバグにより、ページが時間の経過と共により多くのメモリをより多く使用している場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="9c797-116">A memory leak is when a bug in the page causes the page to progressively use more and more memory over time.</span></span>  
*   <span data-ttu-id="9c797-117">**ページのパフォーマンスが一貫して悪く**なります。</span><span class="sxs-lookup"><span data-stu-id="9c797-117">**The performance of a page is consistently bad**.</span></span>  <span data-ttu-id="9c797-118">これは、メモリの膨張の症状である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-118">This is possibly a symptom of memory bloat.</span></span>  <span data-ttu-id="9c797-119">メモリの膨張とは、ページが最適なページ速度に必要とするよりも多くのメモリを使用することです。</span><span class="sxs-lookup"><span data-stu-id="9c797-119">Memory bloat is when a page uses more memory than is necessary for optimal page speed.</span></span>  
*   <span data-ttu-id="9c797-120">**ページのパフォーマンスが遅れているか、または頻繁に一時停止するように表示され**ます。</span><span class="sxs-lookup"><span data-stu-id="9c797-120">**The performance of a page is delayed or appears to pause frequently**.</span></span>  <span data-ttu-id="9c797-121">これは、ガベージコレクションが頻繁に発生する可能性が高いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="9c797-121">This is possibly a symptom of frequent garbage collections.</span></span>  <span data-ttu-id="9c797-122">ガベージコレクションは、ブラウザーがメモリを再収集したときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-122">Garbage collection is when the browser reclaims memory.</span></span>  <span data-ttu-id="9c797-123">この問題が発生すると、ブラウザーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-123">The browser decides when this happens.</span></span>  <span data-ttu-id="9c797-124">コレクション中には、実行中のすべてのスクリプトが一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-124">During collections, all script running is paused.</span></span>  <span data-ttu-id="9c797-125">そのため、ブラウザーが大量にガベージコレクションを実行している場合、スクリプトランタイムはあまり中断されません。</span><span class="sxs-lookup"><span data-stu-id="9c797-125">So if the browser is garbage collecting a lot, script runtime is going to get paused a lot.</span></span>  

### <span data-ttu-id="9c797-126">メモリ量の増大: "多すぎますか?"</span><span class="sxs-lookup"><span data-stu-id="9c797-126">Memory bloat: how much is "too much"?</span></span>  

<span data-ttu-id="9c797-127">メモリリークは簡単に定義できます。</span><span class="sxs-lookup"><span data-stu-id="9c797-127">A memory leak is easy to define.</span></span>  <span data-ttu-id="9c797-128">サイトでより多くのメモリを使用している場合は、リークが発生しています。</span><span class="sxs-lookup"><span data-stu-id="9c797-128">If a site is progressively using more and more memory, then you have a leak.</span></span>  <span data-ttu-id="9c797-129">ただし、メモリの膨張は、ピン留めが少し困難です。</span><span class="sxs-lookup"><span data-stu-id="9c797-129">But memory bloat is a bit harder to pin down.</span></span>  <span data-ttu-id="9c797-130">"過剰なメモリを使用しています" とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="9c797-130">What qualifies as "using too much memory"?</span></span>  

<span data-ttu-id="9c797-131">デバイスやブラウザーによって機能が異なるため、ここでは、ハード番号はありません。</span><span class="sxs-lookup"><span data-stu-id="9c797-131">There are no hard numbers here, because different devices and browsers have different capabilities.</span></span>  <span data-ttu-id="9c797-132">ハイエンドのスマートフォンでスムーズに実行される同じページが、ローエンドのスマートフォンでクラッシュすることがあります。</span><span class="sxs-lookup"><span data-stu-id="9c797-132">The same page that runs smoothly on a high-end smartphone may crash on a low-end smartphone.</span></span>  

<span data-ttu-id="9c797-133">ここで重要なのは、鉄道モデルを使用し、ユーザーに焦点を合わせることです。</span><span class="sxs-lookup"><span data-stu-id="9c797-133">The key here is to use the RAIL model and focus on your users.</span></span>  <span data-ttu-id="9c797-134">ユーザーが使用しているデバイスを確認し、それらのデバイスでページをテストします。</span><span class="sxs-lookup"><span data-stu-id="9c797-134">Find out what devices are popular with your users, and then test out your page on those devices.</span></span>  <span data-ttu-id="9c797-135">エクスペリエンスが一貫して悪い場合は、ページがこれらのデバイスのメモリ機能を超えている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-135">If the experience is consistently bad, the page may be exceeding the memory capabilities of those devices.</span></span>  

## <span data-ttu-id="9c797-136">Microsoft Edge Browser タスクマネージャーを使用してリアルタイムでメモリ使用量を監視する</span><span class="sxs-lookup"><span data-stu-id="9c797-136">Monitor memory use in realtime with the Microsoft Edge Browser Task Manager</span></span>  

<span data-ttu-id="9c797-137">Microsoft Edge ブラウザーのタスクマネージャーを使用して、メモリの問題の調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="9c797-137">Use the Microsoft Edge Browser Task Manager as a starting point to your memory issue investigation.</span></span>  <span data-ttu-id="9c797-138">Microsoft Edge Browser のタスクマネージャーは、ページが現在使用しているメモリの量を示すリアルタイムモニターです。</span><span class="sxs-lookup"><span data-stu-id="9c797-138">The Microsoft Edge Browser Task Manager is a realtime monitor that tells you how much memory a page is currently using.</span></span>  

1.  <span data-ttu-id="9c797-139">`Shift` + `Esc` Microsoft edge のメインメニューをクリックするか、[**その他のツール**] を選択して、  >  **Browser Task Manager** microsoft edge browser のタスクマネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c797-139">Press `Shift`+`Esc` or go to the Microsoft Edge main menu and select **More tools** > **Browser Task Manager** to open the Microsoft Edge Browser Task Manager.</span></span>  
    
    > ##### <span data-ttu-id="9c797-140">図 1</span><span class="sxs-lookup"><span data-stu-id="9c797-140">Figure 1</span></span>  
    > <span data-ttu-id="9c797-141">Microsoft Edge Browser のタスクマネージャーを開く</span><span class="sxs-lookup"><span data-stu-id="9c797-141">Opening the Microsoft Edge Browser Task Manager</span></span>  
    > ![Microsoft Edge Browser のタスクマネージャーを開く][ImageTaskManager]  
    
1.  <span data-ttu-id="9c797-143">Microsoft Edge Browser タスクマネージャーのテーブルヘッダーを右クリックし、[ **JavaScript メモリ**] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9c797-143">Right-click on the table header of the Microsoft Edge Browser Task Manager and enable **JavaScript memory**.</span></span>  
    
    > ##### <span data-ttu-id="9c797-144">図 2</span><span class="sxs-lookup"><span data-stu-id="9c797-144">Figure 2</span></span>  
    > <span data-ttu-id="9c797-145">JavaScript メモリを有効にする</span><span class="sxs-lookup"><span data-stu-id="9c797-145">Enable JavaScript memory</span></span>  
    > ![JavaScript メモリを有効にする][ImageJavascriptMemory]  
    
<span data-ttu-id="9c797-147">次の2つの列は、ページでメモリを使用する方法について、さまざまなことを示しています。</span><span class="sxs-lookup"><span data-stu-id="9c797-147">These two columns tell you different things about how your page is using memory:</span></span>  

*   <span data-ttu-id="9c797-148">**Memory**列は、ネイティブメモリを表します。</span><span class="sxs-lookup"><span data-stu-id="9c797-148">The **Memory** column represents native memory.</span></span>  <span data-ttu-id="9c797-149">DOM ノードは、ネイティブメモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-149">DOM nodes are stored in native memory.</span></span>  <span data-ttu-id="9c797-150">この値が増加すると、DOM ノードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-150">If this value is increasing, DOM nodes are getting created.</span></span>  
*   <span data-ttu-id="9c797-151">**JavaScript メモリ**列は、JS ヒープを表します。</span><span class="sxs-lookup"><span data-stu-id="9c797-151">The **JavaScript Memory** column represents the JS heap.</span></span>  <span data-ttu-id="9c797-152">この列には2つの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c797-152">This column contains two values.</span></span>  <span data-ttu-id="9c797-153">目的の値は、実際の番号 \ (かっこで囲まれた数値) です。</span><span class="sxs-lookup"><span data-stu-id="9c797-153">The value you are interested in is the live number \(the number in parentheses\).</span></span>  <span data-ttu-id="9c797-154">実際の番号は、ページ上の到達可能なオブジェクトが使用しているメモリの量を示します。</span><span class="sxs-lookup"><span data-stu-id="9c797-154">The live number represents how much memory the reachable objects on your page are using.</span></span>  <span data-ttu-id="9c797-155">この数値が増加している場合は、新しいオブジェクトが作成されているか、既存のオブジェクトが増加しています。</span><span class="sxs-lookup"><span data-stu-id="9c797-155">If this number is increasing, either new objects are being created, or the existing objects are growing.</span></span>  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <span data-ttu-id="9c797-156">パフォーマンスパネルを使用したメモリリークの視覚化</span><span class="sxs-lookup"><span data-stu-id="9c797-156">Visualize memory leaks with Performance panel</span></span>  

<span data-ttu-id="9c797-157">また、パフォーマンスパネルを調査の開始点として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c797-157">You may also use the Performance panel as another starting point in your investigation.</span></span>  <span data-ttu-id="9c797-158">パフォーマンスパネルを使用すると、時間の経過に伴うページのメモリ使用量をビジュアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="9c797-158">The Performance panel helps you visualize the memory use of a page over time.</span></span>  

1.  <span data-ttu-id="9c797-159">DevTools で [**パフォーマンス**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c797-159">Open the **Performance** panel on DevTools.</span></span>  
1.  <span data-ttu-id="9c797-160">[**メモリ**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9c797-160">Enable the **Memory** checkbox.</span></span>  
1.  <span data-ttu-id="9c797-161">[レコーディングを作成][DevtoolsEvaluatePerformanceReferenceRecord]します。</span><span class="sxs-lookup"><span data-stu-id="9c797-161">[Make a recording][DevtoolsEvaluatePerformanceReferenceRecord].</span></span>  

> [!TIP]
> <span data-ttu-id="9c797-162">記録を開始して、強制ガベージコレクションで終了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9c797-162">It is a good practice to start and end your recording with a forced garbage collection.</span></span>  <span data-ttu-id="9c797-163">記録中に **[ガベージコレクションの** ![ 強制実行 ][ImageForceGarbageCollectionIcon] ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c797-163">Click the **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button while recording to force garbage collection.</span></span>  

<span data-ttu-id="9c797-164">メモリ記録を示すには、次のコードを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9c797-164">To demonstrate memory recordings, consider the code below:</span></span>  

```javascript
var x = [];
function grow() {
    for (var i = 0; i < 10000; i++) {
        document.body.appendChild(document.createElement('div'));
    }
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="9c797-165">コードで参照されているボタンが押されるたびに、1万 `div` ノードがドキュメントの本文に追加され、100万 `x` 文字の文字列が配列にプッシュされ `x` ます。</span><span class="sxs-lookup"><span data-stu-id="9c797-165">Every time that the button referenced in the code is pressed, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array.</span></span>  <span data-ttu-id="9c797-166">このコードを実行すると、**パフォーマンス**パネルの[図 3](#figure-3)のような記録が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-166">Running this code produces a recording in the **Performance** panel like [Figure 3](#figure-3).</span></span>  

> ##### <span data-ttu-id="9c797-167">図 3</span><span class="sxs-lookup"><span data-stu-id="9c797-167">Figure 3</span></span>  
> <span data-ttu-id="9c797-168">単純な成長</span><span class="sxs-lookup"><span data-stu-id="9c797-168">Simple growth</span></span>  
> ![単純な成長][ImageSimpleGrowth]  

<span data-ttu-id="9c797-170">まず、ユーザーインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9c797-170">First, an explanation of the user interface.</span></span>  <span data-ttu-id="9c797-171">**概要**ウィンドウの**ヒープ**グラフ \ ( **NET**\) は、JS ヒープを表します。</span><span class="sxs-lookup"><span data-stu-id="9c797-171">The **HEAP** graph in the **Overview** pane \(below **NET**\) represents the JS heap.</span></span>  <span data-ttu-id="9c797-172">[**概要**] ウィンドウの下には、[**カウンター** ] ウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="9c797-172">Below the **Overview** pane is the **Counter** pane.</span></span>  <span data-ttu-id="9c797-173">ここでは、JS ヒープ (**概要**ウィンドウの**ヒープ**グラフと同じ)、ドキュメント、DOM ノード、リスナー、および GPU メモリの使用状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c797-173">Here you are able to see memory usage broken down by JS heap \(same as **HEAP** graph in the **Overview** pane\), documents, DOM nodes, listeners, and GPU memory.</span></span>  <span data-ttu-id="9c797-174">チェックボックスを無効にすると、グラフから非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9c797-174">Disabling a checkbox hides it from the graph.</span></span>  

<span data-ttu-id="9c797-175">これで、コードの分析が[図 3](#figure-3)と比較されました。</span><span class="sxs-lookup"><span data-stu-id="9c797-175">Now, an analysis of the code compared with [Figure 3](#figure-3).</span></span>  <span data-ttu-id="9c797-176">Node カウンター (緑のグラフ \) を見ると、コードに一致していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c797-176">If you look at the node counter \(the green graph\) you are able to see that it matches up cleanly with the code.</span></span>  <span data-ttu-id="9c797-177">個別の手順でノードカウントが増加します。</span><span class="sxs-lookup"><span data-stu-id="9c797-177">The node count increases in discrete steps.</span></span>  <span data-ttu-id="9c797-178">ノード数が増加すると、がに `grow()` なります。</span><span class="sxs-lookup"><span data-stu-id="9c797-178">You may presume that each increase in the node count is a call to `grow()`.</span></span>  <span data-ttu-id="9c797-179">JS ヒープグラフ \ (青色のグラフ \) は、それほど簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="9c797-179">The JS heap graph \(the blue graph\) is not as straightforward.</span></span>  <span data-ttu-id="9c797-180">ベストプラクティスに従うと、最初の dip は、実際には強制的なガベージコレクションです。 (**ガベージ**コレクションの強制ガベージコレクションボタンを押すと実現 ![ ][ImageForceGarbageCollectionIcon] できます)。</span><span class="sxs-lookup"><span data-stu-id="9c797-180">In keeping with best practices, the first dip is actually a forced garbage collection \(achieved by pressing the  **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button\).</span></span>  <span data-ttu-id="9c797-181">レコーディングの進行に応じて、JS ヒープサイズのスパイクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c797-181">As the recording progresses you are able to see that the JS heap size spikes.</span></span>  <span data-ttu-id="9c797-182">これは自然であり、予想される結果です。 JavaScript コードは、ボタンをクリックするたびに DOM ノードを作成し、100万文字の文字列を作成するときに多くの作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c797-182">This is natural and expected:  the JavaScript code is creating the DOM nodes on every button click and doing a lot of work when it creates the string of one million characters.</span></span>  <span data-ttu-id="9c797-183">ここでの重要なポイントは、JS ヒープの終了日が開始日よりも大きくなります (ここでは、"先頭" は強制ガベージコレクションの後にあります)。</span><span class="sxs-lookup"><span data-stu-id="9c797-183">The key thing here is the fact that the JS heap ends higher than it began \(the "beginning" here being the point after the forced garbage collection\).</span></span>  <span data-ttu-id="9c797-184">実際の環境では、JS ヒープサイズまたはノードサイズが増加するというパターンが表示された場合、メモリリークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-184">In the real world, if you saw this pattern of increasing JS heap size or node size, it may potentially define a memory leak.</span></span>  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <span data-ttu-id="9c797-185">ヒープスナップショットによるデタッチされた DOM ツリーメモリリークの検出</span><span class="sxs-lookup"><span data-stu-id="9c797-185">Discover detached DOM tree memory leaks with Heap Snapshots</span></span>  

<span data-ttu-id="9c797-186">DOM ノードは、ページ上で実行されている DOM ツリーまたは JavaScript コードからノードへの参照がない場合にのみガベージコレクションされます。</span><span class="sxs-lookup"><span data-stu-id="9c797-186">A DOM node is only garbage collected when there are no references to the node from either the DOM tree or JavaScript code running on the page.</span></span>  <span data-ttu-id="9c797-187">ノードは、DOM ツリーから削除されたときに "デタッチ" されますが、一部の JavaScript ではそのノードを引き続き参照します。</span><span class="sxs-lookup"><span data-stu-id="9c797-187">A node is said to be "detached" when it is removed from the DOM tree but some JavaScript still references it.</span></span>  <span data-ttu-id="9c797-188">デタッチされた DOM ノードは、メモリリークの一般的な原因です。</span><span class="sxs-lookup"><span data-stu-id="9c797-188">Detached DOM nodes are a common cause of memory leaks.</span></span>  <span data-ttu-id="9c797-189">このセクションでは、DevTools でのヒーププロファイラーを使って、デタッチされているノードを特定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c797-189">This section teaches you how to use the heap profilers in DevTools to identify detached nodes.</span></span>  

<span data-ttu-id="9c797-190">デタッチされた DOM ノードの簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9c797-190">Here is a simple example of detached DOM nodes.</span></span>  

```javascript
var detachedNodes;
function create() {
    var ul = document.createElement('ul');
    for (var i = 0; i < 10; i++) {
        var li = document.createElement('li');
        ul.appendChild(li);
    }
    detachedNodes = ul;
}
document.getElementById('create').addEventListener('click', create);
```  

<span data-ttu-id="9c797-191">コードで参照されているボタンをクリックすると、 `ul` 10 個の子を持つノードが作成さ `li` れます。</span><span class="sxs-lookup"><span data-stu-id="9c797-191">Clicking the button referenced in the code creates a `ul` node with ten `li` children.</span></span>  <span data-ttu-id="9c797-192">これらのノードはコードによって参照されますが、DOM ツリーには存在しないため、それぞれがデタッチされます。</span><span class="sxs-lookup"><span data-stu-id="9c797-192">These nodes are referenced by the code but do not exist in the DOM tree, so each is detached.</span></span>  

<span data-ttu-id="9c797-193">ヒープスナップショットは、デタッチされたノードを特定する方法の1つです。</span><span class="sxs-lookup"><span data-stu-id="9c797-193">Heap snapshots are one way to identify detached nodes.</span></span>  <span data-ttu-id="9c797-194">名前として、ヒープスナップショットは、スナップショットの時点で、ページの JS オブジェクトと DOM ノードの間でメモリがどのように配分されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="9c797-194">As the name implies, heap snapshots show you how memory is distributed among the JS objects and DOM nodes for your page at the point of time of the snapshot.</span></span>  

<span data-ttu-id="9c797-195">スナップショットを作成するには、DevTools を開き、[**メモリ**] パネルに移動して、[**ヒープスナップショット**] ラジオボタンを選択し、[**スナップショットを撮る**] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="9c797-195">To create a snapshot, open DevTools and go to the **Memory** panel, select the **Heap snapshot** radio button, and then press the **Take snapshot** button.</span></span>  

> ##### <span data-ttu-id="9c797-196">図 4</span><span class="sxs-lookup"><span data-stu-id="9c797-196">Figure 4</span></span>  
> <span data-ttu-id="9c797-197">ヒープスナップショットの取得</span><span class="sxs-lookup"><span data-stu-id="9c797-197">Take heap snapshot</span></span>  
> ![ヒープスナップショットの取得][ImageTakeHeapSnapshot]  

<span data-ttu-id="9c797-199">スナップショットの処理と読み込みに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-199">The snapshot may take some time to process and load.</span></span>  <span data-ttu-id="9c797-200">完了したら、左側のパネル \ (名前付き**ヒープスナップショット**) から選択します。</span><span class="sxs-lookup"><span data-stu-id="9c797-200">After it is finished, select it from the left-hand panel \(named **HEAP SNAPSHOTS**\).</span></span>  

<span data-ttu-id="9c797-201">`Detached`デタッチされた DOM ツリーを検索するには、**クラスフィルター**のテキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9c797-201">Type `Detached` in the **Class filter** textbox to search for detached DOM trees.</span></span>  

> ##### <span data-ttu-id="9c797-202">図 5</span><span class="sxs-lookup"><span data-stu-id="9c797-202">Figure 5</span></span>  
> <span data-ttu-id="9c797-203">デタッチしたノードのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="9c797-203">Filtering for detached nodes</span></span>  
> ![デタッチしたノードのフィルター処理][ImageFilteringForDetachedNodes]  

<span data-ttu-id="9c797-205">Carats を展開して、デタッチされたツリーを調査します。</span><span class="sxs-lookup"><span data-stu-id="9c797-205">Expand the carats to investigate a detached tree.</span></span>  

> ##### <span data-ttu-id="9c797-206">図 6</span><span class="sxs-lookup"><span data-stu-id="9c797-206">Figure 6</span></span>  
> <span data-ttu-id="9c797-207">デタッチしたツリーの調査</span><span class="sxs-lookup"><span data-stu-id="9c797-207">Investigating detached tree</span></span>  
> ![デタッチしたツリーの調査][ImageInvestigatingDetachedTree]  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

<span data-ttu-id="9c797-209">ノードをクリックして、さらに詳しく調べます。</span><span class="sxs-lookup"><span data-stu-id="9c797-209">Click on a node to investigate it further.</span></span>  <span data-ttu-id="9c797-210">[**オブジェクト**] ウィンドウには、参照しているコードに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-210">In the **Objects** pane you are able to see more information about the code that is referencing it.</span></span>  <span data-ttu-id="9c797-211">たとえば、[図 7](#figure-7)では、変数がそのノードを参照していることを確認でき `detachedNodes` ます。</span><span class="sxs-lookup"><span data-stu-id="9c797-211">For example, in [Figure 7](#figure-7) you are able to see that the `detachedNodes` variable is referencing the node.</span></span>  <span data-ttu-id="9c797-212">この特定のメモリリークを解決するには、変数を使うコードを調べて、不要 `detachedUNode` になったときにノードへの参照が削除されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-212">To fix this particular memory leak, you should study the code that uses the `detachedUNode` variable and ensure that the reference to the node is removed when it is no longer needed.</span></span>

> ##### <span data-ttu-id="9c797-213">図 7</span><span class="sxs-lookup"><span data-stu-id="9c797-213">Figure 7</span></span>  
> <span data-ttu-id="9c797-214">ノードの調査</span><span class="sxs-lookup"><span data-stu-id="9c797-214">Investigating a node</span></span>  
> ![ノードの調査][ImageInvestigatingNode]  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <span data-ttu-id="9c797-216">タイムライン上の割り当てインストルメンテーションを使用して JS ヒープメモリリークを特定する</span><span class="sxs-lookup"><span data-stu-id="9c797-216">Identify JS heap memory leaks with Allocation instrumentation on timeline</span></span>  

<span data-ttu-id="9c797-217">**タイムライン上の割り当てインストルメンテーション**は、JS ヒープのメモリリークを追跡するのに役立つ別のツールです。</span><span class="sxs-lookup"><span data-stu-id="9c797-217">**Allocation instrumentation on timeline** is another tool that may help you track down memory leaks in your JS heap.</span></span>  

<span data-ttu-id="9c797-218">次のコードを使用して、**タイムラインの割り当てインストルメンテーション**を示します。</span><span class="sxs-lookup"><span data-stu-id="9c797-218">Demonstrate **Allocation instrumentation on timeline**  using the following code.</span></span>  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="9c797-219">コードで参照されているボタンが押されるたびに、配列に100万文字の文字列が追加され `x` ます。</span><span class="sxs-lookup"><span data-stu-id="9c797-219">Every time that the button referenced in the code is pushed, a string of one million characters is added to the `x` array.</span></span>  

<span data-ttu-id="9c797-220">タイムライン上に割り当てインストルメンテーションを記録するには、[DevTools] を開き、[**メモリ**] パネルに移動して、[**タイムライン上の割り当てインストルメンテーション**] を選びます。次に、[**スタート**] ボタンを押して、メモリリークの原因であると思われる操作を実行し、完了したら [**記録**終了] をクリックし ![ ][ImageStopRecordingIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="9c797-220">To record an Allocation instrumentation on timeline, open DevTools, go to the **Memory** panel, select the **Allocation instrumentation on timeline** radio button, press the **Start** button, perform the action that you suspect is causing the memory leak, and then press the **Stop recording heap profile** ![stop recording][ImageStopRecordingIcon] button when you are done.</span></span>  

<span data-ttu-id="9c797-221">記録中は、[図 8](#figure-8)のように、タイムライン上の割り当てインストルメンテーションで青色のバーが表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c797-221">As you are recording, notice if any blue bars show up on the Allocation instrumentation on timeline, like in [Figure 8](#figure-8).</span></span>  

> ##### <span data-ttu-id="9c797-222">図 8</span><span class="sxs-lookup"><span data-stu-id="9c797-222">Figure 8</span></span>  
> <span data-ttu-id="9c797-223">新しい割り当て</span><span class="sxs-lookup"><span data-stu-id="9c797-223">New allocations</span></span>  
> ![新しい割り当て][ImageNewAllocations]  

<span data-ttu-id="9c797-225">これらの青いバーは、新しいメモリ割り当てを表します。</span><span class="sxs-lookup"><span data-stu-id="9c797-225">Those blue bars represent new memory allocations.</span></span>  <span data-ttu-id="9c797-226">これらの新しいメモリ割り当ては、メモリリークの候補です。</span><span class="sxs-lookup"><span data-stu-id="9c797-226">Those new memory allocations are your candidates for memory leaks.</span></span>  <span data-ttu-id="9c797-227">バーを拡大して、指定した期間内に割り当てられたオブジェクトのみを表示するように、**コンストラクター**ウィンドウをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="9c797-227">You are able to zoom on a bar to filter the **Constructor** pane to only show objects that were allocated during the specified timeframe.</span></span>  

> ##### <span data-ttu-id="9c797-228">図 9</span><span class="sxs-lookup"><span data-stu-id="9c797-228">Figure 9</span></span>  
> <span data-ttu-id="9c797-229">拡大された割り当てタイムライン</span><span class="sxs-lookup"><span data-stu-id="9c797-229">Zoomed allocation timeline</span></span>  
> ![拡大された割り当てタイムライン][ImageZoomedAllocationTimeline]  

<span data-ttu-id="9c797-231">オブジェクトを展開し、その値をクリックすると、**オブジェクト**ウィンドウの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-231">Expand the object and click on the value to view more details in the **Object** pane.</span></span>  <span data-ttu-id="9c797-232">たとえば、[図 10](#figure-10)では、新しく割り当てられたオブジェクトの詳細を表示することで、 `x` スコープ内の変数に割り当てられていることを確認でき `Window` ます。</span><span class="sxs-lookup"><span data-stu-id="9c797-232">For example, in [Figure 10](#figure-10), by viewing the details of the object that was newly allocated, you should be able to see that it was allocated to the `x` variable in the `Window` scope.</span></span>  

> ##### <span data-ttu-id="9c797-233">図 10</span><span class="sxs-lookup"><span data-stu-id="9c797-233">Figure 10</span></span> 
> <span data-ttu-id="9c797-234">オブジェクトの詳細</span><span class="sxs-lookup"><span data-stu-id="9c797-234">Object details</span></span>  
> ![オブジェクトの詳細][ImageObjectDetail]  

## <span data-ttu-id="9c797-236">関数によるメモリ割り当てを調べる</span><span class="sxs-lookup"><span data-stu-id="9c797-236">Investigate memory allocation by function</span></span>   

<span data-ttu-id="9c797-237">**アロケーションサンプリング**プロファイリング型を使って、JavaScript 関数によるメモリ割り当てを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c797-237">Use the **Allocation sampling** profiling type to view memory allocation by JavaScript function.</span></span>  

> ##### <span data-ttu-id="9c797-238">図 11</span><span class="sxs-lookup"><span data-stu-id="9c797-238">Figure 11</span></span>  
> <span data-ttu-id="9c797-239">レコード割り当てのサンプリング</span><span class="sxs-lookup"><span data-stu-id="9c797-239">Record Allocation sampling</span></span>  
> ![レコード割り当てのサンプリング][ImageRecordAllocationSampling]  

1.  <span data-ttu-id="9c797-241">[**割り当てのサンプリング**] ラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c797-241">Select the **Allocation sampling** radio button.</span></span>  <span data-ttu-id="9c797-242">ページに作業者がいる場合、[**スタート**] ボタンの横にあるドロップダウンメニューを使用して、そのユーザーをプロファイリングターゲットとして選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="9c797-242">If there is a worker on the page, you are able to select that as the profiling target using the dropdown menu next to the **Start** button.</span></span>  
1.  <span data-ttu-id="9c797-243">[**スタート**] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="9c797-243">Press the **Start** button.</span></span>  
1.  <span data-ttu-id="9c797-244">調査するページに対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c797-244">Perform the actions on the page which you want to investigate.</span></span>  
1.  <span data-ttu-id="9c797-245">すべての操作が完了したら、[**停止**] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="9c797-245">Press the **Stop** button when you have finished all of your actions.</span></span>  

<span data-ttu-id="9c797-246">DevTools には、関数によるメモリ割り当ての内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-246">DevTools shows you a breakdown of memory allocation by function.</span></span>  <span data-ttu-id="9c797-247">既定のビューは**ヘビー (ボトムアップ)** で、最も多くのメモリを割り当てた関数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-247">The default view is **Heavy (Bottom Up)**, which displays the functions that allocated the most memory at the top.</span></span>  

> ##### <span data-ttu-id="9c797-248">図 12</span><span class="sxs-lookup"><span data-stu-id="9c797-248">Figure 12</span></span>  
> <span data-ttu-id="9c797-249">割り当てのサンプリング</span><span class="sxs-lookup"><span data-stu-id="9c797-249">Allocation sampling</span></span>  
>![割り当てのサンプリング][ImageAllocationSampling]  

## <span data-ttu-id="9c797-251">頻繁にガベージコレクションを見つける</span><span class="sxs-lookup"><span data-stu-id="9c797-251">Spot frequent garbage collections</span></span>  

<span data-ttu-id="9c797-252">ページが頻繁に一時停止するように見える場合は、ガベージコレクションの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c797-252">If your page appears to pause frequently, then you may have garbage collection issues.</span></span>  

<span data-ttu-id="9c797-253">Microsoft Edge Browser タスクマネージャーまたはパフォーマンスメモリ記録を使って、頻繁にガベージコレクションを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="9c797-253">You are able to use either the Microsoft Edge Browser Task Manager or Performance memory recordings to spot frequent garbage collection.</span></span>  <span data-ttu-id="9c797-254">Microsoft Edge ブラウザータスクマネージャーでは、頻繁に増加している**メモリ**または**JavaScript メモリ**値がガベージコレクションの頻度を頻繁に表しています。</span><span class="sxs-lookup"><span data-stu-id="9c797-254">In the Microsoft Edge Browser Task Manager, frequently rising and falling **Memory** or **JavaScript Memory** values represent frequent garbage collection.</span></span>  <span data-ttu-id="9c797-255">[パフォーマンスの記録] では、JS ヒープまたはノード数のグラフに頻繁に変更 (上昇と下降) した場合、ガベージコレクションが頻繁に行われることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9c797-255">In Performance recordings, frequent changes (rising and falling) to the JS heap or node count graphs indicate frequent garbage collection.</span></span>  

<span data-ttu-id="9c797-256">問題を特定した後は、**タイムライン記録での割り当てインストルメンテーション**を使って、メモリが割り当てられている場所と割り当ての原因となっている関数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c797-256">After you have identified the problem, you are able to use an **Allocation instrumentation on timeline** recording to find out where memory is being allocated and which functions are causing the allocations.</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageForceGarbageCollectionIcon]: /microsoft-edge/devtools-guide-chromium/media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: /microsoft-edge/devtools-guide-chromium/media/stop-recording-icon.msft.png  

[ImageTaskManager]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png "図 1: Microsoft Edge ブラウザーのタスクマネージャーを開く"  
[ImageJavascriptMemory]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png "図 2: JavaScript メモリを有効にする"  
[ImageSimpleGrowth]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-1-performance-memory.msft.png "図 3: 単純な成長"  
[ImageTakeHeapSnapshot]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png "図 4: ヒープスナップショットを撮る"  
[ImageFilteringForDetachedNodes]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png "図 5: デタッチしたノードのフィルター処理"  
[ImageInvestigatingDetachedTree]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png "図 6: デタッチしたツリーの調査"  
[ImageInvestigatingNode]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png "図 7: ノードの調査"  
[ImageNewAllocations]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png "図 8: 新しい割り当て"  
[ImageZoomedAllocationTimeline]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png "図 9: 割り当てのタイムラインを拡大する"  
[ImageObjectDetail]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png "図 10: オブジェクトの詳細"  
[ImageRecordAllocationSampling]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png "図 11: 割り当てのサンプリングの記録"  
[ImageAllocationSampling]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png "図 12: 割り当てのサンプリング"  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "レコードパフォーマンス-パフォーマンス分析のリファレンス"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> <span data-ttu-id="9c797-270">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c797-270">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9c797-271">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="9c797-271">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9c797-273">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9c797-273">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
