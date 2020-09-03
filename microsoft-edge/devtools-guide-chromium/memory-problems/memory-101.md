---
description: このセクションでは、メモリ分析で使われる一般的な用語について説明します。また、さまざまな言語向けのさまざまなメモリプロファイリングツールにも適用されます。
title: メモリの用語
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3455b05cf19f3aa5a69de5571ab3a24d5654dfe4
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992751"
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

# <span data-ttu-id="f62c2-104">メモリの用語</span><span class="sxs-lookup"><span data-stu-id="f62c2-104">Memory Terminology</span></span>  

<span data-ttu-id="f62c2-105">このセクションでは、メモリ分析で使われる一般的な用語について説明します。また、さまざまな言語向けのさまざまなメモリプロファイリングツールにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-105">This section describes common terms used in memory analysis, and is applicable to a variety of memory profiling tools for different languages.</span></span>  

<span data-ttu-id="f62c2-106">ここで説明する用語と意見は、「 [メモリパネル][DevtoolsMemoryProblemsHeapSnapshots]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f62c2-106">The terms and notions described here refer to the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="f62c2-107">Java、.NET、または他のメモリプロファイラーのいずれかを使用したことがある場合は、これはリフレッシャーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-107">If you have ever worked with either the Java, .NET, or some other memory profiler, then this may be a refresher.</span></span>  

## <span data-ttu-id="f62c2-108">オブジェクトサイズ</span><span class="sxs-lookup"><span data-stu-id="f62c2-108">Object sizes</span></span>  

<span data-ttu-id="f62c2-109">メモリは、プリミティブ型 \ (数値と文字列 \) とオブジェクト \ (連想配列) でのグラフと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-109">Think of memory as a graph with primitive types \(like numbers and strings\) and objects \(associative arrays\).</span></span>  <span data-ttu-id="f62c2-110">視覚的には、次のように相互に接続された複数の点でグラフとして表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-110">It might visually be represented as a graph with a number of interconnected points as follows:</span></span>  

:::image type="complex" source="../media/memory-problems-thinkgraph.msft.png" alt-text="メモリの視覚的表現" lightbox="../media/memory-problems-thinkgraph.msft.png":::
   <span data-ttu-id="f62c2-112">メモリの視覚的表現</span><span class="sxs-lookup"><span data-stu-id="f62c2-112">Visual representation of memory</span></span>  
:::image-end:::  

<span data-ttu-id="f62c2-113">オブジェクトには次の2つの方法でメモリを保持できます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-113">An object may hold memory in two ways:</span></span>  

*   <span data-ttu-id="f62c2-114">オブジェクトを直接選びます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-114">Directly by the object.</span></span>  
*   <span data-ttu-id="f62c2-115">他**のオブジェクト** への参照を保持することによって暗黙的に、ガベージコレクターによってそれらのオブジェクトが自動的に破棄されることを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-115">Implicitly by holding references to other objects, and therefore preventing those objects from being automatically disposed by a garbage collector \(**GC** for short\).</span></span>  

<span data-ttu-id="f62c2-116">DevTools で [メモリ][DevtoolsMemoryProblemsHeapSnapshots] パネルを操作しているときに ( **メモリ**にあるメモリの問題を調査するためのツール)、いくつかの情報の列が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-116">When working with the [Memory][DevtoolsMemoryProblemsHeapSnapshots] panel in DevTools \(a tool for investigating memory issues found under **Memory**\), you may find yourself looking at a few different columns of information.</span></span>  <span data-ttu-id="f62c2-117">目立たない2つの **サイズは浅いサイズ** で、保持されている **サイズ**ですが、これらは何を表しますか?</span><span class="sxs-lookup"><span data-stu-id="f62c2-117">Two that stand out are **Shallow Size** and **Retained Size**, but what do these represent?</span></span>  

:::image type="complex" source="../media/memory-problems-shallow-retained.msft.png" alt-text="浅いサイズと保持サイズ" lightbox="../media/memory-problems-shallow-retained.msft.png":::
   <span data-ttu-id="f62c2-119">浅いサイズと保持サイズ</span><span class="sxs-lookup"><span data-stu-id="f62c2-119">Shallow and Retained Size</span></span>  
:::image-end:::  

