---
description: このセクションでは、メモリ分析で使用される一般的な用語について説明し、さまざまな言語のさまざまなメモリ プロファイリング ツールに適用できます。
title: メモリの関連用語
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 58b3ecde157b1c551b6c0cd435049ce221555519
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564771"
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
   limitations under the License. -->
# <a name="memory-terminology"></a><span data-ttu-id="f5414-104">メモリの関連用語</span><span class="sxs-lookup"><span data-stu-id="f5414-104">Memory terminology</span></span>  

<span data-ttu-id="f5414-105">この記事では、メモリ分析で使用される一般的な用語について説明し、さまざまな言語のさまざまなメモリ プロファイリング ツールに適用できます。</span><span class="sxs-lookup"><span data-stu-id="f5414-105">This article describes common terms used in memory analysis, and is applicable to various memory profiling tools for different languages.</span></span>  

<span data-ttu-id="f5414-106">ここで説明する用語と用語は、メモリ パネルを [参照します][DevtoolsMemoryProblemsHeapSnapshots]。</span><span class="sxs-lookup"><span data-stu-id="f5414-106">The terms and notions described here refer to the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="f5414-107">アプリケーション、.NET、または他のJavaプロファイラーを使用した場合、この記事は更新プログラムになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5414-107">If you have ever worked with either the Java, .NET, or some other memory profiler, then this article may be a refresher.</span></span>  

## <a name="object-sizes"></a><span data-ttu-id="f5414-108">オブジェクトのサイズ</span><span class="sxs-lookup"><span data-stu-id="f5414-108">Object sizes</span></span>  

<span data-ttu-id="f5414-109">メモリは、プリミティブ型 \(数値や文字列\など) とオブジェクト \(連想配列\) を持つグラフと考えてください。</span><span class="sxs-lookup"><span data-stu-id="f5414-109">Think of memory as a graph with primitive types \(like numbers and strings\) and objects \(associative arrays\).</span></span>  <span data-ttu-id="f5414-110">次の図のような多くの相互に接続されたポイントを含むグラフとして表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5414-110">It may display as a graph with many interconnected points such as following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-thinkgraph.msft.png" alt-text="メモリの視覚的表現" lightbox="../media/memory-problems-thinkgraph.msft.png":::
   <span data-ttu-id="f5414-112">メモリの視覚的表現</span><span class="sxs-lookup"><span data-stu-id="f5414-112">Visual representation of memory</span></span>  
:::image-end:::  

<span data-ttu-id="f5414-113">オブジェクトは、次の 2 つの方法でメモリを保持できます。</span><span class="sxs-lookup"><span data-stu-id="f5414-113">An object may hold memory in two ways:</span></span>  

*   <span data-ttu-id="f5414-114">オブジェクトによって直接指定します。</span><span class="sxs-lookup"><span data-stu-id="f5414-114">Directly by the object.</span></span>  
*   <span data-ttu-id="f5414-115">暗黙的に、他のオブジェクトへの参照を保持し、ガベージ コレクターによってそれらのオブジェクトが自動的に破棄されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="f5414-115">Implicitly by holding references to other objects, and therefore preventing those objects from being automatically disposed by a garbage collector.</span></span>  

<span data-ttu-id="f5414-116">DevTools [][DevtoolsMemoryProblemsHeapSnapshots] \(Memory **\で**見つかったメモリの問題を調査するツール) のメモリ パネルを操作すると、いくつかの異なる列の情報を見ている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5414-116">When working with the [Memory][DevtoolsMemoryProblemsHeapSnapshots] panel in DevTools \(a tool for investigating memory issues found under **Memory**\), you may find yourself looking at a few different columns of information.</span></span>  <span data-ttu-id="f5414-117">目立つのは、**シャロー サイズと\*\*\*\*保持サイズですが**、これらは何を表していますか?</span><span class="sxs-lookup"><span data-stu-id="f5414-117">Two that stand out are **Shallow Size** and **Retained Size**, but what do these represent?</span></span>  

