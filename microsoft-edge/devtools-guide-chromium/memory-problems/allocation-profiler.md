---
description: タイムラインで Allocation インストルメンテーションを使用して、適切にガベージ コレクションされていないオブジェクトを検索し、メモリを保持し続ける。
title: タイムラインで割り当てインストルメンテーションを使用する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 374b7f0ad80b8975319b2b0ec5cecf42ce4bde82
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397819"
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

# <a name="how-to-use-allocation-instrumentation-on-timeline"></a><span data-ttu-id="e977c-104">タイムラインで割り当てインストルメンテーションを使用する方法</span><span class="sxs-lookup"><span data-stu-id="e977c-104">How to use Allocation instrumentation on Timeline</span></span>  

<span data-ttu-id="e977c-105">タイムライン **で Allocation インストルメンテーション** を使用して、適切にガベージ コレクションされていないオブジェクトを検索し、メモリを保持し続ける。</span><span class="sxs-lookup"><span data-stu-id="e977c-105">Use **Allocation instrumentation on timeline** to find objects that are not being properly garbage collected, and continue to retain memory.</span></span>  

## <a name="how-allocation-instrumentation-on-timeline-works"></a><span data-ttu-id="e977c-106">タイムラインでの割り当てインストルメンテーションの動作</span><span class="sxs-lookup"><span data-stu-id="e977c-106">How Allocation instrumentation on timeline works</span></span>  

<span data-ttu-id="e977c-107">**タイムライン上の割り当てインス**トルメンテーション は、ヒープ プロファイラーの詳細なスナップショット情報と、パフォーマンス パネルの増分更新と追跡を**組み合**わせたものになります。</span><span class="sxs-lookup"><span data-stu-id="e977c-107">**Allocation instrumentation on timeline** combines the detailed snapshot information of the **heap profiler** with the incremental updating and tracking of the **Performance** panel.</span></span>  <span data-ttu-id="e977c-108">同様に、オブジェクトのヒープ割り当てを追跡するには、記録を開始し、一連のアクションを実行し、分析のために記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="e977c-108">Similarly, tracking heap allocation for objects involves starting a recording, performing a sequence of actions, and stopping the recording for analysis.</span></span>  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

<span data-ttu-id="e977c-109">**タイムライン上の割り当て** インストルメンテーションは、記録 \(50 ms\ごとに頻繁に) と、記録の最後に 1 つの最終スナップショット全体でヒープ スナップショットを定期的に取得します。</span><span class="sxs-lookup"><span data-stu-id="e977c-109">**Allocation instrumentation on timeline** takes heap snapshots periodically throughout the recording \(as frequently as every 50 ms\) and one final snapshot at the end of the recording.</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png" alt-text="タイムラインでの割り当てインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png":::
   **<span data-ttu-id="e977c-111">タイムラインでの割り当てインストルメンテーション</span><span class="sxs-lookup"><span data-stu-id="e977c-111">Allocation instrumentation on timeline</span></span>**  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="e977c-112">the の後の番号は、記録セッション中に作成された複数のスナップショット全体で保持 `@` されるオブジェクト ID です。</span><span class="sxs-lookup"><span data-stu-id="e977c-112">The number after the `@` is an object ID that persists across the multiple snapshots taken during the recording session.</span></span>  <span data-ttu-id="e977c-113">永続オブジェクト ID を使用すると、ヒープ状態を正確に比較できます。</span><span class="sxs-lookup"><span data-stu-id="e977c-113">The persistent object ID enables precise comparison between heap states.</span></span>  <span data-ttu-id="e977c-114">オブジェクトはガベージ コレクション中に移動されます。そのため、オブジェクトのアドレスを表示すると意味がありません。</span><span class="sxs-lookup"><span data-stu-id="e977c-114">Objects are moved during garbage collections, so displaying the address of an object makes no sense.</span></span>  

## <a name="enable-allocation-instrumentation-on-timeline"></a><span data-ttu-id="e977c-115">タイムラインで割り当てインストルメンテーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="e977c-115">Enable Allocation Instrumentation on Timeline</span></span>  

<span data-ttu-id="e977c-116">タイムラインでの割り当てインストルメンテーションの使用 **を開始するには、次のアクションを実行します**。</span><span class="sxs-lookup"><span data-stu-id="e977c-116">Complete the following actions to begin using **Allocation instrumentation on timeline**.</span></span>  

