---
title: タイムラインでの割り当てインストルメンテーションの使い方
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ab7a270e1d599e254aaaf4515b6898cb1d9782fc
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611735"
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





# <span data-ttu-id="c778c-103">タイムラインでの割り当てインストルメンテーションの使い方</span><span class="sxs-lookup"><span data-stu-id="c778c-103">How to Use Allocation Instrumentation on Timeline</span></span>  



<span data-ttu-id="c778c-104">**タイムライン上で割り当てインストルメンテーション**を使用して、適切なガベージコレクションが実行されていないオブジェクトを探し、引き続きメモリを保持します。</span><span class="sxs-lookup"><span data-stu-id="c778c-104">Use **Allocation instrumentation on timeline** to find objects that are not being properly garbage collected, and continue to retain memory.</span></span>  

## <span data-ttu-id="c778c-105">タイムラインの割り当てインストルメンテーションのしくみ</span><span class="sxs-lookup"><span data-stu-id="c778c-105">How Allocation instrumentation on timeline works</span></span>  

<span data-ttu-id="c778c-106">**タイムライン上の割り当てインストルメンテーション**は、**ヒーププロファイラー**の詳細なスナップショット情報を、**パフォーマンス**パネルの段階的な更新と追跡と組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="c778c-106">**Allocation instrumentation on timeline** combines the detailed snapshot information of the **heap profiler** with the incremental updating and tracking of the **Performance** panel.</span></span>  <span data-ttu-id="c778c-107">同様に、オブジェクトのヒープ割り当てのトラッキングでは、記録の開始、一連の操作の実行、分析のための記録の停止などを行います。</span><span class="sxs-lookup"><span data-stu-id="c778c-107">Similarly, tracking heap allocation for objects involves starting a recording, performing a sequence of actions, and stopping the recording for analysis.</span></span>  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

<span data-ttu-id="c778c-108">**タイムラインの割り当てインストルメンテーション**は、記録中の (50 ミリ秒間のすべての頻度で) ヒープスナップショットと、記録の最後に1つの最終スナップショットを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c778c-108">**Allocation instrumentation on timeline** takes heap snapshots periodically throughout the recording \(as frequently as every 50 ms!\) and one final snapshot at the end of the recording.</span></span>  

> ##### <span data-ttu-id="c778c-109">図 1</span><span class="sxs-lookup"><span data-stu-id="c778c-109">Figure 1</span></span>  
> **<span data-ttu-id="c778c-110">タイムライン上の割り当てインストルメンテーション</span><span class="sxs-lookup"><span data-stu-id="c778c-110">Allocation instrumentation on timeline</span></span>**  
> ![タイムライン上の割り当てインストルメンテーション][ImageObjectTracker]  

> [!NOTE]
> <span data-ttu-id="c778c-112">の後の番号は、 `@` 記録セッション中に作成された複数のスナップショット間で保持されるオブジェクト ID です。</span><span class="sxs-lookup"><span data-stu-id="c778c-112">The number after the `@` is an object ID that persists across the multiple snapshots taken during the recording session.</span></span>  <span data-ttu-id="c778c-113">永続的なオブジェクト ID によって、ヒープの状態を正確に比較できます。</span><span class="sxs-lookup"><span data-stu-id="c778c-113">The persistent object ID enables precise comparison between heap states.</span></span>  <span data-ttu-id="c778c-114">オブジェクトはガベージコレクション中に移動されるため、オブジェクトのアドレスを表示すると意味がありません。</span><span class="sxs-lookup"><span data-stu-id="c778c-114">Objects are moved during garbage collections, so displaying the address of an object makes no sense.</span></span>  

## <span data-ttu-id="c778c-115">タイムラインでの割り当てインストルメンテーションの有効化</span><span class="sxs-lookup"><span data-stu-id="c778c-115">Enable Allocation Instrumentation on Timeline</span></span>  

<span data-ttu-id="c778c-116">**タイムラインでの割り当てインストルメンテーションの**使用を開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c778c-116">Follow these steps to begin using **Allocation instrumentation on timeline**.</span></span>  

1.  <span data-ttu-id="c778c-117">[DevTools を開き][DevtoolsOpenIndex]ます。</span><span class="sxs-lookup"><span data-stu-id="c778c-117">[Open the DevTools][DevtoolsOpenIndex].</span></span>  
1.  <span data-ttu-id="c778c-118">[**メモリ**] パネルを開き、[**タイムライン上の割り当てインストルメンテーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c778c-118">Open the **Memory** panel, select the **Allocation instrumentation on timeline** radio button.</span></span>  
1.  <span data-ttu-id="c778c-119">Start recording (録画開始) </span><span class="sxs-lookup"><span data-stu-id="c778c-119">Start recording.</span></span>  

> ##### <span data-ttu-id="c778c-120">図 2</span><span class="sxs-lookup"><span data-stu-id="c778c-120">Figure 2</span></span>  
> <span data-ttu-id="c778c-121">ヒープ割り当てプロファイラーの記録</span><span class="sxs-lookup"><span data-stu-id="c778c-121">Record heap allocations profiler</span></span>  
> ![ヒープ割り当てプロファイラーの記録][ImageRecordHeap]  

## <span data-ttu-id="c778c-123">ヒープ割り当てタイムラインの読み取り</span><span class="sxs-lookup"><span data-stu-id="c778c-123">Read a heap allocation timeline</span></span>  

<span data-ttu-id="c778c-124">ヒープ割り当てのタイムラインには、オブジェクトが作成されている場所と保持パスが示されます。</span><span class="sxs-lookup"><span data-stu-id="c778c-124">The heap allocation timeline shows where objects are being created and identifies the retaining path.</span></span>  <span data-ttu-id="c778c-125">[図 3](#figure-3)では、一番上にあるバーに、新しいオブジェクトがヒープで見つかったことが示されます。</span><span class="sxs-lookup"><span data-stu-id="c778c-125">In [Figure 3](#figure-3), the bars at the top indicate when new objects are found in the heap.</span></span>  

<span data-ttu-id="c778c-126">各バーの高さは、最近割り当てられたオブジェクトのサイズに対応し、バーの色は、それらのオブジェクトが最終的なヒープスナップショットでまだ存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c778c-126">The height of each bar corresponds to the size of the recently allocated objects, and the color of the bars indicate whether or not those objects are still live in the final heap snapshot.</span></span>  <span data-ttu-id="c778c-127">青いバーは、タイムラインの最後にあるオブジェクトを示します。灰色のバーは、タイムラインで割り当てられたが、ガベージコレクションされているオブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="c778c-127">Blue bars indicate objects that are still live at the end of the timeline, Gray bars indicate objects that were allocated during the timeline, but have since been garbage collected.</span></span>  

> ##### <span data-ttu-id="c778c-128">図 3</span><span class="sxs-lookup"><span data-stu-id="c778c-128">Figure 3</span></span>  
> <span data-ttu-id="c778c-129">**タイムラインスナップショットの割り当てインストルメンテーション**</span><span class="sxs-lookup"><span data-stu-id="c778c-129">**Allocation instrumentation on timeline** snapshot</span></span>  
> ![タイムラインスナップショットの割り当てインストルメンテーション][ImageCollected]  

<!--In [Figure 4](#figure-4), an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple click actions  -->  

<span data-ttu-id="c778c-131">上のタイムラインのスライダーを使用して、特定のスナップショットを拡大し、その時点で最近割り当てられたオブジェクトを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="c778c-131">You are able to use the sliders in the timeline above to zoom into that particular snapshot and see the objects that were recently allocated at that point:</span></span>  

> ##### <span data-ttu-id="c778c-132">図 4</span><span class="sxs-lookup"><span data-stu-id="c778c-132">Figure 4</span></span>  
> <span data-ttu-id="c778c-133">スナップショットの拡大</span><span class="sxs-lookup"><span data-stu-id="c778c-133">Zoom into snapshot</span></span>  
> ![スナップショットの拡大][ImageSliders]  

<span data-ttu-id="c778c-135">ヒープ内の特定のオブジェクトをクリックすると、ヒープスナップショットの下の部分に保持ツリーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c778c-135">Clicking on a specific object in the heap shows the retaining tree in the bottom portion of the heap snapshot.</span></span>  <span data-ttu-id="c778c-136">オブジェクトへの保持パスを調べることで、オブジェクトが収集されなかった理由を理解するために十分な情報を得ることができます。また、不要な参照を削除するために必要なコードの変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c778c-136">Examining the retaining path to the object should give you enough information to understand why the object was not collected, and you should make the necessary code changes to remove the unnecessary reference.</span></span>  

## <span data-ttu-id="c778c-137">関数によるメモリ割り当てを表示する</span><span class="sxs-lookup"><span data-stu-id="c778c-137">View memory allocation by function</span></span>   

<span data-ttu-id="c778c-138">JavaScript 関数によるメモリ割り当てを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c778c-138">You are able to view memory allocation by JavaScript function.</span></span>  <span data-ttu-id="c778c-139">詳細については、「[関数によるメモリ割り当てを調査][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c778c-139">See [Investigate memory allocation by function][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction] for more information.</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageObjectTracker]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png "図 1: タイムラインの割り当てインストルメンテーション"  
[ImageRecordHeap]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png "図 2: ヒープ割り当てプロファイラーの記録"  
[ImageCollected]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-memory-allocation-timelines-snapshot.msft.png "図 3: タイムラインスナップショットの割り当てインストルメンテーション"  
[ImageSliders]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png "図 4: スナップショットにズームする"  

<!-- links -->  

[DevToolsOpenIndex]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge (Chromium) DevTools を開く"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: /microsoft-edge/devtools-guide-chromium/memory-problems/index#investigate-memory-allocation-by-function "関数によるメモリ割り当てを調べる-メモリの問題を解決する"  

<!--[HeapProfiler]: ../profile/memory-problems/heap-snapshots ""  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "Microsoft Edge チャネルをダウンロードする"  

> [!NOTE]
> <span data-ttu-id="c778c-147">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c778c-147">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c778c-148">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler)にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="c778c-148">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c778c-150">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c778c-150">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
