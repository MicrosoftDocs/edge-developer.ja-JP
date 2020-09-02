---
title: ヒープスナップショットの記録方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 183482660ed5fc50862dfd2cce7209384fee93e3
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986172"
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

# <span data-ttu-id="92a14-103">ヒープスナップショットの記録方法</span><span class="sxs-lookup"><span data-stu-id="92a14-103">How to record heap snapshots</span></span>  

<span data-ttu-id="92a14-104">Microsoft Edge DevTools ヒーププロファイラーを使用してヒープスナップショットを記録し、メモリリークを検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="92a14-104">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span></span>  

<span data-ttu-id="92a14-105">Microsoft Edge DevTools ヒーププロファイラーは、JavaScript オブジェクトとページの関連する DOM ノードによるメモリ分布を示しています。</span><span class="sxs-lookup"><span data-stu-id="92a14-105">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span></span>  <span data-ttu-id="92a14-106">これは、JavaScript ヒープ \ (JS ヒープ) スナップショットの取得、メモリグラフの分析、スナップショットの比較、メモリリークの検出に使用します。</span><span class="sxs-lookup"><span data-stu-id="92a14-106">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span></span>  <span data-ttu-id="92a14-107">「 [オブジェクトを保持するツリー][DevtoolsMemoryProblems101ObjectsRetainingTree]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92a14-107">See also [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span></span>  

## <span data-ttu-id="92a14-108">スナップショットを撮る</span><span class="sxs-lookup"><span data-stu-id="92a14-108">Take a snapshot</span></span>  

