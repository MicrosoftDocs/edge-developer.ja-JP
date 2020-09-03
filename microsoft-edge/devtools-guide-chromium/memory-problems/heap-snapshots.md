---
description: Microsoft Edge DevTools ヒーププロファイラーを使用してヒープスナップショットを記録し、メモリリークを検出する方法について説明します。
title: ヒープスナップショットの記録方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 15692b0258de6db66c0b58a2659348a6e849aaca
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993472"
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

# <span data-ttu-id="ec5d4-104">ヒープスナップショットの記録方法</span><span class="sxs-lookup"><span data-stu-id="ec5d4-104">How to record heap snapshots</span></span>  

<span data-ttu-id="ec5d4-105">Microsoft Edge DevTools ヒーププロファイラーを使用してヒープスナップショットを記録し、メモリリークを検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-105">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span></span>  

<span data-ttu-id="ec5d4-106">Microsoft Edge DevTools ヒーププロファイラーは、JavaScript オブジェクトとページの関連する DOM ノードによるメモリ分布を示しています。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-106">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span></span>  <span data-ttu-id="ec5d4-107">これは、JavaScript ヒープ \ (JS ヒープ) スナップショットの取得、メモリグラフの分析、スナップショットの比較、メモリリークの検出に使用します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-107">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span></span>  <span data-ttu-id="ec5d4-108">「 [オブジェクトを保持するツリー][DevtoolsMemoryProblems101ObjectsRetainingTree]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-108">See also [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span></span>  

## <span data-ttu-id="ec5d4-109">スナップショットを撮る</span><span class="sxs-lookup"><span data-stu-id="ec5d4-109">Take a snapshot</span></span>  

