---
description: Microsoft Edge DevTools メモリパネルを使用して、負荷の高い機能を特定します。
title: JavaScript ランタイムを高速化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 27afe999083470cde0cc0fabf76d0d1ab54e6562
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993584"
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

# <span data-ttu-id="0eb32-104">JavaScript の実行時間を短縮する</span><span class="sxs-lookup"><span data-stu-id="0eb32-104">Speed up JavaScript runtime</span></span>  

<span data-ttu-id="0eb32-105">**メモリ**パネルを使用して負荷の高い機能を特定します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-105">Identify expensive functions using the **Memory** panel.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="サンプルプロファイル" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="0eb32-107">サンプルプロファイル</span><span class="sxs-lookup"><span data-stu-id="0eb32-107">Sample Profiles</span></span>  
:::image-end:::  

### <span data-ttu-id="0eb32-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="0eb32-108">Summary</span></span>  

*   <span data-ttu-id="0eb32-109">呼び出された関数と、 **メモリ** パネルの割り当てサンプリングで必要なメモリの量を記録します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** panel.</span></span>  
*   <span data-ttu-id="0eb32-110">プロファイルを炎のグラフとして視覚化します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-110">Visualize your profiles as a flame chart.</span></span>  
    
## <span data-ttu-id="0eb32-111">サンプリングプロファイルを記録する</span><span class="sxs-lookup"><span data-stu-id="0eb32-111">Record a Sampling Profile</span></span>  

<span data-ttu-id="0eb32-112">JavaScript で jank に気付いた場合は、サンプリングプロファイルを収集します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="0eb32-113">サンプリングプロファイルは、ページ内の関数で実行時間が消費される場所を示します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-113">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="0eb32-114">DevTools の **メモリ** パネルに移動します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-114">Go to the **Memory** panel of DevTools.</span></span>  
1.  <span data-ttu-id="0eb32-115">[ **割り当てのサンプリング** ] ラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-115">Select the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="0eb32-116">**[スタート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-116">Select **Start**.</span></span>  
1.  <span data-ttu-id="0eb32-117">分析しようとしている内容に応じて、ページをもう一度読み込むか、ページを操作するか、またはページを実行します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-117">Depending on what you are trying to analyze, you may either reload the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="0eb32-118">完了したら、[ **停止** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-118">Select the **Stop** button when you are finished.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="0eb32-119">また、 [コンソールユーティリティ API][DevtoolsConsoleUtilities] を使って、コマンドラインからプロファイルの記録とグループ化を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <span data-ttu-id="0eb32-120">サンプリングプロファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="0eb32-120">View Sampling Profile</span></span>  

<span data-ttu-id="0eb32-121">録音が終了すると、DevTools は、記録されたデータを使って、[**サンプリングプロファイル**] の下に**メモリ**パネルを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="0eb32-122">既定のビューは [ **ヘビー] (ボトムアップ)** です。</span><span class="sxs-lookup"><span data-stu-id="0eb32-122">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="0eb32-123">このビューでは、パフォーマンスに最も影響を及ぼしている関数を確認し、その機能への呼び出しパスを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-123">This view enables you to see which functions had the most impact on performance and examine the calling paths to those functions.</span></span>  

### <span data-ttu-id="0eb32-124">並べ替え順序を変更する</span><span class="sxs-lookup"><span data-stu-id="0eb32-124">Change sort order</span></span>  

<span data-ttu-id="0eb32-125">並べ替え順序を変更するには、[ **選択した関数** \ (フォーカス選択された関数 \)] の横にあるドロップダウンメニューを選択し、 ![ ][ImageFocusIcon] 次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-125">To change the sorting order, select the dropdown menu next to the **focus selected function** \(![focus selected function][ImageFocusIcon]\) icon and then choose one of the following options.</span></span>

<span data-ttu-id="0eb32-126">**グラフ**。</span><span class="sxs-lookup"><span data-stu-id="0eb32-126">**Chart**.</span></span>  <span data-ttu-id="0eb32-127">記録の時系列グラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-127">Displays a chronological chart of the recording.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="炎のグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="0eb32-129">炎のグラフ</span><span class="sxs-lookup"><span data-stu-id="0eb32-129">Flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="0eb32-130">**ヘビー (ボトムアップ)**</span><span class="sxs-lookup"><span data-stu-id="0eb32-130">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="0eb32-131">パフォーマンスに影響を与えて関数を一覧表示し、関数への呼び出しパスを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-131">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="0eb32-132">これは既定のビューです。</span><span class="sxs-lookup"><span data-stu-id="0eb32-132">This is the default view.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="ヘビーグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="0eb32-134">ヘビーグラフ</span><span class="sxs-lookup"><span data-stu-id="0eb32-134">Heavy chart</span></span>  
:::image-end:::  