:::image type="complex" source="../media/memory-problems-shallow-retained.msft.png" alt-text="浅いサイズと保持サイズ" lightbox="../media/memory-problems-shallow-retained.msft.png":::
   <span data-ttu-id="f5414-119">浅いサイズと保持サイズ</span><span class="sxs-lookup"><span data-stu-id="f5414-119">Shallow and Retained Size</span></span>  
:::image-end:::  

### <a name="shallow-size"></a><span data-ttu-id="f5414-120">浅いサイズ</span><span class="sxs-lookup"><span data-stu-id="f5414-120">Shallow size</span></span>  

<span data-ttu-id="f5414-121">これは、オブジェクトによって保持されるメモリのサイズです。</span><span class="sxs-lookup"><span data-stu-id="f5414-121">This is the size of memory that is held by the object.</span></span>  

<span data-ttu-id="f5414-122">一般的な JavaScript オブジェクトには、説明用と即時値の格納用に予約されたメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="f5414-122">Typical JavaScript objects have some memory reserved for their description and for storing immediate values.</span></span>  <span data-ttu-id="f5414-123">通常、配列と文字列だけが大きな浅いサイズを持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5414-123">Usually, only arrays and strings are able to have a significant shallow size.</span></span>  <span data-ttu-id="f5414-124">ただし、文字列と外部配列は、多くの場合、メイン ストレージをレンダラー メモリに格納し、JavaScript ヒープ上の小さなラッパー オブジェクトのみを公開します。</span><span class="sxs-lookup"><span data-stu-id="f5414-124">However, strings and external arrays often have their main storage in renderer memory, exposing only a small wrapper object on the JavaScript heap.</span></span>  

<span data-ttu-id="f5414-125">レンダラー メモリは、検査されたページがレンダリングされるプロセスのすべてのメモリです。ページによって開始された専用ワーカーのネイティブ メモリ + JS ヒープ メモリ + JS ヒープ メモリ。</span><span class="sxs-lookup"><span data-stu-id="f5414-125">Renderer memory is all memory of the process where an inspected page is rendered: native memory + JS heap memory of the page + JS heap memory of all dedicated workers started by the page.</span></span>  <span data-ttu-id="f5414-126">それにもかかわらず、小さなオブジェクトでも、自動ガベージ コレクション プロセスによって他のオブジェクトが破棄されるのを防ぐことによって、大量のメモリを間接的に保持できます。</span><span class="sxs-lookup"><span data-stu-id="f5414-126">Nevertheless, even a small object is able to hold a large amount of memory indirectly, by preventing other objects from being disposed of by the automatic garbage collection process.</span></span>  

### <a name="retained-size"></a><span data-ttu-id="f5414-127">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="f5414-127">Retained size</span></span>  

<span data-ttu-id="f5414-128">これは、ガベージ コレクターのルートから到達不能にされた依存オブジェクトと共にオブジェクトが削除された後に解放されるメモリ **のサイズです**。</span><span class="sxs-lookup"><span data-stu-id="f5414-128">This is the size of memory that is freed once the object is deleted along with the dependent objects that were made unreachable from **Garbage Collector roots**.</span></span>  

<span data-ttu-id="f5414-129">**ガベージ コレクターのルート**は、\*\*\*\* ネイティブ コードから V8 以外の JavaScript オブジェクトへの参照を行う際に \(local または global\) で作成されるハンドルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-129">**Garbage Collector roots** are made up of **handles** that are created \(either local or global\) when making a reference from native code to a JavaScript object outside of V8.</span></span>  <span data-ttu-id="f5414-130">このようなハンドルはすべて **、GC**ルート の [スコープの処理] および [GC ルート] グローバル ハンドルのヒープ スナップショット  >  \*\*\*\*\*\*内\*\*  >  **で見つかる場合があります**。</span><span class="sxs-lookup"><span data-stu-id="f5414-130">All such handles may be found within a heap snapshot under **GC roots** > **Handle scope** and **GC roots** > **Global handles**.</span></span>  <span data-ttu-id="f5414-131">ブラウザーの実装の詳細を詳しく説明せずに、このドキュメントのハンドルを記述すると、わかりにくい場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5414-131">Describing the handles in this documentation without diving into details of the browser implementation may be confusing.</span></span>  <span data-ttu-id="f5414-132">ガベージ コレクターのルートとハンドルはどちらも、心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f5414-132">Both Garbage Collector roots and the handles are not something you need to worry about.</span></span>  