<span data-ttu-id="ec5d4-110">[ **メモリ** ] パネルで、[ **スナップショット**の作成] を選択し、[ **開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-110">On the **Memory** panel, choose **Take snapshot**, then click **Start**.</span></span>  <span data-ttu-id="ec5d4-111">`Ctrl` + `E` \ (Windows \) または `Cmd` + `E` \ (macOS \) を押すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-111">You may also press `Ctrl`+`E` \(Windows\) or `Cmd`+`E` \(macOS\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="プロファイルの種類の選択" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   <span data-ttu-id="ec5d4-113">プロファイルの種類の選択</span><span class="sxs-lookup"><span data-stu-id="ec5d4-113">Select profiling type</span></span>  
:::image-end:::  

<span data-ttu-id="ec5d4-114">**スナップショット** は、最初はレンダラープロセスメモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-114">**Snapshots** are initially stored in the renderer process memory.</span></span>  <span data-ttu-id="ec5d4-115">スナップショットは、スナップショットアイコンをクリックして表示すると、DevTools に転送されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-115">Snapshots are transferred to the DevTools on demand, when you click on the snapshot icon to view it.</span></span>  

<span data-ttu-id="ec5d4-116">スナップショットが DevTools に読み込まれ、解析されると、スナップショットのタイトルの下に表示される数値が表示され、 [アクセス可能な JavaScript オブジェクトの合計サイズ][DevtoolsMemoryProblems101ObjectSizes]が示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-116">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="到達可能なオブジェクトの合計サイズ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   <span data-ttu-id="ec5d4-118">到達可能なオブジェクトの合計サイズ</span><span class="sxs-lookup"><span data-stu-id="ec5d4-118">Total size of reachable objects</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="ec5d4-119">スナップショットには、到達可能なオブジェクトのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-119">Only reachable objects are included in snapshots.</span></span>  <span data-ttu-id="ec5d4-120">また、スナップショットの取得は、常にガベージコレクションで開始されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-120">Also, taking a snapshot always starts with a garbage collection.</span></span>  

## <span data-ttu-id="ec5d4-121">スナップショットをクリアする</span><span class="sxs-lookup"><span data-stu-id="ec5d4-121">Clear snapshots</span></span>  

<span data-ttu-id="ec5d4-122">[ **すべてのプロファイルをクリア** ] アイコンをクリックして、スナップショットを削除します (devtools から、およびレンダラープロセスに関連付けられているすべてのメモリの両方)。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-122">Click **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="スナップショットを削除する" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   <span data-ttu-id="ec5d4-124">スナップショットを削除する</span><span class="sxs-lookup"><span data-stu-id="ec5d4-124">Remove snapshots</span></span>  
:::image-end:::  

<span data-ttu-id="ec5d4-125">DevTools ウィンドウを閉じると、レンダラープロセスに関連するメモリからプロファイルが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-125">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span></span>  <span data-ttu-id="ec5d4-126">DevTools を再び開くと、以前に使用していたスナップショットがすべて、スナップショットの一覧に再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-126">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span></span>  

> [!NOTE]
> <span data-ttu-id="ec5d4-127">この例では、 [散在][GlitchDevtoolsMemoryExample03] しているオブジェクトの例を試して、ヒーププロファイラーを使ってそのオブジェクトをプロファイルしています。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-127">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span></span>  <span data-ttu-id="ec5d4-128">いくつかの \ (オブジェクト \) 項目の割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-128">You should see a number of \(object\) item allocations.</span></span>  

## <span data-ttu-id="ec5d4-129">スナップショットの表示</span><span class="sxs-lookup"><span data-stu-id="ec5d4-129">View snapshots</span></span>  

<span data-ttu-id="ec5d4-130">さまざまなタスクについてさまざまな視点からスナップショットを表示します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-130">View snapshots from different perspectives for different tasks.</span></span>  

<span data-ttu-id="ec5d4-131">[**概要] ビュー**は、コンストラクター名によってグループ化されたオブジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-131">**Summary view** shows objects grouped by the constructor name.</span></span>  <span data-ttu-id="ec5d4-132">このオブジェクトを使うと、コンストラクター名によってグループ化された型に基づいて、オブジェクト \ (およびメモリ使用量) を簡単に探すことができます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-132">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span></span>  <span data-ttu-id="ec5d4-133">これは、 **DOM リークを追跡**する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-133">It is particularly helpful for **tracking down DOM leaks**.</span></span>

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

<span data-ttu-id="ec5d4-134">**比較ビュー**。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-134">**Comparison view**.</span></span>  <span data-ttu-id="ec5d4-135">2つのスナップショットの差を表示します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-135">Displays the difference between two snapshots.</span></span>  <span data-ttu-id="ec5d4-136">操作の前後の2つ以上のメモリスナップショットを比較するために使います。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-136">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span></span>  <span data-ttu-id="ec5d4-137">解放されたメモリと参照カウントでデルタを調べると、メモリリークの有無と原因を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-137">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span></span>  

<span data-ttu-id="ec5d4-138">**コンテインメントビュー**。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-138">**Containment view**.</span></span>  <span data-ttu-id="ec5d4-139">ヒープの内容を調査できます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-139">Allows exploration of heap contents.</span></span>  <span data-ttu-id="ec5d4-140">**コンテインメントビュー** では、オブジェクト構造の詳細が表示され、グローバル名前空間 \ (ウィンドウ \) で参照されているオブジェクトを分析して、オブジェクトをどのように維持しているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-140">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span></span>  <span data-ttu-id="ec5d4-141">これを使って、クロージャを分析し、オブジェクトを低レベルで見ていきます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-141">Use it to analyze closures and dive into your objects at a low level.</span></span>  

<span data-ttu-id="ec5d4-142">ビューを切り替えるには、ビューの上部にあるセレクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-142">To switch between views, use the selector at the top of the view.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="ビューセレクターの切り替え" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   <span data-ttu-id="ec5d4-144">ビューセレクターの切り替え</span><span class="sxs-lookup"><span data-stu-id="ec5d4-144">Switch views selector</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="ec5d4-145">すべてのプロパティが JavaScript ヒープに保存されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-145">Not all properties are stored on the JavaScript heap.</span></span>  <span data-ttu-id="ec5d4-146">ネイティブコードを実行する getter を使って実装されたプロパティはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-146">Properties implemented using getters that run native code are not captured.</span></span>  <span data-ttu-id="ec5d4-147">また、数値などの文字列以外の値はキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-147">Also, non-string values such as numbers are not captured.</span></span>  

### <span data-ttu-id="ec5d4-148">サマリービュー</span><span class="sxs-lookup"><span data-stu-id="ec5d4-148">Summary view</span></span>  

<span data-ttu-id="ec5d4-149">最初に、スナップショットが [概要] ビューで開き、次のようにオブジェクトの合計が表示されます。これは、インスタンスを表示するために展開することができます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-149">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="サマリービュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   <span data-ttu-id="ec5d4-151">**サマリー** ビュー</span><span class="sxs-lookup"><span data-stu-id="ec5d4-151">**Summary** view</span></span>  
:::image-end:::  

<span data-ttu-id="ec5d4-152">トップレベルのエントリは、"合計" 行です。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-152">Top-level entries are "total" lines.</span></span>  

| <span data-ttu-id="ec5d4-153">トップレベルのエントリ</span><span class="sxs-lookup"><span data-stu-id="ec5d4-153">Top-level entries</span></span> | <span data-ttu-id="ec5d4-154">説明</span><span class="sxs-lookup"><span data-stu-id="ec5d4-154">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="ec5d4-155">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="ec5d4-155">Constructor</span></span>** | <span data-ttu-id="ec5d4-156">このコンストラクターを使用して作成されたすべてのオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-156">Represents all objects created using this constructor.</span></span>  |  
| **<span data-ttu-id="ec5d4-157">距離</span><span class="sxs-lookup"><span data-stu-id="ec5d4-157">Distance</span></span>** | <span data-ttu-id="ec5d4-158">ノードの最短のシンプルパスを使用してルートへの距離を表示します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-158">displays the distance to the root using the shortest simple path of nodes.</span></span>  |  
| **<span data-ttu-id="ec5d4-159">浅いサイズ</span><span class="sxs-lookup"><span data-stu-id="ec5d4-159">Shallow size</span></span>** | <span data-ttu-id="ec5d4-160">特定のコンストラクター関数で作成されたすべてのオブジェクトの浅いサイズの合計を表示します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-160">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span></span>  <span data-ttu-id="ec5d4-161">緩斜面サイズとは、オブジェクトによって保持されているメモリのサイズです (一般的には、配列と文字列の緩斜面サイズが大きくなります)。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-161">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span></span>  <span data-ttu-id="ec5d4-162">「 [オブジェクトサイズ][DevtoolsMemoryProblems101ObjectSizes]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-162">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  
| **<span data-ttu-id="ec5d4-163">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="ec5d4-163">Retained size</span></span>** | <span data-ttu-id="ec5d4-164">同じオブジェクトセット間で保持される最大のサイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-164">Displays the maximum retained size among the same set of objects.</span></span>  <span data-ttu-id="ec5d4-165">オブジェクトが削除された後に解放できるメモリのサイズ \ (および依存関係がなくなります) は、保持されているサイズと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-165">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span></span>  <span data-ttu-id="ec5d4-166">「 [オブジェクトサイズ][DevtoolsMemoryProblems101ObjectSizes]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-166">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

<span data-ttu-id="ec5d4-167">上のビューで合計行を展開すると、すべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-167">After expanding a total line in the upper view, all of the instances are displayed.</span></span>  <span data-ttu-id="ec5d4-168">各インスタンスについて、"浅い" と "保持されるサイズ" が対応する列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-168">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span></span>  <span data-ttu-id="ec5d4-169">文字の後に `@` 表示される数値は、オブジェクトの一意の ID です。ヒープスナップショットは、オブジェクトごとに比較できます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-169">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span></span>  

<span data-ttu-id="ec5d4-170">黄色のオブジェクトには JavaScript 参照と赤のオブジェクトがあり、いずれかが黄色の背景で参照される切り離されたノードであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-170">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span></span>  

**<span data-ttu-id="ec5d4-171">ヒーププロファイラーのさまざまなコンストラクター \ (グループ \) エントリに対応するものは何ですか?</span><span class="sxs-lookup"><span data-stu-id="ec5d4-171">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span></span>**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="コンストラクターグループ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   <span data-ttu-id="ec5d4-173">**コンストラクター** グループ</span><span class="sxs-lookup"><span data-stu-id="ec5d4-173">**Constructor** groups</span></span>  
:::image-end:::  

| <span data-ttu-id="ec5d4-174">コンストラクター \ (グループ \) エントリ</span><span class="sxs-lookup"><span data-stu-id="ec5d4-174">Constructor \(group\) entry</span></span> | <span data-ttu-id="ec5d4-175">説明</span><span class="sxs-lookup"><span data-stu-id="ec5d4-175">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="ec5d4-176">\ (グローバルプロパティ \)</span><span class="sxs-lookup"><span data-stu-id="ec5d4-176">\(global property\)</span></span>** | <span data-ttu-id="ec5d4-177">グローバルオブジェクトの間 ( `window` \) とそれが参照するオブジェクトの間の中間オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-177">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span></span>  <span data-ttu-id="ec5d4-178">コンストラクターを使ってオブジェクトを作成 `Person` し、グローバルオブジェクトで保持している場合、保持パスは次のようになり `[global] > \(global property\) > Person` ます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-178">If an object is created using a constructor `Person` and is held by a global object, the retaining path would look like `[global] > \(global property\) > Person`.</span></span>  <span data-ttu-id="ec5d4-179">これは、オブジェクトが互いに直接参照する場合とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-179">This contrasts with the norm, where objects directly reference each other.</span></span>  <span data-ttu-id="ec5d4-180">中間オブジェクトは、パフォーマンス上の理由で存在します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-180">Intermediate objects exist for performance reasons.</span></span>  <span data-ttu-id="ec5d4-181">グローバル変数は定期的に変更され、プロパティアクセスの最適化が行われます。グローバルでないオブジェクトには、グローバルには適用されません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-181">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span></span>  |  
| **<span data-ttu-id="ec5d4-182">\ (ルート \)</span><span class="sxs-lookup"><span data-stu-id="ec5d4-182">\(roots\)</span></span>** | <span data-ttu-id="ec5d4-183">保持ツリービューのルートエントリは、選択したオブジェクトを参照するエンティティです。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-183">The root entries in the retaining tree view are the entities that have references to the selected object.</span></span>  <span data-ttu-id="ec5d4-184">エンジン固有の目的で、エンジンによって作成された参照をエントリにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-184">The entries may also be references created by the engine for engine-specific purposes.</span></span>  <span data-ttu-id="ec5d4-185">エンジンには参照オブジェクトをキャッシュしていますが、このような参照はすべて脆弱であり、実際には厳密な参照がないため、オブジェクトは収集されません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-185">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span></span>  |  
| **<span data-ttu-id="ec5d4-186">\ (休業)</span><span class="sxs-lookup"><span data-stu-id="ec5d4-186">\(closure\)</span></span>** | <span data-ttu-id="ec5d4-187">関数クロージャによってオブジェクトのグループに対する参照の数。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-187">A count of references to a group of objects through function closures.</span></span>  |  
| **<span data-ttu-id="ec5d4-188">\ (配列, 文字列, 数値, regexp \)</span><span class="sxs-lookup"><span data-stu-id="ec5d4-188">\(array, string, number, regexp\)</span></span>** | <span data-ttu-id="ec5d4-189">配列、文字列、数値、または正規表現を参照するプロパティを持つオブジェクト型のリスト。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-189">A list of object types with properties which reference an Array, String, Number, or regular expression.</span></span>  |  
| **<span data-ttu-id="ec5d4-190">\ (コンパイル済みコード)</span><span class="sxs-lookup"><span data-stu-id="ec5d4-190">\(compiled code\)</span></span>** | <span data-ttu-id="ec5d4-191">コンパイル済みコードに関連するすべて。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-191">Everything related to compiled code.</span></span>  <span data-ttu-id="ec5d4-192">スクリプトは関数と似ていますが、本文に対応してい `<script>` ます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-192">Script is similar to a function, but corresponds to a `<script>` body.</span></span>  <span data-ttu-id="ec5d4-193">SharedFunctionInfos 機能 \ (SFI \) は、関数とコンパイルされたコードの間に位置するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-193">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span></span>  <span data-ttu-id="ec5d4-194">関数は通常、コンテキストを持ちますが、SFIs はできません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-194">Functions usually have a context, while SFIs do not.</span></span>  |  
| <span data-ttu-id="ec5d4-195">**HTMLDivElement**、 **HTMLAnchorElement**、 **documentfragment**など。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-195">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span></span>  | <span data-ttu-id="ec5d4-196">コードで参照されている特定の型の要素またはドキュメントオブジェクトへの参照。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-196">References to elements or document objects of a particular type referenced by your code.</span></span>  |  

<!--todo: add heap profiling summary section when available -->  

### <span data-ttu-id="ec5d4-197">比較ビュー</span><span class="sxs-lookup"><span data-stu-id="ec5d4-197">Comparison view</span></span>  

<span data-ttu-id="ec5d4-198">リークしたオブジェクトを検索するには、複数のスナップショットを相互に比較します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-198">Find leaked objects by comparing multiple snapshots to each other.</span></span>  <span data-ttu-id="ec5d4-199">特定のアプリケーションの操作によってリークが発生しないことを確認するには (たとえば、ドキュメントを開いて、それを閉じるときに、通常は1組の直接操作と逆方向の操作のペアである)、次のシナリオに従うことができます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-199">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span></span>  

1.  <span data-ttu-id="ec5d4-200">操作を実行する前に、ヒープスナップショットを取得します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-200">Take a heap snapshot before performing an operation.</span></span>  
1.  <span data-ttu-id="ec5d4-201">操作を実行します (リークの原因と思われる何らかの方法でページを操作します)。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-201">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span></span>  
1.  <span data-ttu-id="ec5d4-202">逆の操作を実行します (反対の操作を行って、何度も繰り返します)。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-202">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span></span>  
1.  <span data-ttu-id="ec5d4-203">2つ目のヒープスナップショットを取得し、そのビューを**スナップショット 1**と比較して**比較**します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-203">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span></span>  
    
<span data-ttu-id="ec5d4-204">[ **比較** ] ビューでは、2つのスナップショットの差が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-204">In the **Comparison** view, the difference between two snapshots is displayed.</span></span>  <span data-ttu-id="ec5d4-205">合計項目を展開すると、追加または削除されたオブジェクトインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-205">When expanding a total entry, added and deleted object instances are shown.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比較ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   <span data-ttu-id="ec5d4-207">**比較** ビュー</span><span class="sxs-lookup"><span data-stu-id="ec5d4-207">**Comparison** view</span></span>  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### <span data-ttu-id="ec5d4-208">コンテインメントビュー</span><span class="sxs-lookup"><span data-stu-id="ec5d4-208">Containment view</span></span>  

<span data-ttu-id="ec5d4-209">**コンテインメント**ビューは、基本的には、アプリケーションのオブジェクト構造の "鳥の視点" ビューです。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-209">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span></span>  <span data-ttu-id="ec5d4-210">この機能を使用すると、JavaScript オブジェクトを構成する仮想マシン \ (VM) 内部オブジェクトを監視したり、アプリケーションが非常に低レベルで使用しているメモリ量を把握したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-210">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span></span>  

| <span data-ttu-id="ec5d4-211">コンテインメントビューのエントリポイント</span><span class="sxs-lookup"><span data-stu-id="ec5d4-211">Containment view entry points</span></span> | <span data-ttu-id="ec5d4-212">説明</span><span class="sxs-lookup"><span data-stu-id="ec5d4-212">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="ec5d4-213">DOMWindow オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ec5d4-213">DOMWindow objects</span></span>** | <span data-ttu-id="ec5d4-214">JavaScript コードのグローバルオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-214">Global objects for JavaScript code.</span></span>  |  
| **<span data-ttu-id="ec5d4-215">GC ルート</span><span class="sxs-lookup"><span data-stu-id="ec5d4-215">GC roots</span></span>** | <span data-ttu-id="ec5d4-216">VM のガーベジで使用される実際の GC ルート。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-216">The actual GC roots used by the garbage of the VM.</span></span>  <span data-ttu-id="ec5d4-217">GC ルートは、組み込みのオブジェクトマップ、シンボルテーブル、VM スレッドスタック、コンパイルキャッシュ、ハンドルスコープ、グローバルハンドルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-217">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span></span>  |  
| **<span data-ttu-id="ec5d4-218">ネイティブオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ec5d4-218">Native objects</span></span>** | <span data-ttu-id="ec5d4-219">ブラウザーオブジェクトは、JavaScript 仮想マシンの内部に "プッシュされました" (JavaScript VM \) で、オートメーション (DOM ノード、CSS ルールなど) を許可します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-219">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span></span>  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="コンテインメントビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   <span data-ttu-id="ec5d4-221">**コンテインメント** ビュー</span><span class="sxs-lookup"><span data-stu-id="ec5d4-221">**Containment** view</span></span>  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> <span data-ttu-id="ec5d4-222">クロージャに関するヒント。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-222">A tip about closures.</span></span>  <span data-ttu-id="ec5d4-223">スナップショットのクロージャを簡単に区別できるように、関数に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-223">Name the functions so you are able to easily distinguish between closures in the snapshot.</span></span>  <span data-ttu-id="ec5d4-224">たとえば、次の例では、名前付き関数は使用されません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-224">For example, this example does not use named functions.</span></span>  
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
> <span data-ttu-id="ec5d4-225">以下のコードスニペットでは、名前付き関数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-225">The followingcode snippet uses named functions.</span></span>  
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
> > <span data-ttu-id="ec5d4-226">この例では、メモリ上でのクロージャの影響を分析するための悪を示して [ `eval` い][GlitchDevtoolsMemoryExample07] ます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-226">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span></span>  <span data-ttu-id="ec5d4-227">また、この例では、 [ヒープ割り当て][GlitchDevtoolsMemoryExample08]の記録に関する次の例を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-227">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span></span>  
> 

## <span data-ttu-id="ec5d4-228">色のコーディングを検索する</span><span class="sxs-lookup"><span data-stu-id="ec5d4-228">Look up color coding</span></span>  

<span data-ttu-id="ec5d4-229">オブジェクトのプロパティとプロパティ値の型が異なり、それに応じて色付けされます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-229">Properties and property values of objects have different types and are colored accordingly.</span></span>  <span data-ttu-id="ec5d4-230">各プロパティには、4つの型のいずれかが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-230">Each property has one of four types.</span></span>  

| <span data-ttu-id="ec5d4-231">プロパティの種類</span><span class="sxs-lookup"><span data-stu-id="ec5d4-231">Property Type</span></span> | <span data-ttu-id="ec5d4-232">説明</span><span class="sxs-lookup"><span data-stu-id="ec5d4-232">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="ec5d4-233">a: プロパティ</span><span class="sxs-lookup"><span data-stu-id="ec5d4-233">a: property</span></span>** | <span data-ttu-id="ec5d4-234">名前を付けた標準プロパティ `.` 。 \ (ドット \) 演算子、または `[` `]` \ (かっこ \) 表記を使用してアクセスし `["foo bar"]` ます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-234">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span></span>  |  
| **<span data-ttu-id="ec5d4-235">0: 要素</span><span class="sxs-lookup"><span data-stu-id="ec5d4-235">0: element</span></span>** | <span data-ttu-id="ec5d4-236">`[` `]` \ (かっこ \) 表記法によってアクセスされる、数値インデックスを持つ標準プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-236">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span></span>  |  
| **<span data-ttu-id="ec5d4-237">a: context var</span><span class="sxs-lookup"><span data-stu-id="ec5d4-237">a: context var</span></span>** |  <span data-ttu-id="ec5d4-238">関数の中で変数名によってアクセスできる関数のコンテキスト内の変数。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-238">A variable in a function context, accessible by the variable name from inside a function closure.</span></span>  |  
| **<span data-ttu-id="ec5d4-239">a: システムの prop</span><span class="sxs-lookup"><span data-stu-id="ec5d4-239">a: system prop</span></span>** | <span data-ttu-id="ec5d4-240">Javascript の VM によって追加されたプロパティ。 JavaScript コードからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-240">A property added by the JavaScript VM, not accessible from JavaScript code.</span></span>  |  

<span data-ttu-id="ec5d4-241">として指定 `System` されているオブジェクトは、JavaScript の型に対応していません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-241">Objects designated as `System` do not have a corresponding JavaScript type.</span></span>  <span data-ttu-id="ec5d4-242">それぞれは、Javascript VM のオブジェクトシステム実装の一部です。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-242">Each is part of the object system implementation of the Javascript VM.</span></span>  <span data-ttu-id="ec5d4-243">V8 は、内部オブジェクトのほとんどを、ユーザーの JS オブジェクトと同じヒープに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-243">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span></span>  <span data-ttu-id="ec5d4-244">そのため、これらは V8 の内部構造にすぎません。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-244">So these are just V8 internals.</span></span>  

## <span data-ttu-id="ec5d4-245">特定のオブジェクトを検索する</span><span class="sxs-lookup"><span data-stu-id="ec5d4-245">Find a specific object</span></span>  

<span data-ttu-id="ec5d4-246">収集されたヒープ内のオブジェクトを検索するには、を使用 `Ctrl` + `F` してオブジェクト ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-246">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span></span>  

## <span data-ttu-id="ec5d4-247">DOM リークの発見</span><span class="sxs-lookup"><span data-stu-id="ec5d4-247">Uncover DOM leaks</span></span>  

<span data-ttu-id="ec5d4-248">ヒーププロファイラーには、ブラウザーのネイティブオブジェクトの間で双方向の依存関係 (DOM ノード、CSS ルール \)、JavaScript オブジェクトの間で双方向の依存関係を反映する機能があります。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-248">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span></span>
<span data-ttu-id="ec5d4-249">これにより、デタッチした切り離された DOM サブツリーを回避して、非表示のリークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-249">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span></span>  

<span data-ttu-id="ec5d4-250">DOM リークは想像よりも大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-250">DOM leaks may be bigger than you think.</span></span>  <span data-ttu-id="ec5d4-251">次の例について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-251">Consider the following sample.</span></span>  <span data-ttu-id="ec5d4-252">#Tree GC はいつですか?</span><span class="sxs-lookup"><span data-stu-id="ec5d4-252">When is the #tree GC?</span></span>  

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

<span data-ttu-id="ec5d4-253">は、 `#leaf` 関連する親 \ (parentNode \) への参照を保持し、 `#tree` leafRef が nullified の場合にのみ、GC の候補の下にあるツリー全体を示し `#tree` ます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-253">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span></span>  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM サブツリー" lightbox="../media/memory-problems-tree-gc.msft.png":::
   <span data-ttu-id="ec5d4-255">DOM サブツリー</span><span class="sxs-lookup"><span data-stu-id="ec5d4-255">DOM subtrees</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="ec5d4-256">例: リークしている可能性のある [DOM ノード][GlitchDevtoolsMemoryExample06] を理解し、それを検出する方法については、次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-256">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span></span>  <span data-ttu-id="ec5d4-257">次の例では、 [DOM リークが予想よりも大きくなって][GlitchDevtoolsMemoryExample09]います。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-257">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span></span>  

<span data-ttu-id="ec5d4-258">DOM のリークとメモリ分析の基礎の詳細については、「 [Microsoft Edge DevTools によるメモリリークの検出とデバッグ][GonzaloRuizdeVillaMemory] Gonzalo Ruiz de Villa」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-258">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span></span>  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

## <span data-ttu-id="ec5d4-259">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="ec5d4-259">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="ec5d4-269">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-269">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ec5d4-270">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-270">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ec5d4-272">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ec5d4-272">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
