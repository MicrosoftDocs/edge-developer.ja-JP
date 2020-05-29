---
description: メモリパネルを使用して、
title: DevTools-Memory
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、memory、heap、GC、ガベージコレクション、保持サイズ、dominators
ms.custom: seodec18
ms.openlocfilehash: 416ba144f7e22bd50f5d2a3437bc21d9d31a9035
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569677"
---
# <span data-ttu-id="3c52e-104">メモリ</span><span class="sxs-lookup"><span data-stu-id="3c52e-104">Memory</span></span>

<span data-ttu-id="3c52e-105">**メモリ**パネルを使用して、システムリソースの使用を測定したり、コード実行のさまざまな状態でヒープスナップショットを比較したりします。</span><span class="sxs-lookup"><span data-stu-id="3c52e-105">Use the **Memory** panel to measure your use of system resources and compare heap snapshots at different states of code execution.</span></span> <span data-ttu-id="3c52e-106">これにより、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="3c52e-106">With it, you can:</span></span>

- <span data-ttu-id="3c52e-107">[ページのメモリ消費量をリアルタイムでグラフ](#memory-usage-timeline)化し、ヒープのスナップショットを取る</span><span class="sxs-lookup"><span data-stu-id="3c52e-107">[Graph the memory consumption of your page in real time](#memory-usage-timeline) and take snapshots of the heap</span></span>
- <span data-ttu-id="3c52e-108">DOM にアタッチされていない保持オブジェクトなど、コードで発生する[可能性のあるメモリの問題を特定](#snapshot-summary)する</span><span class="sxs-lookup"><span data-stu-id="3c52e-108">[Identify potential memory issues](#snapshot-summary) in your code, such as retained objects not attached to the DOM</span></span>
- <span data-ttu-id="3c52e-109">問題を特定するためのオブジェクトの種類、インスタンス数、サイズ、参照によって[メモリ使用量データを確認](#snapshot-details)する</span><span class="sxs-lookup"><span data-stu-id="3c52e-109">[Review memory usage data](#snapshot-details) by object type, instance count, size, and references to help isolate issues</span></span>
- <span data-ttu-id="3c52e-110">[スナップショットデータフィルターを適用](#filters)して、非実用的な情報のノイズを軽減する</span><span class="sxs-lookup"><span data-stu-id="3c52e-110">[Apply snapshot data filters](#filters) to reduce the noise of non-actionable information</span></span>
- <span data-ttu-id="3c52e-111">[特定のオブジェクトのメモリコスト](#object-references)とそれを維持している参照を特定する</span><span class="sxs-lookup"><span data-stu-id="3c52e-111">[Identify the memory cost of a specific object](#object-references) and the references keeping it alive</span></span>
- <span data-ttu-id="3c52e-112">メモリリークおよびその他の問題のソースを追跡するために、[調査のさまざまなフェーズでヒープを比較します](#snapshot-comparison)。</span><span class="sxs-lookup"><span data-stu-id="3c52e-112">[Diff the heap at different phases of your investigation](#snapshot-comparison) to track down the source of memory leaks and other problems</span></span>

![Microsoft Edge DevTools の [メモリ] パネル](./media/memory.png)


## <span data-ttu-id="3c52e-114">ツール バー</span><span class="sxs-lookup"><span data-stu-id="3c52e-114">Toolbar</span></span>

1. <span data-ttu-id="3c52e-115">**プロファイリングセッションの開始/停止 (Ctrl + E)**: プロファイラーを有効にすると、メモリ使用量を追跡してヒープのスナップショットを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-115">**Start/Stop profiling session (Ctrl+E)**: Turning on the profiler enables you to track memory usage and take snapshots of the heap.</span></span>
2. <span data-ttu-id="3c52e-116">**プロファイルセッションのインポート (Ctrl + O)**: 保存されている devtools メモリ診断セッションを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-116">**Import profiling session (Ctrl+O)**: Load a saved  DevTools memory diagnostic session.</span></span>
3. <span data-ttu-id="3c52e-117">**プロファイルセッションのエクスポート (Ctrl + S)**: 現在の診断セッションをディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-117">**Export profiling session (Ctrl+S)**: Save the current diagnostic session to disk.</span></span>
4. <span data-ttu-id="3c52e-118">**ヒープスナップショットの取得 (Ctrl + Shift + T)**: 指定された時点で現在のメモリ割り当てを記録します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-118">**Take heap snapshot (Ctrl+Shift+T)**: Record current memory allocations for a given point of time.</span></span>


## <span data-ttu-id="3c52e-119">メモリ使用量のタイムライン</span><span class="sxs-lookup"><span data-stu-id="3c52e-119">Memory usage timeline</span></span>

<span data-ttu-id="3c52e-120">メモリの問題は、パフォーマンスの問題の主な原因となる可能性があり、その結果、ページの応答が laggy、時間の経過と共に変化します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-120">Memory problems can be a major culprit of performance issues, causing your page to become increasingly unresponsive and laggy over time.</span></span>

<span data-ttu-id="3c52e-121">ページのメモリ使用量を分析するための最初の手順は、メモリを大量に消費したり、メモリリークが発生したりする可能性がある手順を再現するために、[プロファイルセッションを開始](#toolbar)して、ヒープのスナップショットを作成することです。</span><span class="sxs-lookup"><span data-stu-id="3c52e-121">The first step to analyzing the memory usage of your page is to [start a profiling session](#toolbar) in order to take before/after snapshots of the heap as you repro the steps causing memory bloat or a suspected memory leak.</span></span>

<span data-ttu-id="3c52e-122">メモリプロファイラーを起動すると、プロセスメモリグラフが表示され、時間の経過に伴う全体的なプライベートワーキングセット (ページによって消費されるメモリの量) を監視できます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-122">When you start the memory profiler, you will see a process memory graph that allows you to observe the overall private working set (the amount of memory consumed by the page) over time.</span></span> <span data-ttu-id="3c52e-123">メモリグラフには、プライベートバイト、ネイティブメモリ、JavaScript ヒープなど、タブのプロセスメモリのライブビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-123">The memory graph shows you a live view of the tab's process memory, which includes private bytes, native memory, and the JavaScript heap.</span></span> 

![メモリ使用量のタイムライン](./media/memory_timeline.png)

 <span data-ttu-id="3c52e-125">グラフでは、予期しないメモリ保持期間が表示された場合など、[ヒープスナップショットの取得](#toolbar)が適切かどうかを判断できるように、ページのメモリの傾向を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-125">The graph gives you an indication of the memory trend for the page which enables you to judge when it is appropriate to [take a heap snapshot](#toolbar) for later comparison, such as when you see periods of unexpected memory retention.</span></span>

### <span data-ttu-id="3c52e-126">Performance. マーク ()</span><span class="sxs-lookup"><span data-stu-id="3c52e-126">Performance.mark()</span></span>

<span data-ttu-id="3c52e-127">**User marks** [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) コードまたは devtools[**本体**](./console.md)からメソッドを呼び出すことによって、分析セッション中にキーイベントを識別しやすいように、カスタムユーザーマークをタイムラインに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-127">You can add custom **User marks** to the timeline to help identify  key events during the course of your analysis session by calling the [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span>

### <span data-ttu-id="3c52e-128">本体の Heapheapsnapshot ()</span><span class="sxs-lookup"><span data-stu-id="3c52e-128">Console.takeheapSnapshot()</span></span>

<span data-ttu-id="3c52e-129">場合によっては、DOM の大きな変異の直前など、特定の時点でスナップショットを作成することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c52e-129">Sometimes you need to take snapshots at very specific points in time, such as immediately before a large mutation of the DOM.</span></span> <span data-ttu-id="3c52e-130">このような場合は、を使用して、プログラムでスナップショットを取得でき [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots) ます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-130">In these cases,you can take snapshots programmatically with [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots).</span></span>

## <span data-ttu-id="3c52e-131">スナップショットの概要</span><span class="sxs-lookup"><span data-stu-id="3c52e-131">Snapshot summary</span></span>

<span data-ttu-id="3c52e-132">[スナップショットを撮る](#toolbar)と、スナップショットが取得された時点の JavaScript ヒープのサイズと、ページの割り当てられたオブジェクトの数と共に、概要タイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-132">[Taking a snapshot](#toolbar) will generate a summary tile that indicates the size of the JavaScript heap at the time the snapshot was taken, along with the number of objects allocated and a screenshot of the page.</span></span> <span data-ttu-id="3c52e-133">分析が必要なユーザーシナリオでは、いつでもスナップショットを撮ることができます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-133">You can continue to take snapshots at any time as you run through the user scenario requiring analysis.</span></span> <span data-ttu-id="3c52e-134">スナップショットは追加のタイルを生成します。各タイルは、前のスナップショットからの JavaScript メモリの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c52e-134">The snapshots generate additional tiles, each of which indicates the difference in JavaScript memory from the previous snapshot.</span></span>

![ヒープスナップショット](./media/memory_snapshot.png)

<span data-ttu-id="3c52e-136">[サマリー] タイルの値をクリックすると、[スナップショットデータの詳細](#snapshot-details)が表示されているウィンドウに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="3c52e-136">Clicking on the values in the summary tile will switch to the pane showing [details of the snapshot data](#snapshot-details).</span></span> <span data-ttu-id="3c52e-137">潜在的な[メモリの問題は](#snapshot-details)、青色の情報 ("i") アイコンで示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-137">Potential [memory issues are indicated](#snapshot-details) with a blue informational ("i") icon.</span></span>

## <span data-ttu-id="3c52e-138">スナップショットの詳細</span><span class="sxs-lookup"><span data-stu-id="3c52e-138">Snapshot details</span></span>

<span data-ttu-id="3c52e-139">[*スナップショット*] ウィンドウのデータには、ページによって作成されたオブジェクトと、JavaScript フレームワークによって割り当てられたメモリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-139">The data in the *Snapshot* pane shows the objects created by your page along with any memory allocated by JavaScript frameworks you may be consuming.</span></span>

![スナップショットの詳細テーブル](./media/memory_details.png)

<span data-ttu-id="3c52e-141">3つのタブは、データのさまざまなビューを表します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-141">The three tabs represent different views of the data:</span></span>

#### <span data-ttu-id="3c52e-142">型</span><span class="sxs-lookup"><span data-stu-id="3c52e-142">Types</span></span>

<span data-ttu-id="3c52e-143">オブジェクトの種類別にグループ化された、ヒープ上のオブジェクトの数と合計サイズが示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-143">Shows the instance count and total size of objects on the heap, grouped by object type.</span></span> <span data-ttu-id="3c52e-144">既定では、これらはインスタンス数によって並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-144">By default, these are sorted by instance count.</span></span>

<span data-ttu-id="3c52e-145">[上の*型*] ウィンドウでオブジェクトを選ぶと、下側のウィンドウの[オブジェクト参照](#object-references)テーブルに、そのオブジェクトを指し示すすべてのオブジェクトが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-145">When you select an object in the upper *Types* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

#### <span data-ttu-id="3c52e-146">起源</span><span class="sxs-lookup"><span data-stu-id="3c52e-146">Roots</span></span>

<span data-ttu-id="3c52e-147">子参照の階層ビューを示して、オブジェクトがグローバルオブジェクトにどのようにルートされるかを説明し、ガベージコレクションされないようにします。</span><span class="sxs-lookup"><span data-stu-id="3c52e-147">Shows a hierarchical view of child references to describe how objects are rooted to the global object, thus preventing them from being garbage-collected.</span></span>

<span data-ttu-id="3c52e-148">既定では、子ノードは [保持サイズ] 列によって並べ替えられ、最大値は先頭になります。</span><span class="sxs-lookup"><span data-stu-id="3c52e-148">By default, the child nodes are sorted by the retained size column, with the largest at the top.</span></span>

#### <span data-ttu-id="3c52e-149">Dominators</span><span class="sxs-lookup"><span data-stu-id="3c52e-149">Dominators</span></span>

<span data-ttu-id="3c52e-150">他のオブジェクトを排他的に参照するヒープ上のオブジェクトの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-150">Shows a list of objects on the heap that have exclusive references to other objects.</span></span> <span data-ttu-id="3c52e-151">Dominators は保持サイズによって並べ替えられ、オブジェクトが最も簡単に利用できるメモリを大量に消費していることを示します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-151">Dominators are sorted by retained size to indicate the objects consuming the most memory that are potentially easiest to free.</span></span>

<span data-ttu-id="3c52e-152">ここでは、 *Types、root* 、 *Dominators*の各ビューの列を解釈する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-152">Here's how to interpret the columns in the *Types, Roots* and *Dominators* views:</span></span>

<span data-ttu-id="3c52e-153">列</span><span class="sxs-lookup"><span data-stu-id="3c52e-153">Column</span></span> | <span data-ttu-id="3c52e-154">説明</span><span class="sxs-lookup"><span data-stu-id="3c52e-154">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3c52e-155">識別子</span><span class="sxs-lookup"><span data-stu-id="3c52e-155">Identifier(s)</span></span> | <span data-ttu-id="3c52e-156">オブジェクトを最適に識別する名前。</span><span class="sxs-lookup"><span data-stu-id="3c52e-156">Name that best identifies the object.</span></span> <span data-ttu-id="3c52e-157">たとえば、HTML 要素の場合、スナップショットの詳細には ID 属性値が表示されます (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="3c52e-157">For example, for HTML elements the snapshot details show the ID attribute value, if one is used.</span></span>
<span data-ttu-id="3c52e-158">種類</span><span class="sxs-lookup"><span data-stu-id="3c52e-158">Type</span></span> | <span data-ttu-id="3c52e-159">オブジェクトの種類 (たとえば、 *HTMLDivElement*)。</span><span class="sxs-lookup"><span data-stu-id="3c52e-159">Object type (for example, *HTMLDivElement*).</span></span>
<span data-ttu-id="3c52e-160">Size</span><span class="sxs-lookup"><span data-stu-id="3c52e-160">Size</span></span> | <span data-ttu-id="3c52e-161">オブジェクトのサイズ。参照されているオブジェクトのサイズは含まれません。</span><span class="sxs-lookup"><span data-stu-id="3c52e-161">Object size, not including the size of any referenced objects.</span></span>
<span data-ttu-id="3c52e-162">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="3c52e-162">Retained size</span></span> | <span data-ttu-id="3c52e-163">オブジェクトサイズと、他の親がないすべての子オブジェクトのサイズ。</span><span class="sxs-lookup"><span data-stu-id="3c52e-163">Object size plus the size of all child objects that have no other parents.</span></span> <span data-ttu-id="3c52e-164">実際には、このオブジェクトによって保持されているメモリの量であるため、オブジェクトを削除した場合は、指定したメモリ量が解放されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-164">For practical purposes, this is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>
<span data-ttu-id="3c52e-165">Count</span><span class="sxs-lookup"><span data-stu-id="3c52e-165">Count</span></span> | <span data-ttu-id="3c52e-166">オブジェクトインスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="3c52e-166">Number of object instances.</span></span> <span data-ttu-id="3c52e-167">この値は、[タイプビューでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-167">This value appears only in the Types view.</span></span>

<span data-ttu-id="3c52e-168">上の*Dominators*ウィンドウでオブジェクトを選ぶと、下側のウィンドウの [[オブジェクト参照](#object-references)] テーブルに、そのオブジェクトをポイントしているすべてのオブジェクトが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-168">When you select an object in the upper *Dominators* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

### <span data-ttu-id="3c52e-169">フィルター</span><span class="sxs-lookup"><span data-stu-id="3c52e-169">Filters</span></span>

<span data-ttu-id="3c52e-170">表のデータをさらに調整するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3c52e-170">You can further adjust data in the table with the following:</span></span>

![組み込みのアドインとオブジェクト Id をフィルター処理する](./media/memory_filter.png)

1. <span data-ttu-id="3c52e-172">**識別子フィルター**: 特定のオブジェクト識別子を検索してデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="3c52e-172">**Identifier filter**: Filter out data by searching for a particular object identifier</span></span>
2. <span data-ttu-id="3c52e-173">**グループ化 dominator**: オブジェクトの最上位のビューには、他のオブジェクトへの*排他*参照を持つオブジェクトのみが表示されます (これは [ *Dominators* ] タブの既定のビューです)。</span><span class="sxs-lookup"><span data-stu-id="3c52e-173">**Group by dominator**: Only objects with *exclusive* references to other objects are shown in the top-level view of objects (this is the default view in the *Dominators* tab).</span></span>
3. <span data-ttu-id="3c52e-174">**組み込みのフィルター**: 既定では、JavaScript の[組み込みオブジェクト](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects)がリストに含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c52e-174">**Built-ins / IDs filter**: By default, [JavaScript built-in objects](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) are included in the list.</span></span> <span data-ttu-id="3c52e-175">オブジェクト Id の一覧表示は、複数の匿名オブジェクトを区別する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="3c52e-175">Listing object IDs can be useful if there are multiple anonymous objects which need to be differentiated.</span></span>

<span data-ttu-id="3c52e-176">*種類、ルート*、 *Dominators*の各ビューにはそれぞれ専用のフィルターがあります。そのため、別のビューに切り替えると、フィルターは保持されません。</span><span class="sxs-lookup"><span data-stu-id="3c52e-176">The *Types, Roots* and *Dominators* views each has its own filter, so the filter isn't preserved when you switch to another view.</span></span>

### <span data-ttu-id="3c52e-177">オブジェクト参照</span><span class="sxs-lookup"><span data-stu-id="3c52e-177">Object references</span></span>

<span data-ttu-id="3c52e-178">[**Types**](#types)ビューと[**Dominators**](#dominators)ビューでは、下部ウィンドウには共有参照を表示する**オブジェクト参照**リストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c52e-178">In the [**Types**](#types) and [**Dominators**](#dominators) views, the lower pane contains an **Object references** list that displays shared references.</span></span> <span data-ttu-id="3c52e-179">上のウィンドウでオブジェクトを選ぶと、そのオブジェクトをポイントしているすべてのオブジェクトが表示されます。つまり、選択したオブジェクトをアクティブな状態に維持しているオブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-179">When you choose an object in the upper pane, this list displays all objects that point to that object--in other words, the objects that are keeping the selected object alive.</span></span>

<span data-ttu-id="3c52e-180">循環参照には、アスタリスク (\*) と情報のヒントが表示され、展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c52e-180">Circular references are shown with an asterisk (\*) and informational tooltip, and cannot be expanded.</span></span> <span data-ttu-id="3c52e-181">そうしないと、参照ツリーをウォークしたり、メモリを保持しているオブジェクトを識別したりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="3c52e-181">Otherwise, they would prevent you from walking up the reference tree and identifying objects that are retaining memory.</span></span>

<span data-ttu-id="3c52e-182">同等のオブジェクトをすばやく識別するには、[ *id* ] 列でオブジェクト名の横にオブジェクト id を表示するには、[[*オブジェクト id の表示*](#filters)] フィルターオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3c52e-182">To quickly identify equivalent objects, tick the [*Display object IDs*](#filters) filter option to display object IDs next to object names in the *Identifier(s)* column.</span></span> <span data-ttu-id="3c52e-183">同じ ID を持つオブジェクトは共有参照です。</span><span class="sxs-lookup"><span data-stu-id="3c52e-183">Objects that have the same ID are shared references.</span></span>

### <span data-ttu-id="3c52e-184">スナップショットの比較</span><span class="sxs-lookup"><span data-stu-id="3c52e-184">Snapshot comparison</span></span>

<span data-ttu-id="3c52e-185">[[スナップショットの概要] タイル](#snapshot-summary)の [スナップショットの[比較] タブ](#snapshot-details)または [比較] リンクをクリックすると、2つのスナップショット間の情報の相違が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-185">Clicking on a [snapshot comparison tab](#snapshot-details) or comparison link on the [snapshot summary tile](#snapshot-summary)  will show a diff of information between the two snapshots.</span></span> <span data-ttu-id="3c52e-186">[比較] ウィンドウで、 *Dominators、Types* 、および*root*の各ビューには、1つのスナップショットに対して表示されるのと同じ[*スナップショットの詳細*](#snapshot-details)が用意されています。次のような追加の値があります。</span><span class="sxs-lookup"><span data-stu-id="3c52e-186">In the comparison pane, the *Dominators, Types* and *Roots* views provide the same [*snapshot details*](#snapshot-details) you would see for a single snapshots, with these additional values:</span></span>

<span data-ttu-id="3c52e-187">列</span><span class="sxs-lookup"><span data-stu-id="3c52e-187">Column</span></span> | <span data-ttu-id="3c52e-188">説明</span><span class="sxs-lookup"><span data-stu-id="3c52e-188">Description</span></span>
:------------ | :-------------
<span data-ttu-id="3c52e-189">サイズの相違。</span><span class="sxs-lookup"><span data-stu-id="3c52e-189">Size diff.</span></span> | <span data-ttu-id="3c52e-190">現在のスナップショット内のオブジェクトのサイズと前のスナップショットのサイズの違い。参照先のオブジェクトのサイズは含まれません。</span><span class="sxs-lookup"><span data-stu-id="3c52e-190">Difference between the size of the object in the current snapshot and its size in the previous snapshot, not including the size of any referenced objects.</span></span>
<span data-ttu-id="3c52e-191">保持されているサイズの差分。</span><span class="sxs-lookup"><span data-stu-id="3c52e-191">Retained size diff.</span></span> | <span data-ttu-id="3c52e-192">現在のスナップショット内のオブジェクトの保持サイズと、以前のスナップショットで保持されているサイズの差。</span><span class="sxs-lookup"><span data-stu-id="3c52e-192">Difference between the retained size of the object in the current snapshot and its retained size in the previous snapshot.</span></span> <span data-ttu-id="3c52e-193">保持されるサイズには、オブジェクトサイズと、他の親を持たないすべての子オブジェクトのサイズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-193">The retained size includes the object size plus the size of all its child objects that have no other parents.</span></span> <span data-ttu-id="3c52e-194">実際には、保持されるサイズは、オブジェクトによって保持されているメモリの量であるため、オブジェクトを削除した場合、指定したメモリ量が解放されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-194">For practical purposes, the retained size is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>

<span data-ttu-id="3c52e-195">**スコープ**ドロップダウンを使用して、スナップショット間の差分情報をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-195">You can use the **Scope** dropdown to filter differential info between snapshots:</span></span>

![スナップショット comparisions のスコーピング filter](./media/memory_comparison_scope_filter.png)

- <strong><span data-ttu-id="3c52e-197">[Snapshot から] に残ったオブジェクト <number></strong> : ヒープに追加されたオブジェクトと、ベースラインスナップショットから以前のスナップショットへのヒープから削除されたオブジェクトの相違点を示します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-197">Objects left over from Snapshot #<number></strong>: Shows the diff between the objects added to the heap and removed from the heap from the baseline snapshot to the previous snapshot.</span></span> <span data-ttu-id="3c52e-198">たとえば、[スナップショットの概要] が [ <em> オブジェクト数] に + 205/-195 と表示されている場合、 </em> このフィルターでは、追加したが削除されていない10個のオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-198">For example, if the snapshot summary shows <em>+205 / -195</em> in the object count, this filter will show you the ten objects that were added but not removed.</span></span>

- <strong><span data-ttu-id="3c52e-199">Snapshot # と #: の間に追加されたオブジェクト <number> <number></strong> は、前のスナップショットからヒープに追加されたすべてのオブジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c52e-199">Objects added between Snapshot #<number> and #<number></strong>: Shows all objects added to the heap from the previous snapshot.</span></span>

- <strong><span data-ttu-id="3c52e-200">Snapshot のすべてのオブジェクト <number></strong> : ヒープ上のすべてのオブジェクトを表示します (つまり、フィルター処理さ <em> </em> れていないビュー)。</span><span class="sxs-lookup"><span data-stu-id="3c52e-200">All objects in Snapshot #<number></strong>: Shows all objects on the heap (in other words, an <em>unfiltered</em> view).</span></span>

<span data-ttu-id="3c52e-201">既定では、[*一致しない参照を表示する]* フィルターが比較ビューに適用され、現在のスコープフィルターに一致しないオブジェクト参照が示されます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-201">By default, the *Show non-matching references* filter is applied to the comparison view to indicate object references that don't match the current Scope filter.</span></span> <span data-ttu-id="3c52e-202">この機能は、ドロップダウンメニューからオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-202">You can turn it off from the dropdown menu:</span></span>

![スナップショット比較の一致しない参照フィルター](./media/memory_comparison_matching_filter.png)


## <span data-ttu-id="3c52e-204">ショートカット</span><span class="sxs-lookup"><span data-stu-id="3c52e-204">Shortcuts</span></span>

 <span data-ttu-id="3c52e-205">操作</span><span class="sxs-lookup"><span data-stu-id="3c52e-205">Action</span></span> | <span data-ttu-id="3c52e-206">キー</span><span class="sxs-lookup"><span data-stu-id="3c52e-206">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="3c52e-207">プロファイリングセッションの開始/停止</span><span class="sxs-lookup"><span data-stu-id="3c52e-207">Start / Stop profiling session</span></span>  | `Ctrl` + `E`
<span data-ttu-id="3c52e-208">プロファイルセッションのインポート</span><span class="sxs-lookup"><span data-stu-id="3c52e-208">Import profiling session</span></span> | `Ctrl` + `O`
<span data-ttu-id="3c52e-209">プロファイリングセッションのエクスポート</span><span class="sxs-lookup"><span data-stu-id="3c52e-209">Export profiling session</span></span> | `Ctrl` + `S`
<span data-ttu-id="3c52e-210">ヒープスナップショットの取得</span><span class="sxs-lookup"><span data-stu-id="3c52e-210">Take heap snapshot</span></span> | `Ctrl` + `Shift` + `T`

## <span data-ttu-id="3c52e-211">既知の問題</span><span class="sxs-lookup"><span data-stu-id="3c52e-211">Known Issues</span></span>

### <span data-ttu-id="3c52e-212">プロファイルセッションの開始中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="3c52e-212">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="3c52e-213">このエラーメッセージが表示される場合: メモリツールで**プロファイリングセッションを開始するときにエラーが発生しまし**た。回避策については、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="3c52e-213">If you see this error message: **An error occurred while starting the profiling session** in the Memory tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="3c52e-214">キーを押し `Windows Key`  +  `R` ます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-214">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="3c52e-215">[実行] ダイアログボックスで、「 **services.msc**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-215">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="3c52e-217">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を探して右クリックします。</span><span class="sxs-lookup"><span data-stu-id="3c52e-217">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="3c52e-219">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="3c52e-219">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="3c52e-221">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、目的のページに移動して、キーを押し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="3c52e-221">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="3c52e-222">これで、プロファイリングを開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3c52e-222">You should now be able to begin profiling.</span></span> 
![既知の問題-4](./media/known_issues_4-memory.PNG)

<span data-ttu-id="3c52e-224">まだ問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="3c52e-224">Still running into problems?</span></span> <span data-ttu-id="3c52e-225">フィードバックの**送信**アイコンを使ってフィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="3c52e-225">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題-5](./media/known_issues_5.PNG)