<span data-ttu-id="0eb32-135">**ツリー \ (上から下へ)**</span><span class="sxs-lookup"><span data-stu-id="0eb32-135">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="0eb32-136">呼び出し履歴の先頭から、呼び出し元の構造体の全体像が示されます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-136">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="ツリーグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   <span data-ttu-id="0eb32-138">ツリーグラフ</span><span class="sxs-lookup"><span data-stu-id="0eb32-138">Tree chart</span></span>  
:::image-end:::  

### <span data-ttu-id="0eb32-139">除外関数</span><span class="sxs-lookup"><span data-stu-id="0eb32-139">Exclude functions</span></span>  

<span data-ttu-id="0eb32-140">サンプリングプロファイルから関数を除外するには、関数を選び、[ **選択した関数を除外** \ ( ![ 選択した関数 \ を除外 ][ImageExcludeIcon] )] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-140">To exclude a function from your Sampling Profile, select it and then select the **exclude selected function** \(![exclude selected function][ImageExcludeIcon]\) button.</span></span>  <span data-ttu-id="0eb32-141">除外関数 \ (子 \) の要求関数 \ (親 \) には、除外された関数 \ (子) に割り当てられた割り当て済みのメモリが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-141">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="0eb32-142">すべての関数 **を復元** する (すべての関数を復元) ボタンを選択して、除外され ![ ][ImageRestoreIcon] た関数をすべて記録に戻します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-142">Select the **restore all functions** \(![restore all functions][ImageRestoreIcon]\) button to restore all excluded functions back into the recording.</span></span>  

## <span data-ttu-id="0eb32-143">サンプリングプロファイルをグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="0eb32-143">View Sampling Profile as Chart</span></span>  

<span data-ttu-id="0eb32-144">グラフビューでは、時間の経過に伴うサンプリングプロファイルが視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-144">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="0eb32-145">[サンプリングプロファイルを記録](#record-a-sampling-profile)したら、[[並べ替え順序](#change-sort-order)] を [**グラフ**] に変更して、記録を炎グラフとして表示します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-145">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="炎のグラフビュー" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="0eb32-147">炎のグラフビュー</span><span class="sxs-lookup"><span data-stu-id="0eb32-147">Flame chart view</span></span>  
:::image-end:::  

<span data-ttu-id="0eb32-148">炎のグラフは、2つの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="0eb32-148">The flame chart is split into two parts.</span></span>  

| <span data-ttu-id="0eb32-149">位置</span><span class="sxs-lookup"><span data-stu-id="0eb32-149">index</span></span> | <span data-ttu-id="0eb32-150">領域</span><span class="sxs-lookup"><span data-stu-id="0eb32-150">Part</span></span> | <span data-ttu-id="0eb32-151">説明</span><span class="sxs-lookup"><span data-stu-id="0eb32-151">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="0eb32-152">件</span><span class="sxs-lookup"><span data-stu-id="0eb32-152">1</span></span> | <span data-ttu-id="0eb32-153">概要</span><span class="sxs-lookup"><span data-stu-id="0eb32-153">Overview</span></span> | <span data-ttu-id="0eb32-154">レコーディング全体の鳥ビュー。</span><span class="sxs-lookup"><span data-stu-id="0eb32-154">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="0eb32-155">バーの高さは、通話スタックの深度に対応しています。</span><span class="sxs-lookup"><span data-stu-id="0eb32-155">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="0eb32-156">そのため、バーが大きくなるほど、さらに多くのコールスタックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-156">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="0eb32-157">両面</span><span class="sxs-lookup"><span data-stu-id="0eb32-157">2</span></span> | <span data-ttu-id="0eb32-158">通話スタック</span><span class="sxs-lookup"><span data-stu-id="0eb32-158">Call Stacks</span></span> | <span data-ttu-id="0eb32-159">これは、記録中に呼び出された関数の詳細ビューです。</span><span class="sxs-lookup"><span data-stu-id="0eb32-159">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="0eb32-160">横軸は time と縦軸で、通話スタックです。</span><span class="sxs-lookup"><span data-stu-id="0eb32-160">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="0eb32-161">スタックは、上から順に並べて整理されます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-161">The stacks are organized top-down.</span></span>  <span data-ttu-id="0eb32-162">そのため、先頭の関数は、その下にある関数の下にあります。</span><span class="sxs-lookup"><span data-stu-id="0eb32-162">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="0eb32-163">関数はランダムに色付けされます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-163">Functions are colored randomly.</span></span>  <span data-ttu-id="0eb32-164">他のパネルで使用されている色との関連付けはありません。</span><span class="sxs-lookup"><span data-stu-id="0eb32-164">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="0eb32-165">ただし、各ランタイムでパターンを表示できるように、呼び出し時には関数の色が常に同じになります。</span><span class="sxs-lookup"><span data-stu-id="0eb32-165">However, functions are always colored the same across invocations so that you are able to see patterns in each runtime.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="注釈付きの炎のグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   <span data-ttu-id="0eb32-167">注釈付きの炎のグラフ</span><span class="sxs-lookup"><span data-stu-id="0eb32-167">Annotated flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="0eb32-168">長い通話スタックは必ずしも重大ではありません。これは、多くの関数が呼び出されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-168">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="0eb32-169">ただし、ワイドバーは、関数が完了するまでに時間がかかりすぎることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-169">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="0eb32-170">これらは最適化の候補です。</span><span class="sxs-lookup"><span data-stu-id="0eb32-170">These are candidates for optimization.</span></span>  

### <span data-ttu-id="0eb32-171">記録の特定の部分を拡大する</span><span class="sxs-lookup"><span data-stu-id="0eb32-171">Zoom in on specific parts of recording</span></span>  

<span data-ttu-id="0eb32-172">呼び出し履歴の特定の部分を拡大するには、マウスを選択してから、[概要] にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0eb32-172">Select, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="0eb32-173">拡大すると、選択した記録の一部が自動的に通話スタックに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-173">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="拡大されたグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   <span data-ttu-id="0eb32-175">拡大されたグラフ</span><span class="sxs-lookup"><span data-stu-id="0eb32-175">Chart zoomed</span></span>  
:::image-end:::  

### <span data-ttu-id="0eb32-176">関数の詳細の表示</span><span class="sxs-lookup"><span data-stu-id="0eb32-176">View function details</span></span>  

<span data-ttu-id="0eb32-177">[関数] を選択して、[ **ソース** ] パネルで定義を表示します。</span><span class="sxs-lookup"><span data-stu-id="0eb32-177">Select on a function to view the definition in the **Sources** panel.</span></span>  

<span data-ttu-id="0eb32-178">関数の上にマウスポインターを移動すると、名前とタイミングのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-178">Hover over a function to display the name and timing data.</span></span>  <span data-ttu-id="0eb32-179">以下の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-179">The following information is provided.</span></span>  

| <span data-ttu-id="0eb32-180">詳しく</span><span class="sxs-lookup"><span data-stu-id="0eb32-180">Detail</span></span> | <span data-ttu-id="0eb32-181">説明</span><span class="sxs-lookup"><span data-stu-id="0eb32-181">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="0eb32-182">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="0eb32-182">Name</span></span>** | <span data-ttu-id="0eb32-183">関数の名前。</span><span class="sxs-lookup"><span data-stu-id="0eb32-183">The name of the function.</span></span>  |  
| **<span data-ttu-id="0eb32-184">自己サイズ</span><span class="sxs-lookup"><span data-stu-id="0eb32-184">Self size</span></span>** | <span data-ttu-id="0eb32-185">関数のステートメントのみを含む、関数の現在の呼び出しのサイズ。</span><span class="sxs-lookup"><span data-stu-id="0eb32-185">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="0eb32-186">合計サイズ</span><span class="sxs-lookup"><span data-stu-id="0eb32-186">Total size</span></span>** | <span data-ttu-id="0eb32-187">この関数と呼び出された関数の現在の呼び出しのサイズ。</span><span class="sxs-lookup"><span data-stu-id="0eb32-187">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="0eb32-188">URL</span><span class="sxs-lookup"><span data-stu-id="0eb32-188">URL</span></span>** | <span data-ttu-id="0eb32-189">Where の形式での関数定義の場所は、関数が定義されている `base.js:261` `base.js` ファイルの名前であり、 `261` 定義の行番号です。</span><span class="sxs-lookup"><span data-stu-id="0eb32-189">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="関数の詳細をグラフで表示する" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   <span data-ttu-id="0eb32-191">関数の詳細をグラフで表示する</span><span class="sxs-lookup"><span data-stu-id="0eb32-191">View functions details in chart</span></span>  
:::image-end:::  

## <span data-ttu-id="0eb32-192">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="0eb32-192">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExcludeIcon]: ../media/exclude-icon.msft.png  
[ImageFocusIcon]: ../media/focus-icon.msft.png  
[ImageRestoreIcon]: ../media/restore-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "プロファイル-本体ユーティリティー API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd-本体ユーティリティー API リファレンス |Microsoft ドキュメント"  

> [!NOTE]
> <span data-ttu-id="0eb32-196">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0eb32-196">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0eb32-197">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) にあり、 [Kayce basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) および [Meggin Kearney][MegginKearney] \ (Tech writer \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="0eb32-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0eb32-199">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0eb32-199">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
