---
description: DevTools でパフォーマンスを記録および分析するためのすべての方法Microsoft Edge参照。
title: パフォーマンス分析リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e7774dc0aab647b8cf2bf47699368fafe6c21d70
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439690"
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

# <a name="performance-analysis-reference"></a><span data-ttu-id="c2001-104">パフォーマンス分析リファレンス</span><span class="sxs-lookup"><span data-stu-id="c2001-104">Performance analysis reference</span></span>  

<span data-ttu-id="c2001-105">このページは、パフォーマンスの分析に関連Microsoft Edge DevTools 機能の包括的なリファレンスです。</span><span class="sxs-lookup"><span data-stu-id="c2001-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="c2001-106">[DevTools][MicrosoftEdgeDevTools][はじめに][DevtoolsEvaluatePerformanceGettingStarted]を使用してページのパフォーマンスを分析する方法に関するガイド付きチュートリアルについては、「ランタイム パフォーマンスの分析」に移動Microsoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="c2001-106">Navigate to [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="record-performance"></a><span data-ttu-id="c2001-107">レコードのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="c2001-107">Record performance</span></span>  

### <a name="record-runtime-performance"></a><span data-ttu-id="c2001-108">実行時のパフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="c2001-108">Record runtime performance</span></span>  

<span data-ttu-id="c2001-109">読み込みではなく、実行中のページのパフォーマンスを分析する場合は、実行時のパフォーマンスを記録します。</span><span class="sxs-lookup"><span data-stu-id="c2001-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="c2001-110">分析するページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2001-110">Navigate to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="c2001-111">DevTools **で** パフォーマンス ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-111">Open the **Performance** tool in DevTools.</span></span>  
1.  <span data-ttu-id="c2001-112">**[Record** \( Record icon ![ ](../media/record-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="c2001-112">Choose **Record** \(![Record icon](../media/record-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="c2001-114">Record</span><span class="sxs-lookup"><span data-stu-id="c2001-114">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="c2001-115">ページを操作します。</span><span class="sxs-lookup"><span data-stu-id="c2001-115">Interact with the page.</span></span>  <span data-ttu-id="c2001-116">DevTools は、操作の結果として発生するページアクティビティを記録します。</span><span class="sxs-lookup"><span data-stu-id="c2001-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="c2001-117">もう一 **度 [録音]** を選択するか、[ **停止] を選択して** 記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="c2001-117">Choose **Record** again or choose **Stop** to stop recording.</span></span>  
    
### <a name="record-load-performance"></a><span data-ttu-id="c2001-118">レコードの読み込みパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="c2001-118">Record load performance</span></span>  

<span data-ttu-id="c2001-119">実行中ではなく、読み込み中にページのパフォーマンスを分析する場合は、読み込みパフォーマンスを記録します。</span><span class="sxs-lookup"><span data-stu-id="c2001-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="c2001-120">分析するページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2001-120">Navigate to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="c2001-121">DevTools **の** [パフォーマンス] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="c2001-122">[更新 **] ページ** \( Refresh Page ![ ](../media/refresh-page-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2001-122">Choose **Refresh page** \(![Refresh Page](../media/refresh-page-icon.msft.png)\).</span></span>  <span data-ttu-id="c2001-123">DevTools は、ページの更新中にパフォーマンス 指標を記録し、読み込み完了から数秒後に自動的に記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="c2001-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="[更新] ページ" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="c2001-125">[更新] ページ</span><span class="sxs-lookup"><span data-stu-id="c2001-125">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="c2001-126">DevTools は、ほとんどのアクティビティが発生した記録部分を自動的に拡大表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="ページ読み込み記録" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="c2001-128">ページ読み込み記録</span><span class="sxs-lookup"><span data-stu-id="c2001-128">A page-load recording</span></span>  
:::image-end:::  

### <a name="capture-screenshots-while-recording"></a><span data-ttu-id="c2001-129">記録中にスクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="c2001-129">Capture screenshots while recording</span></span>  

<span data-ttu-id="c2001-130">[スクリーンショット] チェック **ボックスをオン** にすると、記録中にすべてのフレームのスクリーンショットがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="c2001-130">Turn on the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="[スクリーンショット] チェック ボックス" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="c2001-132">[ **スクリーンショット] チェック** ボックス</span><span class="sxs-lookup"><span data-stu-id="c2001-132">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-133">[スクリーンショット [の表示] に移動](#view-a-screenshot) して、スクリーンショットを操作する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="c2001-133">Navigate to [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <a name="force-garbage-collection-while-recording"></a><span data-ttu-id="c2001-134">記録中にガベージ コレクションを強制する</span><span class="sxs-lookup"><span data-stu-id="c2001-134">Force garbage collection while recording</span></span>  

<span data-ttu-id="c2001-135">ページの記録中に、[ガベージを収集 **する]** \( ガベージ アイコン \) を選択してガベージ コレクション ![ ](../media/collect-garbage-icon.msft.png) を強制します。</span><span class="sxs-lookup"><span data-stu-id="c2001-135">While you are recording a page, choose **Collect garbage** \(![Collect garbage icon](../media/collect-garbage-icon.msft.png)\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="ガベージの収集" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="c2001-137">ガベージの収集</span><span class="sxs-lookup"><span data-stu-id="c2001-137">Collect garbage</span></span>  
:::image-end:::  

### <a name="show-recording-settings"></a><span data-ttu-id="c2001-138">記録設定を表示する</span><span class="sxs-lookup"><span data-stu-id="c2001-138">Show recording settings</span></span>  

<span data-ttu-id="c2001-139">DevTools **がパフォーマンス** 記録をキャプチャする方法に関連するその他の設定を公開するには、[ ![ キャプチャ設定 ](../media/capture-settings-icon.msft.png) \( Capture settings \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2001-139">Choose **Capture settings** \(![Capture settings](../media/capture-settings-icon.msft.png)\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text="[キャプチャ設定] セクション" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="c2001-141">[**キャプチャ設定]** セクション</span><span class="sxs-lookup"><span data-stu-id="c2001-141">The **Capture Settings** section</span></span>  
:::image-end:::  

### <a name="disable-javascript-samples"></a><span data-ttu-id="c2001-142">JavaScript サンプルを無効にする</span><span class="sxs-lookup"><span data-stu-id="c2001-142">Disable JavaScript samples</span></span>  

<span data-ttu-id="c2001-143">既定では、レコーディング **のメイン セクション** には、レコーディング中に呼び出された JavaScript 関数の詳細な呼び出し履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="c2001-144">これらの呼び出し履歴を無効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-144">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="c2001-145">[キャプチャ設定 **] メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-145">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="c2001-146">[記録設定 [の表示] に移動します](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="c2001-146">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="c2001-147">[JavaScript サンプルを **無効にする] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="c2001-147">Turn on the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="c2001-148">ページの記録を取ります。</span><span class="sxs-lookup"><span data-stu-id="c2001-148">Take a recording of the page.</span></span>  
    
<span data-ttu-id="c2001-149">次の 2 つの図は、JavaScript サンプルの無効化と有効化の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2001-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="c2001-150">録音 **の** Main セクションは、すべての JavaScript 呼び出しスタックを省略しますので、サンプリングが無効になっている場合にはるかに短くなります。</span><span class="sxs-lookup"><span data-stu-id="c2001-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="JS サンプルが無効になっている場合の記録の例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="c2001-152">JS サンプルが無効になっている場合の記録の例</span><span class="sxs-lookup"><span data-stu-id="c2001-152">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="JS サンプルを有効にした場合の記録の例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="c2001-154">JS サンプルを有効にした場合の記録の例</span><span class="sxs-lookup"><span data-stu-id="c2001-154">An example of a recording when JS samples are turned on</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="throttle-the-network-while-recording"></a><span data-ttu-id="c2001-155">記録中にネットワークを調整する</span><span class="sxs-lookup"><span data-stu-id="c2001-155">Throttle the network while recording</span></span>  

<span data-ttu-id="c2001-156">記録中にネットワークを調整するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c2001-156">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="c2001-157">[キャプチャ設定 **] メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-157">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="c2001-158">[記録設定 [の表示] に移動します](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="c2001-158">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="c2001-159">ネットワーク **を** 調整の目的のレベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="c2001-159">Set **Network** to the desired level of throttling.</span></span>  
    
### <a name="throttle-the-cpu-while-recording"></a><span data-ttu-id="c2001-160">記録中に CPU を調整する</span><span class="sxs-lookup"><span data-stu-id="c2001-160">Throttle the CPU while recording</span></span>  

<span data-ttu-id="c2001-161">記録中に CPU を調整するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c2001-161">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="c2001-162">[キャプチャ設定 **] メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-162">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="c2001-163">[記録設定 [の表示] に移動します](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="c2001-163">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="c2001-164">**CPU を**調整の目的のレベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="c2001-164">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="c2001-165">調整は、コンピューターの機能を基準にしています。</span><span class="sxs-lookup"><span data-stu-id="c2001-165">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="c2001-166">たとえば **、2 倍のスローダウン オプションを使用** すると、CPU の動作は通常の 2 倍遅くなります。</span><span class="sxs-lookup"><span data-stu-id="c2001-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="c2001-167">DevTools は、モバイル デバイスのアーキテクチャがデスクトップやラップトップのアーキテクチャと大違いなので、モバイル デバイスの CPU を実際にシミュレートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2001-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <a name="turn-on-advanced-paint-instrumentation"></a><span data-ttu-id="c2001-168">高度なペイントインストルメンテーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="c2001-168">Turn on advanced paint instrumentation</span></span>  

<span data-ttu-id="c2001-169">ペイントインストルメンテーションの詳細を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-169">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="c2001-170">[キャプチャ設定 **] メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-170">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="c2001-171">[記録設定 [の表示] に移動します](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="c2001-171">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="c2001-172">[高度な **ペイントインストルメンテーションを有効にする (低速)] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="c2001-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="c2001-173">ペイント情報を操作する方法については、「レイヤーの表示」[](#view-layers-information)と「ペイント プロファイラーの表示[」に移動します](#view-paint-profiler)。</span><span class="sxs-lookup"><span data-stu-id="c2001-173">To learn how to interact with the paint information, navigate to [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <a name="save-a-recording"></a><span data-ttu-id="c2001-174">録音を保存する</span><span class="sxs-lookup"><span data-stu-id="c2001-174">Save a recording</span></span>  

<span data-ttu-id="c2001-175">記録を保存するには、コンテキスト メニュー \(右クリック\) を開き、[プロファイルの保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c2001-175">To save a recording, open the contextual menu \(right-click\), and choose **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="プロファイルの保存" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="c2001-177">プロファイルの保存</span><span class="sxs-lookup"><span data-stu-id="c2001-177">Save Profile</span></span>**  
:::image-end:::  

## <a name="load-a-recording"></a><span data-ttu-id="c2001-178">レコーディングを読み込む</span><span class="sxs-lookup"><span data-stu-id="c2001-178">Load a recording</span></span>  

<span data-ttu-id="c2001-179">記録を読み込むには、コンテキスト メニュー \(右クリック\) を開き、[プロファイルの読み込み] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c2001-179">To load a recording, open the contextual menu \(right-click\), and choose **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="プロファイルの読み込み" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="c2001-181">プロファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="c2001-181">Load Profile</span></span>**  
:::image-end:::  

## <a name="clear-the-previous-recording"></a><span data-ttu-id="c2001-182">前の記録をクリアする</span><span class="sxs-lookup"><span data-stu-id="c2001-182">Clear the previous recording</span></span>  

<span data-ttu-id="c2001-183">録音を行った後、[記録を **クリアする** ]\( [録音のクリア] アイコン \) を選択して、[パフォーマンス] パネルからその ![ ](../media/clear-recording-icon.msft.png) 録音を **クリア** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-183">After making a recording, choose **Clear recording** \(![Clear recording icon](../media/clear-recording-icon.msft.png)\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="録音のクリア" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="c2001-185">録音のクリア</span><span class="sxs-lookup"><span data-stu-id="c2001-185">Clear recording</span></span>**  
:::image-end:::  

## <a name="analyze-a-performance-recording"></a><span data-ttu-id="c2001-186">パフォーマンス記録を分析する</span><span class="sxs-lookup"><span data-stu-id="c2001-186">Analyze a performance recording</span></span>  

<span data-ttu-id="c2001-187">実行時の[パフォーマンスまたはレコードの](#record-runtime-performance)[読み](#record-load-performance)込みパフォーマンス\*\*\*\* を記録した後、パフォーマンス パネルには、発生した処理のパフォーマンスを分析するための多くのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <a name="select-a-portion-of-a-recording"></a><span data-ttu-id="c2001-188">録音の一部を選択する</span><span class="sxs-lookup"><span data-stu-id="c2001-188">Select a portion of a recording</span></span>  

<span data-ttu-id="c2001-189">マウスを [概要] の左または右に **ドラッグして** 、録音の一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2001-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="c2001-190">Overview**は\*\*\*\*、FPS、CPU、および** **NET**グラフを含む**セクション**です。</span><span class="sxs-lookup"><span data-stu-id="c2001-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="ズームするには、概要の上にマウスをドラッグします" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="c2001-192">ズームするには、概要の上に **マウスを** ドラッグします</span><span class="sxs-lookup"><span data-stu-id="c2001-192">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-193">キーボードを使用して部分を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c2001-193">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="c2001-194">[メイン] セクションの**背景**を選択するか、その横にある [インタラクション] 、[ネットワーク] 、**または [GPU]** などの**セクションを選択**します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c2001-194">Choose the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="c2001-195">このキーボード ワークフローは、これらのセクションの 1 つがフォーカスされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c2001-195">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="c2001-196">、 、 キーを使用して、それぞれ拡大、左、縮小、 `W` `A` `S` `D` 右に移動します。</span><span class="sxs-lookup"><span data-stu-id="c2001-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="c2001-197">トラックパッドを使用して部分を選択するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-197">To select a portion using a trackpad, complete the following actions.</span></span>  

1.  <span data-ttu-id="c2001-198">[概要] セクションまたは [詳細] **セクション** の上にマウスポインター **を移動** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-198">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="c2001-199">[ **概要** ] セクションは **、FPS、CPU、および** **NET**グラフを含む **領域** です。</span><span class="sxs-lookup"><span data-stu-id="c2001-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="c2001-200">[ **詳細]** セクションは、[メイン] セクション、[ **操作** ] セクションを **含む領域** です。</span><span class="sxs-lookup"><span data-stu-id="c2001-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="c2001-201">2 本の指を使用して、上にスワイプして縮小し、左にスワイプして左に移動し、下にスワイプして拡大し、右にスワイプして右に移動します。</span><span class="sxs-lookup"><span data-stu-id="c2001-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="c2001-202">[メイン] セクションまたは隣接する\*\*\*\* 任意の領域で長いフレーム グラフをスクロールするには、上下にドラッグしながら長押しします。</span><span class="sxs-lookup"><span data-stu-id="c2001-202">To scroll a long flame chart in the **Main** section or any of the neighbors, choose and hold while dragging up and down.</span></span>  <span data-ttu-id="c2001-203">左右にドラッグして、選択した録音部分を移動します。</span><span class="sxs-lookup"><span data-stu-id="c2001-203">Drag left and right to move what portion of the recording is chosen.</span></span>  

### <a name="search-activities"></a><span data-ttu-id="c2001-204">検索アクティビティ</span><span class="sxs-lookup"><span data-stu-id="c2001-204">Search activities</span></span>  

<span data-ttu-id="c2001-205">`Control` + `F` \(Windows,Linux\) または `Command` + `F` \(macOS\) を**選択**して、[パフォーマンス] パネルの下部にある検索ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-205">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="検索ボックス" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="c2001-207">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="c2001-207">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-208">クエリに一致するアクティビティを移動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c2001-208">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="c2001-209">[前 **の** \( ![ 前 ](../media/previous-icon.msft.png) の \) ] ボタンと [ **次** へ] \( ![ Next ](../media/next-icon.msft.png) \) ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2001-209">Use the **Previous** \(![Previous](../media/previous-icon.msft.png)\) and **Next** \(![Next](../media/next-icon.msft.png)\) buttons.</span></span>  
*   <span data-ttu-id="c2001-210">前 `Shift` + `Enter` の項目を選択するか、次 `Enter` の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2001-210">Select `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="c2001-211">クエリ設定を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-211">To modify query settings:</span></span>  

*   <span data-ttu-id="c2001-212">クエリ **で大文字と** 小文字を区別するには、[大文字と小文字を区別 ![ ](../media/search-case-icon.msft.png) する]を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2001-212">Choose **Case sensitive** \(![Case sensitive](../media/search-case-icon.msft.png)\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="c2001-213">クエリ **で正規表現** を ![ ](../media/search-regex-icon.msft.png) 使用するには、Regex \( Regex \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2001-213">Choose **Regex** \(![Regex](../media/search-regex-icon.msft.png)\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="c2001-214">検索ボックスを非表示にする場合は、[キャンセル] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c2001-214">To hide the search box, choose **Cancel**.</span></span>  

### <a name="view-main-thread-activity"></a><span data-ttu-id="c2001-215">メイン スレッドアクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="c2001-215">View main thread activity</span></span>  

<span data-ttu-id="c2001-216">[メイン] **セクション** を使用して、ページのメイン スレッドで発生したアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="[メイン] セクション" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="c2001-218">[ **メイン]** セクション</span><span class="sxs-lookup"><span data-stu-id="c2001-218">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-219">イベントを選択すると、[概要] パネルにイベントの詳細 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-219">Choose an event to view more information about it in the **Summary** panel.</span></span>  <span data-ttu-id="c2001-220">DevTools は、選択したイベントの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-220">DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="[概要] パネルの匿名関数の詳細" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="c2001-222">[概要] パネル `anonymous` の関数**の詳細**</span><span class="sxs-lookup"><span data-stu-id="c2001-222">More information about the `anonymous` function in the **Summary** panel</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-223">DevTools は、フレーム グラフを使用したメイン スレッド アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-223">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="c2001-224">x 軸は、時間の間の記録を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-224">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="c2001-225">y 軸は呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-225">The y-axis represents the call stack.</span></span>  <span data-ttu-id="c2001-226">上のイベントは、その下のイベントを引き起こします。</span><span class="sxs-lookup"><span data-stu-id="c2001-226">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="炎のグラフ" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="c2001-228">炎のグラフ</span><span class="sxs-lookup"><span data-stu-id="c2001-228">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-229">前の図では、イベント `click` によって `Function Call` 53 行目に `activitytabs.js` in が発生しました。</span><span class="sxs-lookup"><span data-stu-id="c2001-229">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="c2001-230">以下 `Function Call` に、匿名関数が実行されたと確認します。</span><span class="sxs-lookup"><span data-stu-id="c2001-230">Below `Function Call`, review that an anonymous function was run.</span></span>  <span data-ttu-id="c2001-231">要求された 、要求 `a` された匿名 `wait` 関数 `Minor GC` 。</span><span class="sxs-lookup"><span data-stu-id="c2001-231">The anonymous function requested `a`, which requested `wait`, which requested `Minor GC`.</span></span>  

<span data-ttu-id="c2001-232">DevTools はスクリプトにランダムな色を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c2001-232">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="c2001-233">前の図では、1 つのスクリプトからの関数要求は淡緑色です。</span><span class="sxs-lookup"><span data-stu-id="c2001-233">In the previous figure, function requests from one script are colored light green.</span></span>  <span data-ttu-id="c2001-234">別のスクリプトからの要求は、色はベージュです。</span><span class="sxs-lookup"><span data-stu-id="c2001-234">Requests from another script are colored beige.</span></span>  <span data-ttu-id="c2001-235">濃い黄色はスクリプト アクティビティを表し、紫色のイベントはレンダリング アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-235">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="c2001-236">これらの濃い黄色と紫色のイベントは、すべての録音で一貫しています。</span><span class="sxs-lookup"><span data-stu-id="c2001-236">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="c2001-237">JavaScript [要求の詳細な](#disable-javascript-samples) フレーム グラフを非表示にする場合は、[JavaScript サンプルを無効にする] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c2001-237">Navigate to [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript requests.</span></span>  <span data-ttu-id="c2001-238">JS サンプルが無効になっている場合は、前の図のような高レベルの `Event: choose` `Function Call` イベントだけが表示 `str` されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-238">When JS samples are disabled, only high-level events such as `Event: choose` and `Function Call` from the previous figure `str` displayed.</span></span>  

### <a name="view-activities-in-a-table"></a><span data-ttu-id="c2001-239">テーブル内のアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="c2001-239">View activities in a table</span></span>  

<span data-ttu-id="c2001-240">ページを記録した後は、アクティビティを分析するために[ **メイン** ] セクションのみに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2001-240">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="c2001-241">DevTools には、アクティビティを分析するための 3 つの表形式ビューも用意されています。</span><span class="sxs-lookup"><span data-stu-id="c2001-241">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="c2001-242">各ビューでは、アクティビティについて異なる視点を示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-242">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="c2001-243">最も作業の原因となるルート アクティビティを表示する場合は、[呼び出しツリー] [パネルを使用](#the-call-tree-panel) します。</span><span class="sxs-lookup"><span data-stu-id="c2001-243">When you want to view the root activities that cause the most work, use the [Call Tree](#the-call-tree-panel) panel.</span></span>  
*   <span data-ttu-id="c2001-244">最も多くの時間が直接費やされたアクティビティを表示する場合は、ボトム [アップ パネルを使用](#the-bottom-up-panel) します。</span><span class="sxs-lookup"><span data-stu-id="c2001-244">When you want to view the activities where the most time was directly spent, use the [Bottom-Up](#the-bottom-up-panel) panel.</span></span>  
*   <span data-ttu-id="c2001-245">記録中にアクティビティが発生した順序で表示する場合は、[イベント ログ] パネル [を使用](#the-event-log-panel) します。</span><span class="sxs-lookup"><span data-stu-id="c2001-245">When you want to view the activities in the order in which they occurred during the recording, use the [Event Log](#the-event-log-panel) panel.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="c2001-246">次の 3 つのセクションはすべて同じデモを参照します。</span><span class="sxs-lookup"><span data-stu-id="c2001-246">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="c2001-247">アクティビティ タブのデモでデモ [を自分で実行します][ActivityTabsDemo]。</span><span class="sxs-lookup"><span data-stu-id="c2001-247">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <a name="root-activities"></a><span data-ttu-id="c2001-248">ルート アクティビティ</span><span class="sxs-lookup"><span data-stu-id="c2001-248">Root activities</span></span>  

<span data-ttu-id="c2001-249">ここでは、コール ツリー**パネル、ボトム**アップ パネル、および\*\*\*\* イベント ログ\*\*\*\* パネルに記載されているルート アクティビティの概念**について説明**します。</span><span class="sxs-lookup"><span data-stu-id="c2001-249">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** panel, **Bottom-Up** panel, and **Event Log** panel.</span></span>  

<span data-ttu-id="c2001-250">ルート アクティビティは、ブラウザーが何らかの作業を行う原因となるアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="c2001-250">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="c2001-251">たとえば、Web ページを選択すると、ブラウザーはルート `Event` アクティビティとしてアクティビティを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-251">For example, when you choose a webpage, the browser runs an `Event` activity as the root activity.</span></span>  <span data-ttu-id="c2001-252">そのため `Event` 、ハンドラーが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2001-252">That `Event` may cause a handler to run, and so on.</span></span>  

<span data-ttu-id="c2001-253">[メイン] セクションのフレーム **グラフでは** 、ルート アクティビティはグラフの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-253">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="c2001-254">[呼 **び出しツリー]** **パネルと [イベント ログ] パネル** では、ルート アクティビティがトップ レベルのアイテムです。</span><span class="sxs-lookup"><span data-stu-id="c2001-254">In the **Call Tree** and **Event Log** panels, root activities are the top-level items.</span></span>  

<span data-ttu-id="c2001-255">ルート アクティビティ [の例については、[呼び](#the-call-tree-panel) 出しツリー] パネルに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2001-255">Navigate to the [Call Tree](#the-call-tree-panel) panel for an example of root activities.</span></span>  

#### <a name="the-call-tree-panel"></a><span data-ttu-id="c2001-256">[呼び出しツリー] パネル</span><span class="sxs-lookup"><span data-stu-id="c2001-256">The Call Tree panel</span></span>  

<span data-ttu-id="c2001-257">[呼び **出しツリー] パネル** を使用して、最 [も多くの作業を引き起](#root-activities) こすルート アクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-257">Use the **Call Tree** panel to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="c2001-258">[ **呼び出しツリー]** パネルには、録音の選択した部分の間にのみアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-258">The **Call Tree** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="c2001-259">[録音の [一部を選択する] に](#select-a-portion-of-a-recording) 移動して、部分を選択する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="c2001-259">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="[呼び出しツリー] パネル" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="c2001-261">[ **呼び出しツリー]** パネル</span><span class="sxs-lookup"><span data-stu-id="c2001-261">The **Call Tree** panel</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-262">前の図では、[アクティビティ] 列のアイテムのトップ\*\*\*\* レベル (ルート アクティビティなど) `Evaluate Script` `Parse HTML` を示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-262">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="c2001-263">入れ子は呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-263">The nesting represents the call stack.</span></span>  <span data-ttu-id="c2001-264">たとえば、前の図では、 `Parse HTML` 原因と原因が `Evaluate Script` `Compile Script` . `(anonymous)`</span><span class="sxs-lookup"><span data-stu-id="c2001-264">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="c2001-265">**Self Time は** 、そのアクティビティに直接費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-265">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="c2001-266">**[合計時間** ] は、そのアクティビティまたはすべての子で費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-266">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="c2001-267">[**自己時間]、[\*\*\*\*合計時間]、** または [**アクティビティ]** を選択して、その列でテーブルを並べ替える。</span><span class="sxs-lookup"><span data-stu-id="c2001-267">Choose **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="c2001-268">[フィルター] **テキスト ボックス** を使用して、アクティビティ名でイベントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c2001-268">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="c2001-269">既定では、[ **グループ化] メニュー** は [グループ化なし **] に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="c2001-269">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="c2001-270">[グループ **化] メニューを使用** して、さまざまな条件に基づいてアクティビティ テーブルを並べ替える。</span><span class="sxs-lookup"><span data-stu-id="c2001-270">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="c2001-271">[ **最も重いスタック** \( 最も重いスタック \を表示する] を選択して、アクティビティ テーブルの右側に別のテーブル ![ ](../media/show-heaviest-stack-icon.msft.png) を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-271">Choose **Show Heaviest Stack** \(![Show Heaviest Stack](../media/show-heaviest-stack-icon.msft.png)\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="c2001-272">最も重いスタック テーブルを設定 **するアクティビティを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-272">Choose an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="c2001-273">[ **最も重いスタック]** テーブルには、選択したアクティビティの子の実行に最も時間がかかった時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-273">The **Heaviest Stack** table displays which children of the selected activity took the longest time to run.</span></span>  

#### <a name="the-bottom-up-panel"></a><span data-ttu-id="c2001-274">[Bottom-Up] パネル</span><span class="sxs-lookup"><span data-stu-id="c2001-274">The Bottom-Up panel</span></span>  

<span data-ttu-id="c2001-275">ボトムアップ **パネルを使用して** 、集計で最も時間がかかったアクティビティを直接表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-275">Use the **Bottom-Up** panel to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="c2001-276">ボトム **アップ パネルには、** 記録の選択した部分の間にのみアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-276">The **Bottom-Up** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="c2001-277">[録音の [一部を選択する] に](#select-a-portion-of-a-recording) 移動して、部分を選択する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="c2001-277">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="[Bottom-Up] パネル" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="c2001-279">[ **ボトムアップ]** パネル</span><span class="sxs-lookup"><span data-stu-id="c2001-279">The **Bottom-Up** panel</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-280">前の **図のメイン** セクションのフレーム グラフで、ほとんどすべての時間が実行に費やされた状態に移動します `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="c2001-280">In the **Main** section flame chart of the previous figure, navigate to that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="c2001-281">前の図の **ボトムアップ パネルの** トップ アクティビティはです `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="c2001-281">The top activity in the **Bottom-Up** panel of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="c2001-282">[ボトムアップ] **パネルに移動** します。次に最も高価なアクティビティは `Layout` です。</span><span class="sxs-lookup"><span data-stu-id="c2001-282">Navigate to the **Bottom-Up** panel, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="c2001-283">[Self **Time]** 列は、すべての発生回数にわたって、そのアクティビティに直接費やされた集計時間を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-283">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="c2001-284">[ **合計時間]** 列は、そのアクティビティまたは子の合計時間を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-284">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <a name="the-event-log-panel"></a><span data-ttu-id="c2001-285">[イベント ログ] パネル</span><span class="sxs-lookup"><span data-stu-id="c2001-285">The Event Log panel</span></span>  

<span data-ttu-id="c2001-286">[イベント **ログ] パネル** を使用して、記録中にアクティビティが発生した順序でアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-286">Use the **Event Log** panel to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="c2001-287">[ **イベント ログ] パネル** には、記録の選択した部分の間にのみアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-287">The **Event Log** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="c2001-288">[録音の [一部を選択する] に](#select-a-portion-of-a-recording) 移動して、部分を選択する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="c2001-288">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="[イベント ログ] パネル" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="c2001-290">[ **イベント ログ]** パネル</span><span class="sxs-lookup"><span data-stu-id="c2001-290">The **Event Log** panel</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-291">[ **開始時刻]** 列は、記録の開始位置を基準として、そのアクティビティが開始されたポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-291">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="c2001-292">たとえば、前の図の選択したアイテムの開始時刻は、記録の開始後 `175.7 ms` にアクティビティが 175.7 ミリ秒を開始したという意味です。</span><span class="sxs-lookup"><span data-stu-id="c2001-292">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="c2001-293">[Self **Time]** 列は、そのアクティビティに直接費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-293">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="c2001-294">[ **合計時間]** 列は、そのアクティビティまたは子の中で直接費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-294">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="c2001-295">[**開始時刻]、[\*\*\*\*自己時間]、** または [**合計**時間] を選択して、その列でテーブルを並べ替える。</span><span class="sxs-lookup"><span data-stu-id="c2001-295">Choose **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="c2001-296">[フィルター] **テキスト ボックス** を使用して、アクティビティを名前でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c2001-296">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="c2001-297">[期間 **] メニューを** 使用して、1 ミリ秒未満または 15 ミリ秒未満のアクティビティをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c2001-297">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="c2001-298">既定では、[ **期間] メニュー** は [すべて] に **設定**され、すべてのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-298">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="c2001-299">これらのカテゴリ**からすべての**アクティビティ**をフィルター処理**するには、[\*\*\*\* 読み込み **]、[スクリプト]、[レンダリング**]、または [ペイント] チェック ボックスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c2001-299">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <a name="view-gpu-activity"></a><span data-ttu-id="c2001-300">GPU アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="c2001-300">View GPU activity</span></span>  

<span data-ttu-id="c2001-301">[GPU] セクションで GPU アクティビティ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-301">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="[GPU] セクション" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="c2001-303">**[GPU]** セクション</span><span class="sxs-lookup"><span data-stu-id="c2001-303">The **GPU** section</span></span>  
:::image-end:::  

### <a name="view-raster-activity"></a><span data-ttu-id="c2001-304">ラスター アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="c2001-304">View raster activity</span></span>  

<span data-ttu-id="c2001-305">[ラスター] セクションでラスター アクティビティ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-305">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="[ラスター] セクション" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="c2001-307">[ **ラスター]** セクション</span><span class="sxs-lookup"><span data-stu-id="c2001-307">The **Raster** section</span></span>  
:::image-end:::  

### <a name="view-interactions"></a><span data-ttu-id="c2001-308">操作の表示</span><span class="sxs-lookup"><span data-stu-id="c2001-308">View interactions</span></span>  

<span data-ttu-id="c2001-309">[操作 **] セクションを** 使用して、記録中に発生したユーザー操作を検索して分析します。</span><span class="sxs-lookup"><span data-stu-id="c2001-309">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="[対話] セクション" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="c2001-311">[ **対話]** セクション</span><span class="sxs-lookup"><span data-stu-id="c2001-311">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-312">操作の下部にある赤い線は、メイン スレッドの待機に費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="c2001-312">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="c2001-313">操作を選択して、その詳細を [概要] パネル **に表示** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-313">Choose an interaction to view more information about it in the **Summary** panel.</span></span>  

### <a name="analyze-frames-per-second-fps"></a><span data-ttu-id="c2001-314">1 秒あたりのフレーム数の分析 (FPS)</span><span class="sxs-lookup"><span data-stu-id="c2001-314">Analyze frames per second (FPS)</span></span>  

<span data-ttu-id="c2001-315">DevTools には、1 秒あたりのフレーム数を分析するさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="c2001-315">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="c2001-316">FPS [グラフを使用して](#the-fps-chart) 、記録期間中の FPS の概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2001-316">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="c2001-317">[ [フレーム] セクションを使用](#the-frames-section) して、特定のフレームにかかった時間を表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-317">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="c2001-318">ページの **実行時に、FPS** のリアルタイム推定値として FPS メーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2001-318">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="c2001-319">FPS メーターを [使用してリアルタイムで 1 秒あたりのフレーム数を表示するに移動します](#view-frames-per-second-in-realtime-with-the-fps-meter)。</span><span class="sxs-lookup"><span data-stu-id="c2001-319">Navigate to [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <a name="the-fps-chart"></a><span data-ttu-id="c2001-320">FPS グラフ</span><span class="sxs-lookup"><span data-stu-id="c2001-320">The FPS chart</span></span>  

<span data-ttu-id="c2001-321">**FPS グラフ**は、記録期間中のフレーム レートの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-321">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="c2001-322">一般に、緑のバーが大きいほど、フレーム レートが向上します。</span><span class="sxs-lookup"><span data-stu-id="c2001-322">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="c2001-323">FPS グラフの上の **赤い** バーは、フレーム レートが低く低下し、ユーザーのエクスペリエンスに害を与えた可能性があるという警告です。</span><span class="sxs-lookup"><span data-stu-id="c2001-323">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="c2001-325">**FPS グラフ**</span><span class="sxs-lookup"><span data-stu-id="c2001-325">The **FPS** chart</span></span>  
:::image-end:::  

#### <a name="the-frames-section"></a><span data-ttu-id="c2001-326">[フレーム] セクション</span><span class="sxs-lookup"><span data-stu-id="c2001-326">The Frames section</span></span>  

<span data-ttu-id="c2001-327">[ **フレーム]** セクションでは、特定のフレームにかかった時間を正確に示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-327">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="c2001-328">フレームにマウス ポインターを合わせると、ヒントに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-328">Hover on a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="フレームにカーソルを合わせる" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="c2001-330">フレームにカーソルを合わせる</span><span class="sxs-lookup"><span data-stu-id="c2001-330">Hover on a frame</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-331">[概要] パネルでフレームの詳細を表示するには、フレーム **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-331">Choose a frame to view more information about the frame in the **Summary** panel.</span></span>  <span data-ttu-id="c2001-332">DevTools は、選択したフレームの輪郭を青で示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-332">DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="[概要] パネルでフレームを表示する" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="c2001-334">[概要] パネルでフレーム **を表示** する</span><span class="sxs-lookup"><span data-stu-id="c2001-334">View a frame in the **Summary** panel</span></span>  
:::image-end:::  

### <a name="view-network-requests"></a><span data-ttu-id="c2001-335">ネットワーク要求の表示</span><span class="sxs-lookup"><span data-stu-id="c2001-335">View network requests</span></span>  

<span data-ttu-id="c2001-336">[ネットワーク **] セクションを** 展開して、記録中に発生したネットワーク要求のウォーターフォールを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-336">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="[ネットワーク] セクション" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="c2001-338">[ **ネットワーク]** セクション</span><span class="sxs-lookup"><span data-stu-id="c2001-338">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-339">要求は、次のように色分けされています。</span><span class="sxs-lookup"><span data-stu-id="c2001-339">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="c2001-340">HTML: 青</span><span class="sxs-lookup"><span data-stu-id="c2001-340">HTML: Blue</span></span>  
*   <span data-ttu-id="c2001-341">CSS: Purple</span><span class="sxs-lookup"><span data-stu-id="c2001-341">CSS: Purple</span></span>  
*   <span data-ttu-id="c2001-342">JS: 黄色</span><span class="sxs-lookup"><span data-stu-id="c2001-342">JS: Yellow</span></span>  
*   <span data-ttu-id="c2001-343">画像: 緑</span><span class="sxs-lookup"><span data-stu-id="c2001-343">Images: Green</span></span>  
    
<span data-ttu-id="c2001-344">要求を選択して、その詳細を [概要] パネル **で表示** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-344">Choose a request to view more information about it in the **Summary** panel.</span></span>  <span data-ttu-id="c2001-345">たとえば、前の図では、[概要]\*\*\*\* パネルに、[ネットワーク] セクションで選択されている青色の要求に関する詳細が**表示**されています。</span><span class="sxs-lookup"><span data-stu-id="c2001-345">For example, in the previous figure, the **Summary** panel is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="c2001-346">要求の左上の濃い青色の四角形は、優先度の高い要求を意味します。</span><span class="sxs-lookup"><span data-stu-id="c2001-346">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="c2001-347">明るい青の四角形は優先度の低い四角形を意味します。</span><span class="sxs-lookup"><span data-stu-id="c2001-347">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="c2001-348">たとえば、前の図では、青色の選択された要求の優先度が高く、下の緑色の要求は優先度が低くなります。</span><span class="sxs-lookup"><span data-stu-id="c2001-348">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="c2001-349">次の図の 1st では、要求は左側の行、中央に濃い部分と明るい部分を持つバー、右側の線で表 `www.bing.com` されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-349">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="c2001-350">次の図の 2nd では、ネットワーク ツールのタイミング パネルに同\*\*\*\* じ要求の対応する表現を**示**します。</span><span class="sxs-lookup"><span data-stu-id="c2001-350">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** panel of the **Network** tool.</span></span>  <span data-ttu-id="c2001-351">これら 2 つの表現が互いにマップされる方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-351">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="c2001-352">左側の行は、イベントのグループまでの `Connection Start` すべてです。すべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2001-352">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="c2001-353">言い換えれば、前のすべてです `Request Sent` 。排他的です。</span><span class="sxs-lookup"><span data-stu-id="c2001-353">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="c2001-354">バーの明るい部分は `Request Sent` 、 です `Waiting (TTFB)` 。</span><span class="sxs-lookup"><span data-stu-id="c2001-354">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="c2001-355">バーの暗い部分はです `Content Download` 。</span><span class="sxs-lookup"><span data-stu-id="c2001-355">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="c2001-356">正しい行は、基本的にメイン スレッドの待機に費やされた時間です。</span><span class="sxs-lookup"><span data-stu-id="c2001-356">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="c2001-357">これは、[タイミング] パネルでは **表** されません。</span><span class="sxs-lookup"><span data-stu-id="c2001-357">This is not represented in the **Timing** panel.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="要求の行バー www.bing.com 表示" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="c2001-359">要求の行バー `www.bing.com` 表現</span><span class="sxs-lookup"><span data-stu-id="c2001-359">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="ネットワーク ツール" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="c2001-361">ネットワーク**ツール**</span><span class="sxs-lookup"><span data-stu-id="c2001-361">The **Network** tool</span></span>  
<span data-ttu-id="c2001-362">: ::image-end:::</span><span class="sxs-lookup"><span data-stu-id="c2001-362">:     ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <a name="view-memory-metrics"></a><span data-ttu-id="c2001-363">メモリ メトリックを表示する</span><span class="sxs-lookup"><span data-stu-id="c2001-363">View memory metrics</span></span>  

<span data-ttu-id="c2001-364">[メモリ] チェック **ボックスを** オンにすると、前回の記録のメモリ メトリックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-364">Turn on the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="[メモリ] チェック ボックス" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="c2001-366">[ **メモリ]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="c2001-366">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-367">DevTools は、[概要] **パネルの上** に新しいメモリ グラフ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-367">DevTools displays a new **Memory** chart, above the **Summary** panel.</span></span>  <span data-ttu-id="c2001-368">NET グラフの下には **、HEAP** と呼ばれる新しいグラフ **があります**。</span><span class="sxs-lookup"><span data-stu-id="c2001-368">There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="c2001-369">**HEAP グラフ**は、メモリ グラフの**JS ヒープ**行と同じ情報を**提供**します。</span><span class="sxs-lookup"><span data-stu-id="c2001-369">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="メモリ メトリック" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="c2001-371">メモリ メトリック</span><span class="sxs-lookup"><span data-stu-id="c2001-371">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-372">グラフの色付き線は、グラフの上の色付きチェック ボックスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="c2001-372">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="c2001-373">グラフからそのカテゴリを非表示にするには、チェック ボックスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c2001-373">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="c2001-374">グラフには、現在選択されている記録の領域だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-374">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="c2001-375">たとえば、前の図では、メモリ\*\*\*\* グラフは 400 ミリ秒のマークから 1750 ミリ秒のマークの周りのメモリ使用量のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2001-375">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <a name="view-the-duration-of-a-portion-of-a-recording"></a><span data-ttu-id="c2001-376">記録の一部の期間を表示する</span><span class="sxs-lookup"><span data-stu-id="c2001-376">View the duration of a portion of a recording</span></span>  

<span data-ttu-id="c2001-377">Network や\*\*Main\*\*\*\*\*\* などのセクションを分析する場合、特定のイベントにかかった時間の正確な推定値が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c2001-377">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="c2001-378">録音 `Shift` の一部を選択するには、長押し、左または右にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c2001-378">Hold `Shift`, choose and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="c2001-379">選択内容の下部に、DevTools はその部分にかかった時間を示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-379">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="記録の一部の期間を表示する" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="c2001-381">記録の一部の期間を表示する</span><span class="sxs-lookup"><span data-stu-id="c2001-381">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <a name="view-a-screenshot"></a><span data-ttu-id="c2001-382">スクリーンショットの表示</span><span class="sxs-lookup"><span data-stu-id="c2001-382">View a screenshot</span></span>  

<span data-ttu-id="c2001-383">[記録中 [にスクリーンショットをキャプチャ](#capture-screenshots-while-recording) する] に移動して、スクリーンショットを有効にする方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="c2001-383">Navigate to [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to turn on screenshots.</span></span>  

<span data-ttu-id="c2001-384">[概要] **にカーソル** を合わせると、記録中にページがどのように表示されたのかのスクリーンショットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-384">Hover on the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="c2001-385">概要**は**、CPU、FPS、および**NET\*\*\*\*\*\* グラフを含む**セクション\*\*です。</span><span class="sxs-lookup"><span data-stu-id="c2001-385">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="スクリーンショットの表示" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="c2001-387">スクリーンショットの表示</span><span class="sxs-lookup"><span data-stu-id="c2001-387">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-388">[フレーム] セクションでフレームを選択してスクリーンショットを **表示** することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2001-388">You may also view screenshots by choosing a frame in the **Frames** section.</span></span>  <span data-ttu-id="c2001-389">DevTools は、[概要] パネルに小さなバージョンの **スクリーンショットを表示** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-389">DevTools displays a small version of the screenshot in the **Summary** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="[概要] パネルでスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="c2001-391">[概要] パネルでスクリーンショット **を表示** する</span><span class="sxs-lookup"><span data-stu-id="c2001-391">View a screenshot in the **Summary** panel</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-392">[概要] パネルでサムネイル **を選択** して、スクリーンショットを拡大します。</span><span class="sxs-lookup"><span data-stu-id="c2001-392">Choose the thumbnail in the **Summary** panel to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="[概要] パネルからスクリーンショットを拡大する" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="c2001-394">[概要] パネルからスクリーンショット **を拡大** する</span><span class="sxs-lookup"><span data-stu-id="c2001-394">Zoom into a screenshot from the **Summary** panel</span></span>  
:::image-end:::  

### <a name="view-layers-information"></a><span data-ttu-id="c2001-395">レイヤー情報の表示</span><span class="sxs-lookup"><span data-stu-id="c2001-395">View layers information</span></span>  

<span data-ttu-id="c2001-396">フレームに関する高度なレイヤー情報を表示するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2001-396">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="c2001-397">[高度なペイントインストルメンテーションを有効にする](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="c2001-397">[Turn on advanced paint instrumentation](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="c2001-398">[フレーム] セクションでフレーム **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="c2001-398">Choose a frame in the **Frames** section.</span></span>  <span data-ttu-id="c2001-399">DevTools は、新しい [レイヤー]\*\*\*\* パネルの [イベント ログ] パネルの横に、レイヤーに関する**情報を表示**します。</span><span class="sxs-lookup"><span data-stu-id="c2001-399">DevTools displays information about the layers in the new **Layers** panel, next to the **Event Log** panel.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="[レイヤー] ウィンドウ" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="c2001-401">[ **レイヤー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="c2001-401">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="c2001-402">レイヤーにカーソルを合わせると、図で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-402">Hover on a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="レイヤーを強調表示する" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="c2001-404">レイヤーを強調表示する</span><span class="sxs-lookup"><span data-stu-id="c2001-404">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="c2001-405">図を移動するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-405">To move the diagram:</span></span>  

*   <span data-ttu-id="c2001-406">X **軸と** Y 軸に沿って移動するには、[パン モード\] (パン モード ![ ](../media/pan-mode-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2001-406">Choose **Pan Mode** \(![Pan Mode](../media/pan-mode-icon.msft.png)\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="c2001-407">Z **軸に沿って** 回転するには、[回転 ![ モード ](../media/rotate-mode-icon.msft.png) \] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2001-407">Choose **Rotate Mode** \(![Rotate Mode](../media/rotate-mode-icon.msft.png)\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="c2001-408">[Reset **Transform** \( ![ Reset Transform \) ] を ](../media/reset-transform-icon.msft.png) 選択して、ダイアグラムを元の位置にリセットします。</span><span class="sxs-lookup"><span data-stu-id="c2001-408">Choose **Reset Transform** \(![Reset Transform](../media/reset-transform-icon.msft.png)\) to reset the diagram to the original position.</span></span>  
    
### <a name="view-paint-profiler"></a><span data-ttu-id="c2001-409">ペイント プロファイラーの表示</span><span class="sxs-lookup"><span data-stu-id="c2001-409">View paint profiler</span></span>  

<span data-ttu-id="c2001-410">ペイント イベントに関する詳細な情報を表示するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-410">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="c2001-411">[をオンにする](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="c2001-411">[Turn on](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="c2001-412">[メイン]**セクションペイント**イベントを**選択**します。</span><span class="sxs-lookup"><span data-stu-id="c2001-412">Choose a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="[ペイントプロファイル] パネル" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="c2001-414">[**プロファイルペイント]** パネル</span><span class="sxs-lookup"><span data-stu-id="c2001-414">The **Paint Profiler** panel</span></span>  
    :::image-end:::  
    
## <a name="analyze-rendering-performance-with-the-rendering-tool"></a><span data-ttu-id="c2001-415">レンダリング ツールを使用してレンダリングパフォーマンスを分析する</span><span class="sxs-lookup"><span data-stu-id="c2001-415">Analyze rendering performance with the Rendering tool</span></span>  

<span data-ttu-id="c2001-416">[レンダリング] パネルの **機能を使用** して、ページのレンダリングパフォーマンスを視覚化します。</span><span class="sxs-lookup"><span data-stu-id="c2001-416">Use the features of the **Rendering** panel to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="c2001-417">レンダリング ツール **を開く** 方法:</span><span class="sxs-lookup"><span data-stu-id="c2001-417">To open the **Rendering** tool:</span></span>  

1.  <span data-ttu-id="c2001-418">[コマンド メニューを開きます][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="c2001-418">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="c2001-419">入力を開始 `Rendering` して選択します `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="c2001-419">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="c2001-420">DevTools は **、DevTools** ウィンドウの下部にレンダリング ツールを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-420">DevTools displays the **Rendering** tool at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="レンダリング ツール" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="c2001-422">レンダリング**ツール**</span><span class="sxs-lookup"><span data-stu-id="c2001-422">The **Rendering** tool</span></span>  
    :::image-end:::  
    
### <a name="view-frames-per-second-in-realtime-with-the-fps-meter"></a><span data-ttu-id="c2001-423">FPS メーターを使用してリアルタイムでフレーム/秒を表示する</span><span class="sxs-lookup"><span data-stu-id="c2001-423">View frames per second in realtime with the FPS meter</span></span>  

<span data-ttu-id="c2001-424">**FPS メーターは**、ビューポートの右上隅に表示されるオーバーレイです。</span><span class="sxs-lookup"><span data-stu-id="c2001-424">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="c2001-425">ページの実行に合った FPS のリアルタイム推定値を提供します。</span><span class="sxs-lookup"><span data-stu-id="c2001-425">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="c2001-426">FPS メーターを **開く方法**:</span><span class="sxs-lookup"><span data-stu-id="c2001-426">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="c2001-427">レンダリング ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-427">Open the **Rendering** tool.</span></span>  <span data-ttu-id="c2001-428">[レンダリング ツールを使用してレンダリングパフォーマンスを分析します](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="c2001-428">[Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="c2001-429">[FPS メーター] **チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="c2001-429">Turn on the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="c2001-431">**FPS メーター**</span><span class="sxs-lookup"><span data-stu-id="c2001-431">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <a name="view-painting-events-in-realtime-with-paint-flashing"></a><span data-ttu-id="c2001-432">フラッシュを使用してリアルタイムでペイント イベントをペイントする</span><span class="sxs-lookup"><span data-stu-id="c2001-432">View painting events in realtime with Paint Flashing</span></span>  

<span data-ttu-id="c2001-433">ページペイントすべてのペイント イベントのリアルタイム ビューを取得するには、[フラッシュ] を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2001-433">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="c2001-434">ページの一部が再描画されるたびに、DevTools は、そのセクションのアウトラインを緑色で示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-434">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="c2001-435">フラッシュを有効ペイント、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-435">To turn on Paint Flashing, complete the following actions.</span></span>  

1.  <span data-ttu-id="c2001-436">レンダリング ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-436">Open the **Rendering** tool.</span></span>  <span data-ttu-id="c2001-437">[レンダリング ツール [を使用してレンダリングパフォーマンスを分析する] に移動します](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="c2001-437">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="c2001-438">[フラッシュ] チェック**ボックスペイントオン**にします。</span><span class="sxs-lookup"><span data-stu-id="c2001-438">Turn on the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="ペイント点滅" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="c2001-440">ペイント点滅</span><span class="sxs-lookup"><span data-stu-id="c2001-440">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <a name="view-an-overlay-of-layers-with-layer-borders"></a><span data-ttu-id="c2001-441">[レイヤーの罫線] を使用してレイヤーのオーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="c2001-441">View an overlay of layers with Layer Borders</span></span>  

<span data-ttu-id="c2001-442">レイヤー **罫線を使用** して、ページの上部にレイヤーの罫線とタイルのオーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-442">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="c2001-443">[レイヤー罫線] を有効にする場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-443">To turn on Layer Borders, complete the following actions,</span></span>  

1.  <span data-ttu-id="c2001-444">レンダリング ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-444">Open the **Rendering** tool.</span></span>  <span data-ttu-id="c2001-445">[レンダリング ツール [を使用してレンダリングパフォーマンスを分析する] に移動します](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="c2001-445">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="c2001-446">[レイヤーの罫 **線] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="c2001-446">Turn on the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="レイヤーの罫線" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="c2001-448">レイヤーの罫線</span><span class="sxs-lookup"><span data-stu-id="c2001-448">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="c2001-449">[debug_colors.cc のコメント][ChromiumDebugColors]に移動して、色分けについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c2001-449">Navigate to the comments in [debug_colors.cc][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <a name="find-scroll-performance-issues-in-realtime"></a><span data-ttu-id="c2001-450">リアルタイムでスクロールパフォーマンスの問題を見つける</span><span class="sxs-lookup"><span data-stu-id="c2001-450">Find scroll performance issues in realtime</span></span>  

<span data-ttu-id="c2001-451">スクロールパフォーマンスの問題を使用して、ページのパフォーマンスを低下させる可能性のあるスクロールに関連するイベント リスナーを持つページの要素を識別します。</span><span class="sxs-lookup"><span data-stu-id="c2001-451">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="c2001-452">DevTools は、teal の潜在的に問題のある要素の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c2001-452">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="c2001-453">スクロール パフォーマンスの問題を表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2001-453">To view scroll performance issues, complete the following actions.</span></span> 

1.  <span data-ttu-id="c2001-454">レンダリング ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="c2001-454">Open the **Rendering** tool.</span></span>  <span data-ttu-id="c2001-455">[レンダリング ツール [を使用してレンダリングパフォーマンスを分析する] に移動します](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="c2001-455">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="c2001-456">[パフォーマンスの **問題のスクロール] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="c2001-456">Turn on the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="スクロールパフォーマンスの問題は、レイヤー以外のビューポートに制約のあるオブジェクトがスクロールのパフォーマンスに影響を与える可能性を示します" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="c2001-458">**スクロールパフォーマンスの問題は、** レイヤー以外のビューポートに制約のあるオブジェクトがスクロールのパフォーマンスに影響を与える可能性を示します</span><span class="sxs-lookup"><span data-stu-id="c2001-458">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c2001-459">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c2001-459">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "コマンド メニューを開く - DevTools コマンド Microsoft Edgeコマンド メニューを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "ランタイム パフォーマンス の分析の開始|Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "アクティビティ タブのデモ |グリッチ"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - コード検索"  

> [!NOTE]
> <span data-ttu-id="c2001-465">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2001-465">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c2001-466">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="c2001-466">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c2001-468">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c2001-468">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
