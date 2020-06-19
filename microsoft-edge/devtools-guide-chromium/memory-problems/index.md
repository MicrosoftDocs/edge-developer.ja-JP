---
title: メモリの問題を解決する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b9e6e2af333257f0cbe0a4a354dcd1d7b862af9c
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751990"
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

# <span data-ttu-id="40ce6-103">メモリの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="40ce6-103">Fix Memory Problems</span></span>  

<span data-ttu-id="40ce6-104">Microsoft Edge と DevTools を使って、ページのパフォーマンスに影響するメモリの問題を見つける方法について説明します。これには、メモリリーク、メモリの膨張、ガベージコレクションの頻度などがあります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-104">Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.</span></span>  

### <span data-ttu-id="40ce6-105">まとめ</span><span class="sxs-lookup"><span data-stu-id="40ce6-105">Summary</span></span>  

*   <span data-ttu-id="40ce6-106">Microsoft Edge Browser のタスクマネージャーで現在ページで使用されているメモリの量を確認します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-106">Find out how much memory your page is currently using with the Microsoft Edge Browser Task Manager.</span></span>  
*   <span data-ttu-id="40ce6-107">メモリ使用量を時間の経過と共に**メモリ**パネルでビジュアル化します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-107">Visualize memory usage over time with the **Memory** panel.</span></span>  
*   <span data-ttu-id="40ce6-108">**ヒープスナップショット**を使用して、デタッチされた DOM ツリー (メモリリークの一般的な原因) を特定します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-108">Identify detached DOM trees \(a common cause of memory leaks\) with **Heap snapshot**.</span></span>  
*   <span data-ttu-id="40ce6-109">新しいメモリが JavaScript ヒープ \ (JS ヒープ) に割り当てられている場合は、**タイムラインの割り当てインストルメンテーション**で確認できます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-109">Find out when new memory is being allocated in your JavaScript heap \(JS heap\) with **Allocation instrumentation on timeline**.</span></span>  

## <span data-ttu-id="40ce6-110">概要</span><span class="sxs-lookup"><span data-stu-id="40ce6-110">Overview</span></span>  

<span data-ttu-id="40ce6-111">**鉄道**のパフォーマンスモデルの精神においては、パフォーマンスの取り組みの焦点をユーザーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-111">In the spirit of the **RAIL** performance model, the focus of your performance efforts should be your users.</span></span>  

<!--todo: add RAIL section when available  -->  

<span data-ttu-id="40ce6-112">メモリの問題は、ユーザーによって気が付きされることが多いために重要です。</span><span class="sxs-lookup"><span data-stu-id="40ce6-112">Memory issues are important because they are often perceivable by users.</span></span>  <span data-ttu-id="40ce6-113">次の方法で、メモリの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-113">Users may perceive memory issues in the following ways:</span></span>  

*   <span data-ttu-id="40ce6-114">**ページのパフォーマンスが時間の経過と共に悪化**します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-114">**The performance of a page gets progressively worse over time**.</span></span>  <span data-ttu-id="40ce6-115">これは、メモリリークの症状である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-115">This is possibly a symptom of a memory leak.</span></span>  <span data-ttu-id="40ce6-116">メモリリークは、ページ内のバグにより、ページが時間の経過と共により多くのメモリをより多く使用している場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-116">A memory leak is when a bug in the page causes the page to progressively use more and more memory over time.</span></span>  
*   <span data-ttu-id="40ce6-117">**ページのパフォーマンスが一貫して悪く**なります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-117">**The performance of a page is consistently bad**.</span></span>  <span data-ttu-id="40ce6-118">これは、メモリの膨張の症状である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-118">This is possibly a symptom of memory bloat.</span></span>  <span data-ttu-id="40ce6-119">メモリの膨張とは、ページが最適なページ速度に必要とするよりも多くのメモリを使用することです。</span><span class="sxs-lookup"><span data-stu-id="40ce6-119">Memory bloat is when a page uses more memory than is necessary for optimal page speed.</span></span>  
*   <span data-ttu-id="40ce6-120">**ページのパフォーマンスが遅れているか、または頻繁に一時停止するように表示され**ます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-120">**The performance of a page is delayed or appears to pause frequently**.</span></span>  <span data-ttu-id="40ce6-121">これは、ガベージコレクションが頻繁に発生する可能性が高いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-121">This is possibly a symptom of frequent garbage collections.</span></span>  <span data-ttu-id="40ce6-122">ガベージコレクションは、ブラウザーがメモリを再収集したときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-122">Garbage collection is when the browser reclaims memory.</span></span>  <span data-ttu-id="40ce6-123">この問題が発生すると、ブラウザーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-123">The browser decides when this happens.</span></span>  <span data-ttu-id="40ce6-124">コレクション中には、実行中のすべてのスクリプトが一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-124">During collections, all script running is paused.</span></span>  <span data-ttu-id="40ce6-125">そのため、ブラウザーが大量にガベージコレクションを実行している場合、スクリプトランタイムはあまり中断されません。</span><span class="sxs-lookup"><span data-stu-id="40ce6-125">So if the browser is garbage collecting a lot, script runtime is going to get paused a lot.</span></span>  

### <span data-ttu-id="40ce6-126">メモリ量の増大: "多すぎますか?"</span><span class="sxs-lookup"><span data-stu-id="40ce6-126">Memory bloat: how much is "too much"?</span></span>  

<span data-ttu-id="40ce6-127">メモリリークは簡単に定義できます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-127">A memory leak is easy to define.</span></span>  <span data-ttu-id="40ce6-128">サイトでより多くのメモリを使用している場合は、リークが発生しています。</span><span class="sxs-lookup"><span data-stu-id="40ce6-128">If a site is progressively using more and more memory, then you have a leak.</span></span>  <span data-ttu-id="40ce6-129">ただし、メモリの膨張は、ピン留めが少し困難です。</span><span class="sxs-lookup"><span data-stu-id="40ce6-129">But memory bloat is a bit harder to pin down.</span></span>  <span data-ttu-id="40ce6-130">"過剰なメモリを使用しています" とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="40ce6-130">What qualifies as "using too much memory"?</span></span>  

<span data-ttu-id="40ce6-131">デバイスやブラウザーによって機能が異なるため、ここでは、ハード番号はありません。</span><span class="sxs-lookup"><span data-stu-id="40ce6-131">There are no hard numbers here, because different devices and browsers have different capabilities.</span></span>  <span data-ttu-id="40ce6-132">ハイエンドのスマートフォンでスムーズに実行される同じページが、ローエンドのスマートフォンでクラッシュすることがあります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-132">The same page that runs smoothly on a high-end smartphone may crash on a low-end smartphone.</span></span>  

<span data-ttu-id="40ce6-133">ここで重要なのは、鉄道モデルを使用し、ユーザーに焦点を合わせることです。</span><span class="sxs-lookup"><span data-stu-id="40ce6-133">The key here is to use the RAIL model and focus on your users.</span></span>  <span data-ttu-id="40ce6-134">ユーザーが使用しているデバイスを確認し、それらのデバイスでページをテストします。</span><span class="sxs-lookup"><span data-stu-id="40ce6-134">Find out what devices are popular with your users, and then test out your page on those devices.</span></span>  <span data-ttu-id="40ce6-135">エクスペリエンスが一貫して悪い場合は、ページがこれらのデバイスのメモリ機能を超えている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-135">If the experience is consistently bad, the page may be exceeding the memory capabilities of those devices.</span></span>  

## <span data-ttu-id="40ce6-136">Microsoft Edge Browser タスクマネージャーを使用してリアルタイムでメモリ使用量を監視する</span><span class="sxs-lookup"><span data-stu-id="40ce6-136">Monitor memory use in realtime with the Microsoft Edge Browser Task Manager</span></span>  

<span data-ttu-id="40ce6-137">Microsoft Edge ブラウザーのタスクマネージャーを使用して、メモリの問題の調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-137">Use the Microsoft Edge Browser Task Manager as a starting point to your memory issue investigation.</span></span>  <span data-ttu-id="40ce6-138">Microsoft Edge Browser のタスクマネージャーは、ページが現在使用しているメモリの量を示すリアルタイムモニターです。</span><span class="sxs-lookup"><span data-stu-id="40ce6-138">The Microsoft Edge Browser Task Manager is a realtime monitor that tells you how much memory a page is currently using.</span></span>  

1.  <span data-ttu-id="40ce6-139">`Shift` + `Esc` Microsoft edge のメインメニューをクリックするか、[**その他のツール**] を選択して、  >  **Browser Task Manager** microsoft edge browser のタスクマネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-139">Press `Shift`+`Esc` or go to the Microsoft Edge main menu and select **More tools** > **Browser Task Manager** to open the Microsoft Edge Browser Task Manager.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="Microsoft Edge Browser のタスクマネージャーを開く" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       <span data-ttu-id="40ce6-141">図 1: Microsoft Edge ブラウザーのタスクマネージャーを開く</span><span class="sxs-lookup"><span data-stu-id="40ce6-141">Figure 1:  Opening the Microsoft Edge Browser Task Manager</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="40ce6-142">Microsoft Edge Browser タスクマネージャーのテーブルの見出しにマウスポインターを置いて、コンテキストメニュー \ (右クリック \) を開き、 **JavaScript メモリ**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="40ce6-142">Hover on the table header of the Microsoft Edge Browser Task Manager, open the contextual menu \(right-click\), and enable **JavaScript memory**.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="JavaScript メモリを有効にする" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       <span data-ttu-id="40ce6-144">図 2: JavaScript メモリを有効にする</span><span class="sxs-lookup"><span data-stu-id="40ce6-144">Figure 2:  Enable JavaScript memory</span></span>  
    :::image-end:::  
    
<span data-ttu-id="40ce6-145">この2つの列は、ページがどのようにメモリを使用しているかについて、さまざまなことを示します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-145">These two columns tell you different things about how your page is using memory.</span></span>  

*   <span data-ttu-id="40ce6-146">**Memory**列は、ネイティブメモリを表します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-146">The **Memory** column represents native memory.</span></span>  <span data-ttu-id="40ce6-147">DOM ノードは、ネイティブメモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-147">DOM nodes are stored in native memory.</span></span>  <span data-ttu-id="40ce6-148">この値が増加すると、DOM ノードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-148">If this value is increasing, DOM nodes are getting created.</span></span>  
*   <span data-ttu-id="40ce6-149">**JavaScript メモリ**列は、JS ヒープを表します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-149">The **JavaScript Memory** column represents the JS heap.</span></span>  <span data-ttu-id="40ce6-150">この列には2つの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="40ce6-150">This column contains two values.</span></span>  <span data-ttu-id="40ce6-151">目的の値は、実際の番号 \ (かっこで囲まれた数値) です。</span><span class="sxs-lookup"><span data-stu-id="40ce6-151">The value you are interested in is the live number \(the number in parentheses\).</span></span>  <span data-ttu-id="40ce6-152">実際の番号は、ページ上の到達可能なオブジェクトが使用しているメモリの量を示します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-152">The live number represents how much memory the reachable objects on your page are using.</span></span>  <span data-ttu-id="40ce6-153">この数値が増加している場合は、新しいオブジェクトが作成されているか、既存のオブジェクトが増加しています。</span><span class="sxs-lookup"><span data-stu-id="40ce6-153">If this number is increasing, either new objects are being created, or the existing objects are growing.</span></span>  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <span data-ttu-id="40ce6-154">パフォーマンスパネルを使用したメモリリークの視覚化</span><span class="sxs-lookup"><span data-stu-id="40ce6-154">Visualize memory leaks with Performance panel</span></span>  

<span data-ttu-id="40ce6-155">また、パフォーマンスパネルを調査の開始点として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-155">You may also use the Performance panel as another starting point in your investigation.</span></span>  <span data-ttu-id="40ce6-156">パフォーマンスパネルを使用すると、時間の経過に伴うページのメモリ使用量をビジュアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-156">The Performance panel helps you visualize the memory use of a page over time.</span></span>  

1.  <span data-ttu-id="40ce6-157">DevTools で [**パフォーマンス**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-157">Open the **Performance** panel on DevTools.</span></span>  
1.  <span data-ttu-id="40ce6-158">[**メモリ**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="40ce6-158">Enable the **Memory** checkbox.</span></span>  
1.  <span data-ttu-id="40ce6-159">[レコーディングを作成][DevtoolsEvaluatePerformanceReferenceRecord]します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-159">[Make a recording][DevtoolsEvaluatePerformanceReferenceRecord].</span></span>  

> [!TIP]
> <span data-ttu-id="40ce6-160">記録を開始して、強制ガベージコレクションで終了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40ce6-160">It is a good practice to start and end your recording with a forced garbage collection.</span></span>  <span data-ttu-id="40ce6-161">**collect garbage** ![ 記録中にガベージ ][ImageForceGarbageCollectionIcon] コレクションを強制的に実行するには、[ガベージコレクションの強制実行] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-161">Select the **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button while recording to force garbage collection.</span></span>  

<span data-ttu-id="40ce6-162">メモリ記録を示すには、次のコードを検討してください。</span><span class="sxs-lookup"><span data-stu-id="40ce6-162">To demonstrate memory recordings, consider the code below:</span></span>  

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

<span data-ttu-id="40ce6-163">コードで参照されているボタンが押されるたびに、1万 `div` ノードがドキュメントの本文に追加され、100万 `x` 文字の文字列が配列にプッシュされ `x` ます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-163">Every time that the button referenced in the code is pressed, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array.</span></span>  <span data-ttu-id="40ce6-164">前のコードサンプルを実行すると、次の図のような [**パフォーマンス**] パネルに記録が生成されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-164">Running the previous code sample produces a recording in the **Performance** panel like the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="単純な成長" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   <span data-ttu-id="40ce6-166">図 3: 単純な成長</span><span class="sxs-lookup"><span data-stu-id="40ce6-166">Figure 3:  Simple growth</span></span>  
:::image-end:::  

<span data-ttu-id="40ce6-167">まず、ユーザーインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-167">First, an explanation of the user interface.</span></span>  <span data-ttu-id="40ce6-168">**概要**ウィンドウの**ヒープ**グラフ \ ( **NET**\) は、JS ヒープを表します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-168">The **HEAP** graph in the **Overview** pane \(below **NET**\) represents the JS heap.</span></span>  <span data-ttu-id="40ce6-169">[**概要**] ウィンドウの下には、[**カウンター** ] ウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-169">Below the **Overview** pane is the **Counter** pane.</span></span>  <span data-ttu-id="40ce6-170">ここでは、JS ヒープ (**概要**ウィンドウの**ヒープ**グラフと同じ)、ドキュメント、DOM ノード、リスナー、および GPU メモリの使用状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-170">Here you are able to see memory usage broken down by JS heap \(same as **HEAP** graph in the **Overview** pane\), documents, DOM nodes, listeners, and GPU memory.</span></span>  <span data-ttu-id="40ce6-171">チェックボックスを無効にすると、グラフから非表示になります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-171">Disabling a checkbox hides it from the graph.</span></span>  

<span data-ttu-id="40ce6-172">これで、前の図と比較したコードの分析が実行されました。</span><span class="sxs-lookup"><span data-stu-id="40ce6-172">Now, an analysis of the code compared with the previous figure.</span></span>  <span data-ttu-id="40ce6-173">Node カウンター (緑のグラフ \) を見ると、コードに一致していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-173">If you look at the node counter \(the green graph\) you are able to see that it matches up cleanly with the code.</span></span>  <span data-ttu-id="40ce6-174">個別の手順でノードカウントが増加します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-174">The node count increases in discrete steps.</span></span>  <span data-ttu-id="40ce6-175">ノード数が増加すると、がに `grow()` なります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-175">You may presume that each increase in the node count is a call to `grow()`.</span></span>  <span data-ttu-id="40ce6-176">JS ヒープグラフ \ (青色のグラフ \) は、それほど簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="40ce6-176">The JS heap graph \(the blue graph\) is not as straightforward.</span></span>  <span data-ttu-id="40ce6-177">ベストプラクティスに従うと、最初の dip は、実際には強制的なガベージコレクションです。 (**ガベージ**コレクションの強制ガベージコレクションボタンを押すと実現 ![ ][ImageForceGarbageCollectionIcon] できます)。</span><span class="sxs-lookup"><span data-stu-id="40ce6-177">In keeping with best practices, the first dip is actually a forced garbage collection \(achieved by pressing the  **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button\).</span></span>  <span data-ttu-id="40ce6-178">レコーディングの進行に応じて、JS ヒープサイズのスパイクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-178">As the recording progresses you are able to see that the JS heap size spikes.</span></span>  <span data-ttu-id="40ce6-179">これは自然であり、予想される結果です。 JavaScript コードは、ボタンを押すたびに DOM ノードを作成し、100万文字の文字列を作成するときに多くの作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-179">This is natural and expected:  the JavaScript code is creating the DOM nodes on every button press and doing a lot of work when it creates the string of one million characters.</span></span>  <span data-ttu-id="40ce6-180">ここでの重要なポイントは、JS ヒープの終了日が開始日よりも大きくなります (ここでは、"先頭" は強制ガベージコレクションの後にあります)。</span><span class="sxs-lookup"><span data-stu-id="40ce6-180">The key thing here is the fact that the JS heap ends higher than it began \(the "beginning" here being the point after the forced garbage collection\).</span></span>  <span data-ttu-id="40ce6-181">実際の環境では、JS ヒープサイズまたはノードサイズが増加するというパターンが表示された場合、メモリリークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-181">In the real world, if you saw this pattern of increasing JS heap size or node size, it may potentially define a memory leak.</span></span>  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <span data-ttu-id="40ce6-182">ヒープスナップショットによるデタッチされた DOM ツリーメモリリークの検出</span><span class="sxs-lookup"><span data-stu-id="40ce6-182">Discover detached DOM tree memory leaks with Heap Snapshots</span></span>  

<span data-ttu-id="40ce6-183">DOM ノードは、ページ上で実行されている DOM ツリーまたは JavaScript コードからノードへの参照がない場合にのみガベージコレクションされます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-183">A DOM node is only garbage collected when there are no references to the node from either the DOM tree or JavaScript code running on the page.</span></span>  <span data-ttu-id="40ce6-184">ノードは、DOM ツリーから削除されたときに "デタッチ" されますが、一部の JavaScript ではそのノードを引き続き参照します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-184">A node is said to be "detached" when it is removed from the DOM tree but some JavaScript still references it.</span></span>  <span data-ttu-id="40ce6-185">デタッチされた DOM ノードは、メモリリークの一般的な原因です。</span><span class="sxs-lookup"><span data-stu-id="40ce6-185">Detached DOM nodes are a common cause of memory leaks.</span></span>  <span data-ttu-id="40ce6-186">このセクションでは、DevTools でのヒーププロファイラーを使って、デタッチされているノードを特定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-186">This section teaches you how to use the heap profilers in DevTools to identify detached nodes.</span></span>  

<span data-ttu-id="40ce6-187">デタッチされた DOM ノードの簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-187">Here is a simple example of detached DOM nodes.</span></span>  

```javascript
var detachedTree;

function create() {
    var ul = document.createElement('ul');
    for (var i = 0; i < 10; i++) {
        var li = document.createElement('li');
        ul.appendChild(li);
    }
    detachedTree = ul;
}
document.getElementById('create').addEventListener('click', create);
```  

<span data-ttu-id="40ce6-188">コードで参照されているボタンを選ぶと、 `ul` 10 個の子を持つノードが作成され `li` ます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-188">Selecting the button referenced in the code creates a `ul` node with ten `li` children.</span></span>  <span data-ttu-id="40ce6-189">ノードはコードによって参照されますが、DOM ツリーには存在しないため、それぞれがデタッチされます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-189">The nodes are referenced by the code but do not exist in the DOM tree, so each is detached.</span></span>  

<span data-ttu-id="40ce6-190">ヒープスナップショットは、デタッチされたノードを特定する方法の1つです。</span><span class="sxs-lookup"><span data-stu-id="40ce6-190">Heap snapshots are one way to identify detached nodes.</span></span>  <span data-ttu-id="40ce6-191">名前として、ヒープスナップショットは、スナップショットの時点で、ページの JS オブジェクトと DOM ノードの間でメモリがどのように配分されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="40ce6-191">As the name implies, heap snapshots show you how memory is distributed among the JS objects and DOM nodes for your page at the point of time of the snapshot.</span></span>  

<span data-ttu-id="40ce6-192">スナップショットを作成するには、DevTools を開き、[**メモリ**] パネルに移動して、[**ヒープスナップショット**] ラジオボタンを選択し、[**スナップショットを撮る**] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-192">To create a snapshot, open DevTools and go to the **Memory** panel, select the **Heap snapshot** radio button, and then press the **Take snapshot** button.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="ヒープスナップショットの取得" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   <span data-ttu-id="40ce6-194">図 4: ヒープスナップショットを撮る</span><span class="sxs-lookup"><span data-stu-id="40ce6-194">Figure 4:  Take heap snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="40ce6-195">スナップショットの処理と読み込みに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-195">The snapshot may take some time to process and load.</span></span>  <span data-ttu-id="40ce6-196">完了したら、左側のパネル \ (名前付き**ヒープスナップショット**) から選択します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-196">After it is finished, select it from the left-hand panel \(named **HEAP SNAPSHOTS**\).</span></span>  

<span data-ttu-id="40ce6-197">`Detached`デタッチされた DOM ツリーを検索するには、**クラスフィルター**のテキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-197">Type `Detached` in the **Class filter** textbox to search for detached DOM trees.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="デタッチしたノードのフィルター処理" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   <span data-ttu-id="40ce6-199">図 5: デタッチしたノードのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="40ce6-199">Figure 5:  Filtering for detached nodes</span></span>  
:::image-end:::  

<span data-ttu-id="40ce6-200">Carats を展開して、デタッチされたツリーを調査します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-200">Expand the carats to investigate a detached tree.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="デタッチしたツリーの調査" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   <span data-ttu-id="40ce6-202">図 6: デタッチしたツリーの調査</span><span class="sxs-lookup"><span data-stu-id="40ce6-202">Figure 6:  Investigating detached tree</span></span>  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

<span data-ttu-id="40ce6-203">ノードを選択して、さらに詳しく調べます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-203">Select a node to investigate it further.</span></span>  <span data-ttu-id="40ce6-204">[**オブジェクト**] ウィンドウには、参照しているコードに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-204">In the **Objects** pane you are able to see more information about the code that is referencing it.</span></span>  <span data-ttu-id="40ce6-205">たとえば、次の図では、変数がそのノードを参照していることを確認でき `detachedNodes` ます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-205">For example, in the following figure you are able to see that the `detachedNodes` variable is referencing the node.</span></span>  <span data-ttu-id="40ce6-206">この特定のメモリリークを解決するには、変数を使うコードを調べて、不要 `detachedNodes` になったときにノードへの参照が削除されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-206">To fix this particular memory leak, you should study the code that uses the `detachedNodes` variable and ensure that the reference to the node is removed when it is no longer needed.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="ノードの調査" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   <span data-ttu-id="40ce6-208">図 7: ノードの調査</span><span class="sxs-lookup"><span data-stu-id="40ce6-208">Figure 7:  Investigating a node</span></span>  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <span data-ttu-id="40ce6-209">タイムライン上の割り当てインストルメンテーションを使用して JS ヒープメモリリークを特定する</span><span class="sxs-lookup"><span data-stu-id="40ce6-209">Identify JS heap memory leaks with Allocation instrumentation on timeline</span></span>  

<span data-ttu-id="40ce6-210">**タイムライン上の割り当てインストルメンテーション**は、JS ヒープのメモリリークを追跡するのに役立つ別のツールです。</span><span class="sxs-lookup"><span data-stu-id="40ce6-210">**Allocation instrumentation on timeline** is another tool that may help you track down memory leaks in your JS heap.</span></span>  

<span data-ttu-id="40ce6-211">次のコードを使用して、**タイムラインの割り当てインストルメンテーション**を示します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-211">Demonstrate **Allocation instrumentation on timeline**  using the following code.</span></span>  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="40ce6-212">コードで参照されているボタンが押されるたびに、配列に100万文字の文字列が追加され `x` ます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-212">Every time that the button referenced in the code is pushed, a string of one million characters is added to the `x` array.</span></span>  

<span data-ttu-id="40ce6-213">タイムライン上に割り当てインストルメンテーションを記録するには、[DevTools] を開き、[**メモリ**] パネルに移動して、[**タイムライン上の割り当てインストルメンテーション**] を選びます。次に、[**スタート**] ボタンを押して、メモリリークの原因であると思われる操作を実行し、完了したら [**記録**終了] をクリックし ![ ][ImageStopRecordingIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-213">To record an Allocation instrumentation on timeline, open DevTools, go to the **Memory** panel, select the **Allocation instrumentation on timeline** radio button, press the **Start** button, perform the action that you suspect is causing the memory leak, and then press the **Stop recording heap profile** ![stop recording][ImageStopRecordingIcon] button when you are done.</span></span>  

<span data-ttu-id="40ce6-214">記録中に、次の図のように、タイムライン上の割り当てインストルメンテーションで青色のバーが表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-214">As you are recording, notice if any blue bars show up on the Allocation instrumentation on timeline, like in the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="新しい割り当て" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   <span data-ttu-id="40ce6-216">図 8: 新しい割り当て</span><span class="sxs-lookup"><span data-stu-id="40ce6-216">Figure 8:  New allocations</span></span>  
:::image-end:::  

<span data-ttu-id="40ce6-217">これらの青いバーは、新しいメモリ割り当てを表します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-217">Those blue bars represent new memory allocations.</span></span>  <span data-ttu-id="40ce6-218">これらの新しいメモリ割り当ては、メモリリークの候補です。</span><span class="sxs-lookup"><span data-stu-id="40ce6-218">Those new memory allocations are your candidates for memory leaks.</span></span>  <span data-ttu-id="40ce6-219">バーを拡大して、指定した期間内に割り当てられたオブジェクトのみを表示するように、**コンストラクター**ウィンドウをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-219">You are able to zoom on a bar to filter the **Constructor** pane to only show objects that were allocated during the specified timeframe.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="拡大された割り当てタイムライン" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   <span data-ttu-id="40ce6-221">図 9: 割り当てのタイムラインを拡大する</span><span class="sxs-lookup"><span data-stu-id="40ce6-221">Figure 9:  Zoomed allocation timeline</span></span>  
:::image-end:::  

<span data-ttu-id="40ce6-222">オブジェクトを展開し、[**オブジェクト**] ウィンドウで値を選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-222">Expand the object and select the value to view more details in the **Object** pane.</span></span>  <span data-ttu-id="40ce6-223">たとえば、次の図では、新しく割り当てられたオブジェクトの詳細を表示することで、スコープ内の変数に割り当てられていることを確認でき `x` `Window` ます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-223">For example, in the following figure, by viewing the details of the object that was newly allocated, you should be able to see that it was allocated to the `x` variable in the `Window` scope.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="オブジェクトの詳細" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   <span data-ttu-id="40ce6-225">図 10: オブジェクトの詳細</span><span class="sxs-lookup"><span data-stu-id="40ce6-225">Figure 10:  Object details</span></span>  
:::image-end:::  

## <span data-ttu-id="40ce6-226">関数によるメモリ割り当てを調べる</span><span class="sxs-lookup"><span data-stu-id="40ce6-226">Investigate memory allocation by function</span></span>  

<span data-ttu-id="40ce6-227">**アロケーションサンプリング**プロファイリング型を使って、JavaScript 関数によるメモリ割り当てを表示します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-227">Use the **Allocation sampling** profiling type to view memory allocation by JavaScript function.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="レコード割り当てのサンプリング" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   <span data-ttu-id="40ce6-229">図 11: 割り当てのサンプリングの記録</span><span class="sxs-lookup"><span data-stu-id="40ce6-229">Figure 11:  Record Allocation sampling</span></span>  
:::image-end:::  

1.  <span data-ttu-id="40ce6-230">[**割り当てのサンプリング**] ラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-230">Select the **Allocation sampling** radio button.</span></span>  <span data-ttu-id="40ce6-231">ページに作業者がいる場合、[**スタート**] ボタンの横にあるドロップダウンメニューを使用して、そのユーザーをプロファイリングターゲットとして選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-231">If there is a worker on the page, you are able to select that as the profiling target using the dropdown menu next to the **Start** button.</span></span>  
1.  <span data-ttu-id="40ce6-232">[**スタート**] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-232">Press the **Start** button.</span></span>  
1.  <span data-ttu-id="40ce6-233">調査するページに対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-233">Perform the actions on the page which you want to investigate.</span></span>  
1.  <span data-ttu-id="40ce6-234">すべての操作が完了したら、[**停止**] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="40ce6-234">Press the **Stop** button when you have finished all of your actions.</span></span>  

<span data-ttu-id="40ce6-235">DevTools には、関数によるメモリ割り当ての内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-235">DevTools shows you a breakdown of memory allocation by function.</span></span>  <span data-ttu-id="40ce6-236">既定のビューは**ヘビー (ボトムアップ)** で、最も多くのメモリを割り当てた関数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-236">The default view is **Heavy (Bottom Up)**, which displays the functions that allocated the most memory at the top.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="割り当てのサンプリング" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   <span data-ttu-id="40ce6-238">図 12: 割り当てのサンプリング</span><span class="sxs-lookup"><span data-stu-id="40ce6-238">Figure 12:  Allocation sampling</span></span>  
:::image-end:::  

## <span data-ttu-id="40ce6-239">頻繁にガベージコレクションを見つける</span><span class="sxs-lookup"><span data-stu-id="40ce6-239">Spot frequent garbage collections</span></span>  

<span data-ttu-id="40ce6-240">ページが頻繁に一時停止するように見える場合は、ガベージコレクションの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40ce6-240">If your page appears to pause frequently, then you may have garbage collection issues.</span></span>  

<span data-ttu-id="40ce6-241">Microsoft Edge Browser タスクマネージャーまたはパフォーマンスメモリ記録を使って、頻繁にガベージコレクションを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-241">You are able to use either the Microsoft Edge Browser Task Manager or Performance memory recordings to spot frequent garbage collection.</span></span>  <span data-ttu-id="40ce6-242">Microsoft Edge ブラウザータスクマネージャーでは、頻繁に増加している**メモリ**または**JavaScript メモリ**値がガベージコレクションの頻度を頻繁に表しています。</span><span class="sxs-lookup"><span data-stu-id="40ce6-242">In the Microsoft Edge Browser Task Manager, frequently rising and falling **Memory** or **JavaScript Memory** values represent frequent garbage collection.</span></span>  <span data-ttu-id="40ce6-243">パフォーマンスの記録では、頻繁な変更 (上昇と下降) から JS ヒープまたはノードカウントグラフは、頻繁なガベージコレクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="40ce6-243">In Performance recordings, frequent changes \(rising and falling\) to the JS heap or node count graphs indicate frequent garbage collection.</span></span>  

<span data-ttu-id="40ce6-244">問題を特定した後は、**タイムライン記録での割り当てインストルメンテーション**を使って、メモリが割り当てられている場所と割り当ての原因となっている関数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-244">After you have identified the problem, you are able to use an **Allocation instrumentation on timeline** recording to find out where memory is being allocated and which functions are causing the allocations.</span></span>  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "レコードパフォーマンス-パフォーマンス分析のリファレンス"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> <span data-ttu-id="40ce6-246">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="40ce6-246">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="40ce6-247">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="40ce6-247">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="40ce6-249">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="40ce6-249">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
