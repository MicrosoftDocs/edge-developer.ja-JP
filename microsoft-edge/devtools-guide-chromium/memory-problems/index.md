---
description: Microsoft Edgeと DevTools を使用して、メモリ リーク、メモリの大きさ、頻繁なガベージ コレクションなど、ページのパフォーマンスに影響するメモリの問題を見つける方法について説明します。
title: メモリの問題を修正する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3b2405d23dd6ee349484c9ba66d195e3ed12144b
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565030"
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
# <a name="fix-memory-problems"></a><span data-ttu-id="256b5-104">メモリの問題を修正する</span><span class="sxs-lookup"><span data-stu-id="256b5-104">Fix memory problems</span></span>  

<span data-ttu-id="256b5-105">Microsoft Edgeと DevTools を使用して、メモリ リーク、メモリの大きさ、頻繁なガベージ コレクションなど、ページのパフォーマンスに影響するメモリの問題を見つける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="256b5-105">Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.</span></span>  

### <a name="summary"></a><span data-ttu-id="256b5-106">要約</span><span class="sxs-lookup"><span data-stu-id="256b5-106">Summary</span></span>  

*   <span data-ttu-id="256b5-107">ブラウザー タスク マネージャーでページが現在使用しているメモリMicrosoft Edge確認します。</span><span class="sxs-lookup"><span data-stu-id="256b5-107">Find out how much memory your page is currently using with the Microsoft Edge Browser Task Manager.</span></span>  
*   <span data-ttu-id="256b5-108">[メモリ] パネルを使用して、時間の間にメモリ使用量 **を視覚化** します。</span><span class="sxs-lookup"><span data-stu-id="256b5-108">Visualize memory usage over time with the **Memory** panel.</span></span>  
*   <span data-ttu-id="256b5-109">ヒープ スナップショットを使用して、デタッチされた DOM ツリー \(メモリ リークの一般的な原因\) **を特定します**。</span><span class="sxs-lookup"><span data-stu-id="256b5-109">Identify detached DOM trees \(a common cause of memory leaks\) with **Heap snapshot**.</span></span>  
*   <span data-ttu-id="256b5-110">タイムライン上の Allocation インストルメンテーションを使用して、JavaScript ヒープ \(JS ヒープ\) で新しいメモリが割り当てられている **場合を確認します**。</span><span class="sxs-lookup"><span data-stu-id="256b5-110">Find out when new memory is being allocated in your JavaScript heap \(JS heap\) with **Allocation instrumentation on timeline**.</span></span>  

## <a name="overview"></a><span data-ttu-id="256b5-111">概要</span><span class="sxs-lookup"><span data-stu-id="256b5-111">Overview</span></span>  

<span data-ttu-id="256b5-112">**RAIL**パフォーマンス モデルの精神では、パフォーマンスの取り組みの焦点はユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-112">In the spirit of the **RAIL** performance model, the focus of your performance efforts should be your users.</span></span>  

<!--todo: add RAIL section when available  -->  

<span data-ttu-id="256b5-113">メモリの問題は、ユーザーが認識できる場合が多いので重要です。</span><span class="sxs-lookup"><span data-stu-id="256b5-113">Memory issues are important because they are often perceivable by users.</span></span>  <span data-ttu-id="256b5-114">ユーザーは、次の方法でメモリの問題を認識する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-114">Users may perceive memory issues in the following ways:</span></span>  

