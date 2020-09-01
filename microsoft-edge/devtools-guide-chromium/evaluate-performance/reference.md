---
title: パフォーマンス分析リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 59e2f67d773102554b96749690fae51da09428a8
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984145"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  







# <span data-ttu-id="1b262-103">業績分析のリファレンス</span><span class="sxs-lookup"><span data-stu-id="1b262-103">Performance analysis reference</span></span>   



<span data-ttu-id="1b262-104">このページでは、パフォーマンスの分析に関連する Microsoft Edge DevTools の機能について包括的にご参照ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-104">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="1b262-105">[Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使用してページのパフォーマンスを分析する方法については、ガイド付きチュートリアルの「[実行時のパフォーマンスの分析][DevtoolsEvaluatePerformanceGettingStarted]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-105">See [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="1b262-106">レコードのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="1b262-106">Record performance</span></span>   

### <span data-ttu-id="1b262-107">実行時のパフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="1b262-107">Record runtime performance</span></span>   

<span data-ttu-id="1b262-108">読み込みとは異なり、実行中にページのパフォーマンスを分析する場合は、実行時のパフォーマンスを記録します。</span><span class="sxs-lookup"><span data-stu-id="1b262-108">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="1b262-109">分析対象のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1b262-109">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="1b262-110">DevTools で [ **パフォーマンス** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b262-110">Click the **Performance** tab in DevTools.</span></span>  
1.  <span data-ttu-id="1b262-111">[ **レコーディング** \ ( ![ レコード ][ImageRecordIcon] \)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b262-111">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="1b262-113">Record</span><span class="sxs-lookup"><span data-stu-id="1b262-113">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="1b262-114">ページを操作します。</span><span class="sxs-lookup"><span data-stu-id="1b262-114">Interact with the page.</span></span>  <span data-ttu-id="1b262-115">DevTools は、操作の結果として発生するすべてのページアクティビティを記録します。</span><span class="sxs-lookup"><span data-stu-id="1b262-115">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="1b262-116">[ **記録** ] をもう一度クリックするか、[ **停止** ] をクリックして記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="1b262-116">Click **Record** again or click **Stop** to stop recording.</span></span>  
    
### <span data-ttu-id="1b262-117">読み込みのパフォーマンスの記録</span><span class="sxs-lookup"><span data-stu-id="1b262-117">Record load performance</span></span>   

<span data-ttu-id="1b262-118">実行時とは異なり、読み込み中にページのパフォーマンスを分析する場合は、読み込みのパフォーマンスを記録します。</span><span class="sxs-lookup"><span data-stu-id="1b262-118">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="1b262-119">分析対象のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1b262-119">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="1b262-120">DevTools の [ **パフォーマンス** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b262-120">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="1b262-121">[ **ページの更新** ] をクリックします ([ ![ ページの更新] ][ImageRefreshPageIcon] )。</span><span class="sxs-lookup"><span data-stu-id="1b262-121">Click **Refresh page** \(![Refresh Page][ImageRefreshPageIcon]\).</span></span>  <span data-ttu-id="1b262-122">DevTools では、ページが更新されている間はパフォーマンスのメトリックが記録され、読み込みが完了してから数秒間、自動的に記録が停止します。</span><span class="sxs-lookup"><span data-stu-id="1b262-122">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="ページの更新" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="1b262-124">ページの更新</span><span class="sxs-lookup"><span data-stu-id="1b262-124">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="1b262-125">DevTools は、ほとんどのアクティビティが発生したレコーディングの部分に自動的にズームインします。</span><span class="sxs-lookup"><span data-stu-id="1b262-125">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="ページ読み込みの記録" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="1b262-127">ページ読み込みの記録</span><span class="sxs-lookup"><span data-stu-id="1b262-127">A page-load recording</span></span>  
:::image-end:::  

### <span data-ttu-id="1b262-128">記録中にスクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="1b262-128">Capture screenshots while recording</span></span>   

<span data-ttu-id="1b262-129">記録中にすべてのフレームのスクリーンショットをキャプチャするには、[ **スクリーンショット** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1b262-129">Enable the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="スクリーンショットのチェックボックス" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="1b262-131">**スクリーンショット**のチェックボックス</span><span class="sxs-lookup"><span data-stu-id="1b262-131">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-132">スクリーンショットを操作する方法について [は、「スクリーンショットを表示](#view-a-screenshot) する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-132">See [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <span data-ttu-id="1b262-133">記録中にガベージコレクションを強制する</span><span class="sxs-lookup"><span data-stu-id="1b262-133">Force garbage collection while recording</span></span>   

<span data-ttu-id="1b262-134">ページを記録しているときに、[ **ガーベジ** の収集 \ (ガーベジの収集)] をクリックして ![ ][ImageCollectGarbageIcon] ガーベジコレクションを強制します。</span><span class="sxs-lookup"><span data-stu-id="1b262-134">While you are recording a page, click **Collect garbage** \(![Collect garbage][ImageCollectGarbageIcon]\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="ガーベジの収集" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="1b262-136">ガーベジの収集</span><span class="sxs-lookup"><span data-stu-id="1b262-136">Collect garbage</span></span>  
:::image-end:::  

### <span data-ttu-id="1b262-137">レコーディング設定を表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-137">Show recording settings</span></span>   

<span data-ttu-id="1b262-138">[ **キャプチャ設定** ] ( ![ キャプチャ設定 ][ImageCaptureSettingsIcon] ) をクリックして、devtools がパフォーマンスの記録をキャプチャする方法に関連する詳細設定を公開します。</span><span class="sxs-lookup"><span data-stu-id="1b262-138">Click **Capture settings** \(![Capture settings][ImageCaptureSettingsIcon]\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text="[キャプチャの設定] セクション" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="1b262-140">[ **キャプチャの設定** ] セクション</span><span class="sxs-lookup"><span data-stu-id="1b262-140">The **Capture Settings** section</span></span>  
:::image-end:::  

### <span data-ttu-id="1b262-141">JavaScript のサンプルを無効にする</span><span class="sxs-lookup"><span data-stu-id="1b262-141">Disable JavaScript samples</span></span>   

<span data-ttu-id="1b262-142">記録の **メイン** セクションには、記録中に呼び出された JavaScript 関数の詳細なコールスタックが既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-142">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="1b262-143">次の呼び出し履歴を無効にするには:</span><span class="sxs-lookup"><span data-stu-id="1b262-143">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="1b262-144">[ **キャプチャの設定** ] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b262-144">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="1b262-145">「 [レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-145">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="1b262-146">[ **JavaScript のサンプルを無効** にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1b262-146">Enable the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="1b262-147">ページの記録を取ります。</span><span class="sxs-lookup"><span data-stu-id="1b262-147">Take a recording of the page.</span></span>  
    
<span data-ttu-id="1b262-148">次の2つの図は、JavaScript サンプルの無効化と有効化の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="1b262-148">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="1b262-149">サンプリングが無効になっている場合、記録の **メイン** セクションは、JavaScript のすべての呼び出し履歴を省略しているため、非常に短くなります。</span><span class="sxs-lookup"><span data-stu-id="1b262-149">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="JS サンプルが無効になっている場合のレコーディングの例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="1b262-151">JS サンプルが無効になっている場合のレコーディングの例</span><span class="sxs-lookup"><span data-stu-id="1b262-151">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="JS サンプルが有効になっている場合のレコーディングの例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="1b262-153">JS サンプルが有効になっている場合のレコーディングの例</span><span class="sxs-lookup"><span data-stu-id="1b262-153">An example of a recording when JS samples are enabled</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="1b262-154">記録中にネットワークを調整する</span><span class="sxs-lookup"><span data-stu-id="1b262-154">Throttle the network while recording</span></span>   

<span data-ttu-id="1b262-155">記録中にネットワークを調整するには:</span><span class="sxs-lookup"><span data-stu-id="1b262-155">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="1b262-156">[ **キャプチャの設定** ] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b262-156">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="1b262-157">「 [レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-157">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="1b262-158">**ネットワーク**を適切な調整レベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="1b262-158">Set **Network** to the desired level of throttling.</span></span>  
    
### <span data-ttu-id="1b262-159">記録中に CPU を調整する</span><span class="sxs-lookup"><span data-stu-id="1b262-159">Throttle the CPU while recording</span></span>   

<span data-ttu-id="1b262-160">記録中に CPU を調整するには:</span><span class="sxs-lookup"><span data-stu-id="1b262-160">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="1b262-161">[ **キャプチャの設定** ] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b262-161">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="1b262-162">「 [レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-162">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="1b262-163">**CPU**を目的の調整レベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="1b262-163">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="1b262-164">調整は、コンピューターの機能を基準とします。</span><span class="sxs-lookup"><span data-stu-id="1b262-164">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="1b262-165">たとえば、 **2 倍速の遅延** オプションを使うと、CPU は通常の2倍の速度で動作します。</span><span class="sxs-lookup"><span data-stu-id="1b262-165">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="1b262-166">モバイルデバイスのアーキテクチャはデスクトップとノート pc とは大きく異なりますので、DevTools はモバイルデバイスの Cpu を実際にシミュレートするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1b262-166">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <span data-ttu-id="1b262-167">高度な描画インストルメンテーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="1b262-167">Enable advanced paint instrumentation</span></span>   

<span data-ttu-id="1b262-168">詳細な描画インストルメンテーションを表示するには:</span><span class="sxs-lookup"><span data-stu-id="1b262-168">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="1b262-169">[ **キャプチャの設定** ] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b262-169">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="1b262-170">「 [レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-170">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="1b262-171">**[高度な描画インストルメンテーション (低速) を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1b262-171">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="1b262-172">ペイント情報を操作する方法については、「 [レイヤーの表示](#view-layers-information) と [ペイントプロファイラーの表示](#view-paint-profiler)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b262-172">To learn how to interact with the paint information, see [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <span data-ttu-id="1b262-173">レコーディングを保存する</span><span class="sxs-lookup"><span data-stu-id="1b262-173">Save a recording</span></span>   

<span data-ttu-id="1b262-174">レコーディングを保存するには、右クリックして、[ **プロファイルの保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b262-174">To save a recording, right-click and select **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="プロフィールの保存" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="1b262-176">プロフィールの保存</span><span class="sxs-lookup"><span data-stu-id="1b262-176">Save Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="1b262-177">レコーディングを読み込む</span><span class="sxs-lookup"><span data-stu-id="1b262-177">Load a recording</span></span>   

<span data-ttu-id="1b262-178">レコーディングを読み込むには、右クリックして、[ **プロファイルの読み込み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b262-178">To load a recording, right-click and select **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="プロファイルの読み込み" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="1b262-180">プロファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="1b262-180">Load Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="1b262-181">前の記録をクリアする</span><span class="sxs-lookup"><span data-stu-id="1b262-181">Clear the previous recording</span></span>   

<span data-ttu-id="1b262-182">レコーディングを作成した後、[ **レコーディング** のクリア] (レコーディングを ![ クリア ][ImageClearRecordingIcon] ) を押して、[ **パフォーマンス** ] パネルからその記録をクリアします。</span><span class="sxs-lookup"><span data-stu-id="1b262-182">After making a recording, press **Clear recording** \(![Clear recording][ImageClearRecordingIcon]\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="レコーディングのクリア" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="1b262-184">レコーディングのクリア</span><span class="sxs-lookup"><span data-stu-id="1b262-184">Clear recording</span></span>**  
:::image-end:::  

## <span data-ttu-id="1b262-185">パフォーマンスの記録を分析する</span><span class="sxs-lookup"><span data-stu-id="1b262-185">Analyze a performance recording</span></span>   

<span data-ttu-id="1b262-186">[実行時のパフォーマンス](#record-runtime-performance)または[レコードの読み込みのパフォーマンス](#record-load-performance)を記録すると、**パフォーマンス**パネルに多くのデータが表示され、発生した処理のパフォーマンスを分析できます。</span><span class="sxs-lookup"><span data-stu-id="1b262-186">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <span data-ttu-id="1b262-187">レコーディングの一部を選択する</span><span class="sxs-lookup"><span data-stu-id="1b262-187">Select a portion of a recording</span></span>   

<span data-ttu-id="1b262-188">[ **概要** ] でマウスを左右にドラッグして、レコーディングの一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b262-188">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="1b262-189">**概要**は、 **FPS**、 **CPU**、および**ネット**チャートを含むセクションです。</span><span class="sxs-lookup"><span data-stu-id="1b262-189">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="概要の上でマウスをドラッグして拡大" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="1b262-191">**概要**の上でマウスをドラッグして拡大</span><span class="sxs-lookup"><span data-stu-id="1b262-191">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-192">キーボードを使用して部分を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b262-192">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="1b262-193">**メイン**セクションの背景をクリックするか、[**操作**]、[**ネットワーク**]、[ **GPU**] などの横にあるセクションのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b262-193">Click on the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="1b262-194">このキーボードワークフローは、これらのセクションのいずれかがフォーカスされている場合にのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="1b262-194">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="1b262-195">それぞれ、、、[左へ移動]、[縮小]、 `W` `A` `S` [右へ移動] の各キーを使用し `D` ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-195">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="1b262-196">トラックパッドを使用して部分を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b262-196">To select a portion using a trackpad:</span></span>  

1.  <span data-ttu-id="1b262-197">[ **概要** ] セクションまたは [ **詳細** ] セクションの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="1b262-197">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="1b262-198">[ **概要** ] セクションは、 **FPS**、 **CPU**、および **正味** グラフを含む領域です。</span><span class="sxs-lookup"><span data-stu-id="1b262-198">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="1b262-199">[ **詳細** ] セクションは、 **メイン** セクション、[ **操作** ] セクションなどを含む領域です。</span><span class="sxs-lookup"><span data-stu-id="1b262-199">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="1b262-200">2本の指で上方向にスワイプして縮小し、左方向にスワイプして左へ移動し、下方向にスワイプしてズームインし、右にスワイプして右に移動します。</span><span class="sxs-lookup"><span data-stu-id="1b262-200">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="1b262-201">**メイン**セクションまたはそのいずれかの近隣にある長い炎のグラフをスクロールするには、上下にドラッグしてクリックしたままにします。</span><span class="sxs-lookup"><span data-stu-id="1b262-201">To scroll a long flame chart in the **Main** section or any of the neighbors, click and hold while dragging up and down.</span></span>  <span data-ttu-id="1b262-202">左または右にドラッグして、録音中の部分を移動します。</span><span class="sxs-lookup"><span data-stu-id="1b262-202">Drag left and right to move what portion of the recording is selected.</span></span>  

### <span data-ttu-id="1b262-203">アクティビティを検索する</span><span class="sxs-lookup"><span data-stu-id="1b262-203">Search activities</span></span>   

<span data-ttu-id="1b262-204">[ `Control` + `F` \ (Windows \)] または [ `Command` + `F` \ (macOS \)] を押して、**パフォーマンス**パネルの下部にある [検索] ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b262-204">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="検索ボックス" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="1b262-206">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="1b262-206">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-207">クエリに一致するアクティビティを移動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b262-207">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="1b262-208">**前**の \ ( ![ 前の ][ImagePreviousIcon] \) と**次**の \ (次の \) ボタンを使用し ![ ][ImageNextIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-208">Use the **Previous** \(![Previous][ImagePreviousIcon]\) and **Next** \(![Next][ImageNextIcon]\) buttons.</span></span>  
*   <span data-ttu-id="1b262-209">を押して [前へ] を選択するか、[ `Shift` + `Enter` 次へ] を `Enter` 選択します。</span><span class="sxs-lookup"><span data-stu-id="1b262-209">Press `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="1b262-210">クエリの設定を変更するには:</span><span class="sxs-lookup"><span data-stu-id="1b262-210">To modify query settings:</span></span>  

*   <span data-ttu-id="1b262-211">[ **大文字** と小文字を区別する] を押して ![ ][ImageSearchCaseIcon] 、クエリの大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="1b262-211">Press **Case sensitive** \(![Case sensitive][ImageSearchCaseIcon]\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="1b262-212">**Regex** ![ ][ImageSearchRegexIcon] クエリで正規表現を使用するには、regex \ (regex \) を押します。</span><span class="sxs-lookup"><span data-stu-id="1b262-212">Press **Regex** \(![Regex][ImageSearchRegexIcon]\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="1b262-213">検索ボックスを非表示にするには、 **[キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b262-213">To hide the search box, press **Cancel**.</span></span>  

### <span data-ttu-id="1b262-214">メインスレッドアクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="1b262-214">View main thread activity</span></span>   

<span data-ttu-id="1b262-215">**メイン**セクションを使って、ページのメインスレッドで発生したアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-215">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="メインセクション" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="1b262-217">**メイン**セクション</span><span class="sxs-lookup"><span data-stu-id="1b262-217">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-218">イベントをクリックすると、[ **概要** ] タブにそのイベントの詳細情報が表示されます。 DevTools では、選択したイベントの概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-218">Click on an event to view more information about it in the **Summary** tab.  DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="匿名関数の詳細については、[概要] タブを参照してください。" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="1b262-220">[ `anonymous` **概要** ] タブの関数についての詳細</span><span class="sxs-lookup"><span data-stu-id="1b262-220">More information about the `anonymous` function in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-221">DevTools は、炎グラフによるメインスレッドアクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-221">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="1b262-222">X 軸は、時間の経過に伴う記録を表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-222">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="1b262-223">Y 軸は、呼び出しスタックを表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-223">The y-axis represents the call stack.</span></span>  <span data-ttu-id="1b262-224">一番上にあるイベントは、その下にあるイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="1b262-224">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="炎のグラフ" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="1b262-226">炎のグラフ</span><span class="sxs-lookup"><span data-stu-id="1b262-226">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-227">上の図では、 `click` イベントが53で発生し `Function Call` `activitytabs.js` ています。</span><span class="sxs-lookup"><span data-stu-id="1b262-227">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="1b262-228">次 `Function Call` に、匿名関数が呼び出されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b262-228">Below `Function Call` you see that an anonymous function was called.</span></span>  <span data-ttu-id="1b262-229">呼び出された匿名関数が呼び出され `a` ます。これが呼び出され `wait` `Minor GC` ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-229">The anonymous function called `a`, which called `wait`, which called `Minor GC`.</span></span>  

<span data-ttu-id="1b262-230">DevTools では、スクリプトのランダムな色が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1b262-230">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="1b262-231">前の図では、1つのスクリプトからの関数呼び出しは色が緑になっています。</span><span class="sxs-lookup"><span data-stu-id="1b262-231">In the previous figure, function calls from one script are colored light green.</span></span>  <span data-ttu-id="1b262-232">別のスクリプトからの呼び出しは、色ベージュになります。</span><span class="sxs-lookup"><span data-stu-id="1b262-232">Calls from another script are colored beige.</span></span>  <span data-ttu-id="1b262-233">濃い黄色はスクリプトアクティビティを表し、紫色のイベントはレンダリングアクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-233">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="1b262-234">これらの暗い黄と紫色のイベントは、すべての記録で一貫しています。</span><span class="sxs-lookup"><span data-stu-id="1b262-234">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="1b262-235">JavaScript 呼び出しの詳細な炎グラフを非表示にする場合は、「 [javascript のサンプルを無効](#disable-javascript-samples) にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b262-235">See [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript calls.</span></span>  <span data-ttu-id="1b262-236">JS サンプルが無効になっている場合は、前の図などの上位レベルのイベントのみが表示され `Event: click` `Function Call` ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-236">When JS samples are disabled, you only see high-level events such as `Event: click` and `Function Call` from the previous figure.</span></span>  

### <span data-ttu-id="1b262-237">テーブルのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-237">View activities in a table</span></span>   

<span data-ttu-id="1b262-238">ページを記録したら、 **メイン** セクションに依存してアクティビティを分析する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1b262-238">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="1b262-239">DevTools には、アクティビティを分析するための3つの表形式ビューも用意されています。</span><span class="sxs-lookup"><span data-stu-id="1b262-239">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="1b262-240">各ビューには、次のような操作があります。</span><span class="sxs-lookup"><span data-stu-id="1b262-240">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="1b262-241">最も作業を引き起こしているルートアクティビティを表示するには、[ [通話ツリー] タブ](#the-call-tree-tab)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b262-241">When you want to view the root activities that cause the most work, use [the Call Tree tab](#the-call-tree-tab).</span></span>  
*   <span data-ttu-id="1b262-242">最も多くの時間を費やしたアクティビティを表示する場合は、[ [ボトムアップ] タブ](#the-bottom-up-tab)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b262-242">When you want to view the activities where the most time was directly spent, use [the Bottom-Up tab](#the-bottom-up-tab).</span></span>  
*   <span data-ttu-id="1b262-243">記録中に発生した順番でアクティビティを表示する場合は、 [[イベントログ] タブ](#the-event-log-tab)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b262-243">When you want to view the activities in the order in which they occurred during the recording, use [the Event Log tab](#the-event-log-tab).</span></span>  
    
> [!NOTE]
> <span data-ttu-id="1b262-244">次の3つのセクションはすべて同じデモを示しています。</span><span class="sxs-lookup"><span data-stu-id="1b262-244">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="1b262-245">[アクティビティ] タブの [デモ][ActivityTabsDemo]で、自分でデモを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b262-245">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <span data-ttu-id="1b262-246">ルートアクティビティ</span><span class="sxs-lookup"><span data-stu-id="1b262-246">Root activities</span></span>   

<span data-ttu-id="1b262-247">[**通話ツリー** ] タブ、[**ボトムアップ**] タブ、[**イベントログ**] の各セクションで説明されている**ルートアクティビティ**の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b262-247">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** tab, **Bottom-Up** tab, and **Event Log** sections.</span></span>  

<span data-ttu-id="1b262-248">ルートアクティビティは、ブラウザーが何らかの操作を実行する原因となります。</span><span class="sxs-lookup"><span data-stu-id="1b262-248">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="1b262-249">たとえば、ページをクリックすると、ブラウザーで `Event` ルートアクティビティとしてアクティビティが発生します。</span><span class="sxs-lookup"><span data-stu-id="1b262-249">For example, when you click a page, the browser fires an `Event` activity as the root activity.</span></span>  <span data-ttu-id="1b262-250">これにより、ハンドラーが実行される `Event` 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b262-250">That `Event` might cause a handler to run, and so on.</span></span>  

<span data-ttu-id="1b262-251">**メイン**セクションの炎チャートでは、ルートアクティビティはグラフの一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="1b262-251">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="1b262-252">[ **コールツリー** ] タブと [ **イベントログ** ] タブでは、ルートアクティビティはトップレベルのアイテムです。</span><span class="sxs-lookup"><span data-stu-id="1b262-252">In the **Call Tree** and **Event Log** tabs, root activities are the top-level items.</span></span>  

<span data-ttu-id="1b262-253">ルートアクティビティの例について [は、「通話ツリー」タブ](#the-call-tree-tab) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-253">See [The Call Tree tab](#the-call-tree-tab) for an example of root activities.</span></span>  

#### <span data-ttu-id="1b262-254">[通話ツリー] タブ</span><span class="sxs-lookup"><span data-stu-id="1b262-254">The Call Tree tab</span></span>   

<span data-ttu-id="1b262-255">[ **呼び出しツリー** ] タブを使用して、最も作業を発生させる [ルートアクティビティ](#root-activities) を表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-255">Use the **Call Tree** tab to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="1b262-256">[ **通話ツリー** ] タブには、レコーディングの選択した部分のアクティビティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-256">The **Call Tree** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="1b262-257">部分の選択方法については [、「レコーディングの一部を選択](#select-a-portion-of-a-recording) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b262-257">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="[通話ツリー] タブ" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="1b262-259">[ **通話ツリー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="1b262-259">The **Call Tree** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-260">上の図では、"and" など、" **アクティビティ** " 列の項目の最上位レベルが `Evaluate Script` `Parse HTML` ルートアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="1b262-260">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="1b262-261">入れ子は、呼び出しスタックを表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-261">The nesting represents the call stack.</span></span>  <span data-ttu-id="1b262-262">たとえば、上の図のように、という問題が `Parse HTML` 発生しました `Evaluate Script` `Compile Script` `(anonymous)` 。</span><span class="sxs-lookup"><span data-stu-id="1b262-262">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="1b262-263">**Self time** は、そのアクティビティに直接費やした時間を表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-263">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="1b262-264">**合計時間** は、そのアクティビティまたはいずれかの子に費やした時間を表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-264">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="1b262-265">[ **自己時刻**]、[ **時間の合計**]、または [ **アクティビティ** ] をクリックして、テーブルをその列で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="1b262-265">Click **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="1b262-266">[ **フィルター** ] テキストボックスを使用して、アクティビティ名ごとにイベントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="1b262-266">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="1b262-267">既定では、 **グループ化** メニューは [ **グループ化なし**] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-267">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="1b262-268">[ **グループ化** ] メニューを使用して、さまざまな条件に基づいてアクティビティテーブルを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="1b262-268">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="1b262-269">[最も高い **スタックを表示** ] をクリックし ![ ][ImageShowHeaviestStackIcon] て、 **アクティビティ** テーブルの右側に別のテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-269">Click **Show Heaviest Stack** \(![Show Heaviest Stack][ImageShowHeaviestStackIcon]\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="1b262-270">[アクティビティ] をクリックして、最も **重いスタック** テーブルにデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="1b262-270">Click on an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="1b262-271">最も大きな **スタック** テーブルには、選択したアクティビティのどの子が最も時間がかかるかが示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-271">The **Heaviest Stack** table shows you which children of the selected activity took the longest time to run.</span></span>  

#### <span data-ttu-id="1b262-272">[ボトムアップ] タブ</span><span class="sxs-lookup"><span data-stu-id="1b262-272">The Bottom-Up tab</span></span>   

<span data-ttu-id="1b262-273">[ **ボトムアップ** ] タブを使用して、集計で最も時間のかかるアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-273">Use the **Bottom-Up** tab to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="1b262-274">**下**のタブには、レコーディングの選択した部分のアクティビティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-274">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="1b262-275">部分の選択方法については [、「レコーディングの一部を選択](#select-a-portion-of-a-recording) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b262-275">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="[ボトムアップ] タブ" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="1b262-277">[ **ボトムアップ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="1b262-277">The **Bottom-Up** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-278">前の図の **メイン** セクションの炎のグラフでは、ほとんどの時間が実行されていたことについて説明し `Parse HTML` ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-278">In the **Main** section flame chart of the previous figure, see that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="1b262-279">前の図の **下部** にある [上位] タブのアクティビティは `Parse HTML` です。</span><span class="sxs-lookup"><span data-stu-id="1b262-279">The top activity in the **Bottom-Up** tab of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="1b262-280">**下**のタブでは、次の最も負荷の高いアクティビティが表示されて `Layout` います。</span><span class="sxs-lookup"><span data-stu-id="1b262-280">See in the **Bottom-Up** tab, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="1b262-281">[ **自己時刻** ] 列は、すべてのオカレンスにわたって、そのアクティビティで直接費やした合計時間を表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-281">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="1b262-282">[ **合計時間** 」列は、そのアクティビティまたはいずれかの子に費やした集計時間を表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-282">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <span data-ttu-id="1b262-283">[イベントログ] タブ</span><span class="sxs-lookup"><span data-stu-id="1b262-283">The Event Log tab</span></span>   

<span data-ttu-id="1b262-284">[ **イベントログ** ] タブを使用して、記録中に発生した順序でアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-284">Use the **Event Log** tab to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="1b262-285">[ **イベントログ** ] タブには、記録の選択されている部分のアクティビティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-285">The **Event Log** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="1b262-286">部分の選択方法については [、「レコーディングの一部を選択](#select-a-portion-of-a-recording) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b262-286">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="[イベントログ] タブ" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="1b262-288">[ **イベントログ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="1b262-288">The **Event Log** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-289">[ **開始時刻** ] 列は、そのアクティビティが開始されたポイントを表します。レコーディングの開始日を基準としています。</span><span class="sxs-lookup"><span data-stu-id="1b262-289">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="1b262-290">たとえば、 `175.7 ms` 前の図で選んだ項目の開始時刻は、記録を開始した後にアクティビティが175.7 ミリ秒で開始されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1b262-290">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="1b262-291">**Self time**列は、そのアクティビティに直接費やした時間を表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-291">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="1b262-292">**合計時間**列は、そのアクティビティまたはその子のいずれかに直接費やした時間を表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-292">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="1b262-293">[ **開始時刻**]、[ **自己時刻**]、または [ **合計時間** ] をクリックして、テーブルをその列で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="1b262-293">Click **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="1b262-294">[ **フィルター** ] テキストボックスを使って、名前でアクティビティをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="1b262-294">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="1b262-295">[ **継続時間** ] メニューを使用して、1ミリ秒または15ミリ秒未満のアクティビティを除外します。</span><span class="sxs-lookup"><span data-stu-id="1b262-295">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="1b262-296">既定では、[ **期間** ] メニューは [ **すべて**] に設定されており、すべてのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-296">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="1b262-297">**読み込み**、**スクリプト**、**レンダリング**、または**Painting**のチェックボックスを無効にして、それらのカテゴリのすべてのアクティビティをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="1b262-297">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <span data-ttu-id="1b262-298">GPU アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="1b262-298">View GPU activity</span></span>   

<span data-ttu-id="1b262-299">**Gpu セクションの**gpu アクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-299">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU セクション" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="1b262-301">**GPU**セクション</span><span class="sxs-lookup"><span data-stu-id="1b262-301">The **GPU** section</span></span>  
:::image-end:::  

### <span data-ttu-id="1b262-302">ラスターアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-302">View raster activity</span></span>   

<span data-ttu-id="1b262-303">**ラスターセクションで**ラスターアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-303">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="ラスターセクション" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="1b262-305">**ラスター**セクション</span><span class="sxs-lookup"><span data-stu-id="1b262-305">The **Raster** section</span></span>  
:::image-end:::  

### <span data-ttu-id="1b262-306">ビューの操作</span><span class="sxs-lookup"><span data-stu-id="1b262-306">View interactions</span></span>   

<span data-ttu-id="1b262-307">記録中に発生したユーザー操作を見つけて分析するには、[ **対話** ] セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b262-307">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="[操作] セクション" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="1b262-309">[ **操作** ] セクション</span><span class="sxs-lookup"><span data-stu-id="1b262-309">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-310">対話式の下部にある赤い線は、メインスレッドの待機に費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="1b262-310">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="1b262-311">[ファイルの **概要** ] タブで、操作をクリックして詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-311">Click an interaction to view more information about it in the **Summary** tab.</span></span>  

### <span data-ttu-id="1b262-312">1秒あたりのフレーム数 (FPS) の分析</span><span class="sxs-lookup"><span data-stu-id="1b262-312">Analyze frames per second (FPS)</span></span>   

<span data-ttu-id="1b262-313">DevTools には、1秒あたりのフレームの分析方法が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="1b262-313">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="1b262-314">[Fps チャート](#the-fps-chart)を使用して、記録中の fps の概要を把握します。</span><span class="sxs-lookup"><span data-stu-id="1b262-314">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="1b262-315">[[フレーム] セクション](#the-frames-section)を使用して、特定のフレームの所要時間を表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-315">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="1b262-316">ページの実行時に、fps のリアルタイムの推定に **fps メーター** を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b262-316">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="1b262-317">詳しく [は、「FPS メーターでリアルタイムのフレームを表示する](#view-frames-per-second-in-realtime-with-the-fps-meter)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-317">See [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <span data-ttu-id="1b262-318">FPS グラフ</span><span class="sxs-lookup"><span data-stu-id="1b262-318">The FPS chart</span></span>   

<span data-ttu-id="1b262-319">**FPS**グラフは、記録中のフレームレートの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="1b262-319">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="1b262-320">通常、緑色のバーが大きくなるほど、フレームレートが向上します。</span><span class="sxs-lookup"><span data-stu-id="1b262-320">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="1b262-321">**FPS**グラフの上に赤いバーが表示されるのは、ユーザーエクスペリエンスが損なわれている可能性が高いため、フレームレートが低下するという警告です。</span><span class="sxs-lookup"><span data-stu-id="1b262-321">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="1b262-323">**FPS**グラフ</span><span class="sxs-lookup"><span data-stu-id="1b262-323">The **FPS** chart</span></span>  
:::image-end:::  

#### <span data-ttu-id="1b262-324">[フレーム] セクション</span><span class="sxs-lookup"><span data-stu-id="1b262-324">The Frames section</span></span>   

<span data-ttu-id="1b262-325">**フレーム**セクションでは、特定のフレームの所要時間が正確に示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-325">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="1b262-326">Frame の上にマウスポインターを移動すると、ヒントが表示され、詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-326">Hover over a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="フレームの上にマウスポインターを置く" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="1b262-328">フレームの上にマウスポインターを置く</span><span class="sxs-lookup"><span data-stu-id="1b262-328">Hover over a frame</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-329">フレームをクリックすると、[ **概要** ] タブに、フレームに関するさらに詳しい情報が表示されます。 DevTools では、選択したフレームが青色で示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-329">Click on a frame to view even more information about the frame in the **Summary** tab.  DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="[概要] タブでフレームを表示する" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="1b262-331">[ **概要** ] タブでフレームを表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-331">View a frame in the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="1b262-332">ネットワーク要求を表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-332">View network requests</span></span>   

<span data-ttu-id="1b262-333">[ **ネットワーク** ] セクションを展開すると、記録中に発生した、ウォーターフォールのネットワーク要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-333">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="[ネットワーク] セクション" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="1b262-335">[ **ネットワーク** ] セクション</span><span class="sxs-lookup"><span data-stu-id="1b262-335">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-336">要求は、次のように色分けされます。</span><span class="sxs-lookup"><span data-stu-id="1b262-336">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="1b262-337">HTML: 青</span><span class="sxs-lookup"><span data-stu-id="1b262-337">HTML: Blue</span></span>  
*   <span data-ttu-id="1b262-338">CSS: 紫</span><span class="sxs-lookup"><span data-stu-id="1b262-338">CSS: Purple</span></span>  
*   <span data-ttu-id="1b262-339">JS: 黄</span><span class="sxs-lookup"><span data-stu-id="1b262-339">JS: Yellow</span></span>  
*   <span data-ttu-id="1b262-340">画像: 緑</span><span class="sxs-lookup"><span data-stu-id="1b262-340">Images: Green</span></span>  
    
<span data-ttu-id="1b262-341">[ファイルの **概要** ] タブで要求をクリックすると、詳細情報が表示されます。 たとえば、上の図では、[ **概要** ] タブには、[ **ネットワーク** ] セクションで選択された青い要求についての詳細情報が表示されています。</span><span class="sxs-lookup"><span data-stu-id="1b262-341">Click on a request to view more information about it in the **Summary** tab.  For example, in the previous figure, the **Summary** tab is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="1b262-342">要求の左上の濃い青色の正方形は、優先度の高い要求であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1b262-342">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="1b262-343">薄い青色の正方形は、優先度が低いことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1b262-343">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="1b262-344">たとえば、前の図では、青色の選択された要求の優先度は高く、緑の1つは優先度の低いものです。</span><span class="sxs-lookup"><span data-stu-id="1b262-344">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="1b262-345">次の図のうちの1つ目では、要求は `www.bing.com` 左側にある線で表され、中央に暗い部分と薄い部分があるバー、右側に線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-345">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="1b262-346">次の図の2に、[**ネットワーク**] パネルの [**タイミング**] タブに表示される同じ要求の対応表現を示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-346">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** tab of the **Network** panel.</span></span>  <span data-ttu-id="1b262-347">2つの表現が相互にマップされる方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-347">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="1b262-348">左側の行は、一連のイベントを含むすべての項目になり `Connection Start` ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-348">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="1b262-349">つまり、これはすべて、排他的な前にあり `Request Sent` ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-349">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="1b262-350">バーの光部分は `Request Sent` と `Waiting (TTFB)` です。</span><span class="sxs-lookup"><span data-stu-id="1b262-350">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="1b262-351">バーの暗い部分は `Content Download` です。</span><span class="sxs-lookup"><span data-stu-id="1b262-351">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="1b262-352">適切な行は、基本的にメインスレッドの待機に費やされた時間です。</span><span class="sxs-lookup"><span data-stu-id="1b262-352">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="1b262-353">これは、[ **タイミング** ] タブには表示されません。</span><span class="sxs-lookup"><span data-stu-id="1b262-353">This is not represented in the **Timing** tab.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="Www.bing.com 要求の線の表示" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="1b262-355">要求の線の表示 `www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="1b262-355">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="[ネットワーク] セクション" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="1b262-357">[ **ネットワーク** ] セクション</span><span class="sxs-lookup"><span data-stu-id="1b262-357">The **Network** section</span></span>  
<span data-ttu-id="1b262-358">::: イメージ終了:::</span><span class="sxs-lookup"><span data-stu-id="1b262-358">:      ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="1b262-359">メモリメトリックの表示</span><span class="sxs-lookup"><span data-stu-id="1b262-359">View memory metrics</span></span>   

<span data-ttu-id="1b262-360">[ **メモリ** ] チェックボックスを有効にして、最後の記録からメモリ指標を表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-360">Enable the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="メモリチェックボックス" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="1b262-362">**メモリ**チェックボックス</span><span class="sxs-lookup"><span data-stu-id="1b262-362">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-363">DevTools で、[**概要**] タブの上に新しい**メモリ**グラフが表示されます。 また、[**ヒープ**] という新しいグラフも表示**されます**。</span><span class="sxs-lookup"><span data-stu-id="1b262-363">DevTools displays a new **Memory** chart, above the **Summary** tab.  There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="1b262-364">**ヒープ**グラフは、**メモリ**グラフの**JS ヒープ**行と同じ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b262-364">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="メモリメトリック" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="1b262-366">メモリメトリック</span><span class="sxs-lookup"><span data-stu-id="1b262-366">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-367">グラフ上の色付きの線は、グラフ上の色付きのチェックボックスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="1b262-367">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="1b262-368">チェックボックスを無効にして、そのカテゴリをグラフから非表示にする。</span><span class="sxs-lookup"><span data-stu-id="1b262-368">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="1b262-369">グラフには、現在選択されているレコーディングの領域のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-369">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="1b262-370">たとえば、上の図では、 **メモリ** グラフは 400 ms マークの前後にあるメモリ使用量のみを 1750 ms マークに示しています。</span><span class="sxs-lookup"><span data-stu-id="1b262-370">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <span data-ttu-id="1b262-371">レコーディングの一部の継続時間を表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-371">View the duration of a portion of a recording</span></span>   

<span data-ttu-id="1b262-372">**Network**や**Main**などのセクションを分析するときに、特定のイベントの所要時間をより正確に予測する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b262-372">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="1b262-373">長押しして長押しし、 `Shift` 左または右にドラッグしてレコーディングの一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b262-373">Hold `Shift`, click and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="1b262-374">選択範囲の一番下にある DevTools は、その部分の所要時間を示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-374">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="レコーディングの一部の継続時間を表示する" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="1b262-376">レコーディングの一部の継続時間を表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-376">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <span data-ttu-id="1b262-377">スクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-377">View a screenshot</span></span>   

<span data-ttu-id="1b262-378">スクリーンショットを有効にする方法については、「 [記録中のスクリーンショットのキャプチャ](#capture-screenshots-while-recording) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-378">See [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to enable screenshots.</span></span>  

<span data-ttu-id="1b262-379">**概要**にマウスポインターを合わせると、その時点でページがどのように表示されたかを示すスクリーンショットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-379">Hover over the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="1b262-380">**概要**は、 **CPU**、 **FPS**、および**ネット**チャートを含むセクションです。</span><span class="sxs-lookup"><span data-stu-id="1b262-380">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="スクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="1b262-382">スクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-382">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-383">**フレーム**セクションのフレームをクリックしてスクリーンショットを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b262-383">You may also view screenshots by clicking a frame in the **Frames** section.</span></span>  <span data-ttu-id="1b262-384">DevTools では、[ **概要** ] タブにスクリーンショットの小さなバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-384">DevTools displays a small version of the screenshot in the **Summary** tab.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="[概要] タブにスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="1b262-386">[ **概要** ] タブにスクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-386">View a screenshot in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-387">[ **概要** ] タブでサムネイルをクリックして、スクリーンショットを拡大します。</span><span class="sxs-lookup"><span data-stu-id="1b262-387">Click the thumbnail in the **Summary** tab to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="[概要] タブでスクリーンショットを拡大する" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="1b262-389">[ **概要** ] タブでスクリーンショットを拡大する</span><span class="sxs-lookup"><span data-stu-id="1b262-389">Zoom into a screenshot from the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="1b262-390">レイヤー情報の表示</span><span class="sxs-lookup"><span data-stu-id="1b262-390">View layers information</span></span>   

<span data-ttu-id="1b262-391">フレームに関する高度なレイヤー情報を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b262-391">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="1b262-392">[高度な描画インストルメンテーションを有効に](#enable-advanced-paint-instrumentation)します。</span><span class="sxs-lookup"><span data-stu-id="1b262-392">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="1b262-393">**フレームセクションで**フレームを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b262-393">Select a frame in the **Frames** section.</span></span>  <span data-ttu-id="1b262-394">[開発ツール] では、[新しい **レイヤー** ] タブの [ **イベントログ** ] タブの横に、レイヤーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-394">DevTools displays information about the layers in the new **Layers** tab, next to the **Event Log** tab.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="[レイヤー] ウィンドウ" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="1b262-396">[ **レイヤー** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="1b262-396">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="1b262-397">レイヤーをポイントすると、図の中で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-397">Hover over a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="レイヤーを強調表示する" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="1b262-399">レイヤーを強調表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-399">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="1b262-400">ダイアグラムを移動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b262-400">To move the diagram:</span></span>  

*   <span data-ttu-id="1b262-401">**Pan Mode** ![ ][ImagePanModeIcon] X 軸と Y 軸に沿って移動するには、[パンモード \] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b262-401">Click **Pan Mode** \(![Pan Mode][ImagePanModeIcon]\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="1b262-402">**Rotate Mode** ![ ][ImageRotateModeIcon] Z 軸に沿って回転させるには、[回転モード \ (回転モード \)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b262-402">Click **Rotate Mode** \(![Rotate Mode][ImageRotateModeIcon]\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="1b262-403">[ **変形のリセット** ] ([ ![ 変形のリセット] ][ImageResetTransformIcon] ) をクリックして、図を元の位置にリセットします。</span><span class="sxs-lookup"><span data-stu-id="1b262-403">Click **Reset Transform** \(![Reset Transform][ImageResetTransformIcon]\) to reset the diagram to the original position.</span></span>  
    
### <span data-ttu-id="1b262-404">ペイントプロファイラーの表示</span><span class="sxs-lookup"><span data-stu-id="1b262-404">View paint profiler</span></span>   

<span data-ttu-id="1b262-405">ペイントイベントに関する詳細情報を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b262-405">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="1b262-406">[高度な描画インストルメンテーションを有効に](#enable-advanced-paint-instrumentation)します。</span><span class="sxs-lookup"><span data-stu-id="1b262-406">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="1b262-407">**メイン**セクションで**Paint**イベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b262-407">Select a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="[ペイントプロファイラー] タブ" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="1b262-409">[ **ペイントプロファイラー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="1b262-409">The **Paint Profiler** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="1b262-410">[レンダリング] タブでのレンダリングのパフォーマンスの分析</span><span class="sxs-lookup"><span data-stu-id="1b262-410">Analyze rendering performance with the Rendering tab</span></span>   

<span data-ttu-id="1b262-411">[ **レンダリング** ] タブの機能を使用すると、ページのレンダリングパフォーマンスを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="1b262-411">Use the features of the **Rendering** tab to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="1b262-412">[ **レンダリング** ] タブを開くには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b262-412">To open the **Rendering** tab:</span></span>  

1.  <span data-ttu-id="1b262-413">[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-413">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="1b262-414">入力を開始し `Rendering` 、を選択し `Show Rendering` ます。</span><span class="sxs-lookup"><span data-stu-id="1b262-414">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="1b262-415">DevTools は、DevTools ウィンドウの下部にある [ **レンダリング** ] タブを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-415">DevTools displays the **Rendering** tab at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="[レンダリング] タブ" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="1b262-417">[ **レンダリング** ] タブ</span><span class="sxs-lookup"><span data-stu-id="1b262-417">The **Rendering** tab</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="1b262-418">FPS メーターを使ってリアルタイムで1秒あたりのフレームを表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-418">View frames per second in realtime with the FPS meter</span></span>   

<span data-ttu-id="1b262-419">**FPS メーター**は、ビューポートの右上隅に表示されるオーバーレイです。</span><span class="sxs-lookup"><span data-stu-id="1b262-419">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="1b262-420">ページの実行時に、リアルタイムでの FPS の推定値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-420">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="1b262-421">**FPS メーター**を開くには:</span><span class="sxs-lookup"><span data-stu-id="1b262-421">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="1b262-422">[ **レンダリング** ] タブを開きます。 「 [レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-422">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="1b262-423">[ **FPS メーター** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1b262-423">Enable the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="1b262-425">**FPS メーター**</span><span class="sxs-lookup"><span data-stu-id="1b262-425">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="1b262-426">ペイントの点滅でリアルタイムで描画イベントを表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-426">View painting events in realtime with Paint Flashing</span></span>   

<span data-ttu-id="1b262-427">[ペイントのフラッシュ] を使って、ページ上のすべての描画イベントをリアルタイムで表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-427">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="1b262-428">ページの一部が再描画されるたびに、DevTools でそのセクションの輪郭が緑色で示されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-428">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="1b262-429">ペイントのフラッシュを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="1b262-429">To enable Paint Flashing:</span></span>  

1.  <span data-ttu-id="1b262-430">[ **レンダリング** ] タブを開きます。 「 [レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-430">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="1b262-431">[ **ペイントの点滅** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1b262-431">Enable the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="ペイントの点滅" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="1b262-433">ペイントの点滅</span><span class="sxs-lookup"><span data-stu-id="1b262-433">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <span data-ttu-id="1b262-434">レイヤーの枠線を使用してレイヤーを重ねて表示する</span><span class="sxs-lookup"><span data-stu-id="1b262-434">View an overlay of layers with Layer Borders</span></span>   

<span data-ttu-id="1b262-435">レイヤー境界 **線** を使用して、レイヤーの境界線とタイルをページの上に重ねて表示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-435">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="1b262-436">レイヤーの境界線を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="1b262-436">To enable Layer Borders:</span></span>  

1.  <span data-ttu-id="1b262-437">[ **レンダリング** ] タブを開きます。 「 [レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-437">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="1b262-438">[ **レイヤー罫線** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1b262-438">Enable the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="レイヤーの枠線" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="1b262-440">レイヤーの枠線</span><span class="sxs-lookup"><span data-stu-id="1b262-440">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="1b262-441">色 codings の説明については、のコメントを参照してください [`debug_colors.cc`][ChromiumDebugColors] 。</span><span class="sxs-lookup"><span data-stu-id="1b262-441">See the comments in [`debug_colors.cc`][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <span data-ttu-id="1b262-442">スクロールパフォーマンスの問題をリアルタイムで見つける</span><span class="sxs-lookup"><span data-stu-id="1b262-442">Find scroll performance issues in realtime</span></span>   

<span data-ttu-id="1b262-443">スクロールパフォーマンスの問題を使って、スクロールに関連するイベントリスナーを持つページの要素を特定し、ページのパフォーマンスに悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b262-443">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="1b262-444">DevTools では、青緑で問題が発生する可能性のある要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b262-444">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="1b262-445">スクロールパフォーマンスの問題を表示するには:</span><span class="sxs-lookup"><span data-stu-id="1b262-445">To view scroll performance issues:</span></span>  

1.  <span data-ttu-id="1b262-446">[ **レンダリング** ] タブを開きます。 「 [レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b262-446">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="1b262-447">[ **パフォーマンスの問題のスクロール** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1b262-447">Enable the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="スクロールパフォーマンスの問題は、非レイヤーのビューポートに制約のあるオブジェクトによってパフォーマンスの低下が発生する可能性があることを示します。" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="1b262-449">**スクロールパフォーマンスの問題** は、非レイヤーのビューポートに制約のあるオブジェクトによってパフォーマンスの低下が発生する可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="1b262-449">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
<!--  
<!--    


-->  

<!-- image links -->  

[ImageCaptureSettingsIcon]: ../media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: ../media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: ../media/collect-garbage-icon.msft.png  
[ImageNextIcon]: ../media/next-icon.msft.png  
[ImagePanModeIcon]: ../media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: ../media/previous-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png
[ImageRefreshPageIcon]: ../media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: ../media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: ../media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: ../media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: ../media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: ../media/show-heaviest-stack-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "コマンドメニューを開きます。 [Microsoft Edge DevTools] コマンドメニューでコマンドを実行します。Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "実行時のパフォーマンスの分析を開始する |Microsoft ドキュメント"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "アクティビティタブのデモ |故障"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors cc-コードの検索"  

> [!NOTE]
> <span data-ttu-id="1b262-455">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b262-455">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1b262-456">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="1b262-456">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1b262-458">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1b262-458">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
