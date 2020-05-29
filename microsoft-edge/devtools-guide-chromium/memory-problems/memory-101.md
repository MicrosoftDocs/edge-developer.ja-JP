---
title: メモリの用語
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e3373cf1475ec0eeaabcebf1a7f49505c7a3c1bb
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611728"
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





# <span data-ttu-id="dc5fa-103">メモリの用語</span><span class="sxs-lookup"><span data-stu-id="dc5fa-103">Memory Terminology</span></span>   



<span data-ttu-id="dc5fa-104">このセクションでは、メモリ分析で使われる一般的な用語について説明します。また、さまざまな言語向けのさまざまなメモリプロファイリングツールにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-104">This section describes common terms used in memory analysis, and is applicable to a variety of memory profiling tools for different languages.</span></span>  

<span data-ttu-id="dc5fa-105">ここで説明する用語と意見は、「[メモリパネル][DevtoolsMemoryProblemsHeapSnapshots]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-105">The terms and notions described here refer to the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="dc5fa-106">Java、.NET、または他のメモリプロファイラーのいずれかを使用したことがある場合は、これはリフレッシャーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-106">If you have ever worked with either the Java, .NET, or some other memory profiler, then this may be a refresher.</span></span>  

## <span data-ttu-id="dc5fa-107">オブジェクトサイズ</span><span class="sxs-lookup"><span data-stu-id="dc5fa-107">Object sizes</span></span>  

<span data-ttu-id="dc5fa-108">メモリは、プリミティブ型 \ (数値と文字列 \) とオブジェクト \ (連想配列) でのグラフと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-108">Think of memory as a graph with primitive types \(like numbers and strings\) and objects \(associative arrays\).</span></span>  <span data-ttu-id="dc5fa-109">視覚的には、次のように相互に接続された複数の点でグラフとして表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-109">It might visually be represented as a graph with a number of interconnected points as follows:</span></span>  

> ##### <span data-ttu-id="dc5fa-110">図 1</span><span class="sxs-lookup"><span data-stu-id="dc5fa-110">Figure 1</span></span>  
> <span data-ttu-id="dc5fa-111">メモリの視覚的表現</span><span class="sxs-lookup"><span data-stu-id="dc5fa-111">Visual representation of memory</span></span>  
>![メモリの視覚的表現][ImageThinkGraph]  

<span data-ttu-id="dc5fa-113">オブジェクトには次の2つの方法でメモリを保持できます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-113">An object may hold memory in two ways:</span></span>  

*   <span data-ttu-id="dc5fa-114">オブジェクトを直接選びます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-114">Directly by the object.</span></span>  
*   <span data-ttu-id="dc5fa-115">他**のオブジェクト**への参照を保持することによって暗黙的に、ガベージコレクターによってそれらのオブジェクトが自動的に破棄されることを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-115">Implicitly by holding references to other objects, and therefore preventing those objects from being automatically disposed by a garbage collector \(**GC** for short\).</span></span>  

<span data-ttu-id="dc5fa-116">DevTools で[メモリパネル][DevtoolsMemoryProblemsHeapSnapshots]を操作しているとき ("メモリ" の下にあるメモリの問題を調査するツール)、いくつかの情報の列が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-116">When working with the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots] in DevTools \(a tool for investigating memory issues found under "Memory"\), you may find yourself looking at a few different columns of information.</span></span>  <span data-ttu-id="dc5fa-117">目立たない2つの**サイズは浅いサイズ**で、保持されている**サイズ**ですが、これらは何を表しますか?</span><span class="sxs-lookup"><span data-stu-id="dc5fa-117">Two that stand out are **Shallow Size** and **Retained Size**, but what do these represent?</span></span>  

> ##### <span data-ttu-id="dc5fa-118">図 2</span><span class="sxs-lookup"><span data-stu-id="dc5fa-118">Figure 2</span></span>  
> <span data-ttu-id="dc5fa-119">浅いサイズと保持サイズ</span><span class="sxs-lookup"><span data-stu-id="dc5fa-119">Shallow and Retained Size</span></span>  
>![浅いサイズと保持サイズ][ImageShallowRetained]  

### <span data-ttu-id="dc5fa-121">浅いサイズ</span><span class="sxs-lookup"><span data-stu-id="dc5fa-121">Shallow size</span></span>  

