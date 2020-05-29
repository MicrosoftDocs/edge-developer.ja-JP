---
title: 業績分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: acd6e3e68f89096cf80c08f0d0c3430ab31eaec1
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611749"
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







# <span data-ttu-id="2024b-103">業績分析のリファレンス</span><span class="sxs-lookup"><span data-stu-id="2024b-103">Performance Analysis Reference</span></span>   



<span data-ttu-id="2024b-104">このページでは、パフォーマンスの分析に関連する Microsoft Edge DevTools の機能について包括的にご参照ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-104">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="2024b-105">[Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使用してページのパフォーマンスを分析する方法については、ガイド付きチュートリアルの「[実行時のパフォーマンスの分析][DevtoolsEvaluatePerformanceGettingStarted]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-105">See [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="2024b-106">レコードのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="2024b-106">Record performance</span></span>   

### <span data-ttu-id="2024b-107">実行時のパフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="2024b-107">Record runtime performance</span></span>   

<span data-ttu-id="2024b-108">読み込みとは異なり、実行中にページのパフォーマンスを分析する場合は、実行時のパフォーマンスを記録します。</span><span class="sxs-lookup"><span data-stu-id="2024b-108">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="2024b-109">分析対象のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2024b-109">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="2024b-110">DevTools で [**パフォーマンス**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2024b-110">Click the **Performance** tab in DevTools.</span></span>  
1.  <span data-ttu-id="2024b-111">[**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-111">Click **Record** ![Record][ImageRecordIcon].</span></span>  
    
    > ##### <span data-ttu-id="2024b-112">図 1</span><span class="sxs-lookup"><span data-stu-id="2024b-112">Figure 1</span></span>  
    > **<span data-ttu-id="2024b-113">Record</span><span class="sxs-lookup"><span data-stu-id="2024b-113">Record</span></span>**  
    > ![Record][ImageRecord]  

1.  <span data-ttu-id="2024b-115">ページを操作します。</span><span class="sxs-lookup"><span data-stu-id="2024b-115">Interact with the page.</span></span>  <span data-ttu-id="2024b-116">DevTools は、操作の結果として発生するすべてのページアクティビティを記録します。</span><span class="sxs-lookup"><span data-stu-id="2024b-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="2024b-117">[**記録**] をもう一度クリックするか、[**停止**] をクリックして記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="2024b-117">Click **Record** again or click **Stop** to stop recording.</span></span>  

### <span data-ttu-id="2024b-118">読み込みのパフォーマンスの記録</span><span class="sxs-lookup"><span data-stu-id="2024b-118">Record load performance</span></span>   

<span data-ttu-id="2024b-119">実行時とは異なり、読み込み中にページのパフォーマンスを分析する場合は、読み込みのパフォーマンスを記録します。</span><span class="sxs-lookup"><span data-stu-id="2024b-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="2024b-120">分析対象のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2024b-120">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="2024b-121">DevTools の [**パフォーマンス**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2024b-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="2024b-122">[**ページ** ![ の更新ページの更新] をクリックし ][ImageRefreshPageIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-122">Click **Refresh page** ![Refresh Page][ImageRefreshPageIcon].</span></span>  <span data-ttu-id="2024b-123">DevTools では、ページが更新されている間はパフォーマンスのメトリックが記録され、読み込みが完了してから数秒間、自動的に記録が停止します。</span><span class="sxs-lookup"><span data-stu-id="2024b-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    > ##### <span data-ttu-id="2024b-124">図 2</span><span class="sxs-lookup"><span data-stu-id="2024b-124">Figure 2</span></span>  
    > **<span data-ttu-id="2024b-125">ページの更新</span><span class="sxs-lookup"><span data-stu-id="2024b-125">Refresh page</span></span>**  
    > ![ページの更新][ImageRefreshPage]  

<span data-ttu-id="2024b-127">DevTools は、ほとんどのアクティビティが発生したレコーディングの部分に自動的にズームインします。</span><span class="sxs-lookup"><span data-stu-id="2024b-127">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

> ##### <span data-ttu-id="2024b-128">図 3</span><span class="sxs-lookup"><span data-stu-id="2024b-128">Figure 3</span></span>  
> <span data-ttu-id="2024b-129">ページ読み込みの記録</span><span class="sxs-lookup"><span data-stu-id="2024b-129">A page-load recording</span></span>  
> ![ページ読み込みの記録][ImageLoadRecording]  

### <span data-ttu-id="2024b-131">記録中にスクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="2024b-131">Capture screenshots while recording</span></span>   

<span data-ttu-id="2024b-132">記録中にすべてのフレームのスクリーンショットをキャプチャするには、[**スクリーンショット**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2024b-132">Enable the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

> ##### <span data-ttu-id="2024b-133">図 4</span><span class="sxs-lookup"><span data-stu-id="2024b-133">Figure 4</span></span>  
> <span data-ttu-id="2024b-134">**スクリーンショット**のチェックボックス</span><span class="sxs-lookup"><span data-stu-id="2024b-134">The **Screenshots** checkbox</span></span>  
> ![スクリーンショットのチェックボックス][ImageScreenshots]  

<span data-ttu-id="2024b-136">スクリーンショットを操作する方法について[は、「スクリーンショットを表示](#view-a-screenshot)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-136">See [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <span data-ttu-id="2024b-137">記録中にガベージコレクションを強制する</span><span class="sxs-lookup"><span data-stu-id="2024b-137">Force garbage collection while recording</span></span>   

<span data-ttu-id="2024b-138">ページを記録しているときに、[ガーベジコレクトの**収集**] をクリックして ![ ][ImageCollectGarbageIcon] ガベージコレクションを強制します。</span><span class="sxs-lookup"><span data-stu-id="2024b-138">While you are recording a page, click **Collect garbage** ![Collect garbage][ImageCollectGarbageIcon] to force garbage collection.</span></span>  

> ##### <span data-ttu-id="2024b-139">図 5</span><span class="sxs-lookup"><span data-stu-id="2024b-139">Figure 5</span></span>  
> <span data-ttu-id="2024b-140">ガーベジの収集</span><span class="sxs-lookup"><span data-stu-id="2024b-140">Collect garbage</span></span>  
> ![ガーベジの収集][ImageCollectGarbage]  

### <span data-ttu-id="2024b-142">レコーディング設定を表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-142">Show recording settings</span></span>   

<span data-ttu-id="2024b-143">[**キャプチャ設定**キャプチャの設定] をクリックして、 ![ ][ImageCaptureSettingsIcon] devtools がパフォーマンスの記録をキャプチャする方法に関連するその他の設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-143">Click **Capture settings** ![Capture settings][ImageCaptureSettingsIcon] to expose more settings related to how DevTools captures performance recordings.</span></span>  

> ##### <span data-ttu-id="2024b-144">図 6</span><span class="sxs-lookup"><span data-stu-id="2024b-144">Figure 6</span></span>  
> <span data-ttu-id="2024b-145">[**キャプチャの設定**] セクション</span><span class="sxs-lookup"><span data-stu-id="2024b-145">The **Capture settings** section</span></span>  
> ![[キャプチャの設定] セクション][ImageCaptureSettings]  

### <span data-ttu-id="2024b-147">JavaScript のサンプルを無効にする</span><span class="sxs-lookup"><span data-stu-id="2024b-147">Disable JavaScript samples</span></span>   

<span data-ttu-id="2024b-148">記録の**メイン**セクションには、記録中に呼び出された JavaScript 関数の詳細なコールスタックが既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-148">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="2024b-149">次の呼び出し履歴を無効にするには:</span><span class="sxs-lookup"><span data-stu-id="2024b-149">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="2024b-150">[**キャプチャの設定**] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="2024b-150">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="2024b-151">「[レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-151">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="2024b-152">[ **JavaScript のサンプルを無効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2024b-152">Enable the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="2024b-153">ページの記録を取ります。</span><span class="sxs-lookup"><span data-stu-id="2024b-153">Take a recording of the page.</span></span>  

<span data-ttu-id="2024b-154">[図 7](#figure-7)と[図 8](#figure-8)は、JavaScript サンプルの無効化と有効化の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="2024b-154">[Figure 7](#figure-7) and [Figure 8](#figure-8) show the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="2024b-155">サンプリングが無効になっている場合、記録の**メイン**セクションは、JavaScript のすべての呼び出し履歴を省略しているため、非常に短くなります。</span><span class="sxs-lookup"><span data-stu-id="2024b-155">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

> ##### <span data-ttu-id="2024b-156">図 7</span><span class="sxs-lookup"><span data-stu-id="2024b-156">Figure 7</span></span>  
> <span data-ttu-id="2024b-157">JS サンプルが無効になっている場合のレコーディングの例</span><span class="sxs-lookup"><span data-stu-id="2024b-157">An example of a recording when JS samples are disabled</span></span>  
> ![JS サンプルが無効になっている場合のレコーディングの例][ImageJSSamplesDisabled]  

> ##### <span data-ttu-id="2024b-159">図 8</span><span class="sxs-lookup"><span data-stu-id="2024b-159">Figure 8</span></span>  
> <span data-ttu-id="2024b-160">JS サンプルが有効になっている場合のレコーディングの例</span><span class="sxs-lookup"><span data-stu-id="2024b-160">An example of a recording when JS samples are enabled</span></span>  
> ![JS サンプルが有効になっている場合のレコーディングの例][ImageJSSamplesEnabled]  

### <span data-ttu-id="2024b-162">記録中にネットワークを調整する</span><span class="sxs-lookup"><span data-stu-id="2024b-162">Throttle the network while recording</span></span>   

<span data-ttu-id="2024b-163">記録中にネットワークを調整するには:</span><span class="sxs-lookup"><span data-stu-id="2024b-163">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="2024b-164">[**キャプチャの設定**] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="2024b-164">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="2024b-165">「[レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-165">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="2024b-166">**ネットワーク**を適切な調整レベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="2024b-166">Set **Network** to the desired level of throttling.</span></span>  

### <span data-ttu-id="2024b-167">記録中に CPU を調整する</span><span class="sxs-lookup"><span data-stu-id="2024b-167">Throttle the CPU while recording</span></span>   

<span data-ttu-id="2024b-168">記録中に CPU を調整するには:</span><span class="sxs-lookup"><span data-stu-id="2024b-168">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="2024b-169">[**キャプチャの設定**] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="2024b-169">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="2024b-170">「[レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-170">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="2024b-171">**CPU**を目的の調整レベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="2024b-171">Set **CPU** to the desired level of throttling.</span></span>  

<span data-ttu-id="2024b-172">調整は、コンピューターの機能を基準とします。</span><span class="sxs-lookup"><span data-stu-id="2024b-172">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="2024b-173">たとえば、 **2 倍速の遅延**オプションを使うと、CPU は通常の2倍の速度で動作します。</span><span class="sxs-lookup"><span data-stu-id="2024b-173">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="2024b-174">モバイルデバイスのアーキテクチャはデスクトップとノート pc とは大きく異なりますので、DevTools はモバイルデバイスの Cpu を実際にシミュレートするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2024b-174">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <span data-ttu-id="2024b-175">高度な描画インストルメンテーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="2024b-175">Enable advanced paint instrumentation</span></span>   

<span data-ttu-id="2024b-176">詳細な描画インストルメンテーションを表示するには:</span><span class="sxs-lookup"><span data-stu-id="2024b-176">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="2024b-177">[**キャプチャの設定**] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="2024b-177">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="2024b-178">「[レコーディング設定を表示する」を](#show-recording-settings)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-178">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="2024b-179">**[高度な描画インストルメンテーション (低速) を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2024b-179">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="2024b-180">ペイント情報を操作する方法については、「[レイヤーの表示](#view-layers-information)と[ペイントプロファイラーの表示](#view-paint-profiler)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2024b-180">To learn how to interact with the paint information, see [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <span data-ttu-id="2024b-181">レコーディングを保存する</span><span class="sxs-lookup"><span data-stu-id="2024b-181">Save a recording</span></span>   

<span data-ttu-id="2024b-182">レコーディングを保存するには、右クリックして、[**プロファイルの保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2024b-182">To save a recording, right-click and select **Save Profile**.</span></span>  

> ##### <span data-ttu-id="2024b-183">図 9</span><span class="sxs-lookup"><span data-stu-id="2024b-183">Figure 9</span></span>  
> **<span data-ttu-id="2024b-184">プロフィールの保存</span><span class="sxs-lookup"><span data-stu-id="2024b-184">Save Profile</span></span>**  
> ![プロフィールの保存][ImageSaveProfile]  

## <span data-ttu-id="2024b-186">レコーディングを読み込む</span><span class="sxs-lookup"><span data-stu-id="2024b-186">Load a recording</span></span>   

<span data-ttu-id="2024b-187">レコーディングを読み込むには、右クリックして、[**プロファイルの読み込み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2024b-187">To load a recording, right-click and select **Load Profile**.</span></span>  

> ##### <span data-ttu-id="2024b-188">図 10</span><span class="sxs-lookup"><span data-stu-id="2024b-188">Figure 10</span></span>  
> **<span data-ttu-id="2024b-189">プロファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="2024b-189">Load Profile</span></span>**  
> ![プロファイルの読み込み][ImageLoadProfile]  

## <span data-ttu-id="2024b-191">前の記録をクリアする</span><span class="sxs-lookup"><span data-stu-id="2024b-191">Clear the previous recording</span></span>   

<span data-ttu-id="2024b-192">レコーディングを作成した後、[レコーディングのクリア]**を押して** ![ 、[ ][ImageClearRecordingIcon] **パフォーマンス**] パネルからその記録をクリアします。</span><span class="sxs-lookup"><span data-stu-id="2024b-192">After making a recording, press **Clear recording** ![Clear recording][ImageClearRecordingIcon] to clear that recording from the **Performance** panel.</span></span>  

> ##### <span data-ttu-id="2024b-193">図 11</span><span class="sxs-lookup"><span data-stu-id="2024b-193">Figure 11</span></span>  
> <span data-ttu-id="2024b-194">レコーディングのクリア</span><span class="sxs-lookup"><span data-stu-id="2024b-194">Clear recording</span></span>  
> ![レコーディングのクリア][ImageClearRecording]  

## <span data-ttu-id="2024b-196">パフォーマンスの記録を分析する</span><span class="sxs-lookup"><span data-stu-id="2024b-196">Analyze a performance recording</span></span>   

<span data-ttu-id="2024b-197">[実行時のパフォーマンス](#record-runtime-performance)または[レコードの読み込みのパフォーマンス](#record-load-performance)を記録すると、**パフォーマンス**パネルに多くのデータが表示され、発生した処理のパフォーマンスを分析できます。</span><span class="sxs-lookup"><span data-stu-id="2024b-197">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <span data-ttu-id="2024b-198">レコーディングの一部を選択する</span><span class="sxs-lookup"><span data-stu-id="2024b-198">Select a portion of a recording</span></span>   

<span data-ttu-id="2024b-199">[**概要**] でマウスを左右にドラッグして、レコーディングの一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="2024b-199">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="2024b-200">**概要**は、 **FPS**、 **CPU**、および**ネット**チャートを含むセクションです。</span><span class="sxs-lookup"><span data-stu-id="2024b-200">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

> ##### <span data-ttu-id="2024b-201">図 12</span><span class="sxs-lookup"><span data-stu-id="2024b-201">Figure 12</span></span>  
> <span data-ttu-id="2024b-202">概要の上でマウスをドラッグしてズーム</span><span class="sxs-lookup"><span data-stu-id="2024b-202">Dragging the mouse across the Overview to zoom</span></span>  
> ![概要の上でマウスをドラッグしてズーム][ImageZoom]  

<span data-ttu-id="2024b-204">キーボードを使用して部分を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2024b-204">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="2024b-205">**メイン**セクションの背景をクリックするか、[**操作**]、[**ネットワーク**]、[ **GPU**] などの横にあるセクションのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2024b-205">Click on the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="2024b-206">このキーボードワークフローは、これらのセクションのいずれかがフォーカスされている場合にのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="2024b-206">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="2024b-207">それぞれ、、、[左へ移動]、[縮小]、 `W` `A` `S` [右へ移動] の各キーを使用し `D` ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-207">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="2024b-208">トラックパッドを使用して部分を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2024b-208">To select a portion using a trackpad:</span></span>  

1.  <span data-ttu-id="2024b-209">[**概要**] セクションまたは [**詳細**] セクションの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="2024b-209">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="2024b-210">[**概要**] セクションは、 **FPS**、 **CPU**、および**正味**グラフを含む領域です。</span><span class="sxs-lookup"><span data-stu-id="2024b-210">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="2024b-211">[**詳細**] セクションは、**メイン**セクション、[**操作**] セクションなどを含む領域です。</span><span class="sxs-lookup"><span data-stu-id="2024b-211">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="2024b-212">2本の指で上方向にスワイプして縮小し、左方向にスワイプして左へ移動し、下方向にスワイプしてズームインし、右にスワイプして右に移動します。</span><span class="sxs-lookup"><span data-stu-id="2024b-212">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="2024b-213">**メイン**セクションまたはそのいずれかの近隣にある長い炎のグラフをスクロールするには、上下にドラッグしてクリックしたままにします。</span><span class="sxs-lookup"><span data-stu-id="2024b-213">To scroll a long flame chart in the **Main** section or any of the neighbors, click and hold while dragging up and down.</span></span>  <span data-ttu-id="2024b-214">左または右にドラッグして、録音中の部分を移動します。</span><span class="sxs-lookup"><span data-stu-id="2024b-214">Drag left and right to move what portion of the recording is selected.</span></span>  

### <span data-ttu-id="2024b-215">アクティビティを検索する</span><span class="sxs-lookup"><span data-stu-id="2024b-215">Search activities</span></span>   

<span data-ttu-id="2024b-216">[ `Control` + `F` \ (Windows \)] または [ `Command` + `F` \ (macOS \)] を押して、**パフォーマンス**パネルの下部にある [検索] ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="2024b-216">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

> ##### <span data-ttu-id="2024b-217">図 13</span><span class="sxs-lookup"><span data-stu-id="2024b-217">Figure 13</span></span>  
> <span data-ttu-id="2024b-218">ウィンドウの下部にある [検索] ボックスで regex を使用して、で始まるすべてのアクティビティを検索する</span><span class="sxs-lookup"><span data-stu-id="2024b-218">Using regex in the search box at the bottom of the window to find any activity that begins with</span></span> `E`  
> ![検索ボックス][ImageSearch]  

<span data-ttu-id="2024b-220">クエリに一致するアクティビティを移動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2024b-220">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="2024b-221">**前** ![ と次のボタンを使用し ][ImagePreviousIcon] **Next** ![ ][ImageNextIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-221">Use the **Previous** ![Previous][ImagePreviousIcon] and **Next** ![Next][ImageNextIcon] buttons.</span></span>  
*   <span data-ttu-id="2024b-222">を押して [前へ] を選択するか、[ `Shift` + `Enter` 次へ] を `Enter` 選択します。</span><span class="sxs-lookup"><span data-stu-id="2024b-222">Press `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="2024b-223">クエリの設定を変更するには:</span><span class="sxs-lookup"><span data-stu-id="2024b-223">To modify query settings:</span></span>  

*   <span data-ttu-id="2024b-224">大文字と**小文字を**区別 ![ ][ImageSearchCaseIcon] します。クエリの大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="2024b-224">Press **Case sensitive** ![Case sensitive][ImageSearchCaseIcon] to make the query case sensitive.</span></span>  
*   <span data-ttu-id="2024b-225">**Regex** ![ ][ImageSearchRegexIcon] クエリで正規表現を使用するには、regex regex を押します。</span><span class="sxs-lookup"><span data-stu-id="2024b-225">Press **Regex** ![Regex][ImageSearchRegexIcon] to use a regular expression in your query.</span></span>  

<span data-ttu-id="2024b-226">検索ボックスを非表示にするには、 **[キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2024b-226">To hide the search box, press **Cancel**.</span></span>  

### <span data-ttu-id="2024b-227">メインスレッドアクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="2024b-227">View main thread activity</span></span>   

<span data-ttu-id="2024b-228">**メイン**セクションを使って、ページのメインスレッドで発生したアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-228">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

> ##### <span data-ttu-id="2024b-229">図 14</span><span class="sxs-lookup"><span data-stu-id="2024b-229">Figure 14</span></span>  
> <span data-ttu-id="2024b-230">**メイン**セクション</span><span class="sxs-lookup"><span data-stu-id="2024b-230">The **Main** section</span></span>  
> ![メインセクション][ImageMain]  

<span data-ttu-id="2024b-232">イベントをクリックすると、[**概要**] タブにそのイベントの詳細情報が表示されます。 DevTools では、選択したイベントの概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-232">Click on an event to view more information about it in the **Summary** tab.  DevTools outlines the selected event.</span></span>  

> ##### <span data-ttu-id="2024b-233">図 15</span><span class="sxs-lookup"><span data-stu-id="2024b-233">Figure 15</span></span>  
> <span data-ttu-id="2024b-234">[ `anonymous` **概要**] タブの関数についての詳細</span><span class="sxs-lookup"><span data-stu-id="2024b-234">More information about the `anonymous` function in the **Summary** tab</span></span>  
> ![匿名関数の詳細については、[概要] タブを参照してください。][ImageMainEventSummary]  

<span data-ttu-id="2024b-236">DevTools は、炎グラフによるメインスレッドアクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-236">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="2024b-237">X 軸は、時間の経過に伴う記録を表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-237">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="2024b-238">Y 軸は、呼び出しスタックを表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-238">The y-axis represents the call stack.</span></span>  <span data-ttu-id="2024b-239">一番上にあるイベントは、その下にあるイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="2024b-239">The events on top cause the events below it.</span></span>  

> ##### <span data-ttu-id="2024b-240">図 16</span><span class="sxs-lookup"><span data-stu-id="2024b-240">Figure 16</span></span>  
> <span data-ttu-id="2024b-241">**メイン**セクションの炎のグラフ</span><span class="sxs-lookup"><span data-stu-id="2024b-241">A flame chart in the **Main** section</span></span>  
> ![炎のグラフ][ImageFlameChart]  

<span data-ttu-id="2024b-243">[図 16](#figure-16)では、イベントが53で発生しました `click` `Function Call` `activitytabs.js` 。</span><span class="sxs-lookup"><span data-stu-id="2024b-243">In [Figure 16](#figure-16), a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="2024b-244">次 `Function Call` に、匿名関数が呼び出されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2024b-244">Below `Function Call` you see that an anonymous function was called.</span></span>  <span data-ttu-id="2024b-245">呼び出された匿名関数が呼び出され `a` ます。これが呼び出され `wait` `Minor GC` ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-245">The anonymous function called `a`, which called `wait`, which called `Minor GC`.</span></span>  

<span data-ttu-id="2024b-246">DevTools では、スクリプトのランダムな色が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2024b-246">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="2024b-247">[図 16](#figure-16)では、1つのスクリプトからの関数の呼び出しは色が緑色になります。</span><span class="sxs-lookup"><span data-stu-id="2024b-247">In [Figure 16](#figure-16), function calls from one script are colored light green.</span></span>  <span data-ttu-id="2024b-248">別のスクリプトからの呼び出しは、色ベージュになります。</span><span class="sxs-lookup"><span data-stu-id="2024b-248">Calls from another script are colored beige.</span></span>  <span data-ttu-id="2024b-249">濃い黄色はスクリプトアクティビティを表し、紫色のイベントはレンダリングアクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-249">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="2024b-250">これらの暗い黄と紫色のイベントは、すべての記録で一貫しています。</span><span class="sxs-lookup"><span data-stu-id="2024b-250">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="2024b-251">JavaScript 呼び出しの詳細な炎グラフを非表示にする場合は、「 [javascript のサンプルを無効](#disable-javascript-samples)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2024b-251">See [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript calls.</span></span>  <span data-ttu-id="2024b-252">JS サンプルが無効になっている場合は、図16などの上位レベルのイベントのみが表示され `Event: click` `Function Call` ます。 [Figure 16](#figure-16)</span><span class="sxs-lookup"><span data-stu-id="2024b-252">When JS samples are disabled, you only see high-level events such as `Event: click` and `Function Call` from [Figure 16](#figure-16).</span></span>  

### <span data-ttu-id="2024b-253">テーブルのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-253">View activities in a table</span></span>   

<span data-ttu-id="2024b-254">ページを記録したら、**メイン**セクションに依存してアクティビティを分析する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2024b-254">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="2024b-255">DevTools には、アクティビティを分析するための3つの表形式ビューも用意されています。</span><span class="sxs-lookup"><span data-stu-id="2024b-255">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="2024b-256">各ビューには、次のような操作があります。</span><span class="sxs-lookup"><span data-stu-id="2024b-256">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="2024b-257">最も作業を引き起こしているルートアクティビティを表示するには、[ [**通話ツリー** ] タブ](#the-call-tree-tab)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2024b-257">When you want to view the root activities that cause the most work, use [the **Call Tree** tab](#the-call-tree-tab).</span></span>  
*   <span data-ttu-id="2024b-258">最も多くの時間を費やしたアクティビティを表示する場合は、[ [**ボトムアップ**] タブ](#the-bottom-up-tab)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2024b-258">When you want to view the activities where the most time was directly spent, use [the **Bottom-Up** tab](#the-bottom-up-tab).</span></span>  
*   <span data-ttu-id="2024b-259">記録中に発生した順番でアクティビティを表示する場合は、 [[**イベントログ**] タブ](#the-event-log-tab)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2024b-259">When you want to view the activities in the order in which they occurred during the recording, use [the **Event Log** tab](#the-event-log-tab).</span></span>  

> [!NOTE]
> <span data-ttu-id="2024b-260">次の3つのセクションはすべて同じデモを示しています。</span><span class="sxs-lookup"><span data-stu-id="2024b-260">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="2024b-261">[アクティビティ] タブの[デモ][ActivityTabsDemo]で、自分でデモを実行します。</span><span class="sxs-lookup"><span data-stu-id="2024b-261">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <span data-ttu-id="2024b-262">ルートアクティビティ</span><span class="sxs-lookup"><span data-stu-id="2024b-262">Root activities</span></span>   

<span data-ttu-id="2024b-263">[**通話ツリー** ] タブ、[**ボトムアップ**] タブ、[**イベントログ**] の各セクションで説明されている**ルートアクティビティ**の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="2024b-263">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** tab, **Bottom-Up** tab, and **Event Log** sections.</span></span>  

<span data-ttu-id="2024b-264">ルートアクティビティは、ブラウザーが何らかの操作を実行する原因となります。</span><span class="sxs-lookup"><span data-stu-id="2024b-264">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="2024b-265">たとえば、ページをクリックすると、ブラウザーで `Event` ルートアクティビティとしてアクティビティが発生します。</span><span class="sxs-lookup"><span data-stu-id="2024b-265">For example, when you click a page, the browser fires an `Event` activity as the root activity.</span></span>  <span data-ttu-id="2024b-266">これにより、ハンドラーが実行される `Event` 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2024b-266">That `Event` might cause a handler to run, and so on.</span></span>  

<span data-ttu-id="2024b-267">**メイン**セクションの炎チャートでは、ルートアクティビティはグラフの一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="2024b-267">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="2024b-268">[**コールツリー** ] タブと [**イベントログ**] タブでは、ルートアクティビティはトップレベルのアイテムです。</span><span class="sxs-lookup"><span data-stu-id="2024b-268">In the **Call Tree** and **Event Log** tabs, root activities are the top-level items.</span></span>  

<span data-ttu-id="2024b-269">ルートアクティビティの例について[は、「通話ツリー」タブ](#the-call-tree-tab)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-269">See [The Call Tree tab](#the-call-tree-tab) for an example of root activities.</span></span>  

#### <span data-ttu-id="2024b-270">[通話ツリー] タブ</span><span class="sxs-lookup"><span data-stu-id="2024b-270">The Call Tree tab</span></span>   

<span data-ttu-id="2024b-271">[**呼び出しツリー** ] タブを使用して、最も作業を発生させる[ルートアクティビティ](#root-activities)を表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-271">Use the **Call Tree** tab to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="2024b-272">[**通話ツリー** ] タブには、レコーディングの選択した部分のアクティビティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-272">The **Call Tree** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="2024b-273">部分の選択方法については[、「レコーディングの一部を選択](#select-a-portion-of-a-recording)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2024b-273">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

> ##### <span data-ttu-id="2024b-274">図 17</span><span class="sxs-lookup"><span data-stu-id="2024b-274">Figure 17</span></span>  
> <span data-ttu-id="2024b-275">[**通話ツリー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="2024b-275">The **Call Tree** tab</span></span>  
> ![[通話ツリー] タブ][ImageCallTree]  

<span data-ttu-id="2024b-277">[図 17](#figure-17)では、"and" などの [**アクティビティ**] 列の項目の最上位レベルを示してい `Evaluate Script` `Parse HTML` ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-277">In [Figure 17](#figure-17), the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="2024b-278">入れ子は、呼び出しスタックを表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-278">The nesting represents the call stack.</span></span>  <span data-ttu-id="2024b-279">たとえば、[図 17](#figure-17)の場合は、という原因 `Parse HTML` `Evaluate Script` `Compile Script` と `(anonymous)` なります。</span><span class="sxs-lookup"><span data-stu-id="2024b-279">For example, in [Figure 17](#figure-17), `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="2024b-280">**Self time**は、そのアクティビティに直接費やした時間を表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-280">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="2024b-281">**合計時間**は、そのアクティビティまたはいずれかの子に費やした時間を表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-281">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="2024b-282">[**自己時刻**]、[**時間の合計**]、または [**アクティビティ**] をクリックして、テーブルをその列で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="2024b-282">Click **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="2024b-283">[**フィルター** ] テキストボックスを使用して、アクティビティ名ごとにイベントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="2024b-283">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="2024b-284">既定では、**グループ化**メニューは [**グループ化なし**] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-284">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="2024b-285">[**グループ化**] メニューを使用して、さまざまな条件に基づいてアクティビティテーブルを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="2024b-285">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="2024b-286">[最も**重いスタック**を表示] をクリックし ![ ][ImageShowHeaviestStackIcon] て、**アクティビティ**テーブルの右側に別のテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-286">Click **Show Heaviest Stack** ![Show Heaviest Stack][ImageShowHeaviestStackIcon] to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="2024b-287">[アクティビティ] をクリックして、最も**重いスタック**テーブルにデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="2024b-287">Click on an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="2024b-288">最も大きな**スタック**テーブルには、選択したアクティビティのどの子が最も時間がかかるかが示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-288">The **Heaviest Stack** table shows you which children of the selected activity took the longest time to run.</span></span>  

#### <span data-ttu-id="2024b-289">[ボトムアップ] タブ</span><span class="sxs-lookup"><span data-stu-id="2024b-289">The Bottom-Up tab</span></span>   

<span data-ttu-id="2024b-290">[**ボトムアップ**] タブを使用して、集計で最も時間のかかるアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-290">Use the **Bottom-Up** tab to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="2024b-291">**下**のタブには、レコーディングの選択した部分のアクティビティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-291">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="2024b-292">部分の選択方法については[、「レコーディングの一部を選択](#select-a-portion-of-a-recording)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2024b-292">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

> ##### <span data-ttu-id="2024b-293">図18</span><span class="sxs-lookup"><span data-stu-id="2024b-293">Figure 18</span></span>  
> <span data-ttu-id="2024b-294">[**ボトムアップ**] タブ</span><span class="sxs-lookup"><span data-stu-id="2024b-294">The **Bottom-Up** tab</span></span>  
> ![[ボトムアップ] タブ][ImageBottomUp]  

<span data-ttu-id="2024b-296">[図 18](#figure-18)の**メイン**セクションの炎のグラフでは、ほとんどの時間が実行されていたことについて説明し `Parse HTML` ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-296">In the **Main** section flame chart of [Figure 18](#figure-18), see that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="2024b-297">[図 18](#figure-18)の一番**下**のタブにある一番上のアクティビティは `Parse HTML` です。</span><span class="sxs-lookup"><span data-stu-id="2024b-297">The top activity in the **Bottom-Up** tab of [Figure 18](#figure-18) is `Parse HTML`.</span></span>  <!--In the flame chart of [Figure 18](#figure-18), the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="2024b-298">**下**のタブでは、次の最も負荷の高いアクティビティが表示されて `Layout` います。</span><span class="sxs-lookup"><span data-stu-id="2024b-298">See in the **Bottom-Up** tab, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="2024b-299">[**自己時刻**] 列は、すべてのオカレンスにわたって、そのアクティビティで直接費やした合計時間を表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-299">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="2024b-300">[**合計時間**」列は、そのアクティビティまたはいずれかの子に費やした集計時間を表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-300">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <span data-ttu-id="2024b-301">[イベントログ] タブ</span><span class="sxs-lookup"><span data-stu-id="2024b-301">The Event Log tab</span></span>   

<span data-ttu-id="2024b-302">[**イベントログ**] タブを使用して、記録中に発生した順序でアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-302">Use the **Event Log** tab to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="2024b-303">[**イベントログ**] タブには、記録の選択されている部分のアクティビティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-303">The **Event Log** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="2024b-304">部分の選択方法については[、「レコーディングの一部を選択](#select-a-portion-of-a-recording)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2024b-304">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

> ##### <span data-ttu-id="2024b-305">図19</span><span class="sxs-lookup"><span data-stu-id="2024b-305">Figure 19</span></span>  
> <span data-ttu-id="2024b-306">[**イベントログ**] タブ</span><span class="sxs-lookup"><span data-stu-id="2024b-306">The **Event Log** tab</span></span>  
> ![[イベントログ] タブ][ImageEventLog]  

<span data-ttu-id="2024b-308">[**開始時刻**] 列は、そのアクティビティが開始されたポイントを表します。レコーディングの開始日を基準としています。</span><span class="sxs-lookup"><span data-stu-id="2024b-308">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="2024b-309">たとえば、 `175.7 ms` [図 19](#figure-19)で選択したアイテムの開始時刻は、記録を開始した後にアクティビティが175.7 ミリ秒で開始されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2024b-309">For example, the start time of `175.7 ms` for the selected item in [Figure 19](#figure-19) means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="2024b-310">**Self time**列は、そのアクティビティに直接費やした時間を表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-310">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="2024b-311">**合計時間**列は、そのアクティビティまたはその子のいずれかに直接費やした時間を表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-311">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="2024b-312">[**開始時刻**]、[**自己時刻**]、または [**合計時間**] をクリックして、テーブルをその列で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="2024b-312">Click **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="2024b-313">[**フィルター** ] テキストボックスを使って、名前でアクティビティをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="2024b-313">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="2024b-314">[**継続時間**] メニューを使用して、1ミリ秒または15ミリ秒未満のアクティビティを除外します。</span><span class="sxs-lookup"><span data-stu-id="2024b-314">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="2024b-315">既定では、[**期間**] メニューは [**すべて**] に設定されており、すべてのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-315">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="2024b-316">**読み込み**、**スクリプト**、**レンダリング**、または**Painting**のチェックボックスを無効にして、それらのカテゴリのすべてのアクティビティをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="2024b-316">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <span data-ttu-id="2024b-317">GPU アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="2024b-317">View GPU activity</span></span>   

<span data-ttu-id="2024b-318">**Gpu セクションの**gpu アクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-318">View GPU activity in the **GPU** section.</span></span>  

> ##### <span data-ttu-id="2024b-319">図20</span><span class="sxs-lookup"><span data-stu-id="2024b-319">Figure 20</span></span>  
> <span data-ttu-id="2024b-320">**GPU**セクション</span><span class="sxs-lookup"><span data-stu-id="2024b-320">The **GPU** section</span></span>  
> ![GPU セクション][ImageGpu]  

### <span data-ttu-id="2024b-322">ラスターアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-322">View raster activity</span></span>   

<span data-ttu-id="2024b-323">**ラスターセクションで**ラスターアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-323">View raster activity in the **Raster** section.</span></span>  

> ##### <span data-ttu-id="2024b-324">図21</span><span class="sxs-lookup"><span data-stu-id="2024b-324">Figure 21</span></span>  
> <span data-ttu-id="2024b-325">**ラスター**セクション</span><span class="sxs-lookup"><span data-stu-id="2024b-325">The **Raster** section</span></span>  
> ![ラスターセクション][ImageRaster]  

### <span data-ttu-id="2024b-327">ビューの操作</span><span class="sxs-lookup"><span data-stu-id="2024b-327">View interactions</span></span>   

<span data-ttu-id="2024b-328">記録中に発生したユーザー操作を見つけて分析するには、[**対話**] セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="2024b-328">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

> ##### <span data-ttu-id="2024b-329">図22</span><span class="sxs-lookup"><span data-stu-id="2024b-329">Figure 22</span></span>  
> <span data-ttu-id="2024b-330">[**操作**] セクション</span><span class="sxs-lookup"><span data-stu-id="2024b-330">The **Interactions** section</span></span>  
> ![[操作] セクション][ImageInteractions]  

<span data-ttu-id="2024b-332">対話式の下部にある赤い線は、メインスレッドの待機に費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="2024b-332">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="2024b-333">[ファイルの**概要**] タブで、操作をクリックして詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-333">Click an interaction to view more information about it in the **Summary** tab.</span></span>  

### <span data-ttu-id="2024b-334">1秒あたりのフレーム数 (FPS) の分析</span><span class="sxs-lookup"><span data-stu-id="2024b-334">Analyze frames per second (FPS)</span></span>   

<span data-ttu-id="2024b-335">DevTools には、1秒あたりのフレームの分析方法が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="2024b-335">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="2024b-336">[ **Fps**チャート](#the-fps-chart)を使用して、記録中の fps の概要を把握します。</span><span class="sxs-lookup"><span data-stu-id="2024b-336">Use [the **FPS** chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="2024b-337">[[**フレーム**] セクション](#the-frames-section)を使用して、特定のフレームの所要時間を表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-337">Use [the **Frames** section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="2024b-338">ページの実行時に、fps のリアルタイムの推定に**fps メーター**を使用します。</span><span class="sxs-lookup"><span data-stu-id="2024b-338">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="2024b-339">詳しく[は、「FPS メーターでリアルタイムのフレームを表示する](#view-frames-per-second-in-realtime-with-the-fps-meter)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-339">See [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  

#### <span data-ttu-id="2024b-340">FPS グラフ</span><span class="sxs-lookup"><span data-stu-id="2024b-340">The FPS chart</span></span>   

<span data-ttu-id="2024b-341">**FPS**グラフは、記録中のフレームレートの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="2024b-341">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="2024b-342">通常、緑色のバーが大きくなるほど、フレームレートが向上します。</span><span class="sxs-lookup"><span data-stu-id="2024b-342">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="2024b-343">**FPS**グラフの上に赤いバーが表示されるのは、ユーザーエクスペリエンスが損なわれている可能性が高いため、フレームレートが低下するという警告です。</span><span class="sxs-lookup"><span data-stu-id="2024b-343">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

> ##### <span data-ttu-id="2024b-344">図23</span><span class="sxs-lookup"><span data-stu-id="2024b-344">Figure 23</span></span>  
> <span data-ttu-id="2024b-345">FPS グラフ</span><span class="sxs-lookup"><span data-stu-id="2024b-345">The FPS chart</span></span>  
> ![FPS グラフ][ImageFpsChart]  

#### <span data-ttu-id="2024b-347">[フレーム] セクション</span><span class="sxs-lookup"><span data-stu-id="2024b-347">The Frames section</span></span>   

<span data-ttu-id="2024b-348">**フレーム**セクションでは、特定のフレームの所要時間が正確に示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-348">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="2024b-349">Frame の上にマウスポインターを移動すると、ヒントが表示され、詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-349">Hover over a frame to view a tooltip with more information about it.</span></span>  

> ##### <span data-ttu-id="2024b-350">図24</span><span class="sxs-lookup"><span data-stu-id="2024b-350">Figure 24</span></span>  
> <span data-ttu-id="2024b-351">フレーム上のマウスポインター</span><span class="sxs-lookup"><span data-stu-id="2024b-351">Hovering over a frame</span></span>  
> ![フレーム上のマウスポインター][ImageFramesSection]  

<span data-ttu-id="2024b-353">フレームをクリックすると、[**概要**] タブに、フレームに関するさらに詳しい情報が表示されます。 DevTools では、選択したフレームが青色で示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-353">Click on a frame to view even more information about the frame in the **Summary** tab.  DevTools outlines the selected frame in blue.</span></span>  

> ##### <span data-ttu-id="2024b-354">図25</span><span class="sxs-lookup"><span data-stu-id="2024b-354">Figure 25</span></span>  
> <span data-ttu-id="2024b-355">[**概要**] タブでのフレームの表示</span><span class="sxs-lookup"><span data-stu-id="2024b-355">Viewing a frame in the **Summary** tab</span></span>  
> ![[概要] タブでのフレームの表示][ImageFrameSummary]  

### <span data-ttu-id="2024b-357">ネットワーク要求を表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-357">View network requests</span></span>   

<span data-ttu-id="2024b-358">[**ネットワーク**] セクションを展開すると、記録中に発生した、ウォーターフォールのネットワーク要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-358">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

> ##### <span data-ttu-id="2024b-359">図26</span><span class="sxs-lookup"><span data-stu-id="2024b-359">Figure 26</span></span>  
> <span data-ttu-id="2024b-360">[**ネットワーク**] セクション</span><span class="sxs-lookup"><span data-stu-id="2024b-360">The **Network** section</span></span>  
> ![[ネットワーク] セクション][ImageNetworkRequest]  

<span data-ttu-id="2024b-362">要求は、次のように色分けされます。</span><span class="sxs-lookup"><span data-stu-id="2024b-362">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="2024b-363">HTML: 青</span><span class="sxs-lookup"><span data-stu-id="2024b-363">HTML: Blue</span></span>  
*   <span data-ttu-id="2024b-364">CSS: 紫</span><span class="sxs-lookup"><span data-stu-id="2024b-364">CSS: Purple</span></span>  
*   <span data-ttu-id="2024b-365">JS: 黄</span><span class="sxs-lookup"><span data-stu-id="2024b-365">JS: Yellow</span></span>  
*   <span data-ttu-id="2024b-366">画像: 緑</span><span class="sxs-lookup"><span data-stu-id="2024b-366">Images: Green</span></span>  

<span data-ttu-id="2024b-367">[ファイルの**概要**] タブで要求をクリックすると、詳細情報が表示されます。 たとえば、[図 26](#figure-26)の [**概要**] タブには、[**ネットワーク**] セクションで選択された青い要求についての詳細情報が表示されています。</span><span class="sxs-lookup"><span data-stu-id="2024b-367">Click on a request to view more information about it in the **Summary** tab.  For example, in [Figure 26](#figure-26) the **Summary** tab is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="2024b-368">要求の左上の濃い青色の正方形は、優先度の高い要求であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2024b-368">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="2024b-369">薄い青色の正方形は、優先度が低いことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2024b-369">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="2024b-370">たとえば、[図 26](#figure-26)では、選択されている要求の優先度が高く、緑色の1つが低い優先度であることを示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-370">For example, in [Figure 26](#figure-26) the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="2024b-371">[図 27](#figure-27)では、要求は `www.bing.com` 左側の線で表され、中央に暗い部分と薄い部分があるバー、右側に線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-371">In [Figure 27](#figure-27), the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="2024b-372">[図 28](#figure-28)は、[**ネットワーク**] パネルの [**タイミング**] タブに表示される同じ要求の対応表現を示しています。</span><span class="sxs-lookup"><span data-stu-id="2024b-372">[Figure 28](#figure-28) shows the corresponding representation of the same request in the **Timing** tab of the **Network** panel.</span></span>  <span data-ttu-id="2024b-373">2つの表現が相互にマップされる方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-373">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="2024b-374">左側の行は、一連のイベントを含むすべての項目になり `Connection Start` ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-374">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="2024b-375">つまり、これはすべて、排他的な前にあり `Request Sent` ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-375">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="2024b-376">バーの光部分は `Request Sent` と `Waiting (TTFB)` です。</span><span class="sxs-lookup"><span data-stu-id="2024b-376">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="2024b-377">バーの暗い部分は `Content Download` です。</span><span class="sxs-lookup"><span data-stu-id="2024b-377">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="2024b-378">適切な行は、基本的にメインスレッドの待機に費やされた時間です。</span><span class="sxs-lookup"><span data-stu-id="2024b-378">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="2024b-379">これは、[**タイミング**] タブには表示されません。</span><span class="sxs-lookup"><span data-stu-id="2024b-379">This is not represented in the **Timing** tab.</span></span>  

> ##### <span data-ttu-id="2024b-380">図27</span><span class="sxs-lookup"><span data-stu-id="2024b-380">Figure 27</span></span>  
> <span data-ttu-id="2024b-381">要求の線の表示 `www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="2024b-381">The line-bar representation of the `www.bing.com` request</span></span>  
> ![Www.bing.com 要求の線の表示][ImageLineBar]  

> ##### <span data-ttu-id="2024b-383">図28</span><span class="sxs-lookup"><span data-stu-id="2024b-383">Figure 28</span></span>  
> <span data-ttu-id="2024b-384">要求の [**タイミング**] タブの表示 `www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="2024b-384">The **Timing** tab representation of the `www.bing.com` request</span></span>  
> ![[ネットワーク] セクション][ImageTiming]  

### <span data-ttu-id="2024b-386">メモリメトリックの表示</span><span class="sxs-lookup"><span data-stu-id="2024b-386">View memory metrics</span></span>   

<span data-ttu-id="2024b-387">[**メモリ**] チェックボックスを有効にして、最後の記録からメモリ指標を表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-387">Enable the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

> ##### <span data-ttu-id="2024b-388">図29</span><span class="sxs-lookup"><span data-stu-id="2024b-388">Figure 29</span></span>  
> <span data-ttu-id="2024b-389">**メモリ**チェックボックス</span><span class="sxs-lookup"><span data-stu-id="2024b-389">The **Memory** checkbox</span></span>  
> ![メモリチェックボックス][ImageMemory]  

<span data-ttu-id="2024b-391">DevTools で、[**概要**] タブの上に新しい**メモリ**グラフが表示されます。 また、[**ヒープ**] という新しいグラフも表示**されます**。</span><span class="sxs-lookup"><span data-stu-id="2024b-391">DevTools displays a new **Memory** chart, above the **Summary** tab.  There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="2024b-392">**ヒープ**グラフは、**メモリ**グラフの**JS ヒープ**行と同じ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2024b-392">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

> ##### <span data-ttu-id="2024b-393">図30</span><span class="sxs-lookup"><span data-stu-id="2024b-393">Figure 30</span></span>  
> <span data-ttu-id="2024b-394">メモリメトリック、[**概要**] タブの上</span><span class="sxs-lookup"><span data-stu-id="2024b-394">Memory metrics, above the **Summary** tab</span></span>  
> ![メモリメトリック][ImageMemoryMetrics]  

<span data-ttu-id="2024b-396">グラフ上の色付きの線は、グラフ上の色付きのチェックボックスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="2024b-396">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="2024b-397">チェックボックスを無効にして、そのカテゴリをグラフから非表示にする。</span><span class="sxs-lookup"><span data-stu-id="2024b-397">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="2024b-398">グラフには、現在選択されているレコーディングの領域のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-398">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="2024b-399">たとえば、[図 30](#figure-30)の**メモリ**グラフでは、400 ms マークの前後にあるメモリ使用量のみが 1750 ms マークに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-399">For example, in [Figure 30](#figure-30), the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <span data-ttu-id="2024b-400">レコーディングの一部の継続時間を表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-400">View the duration of a portion of a recording</span></span>   

<span data-ttu-id="2024b-401">**Network**や**Main**などのセクションを分析するときに、特定のイベントの所要時間をより正確に予測する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2024b-401">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="2024b-402">長押しして長押しし、 `Shift` 左または右にドラッグしてレコーディングの一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="2024b-402">Hold `Shift`, click and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="2024b-403">選択範囲の一番下にある DevTools は、その部分の所要時間を示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-403">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

> ##### <span data-ttu-id="2024b-404">図31</span><span class="sxs-lookup"><span data-stu-id="2024b-404">Figure 31</span></span>  
> <span data-ttu-id="2024b-405">`9.47ms`選択した部分の一番下にあるタイムスタンプは、その部分の所要時間を示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-405">The `9.47ms` timestamp at the bottom of the selected portion indicates how long that portion took</span></span>  
> ![レコーディングの一部の継続時間を表示する][ImageDuration]  

### <span data-ttu-id="2024b-407">スクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-407">View a screenshot</span></span>   

<span data-ttu-id="2024b-408">スクリーンショットを有効にする方法については、「[記録中のスクリーンショットのキャプチャ](#capture-screenshots-while-recording)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-408">See [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to enable screenshots.</span></span>  

<span data-ttu-id="2024b-409">**概要**にマウスポインターを合わせると、その時点でページがどのように表示されたかを示すスクリーンショットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-409">Hover over the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="2024b-410">**概要**は、 **CPU**、 **FPS**、および**ネット**チャートを含むセクションです。</span><span class="sxs-lookup"><span data-stu-id="2024b-410">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

> ##### <span data-ttu-id="2024b-411">図32</span><span class="sxs-lookup"><span data-stu-id="2024b-411">Figure 32</span></span>  
> <span data-ttu-id="2024b-412">スクリーンショットの表示</span><span class="sxs-lookup"><span data-stu-id="2024b-412">Viewing a screenshot</span></span>  
> ![スクリーンショットの表示][ImageViewScreenshot]  

<span data-ttu-id="2024b-414">**フレーム**セクションのフレームをクリックしてスクリーンショットを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2024b-414">You may also view screenshots by clicking a frame in the **Frames** section.</span></span>  <span data-ttu-id="2024b-415">DevTools では、[**概要**] タブにスクリーンショットの小さなバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-415">DevTools displays a small version of the screenshot in the **Summary** tab.</span></span>  

> ##### <span data-ttu-id="2024b-416">図33</span><span class="sxs-lookup"><span data-stu-id="2024b-416">Figure 33</span></span>  
> <span data-ttu-id="2024b-417">フレームセクションのフレームをクリックすると、 `233.9ms` そのフレームのスクリーンショットが [**概要**] タブに表示さ**Frames**れます。</span><span class="sxs-lookup"><span data-stu-id="2024b-417">After clicking the `233.9ms` frame in the **Frames** section, the screenshot for that frame is displayed in the **Summary** tab</span></span>  
> ![[概要] タブのスクリーンショットの表示][ImageFrameScreenshotSummary]  

<span data-ttu-id="2024b-419">[**概要**] タブでサムネイルをクリックして、スクリーンショットを拡大します。</span><span class="sxs-lookup"><span data-stu-id="2024b-419">Click the thumbnail in the **Summary** tab to zoom in on the screenshot.</span></span>  

> ##### <span data-ttu-id="2024b-420">図34</span><span class="sxs-lookup"><span data-stu-id="2024b-420">Figure 34</span></span>  
> <span data-ttu-id="2024b-421">[**概要**] タブでサムネイルをクリックすると、devtools のスクリーンショットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-421">After clicking the thumbnail in the **Summary** tab, DevTools zooms in on the screenshot</span></span>  
> ![[概要] タブのスクリーンショットを拡大する][ImageFrameScreenshotZoom]  

### <span data-ttu-id="2024b-423">レイヤー情報の表示</span><span class="sxs-lookup"><span data-stu-id="2024b-423">View layers information</span></span>   

<span data-ttu-id="2024b-424">フレームに関する高度なレイヤー情報を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2024b-424">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="2024b-425">[高度な描画インストルメンテーションを有効に](#enable-advanced-paint-instrumentation)します。</span><span class="sxs-lookup"><span data-stu-id="2024b-425">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="2024b-426">**フレームセクションで**フレームを選択します。</span><span class="sxs-lookup"><span data-stu-id="2024b-426">Select a frame in the **Frames** section.</span></span>  <span data-ttu-id="2024b-427">[開発ツール] では、[新しい**レイヤー** ] タブの [**イベントログ**] タブの横に、レイヤーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-427">DevTools displays information about the layers in the new **Layers** tab, next to the **Event Log** tab.</span></span>  
    
    > ##### <span data-ttu-id="2024b-428">図35</span><span class="sxs-lookup"><span data-stu-id="2024b-428">Figure 35</span></span>  
    > <span data-ttu-id="2024b-429">[**レイヤー** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="2024b-429">The **Layers** pane</span></span>  
    > ![[レイヤー] ウィンドウ][ImageLayers]  
    
<span data-ttu-id="2024b-431">レイヤーをポイントすると、図の中で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-431">Hover over a layer to highlight it in the diagram.</span></span>  

> ##### <span data-ttu-id="2024b-432">図36</span><span class="sxs-lookup"><span data-stu-id="2024b-432">Figure 36</span></span>  
> <span data-ttu-id="2024b-433">強調表示されたレイヤー **#39**</span><span class="sxs-lookup"><span data-stu-id="2024b-433">Highlighting layer **#39**</span></span>  
> ![レイヤーの強調表示][ImageLayerHover]  

<span data-ttu-id="2024b-435">ダイアグラムを移動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2024b-435">To move the diagram:</span></span>  

*   <span data-ttu-id="2024b-436">**Pan Mode** ![ ][ImagePanModeIcon] X 軸と Y 軸に沿って移動するには、[パンモード] パンモードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2024b-436">Click **Pan Mode** ![Pan Mode][ImagePanModeIcon] to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="2024b-437">Z 軸に沿って回転させるには、[**回転モード**] をクリックし ![ ][ImageRotateModeIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-437">Click **Rotate Mode** ![Rotate Mode][ImageRotateModeIcon] to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="2024b-438">[**変形** ![ のリセット] をクリックして ][ImageResetTransformIcon] 、図を元の位置にリセットします。</span><span class="sxs-lookup"><span data-stu-id="2024b-438">Click **Reset Transform** ![Reset Transform][ImageResetTransformIcon] to reset the diagram to the original position.</span></span>  

### <span data-ttu-id="2024b-439">ペイントプロファイラーの表示</span><span class="sxs-lookup"><span data-stu-id="2024b-439">View paint profiler</span></span>   

<span data-ttu-id="2024b-440">ペイントイベントに関する詳細情報を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2024b-440">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="2024b-441">[高度な描画インストルメンテーションを有効に](#enable-advanced-paint-instrumentation)します。</span><span class="sxs-lookup"><span data-stu-id="2024b-441">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="2024b-442">**メイン**セクションで**Paint**イベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="2024b-442">Select a **Paint** event in the **Main** section.</span></span>  
    
    > ##### <span data-ttu-id="2024b-443">図37</span><span class="sxs-lookup"><span data-stu-id="2024b-443">Figure 37</span></span>  
    > <span data-ttu-id="2024b-444">[**ペイントプロファイラー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="2024b-444">The **Paint Profiler** tab</span></span>  
    > ![[ペイントプロファイラー] タブ][ImagePaintProfiler]  
    
## <span data-ttu-id="2024b-446">[レンダリング] タブでのレンダリングのパフォーマンスの分析</span><span class="sxs-lookup"><span data-stu-id="2024b-446">Analyze rendering performance with the Rendering tab</span></span>   

<span data-ttu-id="2024b-447">[**レンダリング**] タブの機能を使用すると、ページのレンダリングパフォーマンスを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="2024b-447">Use the features of the **Rendering** tab to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="2024b-448">[**レンダリング**] タブを開くには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2024b-448">To open the **Rendering** tab:</span></span>  

1.  <span data-ttu-id="2024b-449">[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-449">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="2024b-450">入力を開始し `Rendering` 、を選択し `Show Rendering` ます。</span><span class="sxs-lookup"><span data-stu-id="2024b-450">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="2024b-451">DevTools は、DevTools ウィンドウの下部にある [**レンダリング**] タブを表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-451">DevTools displays the **Rendering** tab at the bottom of your DevTools window.</span></span>  
    
    > ##### <span data-ttu-id="2024b-452">図38</span><span class="sxs-lookup"><span data-stu-id="2024b-452">Figure 38</span></span>  
    > <span data-ttu-id="2024b-453">[**レンダリング**] タブ</span><span class="sxs-lookup"><span data-stu-id="2024b-453">The **Rendering** tab</span></span>  
    > ![[レンダリング] タブ][ImageRenderingTab]  
    
### <span data-ttu-id="2024b-455">FPS メーターを使ってリアルタイムで1秒あたりのフレームを表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-455">View frames per second in realtime with the FPS meter</span></span>   

<span data-ttu-id="2024b-456">**FPS メーター**は、ビューポートの右上隅に表示されるオーバーレイです。</span><span class="sxs-lookup"><span data-stu-id="2024b-456">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="2024b-457">ページの実行時に、リアルタイムでの FPS の推定値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-457">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="2024b-458">**FPS メーター**を開くには:</span><span class="sxs-lookup"><span data-stu-id="2024b-458">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="2024b-459">[**レンダリング**] タブを開きます。 「[レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-459">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="2024b-460">[ **FPS メーター** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2024b-460">Enable the **FPS Meter** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="2024b-461">図39</span><span class="sxs-lookup"><span data-stu-id="2024b-461">Figure 39</span></span>  
    > <span data-ttu-id="2024b-462">FPS メーター</span><span class="sxs-lookup"><span data-stu-id="2024b-462">The FPS meter</span></span>  
    > ![FPS メーター][ImageFpsMeter]  
    
### <span data-ttu-id="2024b-464">ペイントの点滅でリアルタイムで描画イベントを表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-464">View painting events in realtime with Paint Flashing</span></span>   

<span data-ttu-id="2024b-465">[ペイントのフラッシュ] を使って、ページ上のすべての描画イベントをリアルタイムで表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-465">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="2024b-466">ページの一部が再描画されるたびに、DevTools でそのセクションの輪郭が緑色で示されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-466">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="2024b-467">ペイントのフラッシュを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="2024b-467">To enable Paint Flashing:</span></span>  

1.  <span data-ttu-id="2024b-468">[**レンダリング**] タブを開きます。 「[レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-468">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="2024b-469">[**ペイントの点滅**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2024b-469">Enable the **Paint Flashing** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="2024b-470">図40</span><span class="sxs-lookup"><span data-stu-id="2024b-470">Figure 40</span></span>  
    > **<span data-ttu-id="2024b-471">ペイントの点滅</span><span class="sxs-lookup"><span data-stu-id="2024b-471">Paint Flashing</span></span>**  
    > ![ペイントの点滅][ImagePaintFlashing]  
    
### <span data-ttu-id="2024b-473">レイヤーの枠線を使用してレイヤーを重ねて表示する</span><span class="sxs-lookup"><span data-stu-id="2024b-473">View an overlay of layers with Layer Borders</span></span>   

<span data-ttu-id="2024b-474">レイヤー境界**線**を使用して、レイヤーの境界線とタイルをページの上に重ねて表示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-474">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="2024b-475">レイヤーの境界線を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="2024b-475">To enable Layer Borders:</span></span>  

1.  <span data-ttu-id="2024b-476">[**レンダリング**] タブを開きます。 「[レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-476">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="2024b-477">[**レイヤー罫線**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2024b-477">Enable the **Layer Borders** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="2024b-478">図41</span><span class="sxs-lookup"><span data-stu-id="2024b-478">Figure 41</span></span>  
    > **<span data-ttu-id="2024b-479">レイヤーの枠線</span><span class="sxs-lookup"><span data-stu-id="2024b-479">Layer Borders</span></span>**  
    > ![レイヤーの枠線][ImageLayerBorders]  
    
<span data-ttu-id="2024b-481">色 codings の説明については、のコメントを参照してください [`debug_colors.cc`][ChromiumDebugColors] 。</span><span class="sxs-lookup"><span data-stu-id="2024b-481">See the comments in [`debug_colors.cc`][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <span data-ttu-id="2024b-482">スクロールパフォーマンスの問題をリアルタイムで見つける</span><span class="sxs-lookup"><span data-stu-id="2024b-482">Find scroll performance issues in realtime</span></span>   

<span data-ttu-id="2024b-483">スクロールパフォーマンスの問題を使って、スクロールに関連するイベントリスナーを持つページの要素を特定し、ページのパフォーマンスに悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2024b-483">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="2024b-484">DevTools では、青緑で問題が発生する可能性のある要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2024b-484">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="2024b-485">スクロールパフォーマンスの問題を表示するには:</span><span class="sxs-lookup"><span data-stu-id="2024b-485">To view scroll performance issues:</span></span>  

1.  <span data-ttu-id="2024b-486">[**レンダリング**] タブを開きます。 「[レンダリングのパフォーマンスを分析する」を](#analyze-rendering-performance-with-the-rendering-tab)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2024b-486">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="2024b-487">[**パフォーマンスの問題のスクロール**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2024b-487">Enable the **Scrolling Performance Issues** checkbox.</span></span>  
 
    > ##### <span data-ttu-id="2024b-488">図42</span><span class="sxs-lookup"><span data-stu-id="2024b-488">Figure 42</span></span>  
    > <span data-ttu-id="2024b-489">**スクロールパフォーマンスの問題**は、非レイヤーのビューポートに制約のあるオブジェクトによってパフォーマンスの低下が発生する可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="2024b-489">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    > ![スクロールパフォーマンスの問題は、非レイヤーのビューポートに制約のあるオブジェクトによってパフォーマンスの低下が発生する可能性があることを示します。][ImageScrollingPerformanceIssues]  
    

<!--    -->  



<!-- image links -->  

[ImageCaptureSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: /microsoft-edge/devtools-guide-chromium/media/collect-garbage-icon.msft.png  
[ImageNextIcon]: /microsoft-edge/devtools-guide-chromium/media/next-icon.msft.png  
[ImagePanModeIcon]: /microsoft-edge/devtools-guide-chromium/media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: /microsoft-edge/devtools-guide-chromium/media/previous-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: /microsoft-edge/devtools-guide-chromium/media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: /microsoft-edge/devtools-guide-chromium/media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: /microsoft-edge/devtools-guide-chromium/media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: /microsoft-edge/devtools-guide-chromium/media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: /microsoft-edge/devtools-guide-chromium/media/show-heaviest-stack-icon.msft.png  

[ImageRecord]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-record-highlight.msft.png "図 1: レコード"  
[ImageRefreshPage]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refresh-button.msft.png "図 2: ページの更新"  
[ImageLoadRecording]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed.msft.png "図 3: ページ読み込みの記録"  
[ImageScreenshots]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png "図 4: [スクリーンショット] チェックボックス"  
[ImageCollectGarbage]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-collect-garbage-button.msft.png "図 5: ガーベジの収集"  
[ImageCaptureSettings]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png "図 6: [キャプチャの設定] セクション"  
[ImageJSSamplesDisabled]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png "図 7: JS サンプルが無効になっている場合のレコーディングの例"  
[ImageJSSamplesEnabled]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png "図 8: JS サンプルが有効な場合のレコーディングの例"  
[ImageSaveProfile]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png "図 9: プロファイルの保存"  
[ImageLoadProfile]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png "図 10: プロファイルの読み込み"  
[ImageClearRecording]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png "図 11: レコーディングをクリアする"  
[ImageZoom]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-zoom-highlighted.msft.png "図 12: 概要の上でマウスをドラッグしてズームする"  
[ImageSearch]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-search-regex.msft.png "図 13: 検索ボックス"  
[ImageMain]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-zoomed.msft.png "図 14: メインセクション"  
[ImageMainEventSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-me.msft.png "図 15: 匿名関数の詳細については、[概要] タブを参照してください。"  
[ImageFlameChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-flame-chart.msft.png "図 16: 炎の図"  
[ImageCallTree]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-call-tree.msft.png "図 17: [通話ツリー] タブ"  
[ImageBottomUp]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-bottoms-up.msft.png "図 18: ボトムアップタブ"  
[ImageEventLog]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-event-log.msft.png "図 19: [イベントログ] タブ"  
[ImageGpu]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-gpu-zoomed.msft.png "図 20: GPU セクション"  
[ImageRaster]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-raster.msft.png "図 21: ラスターセクション"  
[ImageInteractions]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-interactions-animation.msft.png "図 22: [操作] セクション"  
[ImageFpsChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-fps-highlight.msft.png "図 23: FPS グラフ"  
[ImageFramesSection]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-hover.msft.png "図 24: フレームの上にマウスポインターを置く"  
[ImageFrameSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-summary.msft.png "図 25: [概要] タブのフレームの表示"  
[ImageNetworkRequest]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-network.msft.png "図 26: [ネットワーク] セクション"  
[ImageLineBar]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-performance-network.msft.png "図 27: www.bing.com 要求のラインバー表現"  
[ImageTiming]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-network-timing.msft.png "図 28: [ネットワーク] セクション"  
[ImageMemory]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-memory-highlight.msft.png "図 29: メモリチェックボックス"  
[ImageMemoryMetrics]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-memory-chart.msft.png "図 30: メモリの測定値"  
[ImageDuration]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-duration.msft.png "図 31: レコーディングの一部の継続時間を表示する"  
[ImageViewScreenshot]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-screenshots-hover.msft.png "図 32: スクリーンショットの表示"  
[ImageFrameScreenshotSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-preview.msft.png "図 33: [概要] タブのスクリーンショットの表示"  
[ImageFrameScreenshotZoom]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-preview-select.msft.png "図 34: [概要] タブのスクリーンショットを拡大する"  
[ImageLayers]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-layers-all.msft.png "図 35: [レイヤー] ウィンドウ"  
[ImageLayerHover]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png "図 36: レイヤーの強調表示"  
[ImagePaintProfiler]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-paint-profiler.msft.png "図 37: [ペイントプロファイラー] タブ"  
[ImageRenderingTab]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-console-drawer-rendering.msft.png "図 38: [レンダリング] タブ"  
[ImageFpsMeter]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-jank-console-rendering-frame-rate.msft.png "図 39: FPS メーター"  
[ImagePaintFlashing]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png "図 40: ペイントが点滅する"  
[ImageLayerBorders]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png "図 41: レイヤーの境界線"  
[ImageScrollingPerformanceIssues]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png "図 42: スクロールパフォーマンスの問題は、非レイヤーのビューポートの制約を受けると、スクロールのパフォーマンスに悪影響を与える可能性があることを示す"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index#open-the-command-menu "コマンドメニューを開きます (Microsoft Edge の DevTools コマンドメニューを使用してコマンドを実行します)。"  
[DevtoolsEvaluatePerformanceGettingStarted]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/index "実行時のパフォーマンスの分析を開始する"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "アクティビティタブのデモ"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors cc-コードの検索"  

> [!NOTE]
> <span data-ttu-id="2024b-538">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="2024b-538">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2024b-539">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="2024b-539">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="2024b-541">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="2024b-541">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