*   <span data-ttu-id="256b5-115">**ページのパフォーマンスは時間の間に徐々に悪化します**。</span><span class="sxs-lookup"><span data-stu-id="256b5-115">**The performance of a page gets progressively worse over time**.</span></span>  <span data-ttu-id="256b5-116">これは、メモリ リークの症状である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-116">This is possibly a symptom of a memory leak.</span></span>  <span data-ttu-id="256b5-117">メモリ リークとは、ページ内のバグによって、ページが時間の間に徐々に多くのメモリを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="256b5-117">A memory leak is when a bug in the page causes the page to progressively use more and more memory over time.</span></span>  
*   <span data-ttu-id="256b5-118">**ページのパフォーマンスは一貫して悪いです**。</span><span class="sxs-lookup"><span data-stu-id="256b5-118">**The performance of a page is consistently bad**.</span></span>  <span data-ttu-id="256b5-119">これは、メモリが大きかった場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-119">This is possibly a symptom of memory bloat.</span></span>  <span data-ttu-id="256b5-120">メモリが大きかったのは、ページが最適なページ速度に必要なメモリを超えるメモリを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="256b5-120">Memory bloat is when a page uses more memory than is necessary for optimal page speed.</span></span>  
*   <span data-ttu-id="256b5-121">**ページのパフォーマンスが遅れているか、頻繁に一時停止します**。</span><span class="sxs-lookup"><span data-stu-id="256b5-121">**The performance of a page is delayed or appears to pause frequently**.</span></span>  <span data-ttu-id="256b5-122">これは、ガベージ コレクションが頻繁に発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-122">This is possibly a symptom of frequent garbage collections.</span></span>  <span data-ttu-id="256b5-123">ガベージ コレクションは、ブラウザーがメモリを再利用する場合です。</span><span class="sxs-lookup"><span data-stu-id="256b5-123">Garbage collection is when the browser reclaims memory.</span></span>  <span data-ttu-id="256b5-124">ブラウザーは、これがいつ行なうのかを決定します。</span><span class="sxs-lookup"><span data-stu-id="256b5-124">The browser decides when this happens.</span></span>  <span data-ttu-id="256b5-125">コレクション中は、実行中のすべてのスクリプトが一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-125">During collections, all script running is paused.</span></span>  <span data-ttu-id="256b5-126">そのため、ブラウザーがガベージ コレクションを多く行っている場合、スクリプト ランタイムは多くの一時停止を受け取るつもりです。</span><span class="sxs-lookup"><span data-stu-id="256b5-126">So if the browser is garbage collecting a lot, script runtime is going to get paused a lot.</span></span>  

### <a name="memory-bloat-how-much-is-too-much"></a><span data-ttu-id="256b5-127">メモリが大きすぎる: どのくらい "多すぎます"?</span><span class="sxs-lookup"><span data-stu-id="256b5-127">Memory bloat: how much is "too much"?</span></span>  

<span data-ttu-id="256b5-128">メモリ リークは簡単に定義できます。</span><span class="sxs-lookup"><span data-stu-id="256b5-128">A memory leak is easy to define.</span></span>  <span data-ttu-id="256b5-129">サイトが徐々に多くのメモリを使用している場合は、リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="256b5-129">If a site is progressively using more and more memory, then you have a leak.</span></span>  <span data-ttu-id="256b5-130">ただし、メモリが大きくなった場合は、ピン留めするのが少し難しくなります。</span><span class="sxs-lookup"><span data-stu-id="256b5-130">But memory bloat is a bit harder to pin down.</span></span>  <span data-ttu-id="256b5-131">「メモリを使いすぎ」と見なす条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="256b5-131">What qualifies as "using too much memory"?</span></span>  

<span data-ttu-id="256b5-132">デバイスやブラウザーによって機能が異なるので、ハード番号はありません。</span><span class="sxs-lookup"><span data-stu-id="256b5-132">There are no hard numbers here, because different devices and browsers have different capabilities.</span></span>  <span data-ttu-id="256b5-133">高級スマートフォンでスムーズに動作するページと同じページが、ローエンド スマートフォンでクラッシュする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-133">The same page that runs smoothly on a high-end smartphone may crash on a low-end smartphone.</span></span>  

<span data-ttu-id="256b5-134">ここで重要なのは、RAIL モデルを使用してユーザーに焦点を当てる方法です。</span><span class="sxs-lookup"><span data-stu-id="256b5-134">The key here is to use the RAIL model and focus on your users.</span></span>  <span data-ttu-id="256b5-135">ユーザーに人気のあるデバイスを確認し、それらのデバイスでページをテストします。</span><span class="sxs-lookup"><span data-stu-id="256b5-135">Find out what devices are popular with your users, and then test out your page on those devices.</span></span>  <span data-ttu-id="256b5-136">エクスペリエンスが一貫して悪い場合、ページがそれらのデバイスのメモリ機能を超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-136">If the experience is consistently bad, the page may be exceeding the memory capabilities of those devices.</span></span>  

## <a name="monitor-memory-use-in-realtime-with-the-microsoft-edge-browser-task-manager"></a><span data-ttu-id="256b5-137">ブラウザー タスク マネージャーでメモリ使用量をリアルタイムMicrosoft Edge監視する</span><span class="sxs-lookup"><span data-stu-id="256b5-137">Monitor memory use in realtime with the Microsoft Edge Browser Task Manager</span></span>  

