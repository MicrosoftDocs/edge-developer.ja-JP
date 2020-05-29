---
title: ヒープスナップショットの記録方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e6f64b219bc2b28d01780c28cc605d56a07cb491
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611679"
---
<!-- Copyright Meggin Kearney 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# <span data-ttu-id="634c8-103">ヒープスナップショットの記録方法</span><span class="sxs-lookup"><span data-stu-id="634c8-103">How to Record Heap Snapshots</span></span>   



<span data-ttu-id="634c8-104">Microsoft Edge DevTools ヒーププロファイラーを使用してヒープスナップショットを記録し、メモリリークを検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="634c8-104">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span></span>  

<span data-ttu-id="634c8-105">Microsoft Edge DevTools ヒーププロファイラーは、JavaScript オブジェクトとページの関連する DOM ノードによるメモリ分布を示しています。</span><span class="sxs-lookup"><span data-stu-id="634c8-105">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span></span>  <span data-ttu-id="634c8-106">これは、JavaScript ヒープ \ (JS ヒープ) スナップショットの取得、メモリグラフの分析、スナップショットの比較、メモリリークの検出に使用します。</span><span class="sxs-lookup"><span data-stu-id="634c8-106">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span></span>  <span data-ttu-id="634c8-107">「[オブジェクトを保持するツリー][DevtoolsMemoryProblems101ObjectsRetainingTree]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="634c8-107">See also [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span></span>  

## <span data-ttu-id="634c8-108">スナップショットを撮る</span><span class="sxs-lookup"><span data-stu-id="634c8-108">Take a snapshot</span></span>  

<span data-ttu-id="634c8-109">[**メモリ**] パネルで、[**スナップショット**の作成] を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="634c8-109">On the **Memory** panel, choose **Take snapshot**, then click **Start**.</span></span>  <span data-ttu-id="634c8-110">`Ctrl` + `E` \ (Windows \) または `Cmd` + `E` \ (macOS \) を押すこともできます。</span><span class="sxs-lookup"><span data-stu-id="634c8-110">You may also press `Ctrl`+`E` \(Windows\) or `Cmd`+`E` \(macOS\).</span></span>  

> ##### <span data-ttu-id="634c8-111">図 1</span><span class="sxs-lookup"><span data-stu-id="634c8-111">Figure 1</span></span>  
> <span data-ttu-id="634c8-112">プロファイルの種類の選択</span><span class="sxs-lookup"><span data-stu-id="634c8-112">Select profiling type</span></span>  
> ![プロファイルの種類の選択][ImageProfilingType]  

<span data-ttu-id="634c8-114">**スナップショット**は、最初はレンダラープロセスメモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-114">**Snapshots** are initially stored in the renderer process memory.</span></span>  <span data-ttu-id="634c8-115">スナップショットは、スナップショットアイコンをクリックして表示すると、DevTools に転送されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-115">Snapshots are transferred to the DevTools on demand, when you click on the snapshot icon to view it.</span></span>  

<span data-ttu-id="634c8-116">スナップショットが DevTools に読み込まれ、解析されると、スナップショットのタイトルの下に表示される数値が表示され、[アクセス可能な JavaScript オブジェクトの合計サイズ][DevtoolsMemoryProblems101ObjectSizes]が示されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-116">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span></span>  

> ##### <span data-ttu-id="634c8-117">図 2</span><span class="sxs-lookup"><span data-stu-id="634c8-117">Figure 2</span></span>  
> <span data-ttu-id="634c8-118">到達可能なオブジェクトの合計サイズ</span><span class="sxs-lookup"><span data-stu-id="634c8-118">Total size of reachable objects</span></span>  
> ![到達可能なオブジェクトの合計サイズ][ImageTotalSize]  

> [!NOTE]
> <span data-ttu-id="634c8-120">スナップショットには、到達可能なオブジェクトのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="634c8-120">Only reachable objects are included in snapshots.</span></span>  <span data-ttu-id="634c8-121">また、スナップショットの取得は、常にガベージコレクションで開始されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-121">Also, taking a snapshot always starts with a garbage collection.</span></span>  

## <span data-ttu-id="634c8-122">スナップショットをクリアする</span><span class="sxs-lookup"><span data-stu-id="634c8-122">Clear snapshots</span></span>  

<span data-ttu-id="634c8-123">[**すべてのプロファイルをクリア**] アイコンをクリックして、スナップショットを削除します (devtools から、およびレンダラープロセスに関連付けられているすべてのメモリの両方)。</span><span class="sxs-lookup"><span data-stu-id="634c8-123">Click **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span></span>  

> ##### <span data-ttu-id="634c8-124">図 3</span><span class="sxs-lookup"><span data-stu-id="634c8-124">Figure 3</span></span>  
> <span data-ttu-id="634c8-125">スナップショットを削除する</span><span class="sxs-lookup"><span data-stu-id="634c8-125">Remove snapshots</span></span>  
> ![スナップショットを削除する][ImageRemoveSnapshots]  

<span data-ttu-id="634c8-127">DevTools ウィンドウを閉じると、レンダラープロセスに関連するメモリからプロファイルが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="634c8-127">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span></span>  <span data-ttu-id="634c8-128">DevTools を再び開くと、以前に使用していたスナップショットがすべて、スナップショットの一覧に再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-128">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span></span>  

> [!NOTE]
> <span data-ttu-id="634c8-129">この例では、[散在][GlitchDevtoolsMemoryExample03]しているオブジェクトの例を試して、ヒーププロファイラーを使ってそのオブジェクトをプロファイルしています。</span><span class="sxs-lookup"><span data-stu-id="634c8-129">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span></span>  <span data-ttu-id="634c8-130">いくつかの \ (オブジェクト \) 項目の割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-130">You should see a number of \(object\) item allocations.</span></span>  

## <span data-ttu-id="634c8-131">スナップショットの表示</span><span class="sxs-lookup"><span data-stu-id="634c8-131">View snapshots</span></span>  

<span data-ttu-id="634c8-132">さまざまなタスクについてさまざまな視点からスナップショットを表示します。</span><span class="sxs-lookup"><span data-stu-id="634c8-132">View snapshots from different perspectives for different tasks.</span></span>  

<span data-ttu-id="634c8-133">[**概要] ビュー**は、コンストラクター名によってグループ化されたオブジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="634c8-133">**Summary view** shows objects grouped by the constructor name.</span></span>  <span data-ttu-id="634c8-134">このオブジェクトを使うと、コンストラクター名によってグループ化された型に基づいて、オブジェクト \ (およびメモリ使用量) を簡単に探すことができます。</span><span class="sxs-lookup"><span data-stu-id="634c8-134">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span></span>  <span data-ttu-id="634c8-135">これは、 **DOM リークを追跡**する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="634c8-135">It is particularly helpful for **tracking down DOM leaks**.</span></span>

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

<span data-ttu-id="634c8-136">**比較ビュー**。</span><span class="sxs-lookup"><span data-stu-id="634c8-136">**Comparison view**.</span></span>  <span data-ttu-id="634c8-137">2つのスナップショットの差を表示します。</span><span class="sxs-lookup"><span data-stu-id="634c8-137">Displays the difference between two snapshots.</span></span>  <span data-ttu-id="634c8-138">操作の前後の2つ以上のメモリスナップショットを比較するために使います。</span><span class="sxs-lookup"><span data-stu-id="634c8-138">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span></span>  <span data-ttu-id="634c8-139">解放されたメモリと参照カウントでデルタを調べると、メモリリークの有無と原因を確認できます。</span><span class="sxs-lookup"><span data-stu-id="634c8-139">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span></span>  

<span data-ttu-id="634c8-140">**コンテインメントビュー**。</span><span class="sxs-lookup"><span data-stu-id="634c8-140">**Containment view**.</span></span>  <span data-ttu-id="634c8-141">ヒープの内容を調査できます。</span><span class="sxs-lookup"><span data-stu-id="634c8-141">Allows exploration of heap contents.</span></span>  <span data-ttu-id="634c8-142">**コンテインメントビュー**では、オブジェクト構造の詳細が表示され、グローバル名前空間 \ (ウィンドウ \) で参照されているオブジェクトを分析して、オブジェクトをどのように維持しているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="634c8-142">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span></span>  <span data-ttu-id="634c8-143">これを使って、クロージャを分析し、オブジェクトを低レベルで見ていきます。</span><span class="sxs-lookup"><span data-stu-id="634c8-143">Use it to analyze closures and dive into your objects at a low level.</span></span>  

<span data-ttu-id="634c8-144">ビューを切り替えるには、ビューの上部にあるセレクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="634c8-144">To switch between views, use the selector at the top of the view.</span></span>  

> ##### <span data-ttu-id="634c8-145">図 4</span><span class="sxs-lookup"><span data-stu-id="634c8-145">Figure 4</span></span>  
> <span data-ttu-id="634c8-146">ビューセレクターの切り替え</span><span class="sxs-lookup"><span data-stu-id="634c8-146">Switch views selector</span></span>  
> ![ビューセレクターの切り替え][ImageSwitchViews]  

> [!NOTE]
> <span data-ttu-id="634c8-148">すべてのプロパティが JavaScript ヒープに保存されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="634c8-148">Not all properties are stored on the JavaScript heap.</span></span>  <span data-ttu-id="634c8-149">ネイティブコードを実行する getter を使って実装されたプロパティはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="634c8-149">Properties implemented using getters that run native code are not captured.</span></span>  <span data-ttu-id="634c8-150">また、数値などの文字列以外の値はキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="634c8-150">Also, non-string values such as numbers are not captured.</span></span>  

### <span data-ttu-id="634c8-151">サマリービュー</span><span class="sxs-lookup"><span data-stu-id="634c8-151">Summary view</span></span>  

<span data-ttu-id="634c8-152">最初に、スナップショットが [概要] ビューで開き、次のようにオブジェクトの合計が表示されます。これは、インスタンスを表示するために展開することができます。</span><span class="sxs-lookup"><span data-stu-id="634c8-152">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span></span>  

> ##### <span data-ttu-id="634c8-153">図 5</span><span class="sxs-lookup"><span data-stu-id="634c8-153">Figure 5</span></span>  
> <span data-ttu-id="634c8-154">サマリービュー</span><span class="sxs-lookup"><span data-stu-id="634c8-154">Summary view</span></span>  
> ![サマリービュー][ImageSummaryView]  

<span data-ttu-id="634c8-156">トップレベルのエントリは、"合計" 行です。</span><span class="sxs-lookup"><span data-stu-id="634c8-156">Top-level entries are "total" lines.</span></span>  

| <span data-ttu-id="634c8-157">トップレベルのエントリ</span><span class="sxs-lookup"><span data-stu-id="634c8-157">Top-level entries</span></span> | <span data-ttu-id="634c8-158">説明</span><span class="sxs-lookup"><span data-stu-id="634c8-158">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="634c8-159">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="634c8-159">Constructor</span></span>** | <span data-ttu-id="634c8-160">このコンストラクターを使用して作成されたすべてのオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="634c8-160">Represents all objects created using this constructor.</span></span>  |  
| **<span data-ttu-id="634c8-161">距離</span><span class="sxs-lookup"><span data-stu-id="634c8-161">Distance</span></span>** | <span data-ttu-id="634c8-162">ノードの最短のシンプルパスを使用してルートへの距離を表示します。</span><span class="sxs-lookup"><span data-stu-id="634c8-162">displays the distance to the root using the shortest simple path of nodes.</span></span>  |  
| **<span data-ttu-id="634c8-163">浅いサイズ</span><span class="sxs-lookup"><span data-stu-id="634c8-163">Shallow size</span></span>** | <span data-ttu-id="634c8-164">特定のコンストラクター関数で作成されたすべてのオブジェクトの浅いサイズの合計を表示します。</span><span class="sxs-lookup"><span data-stu-id="634c8-164">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span></span>  <span data-ttu-id="634c8-165">緩斜面サイズとは、オブジェクトによって保持されているメモリのサイズです (一般的には、配列と文字列の緩斜面サイズが大きくなります)。</span><span class="sxs-lookup"><span data-stu-id="634c8-165">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span></span>  <span data-ttu-id="634c8-166">「[オブジェクトサイズ][DevtoolsMemoryProblems101ObjectSizes]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="634c8-166">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  
| **<span data-ttu-id="634c8-167">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="634c8-167">Retained size</span></span>** | <span data-ttu-id="634c8-168">同じオブジェクトセット間で保持される最大のサイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="634c8-168">Displays the maximum retained size among the same set of objects.</span></span>  <span data-ttu-id="634c8-169">オブジェクトが削除された後に解放できるメモリのサイズ \ (および依存関係がなくなります) は、保持されているサイズと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="634c8-169">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span></span>  <span data-ttu-id="634c8-170">「[オブジェクトサイズ][DevtoolsMemoryProblems101ObjectSizes]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="634c8-170">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

<span data-ttu-id="634c8-171">上のビューで合計行を展開すると、すべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-171">After expanding a total line in the upper view, all of the instances are displayed.</span></span>  <span data-ttu-id="634c8-172">各インスタンスについて、"浅い" と "保持されるサイズ" が対応する列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-172">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span></span>  <span data-ttu-id="634c8-173">文字の後に `@` 表示される数値は、オブジェクトの一意の ID です。ヒープスナップショットは、オブジェクトごとに比較できます。</span><span class="sxs-lookup"><span data-stu-id="634c8-173">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span></span>  

<span data-ttu-id="634c8-174">黄色のオブジェクトには JavaScript 参照と赤のオブジェクトがあり、いずれかが黄色の背景で参照される切り離されたノードであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="634c8-174">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span></span>  

**<span data-ttu-id="634c8-175">ヒーププロファイラーのさまざまなコンストラクター \ (グループ \) エントリに対応するものは何ですか?</span><span class="sxs-lookup"><span data-stu-id="634c8-175">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span></span>**  

> ##### <span data-ttu-id="634c8-176">図 6</span><span class="sxs-lookup"><span data-stu-id="634c8-176">Figure 6</span></span>  
> <span data-ttu-id="634c8-177">コンストラクターグループ</span><span class="sxs-lookup"><span data-stu-id="634c8-177">Constructor groups</span></span>  
> ![コンストラクターグループ][ImageConstructorGroups]  

| <span data-ttu-id="634c8-179">コンストラクター \ (グループ \) エントリ</span><span class="sxs-lookup"><span data-stu-id="634c8-179">Constructor \(group\) entry</span></span> | <span data-ttu-id="634c8-180">説明</span><span class="sxs-lookup"><span data-stu-id="634c8-180">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="634c8-181">\ (グローバルプロパティ \)</span><span class="sxs-lookup"><span data-stu-id="634c8-181">\(global property\)</span></span>** | <span data-ttu-id="634c8-182">グローバルオブジェクトの間 ( `window` \) とそれが参照するオブジェクトの間の中間オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="634c8-182">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span></span>  <span data-ttu-id="634c8-183">コンストラクターを使ってオブジェクトを作成 `Person` し、グローバルオブジェクトで保持している場合、保持パスは次のようになり `[global] > \(global property\) > Person` ます。</span><span class="sxs-lookup"><span data-stu-id="634c8-183">If an object is created using a constructor `Person` and is held by a global object, the retaining path would look like `[global] > \(global property\) > Person`.</span></span>  <span data-ttu-id="634c8-184">これは、オブジェクトが互いに直接参照する場合とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="634c8-184">This contrasts with the norm, where objects directly reference each other.</span></span>  <span data-ttu-id="634c8-185">中間オブジェクトは、パフォーマンス上の理由で存在します。</span><span class="sxs-lookup"><span data-stu-id="634c8-185">Intermediate objects exist for performance reasons.</span></span>  <span data-ttu-id="634c8-186">グローバル変数は定期的に変更され、プロパティアクセスの最適化が行われます。グローバルでないオブジェクトには、グローバルには適用されません。</span><span class="sxs-lookup"><span data-stu-id="634c8-186">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span></span>  |  
| **<span data-ttu-id="634c8-187">\ (ルート \)</span><span class="sxs-lookup"><span data-stu-id="634c8-187">\(roots\)</span></span>** | <span data-ttu-id="634c8-188">保持ツリービューのルートエントリは、選択したオブジェクトを参照するエンティティです。</span><span class="sxs-lookup"><span data-stu-id="634c8-188">The root entries in the retaining tree view are the entities that have references to the selected object.</span></span>  <span data-ttu-id="634c8-189">エンジン固有の目的で、エンジンによって作成された参照をエントリにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="634c8-189">The entries may also be references created by the engine for engine-specific purposes.</span></span>  <span data-ttu-id="634c8-190">エンジンには参照オブジェクトをキャッシュしていますが、このような参照はすべて脆弱であり、実際には厳密な参照がないため、オブジェクトは収集されません。</span><span class="sxs-lookup"><span data-stu-id="634c8-190">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span></span>  |  
| **<span data-ttu-id="634c8-191">\ (休業)</span><span class="sxs-lookup"><span data-stu-id="634c8-191">\(closure\)</span></span>** | <span data-ttu-id="634c8-192">関数クロージャによってオブジェクトのグループに対する参照の数。</span><span class="sxs-lookup"><span data-stu-id="634c8-192">A count of references to a group of objects through function closures.</span></span>  |  
| **<span data-ttu-id="634c8-193">\ (配列, 文字列, 数値, regexp \)</span><span class="sxs-lookup"><span data-stu-id="634c8-193">\(array, string, number, regexp\)</span></span>** | <span data-ttu-id="634c8-194">配列、文字列、数値、または正規表現を参照するプロパティを持つオブジェクト型のリスト。</span><span class="sxs-lookup"><span data-stu-id="634c8-194">A list of object types with properties which reference an Array, String, Number, or regular expression.</span></span>  |  
| **<span data-ttu-id="634c8-195">\ (コンパイル済みコード)</span><span class="sxs-lookup"><span data-stu-id="634c8-195">\(compiled code\)</span></span>** | <span data-ttu-id="634c8-196">コンパイル済みコードに関連するすべて。</span><span class="sxs-lookup"><span data-stu-id="634c8-196">Everything related to compiled code.</span></span>  <span data-ttu-id="634c8-197">スクリプトは関数と似ていますが、本文に対応してい `<script>` ます。</span><span class="sxs-lookup"><span data-stu-id="634c8-197">Script is similar to a function, but corresponds to a `<script>` body.</span></span>  <span data-ttu-id="634c8-198">SharedFunctionInfos 機能 \ (SFI \) は、関数とコンパイルされたコードの間に位置するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="634c8-198">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span></span>  <span data-ttu-id="634c8-199">関数は通常、コンテキストを持ちますが、SFIs はできません。</span><span class="sxs-lookup"><span data-stu-id="634c8-199">Functions usually have a context, while SFIs do not.</span></span>  |  
| <span data-ttu-id="634c8-200">**HTMLDivElement**、 **HTMLAnchorElement**、 **documentfragment**など。</span><span class="sxs-lookup"><span data-stu-id="634c8-200">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span></span>  | <span data-ttu-id="634c8-201">コードで参照されている特定の型の要素またはドキュメントオブジェクトへの参照。</span><span class="sxs-lookup"><span data-stu-id="634c8-201">References to elements or document objects of a particular type referenced by your code.</span></span>  |  

<!--todo: add heap profiling summary section when available -->  

### <span data-ttu-id="634c8-202">比較ビュー</span><span class="sxs-lookup"><span data-stu-id="634c8-202">Comparison view</span></span>  

<span data-ttu-id="634c8-203">リークしたオブジェクトを検索するには、複数のスナップショットを相互に比較します。</span><span class="sxs-lookup"><span data-stu-id="634c8-203">Find leaked objects by comparing multiple snapshots to each other.</span></span>  <span data-ttu-id="634c8-204">特定のアプリケーションの操作によってリークが発生しないことを確認するには (たとえば、ドキュメントを開いて、それを閉じるときに、通常は1組の直接操作と逆方向の操作のペアである)、次のシナリオに従うことができます。</span><span class="sxs-lookup"><span data-stu-id="634c8-204">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span></span>  

1.  <span data-ttu-id="634c8-205">操作を実行する前に、ヒープスナップショットを取得します。</span><span class="sxs-lookup"><span data-stu-id="634c8-205">Take a heap snapshot before performing an operation.</span></span>  
1.  <span data-ttu-id="634c8-206">操作を実行します (リークの原因と思われる何らかの方法でページを操作します)。</span><span class="sxs-lookup"><span data-stu-id="634c8-206">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span></span>  
1.  <span data-ttu-id="634c8-207">逆の操作を実行します (反対の操作を行って、何度も繰り返します)。</span><span class="sxs-lookup"><span data-stu-id="634c8-207">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span></span>  
1.  <span data-ttu-id="634c8-208">2つ目のヒープスナップショットを取得し、そのビューを**スナップショット 1**と比較して**比較**します。</span><span class="sxs-lookup"><span data-stu-id="634c8-208">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span></span>  

<span data-ttu-id="634c8-209">[**比較**] ビューでは、2つのスナップショットの差が表示されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-209">In the **Comparison** view, the difference between two snapshots is displayed.</span></span>  <span data-ttu-id="634c8-210">合計項目を展開すると、追加または削除されたオブジェクトインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-210">When expanding a total entry, added and deleted object instances are shown.</span></span>  

> ##### <span data-ttu-id="634c8-211">図 7</span><span class="sxs-lookup"><span data-stu-id="634c8-211">Figure 7</span></span>  
> <span data-ttu-id="634c8-212">比較ビュー</span><span class="sxs-lookup"><span data-stu-id="634c8-212">Comparison view</span></span>  
> ![比較ビュー][ImageComparisonView]  

<!--todo: add HeapProfilingComparison section when available  -->  

### <span data-ttu-id="634c8-214">コンテインメントビュー</span><span class="sxs-lookup"><span data-stu-id="634c8-214">Containment view</span></span>  

<span data-ttu-id="634c8-215">**コンテインメント**ビューは、基本的には、アプリケーションのオブジェクト構造の "鳥の視点" ビューです。</span><span class="sxs-lookup"><span data-stu-id="634c8-215">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span></span>  <span data-ttu-id="634c8-216">この機能を使用すると、JavaScript オブジェクトを構成する仮想マシン \ (VM) 内部オブジェクトを監視したり、アプリケーションが非常に低レベルで使用しているメモリ量を把握したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="634c8-216">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span></span>  

| <span data-ttu-id="634c8-217">コンテインメントビューのエントリポイント</span><span class="sxs-lookup"><span data-stu-id="634c8-217">Containment view entry points</span></span> | <span data-ttu-id="634c8-218">説明</span><span class="sxs-lookup"><span data-stu-id="634c8-218">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="634c8-219">DOMWindow オブジェクト</span><span class="sxs-lookup"><span data-stu-id="634c8-219">DOMWindow objects</span></span>** | <span data-ttu-id="634c8-220">JavaScript コードのグローバルオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="634c8-220">Global objects for JavaScript code.</span></span>  |  
| **<span data-ttu-id="634c8-221">GC ルート</span><span class="sxs-lookup"><span data-stu-id="634c8-221">GC roots</span></span>** | <span data-ttu-id="634c8-222">VM のガーベジで使用される実際の GC ルート。</span><span class="sxs-lookup"><span data-stu-id="634c8-222">The actual GC roots used by the garbage of the VM.</span></span>  <span data-ttu-id="634c8-223">GC ルートは、組み込みのオブジェクトマップ、シンボルテーブル、VM スレッドスタック、コンパイルキャッシュ、ハンドルスコープ、グローバルハンドルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="634c8-223">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span></span>  |  
| **<span data-ttu-id="634c8-224">ネイティブオブジェクト</span><span class="sxs-lookup"><span data-stu-id="634c8-224">Native objects</span></span>** | <span data-ttu-id="634c8-225">ブラウザーオブジェクトは、JavaScript 仮想マシンの内部に "プッシュされました" (JavaScript VM \) で、オートメーション (DOM ノード、CSS ルールなど) を許可します。</span><span class="sxs-lookup"><span data-stu-id="634c8-225">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span></span>  |  

> ##### <span data-ttu-id="634c8-226">図 8</span><span class="sxs-lookup"><span data-stu-id="634c8-226">Figure 8</span></span>  
> <span data-ttu-id="634c8-227">コンテインメントビュー</span><span class="sxs-lookup"><span data-stu-id="634c8-227">Containment view</span></span>  
> ![コンテインメントビュー][ImageContainmentView]  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> <span data-ttu-id="634c8-229">クロージャに関するヒント。</span><span class="sxs-lookup"><span data-stu-id="634c8-229">A tip about closures.</span></span>  <span data-ttu-id="634c8-230">スナップショットのクロージャを簡単に区別できるように、関数に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="634c8-230">Name the functions so you are able to easily distinguish between closures in the snapshot.</span></span>  <span data-ttu-id="634c8-231">たとえば、次の例では、名前付き関数は使用されません。</span><span class="sxs-lookup"><span data-stu-id="634c8-231">For example, this example does not use named functions.</span></span>  
> 
> ```javascript
> function createLargeClosure() {
>     var largeStr = new Array(1000000).join('x');
>     var lC = function() { // this is NOT a named function
>         return largeStr;
>     };
>     return lC;
> }
> ```  
> 
> <span data-ttu-id="634c8-232">この例では、名前付き関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="634c8-232">This example uses named functions:</span></span>  
> 
> ```javascript
> function createLargeClosure() {
>     var largeStr = new Array(1000000).join('x');
>     var lC = function lC() { // this IS a named function
>         return largeStr;
>     };
>     return lC;
> }
> ```  
> 
> <!--  
> > ##### old Figure 9  
> > Name functions to distinguish between closures  
> > ![Name functions to distinguish between closures][ImageDomLeaks]  
> -->  
> 
> > [!NOTE]
> > <span data-ttu-id="634c8-233">この例では、メモリ上でのクロージャの影響を分析するための悪を示して[ `eval` い][GlitchDevtoolsMemoryExample07]ます。</span><span class="sxs-lookup"><span data-stu-id="634c8-233">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span></span>  <span data-ttu-id="634c8-234">また、この例では、[ヒープ割り当て][GlitchDevtoolsMemoryExample08]の記録に関する次の例を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="634c8-234">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span></span>  
> 

## <span data-ttu-id="634c8-235">色のコーディングを検索する</span><span class="sxs-lookup"><span data-stu-id="634c8-235">Look up color coding</span></span>  

<span data-ttu-id="634c8-236">オブジェクトのプロパティとプロパティ値の型が異なり、それに応じて色付けされます。</span><span class="sxs-lookup"><span data-stu-id="634c8-236">Properties and property values of objects have different types and are colored accordingly.</span></span>  <span data-ttu-id="634c8-237">各プロパティには、4つの型のいずれかが含まれています。</span><span class="sxs-lookup"><span data-stu-id="634c8-237">Each property has one of four types.</span></span>  

| <span data-ttu-id="634c8-238">プロパティの種類</span><span class="sxs-lookup"><span data-stu-id="634c8-238">Property Type</span></span> | <span data-ttu-id="634c8-239">説明</span><span class="sxs-lookup"><span data-stu-id="634c8-239">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="634c8-240">a: プロパティ</span><span class="sxs-lookup"><span data-stu-id="634c8-240">a: property</span></span>** | <span data-ttu-id="634c8-241">名前を付けた標準プロパティ `.` 。 \ (ドット \) 演算子、または `[` `]` \ (かっこ \) 表記を使用してアクセスし `["foo bar"]` ます。</span><span class="sxs-lookup"><span data-stu-id="634c8-241">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span></span>  |  
| **<span data-ttu-id="634c8-242">0: 要素</span><span class="sxs-lookup"><span data-stu-id="634c8-242">0: element</span></span>** | <span data-ttu-id="634c8-243">`[` `]` \ (かっこ \) 表記法によってアクセスされる、数値インデックスを持つ標準プロパティ。</span><span class="sxs-lookup"><span data-stu-id="634c8-243">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span></span>  |  
| **<span data-ttu-id="634c8-244">a: context var</span><span class="sxs-lookup"><span data-stu-id="634c8-244">a: context var</span></span>** |  <span data-ttu-id="634c8-245">関数の中で変数名によってアクセスできる関数のコンテキスト内の変数。</span><span class="sxs-lookup"><span data-stu-id="634c8-245">A variable in a function context, accessible by the variable name from inside a function closure.</span></span>  |  
| **<span data-ttu-id="634c8-246">a: システムの prop</span><span class="sxs-lookup"><span data-stu-id="634c8-246">a: system prop</span></span>** | <span data-ttu-id="634c8-247">Javascript の VM によって追加されたプロパティ。 JavaScript コードからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="634c8-247">A property added by the JavaScript VM, not accessible from JavaScript code.</span></span>  |  

<span data-ttu-id="634c8-248">として指定 `System` されているオブジェクトは、JavaScript の型に対応していません。</span><span class="sxs-lookup"><span data-stu-id="634c8-248">Objects designated as `System` do not have a corresponding JavaScript type.</span></span>  <span data-ttu-id="634c8-249">それぞれは、Javascript VM のオブジェクトシステム実装の一部です。</span><span class="sxs-lookup"><span data-stu-id="634c8-249">Each is part of the object system implementation of the Javascript VM.</span></span>  <span data-ttu-id="634c8-250">V8 は、内部オブジェクトのほとんどを、ユーザーの JS オブジェクトと同じヒープに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="634c8-250">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span></span>  <span data-ttu-id="634c8-251">そのため、これらは V8 の内部構造にすぎません。</span><span class="sxs-lookup"><span data-stu-id="634c8-251">So these are just V8 internals.</span></span>  

## <span data-ttu-id="634c8-252">特定のオブジェクトを検索する</span><span class="sxs-lookup"><span data-stu-id="634c8-252">Find a specific object</span></span>  

<span data-ttu-id="634c8-253">収集されたヒープ内のオブジェクトを検索するには、を使用 `Ctrl` + `F` してオブジェクト ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="634c8-253">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span></span>  

## <span data-ttu-id="634c8-254">DOM リークの発見</span><span class="sxs-lookup"><span data-stu-id="634c8-254">Uncover DOM leaks</span></span>  

<span data-ttu-id="634c8-255">ヒーププロファイラーには、ブラウザーのネイティブオブジェクトの間で双方向の依存関係 (DOM ノード、CSS ルール \)、JavaScript オブジェクトの間で双方向の依存関係を反映する機能があります。</span><span class="sxs-lookup"><span data-stu-id="634c8-255">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span></span>
<span data-ttu-id="634c8-256">これにより、デタッチした切り離された DOM サブツリーを回避して、非表示のリークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="634c8-256">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span></span>  

<span data-ttu-id="634c8-257">DOM リークは想像よりも大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="634c8-257">DOM leaks may be bigger than you think.</span></span>  <span data-ttu-id="634c8-258">次の例について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="634c8-258">Consider the following sample.</span></span>  <span data-ttu-id="634c8-259">#Tree GC はいつですか?</span><span class="sxs-lookup"><span data-stu-id="634c8-259">When is the #tree GC?</span></span>  

```javascript
var select = document.querySelector;
var treeRef = select("#tree");
var leafRef = select("#leaf");
var body = select("body");
body.removeChild(treeRef);
//#tree in not GC yet due to treeRef
treeRef = null;
//#tree is not GC yet due to indirect
//reference from leafRef
leafRef = null;
//#NOW able to be #tree GC
```  

<span data-ttu-id="634c8-260">は、 `#leaf` 関連する親 \ (parentNode \) への参照を保持し、 `#tree` leafRef が nullified の場合にのみ、GC の候補の下にあるツリー全体を示し `#tree` ます。</span><span class="sxs-lookup"><span data-stu-id="634c8-260">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span></span>  

> ##### <span data-ttu-id="634c8-261">図 9</span><span class="sxs-lookup"><span data-stu-id="634c8-261">Figure 9</span></span>  
> <span data-ttu-id="634c8-262">DOM サブツリー</span><span class="sxs-lookup"><span data-stu-id="634c8-262">DOM subtrees</span></span>  
> <span data-ttu-id="634c8-263">![DOM サブツリー][ImageTreeGc]</span><span class="sxs-lookup"><span data-stu-id="634c8-263">![DOM subtrees][ImageTreeGc]</span></span>  

> [!NOTE]
> <span data-ttu-id="634c8-264">例: リークしている可能性のある[DOM ノード][GlitchDevtoolsMemoryExample06]を理解し、それを検出する方法については、次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="634c8-264">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span></span>  <span data-ttu-id="634c8-265">次の例では、 [DOM リークが予想よりも大きくなって][GlitchDevtoolsMemoryExample09]います。</span><span class="sxs-lookup"><span data-stu-id="634c8-265">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span></span>  

<span data-ttu-id="634c8-266">DOM のリークとメモリ分析の基礎の詳細については、「 [Microsoft Edge DevTools によるメモリリークの検出とデバッグ][GonzaloRuizdeVillaMemory]Gonzalo Ruiz de Villa」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="634c8-266">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span></span>  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

<!--## Feedback   -->  



<!-- image links -->  

[ImageProfilingType]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png "図 1: [プロファイルの種類の選択]"  
[ImageTotalSize]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png "図 2: 到達可能なオブジェクトの合計サイズ"  
[ImageRemoveSnapshots]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png "図 3: スナップショットを削除する"  
[ImageSwitchViews]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png "図 4: ビューセレクターの切り替え"  
[ImageSummaryView]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png "図 5: 概要ビュー"  
[ImageConstructorGroups]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png "図 6: コンストラクターグループ"  
[ImageComparisonView]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png "図 7: 比較ビュー"  
[ImageContainmentView]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png "図 8: コンテインメントビュー"  
<!--[ImageDomLeaks]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-domleaks.msft.png "old Figure 9: Name functions to distinguish between closures"  -->  
[ImageTreeGc]:/microsoft-edge/devtools-guide-chromium/media/memory-problems-tree-gc.msft.png "図 9: DOM サブツリー"  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: /microsoft-edge/devtools-guide-chromium/memory-problems/memory-101#object-sizes "オブジェクトサイズ-メモリの用語"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: /microsoft-edge/devtools-guide-chromium/memory-problems/memory-101#objects-retaining-tree "ツリーメモリの用語を保持するオブジェクト"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10-Microsoft Edge (Chromium) DevTools |故障"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "メモリ |スライド"  

> [!NOTE]
> <span data-ttu-id="634c8-285">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="634c8-285">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="634c8-286">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots)にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="634c8-286">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="634c8-288">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="634c8-288">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
