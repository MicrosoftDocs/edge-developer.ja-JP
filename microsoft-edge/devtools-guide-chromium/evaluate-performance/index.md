---
description: Microsoft Edge DevTools で実行時のパフォーマンスを評価する方法について説明します。
title: ランタイム のパフォーマンスの分析の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 439d6d4331550b7fc92bfc5fef4c3fc88df38872
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439613"
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

# <a name="get-started-with-analyzing-runtime-performance"></a><span data-ttu-id="73bfc-104">ランタイム のパフォーマンスの分析の開始</span><span class="sxs-lookup"><span data-stu-id="73bfc-104">Get started with analyzing Runtime performance</span></span>  

> [!NOTE]
> <span data-ttu-id="73bfc-105">ページの読み込み速度を速くする方法については、「オプティマイズ Web サイトの [速度」に移動します][DevtoolsSpeedGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="73bfc-105">To learn how to make your pages load faster, navigate to [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

<span data-ttu-id="73bfc-106">実行時のパフォーマンスは、読み込みとは対照的に、ページの実行時のパフォーマンスです。</span><span class="sxs-lookup"><span data-stu-id="73bfc-106">Runtime performance is how your page performs when it is running, as opposed to loading.</span></span>  <span data-ttu-id="73bfc-107">次のチュートリアル記事では、Microsoft Edge DevTools Performance パネルを使用して実行時のパフォーマンスを分析する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-107">The following tutorial article teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.</span></span>  <span data-ttu-id="73bfc-108">**RAIL**モデルに関して、このチュートリアルで学習するスキルは、ページの応答、アニメーション、アイドル状態のフェーズを分析する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-108">In terms of the **RAIL** model, the skills you learn in this tutorial are useful for analyzing the Response, Animation, and Idle phases of your page.</span></span>  

<!--todo: add rail link when section is ready -->  

## <a name="get-started"></a><span data-ttu-id="73bfc-109">概要</span><span class="sxs-lookup"><span data-stu-id="73bfc-109">Get started</span></span>  

<span data-ttu-id="73bfc-110">次のチュートリアルでは、ライブ ページで DevTools を開き、[パフォーマンス] パネルを使用してページのパフォーマンスのボトルネックを見つける。</span><span class="sxs-lookup"><span data-stu-id="73bfc-110">In the following tutorial, you open DevTools on a live page and use the **Performance** panel to find a performance bottleneck on the page.</span></span>  

1.  <span data-ttu-id="73bfc-111">**InPrivate モードで Microsoft Edge を開きます**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-111">Open Microsoft Edge in **InPrivate Mode**.</span></span>  <span data-ttu-id="73bfc-112">InPrivate モードでは、Microsoft Edge がクリーンな状態で実行されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-112">InPrivate Mode ensures that Microsoft Edge runs in a clean state.</span></span>  <span data-ttu-id="73bfc-113">たとえば、多くの拡張機能がインストールされている場合、拡張機能によってパフォーマンス測定値にノイズが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-113">For example, if you have a lot of extensions installed, the extensions may create noise in your performance measurements.</span></span>  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  <span data-ttu-id="73bfc-114">InPrivate ウィンドウに次のページを読み込む。</span><span class="sxs-lookup"><span data-stu-id="73bfc-114">Load the following page in your InPrivate window.</span></span>  <span data-ttu-id="73bfc-115">このページは、プロファイルを作成するデモです。</span><span class="sxs-lookup"><span data-stu-id="73bfc-115">The page is the demo that you are going to profile.</span></span>  <span data-ttu-id="73bfc-116">ページには、上下に移動する小さなアイコンの束が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-116">The page shows a bunch of little icons moving up and down.</span></span>  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  <span data-ttu-id="73bfc-117">`Control` + `Shift` + `I` \(Windows, Linux\) または `Command` + `Option` + `I` \(macOS\) を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-117">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="左側のデモと右側の DevTools" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       <span data-ttu-id="73bfc-119">左側のデモと右側の DevTools</span><span class="sxs-lookup"><span data-stu-id="73bfc-119">The demo on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="73bfc-120">残りの図では、DevTools はコンテンツに[][DevtoolsCustomizePlacement]焦点を当てるには別のウィンドウにドッキングされません。</span><span class="sxs-lookup"><span data-stu-id="73bfc-120">For the rest of the figures, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] to better focus on the contents.</span></span>  
    
### <a name="simulate-a-mobile-cpu"></a><span data-ttu-id="73bfc-121">モバイル CPU のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="73bfc-121">Simulate a mobile CPU</span></span>  

<span data-ttu-id="73bfc-122">モバイル デバイスの CPU 電力は、デスクトップやラップトップに比してはるかに少ない。</span><span class="sxs-lookup"><span data-stu-id="73bfc-122">Mobile devices have much less CPU power than desktops and laptops.</span></span>  <span data-ttu-id="73bfc-123">ページをプロファイルするたびに、CPU 調整を使用して、モバイル デバイスでのページのパフォーマンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="73bfc-123">Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.</span></span>  

1.  <span data-ttu-id="73bfc-124">DevTools で、[パフォーマンス] ツール **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-124">In DevTools, choose the **Performance** tool.</span></span>  
1.  <span data-ttu-id="73bfc-125">[スクリーンショット] の横にあるチェック ボックスをオン **にします**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-125">Ensure the you choose the checkbox next to **Screenshots**.</span></span>  
1.  <span data-ttu-id="73bfc-126">[ **キャプチャ設定]\(** ![ キャプチャ設定 ](../media/capture-settings-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-126">Choose **Capture Settings** \(![Capture Settings](../media/capture-settings-icon.msft.png)\).</span></span>  <span data-ttu-id="73bfc-127">DevTools は、パフォーマンス 指標のキャプチャ方法に関連する設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-127">DevTools reveals settings related to how it captures performance metrics.</span></span>  
1.  <span data-ttu-id="73bfc-128">**[CPU]** の場合は **、[4 倍の速度低下] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-128">For **CPU**, choose **4x slowdown**.</span></span>  <span data-ttu-id="73bfc-129">DevTools は CPU を調整して、通常の 4 倍遅くします。</span><span class="sxs-lookup"><span data-stu-id="73bfc-129">DevTools throttles your CPU so that it is 4 times slower than usual.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="CPU スロットル" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       <span data-ttu-id="73bfc-131">CPU スロットル</span><span class="sxs-lookup"><span data-stu-id="73bfc-131">CPU throttle</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="73bfc-132">他のページをテストする場合。各ページがローエンド モバイル デバイスで適切に動作する場合は、CPU 調整を **6 倍の速度低下に設定します**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-132">When testing other pages; if you want to ensure that each page works well on low-end mobile devices, set CPU Throttling to **6x slowdown**.</span></span>  <span data-ttu-id="73bfc-133">デモは 6 倍のスローダウンではうまく動作しないので、4 倍のスローダウンを命令目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-133">The demo does not work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.</span></span>  
    
### <a name="set-up-the-demo"></a><span data-ttu-id="73bfc-134">デモのセットアップ</span><span class="sxs-lookup"><span data-stu-id="73bfc-134">Set up the demo</span></span>  

<span data-ttu-id="73bfc-135">Web サイトのすべての閲覧者に一貫して動作するランタイム パフォーマンス デモを作成するのは難しいです。</span><span class="sxs-lookup"><span data-stu-id="73bfc-135">It is hard to create a runtime performance demo that works consistently for all readers of the website.</span></span>  <span data-ttu-id="73bfc-136">次のセクションでは、デモをカスタマイズして、特定のセットアップに関係なく、エクスペリエンスがスクリーンショットや説明と比較的一貫性を保ちます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-136">The following section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions, regardless of your particular set up.</span></span>

1.  <span data-ttu-id="73bfc-137">青い **アイコンが以前よりも明らかに遅くなるまで、[10** の追加] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-137">Choose the **Add 10** button until the blue icons move noticeably slower than before.</span></span>  <span data-ttu-id="73bfc-138">高級機械では、20 回くらい選択できます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-138">On a high-end machine, you may to choose it about 20 times.</span></span>  
1.  <span data-ttu-id="73bfc-139">[最適化 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-139">Choose **Optimize**.</span></span>  <span data-ttu-id="73bfc-140">青いアイコンは、より速く、よりスムーズに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-140">The blue icons should move faster and more smoothly.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="73bfc-141">最適化されたバージョンと最適化されていないバージョンの違いをより適切に表示するには **、[10** の減算] ボタンを数回選択し、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="73bfc-141">To better display a difference between the optimized and un-optimized versions, choose the **Subtract 10** button a few times and try again.</span></span>  
    > <span data-ttu-id="73bfc-142">青いアイコンを追加しすぎると、CPU を最大にし、2 つのバージョンの結果に大きな違いが生じない場合があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-142">If you add too many blue icons, you may max out the CPU and then you may not observe a major difference in the results for the two versions.</span></span>  
    
1.  <span data-ttu-id="73bfc-143">[ **最適化解除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-143">Choose **Un-Optimize**.</span></span>  <span data-ttu-id="73bfc-144">青いアイコンの移動速度が遅く、再び低調になります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-144">The blue icons move slower and with more sluggishness again.</span></span>  
    
### <a name="record-runtime-performance"></a><span data-ttu-id="73bfc-145">実行時のパフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="73bfc-145">Record runtime performance</span></span>  

<span data-ttu-id="73bfc-146">最適化されたバージョンのページを実行すると、青いアイコンの移動速度が速くなります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-146">When you ran the optimized version of the page, the blue icons move faster.</span></span>  <span data-ttu-id="73bfc-147">それはどうしてですか。</span><span class="sxs-lookup"><span data-stu-id="73bfc-147">Why is that?</span></span>  <span data-ttu-id="73bfc-148">どちらのバージョンも、アイコンを同じ時間内に同じ容量の領域に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-148">Both versions are supposed to move the icons the same amount of space in the same amount of time.</span></span>  <span data-ttu-id="73bfc-149">[パフォーマンス] パネルでレコーディングを行い、最適化されていないバージョンでパフォーマンスのボトルネックを検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-149">Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.</span></span>  

1.  <span data-ttu-id="73bfc-150">DevTools で、Record **\(** ![ Record ](../media/record-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-150">In DevTools, choose **Record** \(![Record](../media/record-icon.msft.png)\).</span></span>  <span data-ttu-id="73bfc-151">DevTools は、ページの実行時にパフォーマンス 指標をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="73bfc-151">DevTools captures performance metrics as the page runs.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="ページのプロファイル" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       <span data-ttu-id="73bfc-153">ページのプロファイル</span><span class="sxs-lookup"><span data-stu-id="73bfc-153">Profile the page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="73bfc-154">数秒待ちます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-154">Wait a few seconds.</span></span>  
1.  <span data-ttu-id="73bfc-155">[ **停止] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-155">Choose **Stop**.</span></span>  <span data-ttu-id="73bfc-156">DevTools は記録を停止し、データを処理し、結果を [パフォーマンス] パネルに表示します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-156">DevTools stops recording, processes the data, then displays the results on the Performance panel.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="プロファイルの結果" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       <span data-ttu-id="73bfc-158">プロファイルの結果</span><span class="sxs-lookup"><span data-stu-id="73bfc-158">The results of the profile</span></span>  
    :::image-end:::  
    
<span data-ttu-id="73bfc-159">うわー、それは圧倒的な量のデータです。</span><span class="sxs-lookup"><span data-stu-id="73bfc-159">Wow, that is an overwhelming amount of data.</span></span>  <span data-ttu-id="73bfc-160">心配しないで、すぐにプロセスはもっと理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="73bfc-160">do not worry, soon the process makes more sense.</span></span>  

## <a name="analyze-the-results"></a><span data-ttu-id="73bfc-161">結果を分析する</span><span class="sxs-lookup"><span data-stu-id="73bfc-161">Analyze the results</span></span>  

<span data-ttu-id="73bfc-162">ページのパフォーマンスを記録した後、ページのパフォーマンスの品質を測定し、原因を見つける。</span><span class="sxs-lookup"><span data-stu-id="73bfc-162">After you record the performance of the page, measure the quality of the performance of the page and find the any causes.</span></span>  

### <a name="analyze-frames-per-second"></a><span data-ttu-id="73bfc-163">1 秒あたりのフレーム数の分析</span><span class="sxs-lookup"><span data-stu-id="73bfc-163">Analyze frames per second</span></span>  

<span data-ttu-id="73bfc-164">アニメーションのパフォーマンスを測定する主な指標は、1 秒あたりのフレーム数 \(FPS\) です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-164">The main metric for measuring the performance of any animation is frames per second \(FPS\).</span></span>  <span data-ttu-id="73bfc-165">アニメーションが 60 FPS で実行される場合、ユーザーは満足しています。</span><span class="sxs-lookup"><span data-stu-id="73bfc-165">Users are happy when animations run at 60 FPS.</span></span>  

1.  <span data-ttu-id="73bfc-166">FPS グラフ **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-166">Review the **FPS** chart.</span></span>  <span data-ttu-id="73bfc-167">赤いバーが **FPS**の上に表示されるたびに、フレームレートが低くドロップされ、ユーザー エクスペリエンスに害を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-167">Whenever a red bar is displayed above **FPS**, it means that the framerate dropped so low that it is probably harming the user experience.</span></span>  <span data-ttu-id="73bfc-168">一般に、緑のバーが大きいほど、FPS は高くなります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-168">In general, the higher the green bar, the higher the FPS.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       <span data-ttu-id="73bfc-170">**FPS グラフ**</span><span class="sxs-lookup"><span data-stu-id="73bfc-170">The **FPS** chart</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="73bfc-171">FPS グラフ **の下** に **CPU グラフ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-171">Below the **FPS** chart, the **CPU** chart is displayed.</span></span>  <span data-ttu-id="73bfc-172">CPU グラフの**色**は、[パフォーマンス] パネルの 下部にある [概要] パネルの色に対応します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-172">The colors in the **CPU** chart correspond to the colors in the **Summary** panel, at the bottom of the Performance panel.</span></span>  <span data-ttu-id="73bfc-173">CPU グラフが **色に** 満ちていという事実は、記録中に CPU が最大にされたという意味です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-173">The fact that the **CPU** chart is full of color means that the CPU was maxed out during the recording.</span></span>  <span data-ttu-id="73bfc-174">CPU が長時間使い切った場合は常に、より少ない作業を行う方法を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-174">Whenever the CPU maxed out for long periods, it is an indicator that you should find ways to do less work.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="[CPU グラフ] と [概要] パネル" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       <span data-ttu-id="73bfc-176">**[CPU グラフ**] と **[概要]** パネル</span><span class="sxs-lookup"><span data-stu-id="73bfc-176">The **CPU** chart and **Summary** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="73bfc-177">**FPS、CPU、または** **NET**グラフに**カーソルを合**わせる。</span><span class="sxs-lookup"><span data-stu-id="73bfc-177">Hover on the **FPS**, **CPU**, or **NET** charts.</span></span>  <span data-ttu-id="73bfc-178">DevTools は、その時点でページのスクリーンショットを表示します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-178">DevTools shows a screenshot of the page at that point in time.</span></span>  <span data-ttu-id="73bfc-179">マウスを左右に動かすと、録音が再生されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-179">Move your mouse left and right to replay the recording.</span></span>  <span data-ttu-id="73bfc-180">アクションはスクラブとして参照され、アニメーションの進行状況を手動で分析する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-180">The action is referenced as scrubbing, and it is useful for manually analyzing the progression of animations.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="記録の 2500ms マークを中心にページのスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       <span data-ttu-id="73bfc-182">記録の 2500ms マークを中心にページのスクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="73bfc-182">View a screenshot of the page around the 2500ms mark of the recording</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="73bfc-183">[フレーム **] セクション** で、緑色の四角形の 1 つをポイントします。</span><span class="sxs-lookup"><span data-stu-id="73bfc-183">In the **Frames** section, hover on one of the green squares.</span></span>  <span data-ttu-id="73bfc-184">DevTools には、その特定のフレームの FPS が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-184">DevTools shows you the FPS for that particular frame.</span></span>  <span data-ttu-id="73bfc-185">各フレームは、ターゲットの 60 FPS を大いに下回っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-185">Each frame is probably well below the target of 60 FPS.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="フレームにカーソルを合わせる" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       <span data-ttu-id="73bfc-187">フレームにカーソルを合わせる</span><span class="sxs-lookup"><span data-stu-id="73bfc-187">Hover on a frame</span></span>  
    :::image-end:::  
    
<span data-ttu-id="73bfc-188">もちろん、表示は Web ページがうまく機能していないと示します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-188">Of course, the display indicates that the webpage is not performing well.</span></span>  <span data-ttu-id="73bfc-189">しかし、実際のシナリオでは、明らかではないので、測定を行うすべてのツールを使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-189">But in real scenarios, it may not be so clear, so having all of the tools to make measurements comes in handy.</span></span>  

#### <a name="bonus-open-the-fps-meter"></a><span data-ttu-id="73bfc-190">ボーナス: FPS メーターを開く</span><span class="sxs-lookup"><span data-stu-id="73bfc-190">Bonus: Open the FPS meter</span></span>  

<span data-ttu-id="73bfc-191">もう 1 つの便利なツールは、ページの実行時に FPS のリアルタイム推定値を提供する FPS メーターです。</span><span class="sxs-lookup"><span data-stu-id="73bfc-191">Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.</span></span>  

1.  <span data-ttu-id="73bfc-192">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-192">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="73bfc-193">コマンド メニューで `Rendering` 入力を **開始し、[レンダリング** の表示] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-193">Start typing `Rendering` in the **Command Menu** and choose **Show Rendering**.</span></span>  
1.  <span data-ttu-id="73bfc-194">レンダリング ツール **で、[FPS** メーター] **をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-194">In the **Rendering** tool, turn on **FPS Meter**.</span></span>  <span data-ttu-id="73bfc-195">新しいオーバーレイがビューポートの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-195">A new overlay appears in the top-right of your viewport.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       <span data-ttu-id="73bfc-197">**FPS メーター**</span><span class="sxs-lookup"><span data-stu-id="73bfc-197">The **FPS meter**</span></span>  
        :::image-end:::  
    
1.  <span data-ttu-id="73bfc-198">FPS メーターを **オフにし、[** レンダリング] `Escape` ツールを閉じる場合 **に選択** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-198">Turn off the **FPS Meter** and select `Escape` to close the **Rendering** tool.</span></span>  <span data-ttu-id="73bfc-199">このチュートリアルでは **、FPS メーター** を使用しません。</span><span class="sxs-lookup"><span data-stu-id="73bfc-199">You are not using **FPS Meter** in this tutorial.</span></span>  
    
### <a name="find-the-bottleneck"></a><span data-ttu-id="73bfc-200">ボトルネックを見つける</span><span class="sxs-lookup"><span data-stu-id="73bfc-200">Find the bottleneck</span></span>  

<span data-ttu-id="73bfc-201">アニメーションがうまく機能していないと測定して確認した後、次の手順は「なぜですか」という質問に答えます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-201">After you measured and verified that the animation is not performing well, the next step is to answer the question "why?".</span></span>  

1.  <span data-ttu-id="73bfc-202">イベントが選択されている場合は、[ **概要** ] パネルにアクティビティの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-202">When no events are chosen, the **Summary** panel shows you a breakdown of activity.</span></span>  <span data-ttu-id="73bfc-203">ページはレンダリングに多くの時間を費やしました。</span><span class="sxs-lookup"><span data-stu-id="73bfc-203">The page spent most of the time rendering.</span></span>  <span data-ttu-id="73bfc-204">パフォーマンスは少ない作業を行う技術ですから、レンダリング作業に費やされる時間を減らすことが目標です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-204">Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text="[概要] パネル" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       <span data-ttu-id="73bfc-206">[ **概要]** パネル</span><span class="sxs-lookup"><span data-stu-id="73bfc-206">The **Summary** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="73bfc-207">[メイン] **セクションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-207">Expand the **Main** section.</span></span>  <span data-ttu-id="73bfc-208">DevTools は、メイン スレッドのアクティビティの時間の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-208">DevTools shows you a flame chart of activity on the main thread, over time.</span></span>  <span data-ttu-id="73bfc-209">x 軸は、時間の過ぎた記録を表します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-209">The x-axis represents the recording, over time.</span></span>  <span data-ttu-id="73bfc-210">各バーはイベントを表します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-210">Each bar represents an event.</span></span>  <span data-ttu-id="73bfc-211">バーが広いということは、イベントに時間がかかったという意味です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-211">A wider bar means that event took longer.</span></span>  <span data-ttu-id="73bfc-212">y 軸は呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-212">The y-axis represents the call stack.</span></span>  <span data-ttu-id="73bfc-213">イベントが互いに重なって表示される場合は、上位イベントによって下位イベントが発生したという意味です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-213">When events are stacked on top of each other, it means the upper events caused the lower events.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="[メイン] セクション" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       <span data-ttu-id="73bfc-215">[ **メイン]** セクション</span><span class="sxs-lookup"><span data-stu-id="73bfc-215">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="73bfc-216">記録には多くのデータがあります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-216">There is a lot of data in the recording.</span></span>  <span data-ttu-id="73bfc-217">1 つのイベントを拡大するには。  **FPS、CPU、** および NET グラフを含むセクションである Overview の上でカーソルを選択、保持、**およびドラッグ**します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-217">To Zoom into a single event; choose, hold, and dragg your cursor over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="73bfc-218">[ **メイン]** セクションと **[概要]** パネルには、録音の選択した部分の情報だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-218">The **Main** section and **Summary** panel only display information for the chosen portion of the recording.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="イベントを拡大する" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       <span data-ttu-id="73bfc-220">イベントを拡大する</span><span class="sxs-lookup"><span data-stu-id="73bfc-220">Zoom into an event</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="73bfc-221">もう 1 つの方法として、ズーム、 **メイン** セクションのフォーカス、背景またはイベントの選択、および `W` 、 `A` `S` を選択します `D` 。</span><span class="sxs-lookup"><span data-stu-id="73bfc-221">Another way to zoom, focus the **Main** section, choose the background or an event, and select `W`, `A`, `S`, or `D`.</span></span>  
    
    1.  <span data-ttu-id="73bfc-222">Animation Frame Fired イベントの右の赤い三角形 **にフォーカス** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-222">Focus on the red triangle in the top-right of the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="73bfc-223">赤い三角形が表示されるたびに、イベントに関連する問題が発生する可能性があるという警告です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-223">Whenever a red triangle is displayed, it is a warning that there may be an issue related to the event.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="73bfc-224">Animation **Frame Fired** イベントは [、requestAnimationFrame()][MDNWebRequestAnimationFrame] コールバックが実行されるたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-224">The **Animation Frame Fired** event occurs whenever a [requestAnimationFrame() callback][MDNWebRequestAnimationFrame] is run.</span></span>  
    
1.  <span data-ttu-id="73bfc-225">[アニメーション フレーム **の発生] イベントを選択** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-225">Choose the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="73bfc-226">[ **概要] パネル** に、そのイベントに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-226">The **Summary** panel now shows you information about that event.</span></span>  <span data-ttu-id="73bfc-227">[表示] **リンクに注意** してください。</span><span class="sxs-lookup"><span data-stu-id="73bfc-227">Note the **Reveal** link.</span></span>  <span data-ttu-id="73bfc-228">選択した後、DevTools は Animation Frame Fired イベントを開始したイベント **を強調表示** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-228">After you choose it, DevTools to highlights the event that initiated the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="73bfc-229">また  、app.js:95 リンクにフォーカス します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-229">Also, focus on the **app.js:95** link.</span></span>  <span data-ttu-id="73bfc-230">選択すると、ソース コード内の関連する行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-230">After you choose it, the relevant line in the source code is displayed.</span></span>
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="Animation Frame Fired イベントの詳細" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       <span data-ttu-id="73bfc-232">Animation Frame **Fired イベントの詳細**</span><span class="sxs-lookup"><span data-stu-id="73bfc-232">More information about the **Animation Frame Fired** event</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="73bfc-233">イベントを選択した後、矢印キーを使用して、イベントの横にあるイベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-233">After choosing an event, use the arrow keys to select the events next to it.</span></span>  
    
1.  <span data-ttu-id="73bfc-234">**app.update イベント**では、紫色のイベントが多く発生します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-234">Under the **app.update** event, there is a bunch of purple events.</span></span>  <span data-ttu-id="73bfc-235">紫色の各イベントが広い場合は、それぞれのイベントに赤い三角形が付く可能性があるように見えます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-235">If each purple event was wider, it looks as though each one may have a red triangle on it.</span></span>  
1.  <span data-ttu-id="73bfc-236">紫色のレイアウト イベントのいずれかを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-236">Choose one of the purple **Layout** events.</span></span>  <span data-ttu-id="73bfc-237">DevTools は、[概要] パネルでイベントに関する詳細 **を提供** します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-237">DevTools provides more information about the event in the **Summary** panel.</span></span>  <span data-ttu-id="73bfc-238">実際、強制リフロー \(layout\の別の単語) に関する警告があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-238">Indeed, there is a warning about forced reflows \(another word for layout\).</span></span>  
    
1.  <span data-ttu-id="73bfc-239">[概要 **] パネルで** 、[レイアウトの強制]  の [app.js:71] リンク **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bfc-239">In the **Summary** panel, choose the **app.js:71** link under **Layout Forced**.</span></span>  <span data-ttu-id="73bfc-240">DevTools は、レイアウトを強制したコード行にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="73bfc-240">DevTools takes you to the line of code that forced the layout.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="強制レイアウトの原因となるコード行" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       <span data-ttu-id="73bfc-242">強制レイアウトの原因となるコード行</span><span class="sxs-lookup"><span data-stu-id="73bfc-242">The line of code that caused the forced layout</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="73bfc-243">コードの問題は、各アニメーション フレームで各アイコンのスタイルを変更し、ページ上の各アイコンの位置を照会する点です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-243">The problem with the code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.</span></span>  <span data-ttu-id="73bfc-244">スタイルが変更されたため、ブラウザーは各アイコンの位置が変更されたかどうか分からないので、新しい位置を計算するためにアイコンのレイアウトを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-244">Because the styles changed, the browser does not know if each icon position changed, so it has to re-layout the icon in order to compute the new position.</span></span>  <!--  > To learn more, navigate to [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts].  -->
    
<!-- todo: add layouts section when available -->

<span data-ttu-id="73bfc-245">それは学ぶことが多かった。</span><span class="sxs-lookup"><span data-stu-id="73bfc-245">That was a lot to learn.</span></span>  <span data-ttu-id="73bfc-246">これで、実行時のパフォーマンスを分析するための基本的なワークフローの基盤が構築されました。</span><span class="sxs-lookup"><span data-stu-id="73bfc-246">You now have a solid foundation in the basic workflow for analyzing runtime performance.</span></span>  <span data-ttu-id="73bfc-247">よく出来ました。</span><span class="sxs-lookup"><span data-stu-id="73bfc-247">Good job.</span></span>  

### <a name="bonus-analyze-the-optimized-version"></a><span data-ttu-id="73bfc-248">ボーナス: 最適化されたバージョンを分析する</span><span class="sxs-lookup"><span data-stu-id="73bfc-248">Bonus: Analyze the optimized version</span></span>  

<span data-ttu-id="73bfc-249">学習したワークフローとツールを使用して、デモで [ 最適化] を選択して、最適化されたコードを有効にし、別のパフォーマンス記録を取り、結果を分析します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-249">Using the workflows and tools that you just learned, choose **Optimize** on the demo to turn on the optimized code, take another performance recording, and then analyze the results.</span></span>  <span data-ttu-id="73bfc-250">改善されたフレームレートから、メイン セクションのフレーム グラフ内のイベントの 削減まで、アプリの最適化されたバージョンでは作業が大幅に少なく、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="73bfc-250">From the improved framerate to the reduction in events in the flame chart in the **Main** section, the optimized version of the app does much less work, resulting in better performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="73bfc-251">最適化されたバージョンでさえ、すべてのアイコンのプロパティを操作します `top` 。</span><span class="sxs-lookup"><span data-stu-id="73bfc-251">Even the optimized version is not great, because it manipulates the `top` property of every icon.</span></span>  <span data-ttu-id="73bfc-252">より良い方法は、合成にのみ影響を与えるプロパティに固執する方法です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-252">A better approach is to stick to properties that only affect compositing.</span></span>  <!--  > For more information, navigate to [Use transform and opacity changes for animations][RenderingCompositor].  -->  

<!--todo: add rendering section when available -->

## <a name="next-steps"></a><span data-ttu-id="73bfc-253">次の手順</span><span class="sxs-lookup"><span data-stu-id="73bfc-253">Next steps</span></span>

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
To learn more, navigate to [Measure Performance With The RAIL Model][RAIL].  -->  

<span data-ttu-id="73bfc-254">パフォーマンス ツールの使い心地を **向上するために** 、プラクティスは完璧です。</span><span class="sxs-lookup"><span data-stu-id="73bfc-254">To get more comfortable with the **Performance** tool, practice makes perfect.</span></span>  <span data-ttu-id="73bfc-255">ページのプロファイリングと結果の分析を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="73bfc-255">Try profiling your pages and analyzing the results.</span></span>  <span data-ttu-id="73bfc-256">結果について質問がある場合は、[フィードバックの送信] アイコンを使用し `Alt` + `Shift` + `I` 、[\(Windows, Linux\] を選択 `Option` + `Shift` + `I` )、\(macOS\)を選択するか[、DevTools][TwitterEdgeDevtools]チームをつぶやきます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-256">If you have any questions about your results, use the **Send Feedback** icon, select `Alt`+`Shift`+`I` \(Windows, Linux\), select `Option`+`Shift`+`I` \(macOS\), or [tweet the DevTools team][TwitterEdgeDevtools].</span></span>  <span data-ttu-id="73bfc-257">可能であれば、再現可能なページへのスクリーンショットまたはリンクを含める。</span><span class="sxs-lookup"><span data-stu-id="73bfc-257">Include screenshots or links to reproducible pages, if possible.</span></span>  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="Microsoft Edge DevTools の **Feedback** アイコン" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   <span data-ttu-id="73bfc-259">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="73bfc-259">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

<span data-ttu-id="73bfc-260">最後に、実行時のパフォーマンスを向上させる多くの方法があります。</span><span class="sxs-lookup"><span data-stu-id="73bfc-260">Last, there are many ways to improve runtime performance.</span></span>  <span data-ttu-id="73bfc-261">この記事では、特定のアニメーションのボトルネックに焦点を当て、パフォーマンス パネルを中心にツアーを行いましたが、発生する可能性がある多くのボトルネックの 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="73bfc-261">This article focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.</span></span>  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="73bfc-262">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="73bfc-262">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[DevtoolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更する (Undock、Dock to Bottom、Dock to Left)"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Microsoft Edge DevTools を使用して Web サイトの速度を最適化する"  

[TwitterEdgeDevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "EdgeDevTools - ツイートを投稿|Twitter"  

[MDNWebRequestAnimationFrame]: https://developer.mozilla.org/docs/Web/API/window/requestAnimationFrame "Window.requestAnimationFrame\(\) |MDN"  

<!--[InPrivate]: https://support.microsoft.com/help/4026200/microsoft-edge-browse-inprivate "Browse InPrivate in Microsoft Edge"  -->

<!--[FrameAnatomy]: https://aerotwist.com/blog/the-anatomy-of-a-frame  -->  

<!--[RAIL]: /web/fundamentals/performance/rail  -->  
<!--[RenderingAvoidSynchronousLayouts]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing#avoid_forced_synchronous_layouts  -->  
<!--[RenderingAvoidThrashing]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing  -->  
<!--[RenderingCompositor]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count#use_transform_and_opacity_changes_for_animations  -->  
<!--[RenderingDebounceInputs]: /web/fundamentals/performance/rendering/debounce-your-input-handlers  -->
<!--[RenderingManageLayers]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count  -->  
<!--[RenderingOptimizeJS]: /web/fundamentals/performance/rendering/optimize-javascript-execution  -->  
<!--[RenderingPerformance]: /web/fundamentals/performance/rendering  -->  
<!--[RenderingReduceScope]: /web/fundamentals/performance/rendering/reduce-the-scope-and-complexity-of-style-calculations  -->  
<!--[RenderingSimplifyPaint]: /web/fundamentals/performance/rendering/simplify-paint-complexity-and-reduce-paint-areas  -->  

<!--[StackOverflowAlphabetBrowserDevtools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser - Stack Overflow"  -->  

> [!NOTE]
> <span data-ttu-id="73bfc-267">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="73bfc-267">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="73bfc-268">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="73bfc-268">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="73bfc-270">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="73bfc-270">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
