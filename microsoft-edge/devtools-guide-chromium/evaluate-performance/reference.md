---
description: Microsoft Edge DevTools でパフォーマンスを記録および分析するためのすべての方法に関するリファレンスです。
title: パフォーマンス分析リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d5b6be92c1419ba880a94c62c3f586a740816622
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230762"
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

# <span data-ttu-id="5220b-104">パフォーマンス分析リファレンス</span><span class="sxs-lookup"><span data-stu-id="5220b-104">Performance analysis reference</span></span>  

<span data-ttu-id="5220b-105">このページは、パフォーマンスの分析に関連する Microsoft Edge DevTools 機能の包括的なリファレンスです。</span><span class="sxs-lookup"><span data-stu-id="5220b-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="5220b-106">[Microsoft Edge DevTools][MicrosoftEdgeDevTools][を使用して][DevtoolsEvaluatePerformanceGettingStarted]ページのパフォーマンスを分析する方法に関するガイド付きチュートリアルについては、「ランタイム パフォーマンスの分析の開始」に移動します。</span><span class="sxs-lookup"><span data-stu-id="5220b-106">Navigate to [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="5220b-107">パフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="5220b-107">Record performance</span></span>  

### <span data-ttu-id="5220b-108">実行時のパフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="5220b-108">Record runtime performance</span></span>  