<span data-ttu-id="dc5fa-122">これは、オブジェクトによって保持されているメモリのサイズです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-122">This is the size of memory that is held by the object.</span></span>  

<span data-ttu-id="dc5fa-123">一般的な JavaScript オブジェクトには、説明用に予約されたメモリ、および即時値を格納するためのメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-123">Typical JavaScript objects have some memory reserved for their description and for storing immediate values.</span></span>  <span data-ttu-id="dc5fa-124">通常、非常に浅いサイズを持つことができるのは、配列と文字列のみです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-124">Usually, only arrays and strings are able to have a significant shallow size.</span></span>  <span data-ttu-id="dc5fa-125">ただし、文字列と外部配列には、多くの場合、レンダラーメモリ内にメインストレージがあり、JavaScript ヒープの小さなラッパーオブジェクトのみが公開されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-125">However, strings and external arrays often have their main storage in renderer memory, exposing only a small wrapper object on the JavaScript heap.</span></span>  

<span data-ttu-id="dc5fa-126">レンダラーメモリは、検査されたページがレンダリングされるプロセスのすべてのメモリです。このページで開始されるすべての専用ワーカーの、ネイティブメモリ + JS ヒープメモリ。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-126">Renderer memory is all memory of the process where an inspected page is rendered: native memory + JS heap memory of the page + JS heap memory of all dedicated workers started by the page.</span></span>  <span data-ttu-id="dc5fa-127">ただし、小さいオブジェクトは、他のオブジェクトが自動ガベージコレクションプロセスによって破棄されないようにすることで、大量のメモリを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-127">Nevertheless, even a small object is able to hold a large amount of memory indirectly, by preventing other objects from being disposed of by the automatic garbage collection process.</span></span>  

### <span data-ttu-id="dc5fa-128">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="dc5fa-128">Retained size</span></span>  

<span data-ttu-id="dc5fa-129">これは、オブジェクトが削除された後に、**ガベージコレクタールート**\ (GC ルート) から到達不能になった従属オブジェクトと共に、解放されるメモリのサイズです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-129">This is the size of memory that is freed once the object is deleted along with the dependent objects that were made unreachable from **Garbage Collector roots** \(GC roots\) .</span></span>  

<span data-ttu-id="dc5fa-130">**ガベージコレクターのルート**\ (GC ルート \) は、ネイティブコードから V8 の外部の JavaScript オブジェクトへの参照を作成するときに、(ローカルまたはグローバル \ のどちらかに) 作成された**ハンドル**で構成されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-130">**Garbage Collector roots** \(GC roots\) are made up of **handles** that are created \(either local or global\) when making a reference from native code to a JavaScript object outside of V8.</span></span>  <span data-ttu-id="dc5fa-131">このようなすべてのハンドルは、 **gc ルート**の  >  **スコープ**と**gc ルート**の  >  **グローバルハンドル**で、ヒープスナップショット内に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-131">All such handles may be found within a heap snapshot under **GC roots** > **Handle scope** and **GC roots** > **Global handles**.</span></span>  <span data-ttu-id="dc5fa-132">このドキュメントでは、ブラウザーの実装の詳細について詳しく説明していませんが、混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-132">Describing the handles in this documentation without diving into details of the browser implementation may be confusing.</span></span>  <span data-ttu-id="dc5fa-133">ガベージコレクター (GC) のルートとハンドルはどちらも、気にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-133">Both Garbage Collector (GC) roots and the handles are not something you need to worry about.</span></span>  

<span data-ttu-id="dc5fa-134">多くの内部 GC ルートがあり、そのほとんどがユーザーにとって興味を持ちません。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-134">There are lots of internal GC roots, most of which are not interesting for the users.</span></span>  <span data-ttu-id="dc5fa-135">アプリケーションの観点から見ると、次の種類のルートがあります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-135">From the applications standpoint there are following kinds of roots.</span></span>  