<span data-ttu-id="92a14-109">[ **メモリ** ] パネルで、[ **スナップショット**の作成] を選択し、[ **開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92a14-109">On the **Memory** panel, choose **Take snapshot**, then click **Start**.</span></span>  <span data-ttu-id="92a14-110">`Ctrl` + `E` \ (Windows \) または `Cmd` + `E` \ (macOS \) を押すこともできます。</span><span class="sxs-lookup"><span data-stu-id="92a14-110">You may also press `Ctrl`+`E` \(Windows\) or `Cmd`+`E` \(macOS\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="プロファイルの種類の選択" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   <span data-ttu-id="92a14-112">プロファイルの種類の選択</span><span class="sxs-lookup"><span data-stu-id="92a14-112">Select profiling type</span></span>  
:::image-end:::  

<span data-ttu-id="92a14-113">**スナップショット** は、最初はレンダラープロセスメモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-113">**Snapshots** are initially stored in the renderer process memory.</span></span>  <span data-ttu-id="92a14-114">スナップショットは、スナップショットアイコンをクリックして表示すると、DevTools に転送されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-114">Snapshots are transferred to the DevTools on demand, when you click on the snapshot icon to view it.</span></span>  

<span data-ttu-id="92a14-115">スナップショットが DevTools に読み込まれ、解析されると、スナップショットのタイトルの下に表示される数値が表示され、 [アクセス可能な JavaScript オブジェクトの合計サイズ][DevtoolsMemoryProblems101ObjectSizes]が示されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-115">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="到達可能なオブジェクトの合計サイズ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   <span data-ttu-id="92a14-117">到達可能なオブジェクトの合計サイズ</span><span class="sxs-lookup"><span data-stu-id="92a14-117">Total size of reachable objects</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="92a14-118">スナップショットには、到達可能なオブジェクトのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92a14-118">Only reachable objects are included in snapshots.</span></span>  <span data-ttu-id="92a14-119">また、スナップショットの取得は、常にガベージコレクションで開始されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-119">Also, taking a snapshot always starts with a garbage collection.</span></span>  

## <span data-ttu-id="92a14-120">スナップショットをクリアする</span><span class="sxs-lookup"><span data-stu-id="92a14-120">Clear snapshots</span></span>  

<span data-ttu-id="92a14-121">[ **すべてのプロファイルをクリア** ] アイコンをクリックして、スナップショットを削除します (devtools から、およびレンダラープロセスに関連付けられているすべてのメモリの両方)。</span><span class="sxs-lookup"><span data-stu-id="92a14-121">Click **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="スナップショットを削除する" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   <span data-ttu-id="92a14-123">スナップショットを削除する</span><span class="sxs-lookup"><span data-stu-id="92a14-123">Remove snapshots</span></span>  
:::image-end:::  

<span data-ttu-id="92a14-124">DevTools ウィンドウを閉じると、レンダラープロセスに関連するメモリからプロファイルが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="92a14-124">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span></span>  <span data-ttu-id="92a14-125">DevTools を再び開くと、以前に使用していたスナップショットがすべて、スナップショットの一覧に再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-125">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span></span>  

> [!NOTE]
> <span data-ttu-id="92a14-126">この例では、 [散在][GlitchDevtoolsMemoryExample03] しているオブジェクトの例を試して、ヒーププロファイラーを使ってそのオブジェクトをプロファイルしています。</span><span class="sxs-lookup"><span data-stu-id="92a14-126">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span></span>  <span data-ttu-id="92a14-127">いくつかの \ (オブジェクト \) 項目の割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-127">You should see a number of \(object\) item allocations.</span></span>  

## <span data-ttu-id="92a14-128">スナップショットの表示</span><span class="sxs-lookup"><span data-stu-id="92a14-128">View snapshots</span></span>  

<span data-ttu-id="92a14-129">さまざまなタスクについてさまざまな視点からスナップショットを表示します。</span><span class="sxs-lookup"><span data-stu-id="92a14-129">View snapshots from different perspectives for different tasks.</span></span>  

<span data-ttu-id="92a14-130">[**概要] ビュー**は、コンストラクター名によってグループ化されたオブジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="92a14-130">**Summary view** shows objects grouped by the constructor name.</span></span>  <span data-ttu-id="92a14-131">このオブジェクトを使うと、コンストラクター名によってグループ化された型に基づいて、オブジェクト \ (およびメモリ使用量) を簡単に探すことができます。</span><span class="sxs-lookup"><span data-stu-id="92a14-131">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span></span>  <span data-ttu-id="92a14-132">これは、 **DOM リークを追跡**する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="92a14-132">It is particularly helpful for **tracking down DOM leaks**.</span></span>

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

<span data-ttu-id="92a14-133">**比較ビュー**。</span><span class="sxs-lookup"><span data-stu-id="92a14-133">**Comparison view**.</span></span>  <span data-ttu-id="92a14-134">2つのスナップショットの差を表示します。</span><span class="sxs-lookup"><span data-stu-id="92a14-134">Displays the difference between two snapshots.</span></span>  <span data-ttu-id="92a14-135">操作の前後の2つ以上のメモリスナップショットを比較するために使います。</span><span class="sxs-lookup"><span data-stu-id="92a14-135">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span></span>  <span data-ttu-id="92a14-136">解放されたメモリと参照カウントでデルタを調べると、メモリリークの有無と原因を確認できます。</span><span class="sxs-lookup"><span data-stu-id="92a14-136">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span></span>  

<span data-ttu-id="92a14-137">**コンテインメントビュー**。</span><span class="sxs-lookup"><span data-stu-id="92a14-137">**Containment view**.</span></span>  <span data-ttu-id="92a14-138">ヒープの内容を調査できます。</span><span class="sxs-lookup"><span data-stu-id="92a14-138">Allows exploration of heap contents.</span></span>  <span data-ttu-id="92a14-139">**コンテインメントビュー** では、オブジェクト構造の詳細が表示され、グローバル名前空間 \ (ウィンドウ \) で参照されているオブジェクトを分析して、オブジェクトをどのように維持しているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="92a14-139">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span></span>  <span data-ttu-id="92a14-140">これを使って、クロージャを分析し、オブジェクトを低レベルで見ていきます。</span><span class="sxs-lookup"><span data-stu-id="92a14-140">Use it to analyze closures and dive into your objects at a low level.</span></span>  

<span data-ttu-id="92a14-141">ビューを切り替えるには、ビューの上部にあるセレクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="92a14-141">To switch between views, use the selector at the top of the view.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="ビューセレクターの切り替え" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   <span data-ttu-id="92a14-143">ビューセレクターの切り替え</span><span class="sxs-lookup"><span data-stu-id="92a14-143">Switch views selector</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="92a14-144">すべてのプロパティが JavaScript ヒープに保存されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="92a14-144">Not all properties are stored on the JavaScript heap.</span></span>  <span data-ttu-id="92a14-145">ネイティブコードを実行する getter を使って実装されたプロパティはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="92a14-145">Properties implemented using getters that run native code are not captured.</span></span>  <span data-ttu-id="92a14-146">また、数値などの文字列以外の値はキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="92a14-146">Also, non-string values such as numbers are not captured.</span></span>  

### <span data-ttu-id="92a14-147">サマリービュー</span><span class="sxs-lookup"><span data-stu-id="92a14-147">Summary view</span></span>  

<span data-ttu-id="92a14-148">最初に、スナップショットが [概要] ビューで開き、次のようにオブジェクトの合計が表示されます。これは、インスタンスを表示するために展開することができます。</span><span class="sxs-lookup"><span data-stu-id="92a14-148">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="サマリービュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   <span data-ttu-id="92a14-150">**サマリー** ビュー</span><span class="sxs-lookup"><span data-stu-id="92a14-150">**Summary** view</span></span>  
:::image-end:::  

<span data-ttu-id="92a14-151">トップレベルのエントリは、"合計" 行です。</span><span class="sxs-lookup"><span data-stu-id="92a14-151">Top-level entries are "total" lines.</span></span>  

| <span data-ttu-id="92a14-152">トップレベルのエントリ</span><span class="sxs-lookup"><span data-stu-id="92a14-152">Top-level entries</span></span> | <span data-ttu-id="92a14-153">説明</span><span class="sxs-lookup"><span data-stu-id="92a14-153">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="92a14-154">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="92a14-154">Constructor</span></span>** | <span data-ttu-id="92a14-155">このコンストラクターを使用して作成されたすべてのオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="92a14-155">Represents all objects created using this constructor.</span></span>  |  
| **<span data-ttu-id="92a14-156">距離</span><span class="sxs-lookup"><span data-stu-id="92a14-156">Distance</span></span>** | <span data-ttu-id="92a14-157">ノードの最短のシンプルパスを使用してルートへの距離を表示します。</span><span class="sxs-lookup"><span data-stu-id="92a14-157">displays the distance to the root using the shortest simple path of nodes.</span></span>  |  
| **<span data-ttu-id="92a14-158">浅いサイズ</span><span class="sxs-lookup"><span data-stu-id="92a14-158">Shallow size</span></span>** | <span data-ttu-id="92a14-159">特定のコンストラクター関数で作成されたすべてのオブジェクトの浅いサイズの合計を表示します。</span><span class="sxs-lookup"><span data-stu-id="92a14-159">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span></span>  <span data-ttu-id="92a14-160">緩斜面サイズとは、オブジェクトによって保持されているメモリのサイズです (一般的には、配列と文字列の緩斜面サイズが大きくなります)。</span><span class="sxs-lookup"><span data-stu-id="92a14-160">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span></span>  <span data-ttu-id="92a14-161">「 [オブジェクトサイズ][DevtoolsMemoryProblems101ObjectSizes]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92a14-161">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  
| **<span data-ttu-id="92a14-162">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="92a14-162">Retained size</span></span>** | <span data-ttu-id="92a14-163">同じオブジェクトセット間で保持される最大のサイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="92a14-163">Displays the maximum retained size among the same set of objects.</span></span>  <span data-ttu-id="92a14-164">オブジェクトが削除された後に解放できるメモリのサイズ \ (および依存関係がなくなります) は、保持されているサイズと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="92a14-164">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span></span>  <span data-ttu-id="92a14-165">「 [オブジェクトサイズ][DevtoolsMemoryProblems101ObjectSizes]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92a14-165">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

<span data-ttu-id="92a14-166">上のビューで合計行を展開すると、すべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-166">After expanding a total line in the upper view, all of the instances are displayed.</span></span>  <span data-ttu-id="92a14-167">各インスタンスについて、"浅い" と "保持されるサイズ" が対応する列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-167">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span></span>  <span data-ttu-id="92a14-168">文字の後に `@` 表示される数値は、オブジェクトの一意の ID です。ヒープスナップショットは、オブジェクトごとに比較できます。</span><span class="sxs-lookup"><span data-stu-id="92a14-168">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span></span>  

<span data-ttu-id="92a14-169">黄色のオブジェクトには JavaScript 参照と赤のオブジェクトがあり、いずれかが黄色の背景で参照される切り離されたノードであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="92a14-169">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span></span>  

**<span data-ttu-id="92a14-170">ヒーププロファイラーのさまざまなコンストラクター \ (グループ \) エントリに対応するものは何ですか?</span><span class="sxs-lookup"><span data-stu-id="92a14-170">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span></span>**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="コンストラクターグループ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   <span data-ttu-id="92a14-172">**コンストラクター** グループ</span><span class="sxs-lookup"><span data-stu-id="92a14-172">**Constructor** groups</span></span>  
:::image-end:::  

| <span data-ttu-id="92a14-173">コンストラクター \ (グループ \) エントリ</span><span class="sxs-lookup"><span data-stu-id="92a14-173">Constructor \(group\) entry</span></span> | <span data-ttu-id="92a14-174">説明</span><span class="sxs-lookup"><span data-stu-id="92a14-174">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="92a14-175">\ (グローバルプロパティ \)</span><span class="sxs-lookup"><span data-stu-id="92a14-175">\(global property\)</span></span>** | <span data-ttu-id="92a14-176">グローバルオブジェクトの間 ( `window` \) とそれが参照するオブジェクトの間の中間オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="92a14-176">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span></span>  <span data-ttu-id="92a14-177">コンストラクターを使ってオブジェクトを作成 `Person` し、グローバルオブジェクトで保持している場合、保持パスは次のようになり `[global] > \(global property\) > Person` ます。</span><span class="sxs-lookup"><span data-stu-id="92a14-177">If an object is created using a constructor `Person` and is held by a global object, the retaining path would look like `[global] > \(global property\) > Person`.</span></span>  <span data-ttu-id="92a14-178">これは、オブジェクトが互いに直接参照する場合とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="92a14-178">This contrasts with the norm, where objects directly reference each other.</span></span>  <span data-ttu-id="92a14-179">中間オブジェクトは、パフォーマンス上の理由で存在します。</span><span class="sxs-lookup"><span data-stu-id="92a14-179">Intermediate objects exist for performance reasons.</span></span>  <span data-ttu-id="92a14-180">グローバル変数は定期的に変更され、プロパティアクセスの最適化が行われます。グローバルでないオブジェクトには、グローバルには適用されません。</span><span class="sxs-lookup"><span data-stu-id="92a14-180">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span></span>  |  
| **<span data-ttu-id="92a14-181">\ (ルート \)</span><span class="sxs-lookup"><span data-stu-id="92a14-181">\(roots\)</span></span>** | <span data-ttu-id="92a14-182">保持ツリービューのルートエントリは、選択したオブジェクトを参照するエンティティです。</span><span class="sxs-lookup"><span data-stu-id="92a14-182">The root entries in the retaining tree view are the entities that have references to the selected object.</span></span>  <span data-ttu-id="92a14-183">エンジン固有の目的で、エンジンによって作成された参照をエントリにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="92a14-183">The entries may also be references created by the engine for engine-specific purposes.</span></span>  <span data-ttu-id="92a14-184">エンジンには参照オブジェクトをキャッシュしていますが、このような参照はすべて脆弱であり、実際には厳密な参照がないため、オブジェクトは収集されません。</span><span class="sxs-lookup"><span data-stu-id="92a14-184">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span></span>  |  
| **<span data-ttu-id="92a14-185">\ (休業)</span><span class="sxs-lookup"><span data-stu-id="92a14-185">\(closure\)</span></span>** | <span data-ttu-id="92a14-186">関数クロージャによってオブジェクトのグループに対する参照の数。</span><span class="sxs-lookup"><span data-stu-id="92a14-186">A count of references to a group of objects through function closures.</span></span>  |  
| **<span data-ttu-id="92a14-187">\ (配列, 文字列, 数値, regexp \)</span><span class="sxs-lookup"><span data-stu-id="92a14-187">\(array, string, number, regexp\)</span></span>** | <span data-ttu-id="92a14-188">配列、文字列、数値、または正規表現を参照するプロパティを持つオブジェクト型のリスト。</span><span class="sxs-lookup"><span data-stu-id="92a14-188">A list of object types with properties which reference an Array, String, Number, or regular expression.</span></span>  |  
| **<span data-ttu-id="92a14-189">\ (コンパイル済みコード)</span><span class="sxs-lookup"><span data-stu-id="92a14-189">\(compiled code\)</span></span>** | <span data-ttu-id="92a14-190">コンパイル済みコードに関連するすべて。</span><span class="sxs-lookup"><span data-stu-id="92a14-190">Everything related to compiled code.</span></span>  <span data-ttu-id="92a14-191">スクリプトは関数と似ていますが、本文に対応してい `<script>` ます。</span><span class="sxs-lookup"><span data-stu-id="92a14-191">Script is similar to a function, but corresponds to a `<script>` body.</span></span>  <span data-ttu-id="92a14-192">SharedFunctionInfos 機能 \ (SFI \) は、関数とコンパイルされたコードの間に位置するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="92a14-192">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span></span>  <span data-ttu-id="92a14-193">関数は通常、コンテキストを持ちますが、SFIs はできません。</span><span class="sxs-lookup"><span data-stu-id="92a14-193">Functions usually have a context, while SFIs do not.</span></span>  |  
| <span data-ttu-id="92a14-194">**HTMLDivElement**、 **HTMLAnchorElement**、 **documentfragment**など。</span><span class="sxs-lookup"><span data-stu-id="92a14-194">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span></span>  | <span data-ttu-id="92a14-195">コードで参照されている特定の型の要素またはドキュメントオブジェクトへの参照。</span><span class="sxs-lookup"><span data-stu-id="92a14-195">References to elements or document objects of a particular type referenced by your code.</span></span>  |  

<!--todo: add heap profiling summary section when available -->  

### <span data-ttu-id="92a14-196">比較ビュー</span><span class="sxs-lookup"><span data-stu-id="92a14-196">Comparison view</span></span>  

<span data-ttu-id="92a14-197">リークしたオブジェクトを検索するには、複数のスナップショットを相互に比較します。</span><span class="sxs-lookup"><span data-stu-id="92a14-197">Find leaked objects by comparing multiple snapshots to each other.</span></span>  <span data-ttu-id="92a14-198">特定のアプリケーションの操作によってリークが発生しないことを確認するには (たとえば、ドキュメントを開いて、それを閉じるときに、通常は1組の直接操作と逆方向の操作のペアである)、次のシナリオに従うことができます。</span><span class="sxs-lookup"><span data-stu-id="92a14-198">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span></span>  

1.  <span data-ttu-id="92a14-199">操作を実行する前に、ヒープスナップショットを取得します。</span><span class="sxs-lookup"><span data-stu-id="92a14-199">Take a heap snapshot before performing an operation.</span></span>  
1.  <span data-ttu-id="92a14-200">操作を実行します (リークの原因と思われる何らかの方法でページを操作します)。</span><span class="sxs-lookup"><span data-stu-id="92a14-200">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span></span>  
1.  <span data-ttu-id="92a14-201">逆の操作を実行します (反対の操作を行って、何度も繰り返します)。</span><span class="sxs-lookup"><span data-stu-id="92a14-201">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span></span>  
1.  <span data-ttu-id="92a14-202">2つ目のヒープスナップショットを取得し、そのビューを**スナップショット 1**と比較して**比較**します。</span><span class="sxs-lookup"><span data-stu-id="92a14-202">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span></span>  
    
<span data-ttu-id="92a14-203">[ **比較** ] ビューでは、2つのスナップショットの差が表示されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-203">In the **Comparison** view, the difference between two snapshots is displayed.</span></span>  <span data-ttu-id="92a14-204">合計項目を展開すると、追加または削除されたオブジェクトインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-204">When expanding a total entry, added and deleted object instances are shown.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比較ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   <span data-ttu-id="92a14-206">**比較** ビュー</span><span class="sxs-lookup"><span data-stu-id="92a14-206">**Comparison** view</span></span>  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### <span data-ttu-id="92a14-207">コンテインメントビュー</span><span class="sxs-lookup"><span data-stu-id="92a14-207">Containment view</span></span>  

<span data-ttu-id="92a14-208">**コンテインメント**ビューは、基本的には、アプリケーションのオブジェクト構造の "鳥の視点" ビューです。</span><span class="sxs-lookup"><span data-stu-id="92a14-208">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span></span>  <span data-ttu-id="92a14-209">この機能を使用すると、JavaScript オブジェクトを構成する仮想マシン \ (VM) 内部オブジェクトを監視したり、アプリケーションが非常に低レベルで使用しているメモリ量を把握したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="92a14-209">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span></span>  

| <span data-ttu-id="92a14-210">コンテインメントビューのエントリポイント</span><span class="sxs-lookup"><span data-stu-id="92a14-210">Containment view entry points</span></span> | <span data-ttu-id="92a14-211">説明</span><span class="sxs-lookup"><span data-stu-id="92a14-211">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="92a14-212">DOMWindow オブジェクト</span><span class="sxs-lookup"><span data-stu-id="92a14-212">DOMWindow objects</span></span>** | <span data-ttu-id="92a14-213">JavaScript コードのグローバルオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="92a14-213">Global objects for JavaScript code.</span></span>  |  
| **<span data-ttu-id="92a14-214">GC ルート</span><span class="sxs-lookup"><span data-stu-id="92a14-214">GC roots</span></span>** | <span data-ttu-id="92a14-215">VM のガーベジで使用される実際の GC ルート。</span><span class="sxs-lookup"><span data-stu-id="92a14-215">The actual GC roots used by the garbage of the VM.</span></span>  <span data-ttu-id="92a14-216">GC ルートは、組み込みのオブジェクトマップ、シンボルテーブル、VM スレッドスタック、コンパイルキャッシュ、ハンドルスコープ、グローバルハンドルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="92a14-216">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span></span>  |  
| **<span data-ttu-id="92a14-217">ネイティブオブジェクト</span><span class="sxs-lookup"><span data-stu-id="92a14-217">Native objects</span></span>** | <span data-ttu-id="92a14-218">ブラウザーオブジェクトは、JavaScript 仮想マシンの内部に "プッシュされました" (JavaScript VM \) で、オートメーション (DOM ノード、CSS ルールなど) を許可します。</span><span class="sxs-lookup"><span data-stu-id="92a14-218">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span></span>  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="コンテインメントビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   <span data-ttu-id="92a14-220">**コンテインメント** ビュー</span><span class="sxs-lookup"><span data-stu-id="92a14-220">**Containment** view</span></span>  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> <span data-ttu-id="92a14-221">クロージャに関するヒント。</span><span class="sxs-lookup"><span data-stu-id="92a14-221">A tip about closures.</span></span>  <span data-ttu-id="92a14-222">スナップショットのクロージャを簡単に区別できるように、関数に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a14-222">Name the functions so you are able to easily distinguish between closures in the snapshot.</span></span>  <span data-ttu-id="92a14-223">たとえば、次の例では、名前付き関数は使用されません。</span><span class="sxs-lookup"><span data-stu-id="92a14-223">For example, this example does not use named functions.</span></span>  
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
> <span data-ttu-id="92a14-224">以下のコードスニペットでは、名前付き関数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="92a14-224">The followingcode snippet uses named functions.</span></span>  
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
> :::image type="complex" source="../media/memory-problems-domleaks.msft.png" alt-text="Name functions to distinguish between closures" lightbox="../media/memory-problems-domleaks.msft.png":::
>    Name functions to distinguish between closures  
> :::image-end:::  
> -->  
> 
> > [!NOTE]
> > <span data-ttu-id="92a14-225">この例では、メモリ上でのクロージャの影響を分析するための悪を示して [ `eval` い][GlitchDevtoolsMemoryExample07] ます。</span><span class="sxs-lookup"><span data-stu-id="92a14-225">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span></span>  <span data-ttu-id="92a14-226">また、この例では、 [ヒープ割り当て][GlitchDevtoolsMemoryExample08]の記録に関する次の例を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="92a14-226">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span></span>  
> 

## <span data-ttu-id="92a14-227">色のコーディングを検索する</span><span class="sxs-lookup"><span data-stu-id="92a14-227">Look up color coding</span></span>  

<span data-ttu-id="92a14-228">オブジェクトのプロパティとプロパティ値の型が異なり、それに応じて色付けされます。</span><span class="sxs-lookup"><span data-stu-id="92a14-228">Properties and property values of objects have different types and are colored accordingly.</span></span>  <span data-ttu-id="92a14-229">各プロパティには、4つの型のいずれかが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92a14-229">Each property has one of four types.</span></span>  

| <span data-ttu-id="92a14-230">プロパティの種類</span><span class="sxs-lookup"><span data-stu-id="92a14-230">Property Type</span></span> | <span data-ttu-id="92a14-231">説明</span><span class="sxs-lookup"><span data-stu-id="92a14-231">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="92a14-232">a: プロパティ</span><span class="sxs-lookup"><span data-stu-id="92a14-232">a: property</span></span>** | <span data-ttu-id="92a14-233">名前を付けた標準プロパティ `.` 。 \ (ドット \) 演算子、または `[` `]` \ (かっこ \) 表記を使用してアクセスし `["foo bar"]` ます。</span><span class="sxs-lookup"><span data-stu-id="92a14-233">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span></span>  |  
| **<span data-ttu-id="92a14-234">0: 要素</span><span class="sxs-lookup"><span data-stu-id="92a14-234">0: element</span></span>** | <span data-ttu-id="92a14-235">`[` `]` \ (かっこ \) 表記法によってアクセスされる、数値インデックスを持つ標準プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92a14-235">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span></span>  |  
| **<span data-ttu-id="92a14-236">a: context var</span><span class="sxs-lookup"><span data-stu-id="92a14-236">a: context var</span></span>** |  <span data-ttu-id="92a14-237">関数の中で変数名によってアクセスできる関数のコンテキスト内の変数。</span><span class="sxs-lookup"><span data-stu-id="92a14-237">A variable in a function context, accessible by the variable name from inside a function closure.</span></span>  |  
| **<span data-ttu-id="92a14-238">a: システムの prop</span><span class="sxs-lookup"><span data-stu-id="92a14-238">a: system prop</span></span>** | <span data-ttu-id="92a14-239">Javascript の VM によって追加されたプロパティ。 JavaScript コードからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="92a14-239">A property added by the JavaScript VM, not accessible from JavaScript code.</span></span>  |  

<span data-ttu-id="92a14-240">として指定 `System` されているオブジェクトは、JavaScript の型に対応していません。</span><span class="sxs-lookup"><span data-stu-id="92a14-240">Objects designated as `System` do not have a corresponding JavaScript type.</span></span>  <span data-ttu-id="92a14-241">それぞれは、Javascript VM のオブジェクトシステム実装の一部です。</span><span class="sxs-lookup"><span data-stu-id="92a14-241">Each is part of the object system implementation of the Javascript VM.</span></span>  <span data-ttu-id="92a14-242">V8 は、内部オブジェクトのほとんどを、ユーザーの JS オブジェクトと同じヒープに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="92a14-242">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span></span>  <span data-ttu-id="92a14-243">そのため、これらは V8 の内部構造にすぎません。</span><span class="sxs-lookup"><span data-stu-id="92a14-243">So these are just V8 internals.</span></span>  

## <span data-ttu-id="92a14-244">特定のオブジェクトを検索する</span><span class="sxs-lookup"><span data-stu-id="92a14-244">Find a specific object</span></span>  

<span data-ttu-id="92a14-245">収集されたヒープ内のオブジェクトを検索するには、を使用 `Ctrl` + `F` してオブジェクト ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a14-245">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span></span>  

## <span data-ttu-id="92a14-246">DOM リークの発見</span><span class="sxs-lookup"><span data-stu-id="92a14-246">Uncover DOM leaks</span></span>  

<span data-ttu-id="92a14-247">ヒーププロファイラーには、ブラウザーのネイティブオブジェクトの間で双方向の依存関係 (DOM ノード、CSS ルール \)、JavaScript オブジェクトの間で双方向の依存関係を反映する機能があります。</span><span class="sxs-lookup"><span data-stu-id="92a14-247">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span></span>
<span data-ttu-id="92a14-248">これにより、デタッチした切り離された DOM サブツリーを回避して、非表示のリークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92a14-248">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span></span>  

<span data-ttu-id="92a14-249">DOM リークは想像よりも大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="92a14-249">DOM leaks may be bigger than you think.</span></span>  <span data-ttu-id="92a14-250">次の例について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="92a14-250">Consider the following sample.</span></span>  <span data-ttu-id="92a14-251">#Tree GC はいつですか?</span><span class="sxs-lookup"><span data-stu-id="92a14-251">When is the #tree GC?</span></span>  

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

<span data-ttu-id="92a14-252">は、 `#leaf` 関連する親 \ (parentNode \) への参照を保持し、 `#tree` leafRef が nullified の場合にのみ、GC の候補の下にあるツリー全体を示し `#tree` ます。</span><span class="sxs-lookup"><span data-stu-id="92a14-252">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span></span>  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM サブツリー" lightbox="../media/memory-problems-tree-gc.msft.png":::
   <span data-ttu-id="92a14-254">DOM サブツリー</span><span class="sxs-lookup"><span data-stu-id="92a14-254">DOM subtrees</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="92a14-255">例: リークしている可能性のある [DOM ノード][GlitchDevtoolsMemoryExample06] を理解し、それを検出する方法については、次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92a14-255">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span></span>  <span data-ttu-id="92a14-256">次の例では、 [DOM リークが予想よりも大きくなって][GlitchDevtoolsMemoryExample09]います。</span><span class="sxs-lookup"><span data-stu-id="92a14-256">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span></span>  

<span data-ttu-id="92a14-257">DOM のリークとメモリ分析の基礎の詳細については、「 [Microsoft Edge DevTools によるメモリリークの検出とデバッグ][GonzaloRuizdeVillaMemory] Gonzalo Ruiz de Villa」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a14-257">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span></span>  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

## <span data-ttu-id="92a14-258">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="92a14-258">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "オブジェクトサイズ-メモリの用語 |Microsoft ドキュメント"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "ツリーメモリの用語を保持するオブジェクト |Microsoft ドキュメント"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html-Microsoft Edge (Chromium) DevTools |故障"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "メモリ |スライド"  

> [!NOTE]
> <span data-ttu-id="92a14-268">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="92a14-268">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="92a14-269">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="92a14-269">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="92a14-271">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="92a14-271">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