<span data-ttu-id="256b5-138">メモリの問題Microsoft Edge調査の開始点として、[ブラウザー タスク マネージャー] を使用します。</span><span class="sxs-lookup"><span data-stu-id="256b5-138">Use the Microsoft Edge Browser Task Manager as a starting point to your memory issue investigation.</span></span>  <span data-ttu-id="256b5-139">ブラウザー Microsoft Edgeマネージャーは、ページが現在使用しているメモリの量を示すリアルタイム モニターです。</span><span class="sxs-lookup"><span data-stu-id="256b5-139">The Microsoft Edge Browser Task Manager is a realtime monitor that tells you how much memory a page is currently using.</span></span>  

1.  <span data-ttu-id="256b5-140">メイン `Shift` + `Esc` メニューを選択または移動Microsoft Edge[\*\*\*\* その他のツール] [ブラウザー タスク マネージャー] を選択して、[ブラウザー タスク マネージャー] Microsoft Edge  >  \*\*\*\* 開きます。</span><span class="sxs-lookup"><span data-stu-id="256b5-140">Select `Shift`+`Esc` or navigate to the Microsoft Edge main menu and choose **More tools** > **Browser Task Manager** to open the Microsoft Edge Browser Task Manager.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="ブラウザー タスク Microsoft Edgeを開く" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       <span data-ttu-id="256b5-142">図 1: ブラウザー タスク マネージャー Microsoft Edge開く</span><span class="sxs-lookup"><span data-stu-id="256b5-142">Figure 1:  Opening the Microsoft Edge Browser Task Manager</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="256b5-143">ブラウザー タスク マネージャーのテーブル ヘッダー Microsoft Edgeし、コンテキスト メニュー \(右クリック\) を開き **、JavaScript メモリを有効にします**。</span><span class="sxs-lookup"><span data-stu-id="256b5-143">Hover on the table header of the Microsoft Edge Browser Task Manager, open the contextual menu \(right-click\), and enable **JavaScript memory**.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="JavaScript メモリを有効にする" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       <span data-ttu-id="256b5-145">図 2: JavaScript メモリを有効にする</span><span class="sxs-lookup"><span data-stu-id="256b5-145">Figure 2:  Enable JavaScript memory</span></span>  
    :::image-end:::  
    
<span data-ttu-id="256b5-146">これら 2 つの列は、ページがメモリを使用している方法について異なる点を示します。</span><span class="sxs-lookup"><span data-stu-id="256b5-146">These two columns tell you different things about how your page is using memory.</span></span>  

*   <span data-ttu-id="256b5-147">[ **メモリ] 列** は、ネイティブ メモリを表します。</span><span class="sxs-lookup"><span data-stu-id="256b5-147">The **Memory** column represents native memory.</span></span>  <span data-ttu-id="256b5-148">DOM ノードはネイティブ メモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-148">DOM nodes are stored in native memory.</span></span>  <span data-ttu-id="256b5-149">この値が増えている場合は、DOM ノードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-149">If this value is increasing, DOM nodes are getting created.</span></span>  
*   <span data-ttu-id="256b5-150">**[JavaScript Memory] 列**は、JS ヒープを表します。</span><span class="sxs-lookup"><span data-stu-id="256b5-150">The **JavaScript Memory** column represents the JS heap.</span></span>  <span data-ttu-id="256b5-151">この列には、2 つの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="256b5-151">This column contains two values.</span></span>  <span data-ttu-id="256b5-152">必要な値は、ライブ番号 \(かっこ内の番号\) です。</span><span class="sxs-lookup"><span data-stu-id="256b5-152">The value you are interested in is the live number \(the number in parentheses\).</span></span>  <span data-ttu-id="256b5-153">ライブ番号は、ページ上の到達可能なオブジェクトが使用しているメモリの量を表します。</span><span class="sxs-lookup"><span data-stu-id="256b5-153">The live number represents how much memory the reachable objects on your page are using.</span></span>  <span data-ttu-id="256b5-154">この数が増えている場合は、新しいオブジェクトが作成されているか、既存のオブジェクトが増えています。</span><span class="sxs-lookup"><span data-stu-id="256b5-154">If this number is increasing, either new objects are being created, or the existing objects are growing.</span></span>  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <a name="visualize-memory-leaks-with-performance-panel"></a><span data-ttu-id="256b5-155">[パフォーマンス] パネルでメモリ リークを視覚化する</span><span class="sxs-lookup"><span data-stu-id="256b5-155">Visualize memory leaks with Performance panel</span></span>  