*   <span data-ttu-id="dc5fa-136">Window グローバルオブジェクト \ (各 iframe 内)</span><span class="sxs-lookup"><span data-stu-id="dc5fa-136">Window global object \(in each iframe\).</span></span>  <span data-ttu-id="dc5fa-137">ヒープスナップショットには距離フィールドがあります。これは、ウィンドウから最短の保持パスにあるプロパティ参照の数です。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-137">There is a distance field in the heap snapshots which is the number of property references on the shortest retaining path from the window.</span></span>  
*   <span data-ttu-id="dc5fa-138">ドキュメントを走査して到達可能なすべてのネイティブ DOM ノードで構成されるドキュメント DOM ツリー。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-138">Document DOM tree consisting of all native DOM nodes reachable by traversing the document.</span></span>  <span data-ttu-id="dc5fa-139">すべてのノードに JS ラッパーが含まれているわけではありませんが、ノードにラッパーがある場合は、ドキュメントが生きている間は生きています。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-139">Not all of the nodes may have JS wrappers but if a node has a wrapper, it is alive while the document is alive.</span></span>  
*   <span data-ttu-id="dc5fa-140">場合によっては、**ソース**パネルと**本体**(本体の評価の後など) で、デバッガーコンテキストによってオブジェクトが保持されることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-140">Sometimes objects may be retained by the debugger context in the **Sources** panel and the **Console** \(for example after Console evaluation\).</span></span>  <span data-ttu-id="dc5fa-141">クリアされた**コンソール**パネルを使ってヒープスナップショットを作成します。 [**ソース**] パネルでは、デバッガー内にアクティブなブレークポイントはありません。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-141">Create heap snapshots with a cleared **Console** panel and no active breakpoints in the debugger in the **Sources** panel.</span></span>

>[!TIP]
> <span data-ttu-id="dc5fa-142">**Console** `clear()` [メモリパネル][DevtoolsMemoryProblemsHeapSnapshots]でヒープスナップショットを取得する前に、[**ソース**] パネルでブレークポイントを実行して非アクティブ化して、コンソールパネルをクリアします。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-142">Clear the **Console** panel by running `clear()` and deactivate breakpoints in the **Sources** panel before taking a heap snapshot in the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span></span>

<span data-ttu-id="dc5fa-143">メモリグラフは、そのルートから始まります。これは、 `window` ブラウザーのオブジェクト、または `Global` ノード .js モジュールのオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-143">The memory graph starts with a root, which may be the `window` object of the browser or the `Global` object of a Node.js module.</span></span>  <span data-ttu-id="dc5fa-144">このルートオブジェクトのガベージコレクション (GCd) を制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-144">You do not control how this root object is garbage collected (GCd).</span></span>  

> ##### <span data-ttu-id="dc5fa-145">図 3</span><span class="sxs-lookup"><span data-stu-id="dc5fa-145">Figure 3</span></span>  
> <span data-ttu-id="dc5fa-146">ルートオブジェクトのガーベジコレクションの方法を制御することはできません \ (GCd)。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-146">You are not able to control how the root object is garbage collected \(GCd\).</span></span>  
>![ルートオブジェクトのガベージコレクションの方法を制御することはできません (GCd)。][ImageDontControl]  

<span data-ttu-id="dc5fa-148">ルートから到達できないものはすべて、ガーベジコレクトされた \ (GCd \) を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-148">Whatever is not reachable from the root gets garbage collected \(GCd\).</span></span>  

