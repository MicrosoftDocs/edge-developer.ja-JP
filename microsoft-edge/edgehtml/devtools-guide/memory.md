---
description: メモリ パネルを使用して
title: DevTools - メモリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, メモリ, ヒープ, GC, ガベージ コレクション, 保持されたサイズ, ドミネータ
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5ad284f8072cc296743299ec9c4fb2037f8fd883
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234452"
---
# <span data-ttu-id="bfc2e-104">メモリ</span><span class="sxs-lookup"><span data-stu-id="bfc2e-104">Memory</span></span>

<span data-ttu-id="bfc2e-105">メモリ パネル **を使用** して、システム リソースの使用を測定し、さまざまな状態のコード実行でヒープ スナップショットを比較します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-105">Use the **Memory** panel to measure your use of system resources and compare heap snapshots at different states of code execution.</span></span> <span data-ttu-id="bfc2e-106">この方法を使用すると、次の方法を行います。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-106">With it, you can:</span></span>

- <span data-ttu-id="bfc2e-107">[ページのメモリ消費量をリアルタイムでグラフ化し](#memory-usage-timeline) 、ヒープのスナップショットを取得する</span><span class="sxs-lookup"><span data-stu-id="bfc2e-107">[Graph the memory consumption of your page in real time](#memory-usage-timeline) and take snapshots of the heap</span></span>
- <span data-ttu-id="bfc2e-108">[DOM に接続されていない保持](#snapshot-summary) オブジェクトなど、コード内の潜在的なメモリの問題を特定する</span><span class="sxs-lookup"><span data-stu-id="bfc2e-108">[Identify potential memory issues](#snapshot-summary) in your code, such as retained objects not attached to the DOM</span></span>
- <span data-ttu-id="bfc2e-109">[オブジェクトの種類、インスタンス](#snapshot-details) 数、サイズ、参照別にメモリ使用量データを確認し、問題を特定するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="bfc2e-109">[Review memory usage data](#snapshot-details) by object type, instance count, size, and references to help isolate issues</span></span>
- <span data-ttu-id="bfc2e-110">[スナップショット データ フィルターを適用](#filters) して操作できない情報のノイズを減らす</span><span class="sxs-lookup"><span data-stu-id="bfc2e-110">[Apply snapshot data filters](#filters) to reduce the noise of non-actionable information</span></span>
- <span data-ttu-id="bfc2e-111">[特定のオブジェクトのメモリ コストと](#object-references) 、それを維持する参照を特定する</span><span class="sxs-lookup"><span data-stu-id="bfc2e-111">[Identify the memory cost of a specific object](#object-references) and the references keeping it alive</span></span>
- <span data-ttu-id="bfc2e-112">[調査の異なるフェーズで](#snapshot-comparison) ヒープを比較し、メモリ リークの原因や他の問題を追跡する</span><span class="sxs-lookup"><span data-stu-id="bfc2e-112">[Diff the heap at different phases of your investigation](#snapshot-comparison) to track down the source of memory leaks and other problems</span></span>

![Microsoft Edge DevTools メモリ パネル](./media/memory.png)


## <span data-ttu-id="bfc2e-114">ツール バー</span><span class="sxs-lookup"><span data-stu-id="bfc2e-114">Toolbar</span></span>

1. <span data-ttu-id="bfc2e-115">**プロファイリング セッションの開始/停止 (Ctrl + E)**: プロファイラーを有効にすることで、メモリ使用量を追跡し、ヒープのスナップショットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-115">**Start/Stop profiling session (Ctrl+E)**: Turning on the profiler enables you to track memory usage and take snapshots of the heap.</span></span>
2. <span data-ttu-id="bfc2e-116">**プロファイリング セッションのインポート (Ctrl + O)**: 保存された DevTools メモリ診断セッションを読み込む。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-116">**Import profiling session (Ctrl+O)**: Load a saved  DevTools memory diagnostic session.</span></span>
3. <span data-ttu-id="bfc2e-117">**プロファイリング セッションのエクスポート (Ctrl + S)**: 現在の診断セッションをディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-117">**Export profiling session (Ctrl+S)**: Save the current diagnostic session to disk.</span></span>
4. <span data-ttu-id="bfc2e-118">**ヒープ スナップショットを取得する (Ctrl + Shift + T)**: 特定の時点での現在のメモリ割り当てを記録します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-118">**Take heap snapshot (Ctrl+Shift+T)**: Record current memory allocations for a given point of time.</span></span>


## <span data-ttu-id="bfc2e-119">メモリ使用量のタイムライン</span><span class="sxs-lookup"><span data-stu-id="bfc2e-119">Memory usage timeline</span></span>

<span data-ttu-id="bfc2e-120">メモリの問題は、パフォーマンスの問題の主要な原因となる可能性があります。その結果、ページの応答が低下し、時間の長い時間が続きます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-120">Memory problems can be a major culprit of performance issues, causing your page to become increasingly unresponsive and laggy over time.</span></span>

<span data-ttu-id="bfc2e-121">ページのメモリ使用量を分析する最初の手順は、ヒープの[](#toolbar)スナップショットの前/後にプロファイリング セッションを開始し、メモリが大きかったり、メモリ リークの疑いがあるステップを再生成したりします。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-121">The first step to analyzing the memory usage of your page is to [start a profiling session](#toolbar) in order to take before/after snapshots of the heap as you repro the steps causing memory bloat or a suspected memory leak.</span></span>

<span data-ttu-id="bfc2e-122">メモリ プロファイラーを起動すると、プロセス メモリ グラフが表示されます。これにより、プライベート ワーキング セット全体 (ページによって消費されるメモリの量) を時間の中で確認できます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-122">When you start the memory profiler, you will see a process memory graph that allows you to observe the overall private working set (the amount of memory consumed by the page) over time.</span></span> <span data-ttu-id="bfc2e-123">メモリ グラフには、プライベート バイト、ネイティブ メモリ、JavaScript ヒープを含むタブのプロセス メモリのライブ ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-123">The memory graph shows you a live view of the tab's process memory, which includes private bytes, native memory, and the JavaScript heap.</span></span> 

![メモリ使用量のタイムライン](./media/memory_timeline.png)

 <span data-ttu-id="bfc2e-125">グラフには、ページのメモリ傾向が示されます。これにより、予期しないメモリ保持期間が発生した場合など[](#toolbar)、後で比較するためにヒープ スナップショットを取得する適切な時期を判断できます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-125">The graph gives you an indication of the memory trend for the page which enables you to judge when it is appropriate to [take a heap snapshot](#toolbar) for later comparison, such as when you see periods of unexpected memory retention.</span></span>

### <span data-ttu-id="bfc2e-126">Performance.mark()</span><span class="sxs-lookup"><span data-stu-id="bfc2e-126">Performance.mark()</span></span>

<span data-ttu-id="bfc2e-127">コードまたは DevTools コンソールからメソッドを呼び出すことによって、分析セッションの過程で重要なイベントを識別するのに役立つカスタム ユーザー マークをタイムラインに [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) 追加[**できます**](./console.md)。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-127">You can add custom **User marks** to the timeline to help identify  key events during the course of your analysis session by calling the [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span>

### <span data-ttu-id="bfc2e-128">Console.takeheapSnapshot()</span><span class="sxs-lookup"><span data-stu-id="bfc2e-128">Console.takeheapSnapshot()</span></span>

<span data-ttu-id="bfc2e-129">DOM の大規模な解析の直前など、非常に特定の時点でスナップショットを取得する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-129">Sometimes you need to take snapshots at very specific points in time, such as immediately before a large mutation of the DOM.</span></span> <span data-ttu-id="bfc2e-130">このような場合は、プログラムでスナップショットを取得できます [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots) 。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-130">In these cases,you can take snapshots programmatically with [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots).</span></span>

## <span data-ttu-id="bfc2e-131">スナップショットの概要</span><span class="sxs-lookup"><span data-stu-id="bfc2e-131">Snapshot summary</span></span>

<span data-ttu-id="bfc2e-132">[スナップショットを作成](#toolbar) すると、スナップショットが作成された時点での JavaScript ヒープのサイズと、割り当てられたオブジェクトの数とページのスクリーンショットを示す概要タイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-132">[Taking a snapshot](#toolbar) will generate a summary tile that indicates the size of the JavaScript heap at the time the snapshot was taken, along with the number of objects allocated and a screenshot of the page.</span></span> <span data-ttu-id="bfc2e-133">分析が必要なユーザー シナリオを実行すると、いつでもスナップショットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-133">You can continue to take snapshots at any time as you run through the user scenario requiring analysis.</span></span> <span data-ttu-id="bfc2e-134">スナップショットは追加のタイルを生成し、それぞれのタイルは前のスナップショットからの JavaScript メモリの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-134">The snapshots generate additional tiles, each of which indicates the difference in JavaScript memory from the previous snapshot.</span></span>

![ヒープ スナップショット](./media/memory_snapshot.png)

<span data-ttu-id="bfc2e-136">概要タイルの値をクリックすると、スナップショット データの詳細を表示するウィンドウ [に切り替えます](#snapshot-details)。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-136">Clicking on the values in the summary tile will switch to the pane showing [details of the snapshot data](#snapshot-details).</span></span> <span data-ttu-id="bfc2e-137">潜在的 [なメモリの問題は、青色の](#snapshot-details) 情報 ("i") アイコンで示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-137">Potential [memory issues are indicated](#snapshot-details) with a blue informational ("i") icon.</span></span>

## <span data-ttu-id="bfc2e-138">スナップショットの詳細</span><span class="sxs-lookup"><span data-stu-id="bfc2e-138">Snapshot details</span></span>

<span data-ttu-id="bfc2e-139">[Snapshot] ウィンドウ *の* データには、ページによって作成されたオブジェクトと、使用している可能性のある JavaScript フレームワークによって割り当てられたメモリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-139">The data in the *Snapshot* pane shows the objects created by your page along with any memory allocated by JavaScript frameworks you may be consuming.</span></span>

![スナップショットの詳細の表](./media/memory_details.png)

<span data-ttu-id="bfc2e-141">3 つのタブは、データの異なるビューを表します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-141">The three tabs represent different views of the data:</span></span>

#### <span data-ttu-id="bfc2e-142">型</span><span class="sxs-lookup"><span data-stu-id="bfc2e-142">Types</span></span>

<span data-ttu-id="bfc2e-143">ヒープ上のオブジェクトのインスタンス数と合計サイズを、オブジェクトの種類別にグループ化して示します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-143">Shows the instance count and total size of objects on the heap, grouped by object type.</span></span> <span data-ttu-id="bfc2e-144">既定では、これらはインスタンス数で並べ替えされます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-144">By default, these are sorted by instance count.</span></span>

<span data-ttu-id="bfc2e-145">上部の [種類] ウィンドウ でオブジェクトを選択[](#object-references)すると、下枠の [オブジェクト参照] テーブルに、そのオブジェクトをポイントしているすべてのオブジェクトが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-145">When you select an object in the upper *Types* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

#### <span data-ttu-id="bfc2e-146">ルート</span><span class="sxs-lookup"><span data-stu-id="bfc2e-146">Roots</span></span>

<span data-ttu-id="bfc2e-147">オブジェクトがグローバル オブジェクトにルート化され、ガベージ コレクションが実行されるのを防ぐ方法を説明する子参照の階層ビューを示します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-147">Shows a hierarchical view of child references to describe how objects are rooted to the global object, thus preventing them from being garbage-collected.</span></span>

<span data-ttu-id="bfc2e-148">既定では、子ノードは保持されたサイズの列で並べ替えされ、最も大きいノードが一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-148">By default, the child nodes are sorted by the retained size column, with the largest at the top.</span></span>

#### <span data-ttu-id="bfc2e-149">ドミネータ</span><span class="sxs-lookup"><span data-stu-id="bfc2e-149">Dominators</span></span>

<span data-ttu-id="bfc2e-150">他のオブジェクトへの排他参照を持つヒープ上のオブジェクトの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-150">Shows a list of objects on the heap that have exclusive references to other objects.</span></span> <span data-ttu-id="bfc2e-151">リミネータは保持されたサイズで並べ替え、解放するのが最も簡単な可能性のあるメモリを消費するオブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-151">Dominators are sorted by retained size to indicate the objects consuming the most memory that are potentially easiest to free.</span></span>

<span data-ttu-id="bfc2e-152">型、ルート、およびドミネータ ビューの列を*解釈する方法を次に示*します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-152">Here's how to interpret the columns in the *Types, Roots* and *Dominators* views:</span></span>

<span data-ttu-id="bfc2e-153">列</span><span class="sxs-lookup"><span data-stu-id="bfc2e-153">Column</span></span> | <span data-ttu-id="bfc2e-154">説明</span><span class="sxs-lookup"><span data-stu-id="bfc2e-154">Description</span></span>
:------------ | :-------------
<span data-ttu-id="bfc2e-155">識別子</span><span class="sxs-lookup"><span data-stu-id="bfc2e-155">Identifier(s)</span></span> | <span data-ttu-id="bfc2e-156">オブジェクトを最も識別する名前。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-156">Name that best identifies the object.</span></span> <span data-ttu-id="bfc2e-157">たとえば、HTML 要素の場合、スナップショットの詳細には ID 属性値 (使用されている場合) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-157">For example, for HTML elements the snapshot details show the ID attribute value, if one is used.</span></span>
<span data-ttu-id="bfc2e-158">型</span><span class="sxs-lookup"><span data-stu-id="bfc2e-158">Type</span></span> | <span data-ttu-id="bfc2e-159">オブジェクトの種類 *(HTMLDivElement など*)。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-159">Object type (for example, *HTMLDivElement*).</span></span>
<span data-ttu-id="bfc2e-160">Size</span><span class="sxs-lookup"><span data-stu-id="bfc2e-160">Size</span></span> | <span data-ttu-id="bfc2e-161">オブジェクト のサイズ 。参照されるオブジェクトのサイズは含め)。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-161">Object size, not including the size of any referenced objects.</span></span>
<span data-ttu-id="bfc2e-162">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="bfc2e-162">Retained size</span></span> | <span data-ttu-id="bfc2e-163">オブジェクト のサイズと、他の親を持たないすべての子オブジェクトのサイズ。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-163">Object size plus the size of all child objects that have no other parents.</span></span> <span data-ttu-id="bfc2e-164">実際には、これはオブジェクトによって保持されるメモリの量です。したがって、オブジェクトを削除すると、指定したメモリ量を解放します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-164">For practical purposes, this is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>
<span data-ttu-id="bfc2e-165">Count</span><span class="sxs-lookup"><span data-stu-id="bfc2e-165">Count</span></span> | <span data-ttu-id="bfc2e-166">オブジェクト インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-166">Number of object instances.</span></span> <span data-ttu-id="bfc2e-167">この値は、[種類] ビューにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-167">This value appears only in the Types view.</span></span>

<span data-ttu-id="bfc2e-168">上部の [主ウィンドウ] ウィンドウでオブジェクトを選択[](#object-references)すると、下枠の [オブジェクト参照] テーブルに、そのオブジェクトをポイントしているすべてのオブジェクトが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-168">When you select an object in the upper *Dominators* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

### <span data-ttu-id="bfc2e-169">フィルター</span><span class="sxs-lookup"><span data-stu-id="bfc2e-169">Filters</span></span>

<span data-ttu-id="bfc2e-170">次の機能を使用して、表のデータをさらに調整できます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-170">You can further adjust data in the table with the following:</span></span>

![組み込みおよびオブジェクトの ID をフィルター処理する](./media/memory_filter.png)

1. <span data-ttu-id="bfc2e-172">**識別子フィルター**: 特定のオブジェクト識別子を検索してデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="bfc2e-172">**Identifier filter**: Filter out data by searching for a particular object identifier</span></span>
2. <span data-ttu-id="bfc2e-173">**ドミネー**タによるグループ化: 他のオブジェクトへの排他的な参照を持つオブジェクトだけが、オブジェクトのトップ レベル ビューに表示されます (これは *[デ*ミネータ] タブの既定のビューです)。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-173">**Group by dominator**: Only objects with *exclusive* references to other objects are shown in the top-level view of objects (this is the default view in the *Dominators* tab).</span></span>
3. <span data-ttu-id="bfc2e-174">**組み込み/ID フィルター**: 既定では [、JavaScript](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) の組み込みオブジェクトがリストに含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-174">**Built-ins / IDs filter**: By default, [JavaScript built-in objects](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) are included in the list.</span></span> <span data-ttu-id="bfc2e-175">オブジェクトの一覧は、区別する必要がある匿名オブジェクトが複数ある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-175">Listing object IDs can be useful if there are multiple anonymous objects which need to be differentiated.</span></span>

<span data-ttu-id="bfc2e-176">種類 *ビュー、ルート* ビュー、および *ディ* ミネータ ビューにはそれぞれ独自のフィルターが設定されています。したがって、別のビューに切り替えてもフィルターは保持されません。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-176">The *Types, Roots* and *Dominators* views each has its own filter, so the filter isn't preserved when you switch to another view.</span></span>

### <span data-ttu-id="bfc2e-177">オブジェクト参照</span><span class="sxs-lookup"><span data-stu-id="bfc2e-177">Object references</span></span>

<span data-ttu-id="bfc2e-178">[型[**] ビューと [**](#types)[**管理**](#dominators)ウィンドウ] ビューの下枠には、共有参照を表示する**オブジェクト**参照リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-178">In the [**Types**](#types) and [**Dominators**](#dominators) views, the lower pane contains an **Object references** list that displays shared references.</span></span> <span data-ttu-id="bfc2e-179">上部のウィンドウでオブジェクトを選択すると、そのオブジェクトをポイントしているすべてのオブジェクト (つまり、選択したオブジェクトを維持しているオブジェクト) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-179">When you choose an object in the upper pane, this list displays all objects that point to that object--in other words, the objects that are keeping the selected object alive.</span></span>

<span data-ttu-id="bfc2e-180">循環参照はアスタリスク (\*) と情報ヒントと一緒に表示され、展開できません。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-180">Circular references are shown with an asterisk (\*) and informational tooltip, and cannot be expanded.</span></span> <span data-ttu-id="bfc2e-181">そうしないと、参照ツリーを上がってメモリを保持しているオブジェクトを識別する妨げになります。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-181">Otherwise, they would prevent you from walking up the reference tree and identifying objects that are retaining memory.</span></span>

<span data-ttu-id="bfc2e-182">同等のオブジェクトをすばやく識別するには、[表示オブジェクト [*ID]*](#filters) フィルター オプションをオンにし、[識別子] 列のオブジェクト名の横にオブジェクト ID *を表示* します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-182">To quickly identify equivalent objects, tick the [*Display object IDs*](#filters) filter option to display object IDs next to object names in the *Identifier(s)* column.</span></span> <span data-ttu-id="bfc2e-183">同じ ID を持つオブジェクトは共有参照です。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-183">Objects that have the same ID are shared references.</span></span>

### <span data-ttu-id="bfc2e-184">スナップショットの比較</span><span class="sxs-lookup"><span data-stu-id="bfc2e-184">Snapshot comparison</span></span>

<span data-ttu-id="bfc2e-185">[スナップショットの比較[] タブ](#snapshot-details)または [スナップショットの[](#snapshot-summary)概要] タイルの比較リンクをクリックすると、2 つのスナップショット間の情報の違いが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-185">Clicking on a [snapshot comparison tab](#snapshot-details) or comparison link on the [snapshot summary tile](#snapshot-summary)  will show a diff of information between the two snapshots.</span></span> <span data-ttu-id="bfc2e-186">比較ウィンドウでは、1 つのスナップショットに対 して表示されるのと[](#snapshot-details)同じスナップショットの詳細が、*次*の追加の値で提供されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-186">In the comparison pane, the *Dominators, Types* and *Roots* views provide the same [*snapshot details*](#snapshot-details) you would see for a single snapshots, with these additional values:</span></span>

<span data-ttu-id="bfc2e-187">列</span><span class="sxs-lookup"><span data-stu-id="bfc2e-187">Column</span></span> | <span data-ttu-id="bfc2e-188">説明</span><span class="sxs-lookup"><span data-stu-id="bfc2e-188">Description</span></span>
:------------ | :-------------
<span data-ttu-id="bfc2e-189">サイズの違い。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-189">Size diff.</span></span> | <span data-ttu-id="bfc2e-190">現在のスナップショット内のオブジェクトのサイズと前のスナップショットのサイズの違い。参照されるオブジェクトのサイズは含め)。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-190">Difference between the size of the object in the current snapshot and its size in the previous snapshot, not including the size of any referenced objects.</span></span>
<span data-ttu-id="bfc2e-191">保持サイズの差分。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-191">Retained size diff.</span></span> | <span data-ttu-id="bfc2e-192">現在のスナップショット内のオブジェクトの保持サイズと、前のスナップショットの保持サイズの違い。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-192">Difference between the retained size of the object in the current snapshot and its retained size in the previous snapshot.</span></span> <span data-ttu-id="bfc2e-193">保持されるサイズには、オブジェクト のサイズと、他の親を持たないすべての子オブジェクトのサイズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-193">The retained size includes the object size plus the size of all its child objects that have no other parents.</span></span> <span data-ttu-id="bfc2e-194">実際には、保持されるサイズはオブジェクトによって保持されるメモリの量です。したがって、オブジェクトを削除すると、指定したメモリ量を解放します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-194">For practical purposes, the retained size is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>

<span data-ttu-id="bfc2e-195">[範囲] ドロップダウンを **使用** すると、スナップショット間の差分情報をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-195">You can use the **Scope** dropdown to filter differential info between snapshots:</span></span>

![スナップショット比較用のスコープ フィルター](./media/memory_comparison_scope_filter.png)

- <strong><span data-ttu-id="bfc2e-197">Snapshot # から残されたオブジェクト: ヒープに追加され、ヒープからベースライン スナップショットから以前のスナップショットに削除されたオブジェクトの違い <number></strong> を示します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-197">Objects left over from Snapshot #<number></strong>: Shows the diff between the objects added to the heap and removed from the heap from the baseline snapshot to the previous snapshot.</span></span> <span data-ttu-id="bfc2e-198">たとえば、スナップショットサマリーのオブジェクト数が <em> +205 / -195 の場合、このフィルターは追加されたが削除されていない 10 個のオブジェクト </em> を表示します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-198">For example, if the snapshot summary shows <em>+205 / -195</em> in the object count, this filter will show you the ten objects that were added but not removed.</span></span>

- <strong><span data-ttu-id="bfc2e-199">Snapshot # と # の間に追加されたオブジェクト: 前のスナップショットからヒープに追加 <number> <number></strong> されたオブジェクトすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-199">Objects added between Snapshot #<number> and #<number></strong>: Shows all objects added to the heap from the previous snapshot.</span></span>

- <strong><span data-ttu-id="bfc2e-200">Snapshot # 内のすべてのオブジェクト: ヒープ上のすべてのオブジェクト (つまり、フィルター処理されていないビュー <number></strong> <em> ) を表示 </em> します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-200">All objects in Snapshot #<number></strong>: Shows all objects on the heap (in other words, an <em>unfiltered</em> view).</span></span>

<span data-ttu-id="bfc2e-201">既定では、" *一* 致しない参照の表示" フィルターは、現在の範囲フィルターと一致しないオブジェクト参照を示すために比較ビューに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-201">By default, the *Show non-matching references* filter is applied to the comparison view to indicate object references that don't match the current Scope filter.</span></span> <span data-ttu-id="bfc2e-202">ドロップダウン メニューからオフにできます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-202">You can turn it off from the dropdown menu:</span></span>

![スナップショット比較用の一致しない参照フィルター](./media/memory_comparison_matching_filter.png)


## <span data-ttu-id="bfc2e-204">ショートカット</span><span class="sxs-lookup"><span data-stu-id="bfc2e-204">Shortcuts</span></span>

 <span data-ttu-id="bfc2e-205">操作</span><span class="sxs-lookup"><span data-stu-id="bfc2e-205">Action</span></span> | <span data-ttu-id="bfc2e-206">ショートカット</span><span class="sxs-lookup"><span data-stu-id="bfc2e-206">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="bfc2e-207">プロファイリング セッションの開始/停止</span><span class="sxs-lookup"><span data-stu-id="bfc2e-207">Start / Stop profiling session</span></span>  | `Ctrl` + `E`
<span data-ttu-id="bfc2e-208">プロファイリング セッションのインポート</span><span class="sxs-lookup"><span data-stu-id="bfc2e-208">Import profiling session</span></span> | `Ctrl` + `O`
<span data-ttu-id="bfc2e-209">プロファイリング セッションのエクスポート</span><span class="sxs-lookup"><span data-stu-id="bfc2e-209">Export profiling session</span></span> | `Ctrl` + `S`
<span data-ttu-id="bfc2e-210">ヒープ スナップショットを取得する</span><span class="sxs-lookup"><span data-stu-id="bfc2e-210">Take heap snapshot</span></span> | `Ctrl` + `Shift` + `T`

## <span data-ttu-id="bfc2e-211">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bfc2e-211">Known Issues</span></span>

### <span data-ttu-id="bfc2e-212">プロファイリング セッションの開始中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="bfc2e-212">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="bfc2e-213">このエラー メッセージが表示された **場合:** メモリ ツールでプロファイリング セッションの開始中にエラーが発生した場合は、次の手順に従って回避策を確認してください。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-213">If you see this error message: **An error occurred while starting the profiling session** in the Memory tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="bfc2e-214">を押 `Windows Key`  +  `R` します。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-214">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="bfc2e-215">[ファイル名を指定して実行] ダイアログボックスに **、「services.msc」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-215">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="bfc2e-217">Microsoft **(R) Diagnostics Hub Standard Collector Service** を見つけて右クリックします。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-217">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="bfc2e-219">Microsoft **(R) Diagnostics Hub Standard Collector Service を再起動します**。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-219">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題- 3](./media/known_issues_3.PNG)

5. <span data-ttu-id="bfc2e-221">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、ページに移動して、押します `F12` 。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-221">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="bfc2e-222">これで、プロファイリングを開始できます。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-222">You should now be able to begin profiling.</span></span> 
![既知の問題- 4](./media/known_issues_4-memory.PNG)

<span data-ttu-id="bfc2e-224">それでも問題が発生しますか?</span><span class="sxs-lookup"><span data-stu-id="bfc2e-224">Still running into problems?</span></span> <span data-ttu-id="bfc2e-225">フィードバックの送信アイコンを使用して、フィードバック **をお送り** ください。</span><span class="sxs-lookup"><span data-stu-id="bfc2e-225">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題- 5](./media/known_issues_5.PNG)