<span data-ttu-id="f5414-133">ガベージ コレクターの内部ルートは多数あるが、そのほとんどはユーザーにとって興味深くない。</span><span class="sxs-lookup"><span data-stu-id="f5414-133">There are lots of internal Garbage Collector roots, most of which are not interesting for the users.</span></span>  <span data-ttu-id="f5414-134">アプリケーションの観点から、次の種類のルートがあります。</span><span class="sxs-lookup"><span data-stu-id="f5414-134">From the applications standpoint, there are the following kinds of roots.</span></span>  

*   <span data-ttu-id="f5414-135">Window グローバル オブジェクト \(各 iframe\内)。</span><span class="sxs-lookup"><span data-stu-id="f5414-135">Window global object \(in each iframe\).</span></span>  <span data-ttu-id="f5414-136">ヒープ スナップショットでは、フィールドはウィンドウからの最短保持パス上のプロパティ参照の数 `distance` を示します。</span><span class="sxs-lookup"><span data-stu-id="f5414-136">In the heap snapshots, the `distance` field indicates the number of property references on the shortest retaining path from the window.</span></span>  
*   <span data-ttu-id="f5414-137">ドキュメント DOM ツリーは、ドキュメントを通過して到達可能なすべてのネイティブ DOM ノードで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-137">The document DOM tree, consisting of all native DOM nodes that are reachable by traversing the document.</span></span>  <span data-ttu-id="f5414-138">すべてのノードに JavaScript ラッパーが含まれますが、ノードにラッパーがある場合は、ドキュメントが有効な間、ノードは有効です。</span><span class="sxs-lookup"><span data-stu-id="f5414-138">Not all of the nodes have JavaScript wrappers, but if a node has a wrapper, the node is alive while the document is alive.</span></span>  
*   <span data-ttu-id="f5414-139">場合によっては、ソース ツールとコンソールのデバッグ\*\*\*\* コンテキスト (コンソール評価\*\*\*\* 後など) でオブジェクトが保持される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5414-139">Sometimes objects are retained by the debug context in the **Sources** tool and the **Console**, such as after Console evaluation.</span></span>  <span data-ttu-id="f5414-140">ソース ツールのデバッガーで、クリアされた **コンソール** ツールとアクティブなブレークポイントを使用してヒープ スナップショット **を作成** します。</span><span class="sxs-lookup"><span data-stu-id="f5414-140">Create heap snapshots with a cleared **Console** tool and no active breakpoints in the debugger in the **Sources** tool.</span></span>

>[!TIP]
> <span data-ttu-id="f5414-141">メモリ ツールでヒープ スナップショットを取得する[前][DevtoolsMemoryProblemsHeapSnapshots]に\*\*\*\*、コンソール ツールをクリアし、[ソース] ツールでブレークポイント**を非アクティブ**化します。</span><span class="sxs-lookup"><span data-stu-id="f5414-141">Before taking a heap snapshot in the [Memory][DevtoolsMemoryProblemsHeapSnapshots] tool, clear the **Console** tool and deactivate breakpoints in the **Sources** tool.</span></span>  <span data-ttu-id="f5414-142">コンソール ツールを **クリアするには** 、メソッドを実行 `clear()` します。</span><span class="sxs-lookup"><span data-stu-id="f5414-142">To clear the **Console** tool, run the `clear()` method.</span></span>  

<span data-ttu-id="f5414-143">メモリ グラフはルートから始まり、ブラウザーのオブジェクト、またはモジュールのオブジェクトNode.js `window` `Global` されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-143">The memory graph starts with a root, which may be the `window` object of the browser or the `Global` object of a Node.js module.</span></span>  <span data-ttu-id="f5414-144">ルート オブジェクトのガベージ コレクション方法は制御されません。</span><span class="sxs-lookup"><span data-stu-id="f5414-144">You do not control how the root object is garbage collected.</span></span>  