> [!NOTE]
> <span data-ttu-id="dc5fa-149">[[緩斜面サイズ](#shallow-size)] 列と [[保持サイズ](#retained-size)] 列は両方ともバイト単位のデータを表します。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-149">Both the [Shallow size](#shallow-size) and [Retained size](#retained-size) columns represent data in bytes.</span></span>  

## <span data-ttu-id="dc5fa-150">ツリーを保持するオブジェクト</span><span class="sxs-lookup"><span data-stu-id="dc5fa-150">Objects retaining tree</span></span>  

<span data-ttu-id="dc5fa-151">ヒープは、相互接続されたオブジェクトのネットワークです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-151">The heap is a network of interconnected objects.</span></span>  <span data-ttu-id="dc5fa-152">数学の世界では、この構造は**グラフ**またはメモリグラフと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-152">In the mathematical world, this structure is called a **graph** or memory graph.</span></span>  <span data-ttu-id="dc5fa-153">グラフは、**エッジ**によって接続された**ノード**から構成され、両方のラベルにラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-153">A graph is constructed from **nodes** connected by means of **edges**, both of which are given labels.</span></span>  

*   <span data-ttu-id="dc5fa-154">**ノード**\ (または**オブジェクト**\) は、ビルドに使用された**コンストラクター**関数の名前を使ってラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-154">**Nodes**  \(or **objects**\) are labelled using the name of the **constructor** function that was used to build them.</span></span>  
*   <span data-ttu-id="dc5fa-155">**エッジ**は、**プロパティ**の名前を使用してラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-155">**Edges**  are labelled using the names of **properties**.</span></span>  

<span data-ttu-id="dc5fa-156">[ヒーププロファイラーを使ってプロファイルを記録する方法について][DevtoolsMemoryProblemsHeapSnapshots]説明します。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-156">Learn [how to record a profile using the Heap Profiler][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="dc5fa-157">[図 4](#figure-4)の[メモリパネル][DevtoolsMemoryProblemsHeapSnapshots]でのヒープスナップショットの記録には、"距離" が含まれていることがあります。ガベージコレクター \ (GC \) ルートからの距離。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-157">Some of the eye-catching things that you may see in the Heap Snapshot recording in the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots] in [Figure 4](#figure-4) include distance: the distance from the Garbage Collector \(GC\) root.</span></span>  <span data-ttu-id="dc5fa-158">同じ型のほぼすべてのオブジェクトが同じ距離にあり、数が大きい場合は、調査の対象となります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-158">If almost all the objects of the same type are at the same distance, and a few are at a bigger distance, that is something worth investigating.</span></span>  

> ##### <span data-ttu-id="dc5fa-159">図 4</span><span class="sxs-lookup"><span data-stu-id="dc5fa-159">Figure 4</span></span>  
> <span data-ttu-id="dc5fa-160">ルートからの距離</span><span class="sxs-lookup"><span data-stu-id="dc5fa-160">Distance from root</span></span>  
>![ルートからの距離][ImageRoot]  

## <span data-ttu-id="dc5fa-162">Dominators</span><span class="sxs-lookup"><span data-stu-id="dc5fa-162">Dominators</span></span>  

<span data-ttu-id="dc5fa-163">Dominator オブジェクトは、各オブジェクトに Dominator が1つしかないため、ツリー構造で構成されています。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-163">Dominator objects are comprised of a tree structure because each object has exactly one dominator.</span></span>  <span data-ttu-id="dc5fa-164">オブジェクトの dominator には、優位なオブジェクトへの直接参照がない場合があります。つまり、dominator のツリーはグラフのスパニングツリーではありません。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-164">A dominator of an object may lack direct references to an object it dominates; that is, the tree of the dominator is not a spanning tree of the graph.</span></span>  

<span data-ttu-id="dc5fa-165">[図 5](#figure-5)の場合:</span><span class="sxs-lookup"><span data-stu-id="dc5fa-165">In [Figure 5](#figure-5):</span></span>  

*   <span data-ttu-id="dc5fa-166">ノード1の各ノード2</span><span class="sxs-lookup"><span data-stu-id="dc5fa-166">Node 1 dominates node 2</span></span>  
*   <span data-ttu-id="dc5fa-167">ノード2の各ノード3、4、6</span><span class="sxs-lookup"><span data-stu-id="dc5fa-167">Node 2 dominates nodes 3, 4 and 6</span></span>  
*   <span data-ttu-id="dc5fa-168">ノード3の各ノード5</span><span class="sxs-lookup"><span data-stu-id="dc5fa-168">Node 3 dominates node 5</span></span>  
*   <span data-ttu-id="dc5fa-169">ノード5のつのノード8</span><span class="sxs-lookup"><span data-stu-id="dc5fa-169">Node 5 dominates node 8</span></span>  
*   <span data-ttu-id="dc5fa-170">ノード6の各バージョンノード7</span><span class="sxs-lookup"><span data-stu-id="dc5fa-170">Node 6 dominates node 7</span></span>  

> ##### <span data-ttu-id="dc5fa-171">図 5</span><span class="sxs-lookup"><span data-stu-id="dc5fa-171">Figure 5</span></span>  
> <span data-ttu-id="dc5fa-172">Dominator ツリー構造</span><span class="sxs-lookup"><span data-stu-id="dc5fa-172">Dominator tree structure</span></span>  
>![Dominator ツリー構造][ImageDominatorsSpanning]  

<span data-ttu-id="dc5fa-174">[図 6](#figure-6)では、ノード `#3` は dominator です `#10` が、 `#7` ガベージコレクター \ (GC) からのすべての単純パスにも存在し `#10` ます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-174">In [Figure 6](#figure-6), node `#3` is the dominator of `#10`, but `#7` also exists in every simple path from Garbage Collector \(GC\) to `#10`.</span></span>  <span data-ttu-id="dc5fa-175">したがって、オブジェクト B は、ルートからオブジェクト A へのすべての単純パスに B が存在する場合、オブジェクト A の dominator になります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-175">Therefore, an object B is a dominator of an object A if B exists in every simple path from the root to the object A.</span></span>  

> ##### <span data-ttu-id="dc5fa-176">図 6</span><span class="sxs-lookup"><span data-stu-id="dc5fa-176">Figure 6</span></span>  
> <span data-ttu-id="dc5fa-177">アニメーション化された dominator の図</span><span class="sxs-lookup"><span data-stu-id="dc5fa-177">Animated dominator illustration</span></span>  
>![アニメーション化された dominator の図][ImageDominators]  

## <span data-ttu-id="dc5fa-179">V8 の詳細</span><span class="sxs-lookup"><span data-stu-id="dc5fa-179">V8 specifics</span></span>  

<span data-ttu-id="dc5fa-180">メモリのプロファイリングを行うときは、ヒープスナップショットが特定の方法で表示される理由を理解しておくと便利です。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-180">When profiling memory, it is helpful to understand why heap snapshots look a certain way.</span></span>  <span data-ttu-id="dc5fa-181">このセクションでは、 **V8 JavaScript 仮想マシン**\ (V8 VM または vm \) に特に対応する、いくつかのメモリ関連トピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-181">This section describes some memory-related topics specifically corresponding to the **V8 JavaScript virtual machine** \(V8 VM or VM\).</span></span>  

### <span data-ttu-id="dc5fa-182">JavaScript オブジェクトの表現</span><span class="sxs-lookup"><span data-stu-id="dc5fa-182">JavaScript object representation</span></span>  

<span data-ttu-id="dc5fa-183">プリミティブ型には次の3種類があります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-183">There are three primitive types:</span></span>  

*   <span data-ttu-id="dc5fa-184">番号 ( `3.14159...` \ など)</span><span class="sxs-lookup"><span data-stu-id="dc5fa-184">Numbers \(for example `3.14159...`\)</span></span>  
*   <span data-ttu-id="dc5fa-185">ブール型 ( `true` \ `false` )</span><span class="sxs-lookup"><span data-stu-id="dc5fa-185">Booleans \(`true` or `false`\)</span></span>  
*   <span data-ttu-id="dc5fa-186">文字列 \ (\ など `"Werner Heisenberg"` )</span><span class="sxs-lookup"><span data-stu-id="dc5fa-186">Strings \(for example `"Werner Heisenberg"`\)</span></span>  

<span data-ttu-id="dc5fa-187">プリミティブは、他の値を参照することはできません。また、常に leafs ノードまたは終了ノードを参照します。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-187">Primitives are not able to reference other values and are always leafs or terminating nodes.</span></span>  

<span data-ttu-id="dc5fa-188">**数値**は、次のいずれかの方法で保存できます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-188">**Numbers** are able to be stored as either:</span></span>  

*   <span data-ttu-id="dc5fa-189">31ビットの**小さな**整数値 (**SMI**s \)、または</span><span class="sxs-lookup"><span data-stu-id="dc5fa-189">an immediate 31-bit integer values called **small integers** \(**SMI**s\), or</span></span>  
*   <span data-ttu-id="dc5fa-190">ヒープ**値**と呼ばれるヒープオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-190">heap objects, referred to as **heap numbers**.</span></span> <span data-ttu-id="dc5fa-191">ヒープ値は、 **2 倍**などの SMI フォームに収まらない値や、プロパティの設定など、値の**ボックス**化が必要な場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-191">Heap numbers are used for storing values that do not fit into the SMI form, such as **doubles**, or when a value needs to be **boxed**, such as setting properties on it.</span></span>  

<span data-ttu-id="dc5fa-192">**文字列**は、次のいずれかの方法で保存できます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-192">**Strings** are able to be stored in either:</span></span>  

*   <span data-ttu-id="dc5fa-193">**VM ヒープ**、または</span><span class="sxs-lookup"><span data-stu-id="dc5fa-193">the **VM heap**, or</span></span>
*   <span data-ttu-id="dc5fa-194">**レンダラーのメモリ**内の外部。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-194">externally in the **memory of the renderer**.</span></span>  <span data-ttu-id="dc5fa-195">**ラッパーオブジェクト**が作成され、外部ストレージへのアクセスに使用されます。たとえば、スクリプトソースや Web から受け取ったその他のコンテンツは、VM ヒープにコピーされるのではなく格納されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-195">A **wrapper object** is created and used for accessing external storage where, for example, script sources and other content that is received from the Web is stored, rather than copied onto the VM heap.</span></span>

<span data-ttu-id="dc5fa-196">新しい JavaScript オブジェクト用のメモリは、専用の JavaScript ヒープ \ (または**VM ヒープ**\) から割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-196">Memory for new JavaScript objects is allocated from a dedicated JavaScript heap \(or **VM heap**\).</span></span>  <span data-ttu-id="dc5fa-197">これらのオブジェクトは、V8 のガベージコレクターによって管理されるため、少なくとも1つの強い参照が存在する限り、生きたままです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-197">These objects are managed by the garbage collector in V8 and therefore, stay alive as long as there is at least one strong reference to them.</span></span>  

<span data-ttu-id="dc5fa-198">JavaScript ヒープに含まれないものは、**ネイティブオブジェクト**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-198">Anything not in the JavaScript heap is called a **native object**.</span></span>  <span data-ttu-id="dc5fa-199">ヒープオブジェクトとは対照的に、ネイティブオブジェクトは、有効期間を通じて V8 ガーベジコレクターによって管理されるものではなく、javascript のラッパーオブジェクトを使って JavaScript からのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-199">Native objects, in contrast to heap objects, are not managed by the V8 garbage collector throughout their lifetime, and may only be accessed from JavaScript using the JavaScript wrapper object.</span></span>  

<span data-ttu-id="dc5fa-200">**短所文字列**は、格納された文字列のペアで構成され、その後結合されたオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-200">**Cons string** is an object that consists of pairs of strings stored and then joined, and is a result of concatenation.</span></span>  <span data-ttu-id="dc5fa-201">**短所の文字列**の内容の結合は、必要な場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-201">The joining of the **cons string** contents occurs only as needed.</span></span> <span data-ttu-id="dc5fa-202">例としては、結合された文字列の部分文字列を構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-202">An example would be when a substring of a joined string needs to be constructed.</span></span>

<span data-ttu-id="dc5fa-203">たとえば、とを連結する `a` と、 `b` 連結の結果を表す文字列を取得でき `(a, b)` ます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-203">For example, if you concatenate `a` and `b`, you get a string `(a, b)` which represents the result of concatenation.</span></span>  <span data-ttu-id="dc5fa-204">後でその結果と連結した場合は `d` 、次のような別の**文字列**が返さ `((a, b, d)` れます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-204">If you later concatenated `d` with that result, you get another **cons string**: `((a, b, d)`.</span></span>  

<span data-ttu-id="dc5fa-205">**配列**は数値キーを含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-205">**Array** is an object with numeric keys.</span></span> <span data-ttu-id="dc5fa-206">大量のデータを格納するために、V8 VM では**配列**が広く使われています。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-206">**Arrays** are used extensively in the V8 VM for storing large amounts of data.</span></span> <span data-ttu-id="dc5fa-207">ディクショナリなどのキーと値のペアのセットは、**配列**によってバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-207">Sets of key-value pairs, like dictionaries, are backed up by **arrays**.</span></span>  

<span data-ttu-id="dc5fa-208">一般的な JavaScript オブジェクトは、次の2つの**配列**型のうちの1つに限定されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-208">A typical JavaScript object is stored as only one of two **array** types:</span></span>  

*   <span data-ttu-id="dc5fa-209">"名前付きプロパティ" と "</span><span class="sxs-lookup"><span data-stu-id="dc5fa-209">named properties, and</span></span>  
*   <span data-ttu-id="dc5fa-210">数値要素</span><span class="sxs-lookup"><span data-stu-id="dc5fa-210">numeric elements</span></span>  

<span data-ttu-id="dc5fa-211">プロパティが少数の場合は、JavaScript オブジェクト内にプロパティが内部的に格納されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-211">When there are a small number of properties, the properties are stored internally in the JavaScript object.</span></span>  

<span data-ttu-id="dc5fa-212">**Map**は、オブジェクトの種類とレイアウトの両方を説明するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-212">**Map** is an object that describes both the kind of object it is and the layout.</span></span> <span data-ttu-id="dc5fa-213">たとえば、 [fast プロパティにアクセス][V8FastProperties]するための暗黙的なオブジェクト階層の記述には、maps を使います。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-213">For example, maps are used to describe implicit object hierarchies for [fast property access][V8FastProperties].</span></span>  


### <span data-ttu-id="dc5fa-214">オブジェクトグループ</span><span class="sxs-lookup"><span data-stu-id="dc5fa-214">Object groups</span></span>  

<span data-ttu-id="dc5fa-215">各**native objects**グループは、相互参照を保持するオブジェクトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-215">Each **native objects** group is made up of objects that hold mutual references to each other.</span></span>  <span data-ttu-id="dc5fa-216">たとえば、すべてのノードに関連する親へのリンクと、次の子と次の兄弟へのリンクが含まれている DOM サブツリーで、接続されたグラフを形成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-216">Consider, for example, a DOM subtree where every node has a link to the relative parent and links to the next child and next sibling, thus forming a connected graph.</span></span>  <span data-ttu-id="dc5fa-217">ネイティブオブジェクトは JavaScript ヒープでは表現されないことに注意してください。これは、ネイティブオブジェクトのサイズが0である理由です。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-217">Note that native objects are not represented in the JavaScript heap  —  that is why native objects have zero size.</span></span> <span data-ttu-id="dc5fa-218">代わりに、ラッパーオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-218">Instead, wrapper objects are created.</span></span>  

<span data-ttu-id="dc5fa-219">各ラッパーオブジェクトは、対応するネイティブオブジェクトへの参照を保持します。これには、コマンドをリダイレクトするための参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-219">Each wrapper object holds a reference to the corresponding native object, for redirecting commands to it.</span></span>  <span data-ttu-id="dc5fa-220">さらに、オブジェクトグループはラッパーオブジェクトを保持します。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-220">In turn, an object group holds wrapper objects.</span></span>  <span data-ttu-id="dc5fa-221">ただし、ガベージコレクター \ (GC \) は、ラッパーが参照されなくなったオブジェクトグループを解放するのに十分なものであるため、この方法では、回収不能なサイクルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-221">However, this does not create an uncollectable cycle, as Garbage Collector \(GC\) is smart enough to release object groups whose wrappers are no longer referenced.</span></span> <span data-ttu-id="dc5fa-222">ただし、1つのラッパーの解放を忘れると、グループ全体と関連付けられたラッパーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-222">But forgetting to release a single wrapper holds the whole group and associated wrappers.</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageThinkGraph]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-thinkgraph.msft.png "図 1: メモリの視覚的な表現"  
[ImageShallowRetained]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-shallow-retained.msft.png "図 2: 浅いサイズと保持されているサイズ"  
[ImageDontControl]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-dontcontrol.msft.png "図 3: ルートオブジェクトのガーベジコレクションの方法を制御することはできません (GCd)。"  
[ImageRoot]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-root.msft.png "図 4: ルートからの距離"  
[ImageDominatorsSpanning]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-dominatorsspanning.msft.png "図 5: Dominator ツリー構造"  
[ImageDominators]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-dominators.msft.gif "図 6: アニメーション化された dominator の図"  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: /microsoft-edge/devtools-guide-chromium/media/memory-problems/heap-snapshots "/microsoft-edge/devtools-guide-chromium/media/memory-problems"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "V8 の Fast プロパティ |V8"  

> [!NOTE]
> <span data-ttu-id="dc5fa-231">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-231">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="dc5fa-232">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101)にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-232">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="dc5fa-234">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="dc5fa-234">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney
