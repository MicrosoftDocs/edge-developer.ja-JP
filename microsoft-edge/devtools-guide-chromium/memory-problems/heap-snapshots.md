---
description: Microsoft Edge DevTools ヒープ プロファイラーを使用してヒープ スナップショットを記録し、メモリ リークを見つける方法について説明します。
title: ヒープ スナップショットを記録する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ce7a6f972bed386f96312808428bd74f1241668f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397805"
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

# <a name="how-to-record-heap-snapshots"></a><span data-ttu-id="b2bb8-104">ヒープ スナップショットを記録する方法</span><span class="sxs-lookup"><span data-stu-id="b2bb8-104">How to record heap snapshots</span></span>  

<span data-ttu-id="b2bb8-105">Microsoft Edge DevTools ヒープ プロファイラーを使用してヒープ スナップショットを記録し、メモリ リークを見つける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-105">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span></span>  

<span data-ttu-id="b2bb8-106">Microsoft Edge DevTools ヒープ プロファイラーは、ページの JavaScript オブジェクトと関連する DOM ノードによるメモリの分布を表示します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-106">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span></span>  <span data-ttu-id="b2bb8-107">JavaScript ヒープ \(JS heap\) スナップショットの取得、メモリ グラフの分析、スナップショットの比較、メモリ リークの検出に使用します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-107">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span></span>  <span data-ttu-id="b2bb8-108">[オブジェクト保持 [ツリー] に移動します][DevtoolsMemoryProblems101ObjectsRetainingTree]。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-108">Navigate to [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span></span>  

## <a name="take-a-snapshot"></a><span data-ttu-id="b2bb8-109">スナップショットを作成する</span><span class="sxs-lookup"><span data-stu-id="b2bb8-109">Take a snapshot</span></span>  

<span data-ttu-id="b2bb8-110">[メモリ] **パネルで** 、[スナップショットの取得] **を選択し**、[スタート] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-110">On the **Memory** panel, choose **Take snapshot**, then choose **Start**.</span></span>  <span data-ttu-id="b2bb8-111">`Ctrl` + `E` \(Windows, Linux\) または `Cmd` + `E` \(macOS\) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-111">You may also select `Ctrl`+`E` \(Windows, Linux\) or `Cmd`+`E` \(macOS\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="プロファイルの種類を選択する" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   <span data-ttu-id="b2bb8-113">プロファイルの種類を選択する</span><span class="sxs-lookup"><span data-stu-id="b2bb8-113">Choose profiling type</span></span>  
:::image-end:::  

<span data-ttu-id="b2bb8-114">**スナップショットは** 、最初はレンダラー プロセス メモリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-114">**Snapshots** are initially stored in the renderer process memory.</span></span>  <span data-ttu-id="b2bb8-115">スナップショットは、スナップショット アイコンを選択して表示するときに、オンデマンドで DevTools に転送されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-115">Snapshots are transferred to the DevTools on demand, when you choose on the snapshot icon to view it.</span></span>  

<span data-ttu-id="b2bb8-116">スナップショットが DevTools に読み込まれ、解析された後、スナップショット タイトルの下の番号が表示され、到達可能な JavaScript オブジェクトの合計サイズ [が表示されます][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-116">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="到達可能なオブジェクトの合計サイズ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   <span data-ttu-id="b2bb8-118">到達可能なオブジェクトの合計サイズ</span><span class="sxs-lookup"><span data-stu-id="b2bb8-118">Total size of reachable objects</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="b2bb8-119">スナップショットには、到達可能なオブジェクトだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-119">Only reachable objects are included in snapshots.</span></span>  <span data-ttu-id="b2bb8-120">また、スナップショットの取得は常にガベージ コレクションから始まります。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-120">Also, taking a snapshot always starts with a garbage collection.</span></span>  

## <a name="clear-snapshots"></a><span data-ttu-id="b2bb8-121">スナップショットのクリア</span><span class="sxs-lookup"><span data-stu-id="b2bb8-121">Clear snapshots</span></span>  

<span data-ttu-id="b2bb8-122">[ **すべてのプロファイルをクリアする** ] アイコンを選択して、スナップショット \(DevTools とレンダラー プロセスに関連付けられているメモリの両方)を削除します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-122">Choose **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="スナップショットの削除" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   <span data-ttu-id="b2bb8-124">スナップショットの削除</span><span class="sxs-lookup"><span data-stu-id="b2bb8-124">Remove snapshots</span></span>  
:::image-end:::  

<span data-ttu-id="b2bb8-125">DevTools ウィンドウを閉じると、レンダラー プロセスに関連付けられたメモリからプロファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-125">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span></span>  <span data-ttu-id="b2bb8-126">DevTools を再度開くと、以前に作成されたスナップショットすべてがスナップショットの一覧に再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-126">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span></span>  

> [!NOTE]
> <span data-ttu-id="b2bb8-127">この散布オブジェクトの例を [試し][GlitchDevtoolsMemoryExample03] 、ヒープ プロファイラーを使用してプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-127">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span></span>  <span data-ttu-id="b2bb8-128">\(object\) アイテムの割り当ての数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-128">A number of \(object\) item allocations are displayed.</span></span>  

## <a name="view-snapshots"></a><span data-ttu-id="b2bb8-129">スナップショットの表示</span><span class="sxs-lookup"><span data-stu-id="b2bb8-129">View snapshots</span></span>  

<span data-ttu-id="b2bb8-130">タスクごとに異なる視点からスナップショットを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-130">View snapshots from different perspectives for different tasks.</span></span>  

<span data-ttu-id="b2bb8-131">**概要ビューには、** コンストラクター名でグループ化されたオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-131">**Summary view** shows objects grouped by the constructor name.</span></span>  <span data-ttu-id="b2bb8-132">コンストラクター名でグループ化された型に基づいてオブジェクト \(およびメモリ使用\) を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-132">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span></span>  <span data-ttu-id="b2bb8-133">DOM リークの追跡に **特に役立ちます**。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-133">It is particularly helpful for **tracking down DOM leaks**.</span></span>

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

<span data-ttu-id="b2bb8-134">**比較ビュー**.</span><span class="sxs-lookup"><span data-stu-id="b2bb8-134">**Comparison view**.</span></span>  <span data-ttu-id="b2bb8-135">2 つのスナップショットの違いを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-135">Displays the difference between two snapshots.</span></span>  <span data-ttu-id="b2bb8-136">操作の前と後の 2 つの \(or more\) メモリ スナップショットを比較する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-136">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span></span>  <span data-ttu-id="b2bb8-137">解放されたメモリと参照カウントでデルタを検査すると、メモリ リークの有無と原因を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-137">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span></span>  

<span data-ttu-id="b2bb8-138">**Containment ビュー**.</span><span class="sxs-lookup"><span data-stu-id="b2bb8-138">**Containment view**.</span></span>  <span data-ttu-id="b2bb8-139">ヒープの内容の探索を許可します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-139">Allows exploration of heap contents.</span></span>  <span data-ttu-id="b2bb8-140">**Containment ビューは** 、オブジェクト構造のより良いビューを提供し、グローバル名前空間 \(window\) で参照されているオブジェクトを分析して、オブジェクトを保持しているオブジェクトを見つけるのに役立つ。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-140">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span></span>  <span data-ttu-id="b2bb8-141">クロージャを分析し、低レベルでオブジェクトに飛び込む場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-141">Use it to analyze closures and dive into your objects at a low level.</span></span>  

<span data-ttu-id="b2bb8-142">ビューを切り替える場合は、ビューの上部にあるセレクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-142">To switch between views, use the selector at the top of the view.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="ビューの切り替えセレクター" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   <span data-ttu-id="b2bb8-144">ビューの切り替えセレクター</span><span class="sxs-lookup"><span data-stu-id="b2bb8-144">Switch views selector</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="b2bb8-145">一部のプロパティが JavaScript ヒープに格納される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-145">Not all properties are stored on the JavaScript heap.</span></span>  <span data-ttu-id="b2bb8-146">ネイティブ コードを実行する getter を使用して実装されたプロパティはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-146">Properties implemented using getters that run native code are not captured.</span></span>  <span data-ttu-id="b2bb8-147">また、数値などの文字列以外の値はキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-147">Also, non-string values such as numbers are not captured.</span></span>  

### <a name="summary-view"></a><span data-ttu-id="b2bb8-148">概要ビュー</span><span class="sxs-lookup"><span data-stu-id="b2bb8-148">Summary view</span></span>  

<span data-ttu-id="b2bb8-149">最初は、スナップショットが [概要] ビューに開き、オブジェクトの合計が表示され、インスタンスを表示するために展開される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-149">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="概要ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   <span data-ttu-id="b2bb8-151">**概要ビュー**</span><span class="sxs-lookup"><span data-stu-id="b2bb8-151">**Summary** view</span></span>  
:::image-end:::  

<span data-ttu-id="b2bb8-152">トップ レベルのエントリは"合計" 行です。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-152">Top-level entries are "total" lines.</span></span>  

| <span data-ttu-id="b2bb8-153">トップ レベルのエントリ</span><span class="sxs-lookup"><span data-stu-id="b2bb8-153">Top-level entries</span></span> | <span data-ttu-id="b2bb8-154">説明</span><span class="sxs-lookup"><span data-stu-id="b2bb8-154">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="b2bb8-155">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="b2bb8-155">Constructor</span></span>** | <span data-ttu-id="b2bb8-156">このコンストラクターを使用して作成されたオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-156">Represents all objects created using this constructor.</span></span>  |  
| **<span data-ttu-id="b2bb8-157">距離</span><span class="sxs-lookup"><span data-stu-id="b2bb8-157">Distance</span></span>** | <span data-ttu-id="b2bb8-158">ノードの最短の単純パスを使用してルートまでの距離を表示します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-158">displays the distance to the root using the shortest simple path of nodes.</span></span>  |  
| **<span data-ttu-id="b2bb8-159">浅いサイズ</span><span class="sxs-lookup"><span data-stu-id="b2bb8-159">Shallow size</span></span>** | <span data-ttu-id="b2bb8-160">特定のコンストラクター関数によって作成されたオブジェクトの浅いサイズの合計を表示します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-160">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span></span>  <span data-ttu-id="b2bb8-161">浅いサイズは、オブジェクトが保持するメモリのサイズです (通常、配列と文字列は浅いサイズが大きくなります\)。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-161">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span></span>  <span data-ttu-id="b2bb8-162">[オブジェクトの [サイズ] に移動します][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-162">Navigate to [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  
| **<span data-ttu-id="b2bb8-163">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="b2bb8-163">Retained size</span></span>** | <span data-ttu-id="b2bb8-164">同じオブジェクト セットの中で保持される最大サイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-164">Displays the maximum retained size among the same set of objects.</span></span>  <span data-ttu-id="b2bb8-165">オブジェクトが削除された後に解放できるメモリのサイズ \(および依存が到達不能になった\) は、保持されたサイズと呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-165">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span></span>  <span data-ttu-id="b2bb8-166">[オブジェクトの [サイズ] に移動します][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-166">Navigate to [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

<span data-ttu-id="b2bb8-167">上部ビューで合計行を展開すると、すべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-167">After expanding a total line in the upper view, all of the instances are displayed.</span></span>  <span data-ttu-id="b2bb8-168">インスタンスごとに、浅いサイズと保持されたサイズが対応する列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-168">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span></span>  <span data-ttu-id="b2bb8-169">文字の後の番号はオブジェクトの一意の ID で、オブジェクトごとにヒープ スナップショット `@` を比較できます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-169">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span></span>  

<span data-ttu-id="b2bb8-170">黄色のオブジェクトは JavaScript 参照を持ち、赤いオブジェクトは、黄色の背景を持つノードから参照されるデタッチノードです。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-170">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span></span>  

**<span data-ttu-id="b2bb8-171">ヒープ プロファイラーのさまざまなコンストラクター \(group\) エントリは何に対応しますか?</span><span class="sxs-lookup"><span data-stu-id="b2bb8-171">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span></span>**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="コンストラクター グループ" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   <span data-ttu-id="b2bb8-173">**コンストラクター グループ**</span><span class="sxs-lookup"><span data-stu-id="b2bb8-173">**Constructor** groups</span></span>  
:::image-end:::  

| <span data-ttu-id="b2bb8-174">コンストラクター \(group\) エントリ</span><span class="sxs-lookup"><span data-stu-id="b2bb8-174">Constructor \(group\) entry</span></span> | <span data-ttu-id="b2bb8-175">説明</span><span class="sxs-lookup"><span data-stu-id="b2bb8-175">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="b2bb8-176">\(global property\)</span><span class="sxs-lookup"><span data-stu-id="b2bb8-176">\(global property\)</span></span>** | <span data-ttu-id="b2bb8-177">グローバル オブジェクト \(\など) とによって参照される `window` オブジェクトとの間の中間オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-177">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span></span>  <span data-ttu-id="b2bb8-178">オブジェクトがコンストラクターを使用して作成され、グローバル オブジェクトによって保持されている場合、保持パスは `Person` として表される場合があります `[global] > \(global property\) > Person` 。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-178">If an object is created using a constructor `Person` and is held by a global object, the retaining path may be represented as `[global] > \(global property\) > Person`.</span></span>  <span data-ttu-id="b2bb8-179">これは、オブジェクトが互いに直接参照する標準とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-179">This contrasts with the norm, where objects directly reference each other.</span></span>  <span data-ttu-id="b2bb8-180">パフォーマンス上の理由から、中間オブジェクトが存在します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-180">Intermediate objects exist for performance reasons.</span></span>  <span data-ttu-id="b2bb8-181">グローバルは定期的に変更され、プロパティ アクセスの最適化はグローバル 以外のオブジェクトに対して適切な処理を行います。グローバルオブジェクトには適用できません。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-181">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span></span>  |  
| **<span data-ttu-id="b2bb8-182">\(roots\)</span><span class="sxs-lookup"><span data-stu-id="b2bb8-182">\(roots\)</span></span>** | <span data-ttu-id="b2bb8-183">保持ツリー ビューのルート エントリは、選択したオブジェクトへの参照を持つエンティティです。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-183">The root entries in the retaining tree view are the entities that have references to the selected object.</span></span>  <span data-ttu-id="b2bb8-184">エントリは、エンジン固有の目的でエンジンによって作成された参照である場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-184">The entries may also be references created by the engine for engine-specific purposes.</span></span>  <span data-ttu-id="b2bb8-185">エンジンには参照オブジェクトのキャッシュがありますが、そのような参照はすべて弱く、本当に強力な参照が存在しない場合にオブジェクトが収集されるのを防ぐ必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-185">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span></span>  |  
| **<span data-ttu-id="b2bb8-186">\(closure\)</span><span class="sxs-lookup"><span data-stu-id="b2bb8-186">\(closure\)</span></span>** | <span data-ttu-id="b2bb8-187">関数クロージャを介したオブジェクトのグループへの参照の数。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-187">A count of references to a group of objects through function closures.</span></span>  |  
| **<span data-ttu-id="b2bb8-188">\(array, string, number, regexp\)</span><span class="sxs-lookup"><span data-stu-id="b2bb8-188">\(array, string, number, regexp\)</span></span>** | <span data-ttu-id="b2bb8-189">Array、String、Number、または正規表現を参照するプロパティを持つオブジェクト型のリスト。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-189">A list of object types with properties which reference an Array, String, Number, or regular expression.</span></span>  |  
| **<span data-ttu-id="b2bb8-190">\(コンパイルされたコード\)</span><span class="sxs-lookup"><span data-stu-id="b2bb8-190">\(compiled code\)</span></span>** | <span data-ttu-id="b2bb8-191">コンパイルされたコードに関連するすべて。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-191">Everything related to compiled code.</span></span>  <span data-ttu-id="b2bb8-192">スクリプトは関数に似ていますが、本文に対応 `<script>` します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-192">Script is similar to a function, but corresponds to a `<script>` body.</span></span>  <span data-ttu-id="b2bb8-193">SharedFunctionInfos \(SFI\) は、関数とコンパイル済みコードの間に存在するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-193">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span></span>  <span data-ttu-id="b2bb8-194">通常、関数にはコンテキストが含まれていますが、SFIs はコンテキストを使用できません。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-194">Functions usually have a context, while SFIs do not.</span></span>  |  
| <span data-ttu-id="b2bb8-195">**HTMLDivElement** **、HTMLAnchorElement、DocumentFragment**など。 </span><span class="sxs-lookup"><span data-stu-id="b2bb8-195">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span></span>  | <span data-ttu-id="b2bb8-196">コードによって参照される特定の型の要素またはドキュメント オブジェクトへの参照。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-196">References to elements or document objects of a particular type referenced by your code.</span></span>  |  

<!--todo: add heap profiling summary section when available -->  

### <a name="comparison-view"></a><span data-ttu-id="b2bb8-197">比較ビュー</span><span class="sxs-lookup"><span data-stu-id="b2bb8-197">Comparison view</span></span>  

<span data-ttu-id="b2bb8-198">複数のスナップショットを互いに比較して、リークされたオブジェクトを検索します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-198">Find leaked objects by comparing multiple snapshots to each other.</span></span>  <span data-ttu-id="b2bb8-199">特定のアプリケーション操作でリークが発生しない \(たとえば、通常は、ドキュメントを開いて閉じるなど、直接操作と逆方向の操作のペアを作成しない場合は、ガベージ\を残さない方が良い) を確認するには、次のシナリオに従います。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-199">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span></span>  

1.  <span data-ttu-id="b2bb8-200">操作を実行する前にヒープ スナップショットを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-200">Take a heap snapshot before performing an operation.</span></span>  
1.  <span data-ttu-id="b2bb8-201">操作を実行する \(何らかの方法でページを操作し、リークを引き起こしている可能性があります\)。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-201">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span></span>  
1.  <span data-ttu-id="b2bb8-202">逆方向の操作を実行する \(反対の操作を行い、数回繰り返す\)。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-202">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span></span>  
1.  <span data-ttu-id="b2bb8-203">2 番目のヒープ スナップショットを作成し、このヒープ スナップショットのビューを比較に変更 **し**、スナップショット **1 と比較します**。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-203">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span></span>  
    
<span data-ttu-id="b2bb8-204">比較ビュー **では** 、2 つのスナップショットの違いが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-204">In the **Comparison** view, the difference between two snapshots is displayed.</span></span>  <span data-ttu-id="b2bb8-205">合計エントリを展開すると、追加および削除されたオブジェクト インスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-205">When expanding a total entry, added and deleted object instances are shown.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比較ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   <span data-ttu-id="b2bb8-207">**比較** ビュー</span><span class="sxs-lookup"><span data-stu-id="b2bb8-207">**Comparison** view</span></span>  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### <a name="containment-view"></a><span data-ttu-id="b2bb8-208">Containment ビュー</span><span class="sxs-lookup"><span data-stu-id="b2bb8-208">Containment view</span></span>  

<span data-ttu-id="b2bb8-209">Containment **ビュー** は基本的に、アプリケーションのオブジェクト構造の "鳥の目" です。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-209">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span></span>  <span data-ttu-id="b2bb8-210">これにより、関数クロージャの内部を覗き見し、JavaScript オブジェクトを構成する仮想マシン \(VM\) 内部オブジェクトを観察し、アプリケーションが非常に低いレベルで使用するメモリの量を理解できます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-210">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span></span>  

| <span data-ttu-id="b2bb8-211">格納ビューのエントリ ポイント</span><span class="sxs-lookup"><span data-stu-id="b2bb8-211">Containment view entry points</span></span> | <span data-ttu-id="b2bb8-212">説明</span><span class="sxs-lookup"><span data-stu-id="b2bb8-212">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="b2bb8-213">DOMWindow オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b2bb8-213">DOMWindow objects</span></span>** | <span data-ttu-id="b2bb8-214">JavaScript コードのグローバル オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-214">Global objects for JavaScript code.</span></span>  |  
| **<span data-ttu-id="b2bb8-215">GC ルート</span><span class="sxs-lookup"><span data-stu-id="b2bb8-215">GC roots</span></span>** | <span data-ttu-id="b2bb8-216">VM のガベージによって使用される実際の GC ルート。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-216">The actual GC roots used by the garbage of the VM.</span></span>  <span data-ttu-id="b2bb8-217">GC ルートは、組み込みのオブジェクト マップ、シンボル テーブル、VM スレッド スタック、コンパイル キャッシュ、ハンドル スコープ、およびグローバル ハンドルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-217">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span></span>  |  
| **<span data-ttu-id="b2bb8-218">ネイティブ オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b2bb8-218">Native objects</span></span>** | <span data-ttu-id="b2bb8-219">JavaScript 仮想マシン \(JavaScript VM\) 内のブラウザー オブジェクトを "プッシュ" して、DOM ノード、CSS ルールなど、オートメーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-219">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span></span>  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="Containment ビュー" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   <span data-ttu-id="b2bb8-221">**Containment** ビュー</span><span class="sxs-lookup"><span data-stu-id="b2bb8-221">**Containment** view</span></span>  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> <span data-ttu-id="b2bb8-222">クロージャに関するヒント。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-222">A tip about closures.</span></span>  <span data-ttu-id="b2bb8-223">スナップショット内のクロージャを簡単に区別するために、関数に名前を付ける。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-223">Name the functions so you are able to easily distinguish between closures in the snapshot.</span></span>  <span data-ttu-id="b2bb8-224">たとえば、この例では名前付き関数を使用しない場合です。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-224">For example, this example does not use named functions.</span></span>  
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
> <span data-ttu-id="b2bb8-225">次のコード スニペットでは、名前付き関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-225">The followingcode snippet uses named functions.</span></span>  
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
> > <span data-ttu-id="b2bb8-226">クロージャが [メモリに与 `eval` ][GlitchDevtoolsMemoryExample07] える影響を分析するために悪い理由のこの例を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-226">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span></span>  <span data-ttu-id="b2bb8-227">この例では、ヒープ割り当ての記録を行う方法について [説明][GlitchDevtoolsMemoryExample08]します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-227">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span></span>  
> 

## <a name="look-up-color-coding"></a><span data-ttu-id="b2bb8-228">色分けを見る</span><span class="sxs-lookup"><span data-stu-id="b2bb8-228">Look up color coding</span></span>  

<span data-ttu-id="b2bb8-229">オブジェクトのプロパティとプロパティの値は、さまざまな種類を持ち、色付けされます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-229">Properties and property values of objects have different types and are colored accordingly.</span></span>  <span data-ttu-id="b2bb8-230">各プロパティには、4 つの種類の 1 つがあります。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-230">Each property has one of four types.</span></span>  

| <span data-ttu-id="b2bb8-231">プロパティの種類</span><span class="sxs-lookup"><span data-stu-id="b2bb8-231">Property Type</span></span> | <span data-ttu-id="b2bb8-232">説明</span><span class="sxs-lookup"><span data-stu-id="b2bb8-232">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="b2bb8-233">a: プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2bb8-233">a: property</span></span>** | <span data-ttu-id="b2bb8-234">\(dot\) 演算子を使用してアクセスされる名前を持つ通常のプロパティ、または `.` `[` `]` \(brackets\) 表記など `["foo bar"]` です。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-234">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span></span>  |  
| **<span data-ttu-id="b2bb8-235">0: 要素</span><span class="sxs-lookup"><span data-stu-id="b2bb8-235">0: element</span></span>** | <span data-ttu-id="b2bb8-236">\(brackets\) 表記を使用してアクセスされる、数値インデックス `[` `]` を持つ通常のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-236">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span></span>  |  
| **<span data-ttu-id="b2bb8-237">a: context var</span><span class="sxs-lookup"><span data-stu-id="b2bb8-237">a: context var</span></span>** |  <span data-ttu-id="b2bb8-238">関数のクロージャ内から変数名でアクセスできる関数コンテキスト内の変数。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-238">A variable in a function context, accessible by the variable name from inside a function closure.</span></span>  |  
| **<span data-ttu-id="b2bb8-239">a: system prop</span><span class="sxs-lookup"><span data-stu-id="b2bb8-239">a: system prop</span></span>** | <span data-ttu-id="b2bb8-240">JavaScript のコードからアクセスできない JavaScript VM によって追加されたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-240">A property added by the JavaScript VM, not accessible from JavaScript code.</span></span>  |  

<span data-ttu-id="b2bb8-241">指定されたオブジェクトには `System` 、対応する JavaScript 型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-241">Objects designated as `System` do not have a corresponding JavaScript type.</span></span>  <span data-ttu-id="b2bb8-242">それぞれは、Javascript VM のオブジェクト システム実装の一部です。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-242">Each is part of the object system implementation of the Javascript VM.</span></span>  <span data-ttu-id="b2bb8-243">V8 は、ユーザーの JS オブジェクトと同じヒープ内のほとんどの内部オブジェクトを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-243">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span></span>  <span data-ttu-id="b2bb8-244">したがって、これらは V8 の内部です。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-244">So these are just V8 internals.</span></span>  

## <a name="find-a-specific-object"></a><span data-ttu-id="b2bb8-245">特定のオブジェクトを検索する</span><span class="sxs-lookup"><span data-stu-id="b2bb8-245">Find a specific object</span></span>  

<span data-ttu-id="b2bb8-246">収集されたヒープ内のオブジェクトを見つけるには、オブジェクト ID を使用 `Ctrl` + `F` して検索して指定します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-246">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span></span>  

## <a name="uncover-dom-leaks"></a><span data-ttu-id="b2bb8-247">DOM リークを検出する</span><span class="sxs-lookup"><span data-stu-id="b2bb8-247">Uncover DOM leaks</span></span>  

<span data-ttu-id="b2bb8-248">ヒープ プロファイラーには、ブラウザー ネイティブ オブジェクト \(DOM ノード、CSS ルール\) と JavaScript オブジェクト間の双方向の依存関係を反映する機能があります。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-248">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span></span>
<span data-ttu-id="b2bb8-249">これは、切り離された DOM サブツリーが浮いているのを忘れた場合に、見えないリークが発生しているのを発見するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-249">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span></span>  

<span data-ttu-id="b2bb8-250">DOM リークは、思ったよりも大きい場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-250">DOM leaks may be bigger than you think.</span></span>  <span data-ttu-id="b2bb8-251">次のサンプルを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-251">Consider the following sample.</span></span>  <span data-ttu-id="b2bb8-252">GC の#treeですか?</span><span class="sxs-lookup"><span data-stu-id="b2bb8-252">When is the #tree GC?</span></span>  

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

<span data-ttu-id="b2bb8-253">関連する親 \(parentNode\) への参照を再帰的に保持します。 `#leaf` `#tree` したがって、leafRef が nullified の場合にのみ `#tree` 、GC の候補の下にある WHOLE ツリーになります。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-253">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span></span>  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM サブツリー" lightbox="../media/memory-problems-tree-gc.msft.png":::
   <span data-ttu-id="b2bb8-255">DOM サブツリー</span><span class="sxs-lookup"><span data-stu-id="b2bb8-255">DOM subtrees</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="b2bb8-256">例: リークしている [DOM][GlitchDevtoolsMemoryExample06] ノードのこの例を試して、リークする可能性のある場所と、それを検出する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-256">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span></span>  <span data-ttu-id="b2bb8-257">また、DOM リークが予想以上に大きいという [この例を見る場合があります][GlitchDevtoolsMemoryExample09]。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-257">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span></span>  

<span data-ttu-id="b2bb8-258">DOM リークとメモリ分析の基本について詳しくは [、Gonzalo Ruiz][GonzaloRuizdeVillaMemory] de Villa の Microsoft Edge DevTools を使用してメモリ リークの検索とデバッグを行います。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-258">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span></span>  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b2bb8-259">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="b2bb8-259">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "オブジェクトサイズ - メモリ用語|Microsoft Docs"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "ツリーを保持するオブジェクト - メモリ用語|Microsoft Docs"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html - Microsoft Edge (クロム) DevTools |Glitch"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html - Microsoft Edge (クロム) DevTools |Glitch"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "メモリ |スライド"  

> [!NOTE]
> <span data-ttu-id="b2bb8-269">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-269">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b2bb8-270">元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) つかり [、Meggin Kearney][MegginKearney] \(Technical Writer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-270">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b2bb8-272">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b2bb8-272">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