<span data-ttu-id="256b5-156">また、調査の開始点として [パフォーマンス] パネルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="256b5-156">You may also use the Performance panel as another starting point in your investigation.</span></span>  <span data-ttu-id="256b5-157">[パフォーマンス] パネルを使用すると、ページのメモリ使用量を時間の間に視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="256b5-157">The Performance panel helps you visualize the memory use of a page over time.</span></span>  

1.  <span data-ttu-id="256b5-158">DevTools **の [** パフォーマンス] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="256b5-158">Open the **Performance** panel on DevTools.</span></span>  
1.  <span data-ttu-id="256b5-159">[メモリ] **チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="256b5-159">Enable the **Memory** checkbox.</span></span>  
1.  <span data-ttu-id="256b5-160">[録音を行います][DevtoolsEvaluatePerformanceReferenceRecord]。</span><span class="sxs-lookup"><span data-stu-id="256b5-160">[Make a recording][DevtoolsEvaluatePerformanceReferenceRecord].</span></span>  

> [!TIP]
> <span data-ttu-id="256b5-161">強制ガベージ コレクションを使用して記録を開始および終了する方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="256b5-161">It is a good practice to start and end your recording with a forced garbage collection.</span></span>  <span data-ttu-id="256b5-162">ガベージ コレクションを強制するには、記録中に **[ガベージ**フォース ガベージ コレクション ![ の収集] ][ImageForceGarbageCollectionIcon] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="256b5-162">To force garbage collection, choose the **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button while recording.</span></span>  

<span data-ttu-id="256b5-163">メモリ記録のデモンストレーションを行う場合は、以下のコードを検討してください。</span><span class="sxs-lookup"><span data-stu-id="256b5-163">To demonstrate memory recordings, consider the code below:</span></span>  

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

<span data-ttu-id="256b5-164">コードで参照されるボタンが選択されるたび、10,000 ノードがドキュメント本文に追加され、100 万文字の文字列が配列に `div` `x` プッシュ `x` されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-164">Every time that the button referenced in the code is chosen, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array.</span></span>  <span data-ttu-id="256b5-165">前のコード サンプルを実行すると、次の図のように **[パフォーマンス** ] パネルに記録が生成されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-165">Running the previous code sample produces a recording in the **Performance** panel like the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="単純な成長" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   <span data-ttu-id="256b5-167">図 3: 単純な成長</span><span class="sxs-lookup"><span data-stu-id="256b5-167">Figure 3:  Simple growth</span></span>  
:::image-end:::  

<span data-ttu-id="256b5-168">最初に、ユーザー インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="256b5-168">First, an explanation of the user interface.</span></span>  <span data-ttu-id="256b5-169">[**概要]** ウィンドウ\*\*\*\* \(NET \の下) の**HEAP**グラフは、JS ヒープを表します。</span><span class="sxs-lookup"><span data-stu-id="256b5-169">The **HEAP** graph in the **Overview** pane \(below **NET**\) represents the JS heap.</span></span>  <span data-ttu-id="256b5-170">[概要] **ウィンドウの** 下に [カウンター **] ウィンドウ** があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-170">Below the **Overview** pane is the **Counter** pane.</span></span>  <span data-ttu-id="256b5-171">メモリ使用量は、JS ヒープ \(Overview pane\の**HEAP**グラフと同じ)、ドキュメント、DOM ノード、リスナー、GPU メモリによって分解されます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="256b5-171">The memory usage is broken down by JS heap \(same as **HEAP** graph in the **Overview** pane\), documents, DOM nodes, listeners, and GPU memory.</span></span>  <span data-ttu-id="256b5-172">グラフから非表示にするチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="256b5-172">Turn off a checkbox to hide it from the graph.</span></span>  

<span data-ttu-id="256b5-173">次に、前の図と比較したコードの分析を行います。</span><span class="sxs-lookup"><span data-stu-id="256b5-173">Now, an analysis of the code compared with the previous figure.</span></span>  <span data-ttu-id="256b5-174">ノード カウンター \(緑のグラフ\) を確認すると、コードと完全に一致します。</span><span class="sxs-lookup"><span data-stu-id="256b5-174">If you review the node counter \(the green graph\), it matches up cleanly with the code.</span></span>  <span data-ttu-id="256b5-175">ノード数は、個別のステップで増加します。</span><span class="sxs-lookup"><span data-stu-id="256b5-175">The node count increases in discrete steps.</span></span>  <span data-ttu-id="256b5-176">ノード数が増加するごとに呼び出しである可能性があります `grow()` 。</span><span class="sxs-lookup"><span data-stu-id="256b5-176">You may presume that each increase in the node count is a call to `grow()`.</span></span>  <span data-ttu-id="256b5-177">JS ヒープ グラフ \(青いグラフ\) は、単純ではありません。</span><span class="sxs-lookup"><span data-stu-id="256b5-177">The JS heap graph \(the blue graph\) is not as straightforward.</span></span>  <span data-ttu-id="256b5-178">ベスト プラクティスに従って、最初のディップは実際には強制ガベージ コレクション \(ガベージ フォース ガベージ コレクション の収集ボタン\*\*\*\* ![ を選択) ][ImageForceGarbageCollectionIcon] です。</span><span class="sxs-lookup"><span data-stu-id="256b5-178">In keeping with best practices, the first dip is actually a forced garbage collection \(choose the  **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button\).</span></span>  <span data-ttu-id="256b5-179">記録が進むにつれて、JS ヒープ サイズのスパイクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-179">As the recording progresses, the JS heap size spikes are displayed.</span></span>  <span data-ttu-id="256b5-180">これは自然で予想されます。JavaScript コードは、選択したボタンごとに DOM ノードを作成し、100 万文字の文字列を作成するときに多くの作業を行います。</span><span class="sxs-lookup"><span data-stu-id="256b5-180">This is natural and expected:  the JavaScript code is creating the DOM nodes on every button you choose and doing a lot of work when it creates the string of one million characters.</span></span>  <span data-ttu-id="256b5-181">ここでの重要な点は、JS ヒープが開始した \(強制的なガベージ コレクション\の後のポイントである "beginning" ) よりも高く終わるという事実です。</span><span class="sxs-lookup"><span data-stu-id="256b5-181">The key thing here is the fact that the JS heap ends higher than it began \(the "beginning" here being the point after the forced garbage collection\).</span></span>  <span data-ttu-id="256b5-182">実際には、JS ヒープ サイズまたはノード サイズが増加するパターンを見た場合、メモリ リークが定義される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-182">In the real world, if you saw this pattern of increasing JS heap size or node size, it may potentially define a memory leak.</span></span>  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <a name="discover-detached-dom-tree-memory-leaks-with-heap-snapshots"></a><span data-ttu-id="256b5-183">ヒープ スナップショットを使用して、デタッチされた DOM ツリーのメモリ リークを検出する</span><span class="sxs-lookup"><span data-stu-id="256b5-183">Discover detached DOM tree memory leaks with Heap Snapshots</span></span>  

<span data-ttu-id="256b5-184">DOM ノードは、ページ上で実行されている DOM ツリーまたは JavaScript コードからノードへの参照がない場合にのみガベージ コレクションされます。</span><span class="sxs-lookup"><span data-stu-id="256b5-184">A DOM node is only garbage collected when there are no references to the node from either the DOM tree or JavaScript code running on the page.</span></span>  <span data-ttu-id="256b5-185">ノードは DOM ツリーから削除されると"デタッチ" と言いますが、一部の JavaScript は引き続きそれを参照します。</span><span class="sxs-lookup"><span data-stu-id="256b5-185">A node is said to be "detached" when it is removed from the DOM tree but some JavaScript still references it.</span></span>  <span data-ttu-id="256b5-186">デタッチされた DOM ノードは、メモリ リークの一般的な原因です。</span><span class="sxs-lookup"><span data-stu-id="256b5-186">Detached DOM nodes are a common cause of memory leaks.</span></span>  <span data-ttu-id="256b5-187">このセクションでは、DevTools のヒープ プロファイサーを使用して、デタッチされたノードを識別する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="256b5-187">This section teaches you how to use the heap profilers in DevTools to identify detached nodes.</span></span>  

<span data-ttu-id="256b5-188">デタッチされた DOM ノードの簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="256b5-188">Here is a simple example of detached DOM nodes.</span></span>  

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

<span data-ttu-id="256b5-189">コードで参照されるボタンを選択すると、10 人の子 `ul` を持つノードが作成 `li` されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-189">Choosing the button referenced in the code creates a `ul` node with ten `li` children.</span></span>  <span data-ttu-id="256b5-190">ノードはコードによって参照されますが、DOM ツリーには存在しないので、それぞれが切り離されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-190">The nodes are referenced by the code but do not exist in the DOM tree, so each is detached.</span></span>  

