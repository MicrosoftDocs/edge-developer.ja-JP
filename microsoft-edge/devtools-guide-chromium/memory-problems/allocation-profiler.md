---
description: タイムラインで Allocation インストルメンテーションを使用して、適切にガベージ コレクションされていないオブジェクトを検索し、メモリを保持し続ける。
title: タイムラインで Allocation Instrumentation を使用する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 946c2d8b45f316b491a604c16c37bb2467983222
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230916"
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

# <span data-ttu-id="5d199-104">タイムラインで Allocation インストルメンテーションを使用する方法</span><span class="sxs-lookup"><span data-stu-id="5d199-104">How to use Allocation instrumentation on Timeline</span></span>  

<span data-ttu-id="5d199-105">タイムライン **で Allocation インストルメンテーションを** 使用して、適切にガベージ コレクションされていないオブジェクトを検索し、メモリを保持し続ける。</span><span class="sxs-lookup"><span data-stu-id="5d199-105">Use **Allocation instrumentation on timeline** to find objects that are not being properly garbage collected, and continue to retain memory.</span></span>  

## <span data-ttu-id="5d199-106">タイムラインでの Allocation のインストルメンテーションのしくみ</span><span class="sxs-lookup"><span data-stu-id="5d199-106">How Allocation instrumentation on timeline works</span></span>  

<span data-ttu-id="5d199-107">**タイムラインでの割り当ての**インストルメンテーションは\*\*\*\*、ヒープ プロファイラーの詳細なスナップショット情報と、パフォーマンス パネルの増分更新と追跡を**組み合**わせたものになります。</span><span class="sxs-lookup"><span data-stu-id="5d199-107">**Allocation instrumentation on timeline** combines the detailed snapshot information of the **heap profiler** with the incremental updating and tracking of the **Performance** panel.</span></span>  <span data-ttu-id="5d199-108">同様に、オブジェクトのヒープ割り当てを追跡するには、記録を開始し、一連の操作を実行し、分析のために記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="5d199-108">Similarly, tracking heap allocation for objects involves starting a recording, performing a sequence of actions, and stopping the recording for analysis.</span></span>  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

<span data-ttu-id="5d199-109">**タイムラインでの割** り当てインストルメンテーションは、記録 \(50 ミリ秒ごとに頻繁に) ヒープ スナップショットと、記録の最後に 1 つの最終的なスナップショットを定期的に取得します。</span><span class="sxs-lookup"><span data-stu-id="5d199-109">**Allocation instrumentation on timeline** takes heap snapshots periodically throughout the recording \(as frequently as every 50 ms\) and one final snapshot at the end of the recording.</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png" alt-text="タイムラインでの割り当てインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png":::
   **<span data-ttu-id="5d199-111">タイムラインでの割り当てインストルメンテーション</span><span class="sxs-lookup"><span data-stu-id="5d199-111">Allocation instrumentation on timeline</span></span>**  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5d199-112">その後の数値は、レコーディング セッション中に取得された複数のスナップショット全体にわたって保持される `@` オブジェクト ID です。</span><span class="sxs-lookup"><span data-stu-id="5d199-112">The number after the `@` is an object ID that persists across the multiple snapshots taken during the recording session.</span></span>  <span data-ttu-id="5d199-113">永続的なオブジェクト ID を使用すると、ヒープ状態を正確に比較できます。</span><span class="sxs-lookup"><span data-stu-id="5d199-113">The persistent object ID enables precise comparison between heap states.</span></span>  <span data-ttu-id="5d199-114">オブジェクトはガベージ コレクション中に移動されます。そのため、オブジェクトのアドレスを表示する方法は意味がありません。</span><span class="sxs-lookup"><span data-stu-id="5d199-114">Objects are moved during garbage collections, so displaying the address of an object makes no sense.</span></span>  

## <span data-ttu-id="5d199-115">タイムラインで Allocation Instrumentation を有効にする</span><span class="sxs-lookup"><span data-stu-id="5d199-115">Enable Allocation Instrumentation on Timeline</span></span>  

<span data-ttu-id="5d199-116">タイムラインで Allocation インストルメンテーションの使用を開始するには、 **次の操作を実行します**。</span><span class="sxs-lookup"><span data-stu-id="5d199-116">Complete the following actions to begin using **Allocation instrumentation on timeline**.</span></span>  

1.  <span data-ttu-id="5d199-117">[DevTools を開きます][DevtoolsOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="5d199-117">[Open the DevTools][DevtoolsOpenIndex].</span></span>  
1.  <span data-ttu-id="5d199-118">メモリ パネル **を開** き、タイムラインの [割り当て **インストルメンテーション] ラジオ ボタンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="5d199-118">Open the **Memory** panel, select the **Allocation instrumentation on timeline** radio button.</span></span>  
1.  <span data-ttu-id="5d199-119">Start recording (録画開始) </span><span class="sxs-lookup"><span data-stu-id="5d199-119">Start recording.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png" alt-text="レコード ヒープ割り当てプロファイラー" lightbox="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png":::
       <span data-ttu-id="5d199-121">レコード ヒープ割り当てプロファイラー</span><span class="sxs-lookup"><span data-stu-id="5d199-121">Record heap allocations profiler</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="5d199-122">ヒープ割り当てのタイムラインを読み取る</span><span class="sxs-lookup"><span data-stu-id="5d199-122">Read a heap allocation timeline</span></span>  

<span data-ttu-id="5d199-123">ヒープ割り当てのタイムラインは、オブジェクトが作成されている場所を示し、保持パスを識別します。</span><span class="sxs-lookup"><span data-stu-id="5d199-123">The heap allocation timeline shows where objects are being created and identifies the retaining path.</span></span>  <span data-ttu-id="5d199-124">次の図では、上部のバーは、ヒープ内で新しいオブジェクトが見つかったかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="5d199-124">In the following figure, the bars at the top indicate when new objects are found in the heap.</span></span>  

<span data-ttu-id="5d199-125">各バーの高さは、最近割り当てられたオブジェクトのサイズに対応し、バーの色は、それらのオブジェクトが最終的なヒープ スナップショット内にまだ存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5d199-125">The height of each bar corresponds to the size of the recently allocated objects, and the color of the bars indicate whether or not those objects are still live in the final heap snapshot.</span></span>  <span data-ttu-id="5d199-126">青いバーは、タイムラインの最後にまだ存在しているオブジェクトを示し、灰色のバーは、タイムラインの間に割り当てられたが、その後ガベージ コレクションされたオブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="5d199-126">Blue bars indicate objects that are still live at the end of the timeline, Gray bars indicate objects that were allocated during the timeline, but have since been garbage collected.</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png" alt-text="タイムライン スナップショットでの割り当てのインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png":::
   <span data-ttu-id="5d199-128">**タイムライン スナップショットでの割り当てのインストルメンテーション**</span><span class="sxs-lookup"><span data-stu-id="5d199-128">**Allocation instrumentation on timeline** snapshot</span></span>  
:::image-end:::  

<!--In the following figure, an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple click actions  -->  

<span data-ttu-id="5d199-129">上のタイムラインのスライダーを使って、その特定のスナップショットを拡大し、その時点で最近割り当てられたオブジェクトを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5d199-129">You are able to use the sliders in the timeline above to zoom into that particular snapshot and review the objects that were recently allocated at that point:</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png" alt-text="スナップショットを拡大する" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png":::
   <span data-ttu-id="5d199-131">スナップショットを拡大する</span><span class="sxs-lookup"><span data-stu-id="5d199-131">Zoom into snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="5d199-132">ヒープ内の特定のオブジェクトをクリックすると、ヒープ スナップショットの下部に保持ツリーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d199-132">Clicking on a specific object in the heap shows the retaining tree in the bottom portion of the heap snapshot.</span></span>  <span data-ttu-id="5d199-133">オブジェクトへの保持パスを調べることで、オブジェクトが収集されていない理由を理解するのに十分な情報が得ら、不要な参照を削除するために必要なコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d199-133">Examining the retaining path to the object should give you enough information to understand why the object was not collected, and you should make the necessary code changes to remove the unnecessary reference.</span></span>  

## <span data-ttu-id="5d199-134">メモリ割り当てを関数別に表示する</span><span class="sxs-lookup"><span data-stu-id="5d199-134">View memory allocation by function</span></span>  

<span data-ttu-id="5d199-135">JavaScript 関数によってメモリ割り当てを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5d199-135">You are able to view memory allocation by JavaScript function.</span></span>  <span data-ttu-id="5d199-136">詳細については、「関数別にメモリ割り [当てを調査する」に移動します][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。</span><span class="sxs-lookup"><span data-stu-id="5d199-136">For more information, navigate to [Investigate memory allocation by function][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction].</span></span>  

## <span data-ttu-id="5d199-137">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="5d199-137">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpenIndex]: ../open/index.md "Microsoft Edge (Chromium) DevTools を開く |Microsoft Docs"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: ./index.md#investigate-memory-allocation-by-function "関数別にメモリ割り当てを調査する - メモリの問題を修正する |Microsoft Docs"  

<!--[HeapProfiler]: ./heap-snapshots.md "How to Record Heap Snapshots"  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "Microsoft Edge チャネルをダウンロードする"  

> [!NOTE]
> <span data-ttu-id="5d199-141">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="5d199-141">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5d199-142">元のページはここから [見](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) つかり [、Meggin Kearney][MegginKearney] \(Technical Writer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="5d199-142">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5d199-144">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5d199-144">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