:::image type="complex" source="../media/memory-problems-dontcontrol.msft.png" alt-text="ルート オブジェクトのガベージ コレクション方法を制御できない。" lightbox="../media/memory-problems-dontcontrol.msft.png":::
   <span data-ttu-id="f5414-146">ルート オブジェクトのガベージ コレクション方法を制御できない。</span><span class="sxs-lookup"><span data-stu-id="f5414-146">You are not able to control how the root object is garbage collected.</span></span>  
:::image-end:::  

<span data-ttu-id="f5414-147">ルートから到達できないものは、ガベージ コレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5414-147">Whatever is not reachable from the root gets garbage collected.</span></span>  

> [!NOTE]
> <span data-ttu-id="f5414-148">[浅 [いサイズ] 列と](#shallow-size) [[保持サイズ] 列の両方](#retained-size) が、データをバイト単位で表します。</span><span class="sxs-lookup"><span data-stu-id="f5414-148">Both the [Shallow size](#shallow-size) and [Retained size](#retained-size) columns represent data in bytes.</span></span>  

## <a name="objects-retaining-tree"></a><span data-ttu-id="f5414-149">オブジェクト保持ツリー</span><span class="sxs-lookup"><span data-stu-id="f5414-149">Objects retaining tree</span></span>  

<span data-ttu-id="f5414-150">ヒープは、相互接続されたオブジェクトのネットワークです。</span><span class="sxs-lookup"><span data-stu-id="f5414-150">The heap is a network of interconnected objects.</span></span>  <span data-ttu-id="f5414-151">数学的な世界では、この構造はグラフまたは **メモリ グラフ** と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="f5414-151">In the mathematical world, this structure is called a **graph** or memory graph.</span></span>  <span data-ttu-id="f5414-152">グラフは、**エッジによって接続**されたノードから構成\*\*\*\* され、どちらもラベルが与えられる。</span><span class="sxs-lookup"><span data-stu-id="f5414-152">A graph is constructed from **nodes** connected by means of **edges**, both of which are given labels.</span></span>  

*   <span data-ttu-id="f5414-153">**ノード**\(**またはオブジェクト**\) は、ビルドに使用\*\*\*\* されたコンストラクター関数の名前を使用してラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="f5414-153">**Nodes** \(or **objects**\) are labelled using the name of the **constructor** function that was used to build them.</span></span>  
*   <span data-ttu-id="f5414-154">**エッジ** には、プロパティの名前を使用してラベルが付 **きます**。</span><span class="sxs-lookup"><span data-stu-id="f5414-154">**Edges** are labelled using the names of **properties**.</span></span>  

<span data-ttu-id="f5414-155">ヒープ [プロファイラーを使用してプロファイルを記録する方法について学習します][DevtoolsMemoryProblemsHeapSnapshots]。</span><span class="sxs-lookup"><span data-stu-id="f5414-155">Learn [how to record a profile using the Heap Profiler][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="f5414-156">次の図では、メモリ ツールのヒープ スナップショット記録の中で特に[][DevtoolsMemoryProblemsHeapSnapshots]注意点として、ガベージ コレクター ルートからの距離が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5414-156">In the following figure, some of the notable things in the Heap Snapshot recording in the [Memory][DevtoolsMemoryProblemsHeapSnapshots] tool include distance:  the distance from the Garbage Collector root.</span></span>  <span data-ttu-id="f5414-157">同じ種類のオブジェクトのほとんどすべてが同じ距離で、少数のオブジェクトが大きな距離にある場合は、調査する価値があります。</span><span class="sxs-lookup"><span data-stu-id="f5414-157">If almost all the objects of the same type are at the same distance, and a few are at a bigger distance, that is something worth investigating.</span></span>  

:::image type="complex" source="../media/memory-problems-root.msft.png" alt-text="ルートからの距離" lightbox="../media/memory-problems-root.msft.png":::
   <span data-ttu-id="f5414-159">ルートからの距離</span><span class="sxs-lookup"><span data-stu-id="f5414-159">Distance from root</span></span>  
:::image-end:::  

## <a name="dominators"></a><span data-ttu-id="f5414-160">ドミネーター</span><span class="sxs-lookup"><span data-stu-id="f5414-160">Dominators</span></span>  

<span data-ttu-id="f5414-161">ドミネーター オブジェクトは、各オブジェクトに 1 つのドミネーターを持つため、ツリー構造で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-161">Dominator objects are comprised of a tree structure because each object has exactly one dominator.</span></span>  <span data-ttu-id="f5414-162">オブジェクトのドミネーターは、そのオブジェクトが支配するオブジェクトへの直接参照を欠いている可能性があります。つまり、ドミネーターのツリーはグラフのスパニング ツリーではありません。</span><span class="sxs-lookup"><span data-stu-id="f5414-162">A dominator of an object may lack direct references to an object it dominates; that is, the tree of the dominator is not a spanning tree of the graph.</span></span>  

<span data-ttu-id="f5414-163">次の図では、次のステートメントは true です。</span><span class="sxs-lookup"><span data-stu-id="f5414-163">In the following figure, the following statement are true.</span></span>  

*   <span data-ttu-id="f5414-164">ノード 1 がノード 2 を支配する</span><span class="sxs-lookup"><span data-stu-id="f5414-164">Node 1 dominates node 2</span></span>  
*   <span data-ttu-id="f5414-165">ノード 2 がノード 3、4、6 を支配する</span><span class="sxs-lookup"><span data-stu-id="f5414-165">Node 2 dominates nodes 3, 4 and 6</span></span>  
*   <span data-ttu-id="f5414-166">ノード 3 がノード 5 を支配する</span><span class="sxs-lookup"><span data-stu-id="f5414-166">Node 3 dominates node 5</span></span>  
*   <span data-ttu-id="f5414-167">ノード 5 がノード 8 を支配する</span><span class="sxs-lookup"><span data-stu-id="f5414-167">Node 5 dominates node 8</span></span>  
*   <span data-ttu-id="f5414-168">ノード 6 がノード 7 を支配する</span><span class="sxs-lookup"><span data-stu-id="f5414-168">Node 6 dominates node 7</span></span>  

:::image type="complex" source="../media/memory-problems-dominatorsspanning.msft.png" alt-text="ドミネーター ツリー構造" lightbox="../media/memory-problems-dominatorsspanning.msft.png":::
   <span data-ttu-id="f5414-170">ドミネーター ツリー構造</span><span class="sxs-lookup"><span data-stu-id="f5414-170">Dominator tree structure</span></span>  
:::image-end:::  

<span data-ttu-id="f5414-171">次の図では、node はのドミネーターですが、ガベージ コレクターから `#3` `#10` `#7` `#10` .</span><span class="sxs-lookup"><span data-stu-id="f5414-171">In the following figure, node `#3` is the dominator of `#10`, but `#7` also exists in every simple path from Garbage Collector to `#10`.</span></span>  <span data-ttu-id="f5414-172">したがって、ルートからオブジェクト A への単純なパスに B が存在する場合、オブジェクト B はオブジェクト A のドミネーターになります。</span><span class="sxs-lookup"><span data-stu-id="f5414-172">Therefore, an object B is a dominator of an object A if B exists in every simple path from the root to the object A.</span></span>  

:::image type="complex" source="../media/memory-problems-dominators.msft.gif" alt-text="アニメーションのドミネーター図" lightbox="../media/memory-problems-dominators.msft.gif":::
   <span data-ttu-id="f5414-174">アニメーションのドミネーター図</span><span class="sxs-lookup"><span data-stu-id="f5414-174">Animated dominator illustration</span></span>  
:::image-end:::  

## <a name="v8-specifics"></a><span data-ttu-id="f5414-175">V8 の詳細</span><span class="sxs-lookup"><span data-stu-id="f5414-175">V8 specifics</span></span>  

<span data-ttu-id="f5414-176">メモリをプロファイリングする場合、ヒープ スナップショットが特定の方法で見える理由を理解すると便利です。</span><span class="sxs-lookup"><span data-stu-id="f5414-176">When profiling memory, it is helpful to understand why heap snapshots look a certain way.</span></span>  <span data-ttu-id="f5414-177">このセクションでは **、V8 JavaScript** 仮想マシン \(V8 VM または VM\) に特に対応するメモリ関連のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f5414-177">This section describes some memory-related topics specifically corresponding to the **V8 JavaScript virtual machine** \(V8 VM or VM\).</span></span>  

### <a name="javascript-object-representation"></a><span data-ttu-id="f5414-178">JavaScript オブジェクト表現</span><span class="sxs-lookup"><span data-stu-id="f5414-178">JavaScript object representation</span></span>  

<span data-ttu-id="f5414-179">プリミティブ型は次の 3 種類です。</span><span class="sxs-lookup"><span data-stu-id="f5414-179">There are three primitive types:</span></span>  

*   <span data-ttu-id="f5414-180">数値 \(たとえば `3.14159...` \)</span><span class="sxs-lookup"><span data-stu-id="f5414-180">Numbers \(for example `3.14159...`\)</span></span>  
*   <span data-ttu-id="f5414-181">Booleans \( `true` `false` または \)</span><span class="sxs-lookup"><span data-stu-id="f5414-181">Booleans \(`true` or `false`\)</span></span>  
*   <span data-ttu-id="f5414-182">文字列 \(たとえば `"Werner Heisenberg"` \)</span><span class="sxs-lookup"><span data-stu-id="f5414-182">Strings \(for example `"Werner Heisenberg"`\)</span></span>  

<span data-ttu-id="f5414-183">プリミティブは他の値を参照できないので、常にリーフノードまたは終了ノードです。</span><span class="sxs-lookup"><span data-stu-id="f5414-183">Primitives are not able to reference other values and are always leafs or terminating nodes.</span></span>  

<span data-ttu-id="f5414-184">**数値** は次のように格納できます。</span><span class="sxs-lookup"><span data-stu-id="f5414-184">**Numbers** are able to be stored as either:</span></span>  

*   <span data-ttu-id="f5414-185">小さい整数 \(**SMI**s\) と呼ばれる即時の 31 ビット整数値、または\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f5414-185">an immediate 31-bit integer values called **small integers** \(**SMI**s\), or</span></span>  
*   <span data-ttu-id="f5414-186">ヒープ番号 と呼ばれるヒープ **オブジェクト**。</span><span class="sxs-lookup"><span data-stu-id="f5414-186">heap objects, referred to as **heap numbers**.</span></span> <span data-ttu-id="f5414-187">ヒープ番号は、SMI フォームに収まらない値 (**倍**数など) を格納したり、値をボックス化する必要がある\*\*\*\* 場合 (プロパティの設定など) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-187">Heap numbers are used for storing values that do not fit into the SMI form, such as **doubles**, or when a value needs to be **boxed**, such as setting properties on it.</span></span>  

<span data-ttu-id="f5414-188">**文字列** は、次のいずれかの場所に格納できます。</span><span class="sxs-lookup"><span data-stu-id="f5414-188">**Strings** are able to be stored in either:</span></span>  

*   <span data-ttu-id="f5414-189">**VM ヒープ**、または</span><span class="sxs-lookup"><span data-stu-id="f5414-189">the **VM heap**, or</span></span>
*   <span data-ttu-id="f5414-190">レンダラー のメモリ **に外部的に**.</span><span class="sxs-lookup"><span data-stu-id="f5414-190">externally in the **memory of the renderer**.</span></span>  <span data-ttu-id="f5414-191">ラッパー **オブジェクトが** 作成され、外部ストレージにアクセスするために使用されます。たとえば、スクリプト ソースや Web から受信した他のコンテンツは VM ヒープにコピーされるのではなく、格納されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-191">A **wrapper object** is created and used for accessing external storage where, for example, script sources and other content that is received from the Web is stored, rather than copied onto the VM heap.</span></span>

<span data-ttu-id="f5414-192">新しい JavaScript オブジェクトのメモリは、専用の JavaScript ヒープ \(または VM ヒープ **\) から割り当**てられます。</span><span class="sxs-lookup"><span data-stu-id="f5414-192">Memory for new JavaScript objects is allocated from a dedicated JavaScript heap \(or **VM heap**\).</span></span>  <span data-ttu-id="f5414-193">これらのオブジェクトは V8 のガベージ コレクターによって管理されるため、少なくとも 1 つの強い参照がある限り、生き続けます。</span><span class="sxs-lookup"><span data-stu-id="f5414-193">These objects are managed by the garbage collector in V8 and therefore, stay alive as long as there is at least one strong reference to them.</span></span>  

<span data-ttu-id="f5414-194">JavaScript ヒープ内に含めなかったものはネイティブ オブジェクトと**呼ばれる。**</span><span class="sxs-lookup"><span data-stu-id="f5414-194">Anything not in the JavaScript heap is called a **native object**.</span></span>  <span data-ttu-id="f5414-195">ヒープ オブジェクトとは対照的に、ネイティブ オブジェクトは、V8 ガベージ コレクターの有効期間を通じて管理されるのではなく、JavaScript ラッパー オブジェクトを使用して JavaScript からしかアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5414-195">Native objects, in contrast to heap objects, are not managed by the V8 garbage collector throughout their lifetime, and may only be accessed from JavaScript using the JavaScript wrapper object.</span></span>  

<span data-ttu-id="f5414-196">**Cons string** は、格納された文字列と結合された文字列のペアで構成されるオブジェクトであり、連結の結果です。</span><span class="sxs-lookup"><span data-stu-id="f5414-196">**Cons string** is an object that consists of pairs of strings stored and then joined, and is a result of concatenation.</span></span>  <span data-ttu-id="f5414-197">cons 文字列の内容の **結合は** 、必要に応じてのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="f5414-197">The joining of the **cons string** contents occurs only as needed.</span></span>  <span data-ttu-id="f5414-198">たとえば、結合された文字列の部分文字列を作成する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="f5414-198">For example, when a substring of a joined string needs to be constructed.</span></span>

<span data-ttu-id="f5414-199">たとえば、連結して、連結の結果を表 `a` `b` す文字列 `(a, b)` を取得します。</span><span class="sxs-lookup"><span data-stu-id="f5414-199">For example, if you concatenate `a` and `b`, you get a string `(a, b)` which represents the result of concatenation.</span></span>  <span data-ttu-id="f5414-200">後でその結果と `d` 連結すると、別の cons 文字列 : **が取得されます** `((a, b, d)` 。</span><span class="sxs-lookup"><span data-stu-id="f5414-200">If you later concatenated `d` with that result, you get another **cons string**: `((a, b, d)`.</span></span>  

<span data-ttu-id="f5414-201">**配列** は数値キーを持つオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f5414-201">**Array** is an object with numeric keys.</span></span> <span data-ttu-id="f5414-202">**配列** は、大量のデータを格納するために V8 VM で広範囲に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-202">**Arrays** are used extensively in the V8 VM for storing large amounts of data.</span></span> <span data-ttu-id="f5414-203">辞書のようなキーと値のペアのセットは、配列によってバックアップ **されます**。</span><span class="sxs-lookup"><span data-stu-id="f5414-203">Sets of key-value pairs, like dictionaries, are backed up by **arrays**.</span></span>  

<span data-ttu-id="f5414-204">一般的な JavaScript オブジェクトは、次の 2 つの配列の種類の 1 つとして **のみ格納** されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-204">A typical JavaScript object is stored as only one of two **array** types:</span></span>  

*   <span data-ttu-id="f5414-205">名前付きプロパティ、および</span><span class="sxs-lookup"><span data-stu-id="f5414-205">named properties, and</span></span>  
*   <span data-ttu-id="f5414-206">数値要素</span><span class="sxs-lookup"><span data-stu-id="f5414-206">numeric elements</span></span>  

<span data-ttu-id="f5414-207">プロパティの数が少ない場合、プロパティは内部的に JavaScript オブジェクトに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-207">When there are a small number of properties, the properties are stored internally in the JavaScript object.</span></span>  

<span data-ttu-id="f5414-208">**Map** は、オブジェクトの種類とレイアウトの両方を記述するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f5414-208">**Map** is an object that describes both the kind of object it is and the layout.</span></span> <span data-ttu-id="f5414-209">たとえば、マップは、高速なプロパティ アクセスのために暗黙的なオブジェクト階層を [記述するために使用されます][V8FastProperties]。</span><span class="sxs-lookup"><span data-stu-id="f5414-209">For example, maps are used to describe implicit object hierarchies for [fast property access][V8FastProperties].</span></span>  

### <a name="object-groups"></a><span data-ttu-id="f5414-210">オブジェクト グループ</span><span class="sxs-lookup"><span data-stu-id="f5414-210">Object groups</span></span>  

<span data-ttu-id="f5414-211">各 **ネイティブ オブジェクト グループ** は、相互参照を保持するオブジェクトで作成されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-211">Each **native objects** group is made up of objects that hold mutual references to each other.</span></span>  <span data-ttu-id="f5414-212">たとえば、すべてのノードが相対親へのリンクを持ち、次の子と次の兄弟へのリンクを持つ DOM サブツリーが接続されたグラフを形成するとします。</span><span class="sxs-lookup"><span data-stu-id="f5414-212">Consider, for example, a DOM subtree where every node has a link to the relative parent and links to the next child and next sibling, therefore forming a connected graph.</span></span>  

> [!NOTE]
> <span data-ttu-id="f5414-213">ネイティブ オブジェクトは JavaScript ヒープでは表されません。</span><span class="sxs-lookup"><span data-stu-id="f5414-213">Native objects are not represented in the JavaScript heap.</span></span>  <span data-ttu-id="f5414-214">表現の欠如は、ネイティブ オブジェクトのサイズが 0 である理由です。</span><span class="sxs-lookup"><span data-stu-id="f5414-214">The lack of representation is why native objects have zero size.</span></span> <span data-ttu-id="f5414-215">代わりに、ラッパー オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-215">Instead, wrapper objects are created.</span></span>  

<span data-ttu-id="f5414-216">各ラッパー オブジェクトは、対応するネイティブ オブジェクトへの参照を保持し、コマンドをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="f5414-216">Each wrapper object holds a reference to the corresponding native object, for redirecting commands to it.</span></span>  <span data-ttu-id="f5414-217">次に、オブジェクト グループはラッパー オブジェクトを保持します。</span><span class="sxs-lookup"><span data-stu-id="f5414-217">In turn, an object group holds wrapper objects.</span></span>  <span data-ttu-id="f5414-218">ただし、ガベージ コレクターはラッパーが参照されなくなったオブジェクト グループを解放するのに十分なスマートな機能を持つので、コレクションできないサイクルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="f5414-218">However, this does not create an uncollectable cycle, as Garbage Collector is smart enough to release object groups whose wrappers are no longer referenced.</span></span>  <span data-ttu-id="f5414-219">ただし、1 つのラッパーを解放することを忘れた場合は、グループ全体と関連付けられたラッパーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="f5414-219">But forgetting to release a single wrapper holds the whole group and associated wrappers.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f5414-220">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="f5414-220">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: ./heap-snapshots.md "ヒープ スナップショットを記録する|Microsoft Docs"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "V8 の Fast プロパティ|V8"  

> [!NOTE]
> <span data-ttu-id="f5414-223">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="f5414-223">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f5414-224">元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) つかり [、Meggin Kearney][MegginKearney] \(Technical Writer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="f5414-224">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f5414-226">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f5414-226">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney
