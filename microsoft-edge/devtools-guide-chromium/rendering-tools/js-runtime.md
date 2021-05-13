---
description: DevTools メモリ パネルを使用してMicrosoft Edge関数を識別します。
title: JavaScript ランタイムを高速化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bbac00ab46e205fb692cc3de3e5f08ba854b0911
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565086"
---
<!-- Copyright Kayce Basques and Meggin Kearney

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License. -->
# <a name="speed-up-javascript-runtime"></a><span data-ttu-id="ea630-104">JavaScript ランタイムを高速化する</span><span class="sxs-lookup"><span data-stu-id="ea630-104">Speed up JavaScript runtime</span></span>  

<span data-ttu-id="ea630-105">メモリ ツールを使用して、高価な **関数を識別** します。</span><span class="sxs-lookup"><span data-stu-id="ea630-105">Identify expensive functions using the **Memory** tool.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="サンプル プロファイル" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="ea630-107">サンプル プロファイル</span><span class="sxs-lookup"><span data-stu-id="ea630-107">Sample Profiles</span></span>  
:::image-end:::  

### <a name="summary"></a><span data-ttu-id="ea630-108">要約</span><span class="sxs-lookup"><span data-stu-id="ea630-108">Summary</span></span>  

*   <span data-ttu-id="ea630-109">メモリ ツールの割り当てサンプリングを使用して、呼び出された関数と、各関数が必要とするメモリの量を **正確に記録** します。</span><span class="sxs-lookup"><span data-stu-id="ea630-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** tool.</span></span>  
*   <span data-ttu-id="ea630-110">プロファイルを炎上グラフとして視覚化します。</span><span class="sxs-lookup"><span data-stu-id="ea630-110">Visualize your profiles as a flame chart.</span></span>  
    
## <a name="record-a-sampling-profile"></a><span data-ttu-id="ea630-111">サンプリング プロファイルの記録</span><span class="sxs-lookup"><span data-stu-id="ea630-111">Record a Sampling Profile</span></span>  

<span data-ttu-id="ea630-112">JavaScript で jank に気付いた場合は、サンプリング プロファイルを収集します。</span><span class="sxs-lookup"><span data-stu-id="ea630-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="ea630-113">サンプリング プロファイルは、ページ内の関数に実行時間が費やされる場所を示します。</span><span class="sxs-lookup"><span data-stu-id="ea630-113">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="ea630-114">DevTools **のメモリ** ツールに移動します。</span><span class="sxs-lookup"><span data-stu-id="ea630-114">Navigate to the **Memory** tool of DevTools.</span></span>  
1.  <span data-ttu-id="ea630-115">[割り当 **てサンプリング] ラジオ ボタン** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea630-115">Choose the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="ea630-116">[スタート **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ea630-116">Choose **Start**.</span></span>  
1.  <span data-ttu-id="ea630-117">分析しようとしている内容に応じて、ページを更新するか、ページを操作するか、ページを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea630-117">Depending on what you are trying to analyze, you may either refresh the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="ea630-118">完了したら **、[停止** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ea630-118">Choose the **Stop** button when you are finished.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="ea630-119">コンソール ユーティリティ API [を使用して][DevtoolsConsoleUtilities] 、コマンド ラインからプロファイルを記録およびグループ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea630-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <a name="view-sampling-profile"></a><span data-ttu-id="ea630-120">サンプリング プロファイルの表示</span><span class="sxs-lookup"><span data-stu-id="ea630-120">View Sampling Profile</span></span>  

<span data-ttu-id="ea630-121">録音が完了すると、DevTools は [\*\*\*\*\*\*サンプリング\*\*プロファイル] の [メモリ] パネルに、レコーディングのデータを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea630-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="ea630-122">既定のビューは **Heavy \(Bottom Up\) です**。</span><span class="sxs-lookup"><span data-stu-id="ea630-122">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="ea630-123">このビューでは、パフォーマンスに最も影響を与えた関数を確認し、各関数の要求パスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ea630-123">This view allows you to review which functions had the most impact on performance and examine the requesting path for each function.</span></span>  

### <a name="change-sort-order"></a><span data-ttu-id="ea630-124">並べ替え順序の変更</span><span class="sxs-lookup"><span data-stu-id="ea630-124">Change sort order</span></span>  

<span data-ttu-id="ea630-125">並べ替え順序を変更するには、フォーカス選択関数 **\(** フォーカス選択関数 \) アイコンの横にあるドロップダウン メニューを選択し、次のいずれかのオプション ![ ](../media/focus-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea630-125">To change the sorting order, select the dropdown menu next to the **focus selected function** \(![focus selected function](../media/focus-icon.msft.png)\) icon and then choose one of the following options.</span></span>

<span data-ttu-id="ea630-126">**グラフ**.</span><span class="sxs-lookup"><span data-stu-id="ea630-126">**Chart**.</span></span>  <span data-ttu-id="ea630-127">記録の時系列グラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="ea630-127">Displays a chronological chart of the recording.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="フレーム グラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="ea630-129">フレーム グラフ</span><span class="sxs-lookup"><span data-stu-id="ea630-129">Flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="ea630-130">**Heavy \(Bottom Up\)**.</span><span class="sxs-lookup"><span data-stu-id="ea630-130">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="ea630-131">パフォーマンスに影響を与える関数を一覧表示し、関数への呼び出しパスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ea630-131">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="ea630-132">これは既定のビューです。</span><span class="sxs-lookup"><span data-stu-id="ea630-132">This is the default view.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="重いグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="ea630-134">重いグラフ</span><span class="sxs-lookup"><span data-stu-id="ea630-134">Heavy chart</span></span>  
:::image-end:::  

<span data-ttu-id="ea630-135">**Tree \(Top Down\)**.</span><span class="sxs-lookup"><span data-stu-id="ea630-135">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="ea630-136">呼び出し履歴の上部から始まる呼び出し構造の全体像を示します。</span><span class="sxs-lookup"><span data-stu-id="ea630-136">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="ツリー グラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   <span data-ttu-id="ea630-138">ツリー グラフ</span><span class="sxs-lookup"><span data-stu-id="ea630-138">Tree chart</span></span>  
:::image-end:::  

### <a name="exclude-functions"></a><span data-ttu-id="ea630-139">関数を除外する</span><span class="sxs-lookup"><span data-stu-id="ea630-139">Exclude functions</span></span>  

<span data-ttu-id="ea630-140">サンプリング プロファイルから関数を除外するには、それを選択し、選択した **関数を除外** する \( 選択した関数 ![ \) を除外するボタン ](../media/exclude-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea630-140">To exclude a function from your Sampling Profile, choose it and then choose the **exclude selected function** \(![exclude selected function](../media/exclude-icon.msft.png)\) button.</span></span>  <span data-ttu-id="ea630-141">除外された関数 \(child\) の要求関数 \(parent\) は、除外された関数 \(child\) に割り当てられた割り当てられたメモリで課金されます。</span><span class="sxs-lookup"><span data-stu-id="ea630-141">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="ea630-142">[すべての **関数を復元する** ] \( [すべての関数を復元する\] ボタンを選択して、除外されているすべての関数を記録 ![ ](../media/restore-icon.msft.png) に戻します。</span><span class="sxs-lookup"><span data-stu-id="ea630-142">Choose the **restore all functions** \(![restore all functions](../media/restore-icon.msft.png)\) button to restore all excluded functions back into the recording.</span></span>  

## <a name="view-sampling-profile-as-chart"></a><span data-ttu-id="ea630-143">サンプリング プロファイルをグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="ea630-143">View Sampling Profile as Chart</span></span>  

<span data-ttu-id="ea630-144">グラフ ビューは、サンプリング プロファイルの時間の間に視覚的な表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea630-144">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="ea630-145">サンプリング プロファイル [を記録した後、](#record-a-sampling-profile)並べ替え順序を [グラフ] に変更して、録音をフレーム [グラフとして](#change-sort-order) 表示 **します**。</span><span class="sxs-lookup"><span data-stu-id="ea630-145">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="フレーム グラフ ビュー" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="ea630-147">フレーム グラフ ビュー</span><span class="sxs-lookup"><span data-stu-id="ea630-147">Flame chart view</span></span>  
:::image-end:::  

<span data-ttu-id="ea630-148">フレーム グラフは 2 つの部分に分割されます。</span><span class="sxs-lookup"><span data-stu-id="ea630-148">The flame chart is split into two parts.</span></span>  

| <span data-ttu-id="ea630-149">index</span><span class="sxs-lookup"><span data-stu-id="ea630-149">index</span></span> | <span data-ttu-id="ea630-150">パーツ</span><span class="sxs-lookup"><span data-stu-id="ea630-150">Part</span></span> | <span data-ttu-id="ea630-151">説明</span><span class="sxs-lookup"><span data-stu-id="ea630-151">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="ea630-152">1</span><span class="sxs-lookup"><span data-stu-id="ea630-152">1</span></span> | <span data-ttu-id="ea630-153">概要</span><span class="sxs-lookup"><span data-stu-id="ea630-153">Overview</span></span> | <span data-ttu-id="ea630-154">記録全体の鳥の目のビュー。</span><span class="sxs-lookup"><span data-stu-id="ea630-154">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="ea630-155">バーの高さは、呼び出し履歴の深さに対応します。</span><span class="sxs-lookup"><span data-stu-id="ea630-155">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="ea630-156">そのため、バーが高いほど、呼び出し履歴は深くなります。</span><span class="sxs-lookup"><span data-stu-id="ea630-156">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="ea630-157">2</span><span class="sxs-lookup"><span data-stu-id="ea630-157">2</span></span> | <span data-ttu-id="ea630-158">呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="ea630-158">Call Stacks</span></span> | <span data-ttu-id="ea630-159">これは、記録中に呼び出された関数の詳細なビューです。</span><span class="sxs-lookup"><span data-stu-id="ea630-159">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="ea630-160">横軸は時間、縦軸は呼び出し履歴です。</span><span class="sxs-lookup"><span data-stu-id="ea630-160">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="ea630-161">スタックはトップダウンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ea630-161">The stacks are organized top-down.</span></span>  <span data-ttu-id="ea630-162">したがって、上の関数は、その下の関数を呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="ea630-162">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="ea630-163">関数はランダムに色付けされます。</span><span class="sxs-lookup"><span data-stu-id="ea630-163">Functions are colored randomly.</span></span>  <span data-ttu-id="ea630-164">他のパネルで使用される色には相関関係はありません。</span><span class="sxs-lookup"><span data-stu-id="ea630-164">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="ea630-165">ただし、関数は常に呼び出し間で同じ色を付け、各ランタイムでパターンを観察できます。</span><span class="sxs-lookup"><span data-stu-id="ea630-165">However, functions are always colored the same across invocations so that you may observe patterns in each runtime.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="注釈付きフレーム グラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   <span data-ttu-id="ea630-167">注釈付きフレーム グラフ</span><span class="sxs-lookup"><span data-stu-id="ea630-167">Annotated flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="ea630-168">高い呼び出し履歴は必ずしも重要ではなく、多くの関数が呼び出されたという意味です。</span><span class="sxs-lookup"><span data-stu-id="ea630-168">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="ea630-169">ただし、幅の広いバーは、関数の完了に長い時間がかかったという意味です。</span><span class="sxs-lookup"><span data-stu-id="ea630-169">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="ea630-170">これらは最適化の候補です。</span><span class="sxs-lookup"><span data-stu-id="ea630-170">These are candidates for optimization.</span></span>  

### <a name="zoom-in-on-specific-parts-of-recording"></a><span data-ttu-id="ea630-171">記録の特定の部分を拡大する</span><span class="sxs-lookup"><span data-stu-id="ea630-171">Zoom in on specific parts of recording</span></span>  

<span data-ttu-id="ea630-172">通話履歴の特定の部分を拡大するには、マウスの概要を左右に選択、保持、ドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ea630-172">Choose, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="ea630-173">ズームすると、選択した録音の一部が通話履歴に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea630-173">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="グラフのズーム" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   <span data-ttu-id="ea630-175">グラフのズーム</span><span class="sxs-lookup"><span data-stu-id="ea630-175">Chart zoomed</span></span>  
:::image-end:::  

### <a name="view-function-details"></a><span data-ttu-id="ea630-176">関数の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ea630-176">View function details</span></span>  

<span data-ttu-id="ea630-177">ソース ツールで定義を表示する関数 **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ea630-177">Choose a function to view the definition in the **Sources** tool.</span></span>  

<span data-ttu-id="ea630-178">関数にカーソルを合わせると、名前とタイミング データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea630-178">Hover on a function to display the name and timing data.</span></span>  <span data-ttu-id="ea630-179">以下の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ea630-179">The following information is provided.</span></span>  

| <span data-ttu-id="ea630-180">詳細</span><span class="sxs-lookup"><span data-stu-id="ea630-180">Detail</span></span> | <span data-ttu-id="ea630-181">説明</span><span class="sxs-lookup"><span data-stu-id="ea630-181">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="ea630-182">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="ea630-182">Name</span></span>** | <span data-ttu-id="ea630-183">関数の名前。</span><span class="sxs-lookup"><span data-stu-id="ea630-183">The name of the function.</span></span>  |  
| **<span data-ttu-id="ea630-184">自己サイズ</span><span class="sxs-lookup"><span data-stu-id="ea630-184">Self size</span></span>** | <span data-ttu-id="ea630-185">関数の現在の呼び出しのサイズ (関数内のステートメントのみを含む)。</span><span class="sxs-lookup"><span data-stu-id="ea630-185">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="ea630-186">合計サイズ</span><span class="sxs-lookup"><span data-stu-id="ea630-186">Total size</span></span>** | <span data-ttu-id="ea630-187">この関数の現在の呼び出しのサイズと、呼び出された関数。</span><span class="sxs-lookup"><span data-stu-id="ea630-187">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="ea630-188">URL</span><span class="sxs-lookup"><span data-stu-id="ea630-188">URL</span></span>** | <span data-ttu-id="ea630-189">where 形式の関数定義の場所は、関数が定義されているファイルの名前であり、定義の行 `base.js:261` `base.js` `261` 番号です。</span><span class="sxs-lookup"><span data-stu-id="ea630-189">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="グラフで関数の詳細を表示する" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   <span data-ttu-id="ea630-191">グラフで関数の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ea630-191">View functions details in chart</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="ea630-192">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="ea630-192">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "profile - コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd - コンソール ユーティリティ API リファレンス |Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="ea630-196">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="ea630-196">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ea630-197">元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)見つかり[、Kayce バス][KayceBasques]ク人 \(Technical Writer, Chrome DevTools \& ライトハウス\) と[Meggin Kearney][MegginKearney] \(Tech Writer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="ea630-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ea630-199">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ea630-199">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