<span data-ttu-id="256b5-191">ヒープ スナップショットは、デタッチされたノードを識別する 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="256b5-191">Heap snapshots are one way to identify detached nodes.</span></span>  <span data-ttu-id="256b5-192">名前が示すように、ヒープ スナップショットは、スナップショットの時点でのページの JS オブジェクトと DOM ノード間のメモリの分散方法を示します。</span><span class="sxs-lookup"><span data-stu-id="256b5-192">As the name implies, heap snapshots show you how memory is distributed among the JS objects and DOM nodes for your page at the point of time of the snapshot.</span></span>  

<span data-ttu-id="256b5-193">スナップショットを作成するには、DevTools を開き、[\*\*\*\* メモリ] パネルに\*\*\*\* 移動し、[スナップショットの取得] ボタンの [ヒープ スナップショット] ラジオ >**選択**します。</span><span class="sxs-lookup"><span data-stu-id="256b5-193">To create a snapshot, open DevTools and navigate to the **Memory** panel, choose the **Heap snapshot** radio button > **Take snapshot** button.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="ヒープ スナップショットの取得" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   <span data-ttu-id="256b5-195">図 4: ヒープ スナップショットの取得</span><span class="sxs-lookup"><span data-stu-id="256b5-195">Figure 4:  Take heap snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="256b5-196">スナップショットの処理と読み込みには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-196">The snapshot may take some time to process and load.</span></span>  <span data-ttu-id="256b5-197">完了したら、左側のパネル **\(HEAP SNAPSHOTS**\という名前) から選択します。</span><span class="sxs-lookup"><span data-stu-id="256b5-197">After it is finished, select it from the left-hand panel \(named **HEAP SNAPSHOTS**\).</span></span>  

<span data-ttu-id="256b5-198">[ `Detached` クラス フィルター **] テキスト ボックスに** 入力して、デタッチされた DOM ツリーを検索します。</span><span class="sxs-lookup"><span data-stu-id="256b5-198">Type `Detached` in the **Class filter** textbox to search for detached DOM trees.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="デタッチされたノードのフィルター処理" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   <span data-ttu-id="256b5-200">図 5: デタッチされたノードのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="256b5-200">Figure 5:  Filtering for detached nodes</span></span>  
:::image-end:::  

<span data-ttu-id="256b5-201">カラットを展開して、切り離されたツリーを調査します。</span><span class="sxs-lookup"><span data-stu-id="256b5-201">Expand the carats to investigate a detached tree.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="デタッチされたツリーの調査" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   <span data-ttu-id="256b5-203">図 6: デタッチされたツリーの調査</span><span class="sxs-lookup"><span data-stu-id="256b5-203">Figure 6:  Investigating detached tree</span></span>  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

<span data-ttu-id="256b5-204">さらに調査するノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="256b5-204">Choose a node to investigate it further.</span></span>  <span data-ttu-id="256b5-205">[オブジェクト **] ウィンドウ** で、参照しているコードの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="256b5-205">In the **Objects** pane, you may review more information about the code that is referencing it.</span></span>  <span data-ttu-id="256b5-206">たとえば、次の図では、変数 `detachedNodes` はノードを参照しています。</span><span class="sxs-lookup"><span data-stu-id="256b5-206">For example, in the following figure, the `detachedNodes` variable is referencing the node.</span></span>  <span data-ttu-id="256b5-207">特定のメモリ リークを修正するには、変数を使用するコードを調査し、不要になったときにノードへの参照が削除される `detachedUNode` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-207">To fix the particular memory leak, you should study the code that uses the `detachedUNode` variable and ensure that the reference to the node is removed when it is no longer needed.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="ノードの調査" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   <span data-ttu-id="256b5-209">図 7: ノードの調査</span><span class="sxs-lookup"><span data-stu-id="256b5-209">Figure 7:  Investigating a node</span></span>  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <a name="identify-js-heap-memory-leaks-with-allocation-instrumentation-on-timeline"></a><span data-ttu-id="256b5-210">タイムライン上の Allocation インストルメンテーションを使用して JS ヒープ メモリ リークを特定する</span><span class="sxs-lookup"><span data-stu-id="256b5-210">Identify JS heap memory leaks with Allocation instrumentation on timeline</span></span>  

<span data-ttu-id="256b5-211">**タイムライン上の割り当て** インストルメンテーションは、JS ヒープ内のメモリ リークを追跡するのに役立つもう 1 つのツールです。</span><span class="sxs-lookup"><span data-stu-id="256b5-211">**Allocation instrumentation on timeline** is another tool that may help you track down memory leaks in your JS heap.</span></span>  