### <span data-ttu-id="f62c2-120">浅いサイズ</span><span class="sxs-lookup"><span data-stu-id="f62c2-120">Shallow size</span></span>  

<span data-ttu-id="f62c2-121">これは、オブジェクトによって保持されているメモリのサイズです。</span><span class="sxs-lookup"><span data-stu-id="f62c2-121">This is the size of memory that is held by the object.</span></span>  

<span data-ttu-id="f62c2-122">一般的な JavaScript オブジェクトには、説明用に予約されたメモリ、および即時値を格納するためのメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-122">Typical JavaScript objects have some memory reserved for their description and for storing immediate values.</span></span>  <span data-ttu-id="f62c2-123">通常、非常に浅いサイズを持つことができるのは、配列と文字列のみです。</span><span class="sxs-lookup"><span data-stu-id="f62c2-123">Usually, only arrays and strings are able to have a significant shallow size.</span></span>  <span data-ttu-id="f62c2-124">ただし、文字列と外部配列には、多くの場合、レンダラーメモリ内にメインストレージがあり、JavaScript ヒープの小さなラッパーオブジェクトのみが公開されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-124">However, strings and external arrays often have their main storage in renderer memory, exposing only a small wrapper object on the JavaScript heap.</span></span>  

<span data-ttu-id="f62c2-125">レンダラーメモリは、検査されたページがレンダリングされるプロセスのすべてのメモリです。このページで開始されるすべての専用ワーカーの、ネイティブメモリ + JS ヒープメモリ。</span><span class="sxs-lookup"><span data-stu-id="f62c2-125">Renderer memory is all memory of the process where an inspected page is rendered: native memory + JS heap memory of the page + JS heap memory of all dedicated workers started by the page.</span></span>  <span data-ttu-id="f62c2-126">ただし、小さいオブジェクトは、他のオブジェクトが自動ガベージコレクションプロセスによって破棄されないようにすることで、大量のメモリを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-126">Nevertheless, even a small object is able to hold a large amount of memory indirectly, by preventing other objects from being disposed of by the automatic garbage collection process.</span></span>  

### <span data-ttu-id="f62c2-127">保持サイズ</span><span class="sxs-lookup"><span data-stu-id="f62c2-127">Retained size</span></span>  

<span data-ttu-id="f62c2-128">これは、オブジェクトが削除された後に、 **ガベージコレクタールート** \ (GC ルート) から到達不能になった従属オブジェクトと共に、解放されるメモリのサイズです。</span><span class="sxs-lookup"><span data-stu-id="f62c2-128">This is the size of memory that is freed once the object is deleted along with the dependent objects that were made unreachable from **Garbage Collector roots** \(GC roots\) .</span></span>  

<span data-ttu-id="f62c2-129">**ガベージコレクターのルート** \ (GC ルート \) は、ネイティブコードから V8 の外部の JavaScript オブジェクトへの参照を作成するときに、(ローカルまたはグローバル \ のどちらかに) 作成された **ハンドル** で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-129">**Garbage Collector roots** \(GC roots\) are made up of **handles** that are created \(either local or global\) when making a reference from native code to a JavaScript object outside of V8.</span></span>  <span data-ttu-id="f62c2-130">このようなすべてのハンドルは、 **gc ルート**の  >  **スコープ**と**gc ルート**の  >  **グローバルハンドル**で、ヒープスナップショット内に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-130">All such handles may be found within a heap snapshot under **GC roots** > **Handle scope** and **GC roots** > **Global handles**.</span></span>  <span data-ttu-id="f62c2-131">このドキュメントでは、ブラウザーの実装の詳細について詳しく説明していませんが、混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-131">Describing the handles in this documentation without diving into details of the browser implementation may be confusing.</span></span>  <span data-ttu-id="f62c2-132">ガベージコレクター (GC) のルートとハンドルはどちらも、気にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-132">Both Garbage Collector (GC) roots and the handles are not something you need to worry about.</span></span>  

<span data-ttu-id="f62c2-133">多くの内部 GC ルートがあり、そのほとんどがユーザーにとって興味を持ちません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-133">There are lots of internal GC roots, most of which are not interesting for the users.</span></span>  <span data-ttu-id="f62c2-134">アプリケーションの観点から見ると、次の種類のルートがあります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-134">From the applications standpoint there are following kinds of roots.</span></span>  

*   <span data-ttu-id="f62c2-135">Window グローバルオブジェクト \ (各 iframe 内)</span><span class="sxs-lookup"><span data-stu-id="f62c2-135">Window global object \(in each iframe\).</span></span>  <span data-ttu-id="f62c2-136">ヒープスナップショットには距離フィールドがあります。これは、ウィンドウから最短の保持パスにあるプロパティ参照の数です。</span><span class="sxs-lookup"><span data-stu-id="f62c2-136">There is a distance field in the heap snapshots which is the number of property references on the shortest retaining path from the window.</span></span>  
*   <span data-ttu-id="f62c2-137">ドキュメントを走査して到達可能なすべてのネイティブ DOM ノードで構成されるドキュメント DOM ツリー。</span><span class="sxs-lookup"><span data-stu-id="f62c2-137">Document DOM tree consisting of all native DOM nodes reachable by traversing the document.</span></span>  <span data-ttu-id="f62c2-138">すべてのノードに JS ラッパーが含まれているわけではありませんが、ノードにラッパーがある場合は、ドキュメントが生きている間は生きています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-138">Not all of the nodes may have JS wrappers but if a node has a wrapper, it is alive while the document is alive.</span></span>  
*   <span data-ttu-id="f62c2-139">場合によっては、 **ソース** パネルと **本体** (本体の評価の後など) で、デバッガーコンテキストによってオブジェクトが保持されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-139">Sometimes objects may be retained by the debugger context in the **Sources** panel and the **Console** \(for example after Console evaluation\).</span></span>  <span data-ttu-id="f62c2-140">クリアされた **コンソール** パネルを使ってヒープスナップショットを作成します。 [ **ソース** ] パネルでは、デバッガー内にアクティブなブレークポイントはありません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-140">Create heap snapshots with a cleared **Console** panel and no active breakpoints in the debugger in the **Sources** panel.</span></span>

>[!TIP]
> <span data-ttu-id="f62c2-141">**Console** `clear()` [メモリパネル][DevtoolsMemoryProblemsHeapSnapshots]でヒープスナップショットを取得する前に、[**ソース**] パネルでブレークポイントを実行して非アクティブ化して、コンソールパネルをクリアします。</span><span class="sxs-lookup"><span data-stu-id="f62c2-141">Clear the **Console** panel by running `clear()` and deactivate breakpoints in the **Sources** panel before taking a heap snapshot in the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span></span>

<span data-ttu-id="f62c2-142">メモリグラフは、 `window` ブラウザーのオブジェクトまたは Node.js モジュールのオブジェクトであるルートから始まり `Global` ます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-142">The memory graph starts with a root, which may be the `window` object of the browser or the `Global` object of a Node.js module.</span></span>  <span data-ttu-id="f62c2-143">このルートオブジェクトのガベージコレクション (GCd) を制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-143">You do not control how this root object is garbage collected (GCd).</span></span>  

:::image type="complex" source="../media/memory-problems-dontcontrol.msft.png" alt-text="ルートオブジェクトのガベージコレクションの方法を制御することはできません。" lightbox="../media/memory-problems-dontcontrol.msft.png":::
   <span data-ttu-id="f62c2-145">ルートオブジェクトのガベージコレクションの方法を制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-145">You are not able to control how the root object is garbage collected.</span></span>  
:::image-end:::  

<span data-ttu-id="f62c2-146">ルートから到達できないものはすべて、ガーベジコレクトされた \ (GCd \) を取得します。</span><span class="sxs-lookup"><span data-stu-id="f62c2-146">Whatever is not reachable from the root gets garbage collected \(GCd\).</span></span>  

> [!NOTE]
> <span data-ttu-id="f62c2-147">[ [緩斜面サイズ](#shallow-size) ] 列と [ [保持サイズ](#retained-size) ] 列は両方ともバイト単位のデータを表します。</span><span class="sxs-lookup"><span data-stu-id="f62c2-147">Both the [Shallow size](#shallow-size) and [Retained size](#retained-size) columns represent data in bytes.</span></span>  

## <span data-ttu-id="f62c2-148">ツリーを保持するオブジェクト</span><span class="sxs-lookup"><span data-stu-id="f62c2-148">Objects retaining tree</span></span>  

<span data-ttu-id="f62c2-149">ヒープは、相互接続されたオブジェクトのネットワークです。</span><span class="sxs-lookup"><span data-stu-id="f62c2-149">The heap is a network of interconnected objects.</span></span>  <span data-ttu-id="f62c2-150">数学の世界では、この構造は **グラフ** またはメモリグラフと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-150">In the mathematical world, this structure is called a **graph** or memory graph.</span></span>  <span data-ttu-id="f62c2-151">グラフは、**エッジ**によって接続された**ノード**から構成され、両方のラベルにラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-151">A graph is constructed from **nodes** connected by means of **edges**, both of which are given labels.</span></span>  

*   <span data-ttu-id="f62c2-152">**ノード** \ (または **オブジェクト**\) は、ビルドに使用された **コンストラクター** 関数の名前を使ってラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-152">**Nodes** \(or **objects**\) are labelled using the name of the **constructor** function that was used to build them.</span></span>  
*   <span data-ttu-id="f62c2-153">**エッジ** は、 **プロパティ**の名前を使用してラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-153">**Edges** are labelled using the names of **properties**.</span></span>  

<span data-ttu-id="f62c2-154">[ヒーププロファイラーを使ってプロファイルを記録する方法について][DevtoolsMemoryProblemsHeapSnapshots]説明します。</span><span class="sxs-lookup"><span data-stu-id="f62c2-154">Learn [how to record a profile using the Heap Profiler][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="f62c2-155">次の図では、 [メモリパネル][DevtoolsMemoryProblemsHeapSnapshots] でのヒープスナップショットの記録には、距離 (ガベージコレクター \ (GC \) ルートからの距離) が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-155">In the following figure, some of the eye-catching things that you may see in the Heap Snapshot recording in the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots] include distance:  the distance from the Garbage Collector \(GC\) root.</span></span>  <span data-ttu-id="f62c2-156">同じ型のほぼすべてのオブジェクトが同じ距離にあり、数が大きい場合は、調査の対象となります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-156">If almost all the objects of the same type are at the same distance, and a few are at a bigger distance, that is something worth investigating.</span></span>  

:::image type="complex" source="../media/memory-problems-root.msft.png" alt-text="ルートからの距離" lightbox="../media/memory-problems-root.msft.png":::
   <span data-ttu-id="f62c2-158">ルートからの距離</span><span class="sxs-lookup"><span data-stu-id="f62c2-158">Distance from root</span></span>  
:::image-end:::  

## <span data-ttu-id="f62c2-159">Dominators</span><span class="sxs-lookup"><span data-stu-id="f62c2-159">Dominators</span></span>  

<span data-ttu-id="f62c2-160">Dominator オブジェクトは、各オブジェクトに Dominator が1つしかないため、ツリー構造で構成されています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-160">Dominator objects are comprised of a tree structure because each object has exactly one dominator.</span></span>  <span data-ttu-id="f62c2-161">オブジェクトの dominator には、優位なオブジェクトへの直接参照がない場合があります。つまり、dominator のツリーはグラフのスパニングツリーではありません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-161">A dominator of an object may lack direct references to an object it dominates; that is, the tree of the dominator is not a spanning tree of the graph.</span></span>  

<span data-ttu-id="f62c2-162">次の図では、次のステートメントが true になっています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-162">In the following figure, the following statement are true.</span></span>  

*   <span data-ttu-id="f62c2-163">ノード1の各ノード2</span><span class="sxs-lookup"><span data-stu-id="f62c2-163">Node 1 dominates node 2</span></span>  
*   <span data-ttu-id="f62c2-164">ノード2の各ノード3、4、6</span><span class="sxs-lookup"><span data-stu-id="f62c2-164">Node 2 dominates nodes 3, 4 and 6</span></span>  
*   <span data-ttu-id="f62c2-165">ノード3の各ノード5</span><span class="sxs-lookup"><span data-stu-id="f62c2-165">Node 3 dominates node 5</span></span>  
*   <span data-ttu-id="f62c2-166">ノード5のつのノード8</span><span class="sxs-lookup"><span data-stu-id="f62c2-166">Node 5 dominates node 8</span></span>  
*   <span data-ttu-id="f62c2-167">ノード6の各バージョンノード7</span><span class="sxs-lookup"><span data-stu-id="f62c2-167">Node 6 dominates node 7</span></span>  

:::image type="complex" source="../media/memory-problems-dominatorsspanning.msft.png" alt-text="Dominator ツリー構造" lightbox="../media/memory-problems-dominatorsspanning.msft.png":::
   <span data-ttu-id="f62c2-169">Dominator ツリー構造</span><span class="sxs-lookup"><span data-stu-id="f62c2-169">Dominator tree structure</span></span>  
:::image-end:::  

<span data-ttu-id="f62c2-170">次の図では、node `#3` が dominator のようになって `#10` いますが、 `#7` ガベージコレクター \ (GC) からのすべての単純なパスにも存在し `#10` ます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-170">In the following figure, node `#3` is the dominator of `#10`, but `#7` also exists in every simple path from Garbage Collector \(GC\) to `#10`.</span></span>  <span data-ttu-id="f62c2-171">したがって、オブジェクト B は、ルートからオブジェクト A へのすべての単純パスに B が存在する場合、オブジェクト A の dominator になります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-171">Therefore, an object B is a dominator of an object A if B exists in every simple path from the root to the object A.</span></span>  

:::image type="complex" source="../media/memory-problems-dominators.msft.gif" alt-text="アニメーション化された dominator の図" lightbox="../media/memory-problems-dominators.msft.gif":::
   <span data-ttu-id="f62c2-173">アニメーション化された dominator の図</span><span class="sxs-lookup"><span data-stu-id="f62c2-173">Animated dominator illustration</span></span>  
:::image-end:::  

## <span data-ttu-id="f62c2-174">V8 の詳細</span><span class="sxs-lookup"><span data-stu-id="f62c2-174">V8 specifics</span></span>  

<span data-ttu-id="f62c2-175">メモリのプロファイリングを行うときは、ヒープスナップショットが特定の方法で表示される理由を理解しておくと便利です。</span><span class="sxs-lookup"><span data-stu-id="f62c2-175">When profiling memory, it is helpful to understand why heap snapshots look a certain way.</span></span>  <span data-ttu-id="f62c2-176">このセクションでは、 **V8 JavaScript 仮想マシン** \ (V8 VM または vm \) に特に対応する、いくつかのメモリ関連トピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f62c2-176">This section describes some memory-related topics specifically corresponding to the **V8 JavaScript virtual machine** \(V8 VM or VM\).</span></span>  

### <span data-ttu-id="f62c2-177">JavaScript オブジェクトの表現</span><span class="sxs-lookup"><span data-stu-id="f62c2-177">JavaScript object representation</span></span>  

<span data-ttu-id="f62c2-178">プリミティブ型には次の3種類があります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-178">There are three primitive types:</span></span>  

*   <span data-ttu-id="f62c2-179">番号 ( `3.14159...` \ など)</span><span class="sxs-lookup"><span data-stu-id="f62c2-179">Numbers \(for example `3.14159...`\)</span></span>  
*   <span data-ttu-id="f62c2-180">ブール型 ( `true` \ `false` )</span><span class="sxs-lookup"><span data-stu-id="f62c2-180">Booleans \(`true` or `false`\)</span></span>  
*   <span data-ttu-id="f62c2-181">文字列 \ (\ など `"Werner Heisenberg"` )</span><span class="sxs-lookup"><span data-stu-id="f62c2-181">Strings \(for example `"Werner Heisenberg"`\)</span></span>  

<span data-ttu-id="f62c2-182">プリミティブは、他の値を参照することはできません。また、常に leafs ノードまたは終了ノードを参照します。</span><span class="sxs-lookup"><span data-stu-id="f62c2-182">Primitives are not able to reference other values and are always leafs or terminating nodes.</span></span>  

<span data-ttu-id="f62c2-183">**数値** は、次のいずれかの方法で保存できます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-183">**Numbers** are able to be stored as either:</span></span>  

*   <span data-ttu-id="f62c2-184">31ビットの **小さな** 整数値 (**SMI**s \)、または</span><span class="sxs-lookup"><span data-stu-id="f62c2-184">an immediate 31-bit integer values called **small integers** \(**SMI**s\), or</span></span>  
*   <span data-ttu-id="f62c2-185">ヒープ **値**と呼ばれるヒープオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f62c2-185">heap objects, referred to as **heap numbers**.</span></span> <span data-ttu-id="f62c2-186">ヒープ値は、 **2 倍**などの SMI フォームに収まらない値や、プロパティの設定など、値の **ボックス**化が必要な場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-186">Heap numbers are used for storing values that do not fit into the SMI form, such as **doubles**, or when a value needs to be **boxed**, such as setting properties on it.</span></span>  

<span data-ttu-id="f62c2-187">**文字列** は、次のいずれかの方法で保存できます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-187">**Strings** are able to be stored in either:</span></span>  

*   <span data-ttu-id="f62c2-188">**VM ヒープ**、または</span><span class="sxs-lookup"><span data-stu-id="f62c2-188">the **VM heap**, or</span></span>
*   <span data-ttu-id="f62c2-189">**レンダラーのメモリ**内の外部。</span><span class="sxs-lookup"><span data-stu-id="f62c2-189">externally in the **memory of the renderer**.</span></span>  <span data-ttu-id="f62c2-190">**ラッパーオブジェクト**が作成され、外部ストレージへのアクセスに使用されます。たとえば、スクリプトソースや Web から受け取ったその他のコンテンツは、VM ヒープにコピーされるのではなく格納されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-190">A **wrapper object** is created and used for accessing external storage where, for example, script sources and other content that is received from the Web is stored, rather than copied onto the VM heap.</span></span>

<span data-ttu-id="f62c2-191">新しい JavaScript オブジェクト用のメモリは、専用の JavaScript ヒープ \ (または **VM ヒープ**\) から割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-191">Memory for new JavaScript objects is allocated from a dedicated JavaScript heap \(or **VM heap**\).</span></span>  <span data-ttu-id="f62c2-192">これらのオブジェクトは、V8 のガベージコレクターによって管理されるため、少なくとも1つの強い参照が存在する限り、生きたままです。</span><span class="sxs-lookup"><span data-stu-id="f62c2-192">These objects are managed by the garbage collector in V8 and therefore, stay alive as long as there is at least one strong reference to them.</span></span>  

<span data-ttu-id="f62c2-193">JavaScript ヒープに含まれないものは、 **ネイティブオブジェクト**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-193">Anything not in the JavaScript heap is called a **native object**.</span></span>  <span data-ttu-id="f62c2-194">ヒープオブジェクトとは対照的に、ネイティブオブジェクトは、有効期間を通じて V8 ガーベジコレクターによって管理されるものではなく、javascript のラッパーオブジェクトを使って JavaScript からのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-194">Native objects, in contrast to heap objects, are not managed by the V8 garbage collector throughout their lifetime, and may only be accessed from JavaScript using the JavaScript wrapper object.</span></span>  

<span data-ttu-id="f62c2-195">**短所文字列** は、格納された文字列のペアで構成され、その後結合されたオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f62c2-195">**Cons string** is an object that consists of pairs of strings stored and then joined, and is a result of concatenation.</span></span>  <span data-ttu-id="f62c2-196">**短所の文字列**の内容の結合は、必要な場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="f62c2-196">The joining of the **cons string** contents occurs only as needed.</span></span> <span data-ttu-id="f62c2-197">例としては、結合された文字列の部分文字列を構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f62c2-197">An example would be when a substring of a joined string needs to be constructed.</span></span>

<span data-ttu-id="f62c2-198">たとえば、とを連結する `a` と、 `b` 連結の結果を表す文字列を取得でき `(a, b)` ます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-198">For example, if you concatenate `a` and `b`, you get a string `(a, b)` which represents the result of concatenation.</span></span>  <span data-ttu-id="f62c2-199">後でその結果と連結した場合は `d` 、次のような別の **文字列**が返さ `((a, b, d)` れます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-199">If you later concatenated `d` with that result, you get another **cons string**: `((a, b, d)`.</span></span>  

<span data-ttu-id="f62c2-200">**配列** は数値キーを含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f62c2-200">**Array** is an object with numeric keys.</span></span> <span data-ttu-id="f62c2-201">大量のデータを格納するために、V8 VM では**配列**が広く使われています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-201">**Arrays** are used extensively in the V8 VM for storing large amounts of data.</span></span> <span data-ttu-id="f62c2-202">ディクショナリなどのキーと値のペアのセットは、 **配列**によってバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-202">Sets of key-value pairs, like dictionaries, are backed up by **arrays**.</span></span>  

<span data-ttu-id="f62c2-203">一般的な JavaScript オブジェクトは、次の2つの **配列** 型のうちの1つに限定されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-203">A typical JavaScript object is stored as only one of two **array** types:</span></span>  

*   <span data-ttu-id="f62c2-204">"名前付きプロパティ" と "</span><span class="sxs-lookup"><span data-stu-id="f62c2-204">named properties, and</span></span>  
*   <span data-ttu-id="f62c2-205">数値要素</span><span class="sxs-lookup"><span data-stu-id="f62c2-205">numeric elements</span></span>  

<span data-ttu-id="f62c2-206">プロパティが少数の場合は、JavaScript オブジェクト内にプロパティが内部的に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-206">When there are a small number of properties, the properties are stored internally in the JavaScript object.</span></span>  

<span data-ttu-id="f62c2-207">**Map** は、オブジェクトの種類とレイアウトの両方を説明するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f62c2-207">**Map** is an object that describes both the kind of object it is and the layout.</span></span> <span data-ttu-id="f62c2-208">たとえば、 [fast プロパティにアクセス][V8FastProperties]するための暗黙的なオブジェクト階層の記述には、maps を使います。</span><span class="sxs-lookup"><span data-stu-id="f62c2-208">For example, maps are used to describe implicit object hierarchies for [fast property access][V8FastProperties].</span></span>  

### <span data-ttu-id="f62c2-209">オブジェクトグループ</span><span class="sxs-lookup"><span data-stu-id="f62c2-209">Object groups</span></span>  

<span data-ttu-id="f62c2-210">各 **native objects** グループは、相互参照を保持するオブジェクトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-210">Each **native objects** group is made up of objects that hold mutual references to each other.</span></span>  <span data-ttu-id="f62c2-211">たとえば、すべてのノードに関連する親へのリンクと次の子とその次の兄弟へのリンクが含まれている DOM サブツリーで、接続されたグラフを形成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f62c2-211">Consider, for example, a DOM subtree where every node has a link to the relative parent and links to the next child and next sibling, therefore forming a connected graph.</span></span>  

> [!NOTE]
> <span data-ttu-id="f62c2-212">ネイティブオブジェクトは JavaScript ヒープには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-212">Native objects are not represented in the JavaScript heap.</span></span>  <span data-ttu-id="f62c2-213">ネイティブオブジェクトのサイズが0でない場合は、表示されません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-213">The lack of representation is why native objects have zero size.</span></span> <span data-ttu-id="f62c2-214">代わりに、ラッパーオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-214">Instead, wrapper objects are created.</span></span>  

<span data-ttu-id="f62c2-215">各ラッパーオブジェクトは、対応するネイティブオブジェクトへの参照を保持します。これには、コマンドをリダイレクトするための参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-215">Each wrapper object holds a reference to the corresponding native object, for redirecting commands to it.</span></span>  <span data-ttu-id="f62c2-216">さらに、オブジェクトグループはラッパーオブジェクトを保持します。</span><span class="sxs-lookup"><span data-stu-id="f62c2-216">In turn, an object group holds wrapper objects.</span></span>  <span data-ttu-id="f62c2-217">ただし、ガベージコレクター \ (GC \) は、ラッパーが参照されなくなったオブジェクトグループを解放するのに十分なものであるため、この方法では、回収不能なサイクルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="f62c2-217">However, this does not create an uncollectable cycle, as Garbage Collector \(GC\) is smart enough to release object groups whose wrappers are no longer referenced.</span></span> <span data-ttu-id="f62c2-218">ただし、1つのラッパーの解放を忘れると、グループ全体と関連付けられたラッパーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-218">But forgetting to release a single wrapper holds the whole group and associated wrappers.</span></span>  

## <span data-ttu-id="f62c2-219">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="f62c2-219">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: ./heap-snapshots.md "ヒープスナップショットの記録方法 |Microsoft ドキュメント"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "V8 の Fast プロパティ |V8"  

> [!NOTE]
> <span data-ttu-id="f62c2-222">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f62c2-222">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f62c2-223">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-223">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f62c2-225">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f62c2-225">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney
