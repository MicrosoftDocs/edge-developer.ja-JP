---
title: JavaScript の実行時間を短縮する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0e198be3e1cef53590a24bfaa2382746ced299ed
ms.sourcegitcommit: 0342d99bf8d3212068890bab0e1e960afa507c02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611872"
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





# <span data-ttu-id="7e6b5-103">JavaScript の実行時間を短縮する</span><span class="sxs-lookup"><span data-stu-id="7e6b5-103">Speed Up JavaScript Runtime</span></span>   




<span data-ttu-id="7e6b5-104">**メモリ**パネルを使用して負荷の高い機能を特定します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-104">Identify expensive functions using the **Memory** panel.</span></span>  

> ##### <span data-ttu-id="7e6b5-105">図 1</span><span class="sxs-lookup"><span data-stu-id="7e6b5-105">Figure 1</span></span>  
> <span data-ttu-id="7e6b5-106">サンプリングプロファイル</span><span class="sxs-lookup"><span data-stu-id="7e6b5-106">Sampling Profiles</span></span>  
> ![サンプリングプロファイル][ImageCpuProfile]  

### <span data-ttu-id="7e6b5-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="7e6b5-108">Summary</span></span>  

*   <span data-ttu-id="7e6b5-109">呼び出された関数と、**メモリ**パネルの割り当てサンプリングで必要なメモリの量を記録します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** panel.</span></span>  
*   <span data-ttu-id="7e6b5-110">プロファイルを炎のグラフとして視覚化します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-110">Visualize your profiles as a flame chart.</span></span>  

## <span data-ttu-id="7e6b5-111">サンプリングプロファイルを記録する</span><span class="sxs-lookup"><span data-stu-id="7e6b5-111">Record a Sampling Profile</span></span>  

<span data-ttu-id="7e6b5-112">JavaScript で jank に気付いた場合は、サンプリングプロファイルを収集します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="7e6b5-113">サンプリングプロファイルは、ページ内の関数で実行時間が消費される場所を示します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-113">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="7e6b5-114">DevTools の**メモリ**パネルに移動します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-114">Go to the **Memory** panel of DevTools.</span></span>  
1.  <span data-ttu-id="7e6b5-115">[**割り当てのサンプリング**] ラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-115">Select the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="7e6b5-116">**[スタート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-116">Select **Start**.</span></span>  
1.  <span data-ttu-id="7e6b5-117">分析しようとしている内容に応じて、ページをもう一度読み込むか、ページを操作するか、またはページを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-117">Depending on what you are trying to analyze, you may either reload the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="7e6b5-118">完了したら、[**停止**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-118">Select the **Stop** button when you are finished.</span></span>  

> [!NOTE]
> <span data-ttu-id="7e6b5-119">また、[コンソールユーティリティ API][DevtoolsConsoleUtilities]を使って、コマンドラインからプロファイルの記録とグループ化を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <span data-ttu-id="7e6b5-120">サンプリングプロファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="7e6b5-120">View Sampling Profile</span></span>  

<span data-ttu-id="7e6b5-121">録音が終了すると、DevTools は、記録されたデータを使って、[**サンプリングプロファイル**] の下に**メモリ**パネルを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="7e6b5-122">既定のビューは [**ヘビー] (ボトムアップ)** です。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-122">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="7e6b5-123">このビューでは、パフォーマンスに最も影響を及ぼしている関数を確認し、その機能への呼び出しパスを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-123">This view enables you to see which functions had the most impact on performance and examine the calling paths to those functions.</span></span>  

### <span data-ttu-id="7e6b5-124">並べ替え順序を変更する</span><span class="sxs-lookup"><span data-stu-id="7e6b5-124">Change sort order</span></span>   

<span data-ttu-id="7e6b5-125">並べ替え順序を変更するには、[**フォーカス選択**された関数フォーカス選択関数] の横にあるドロップダウンメニューを選択し、 ![ ][ImageFocusIcon] 次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-125">To change the sorting order, select the dropdown menu next to the **focus selected function** ![focus selected function][ImageFocusIcon] icon and then choose one of the following options.</span></span>

<span data-ttu-id="7e6b5-126">**グラフ**。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-126">**Chart**.</span></span>  <span data-ttu-id="7e6b5-127">記録の時系列グラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-127">Displays a chronological chart of the recording.</span></span>  

> ##### <span data-ttu-id="7e6b5-128">図 2</span><span class="sxs-lookup"><span data-stu-id="7e6b5-128">Figure 2</span></span>  
> <span data-ttu-id="7e6b5-129">炎のグラフ</span><span class="sxs-lookup"><span data-stu-id="7e6b5-129">Flame chart</span></span>  
> ![炎のグラフ][ImageFlameChart]  

<span data-ttu-id="7e6b5-131">**ヘビー (ボトムアップ)**</span><span class="sxs-lookup"><span data-stu-id="7e6b5-131">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="7e6b5-132">パフォーマンスに影響を与えて関数を一覧表示し、関数への呼び出しパスを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-132">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="7e6b5-133">これは既定のビューです。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-133">This is the default view.</span></span>  

> ##### <span data-ttu-id="7e6b5-134">図 3</span><span class="sxs-lookup"><span data-stu-id="7e6b5-134">Figure 3</span></span>  
> <span data-ttu-id="7e6b5-135">ヘビーグラフ</span><span class="sxs-lookup"><span data-stu-id="7e6b5-135">Heavy chart</span></span>  
> ![ヘビーグラフ][ImageHeavyChart]  

<span data-ttu-id="7e6b5-137">**ツリー \ (上から下へ)**</span><span class="sxs-lookup"><span data-stu-id="7e6b5-137">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="7e6b5-138">呼び出し履歴の先頭から、呼び出し元の構造体の全体像が示されます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-138">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

> ##### <span data-ttu-id="7e6b5-139">図 4</span><span class="sxs-lookup"><span data-stu-id="7e6b5-139">Figure 4</span></span>  
> <span data-ttu-id="7e6b5-140">ツリーグラフ</span><span class="sxs-lookup"><span data-stu-id="7e6b5-140">Tree chart</span></span>  
> ![ツリーグラフ][ImageTreeChart]  

### <span data-ttu-id="7e6b5-142">除外関数</span><span class="sxs-lookup"><span data-stu-id="7e6b5-142">Exclude functions</span></span>   

<span data-ttu-id="7e6b5-143">サンプリングプロファイルから関数を除外するには、関数を選択して選択し、[選択した**関数**を除外する] アイコンを選択し ![ ][ImageExcludeIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-143">To exclude a function from your Sampling Profile, select it to select it and then select the **exclude selected function** ![exclude selected function][ImageExcludeIcon] icon.</span></span>  <span data-ttu-id="7e6b5-144">除外関数 \ (子 \) の要求関数 \ (親 \) には、除外された関数 \ (子) に割り当てられた割り当て済みのメモリが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-144">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="7e6b5-145">[すべて**の関数を復元**] を選択して、 ![ 除外さ ][ImageRestoreIcon] れたすべての関数を記録に戻します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-145">Select the **restore all functions** ![restore all functions][ImageRestoreIcon] icon to restore all excluded functions back into the recording.</span></span>  

## <span data-ttu-id="7e6b5-146">サンプリングプロファイルをグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="7e6b5-146">View Sampling Profile as Chart</span></span>   

<span data-ttu-id="7e6b5-147">グラフビューでは、時間の経過に伴うサンプリングプロファイルが視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-147">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="7e6b5-148">[サンプリングプロファイルを記録](#record-a-sampling-profile)したら、[[並べ替え順序](#change-sort-order)] を [**グラフ**] に変更して、記録を炎グラフとして表示します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-148">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

> ##### <span data-ttu-id="7e6b5-149">図 5</span><span class="sxs-lookup"><span data-stu-id="7e6b5-149">Figure 5</span></span>  
> <span data-ttu-id="7e6b5-150">炎のグラフビュー</span><span class="sxs-lookup"><span data-stu-id="7e6b5-150">Flame chart view</span></span>  
> ![炎のグラフビュー][ImageFlameChartView]  

<span data-ttu-id="7e6b5-152">炎のグラフは、2つの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-152">The flame chart is split into two parts.</span></span>  

| | <span data-ttu-id="7e6b5-153">領域</span><span class="sxs-lookup"><span data-stu-id="7e6b5-153">Part</span></span> | <span data-ttu-id="7e6b5-154">説明</span><span class="sxs-lookup"><span data-stu-id="7e6b5-154">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="7e6b5-155">件</span><span class="sxs-lookup"><span data-stu-id="7e6b5-155">1</span></span> | <span data-ttu-id="7e6b5-156">概要</span><span class="sxs-lookup"><span data-stu-id="7e6b5-156">Overview</span></span> | <span data-ttu-id="7e6b5-157">レコーディング全体の鳥ビュー。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-157">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="7e6b5-158">バーの高さは、通話スタックの深度に対応しています。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-158">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="7e6b5-159">そのため、バーが大きくなるほど、さらに多くのコールスタックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-159">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="7e6b5-160">両面</span><span class="sxs-lookup"><span data-stu-id="7e6b5-160">2</span></span> | <span data-ttu-id="7e6b5-161">通話スタック</span><span class="sxs-lookup"><span data-stu-id="7e6b5-161">Call Stacks</span></span> | <span data-ttu-id="7e6b5-162">これは、記録中に呼び出された関数の詳細ビューです。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-162">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="7e6b5-163">横軸は time と縦軸で、通話スタックです。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-163">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="7e6b5-164">スタックは、上から順に並べて整理されます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-164">The stacks are organized top-down.</span></span>  <span data-ttu-id="7e6b5-165">そのため、先頭の関数は、その下にある関数の下にあります。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-165">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="7e6b5-166">関数はランダムに色付けされます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-166">Functions are colored randomly.</span></span>  <span data-ttu-id="7e6b5-167">他のパネルで使用されている色との関連付けはありません。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-167">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="7e6b5-168">ただし、各ランタイムでパターンを表示できるように、呼び出し時には関数の色が常に同じになります。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-168">However, functions are always colored the same across invocations so that you are able to see patterns in each runtime.</span></span>  

> ##### <span data-ttu-id="7e6b5-169">図 6</span><span class="sxs-lookup"><span data-stu-id="7e6b5-169">Figure 6</span></span>  
> <span data-ttu-id="7e6b5-170">注釈付きの炎のグラフ</span><span class="sxs-lookup"><span data-stu-id="7e6b5-170">Annotated flame chart</span></span>  
> ![注釈付きの炎のグラフ][ImageAnnotatedFlameChart]  

<span data-ttu-id="7e6b5-172">長い通話スタックは必ずしも重大ではありません。これは、多くの関数が呼び出されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-172">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="7e6b5-173">ただし、ワイドバーは、関数が完了するまでに時間がかかりすぎることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-173">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="7e6b5-174">これらは最適化の候補です。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-174">These are candidates for optimization.</span></span>  

### <span data-ttu-id="7e6b5-175">記録の特定の部分を拡大する</span><span class="sxs-lookup"><span data-stu-id="7e6b5-175">Zoom in on specific parts of recording</span></span>   

<span data-ttu-id="7e6b5-176">呼び出し履歴の特定の部分を拡大するには、マウスを選択してから、[概要] にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-176">Select, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="7e6b5-177">拡大すると、選択した記録の一部が自動的に通話スタックに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-177">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

> ##### <span data-ttu-id="7e6b5-178">図 7</span><span class="sxs-lookup"><span data-stu-id="7e6b5-178">Figure 7</span></span>  
> <span data-ttu-id="7e6b5-179">拡大されたグラフ</span><span class="sxs-lookup"><span data-stu-id="7e6b5-179">Chart zoomed</span></span>  
> ![拡大されたグラフ][ImageFlameChartZoomed]  

### <span data-ttu-id="7e6b5-181">関数の詳細の表示</span><span class="sxs-lookup"><span data-stu-id="7e6b5-181">View function details</span></span>   

<span data-ttu-id="7e6b5-182">[関数] を選択して、[**ソース**] パネルで定義を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-182">Select on a function to view the definition in the **Sources** panel.</span></span>  

<span data-ttu-id="7e6b5-183">関数の上にマウスポインターを移動すると、名前とタイミングのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-183">Hover over a function to display the name and timing data.</span></span>  <span data-ttu-id="7e6b5-184">以下の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-184">The following information is provided.</span></span>  

| <span data-ttu-id="7e6b5-185">詳しく</span><span class="sxs-lookup"><span data-stu-id="7e6b5-185">Detail</span></span> | <span data-ttu-id="7e6b5-186">説明</span><span class="sxs-lookup"><span data-stu-id="7e6b5-186">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="7e6b5-187">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="7e6b5-187">Name</span></span>** | <span data-ttu-id="7e6b5-188">関数の名前。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-188">The name of the function.</span></span>  |  
| **<span data-ttu-id="7e6b5-189">自己サイズ</span><span class="sxs-lookup"><span data-stu-id="7e6b5-189">Self size</span></span>** | <span data-ttu-id="7e6b5-190">関数のステートメントのみを含む、関数の現在の呼び出しのサイズ。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-190">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="7e6b5-191">合計サイズ</span><span class="sxs-lookup"><span data-stu-id="7e6b5-191">Total size</span></span>** | <span data-ttu-id="7e6b5-192">この関数と呼び出された関数の現在の呼び出しのサイズ。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-192">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="7e6b5-193">URL</span><span class="sxs-lookup"><span data-stu-id="7e6b5-193">URL</span></span>** | <span data-ttu-id="7e6b5-194">Where の形式での関数定義の場所は、関数が定義されている `base.js:261` `base.js` ファイルの名前であり、 `261` 定義の行番号です。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-194">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

> ##### <span data-ttu-id="7e6b5-195">図 8</span><span class="sxs-lookup"><span data-stu-id="7e6b5-195">Figure 8</span></span>  
> <span data-ttu-id="7e6b5-196">グラフでの関数の詳細の表示</span><span class="sxs-lookup"><span data-stu-id="7e6b5-196">Viewing functions details in chart</span></span>  
> ![グラフでの関数の詳細の表示][ImageFunctionsDetails]  

<!--## Feedback   -->  



<!-- image links -->  

[ImageExcludeIcon]: /microsoft-edge/devtools-guide-chromium/media/exclude-icon.msft.png  
[ImageFocusIcon]: /microsoft-edge/devtools-guide-chromium/media/images/focus-icon.msft.png  
[ImageRestoreIcon]: /microsoft-edge/devtools-guide-chromium/media/images/restore-icon.msft.png  

[ImageCpuProfile]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png "図 1: プロファイルのサンプリング"  
[ImageFlameChart]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png "図 2: 炎の図"  
[ImageHeavyChart]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png "図 3: ヘビーチャート"  
[ImageTreeChart]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png "図 4: ツリーグラフ"  
[ImageFlameChartView]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png "図 5: 炎のグラフビュー"  
[ImageAnnotatedFlameChart]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png "図 6: 注釈付きの炎のグラフ"  
[ImageFlameChartZoomed]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png "図 7: 拡大表示されたグラフ"  
[ImageFunctionsDetails]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png "図 8: 関数の詳細をグラフで表示する"  

<!-- links -->  

[DevtoolsConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "コンソールユーティリティ API リファレンス"  
[DevtoolsConsoleUtilitiesProfile]: /microsoft-edge/devtools-guide-chromium/console/utilities#profile "プロファイル-コンソールユーティリティ API リファレンス"  
[DevtoolsConsoleUtilitiesProfileEnd]: /microsoft-edge/devtools-guide-chromium/console/utilities#profileend "profileEnd 本体のユーティリティ API リファレンス"  

> [!NOTE]
> <span data-ttu-id="7e6b5-209">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-209">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7e6b5-210">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)にあり、 [Kayce basques][KayceBasques]テクニカルライター、Chrome devtools & Lighthouse \) および[Meggin Kearney][MegginKearney] \ (Tech writer) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-210">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7e6b5-212">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7e6b5-212">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