1.  <span data-ttu-id="e977c-117">[DevTools を開きます][DevtoolsOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="e977c-117">[Open the DevTools][DevtoolsOpenIndex].</span></span>  
1.  <span data-ttu-id="e977c-118">[メモリ] **パネルを開** き、[タイムライン上の割り当て **インストルメンテーション] ラジオ ボタン** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e977c-118">Open the **Memory** panel, select the **Allocation instrumentation on timeline** radio button.</span></span>  
1.  <span data-ttu-id="e977c-119">Start recording (録画開始) </span><span class="sxs-lookup"><span data-stu-id="e977c-119">Start recording.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png" alt-text="レコード ヒープ割り当てプロファイラー" lightbox="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png":::
       <span data-ttu-id="e977c-121">レコード ヒープ割り当てプロファイラー</span><span class="sxs-lookup"><span data-stu-id="e977c-121">Record heap allocations profiler</span></span>  
    :::image-end:::  
    
## <a name="read-a-heap-allocation-timeline"></a><span data-ttu-id="e977c-122">ヒープ割り当てタイムラインの読み取り</span><span class="sxs-lookup"><span data-stu-id="e977c-122">Read a heap allocation timeline</span></span>  

<span data-ttu-id="e977c-123">ヒープ割り当てタイムラインは、オブジェクトが作成されている場所を示し、保持パスを識別します。</span><span class="sxs-lookup"><span data-stu-id="e977c-123">The heap allocation timeline shows where objects are being created and identifies the retaining path.</span></span>  <span data-ttu-id="e977c-124">次の図では、上部のバーは、ヒープ内で新しいオブジェクトが見つかったかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="e977c-124">In the following figure, the bars at the top indicate when new objects are found in the heap.</span></span>  

<span data-ttu-id="e977c-125">各バーの高さは、最近割り当てられたオブジェクトのサイズに対応し、バーの色は、それらのオブジェクトがまだ最終的なヒープ スナップショットに存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e977c-125">The height of each bar corresponds to the size of the recently allocated objects, and the color of the bars indicate whether or not those objects are still live in the final heap snapshot.</span></span>  <span data-ttu-id="e977c-126">青いバーは、タイムラインの最後にまだ存在するオブジェクトを示し、灰色のバーは、タイムライン中に割り当てられたが、その後ガベージ コレクションされたオブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="e977c-126">Blue bars indicate objects that are still live at the end of the timeline, Gray bars indicate objects that were allocated during the timeline, but have since been garbage collected.</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png" alt-text="タイムライン スナップショットでの割り当てインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png":::
   <span data-ttu-id="e977c-128">**タイムライン スナップショットでの割り当てインストルメン** テーション</span><span class="sxs-lookup"><span data-stu-id="e977c-128">**Allocation instrumentation on timeline** snapshot</span></span>  
:::image-end:::  

<!--In the following figure, an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple choose actions  -->  

<span data-ttu-id="e977c-129">上記のタイムラインのスライダーを使用して、その特定のスナップショットを拡大し、その時点で最近割り当てられたオブジェクトを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e977c-129">You are able to use the sliders in the timeline above to zoom into that particular snapshot and review the objects that were recently allocated at that point:</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png" alt-text="スナップショットを拡大する" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png":::
   <span data-ttu-id="e977c-131">スナップショットを拡大する</span><span class="sxs-lookup"><span data-stu-id="e977c-131">Zoom into snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="e977c-132">ヒープ内の特定のオブジェクトを選択すると、ヒープ スナップショットの下部に保持ツリーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e977c-132">Choosing on a specific object in the heap shows the retaining tree in the bottom portion of the heap snapshot.</span></span>  <span data-ttu-id="e977c-133">オブジェクトへの保持パスを調べるには、オブジェクトが収集されていない理由を理解するのに十分な情報が提供され、不要な参照を削除するために必要なコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e977c-133">Examining the retaining path to the object should give you enough information to understand why the object was not collected, and you should make the necessary code changes to remove the unnecessary reference.</span></span>  

## <a name="view-memory-allocation-by-function"></a><span data-ttu-id="e977c-134">関数別にメモリ割り当てを表示する</span><span class="sxs-lookup"><span data-stu-id="e977c-134">View memory allocation by function</span></span>  

<span data-ttu-id="e977c-135">JavaScript 関数によってメモリ割り当てを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e977c-135">You are able to view memory allocation by JavaScript function.</span></span>  <span data-ttu-id="e977c-136">詳細については、「関数別にメモリ [割り当てを調査する」に移動します][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。</span><span class="sxs-lookup"><span data-stu-id="e977c-136">For more information, navigate to [Investigate memory allocation by function][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e977c-137">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="e977c-137">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpenIndex]: ../open/index.md "Microsoft Edge (クロム) DevTools ファイルを開|Microsoft Docs"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: ./index.md#investigate-memory-allocation-by-function "関数別にメモリ割り当てを調査する - Fix Memory problems |Microsoft Docs"  

<!--[HeapProfiler]: ./heap-snapshots.md "How to Record Heap Snapshots"  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "Microsoft Edge チャネルのダウンロード"  

> [!NOTE]
> <span data-ttu-id="e977c-141">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="e977c-141">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e977c-142">元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) つかり [、Meggin Kearney][MegginKearney] \(Technical Writer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="e977c-142">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="e977c-144">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="e977c-144">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