<span data-ttu-id="256b5-212">次の **コードを使用して、タイムラインで割**  り当てインストルメンテーションを示します。</span><span class="sxs-lookup"><span data-stu-id="256b5-212">Demonstrate **Allocation instrumentation on timeline**  using the following code.</span></span>  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="256b5-213">コードで参照されるボタンがプッシュされるごとに、配列に 100 万文字の文字列が追加 `x` されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-213">Every time that the button referenced in the code is pushed, a string of one million characters is added to the `x` array.</span></span>  

<span data-ttu-id="256b5-214">割り当てインストルメンテーションをタイムラインに記録するには、DevTools を開き、[メモリ] パネルに移動し\*\*\*\*、[タイムライン上の割り当てインストルメンテーション] ラジオ ボタンを選択\*\*\*\* し、[スタート] ボタンを選択し、メモリ リークの原因と思われるアクションを実行し、完了したら [記録ヒープ プロファイルの記録を停止する] ボタンを選択します。 \*\*\*\* \*\*\*\* ![ ][ImageStopRecordingIcon]</span><span class="sxs-lookup"><span data-stu-id="256b5-214">To record an Allocation instrumentation on timeline, open DevTools, navigate to the **Memory** panel, choose the **Allocation instrumentation on timeline** radio button, choose the **Start** button, perform the action that you suspect is causing the memory leak, and then choose the **Stop recording heap profile** ![stop recording][ImageStopRecordingIcon] button when you are done.</span></span>  

<span data-ttu-id="256b5-215">記録中に、次の図のように、タイムラインの Allocation インストルメンテーションに青いバーが表示される場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="256b5-215">As you are recording, notice if any blue bars show up on the Allocation instrumentation on timeline, like in the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="新しい割り当て" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   <span data-ttu-id="256b5-217">図 8: 新しい割り当て</span><span class="sxs-lookup"><span data-stu-id="256b5-217">Figure 8:  New allocations</span></span>  
:::image-end:::  

<span data-ttu-id="256b5-218">これらの青いバーは、新しいメモリ割り当てを表します。</span><span class="sxs-lookup"><span data-stu-id="256b5-218">Those blue bars represent new memory allocations.</span></span>  <span data-ttu-id="256b5-219">これらの新しいメモリ割り当ては、メモリ リークの候補です。</span><span class="sxs-lookup"><span data-stu-id="256b5-219">Those new memory allocations are your candidates for memory leaks.</span></span>  <span data-ttu-id="256b5-220">バーを拡大してコンストラクター ウィンドウをフィルター処理して\*\*\*\*、指定した期間に割り当てられたオブジェクトのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="256b5-220">You are able to zoom on a bar to filter the **Constructor** pane to only show objects that were allocated during the specified timeframe.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="拡大された割り当てタイムライン" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   <span data-ttu-id="256b5-222">図 9: 拡大割り当てのタイムライン</span><span class="sxs-lookup"><span data-stu-id="256b5-222">Figure 9:  Zoomed allocation timeline</span></span>  
:::image-end:::  

<span data-ttu-id="256b5-223">オブジェクトを展開し、値を選択して、[オブジェクト] ウィンドウに詳細を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="256b5-223">Expand the object and select the value to view more details in the **Object** pane.</span></span>  <span data-ttu-id="256b5-224">たとえば、次の図では、新しく割り当てられたオブジェクトの詳細で、スコープ内の変数に割り当 `x` てられたかどうかを示 `Window` します。</span><span class="sxs-lookup"><span data-stu-id="256b5-224">For example, in the following figure, in the details of the newly allocated object indicates that it was allocated to the `x` variable in the `Window` scope.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="オブジェクトの詳細" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   <span data-ttu-id="256b5-226">図 10: オブジェクトの詳細</span><span class="sxs-lookup"><span data-stu-id="256b5-226">Figure 10:  Object details</span></span>  
:::image-end:::  

## <a name="investigate-memory-allocation-by-function"></a><span data-ttu-id="256b5-227">関数別にメモリ割り当てを調査する</span><span class="sxs-lookup"><span data-stu-id="256b5-227">Investigate memory allocation by function</span></span>  

<span data-ttu-id="256b5-228">割り **当てサンプリング プロファイル** の種類を使用して、JavaScript 関数によるメモリ割り当てを表示します。</span><span class="sxs-lookup"><span data-stu-id="256b5-228">Use the **Allocation sampling** profiling type to view memory allocation by JavaScript function.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="レコードの割り当てサンプリング" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   <span data-ttu-id="256b5-230">図 11: レコード割り当てサンプリング</span><span class="sxs-lookup"><span data-stu-id="256b5-230">Figure 11:  Record Allocation sampling</span></span>  
:::image-end:::  

1.  <span data-ttu-id="256b5-231">[割り当 **てサンプリング] ラジオ ボタン** を選択します。</span><span class="sxs-lookup"><span data-stu-id="256b5-231">Choose the **Allocation sampling** radio button.</span></span>  <span data-ttu-id="256b5-232">ページにワーカーが表示されている場合は、[スタート] ボタンの横にあるドロップダウン メニューを使用して、プロファイル **ターゲットとして選択** できます。</span><span class="sxs-lookup"><span data-stu-id="256b5-232">If there is a worker on the page, you are able to select that as the profiling target using the dropdown menu next to the **Start** button.</span></span>  
1.  <span data-ttu-id="256b5-233">[スタート] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="256b5-233">Choose the **Start** button.</span></span>  
1.  <span data-ttu-id="256b5-234">調査する Web ページのアクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="256b5-234">Complete the actions on the webpage which you want to investigate.</span></span>  
1.  <span data-ttu-id="256b5-235">すべての操作 **が完了** したら、[停止] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="256b5-235">Choose the **Stop** button when you have finished all of your actions.</span></span>  

<span data-ttu-id="256b5-236">DevTools は、関数別のメモリ割り当ての内訳を示します。</span><span class="sxs-lookup"><span data-stu-id="256b5-236">DevTools shows you a breakdown of memory allocation by function.</span></span>  <span data-ttu-id="256b5-237">既定のビューは **Heavy (Bottom Up)** で、最もメモリが割り当てられた関数が上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-237">The default view is **Heavy (Bottom Up)**, which displays the functions that allocated the most memory at the top.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="割り当てサンプリング" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   <span data-ttu-id="256b5-239">図 12: 割り当てサンプリング</span><span class="sxs-lookup"><span data-stu-id="256b5-239">Figure 12:  Allocation sampling</span></span>  
:::image-end:::  

## <a name="spot-frequent-garbage-collections"></a><span data-ttu-id="256b5-240">頻繁なガベージ コレクションを見つける</span><span class="sxs-lookup"><span data-stu-id="256b5-240">Spot frequent garbage collections</span></span>  

<span data-ttu-id="256b5-241">ページが頻繁に一時停止する場合は、ガベージ コレクションの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-241">If your page appears to pause frequently, then you may have garbage collection issues.</span></span>  

<span data-ttu-id="256b5-242">ブラウザー タスク マネージャーまたはパフォーマンス メモリMicrosoft Edgeを使用して、頻繁なガベージ コレクションを見つける方法があります。</span><span class="sxs-lookup"><span data-stu-id="256b5-242">You are able to use either the Microsoft Edge Browser Task Manager or Performance memory recordings to spot frequent garbage collection.</span></span>  <span data-ttu-id="256b5-243">ブラウザー タスク Microsoft Edgeでは、頻繁にメモリまたは**JavaScript** \*\*\*\* メモリの値が上昇および低下し、ガベージ コレクションが頻繁に発生します。</span><span class="sxs-lookup"><span data-stu-id="256b5-243">In the Microsoft Edge Browser Task Manager, frequently rising and falling **Memory** or **JavaScript Memory** values represent frequent garbage collection.</span></span>  <span data-ttu-id="256b5-244">パフォーマンスの記録では、JS ヒープまたはノード 数グラフへの頻繁な変更 \(立ち上がりおよび立ち下がり\) は、頻繁なガベージ コレクションを示します。</span><span class="sxs-lookup"><span data-stu-id="256b5-244">In Performance recordings, frequent changes \(rising and falling\) to the JS heap or node count graphs indicate frequent garbage collection.</span></span>  

<span data-ttu-id="256b5-245">問題を特定した後、タイムラインの記録で Allocation イン\*\*\*\* ストルメンテーションを使用して、メモリが割り当てられている場所と割り当てを引き起こしている関数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="256b5-245">After you have identified the problem, you are able to use an **Allocation instrumentation on timeline** recording to find out where memory is being allocated and which functions are causing the allocations.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="256b5-246">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="256b5-246">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "レコードのパフォーマンス - パフォーマンス分析リファレンス"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> <span data-ttu-id="256b5-248">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="256b5-248">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="256b5-249">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="256b5-249">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="256b5-251">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="256b5-251">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