<span data-ttu-id="5220b-109">読み込みではなく、実行中のページのパフォーマンスを分析する場合は、実行時のパフォーマンスを記録します。</span><span class="sxs-lookup"><span data-stu-id="5220b-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="5220b-110">分析するページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5220b-110">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="5220b-111">DevTools **の** [パフォーマンス] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="5220b-111">Choose the **Performance** tab in DevTools.</span></span>  
1.  <span data-ttu-id="5220b-112">Choose **Record** \( ![ Record icon ][ImageRecordIcon] \).</span><span class="sxs-lookup"><span data-stu-id="5220b-112">Choose **Record** \(![Record icon][ImageRecordIcon]\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="5220b-114">Record</span><span class="sxs-lookup"><span data-stu-id="5220b-114">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="5220b-115">ページを操作します。</span><span class="sxs-lookup"><span data-stu-id="5220b-115">Interact with the page.</span></span>  <span data-ttu-id="5220b-116">DevTools は、操作の結果として発生するページ アクティビティを記録します。</span><span class="sxs-lookup"><span data-stu-id="5220b-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="5220b-117">もう一 **度 [Record]** を選ぶか **、[Stop]** を選んでレコーディングを停止します。</span><span class="sxs-lookup"><span data-stu-id="5220b-117">Choose **Record** again or choose **Stop** to stop recording.</span></span>  
    
### <span data-ttu-id="5220b-118">読み込みパフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="5220b-118">Record load performance</span></span>  

<span data-ttu-id="5220b-119">実行中ではなく、読み込み中のページのパフォーマンスを分析する場合は、読み込みパフォーマンスを記録します。</span><span class="sxs-lookup"><span data-stu-id="5220b-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="5220b-120">分析するページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5220b-120">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="5220b-121">DevTools **の** パフォーマンス パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5220b-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="5220b-122">Choose **Refresh page** \( Refresh Page ![ ][ImageRefreshPageIcon] \).</span><span class="sxs-lookup"><span data-stu-id="5220b-122">Choose **Refresh page** \(![Refresh Page][ImageRefreshPageIcon]\).</span></span>  <span data-ttu-id="5220b-123">DevTools は、ページの更新中にパフォーマンス メトリックを記録し、読み込み完了から数秒後に自動的に記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="5220b-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="ページを更新する" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="5220b-125">ページを更新する</span><span class="sxs-lookup"><span data-stu-id="5220b-125">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="5220b-126">DevTools は、ほとんどのアクティビティが発生した記録の部分を自動的に拡大します。</span><span class="sxs-lookup"><span data-stu-id="5220b-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="ページ読み込み記録" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="5220b-128">ページ読み込み記録</span><span class="sxs-lookup"><span data-stu-id="5220b-128">A page-load recording</span></span>  
:::image-end:::  

### <span data-ttu-id="5220b-129">記録中のスクリーンショットのキャプチャ</span><span class="sxs-lookup"><span data-stu-id="5220b-129">Capture screenshots while recording</span></span>  

<span data-ttu-id="5220b-130">**[Screenshots] チェック ボックスをオン**にして、記録中のすべてのフレームのスクリーンショットをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="5220b-130">Turn on the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="[スクリーンショット] チェック ボックス" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="5220b-132">[ **スクリーンショット]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="5220b-132">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-133">[スクリーンショット [の表示] に移動して](#view-a-screenshot) 、スクリーンショットを操作する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="5220b-133">Navigate to [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <span data-ttu-id="5220b-134">記録中にガベージ コレクションを強制する</span><span class="sxs-lookup"><span data-stu-id="5220b-134">Force garbage collection while recording</span></span>  

<span data-ttu-id="5220b-135">ページを記録している間に、[ガベージ\*\*\*\* の収集\ ( ガベージ アイコン \) を収集する] を選択して、ガベージ ![ ][ImageCollectGarbageIcon] コレクションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="5220b-135">While you are recording a page, choose **Collect garbage** \(![Collect garbage icon][ImageCollectGarbageIcon]\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="ガベージを収集する" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="5220b-137">ガベージを収集する</span><span class="sxs-lookup"><span data-stu-id="5220b-137">Collect garbage</span></span>  
:::image-end:::  

### <span data-ttu-id="5220b-138">レコーディング設定を表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-138">Show recording settings</span></span>  

<span data-ttu-id="5220b-139">DevTools **がパフォーマンス** 記録をキャプチャする方法に関連するその他の設定を公開するには、[Capture settings \( ![ Capture settings ][ImageCaptureSettingsIcon] \) ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5220b-139">Choose **Capture settings** \(![Capture settings][ImageCaptureSettingsIcon]\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text="[キャプチャの設定] セクション" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="5220b-141">[ **キャプチャの設定]** セクション</span><span class="sxs-lookup"><span data-stu-id="5220b-141">The **Capture Settings** section</span></span>  
:::image-end:::  

### <span data-ttu-id="5220b-142">JavaScript サンプルを無効にする</span><span class="sxs-lookup"><span data-stu-id="5220b-142">Disable JavaScript samples</span></span>  

<span data-ttu-id="5220b-143">既定では、レコーディングの **Main** セクションには、レコーディング中に呼び出された JavaScript 関数の詳細な呼び出し履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="5220b-144">これらのコール スタックを無効にするには:</span><span class="sxs-lookup"><span data-stu-id="5220b-144">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="5220b-145">[キャプチャの **設定] メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="5220b-145">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="5220b-146">[Show [recording settings] (レコーディング設定の表示) に移動します](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="5220b-146">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="5220b-147">[JavaScript サンプル **を無効にする] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="5220b-147">Turn on the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="5220b-148">ページの記録を取ります。</span><span class="sxs-lookup"><span data-stu-id="5220b-148">Take a recording of the page.</span></span>  
    
<span data-ttu-id="5220b-149">次の 2 つの図は、JavaScript サンプルの無効化と有効化の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="5220b-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="5220b-150">サンプリング **を** 無効にすると、すべての JavaScript 呼び出しスタックが省略されるので、レコーディングの Main セクションははるかに短くなります。</span><span class="sxs-lookup"><span data-stu-id="5220b-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="JS サンプルが無効になっている場合の記録の例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="5220b-152">JS サンプルが無効になっている場合の記録の例</span><span class="sxs-lookup"><span data-stu-id="5220b-152">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="JS サンプルをオンにした場合の記録の例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="5220b-154">JS サンプルをオンにした場合の記録の例</span><span class="sxs-lookup"><span data-stu-id="5220b-154">An example of a recording when JS samples are turned on</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="5220b-155">記録中にネットワークを調整する</span><span class="sxs-lookup"><span data-stu-id="5220b-155">Throttle the network while recording</span></span>  

<span data-ttu-id="5220b-156">記録中にネットワークを調整するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5220b-156">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="5220b-157">[キャプチャの **設定] メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="5220b-157">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="5220b-158">[Show [recording settings] (レコーディング設定の表示) に移動します](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="5220b-158">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="5220b-159">ネットワーク **を** 目的の調整レベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="5220b-159">Set **Network** to the desired level of throttling.</span></span>  
    
### <span data-ttu-id="5220b-160">記録中に CPU を調整する</span><span class="sxs-lookup"><span data-stu-id="5220b-160">Throttle the CPU while recording</span></span>  

<span data-ttu-id="5220b-161">記録中に CPU を調整するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5220b-161">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="5220b-162">[キャプチャの **設定] メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="5220b-162">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="5220b-163">[Show [recording settings] (レコーディング設定の表示) に移動します](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="5220b-163">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="5220b-164">**CPU を**目的の調整レベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="5220b-164">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="5220b-165">調整は、コンピューターの機能に関連します。</span><span class="sxs-lookup"><span data-stu-id="5220b-165">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="5220b-166">たとえば **、2x の** スローダウン オプションでは、CPU の動作が通常よりも 2 倍遅くなります。</span><span class="sxs-lookup"><span data-stu-id="5220b-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="5220b-167">モバイル デバイスのアーキテクチャはデスクトップやノート PC のアーキテクチャと非常に異なっているので、DevTools はモバイル デバイスの CPU を実際にシミュレートするのではありません。</span><span class="sxs-lookup"><span data-stu-id="5220b-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <span data-ttu-id="5220b-168">高度なペイントインストルメンテーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="5220b-168">Turn on advanced paint instrumentation</span></span>  

<span data-ttu-id="5220b-169">ペイントインストルメンテーションの詳細を表示するには:</span><span class="sxs-lookup"><span data-stu-id="5220b-169">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="5220b-170">[キャプチャの **設定] メニューを開** きます。</span><span class="sxs-lookup"><span data-stu-id="5220b-170">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="5220b-171">[Show [recording settings] (レコーディング設定の表示) に移動します](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="5220b-171">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="5220b-172">[高度な **ペイントインストルメンテーションを有効にする (低速) チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="5220b-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="5220b-173">ペイント情報を操作する方法については、「レイヤーの表示」[](#view-layers-information)と「ペイント プロファイラーの[表示」に移動します](#view-paint-profiler)。</span><span class="sxs-lookup"><span data-stu-id="5220b-173">To learn how to interact with the paint information, navigate to [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <span data-ttu-id="5220b-174">レコーディングを保存する</span><span class="sxs-lookup"><span data-stu-id="5220b-174">Save a recording</span></span>  

<span data-ttu-id="5220b-175">記録を保存するには、コンテキスト メニュー \(右クリック\) を開き、[プロファイルの保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5220b-175">To save a recording, open the contextual menu \(right-click\), and choose **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="プロファイルの保存" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="5220b-177">プロファイルの保存</span><span class="sxs-lookup"><span data-stu-id="5220b-177">Save Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="5220b-178">レコーディングを読み込む</span><span class="sxs-lookup"><span data-stu-id="5220b-178">Load a recording</span></span>  

<span data-ttu-id="5220b-179">レコーディングを読み込むには、コンテキスト メニュー \(右クリック\) を開き、[プロファイルの読み込み **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5220b-179">To load a recording, open the contextual menu \(right-click\), and choose **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="プロファイルの読み込み" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="5220b-181">プロファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="5220b-181">Load Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="5220b-182">前のレコーディングをクリアする</span><span class="sxs-lookup"><span data-stu-id="5220b-182">Clear the previous recording</span></span>  

<span data-ttu-id="5220b-183">レコーディングを行った後、Clear **recording** \( Clear recording icon \) を押して、パフォーマンス パネルからそのレコーディング ![ ][ImageClearRecordingIcon] を **クリア** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-183">After making a recording, press **Clear recording** \(![Clear recording icon][ImageClearRecordingIcon]\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="レコーディングのクリア" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="5220b-185">レコーディングのクリア</span><span class="sxs-lookup"><span data-stu-id="5220b-185">Clear recording</span></span>**  
:::image-end:::  

## <span data-ttu-id="5220b-186">パフォーマンス記録を分析する</span><span class="sxs-lookup"><span data-stu-id="5220b-186">Analyze a performance recording</span></span>  

<span data-ttu-id="5220b-187">実行時の[パフォーマンスまたは](#record-runtime-performance)レコード読[](#record-load-performance)み込みパフォーマンスを\*\*\*\* 記録した後、パフォーマンス パネルには、発生したパフォーマンスを分析するための多くのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <span data-ttu-id="5220b-188">レコーディングの一部を選択する</span><span class="sxs-lookup"><span data-stu-id="5220b-188">Select a portion of a recording</span></span>  

<span data-ttu-id="5220b-189">マウスを [概要] の左または右に **ドラッグ** して、レコーディングの一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="5220b-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="5220b-190">概要**は\*\*\*\*、FPS、CPU、および NET\*\*\*\*\*\* グラフを含む**セクション\*\*です。</span><span class="sxs-lookup"><span data-stu-id="5220b-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="マウスを [概要] の上にドラッグしてズームする" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="5220b-192">マウスを [概要] の上 **にドラッグして** ズームする</span><span class="sxs-lookup"><span data-stu-id="5220b-192">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-193">キーボードを使って部分を選択するには:</span><span class="sxs-lookup"><span data-stu-id="5220b-193">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="5220b-194">Main セクションの背景 **、またはその**横にあるセクション (**操作**、ネットワーク **、GPU**など)**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="5220b-194">Choose the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="5220b-195">このキーボード ワークフローは、これらのセクションの 1 つがフォーカスされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="5220b-195">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="5220b-196">拡大、左へ移動、縮小、右に移動するには、キー 、 `W` `A` `S` `D` を使用します。</span><span class="sxs-lookup"><span data-stu-id="5220b-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="5220b-197">トラックパッドを使って部分を選択するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5220b-197">To select a portion using a trackpad, complete the following actions.</span></span>  

1.  <span data-ttu-id="5220b-198">[概要] セクションまたは [ **詳細] セクション** の上にマウス ポインター **を移動** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-198">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="5220b-199">[**概要**] セクションは **、FPS、CPU、および**NET グラフを含む**領域**です。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5220b-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="5220b-200">[ **詳細]** セクションは **、Main** セクションや [Interactions] **セクションを含** む領域です。</span><span class="sxs-lookup"><span data-stu-id="5220b-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="5220b-201">2 本の指でスワイプして縮小表示し、左にスワイプして左に移動し、下にスワイプして拡大し、右にスワイプして右に移動します。</span><span class="sxs-lookup"><span data-stu-id="5220b-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="5220b-202">Main セクションまたは任意の隣接する\*\*\*\* グラフで長い横棒グラフをスクロールするには、上下にドラッグしながら長押しします。</span><span class="sxs-lookup"><span data-stu-id="5220b-202">To scroll a long flame chart in the **Main** section or any of the neighbors, choose and hold while dragging up and down.</span></span>  <span data-ttu-id="5220b-203">左右にドラッグして、レコーディングの選択部分を移動します。</span><span class="sxs-lookup"><span data-stu-id="5220b-203">Drag left and right to move what portion of the recording is chosen.</span></span>  

### <span data-ttu-id="5220b-204">検索アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5220b-204">Search activities</span></span>  

<span data-ttu-id="5220b-205">`Control` + `F` \(Windows,Linux\) または `Command` + `F` \(macOS\)\*\*\*\* を選択して、パフォーマンス パネルの下部にある検索ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="5220b-205">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="検索ボックス" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="5220b-207">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="5220b-207">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-208">クエリに一致するアクティビティを移動するには:</span><span class="sxs-lookup"><span data-stu-id="5220b-208">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="5220b-209">以前の\*\*\*\* \( ![ Previous \) ボタン ][ImagePreviousIcon] と Next \( **Next** \) ボタン ![ ][ImageNextIcon] を使用します。</span><span class="sxs-lookup"><span data-stu-id="5220b-209">Use the **Previous** \(![Previous][ImagePreviousIcon]\) and **Next** \(![Next][ImageNextIcon]\) buttons.</span></span>  
*   <span data-ttu-id="5220b-210">前 `Shift` + `Enter` の項目を選択するか、 `Enter` 次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="5220b-210">Select `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="5220b-211">クエリ設定を変更するには:</span><span class="sxs-lookup"><span data-stu-id="5220b-211">To modify query settings:</span></span>  

*   <span data-ttu-id="5220b-212">大文字 **と小文字を区別** する \( 大文字と小文字を区別する \) を押して、クエリ ![ ][ImageSearchCaseIcon] で大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="5220b-212">Press **Case sensitive** \(![Case sensitive][ImageSearchCaseIcon]\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="5220b-213">**Regex** \( Regex \) キーを押して、クエリで ![ ][ImageSearchRegexIcon] 正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="5220b-213">Press **Regex** \(![Regex][ImageSearchRegexIcon]\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="5220b-214">検索ボックスを非表示にする場合は **、Cancel**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5220b-214">To hide the search box, press **Cancel**.</span></span>  

### <span data-ttu-id="5220b-215">メイン スレッド アクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-215">View main thread activity</span></span>  

<span data-ttu-id="5220b-216">Main セクション **を使用** して、ページのメイン スレッドで発生したアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="Main セクション" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="5220b-218">Main \*\*\*\* セクション</span><span class="sxs-lookup"><span data-stu-id="5220b-218">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-219">イベントを選択すると、そのイベントに関する詳細が [概要] タブ **に表示** されます。 DevTools は、選択したイベントの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-219">Choose an event to view more information about it in the **Summary** tab.  DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="[概要] タブの匿名関数の詳細" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="5220b-221">[概要] `anonymous` タブの関数**の詳細**</span><span class="sxs-lookup"><span data-stu-id="5220b-221">More information about the `anonymous` function in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-222">DevTools は、メイン スレッド アクティビティを表し、グラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-222">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="5220b-223">x 軸は、時間の過ごした記録を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-223">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="5220b-224">y 軸は呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-224">The y-axis represents the call stack.</span></span>  <span data-ttu-id="5220b-225">一番上のイベントは、その下のイベントを引き起こします。</span><span class="sxs-lookup"><span data-stu-id="5220b-225">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="グラフ (グラフ)" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="5220b-227">グラフ (グラフ)</span><span class="sxs-lookup"><span data-stu-id="5220b-227">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-228">前の図では、53 行目にイベント `click` `Function Call` `activitytabs.js` が発生しました。</span><span class="sxs-lookup"><span data-stu-id="5220b-228">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="5220b-229">次 `Function Call` に、匿名関数が実行されたと確認します。</span><span class="sxs-lookup"><span data-stu-id="5220b-229">Below `Function Call`, review that an anonymous function was run.</span></span>  <span data-ttu-id="5220b-230">要求された匿名関数 `a` 。要求 `wait` されました `Minor GC` 。</span><span class="sxs-lookup"><span data-stu-id="5220b-230">The anonymous function requested `a`, which requested `wait`, which requested `Minor GC`.</span></span>  

<span data-ttu-id="5220b-231">DevTools は、スクリプトのランダムな色を割り当てします。</span><span class="sxs-lookup"><span data-stu-id="5220b-231">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="5220b-232">前の図では、1 つのスクリプトからの関数要求は薄い緑色で表示されています。</span><span class="sxs-lookup"><span data-stu-id="5220b-232">In the previous figure, function requests from one script are colored light green.</span></span>  <span data-ttu-id="5220b-233">別のスクリプトからの要求は色分けされています。</span><span class="sxs-lookup"><span data-stu-id="5220b-233">Requests from another script are colored beige.</span></span>  <span data-ttu-id="5220b-234">濃い黄色はスクリプト アクティビティを表し、紫色のイベントはレンダリング アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-234">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="5220b-235">これらの濃い黄色と紫色のイベントは、すべてのレコーディングで一貫しています。</span><span class="sxs-lookup"><span data-stu-id="5220b-235">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="5220b-236">JavaScript 要求 [の詳細な](#disable-javascript-samples) グラフを非表示にする場合は、[JavaScript サンプルを無効にする] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5220b-236">Navigate to [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript requests.</span></span>  <span data-ttu-id="5220b-237">JS サンプルが無効になっている場合は、前の図のような、および前の図からの高レベル `Event: click` `Function Call` のイベントだけが表示 `str` されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-237">When JS samples are disabled, only high-level events such as `Event: click` and `Function Call` from the previous figure `str` displayed.</span></span>  

### <span data-ttu-id="5220b-238">テーブル内のアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-238">View activities in a table</span></span>  

<span data-ttu-id="5220b-239">ページを記録した後は、Main セクションのみを使用してアクティビティ **を分析** する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5220b-239">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="5220b-240">DevTools には、アクティビティを分析するための 3 つの表形式ビューもあります。</span><span class="sxs-lookup"><span data-stu-id="5220b-240">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="5220b-241">各ビューには、アクティビティに対する異なる視点があります。</span><span class="sxs-lookup"><span data-stu-id="5220b-241">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="5220b-242">最も多くの作業を引き起こすルート アクティビティを表示する場合は、[呼び出 [しツリー] タブを使用します](#the-call-tree-tab)。</span><span class="sxs-lookup"><span data-stu-id="5220b-242">When you want to view the root activities that cause the most work, use [the Call Tree tab](#the-call-tree-tab).</span></span>  
*   <span data-ttu-id="5220b-243">最も時間が直接費やされたアクティビティを表示するには、次のBottom-Up [します](#the-bottom-up-tab)。</span><span class="sxs-lookup"><span data-stu-id="5220b-243">When you want to view the activities where the most time was directly spent, use [the Bottom-Up tab](#the-bottom-up-tab).</span></span>  
*   <span data-ttu-id="5220b-244">記録中に発生した順序でアクティビティを表示する場合は、[イベント ログ] タブ [を使用します](#the-event-log-tab)。</span><span class="sxs-lookup"><span data-stu-id="5220b-244">When you want to view the activities in the order in which they occurred during the recording, use [the Event Log tab](#the-event-log-tab).</span></span>  
    
> [!NOTE]
> <span data-ttu-id="5220b-245">次の 3 つのセクションはすべて同じデモを参照します。</span><span class="sxs-lookup"><span data-stu-id="5220b-245">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="5220b-246">アクティビティ タブのデモで [デモを自分で実行します][ActivityTabsDemo]。</span><span class="sxs-lookup"><span data-stu-id="5220b-246">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <span data-ttu-id="5220b-247">ルート アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5220b-247">Root activities</span></span>  

<span data-ttu-id="5220b-248">ここでは、[コール ツリー]\*\*\*\* タブ\*\*\*\*\*\*、[Bottom-Up]\*\* タブ、および [Event **Log]** セクションに記載されているルート アクティビティの概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="5220b-248">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** tab, **Bottom-Up** tab, and **Event Log** sections.</span></span>  

<span data-ttu-id="5220b-249">ルート アクティビティは、ブラウザーが何らかの作業を行う原因となるアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="5220b-249">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="5220b-250">たとえば、Web ページを選択すると、ブラウザーはルート `Event` アクティビティとしてアクティビティを実行します。</span><span class="sxs-lookup"><span data-stu-id="5220b-250">For example, when you choose a webpage, the browser runs an `Event` activity as the root activity.</span></span>  <span data-ttu-id="5220b-251">そのため `Event` 、ハンドラーが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5220b-251">That `Event` may cause a handler to run, and so on.</span></span>  

<span data-ttu-id="5220b-252">Main セクションの **グラフでは、** ルート アクティビティがグラフの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-252">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="5220b-253">[ **呼び出しツリー]** **タブと [イベント ログ] タブ** では、ルート アクティビティがトップ レベルの項目です。</span><span class="sxs-lookup"><span data-stu-id="5220b-253">In the **Call Tree** and **Event Log** tabs, root activities are the top-level items.</span></span>  

<span data-ttu-id="5220b-254">ルート アクティビティ [の例の [呼び出](#the-call-tree-tab) しツリー] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="5220b-254">Navigate to [The Call Tree tab](#the-call-tree-tab) for an example of root activities.</span></span>  

#### <span data-ttu-id="5220b-255">[呼び出しツリー] タブ</span><span class="sxs-lookup"><span data-stu-id="5220b-255">The Call Tree tab</span></span>  

<span data-ttu-id="5220b-256">[呼 **び出しツリー] タブ** を使用して、最も [多くの作業を引き起](#root-activities) こすルート アクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-256">Use the **Call Tree** tab to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="5220b-257">[ **呼び出しツリー]** タブには、レコーディングの選択した部分のアクティビティだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-257">The **Call Tree** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="5220b-258">[記録の [一部を選択] に移動して](#select-a-portion-of-a-recording) 、部分を選択する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="5220b-258">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="[呼び出しツリー] タブ" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="5220b-260">[ **呼び出しツリー]** タブ</span><span class="sxs-lookup"><span data-stu-id="5220b-260">The **Call Tree** tab</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-261">前の図では、[アクティビティ] 列のアイテムのトップ\*\*\*\* レベル (ルート アクティビティなど `Evaluate Script` ) `Parse HTML` です。</span><span class="sxs-lookup"><span data-stu-id="5220b-261">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="5220b-262">入れ子は呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-262">The nesting represents the call stack.</span></span>  <span data-ttu-id="5220b-263">たとえば、前の図では、 `Parse HTML` 原因と原因が `Evaluate Script` 次 `Compile Script` のようになります `(anonymous)` 。</span><span class="sxs-lookup"><span data-stu-id="5220b-263">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="5220b-264">**Self Time は** 、そのアクティビティに直接費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-264">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="5220b-265">**Total Time** は、そのアクティビティまたは任意の子に費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-265">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="5220b-266">[Self **Time]、[Total** **Time]、または** **[Activity]** を選択して、テーブルをその列で並べ替える。</span><span class="sxs-lookup"><span data-stu-id="5220b-266">Choose **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="5220b-267">[フィルター **] テキスト ボックス** を使用して、アクティビティ名でイベントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5220b-267">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="5220b-268">既定では、[ **グループ化] メニュー** は [グループ化なし **] に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="5220b-268">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="5220b-269">[グループ **化] メニューを使用** して、さまざまな条件に基づいてアクティビティ テーブルを並べ替える。</span><span class="sxs-lookup"><span data-stu-id="5220b-269">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="5220b-270">[Show **Heaviest Stack** \( Show Heaviest Stack \) ] を選択して、Activity テーブルの右側に別のテーブル ![ ][ImageShowHeaviestStackIcon] を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-270">Choose **Show Heaviest Stack** \(![Show Heaviest Stack][ImageShowHeaviestStackIcon]\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="5220b-271">最も重いスタック テーブルを設定 **するアクティビティを選択** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-271">Choose an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="5220b-272">最 **も重いスタック** テーブルには、選択したアクティビティの子の実行に最も時間がかかった時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-272">The **Heaviest Stack** table displays which children of the selected activity took the longest time to run.</span></span>  

#### <span data-ttu-id="5220b-273">[Bottom-Up] タブ</span><span class="sxs-lookup"><span data-stu-id="5220b-273">The Bottom-Up tab</span></span>  

<span data-ttu-id="5220b-274">[ **下へ上へ] タブを** 使用して、集計で最も時間を直接取ったアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-274">Use the **Bottom-Up** tab to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="5220b-275">[ **下へ上へ]** タブには、レコーディングの選択した部分の間のアクティビティだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-275">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="5220b-276">[記録の [一部を選択] に移動して](#select-a-portion-of-a-recording) 、部分を選択する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="5220b-276">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="[Bottom-Up] タブ" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="5220b-278">[ **下へ]** タブ</span><span class="sxs-lookup"><span data-stu-id="5220b-278">The **Bottom-Up** tab</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-279">前の **図の Main** セクションのグラフグラフで、ほぼすべての時間が実行に費やされたグラフに移動します `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="5220b-279">In the **Main** section flame chart of the previous figure, navigate to that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="5220b-280">前の図の [ **下から上** へ] タブの一番上のアクティビティは次の値です `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="5220b-280">The top activity in the **Bottom-Up** tab of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="5220b-281">最もコスト **の高い次** のアクティビティである [下向き] タブに移動します `Layout` 。</span><span class="sxs-lookup"><span data-stu-id="5220b-281">Navigate to the **Bottom-Up** tab, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="5220b-282">[Self **Time]** 列は、すべての発生回数にわたって、そのアクティビティに直接費やされた合計時間を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-282">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="5220b-283">[ **合計時間]** 列は、そのアクティビティまたは任意の子に費やされた合計時間を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-283">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <span data-ttu-id="5220b-284">[イベント ログ] タブ</span><span class="sxs-lookup"><span data-stu-id="5220b-284">The Event Log tab</span></span>  

<span data-ttu-id="5220b-285">[イベント **ログ] タブを** 使用して、記録中に発生した順序でアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-285">Use the **Event Log** tab to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="5220b-286">[ **イベント ログ] タブ** には、記録中に選択した部分のアクティビティだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-286">The **Event Log** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="5220b-287">[記録の [一部を選択] に移動して](#select-a-portion-of-a-recording) 、部分を選択する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="5220b-287">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="[イベント ログ] タブ" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="5220b-289">[ **イベント ログ]** タブ</span><span class="sxs-lookup"><span data-stu-id="5220b-289">The **Event Log** tab</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-290">[ **開始時刻]** 列は、記録の開始位置を基準に、そのアクティビティが開始されたポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-290">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="5220b-291">たとえば、前の図で選択したアイテムの開始時刻は、記録が開始した `175.7 ms` 後、アクティビティが 175.7 ミリ秒後に開始されたという意味です。</span><span class="sxs-lookup"><span data-stu-id="5220b-291">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="5220b-292">[Self **Time] 列** は、そのアクティビティに直接費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-292">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="5220b-293">[ **合計時間]** 列は、そのアクティビティまたは任意の子に直接費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-293">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="5220b-294">[ **開始時刻]、[Self** **Time]、または** **[Total Time]** を選択して、テーブルをその列で並べ替える。</span><span class="sxs-lookup"><span data-stu-id="5220b-294">Choose **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="5220b-295">[フィルター **] テキスト ボックス** を使用して、アクティビティを名前でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5220b-295">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="5220b-296">[期間 **] メニューを** 使用して、1 ミリ秒未満または 15 ミリ秒未満のアクティビティをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5220b-296">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="5220b-297">既定では、[ **期間] メニュー** は [すべて] に **設定され、** すべてのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-297">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="5220b-298">[読み**込み\*\*\*\*]、[スクリプト]、[\*\*\*\*レンダリング]、** または [**描画**] チェック ボックスを無効にして、これらのカテゴリからすべてのアクティビティをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5220b-298">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <span data-ttu-id="5220b-299">GPU アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="5220b-299">View GPU activity</span></span>  

<span data-ttu-id="5220b-300">GPU セクションで GPU アクティビティ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-300">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU セクション" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="5220b-302">**GPU セクション**</span><span class="sxs-lookup"><span data-stu-id="5220b-302">The **GPU** section</span></span>  
:::image-end:::  

### <span data-ttu-id="5220b-303">ラスター アクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-303">View raster activity</span></span>  

<span data-ttu-id="5220b-304">[ラスター] セクションでラスター アクティビティ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-304">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="[ラスター] セクション" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="5220b-306">[ **ラスター]** セクション</span><span class="sxs-lookup"><span data-stu-id="5220b-306">The **Raster** section</span></span>  
:::image-end:::  

### <span data-ttu-id="5220b-307">操作の表示</span><span class="sxs-lookup"><span data-stu-id="5220b-307">View interactions</span></span>  

<span data-ttu-id="5220b-308">[操作 **] セクションを** 使用して、レコーディング中に発生したユーザー操作を見つけて分析します。</span><span class="sxs-lookup"><span data-stu-id="5220b-308">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="[操作] セクション" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="5220b-310">[ **操作]** セクション</span><span class="sxs-lookup"><span data-stu-id="5220b-310">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-311">対話式操作の下部にある赤い線は、メイン スレッドの待機に費やされた時間を表します。</span><span class="sxs-lookup"><span data-stu-id="5220b-311">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="5220b-312">操作を選択すると、[概要] タブに詳細 **な情報が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-312">Choose an interaction to view more information about it in the **Summary** tab.</span></span>  

### <span data-ttu-id="5220b-313">秒あたりのフレーム数を分析する (FPS)</span><span class="sxs-lookup"><span data-stu-id="5220b-313">Analyze frames per second (FPS)</span></span>  

<span data-ttu-id="5220b-314">DevTools には、1 秒あたりのフレームを分析するさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="5220b-314">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="5220b-315">[記録期間中の FPS](#the-fps-chart)の概要を取得するには、FPS グラフを使用します。</span><span class="sxs-lookup"><span data-stu-id="5220b-315">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="5220b-316">[[Frames] セクションを使用](#the-frames-section)して、特定のフレームにかかった時間を表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-316">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="5220b-317">ページの **実行中に FPS** のリアルタイム推定値として FPS メーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5220b-317">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="5220b-318">FPS メーターを使って、リアルタイムで [1 秒あたりのフレーム [数の表示] に移動します](#view-frames-per-second-in-realtime-with-the-fps-meter)。</span><span class="sxs-lookup"><span data-stu-id="5220b-318">Navigate to [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <span data-ttu-id="5220b-319">FPS グラフ</span><span class="sxs-lookup"><span data-stu-id="5220b-319">The FPS chart</span></span>  

<span data-ttu-id="5220b-320">**FPS グラフ**は、レコーディング中のフレーム レートの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-320">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="5220b-321">一般に、緑のバーが大きいほど、フレーム レートが良くなります。</span><span class="sxs-lookup"><span data-stu-id="5220b-321">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="5220b-322">FPS グラフの上の赤 **い** バーは、フレーム レートが低く低下し、ユーザーのエクスペリエンスに損害を与えた可能性があるという警告です。</span><span class="sxs-lookup"><span data-stu-id="5220b-322">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="5220b-324">**FPS グラフ**</span><span class="sxs-lookup"><span data-stu-id="5220b-324">The **FPS** chart</span></span>  
:::image-end:::  

#### <span data-ttu-id="5220b-325">[フレーム] セクション</span><span class="sxs-lookup"><span data-stu-id="5220b-325">The Frames section</span></span>  

<span data-ttu-id="5220b-326">**[Frames]** セクションでは、特定のフレームにかかった時間を正確に示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-326">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="5220b-327">フレームの上にマウス ポインターを移動すると、そのフレームに関する詳細な情報を含むヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-327">Hover over a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="フレームにカーソルを合わせる" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="5220b-329">フレームにカーソルを合わせる</span><span class="sxs-lookup"><span data-stu-id="5220b-329">Hover over a frame</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-330">[概要] タブでフレームに関する詳細を表示するには、フレーム **を選択** します。 DevTools は、選択したフレームの輪郭を青で示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-330">Choose a frame to view more information about the frame in the **Summary** tab.  DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="[概要] タブでフレームを表示する" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="5220b-332">[概要] タブでフレーム **を表示** する</span><span class="sxs-lookup"><span data-stu-id="5220b-332">View a frame in the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="5220b-333">ネットワーク要求の表示</span><span class="sxs-lookup"><span data-stu-id="5220b-333">View network requests</span></span>  

<span data-ttu-id="5220b-334">[ネットワーク **] セクションを** 展開して、レコーディング中に発生したネットワーク要求のウォーターフォールを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-334">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="[ネットワーク] セクション" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="5220b-336">[ **ネットワーク]** セクション</span><span class="sxs-lookup"><span data-stu-id="5220b-336">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-337">要求は、次のように色分けされています。</span><span class="sxs-lookup"><span data-stu-id="5220b-337">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="5220b-338">HTML: Blue</span><span class="sxs-lookup"><span data-stu-id="5220b-338">HTML: Blue</span></span>  
*   <span data-ttu-id="5220b-339">CSS: 紫色</span><span class="sxs-lookup"><span data-stu-id="5220b-339">CSS: Purple</span></span>  
*   <span data-ttu-id="5220b-340">JS: Yellow</span><span class="sxs-lookup"><span data-stu-id="5220b-340">JS: Yellow</span></span>  
*   <span data-ttu-id="5220b-341">画像: 緑</span><span class="sxs-lookup"><span data-stu-id="5220b-341">Images: Green</span></span>  
    
<span data-ttu-id="5220b-342">詳細を表示する要求を [概要] タブ**で選択**します。 たとえば、前の図の [概要\*\*\*\*] タブには、[ネットワーク] セクションで選択されている青色の要求に関する詳細が**表示**されています。</span><span class="sxs-lookup"><span data-stu-id="5220b-342">Choose a request to view more information about it in the **Summary** tab.  For example, in the previous figure, the **Summary** tab is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="5220b-343">要求の左上に濃い青色の正方形が表示されている場合は、優先度の高い要求です。</span><span class="sxs-lookup"><span data-stu-id="5220b-343">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="5220b-344">明るい青の正方形は優先順位が低いという意味です。</span><span class="sxs-lookup"><span data-stu-id="5220b-344">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="5220b-345">たとえば、前の図では、青の選択された要求の方が優先度が高く、下の緑色の要求は優先度が低くなります。</span><span class="sxs-lookup"><span data-stu-id="5220b-345">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="5220b-346">次の図の 1 つ目では、要求は左側の行、中央に暗い部分と明るい部分を含むバー、右側に線で表されます。 `www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="5220b-346">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="5220b-347">次の図の 2nd では、[ネットワーク] パネルの [タイミング]\*\*\*\* タブに同じ要求の対応する表現が**示**されています。</span><span class="sxs-lookup"><span data-stu-id="5220b-347">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** tab of the **Network** panel.</span></span>  <span data-ttu-id="5220b-348">次に、これら 2 つの表現を互いにマップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-348">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="5220b-349">左側の行は、イベントのグループ `Connection Start` までのすべてです。</span><span class="sxs-lookup"><span data-stu-id="5220b-349">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="5220b-350">つまり、前のすべてで、排他的 `Request Sent` です。</span><span class="sxs-lookup"><span data-stu-id="5220b-350">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="5220b-351">バーの明るい部分は、 `Request Sent` `Waiting (TTFB)` .</span><span class="sxs-lookup"><span data-stu-id="5220b-351">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="5220b-352">バーの暗い部分は次の値です `Content Download` 。</span><span class="sxs-lookup"><span data-stu-id="5220b-352">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="5220b-353">正しい行は、基本的にメイン スレッドの待機に費やされた時間です。</span><span class="sxs-lookup"><span data-stu-id="5220b-353">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="5220b-354">これは 、[タイミング] タブには **表示** されません。</span><span class="sxs-lookup"><span data-stu-id="5220b-354">This is not represented in the **Timing** tab.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="要求の行バー www.bing.comします。" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="5220b-356">要求の行バー `www.bing.com` 表現</span><span class="sxs-lookup"><span data-stu-id="5220b-356">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="ネットワーク ツール" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="5220b-358">ネットワーク**ツール**</span><span class="sxs-lookup"><span data-stu-id="5220b-358">The **Network** tool</span></span>  
<span data-ttu-id="5220b-359">: ::image-end:::</span><span class="sxs-lookup"><span data-stu-id="5220b-359">:     ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="5220b-360">メモリ メトリックスを表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-360">View memory metrics</span></span>  

<span data-ttu-id="5220b-361">[メモリ] チェック **ボックスを** オンにして、最後の記録のメモリ メトリックを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-361">Turn on the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="[メモリ] チェック ボックス" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="5220b-363">[ **メモリ]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="5220b-363">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-364">DevTools は、[ **概要]** タブの上に新しい **メモリ グラフを表示** します。 また、NET グラフの下には **、HEAP** という新しいグラフ **があります**。</span><span class="sxs-lookup"><span data-stu-id="5220b-364">DevTools displays a new **Memory** chart, above the **Summary** tab.  There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="5220b-365">**HEAP グラフ**は、Memory グラフの**JS ヒープ**行と同じ情報を**提供**します。</span><span class="sxs-lookup"><span data-stu-id="5220b-365">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="メモリメトリックス" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="5220b-367">メモリメトリックス</span><span class="sxs-lookup"><span data-stu-id="5220b-367">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-368">グラフの色付き線は、グラフの上の色付きチェック ボックスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="5220b-368">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="5220b-369">チェック ボックスを無効にして、グラフからそのカテゴリを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="5220b-369">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="5220b-370">グラフには、現在選択されているレコーディングの領域だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-370">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="5220b-371">たとえば、前の図の [メモリ\*\*\*\*] グラフには、400 ミリ秒のマークから 1750 ミリ秒のマークまでメモリ使用量だけが表示されています。</span><span class="sxs-lookup"><span data-stu-id="5220b-371">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <span data-ttu-id="5220b-372">レコーディングの一部の期間を表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-372">View the duration of a portion of a recording</span></span>  

<span data-ttu-id="5220b-373">Network や\*\*Main\*\*\*\*\*\* などのセクションを分析する場合、特定のイベントにかかった時間を正確に見積もる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5220b-373">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="5220b-374">録音 `Shift` の一部を選択するには、長押し、長押し、左右にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5220b-374">Hold `Shift`, choose and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="5220b-375">選択した部分の下部に、DevTools はその部分にかかった時間を示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-375">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="レコーディングの一部の期間を表示する" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="5220b-377">レコーディングの一部の期間を表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-377">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <span data-ttu-id="5220b-378">スクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-378">View a screenshot</span></span>  

<span data-ttu-id="5220b-379">記録中 [に [キャプチャ] のスクリーンショットに移動して](#capture-screenshots-while-recording) 、スクリーンショットを有効にする方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="5220b-379">Navigate to [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to turn on screenshots.</span></span>  

<span data-ttu-id="5220b-380">[概要] **をポイント** すると、記録中にページがどのように表示されたのかのスクリーンショットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-380">Hover over the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="5220b-381">[ **概要** ] は **、CPU、FPS、および** **NET**のグラフを含む **セクション** です。</span><span class="sxs-lookup"><span data-stu-id="5220b-381">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="スクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="5220b-383">スクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-383">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-384">[フレーム] セクションでフレームを選択して、スクリーンショットを **表示** することもできます。</span><span class="sxs-lookup"><span data-stu-id="5220b-384">You may also view screenshots by choosing a frame in the **Frames** section.</span></span>  <span data-ttu-id="5220b-385">DevTools は、[概要] タブに小さいバージョンのスクリーンショット **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-385">DevTools displays a small version of the screenshot in the **Summary** tab.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="[概要] タブでスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="5220b-387">[概要] タブでスクリーンショット **を表示** する</span><span class="sxs-lookup"><span data-stu-id="5220b-387">View a screenshot in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-388">[概要] タブでサムネイル **を選択** して、スクリーンショットを拡大します。</span><span class="sxs-lookup"><span data-stu-id="5220b-388">Choose the thumbnail in the **Summary** tab to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="[概要] タブからスクリーンショットを拡大する" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="5220b-390">[概要] タブからスクリーンショット **を拡大** する</span><span class="sxs-lookup"><span data-stu-id="5220b-390">Zoom into a screenshot from the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="5220b-391">レイヤー情報の表示</span><span class="sxs-lookup"><span data-stu-id="5220b-391">View layers information</span></span>  

<span data-ttu-id="5220b-392">フレームに関する高度なレイヤー情報を表示するには:</span><span class="sxs-lookup"><span data-stu-id="5220b-392">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="5220b-393">[高度なペイントインストルメンテーションを有効にする](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="5220b-393">[Turn on advanced paint instrumentation](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="5220b-394">[フレーム] セクションでフレーム **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-394">Select a frame in the **Frames** section.</span></span>  <span data-ttu-id="5220b-395">DevTools は、[イベント ログ] タブ\*\*\*\* の横にある新しい [レイヤー] タブにレイヤーに関する**情報を表示**します。</span><span class="sxs-lookup"><span data-stu-id="5220b-395">DevTools displays information about the layers in the new **Layers** tab, next to the **Event Log** tab.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="[レイヤー] ウィンドウ" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="5220b-397">[ **レイヤー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="5220b-397">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="5220b-398">レイヤーの上にカーソルを合わせると、図内で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-398">Hover over a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="レイヤーを強調表示する" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="5220b-400">レイヤーを強調表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-400">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="5220b-401">図を移動するには:</span><span class="sxs-lookup"><span data-stu-id="5220b-401">To move the diagram:</span></span>  

*   <span data-ttu-id="5220b-402">[ **パン モード** \( パン モード \) ] を ![ ][ImagePanModeIcon] 選択して、X 軸と Y 軸に沿って移動します。</span><span class="sxs-lookup"><span data-stu-id="5220b-402">Choose **Pan Mode** \(![Pan Mode][ImagePanModeIcon]\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="5220b-403">Z **軸に沿って** 回転するには、回転モード ![ ][ImageRotateModeIcon] \( 回転モード \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5220b-403">Choose **Rotate Mode** \(![Rotate Mode][ImageRotateModeIcon]\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="5220b-404">図 **を元の位置** にリセットするには、Reset ![ Transform \( Reset Transform ][ImageResetTransformIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5220b-404">Choose **Reset Transform** \(![Reset Transform][ImageResetTransformIcon]\) to reset the diagram to the original position.</span></span>  
    
### <span data-ttu-id="5220b-405">ペイント プロファイラーの表示</span><span class="sxs-lookup"><span data-stu-id="5220b-405">View paint profiler</span></span>  

<span data-ttu-id="5220b-406">ペイント イベントに関する詳細な情報を表示するには:</span><span class="sxs-lookup"><span data-stu-id="5220b-406">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="5220b-407">[オンにする](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="5220b-407">[Turn on](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="5220b-408">Main セクション **でペイント** イベント **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="5220b-408">Select a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="[ペイント プロファイラー] タブ" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="5220b-410">[ **ペイント プロファイラー]** タブ</span><span class="sxs-lookup"><span data-stu-id="5220b-410">The **Paint Profiler** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="5220b-411">[レンダリング] タブを使用してレンダリングパフォーマンスを分析する</span><span class="sxs-lookup"><span data-stu-id="5220b-411">Analyze rendering performance with the Rendering tab</span></span>  

<span data-ttu-id="5220b-412">[レンダリング] タブの **機能を使用** して、ページのレンダリング パフォーマンスを視覚化します。</span><span class="sxs-lookup"><span data-stu-id="5220b-412">Use the features of the **Rendering** tab to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="5220b-413">[レンダリング] タブ **を開** く方法:</span><span class="sxs-lookup"><span data-stu-id="5220b-413">To open the **Rendering** tab:</span></span>  

1.  <span data-ttu-id="5220b-414">[コマンド メニューを開きます][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="5220b-414">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="5220b-415">入力を開始 `Rendering` し、選択します `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="5220b-415">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="5220b-416">DevTools は **、DevTools** ウィンドウの下部に [レンダリング] タブを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-416">DevTools displays the **Rendering** tab at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="[レンダリング] タブ" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="5220b-418">[ **レンダリング]** タブ</span><span class="sxs-lookup"><span data-stu-id="5220b-418">The **Rendering** tab</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="5220b-419">FPS メーターを使用してリアルタイムで 1 秒あたりのフレーム数を表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-419">View frames per second in realtime with the FPS meter</span></span>  

<span data-ttu-id="5220b-420">**FPS メーターは**、ビューポートの右上隅に表示されるオーバーレイです。</span><span class="sxs-lookup"><span data-stu-id="5220b-420">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="5220b-421">ページの実行に合った FPS のリアルタイムの推定値を提供します。</span><span class="sxs-lookup"><span data-stu-id="5220b-421">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="5220b-422">FPS メーターを **開く方法**:</span><span class="sxs-lookup"><span data-stu-id="5220b-422">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="5220b-423">[レンダリング] **タブを開** きます。 Na [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span><span class="sxs-lookup"><span data-stu-id="5220b-423">Open the **Rendering** tab.  Na [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="5220b-424">**[FPS メーター] チェック ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="5220b-424">Turn on the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="5220b-426">**FPS メーター**</span><span class="sxs-lookup"><span data-stu-id="5220b-426">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="5220b-427">ペイント フラッシュを使ってリアルタイムで描画イベントを表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-427">View painting events in realtime with Paint Flashing</span></span>  

<span data-ttu-id="5220b-428">ページ上のすべてのペイント イベントのリアルタイム ビューを取得するには、ペイント フラッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="5220b-428">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="5220b-429">ページの一部が再描画されるたびに、DevTools によってそのセクションのアウトラインが緑色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-429">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="5220b-430">ペイント フラッシュを有効にする場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5220b-430">To turn on Paint Flashing, complete the following actions.</span></span>  

1.  <span data-ttu-id="5220b-431">[レンダリング] **タブを開** きます。 [レンダリング] タブ [で [レンダリングパフォーマンスの分析] に移動します](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="5220b-431">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="5220b-432">[ペイントの点滅 **] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="5220b-432">Turn on the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="ペイントの点滅" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="5220b-434">ペイントの点滅</span><span class="sxs-lookup"><span data-stu-id="5220b-434">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <span data-ttu-id="5220b-435">レイヤー罫線を使用してレイヤーのオーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="5220b-435">View an overlay of layers with Layer Borders</span></span>  

<span data-ttu-id="5220b-436">レイヤー **罫線を使用** して、ページの上にレイヤー罫線とタイルのオーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-436">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="5220b-437">レイヤー罫線を有効にする場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5220b-437">To turn on Layer Borders, complete the following actions,</span></span>  

1.  <span data-ttu-id="5220b-438">[レンダリング] **タブを開** きます。 [レンダリング] タブ [で [レンダリングパフォーマンスの分析] に移動します](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="5220b-438">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="5220b-439">[レイヤー罫 **線] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="5220b-439">Turn on the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="レイヤー罫線" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="5220b-441">レイヤー罫線</span><span class="sxs-lookup"><span data-stu-id="5220b-441">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="5220b-442">[debug_colors.cc][ChromiumDebugColors]のコメントに移動して、色分けについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5220b-442">Navigate to the comments in [debug_colors.cc][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <span data-ttu-id="5220b-443">リアルタイムでスクロール パフォーマンスの問題を見つける</span><span class="sxs-lookup"><span data-stu-id="5220b-443">Find scroll performance issues in realtime</span></span>  

<span data-ttu-id="5220b-444">スクロールパフォーマンスの問題を使用して、ページのパフォーマンスを低下させる可能性のあるスクロールに関連するイベント リスナーを持つページの要素を特定します。</span><span class="sxs-lookup"><span data-stu-id="5220b-444">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="5220b-445">DevTools は、問題が発生する可能性のある要素の概要を小さい形で示します。</span><span class="sxs-lookup"><span data-stu-id="5220b-445">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="5220b-446">スクロール パフォーマンスの問題を表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5220b-446">To view scroll performance issues, complete the following actions.</span></span> 

1.  <span data-ttu-id="5220b-447">[レンダリング] **タブを開** きます。 [レンダリング] タブ [で [レンダリングパフォーマンスの分析] に移動します](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="5220b-447">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="5220b-448">**[Scrolling Performance Issues] チェック ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="5220b-448">Turn on the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="スクロールのパフォーマンスの問題は、レイヤー以外のビューポートに制約のあるオブジェクトがスクロールのパフォーマンスを低下させる可能性を示します" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="5220b-450">**スクロールのパフォーマンスの問題は、** レイヤー以外のビューポートに制約のあるオブジェクトがスクロールのパフォーマンスを低下させる可能性を示します</span><span class="sxs-lookup"><span data-stu-id="5220b-450">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="5220b-451">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="5220b-451">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

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

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "コマンド メニューを開く - Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する |Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "ランタイム パフォーマンスの分析を開始する |Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "アクティビティ タブのデモ |不具合"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - コード検索"  

> [!NOTE]
> <span data-ttu-id="5220b-457">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5220b-457">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5220b-458">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="5220b-458">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5220b-460">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5220b-460">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
