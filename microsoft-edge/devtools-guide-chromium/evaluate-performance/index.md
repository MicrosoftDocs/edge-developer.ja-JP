---
title: 実行時のパフォーマンスの分析を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 94753c7024c2f4f4c96d560c815d310b1f9643a1
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931160"
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

# <span data-ttu-id="2792d-103">実行時のパフォーマンスの分析を開始する</span><span class="sxs-lookup"><span data-stu-id="2792d-103">Get started with analyzing Runtime performance</span></span>  

> [!NOTE]
> <span data-ttu-id="2792d-104">ページの読み込みを高速化する方法については、「 [Web サイトの速度を最適化][DevtoolsSpeedGetStarted]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2792d-104">To learn how to make your pages load faster, see [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

<span data-ttu-id="2792d-105">実行時のパフォーマンスは、読み込みとは異なり、ページが実行されている場合の実行方法です。</span><span class="sxs-lookup"><span data-stu-id="2792d-105">Runtime performance is how your page performs when it is running, as opposed to loading.</span></span>  <span data-ttu-id="2792d-106">次のチュートリアルでは、Microsoft Edge DevTools パフォーマンスパネルを使って実行時のパフォーマンスを分析する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2792d-106">The following tutorial article teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.</span></span>  <span data-ttu-id="2792d-107">このチュートリアルで学習するスキル **は、ページ** の応答、アニメーション、およびアイドルフェーズを分析するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2792d-107">In terms of the **RAIL** model, the skills you learn in this tutorial are useful for analyzing the Response, Animation, and Idle phases of your page.</span></span>  

<!--todo: add rail link when section is ready -->  

## <span data-ttu-id="2792d-108">使ってみる</span><span class="sxs-lookup"><span data-stu-id="2792d-108">Get started</span></span>  

<span data-ttu-id="2792d-109">次のチュートリアルでは、ライブページで DevTools を開き、[ **パフォーマンス** ] パネルを使用して、ページ上のパフォーマンスのボトルネックを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2792d-109">In the following tutorial, you open DevTools on a live page and use the **Performance** panel to find a performance bottleneck on the page.</span></span>  

1.  <span data-ttu-id="2792d-110">**InPrivate モード**で Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="2792d-110">Open Microsoft Edge in **InPrivate Mode**.</span></span>  <span data-ttu-id="2792d-111">InPrivate モードでは、Microsoft Edge がクリーンな状態で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-111">InPrivate Mode ensures that Microsoft Edge runs in a clean state.</span></span>  <span data-ttu-id="2792d-112">たとえば、多くの拡張機能がインストールされている場合は、拡張機能によってパフォーマンスの測定値にノイズが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2792d-112">For example, if you have a lot of extensions installed, the extensions may create noise in your performance measurements.</span></span>  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  <span data-ttu-id="2792d-113">InPrivate ウィンドウに次のページを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="2792d-113">Load the following page in your InPrivate window.</span></span>  <span data-ttu-id="2792d-114">このページは、プロファイルを作成しようとしているデモです。</span><span class="sxs-lookup"><span data-stu-id="2792d-114">The page is the demo that you are going to profile.</span></span>  <span data-ttu-id="2792d-115">ページには、上下に移動する小さなアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-115">The page shows a bunch of little icons moving up and down.</span></span>  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  <span data-ttu-id="2792d-116">`Control` + `Shift` + `I` Devtools を開くには、\ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="2792d-116">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="左側のデモと、右側の DevTools" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       <span data-ttu-id="2792d-118">左側のデモと、右側の DevTools</span><span class="sxs-lookup"><span data-stu-id="2792d-118">The demo on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="2792d-119">その他の機能については、「DevTools [」は別のウィンドウにドッキング][DevtoolsCustomizePlacement] 解除され、内容に集中しやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="2792d-119">For the rest of the figures, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] to better focus on the contents.</span></span>  
    
### <span data-ttu-id="2792d-120">モバイル CPU のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="2792d-120">Simulate a mobile CPU</span></span>  

<span data-ttu-id="2792d-121">モバイルデバイスは、デスクトップとノート pc よりも CPU の消費電力が非常に少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="2792d-121">Mobile devices have much less CPU power than desktops and laptops.</span></span>  <span data-ttu-id="2792d-122">ページをプロファイルするたびに、CPU 調整を使って、ページがモバイルデバイスでどのように動作するかをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="2792d-122">Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.</span></span>  

1.  <span data-ttu-id="2792d-123">DevTools で、[ **パフォーマンス** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2792d-123">In DevTools, choose the **Performance** tab.</span></span>  
1.  <span data-ttu-id="2792d-124">[ **スクリーンショット** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2792d-124">Make sure that the **Screenshots** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="2792d-125">[ **キャプチャの設定** ] を選びます。Capture 設定] [ImageCaptureSettingsIcon] \)。</span><span class="sxs-lookup"><span data-stu-id="2792d-125">Choose **Capture Settings** \(![Capture Settings][ImageCaptureSettingsIcon]\).</span></span>  <span data-ttu-id="2792d-126">DevTools は、パフォーマンス指標のキャプチャに関連する設定を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="2792d-126">DevTools reveals settings related to how it captures performance metrics.</span></span>  
1.  <span data-ttu-id="2792d-127">**CPU**の場合は、[ **4 倍速減速**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2792d-127">For **CPU**, select **4x slowdown**.</span></span>  <span data-ttu-id="2792d-128">DevTools では、CPU が通常より4倍遅くなるように CPU を調整します。</span><span class="sxs-lookup"><span data-stu-id="2792d-128">DevTools throttles your CPU so that it is 4 times slower than usual.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="CPU 調整" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       <span data-ttu-id="2792d-130">CPU 調整</span><span class="sxs-lookup"><span data-stu-id="2792d-130">CPU throttle</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="2792d-131">他のページをテストする場合各ページがローエンドのモバイルデバイスで適切に動作することを確認したい場合は、CPU の調整を **6x の速度**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2792d-131">When testing other pages; if you want to ensure that each page works well on low-end mobile devices, set CPU Throttling to **6x slowdown**.</span></span>  <span data-ttu-id="2792d-132">デモは、6x の速度では適切に動作しないため、説明目的のために4倍速の遅延を使います。</span><span class="sxs-lookup"><span data-stu-id="2792d-132">The demo does not work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.</span></span>  
    
### <span data-ttu-id="2792d-133">デモを設定する</span><span class="sxs-lookup"><span data-stu-id="2792d-133">Set up the demo</span></span>  

<span data-ttu-id="2792d-134">Web サイトのすべてのリーダーで一貫して動作するランタイムパフォーマンスのデモを作成することは困難です。</span><span class="sxs-lookup"><span data-stu-id="2792d-134">It is hard to create a runtime performance demo that works consistently for all readers of the website.</span></span>  <span data-ttu-id="2792d-135">以下のセクションでは、特定の設定に関係なく、デモをカスタマイズして、エクスペリエンスがスクリーンショットと説明と比較的一貫していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2792d-135">The following section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions, regardless of your particular set up.</span></span>

1.  <span data-ttu-id="2792d-136">青いアイコンが以前よりも著しく遅くなるまで、[ **10 を追加** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2792d-136">Choose the **Add 10** button until the blue icons move noticeably slower than before.</span></span>  <span data-ttu-id="2792d-137">ハイエンドのコンピュータでは、約20回選択できます。</span><span class="sxs-lookup"><span data-stu-id="2792d-137">On a high-end machine, you may to choose it about 20 times.</span></span>  
1.  <span data-ttu-id="2792d-138">[ **最適化**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2792d-138">Choose **Optimize**.</span></span>  <span data-ttu-id="2792d-139">青いアイコンが速く、スムーズに移動します。</span><span class="sxs-lookup"><span data-stu-id="2792d-139">The blue icons should move faster and more smoothly.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="2792d-140">最適化されたバージョンと最適化されていないバージョンの違いをより詳しく表示するには、[ **10 を減算** ] ボタンを数回選択して、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="2792d-140">To better display a difference between the optimized and un-optimized versions, choose the **Subtract 10** button a few times and try again.</span></span>  
    > <span data-ttu-id="2792d-141">追加した青色のアイコンが多すぎる場合は、CPU を最大にすることができます。2つのバージョンの結果には、大きな違いが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="2792d-141">If you add too many blue icons, you may max out the CPU and then you may not observe a major difference in the results for the two versions.</span></span>  
    
1.  <span data-ttu-id="2792d-142">[ **最適化の取り消し**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2792d-142">Choose **Un-Optimize**.</span></span>  <span data-ttu-id="2792d-143">青いアイコンは遅くなり、さらに sluggishness が増えます。</span><span class="sxs-lookup"><span data-stu-id="2792d-143">The blue icons move slower and with more sluggishness again.</span></span>  
    
### <span data-ttu-id="2792d-144">実行時のパフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="2792d-144">Record runtime performance</span></span>  

<span data-ttu-id="2792d-145">最適化されたバージョンのページを実行すると、青色のアイコンが速く移動します。</span><span class="sxs-lookup"><span data-stu-id="2792d-145">When you ran the optimized version of the page, the blue icons move faster.</span></span>  <span data-ttu-id="2792d-146">それはどうしてですか。</span><span class="sxs-lookup"><span data-stu-id="2792d-146">Why is that?</span></span>  <span data-ttu-id="2792d-147">どちらのバージョンでも、同じ時間の間隔でアイコンを移動することが想定されています。</span><span class="sxs-lookup"><span data-stu-id="2792d-147">Both versions are supposed to move the icons the same amount of space in the same amount of time.</span></span>  <span data-ttu-id="2792d-148">最適化されていないバージョンのパフォーマンスのボトルネックを検出する方法については、パフォーマンスパネルで記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="2792d-148">Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.</span></span>  

1.  <span data-ttu-id="2792d-149">DevTools で、[ **Record** ] (! [Record] [ImageRecordIcon] \)。</span><span class="sxs-lookup"><span data-stu-id="2792d-149">In DevTools, choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  <span data-ttu-id="2792d-150">DevTools は、ページが実行されたときにパフォーマンスのメトリックをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="2792d-150">DevTools captures performance metrics as the page runs.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="ページのプロファイル" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       <span data-ttu-id="2792d-152">ページのプロファイル</span><span class="sxs-lookup"><span data-stu-id="2792d-152">Profile the page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2792d-153">数秒待ってください。</span><span class="sxs-lookup"><span data-stu-id="2792d-153">Wait a few seconds.</span></span>  
1.  <span data-ttu-id="2792d-154">[ **停止**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2792d-154">Choose **Stop**.</span></span>  <span data-ttu-id="2792d-155">DevTools は記録を停止し、データを処理して、パフォーマンスパネルに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="2792d-155">DevTools stops recording, processes the data, then displays the results on the Performance panel.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="プロファイルの結果" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       <span data-ttu-id="2792d-157">プロファイルの結果</span><span class="sxs-lookup"><span data-stu-id="2792d-157">The results of the profile</span></span>  
    :::image-end:::  
    
<span data-ttu-id="2792d-158">これは、データ量が圧倒的であるということです。</span><span class="sxs-lookup"><span data-stu-id="2792d-158">Wow, that is an overwhelming amount of data.</span></span>  <span data-ttu-id="2792d-159">このプロセスについては、すぐに理解してください。</span><span class="sxs-lookup"><span data-stu-id="2792d-159">do not worry, soon the process makes more sense.</span></span>  

## <span data-ttu-id="2792d-160">結果を分析する</span><span class="sxs-lookup"><span data-stu-id="2792d-160">Analyze the results</span></span>  

<span data-ttu-id="2792d-161">ページのパフォーマンスを記録したら、ページのパフォーマンスの品質を測定し、任意の原因を見つけます。</span><span class="sxs-lookup"><span data-stu-id="2792d-161">After you record the performance of the page, measure the quality of the performance of the page and find the any causes.</span></span>  

### <span data-ttu-id="2792d-162">1秒あたりのフレーム数の分析</span><span class="sxs-lookup"><span data-stu-id="2792d-162">Analyze frames per second</span></span>  

<span data-ttu-id="2792d-163">アニメーションのパフォーマンスを測定するための主な指標は、1秒あたりのフレーム数 (FPS) です。</span><span class="sxs-lookup"><span data-stu-id="2792d-163">The main metric for measuring the performance of any animation is frames per second \(FPS\).</span></span>  <span data-ttu-id="2792d-164">アニメーションが 60 FPS で実行されている場合は、ユーザーが満足しています。</span><span class="sxs-lookup"><span data-stu-id="2792d-164">Users are happy when animations run at 60 FPS.</span></span>  

1.  <span data-ttu-id="2792d-165">**FPS**グラフを確認します。</span><span class="sxs-lookup"><span data-stu-id="2792d-165">Look at the **FPS** chart.</span></span>  <span data-ttu-id="2792d-166">**FPS**の上に赤色のバーが表示されている場合は、ユーザーエクスペリエンスが損なわれる可能性が低いため、フレームレートが低下していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2792d-166">Whenever you see a red bar above **FPS**, it means that the framerate dropped so low that it is probably harming the user experience.</span></span>  <span data-ttu-id="2792d-167">一般に、緑色のバーが大きくなるほど、FPS は高くなります。</span><span class="sxs-lookup"><span data-stu-id="2792d-167">In general, the higher the green bar, the higher the FPS.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       <span data-ttu-id="2792d-169">**FPS**グラフ</span><span class="sxs-lookup"><span data-stu-id="2792d-169">The **FPS** chart</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2792d-170">**FPS**グラフの下には、 **CPU**グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-170">Below the **FPS** chart you see the **CPU** chart.</span></span>  <span data-ttu-id="2792d-171">**CPU**グラフの色は、[パフォーマンス] パネルの下部にある [**概要**] タブの色に対応しています。</span><span class="sxs-lookup"><span data-stu-id="2792d-171">The colors in the **CPU** chart correspond to the colors in the **Summary** tab, at the bottom of the Performance panel.</span></span>  <span data-ttu-id="2792d-172">**Cpu**グラフが色がいっぱいになっているということは、記録中に cpu が最大化されていたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2792d-172">The fact that the **CPU** chart is full of color means that the CPU was maxed out during the recording.</span></span>  <span data-ttu-id="2792d-173">長期間にわたって CPU が不足している場合は、作業を軽減する方法を見つけるための手掛かりとなります。</span><span class="sxs-lookup"><span data-stu-id="2792d-173">Whenever you see the CPU maxed out for long periods, it is a cue to find ways to do less work.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="[CPU グラフ] と [概要] タブ" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       <span data-ttu-id="2792d-175">[ **CPU** グラフ] と [ **概要** ] タブ</span><span class="sxs-lookup"><span data-stu-id="2792d-175">The **CPU** chart and **Summary** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2792d-176">**FPS**、 **CPU**、または**ネット**チャートをポイントします。</span><span class="sxs-lookup"><span data-stu-id="2792d-176">Hover on the **FPS**, **CPU**, or **NET** charts.</span></span>  <span data-ttu-id="2792d-177">[DevTools] は、現時点でのページのスクリーンショットを示します。</span><span class="sxs-lookup"><span data-stu-id="2792d-177">DevTools shows a screenshot of the page at that point in time.</span></span>  <span data-ttu-id="2792d-178">マウスを左または右に移動して、記録を再生します。</span><span class="sxs-lookup"><span data-stu-id="2792d-178">Move your mouse left and right to replay the recording.</span></span>  <span data-ttu-id="2792d-179">この操作はスクラブとして参照され、アニメーションの進行状況を手動で分析するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2792d-179">The action is referenced as scrubbing, and it is useful for manually analyzing the progression of animations.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="記録の2500ms マークの周りのページのスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       <span data-ttu-id="2792d-181">記録の2500ms マークの周りのページのスクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="2792d-181">View a screenshot of the page around the 2500ms mark of the recording</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2792d-182">[ **フレーム** ] セクションで、緑色の四角形のいずれかにマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="2792d-182">In the **Frames** section, hover on one of the green squares.</span></span>  <span data-ttu-id="2792d-183">DevTools には、特定のフレームの FPS が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-183">DevTools shows you the FPS for that particular frame.</span></span>  <span data-ttu-id="2792d-184">各フレームは、60 FPS のターゲットよりも適切な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2792d-184">Each frame is probably well below the target of 60 FPS.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="フレーム上にカーソルを移動する" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       <span data-ttu-id="2792d-186">フレーム上にカーソルを移動する</span><span class="sxs-lookup"><span data-stu-id="2792d-186">Hover on a frame</span></span>  
    :::image-end:::  
    
<span data-ttu-id="2792d-187">もちろん、ページが正常に動作していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2792d-187">Of course, you should see that the page is not performing well.</span></span>  <span data-ttu-id="2792d-188">実際のシナリオでは、このことが明確ではない可能性があるため、すべてのツールを使って測定を行うと便利です。</span><span class="sxs-lookup"><span data-stu-id="2792d-188">But in real scenarios, it may not be so clear, so having all of the tools to make measurements comes in handy.</span></span>  

#### <span data-ttu-id="2792d-189">ボーナス: FPS メーターを開く</span><span class="sxs-lookup"><span data-stu-id="2792d-189">Bonus: Open the FPS meter</span></span>  

<span data-ttu-id="2792d-190">もう1つの便利なツールは FPS メーターで、ページの実行時に FPS に対してリアルタイムの推定値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-190">Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.</span></span>  

1.  <span data-ttu-id="2792d-191">[ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選択して、**コマンドメニュー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="2792d-191">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="2792d-192">`Rendering`**コマンドメニュー**で入力を開始し、[**レンダリングの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2792d-192">Start typing `Rendering` in the **Command Menu** and select **Show Rendering**.</span></span>  
1.  <span data-ttu-id="2792d-193">[ **レンダリング** ] タブで、[ **FPS メーター**] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2792d-193">In the **Rendering** tab, enable **FPS Meter**.</span></span>  <span data-ttu-id="2792d-194">新しいオーバーレイがビューポートの右上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-194">A new overlay appears in the top-right of your viewport.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       <span data-ttu-id="2792d-196">**FPS メーター**</span><span class="sxs-lookup"><span data-stu-id="2792d-196">The **FPS meter**</span></span>  
        :::image-end:::  
    
1.  <span data-ttu-id="2792d-197">**FPS メーター**を無効にし、を選択して [ `Escape` **レンダリング**] タブを閉じます。 このチュートリアルでは、 **FPS メーター**は使用していません。</span><span class="sxs-lookup"><span data-stu-id="2792d-197">Disable the **FPS Meter** and select `Escape` to close the **Rendering** tab.  You are not using **FPS Meter** in this tutorial.</span></span>  
    
### <span data-ttu-id="2792d-198">ボトルネックを見つける</span><span class="sxs-lookup"><span data-stu-id="2792d-198">Find the bottleneck</span></span>  

<span data-ttu-id="2792d-199">アニメーションが適切に実行されていないことを測定して確認した後、次の手順は "理由" という質問に答えます。</span><span class="sxs-lookup"><span data-stu-id="2792d-199">After you measured and verified that the animation is not performing well, the next step is to answer the question "why?".</span></span>  

1.  <span data-ttu-id="2792d-200">イベントが選択されていない場合、[ **概要** ] タブにアクティビティの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-200">When no events are selected, the **Summary** tab shows you a breakdown of activity.</span></span>  <span data-ttu-id="2792d-201">このページでは、ほとんどの時間のレンダリングに費やされています。</span><span class="sxs-lookup"><span data-stu-id="2792d-201">The page spent most of the time rendering.</span></span>  <span data-ttu-id="2792d-202">パフォーマンスは、作業を軽減することを目的としているため、目標は、作業のレンダリングに費やされる時間を減らすことです。</span><span class="sxs-lookup"><span data-stu-id="2792d-202">Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text="[概要] タブ" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       <span data-ttu-id="2792d-204">[ **概要** ] タブ</span><span class="sxs-lookup"><span data-stu-id="2792d-204">The **Summary** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2792d-205">**メイン**セクションを展開する。</span><span class="sxs-lookup"><span data-stu-id="2792d-205">Expand the **Main** section.</span></span>  <span data-ttu-id="2792d-206">DevTools には、時間の経過に伴うメインスレッドでのアクティビティを示す炎のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-206">DevTools shows you a flame chart of activity on the main thread, over time.</span></span>  <span data-ttu-id="2792d-207">X 軸は、時間の経過に伴う記録を表します。</span><span class="sxs-lookup"><span data-stu-id="2792d-207">The x-axis represents the recording, over time.</span></span>  <span data-ttu-id="2792d-208">各バーはイベントを表します。</span><span class="sxs-lookup"><span data-stu-id="2792d-208">Each bar represents an event.</span></span>  <span data-ttu-id="2792d-209">広いバーは、イベントが長くなったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2792d-209">A wider bar means that event took longer.</span></span>  <span data-ttu-id="2792d-210">Y 軸は、呼び出しスタックを表します。</span><span class="sxs-lookup"><span data-stu-id="2792d-210">The y-axis represents the call stack.</span></span>  <span data-ttu-id="2792d-211">互いに重なり合っているイベントが表示される場合は、上位のイベントによって下位のイベントが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2792d-211">When you see events stacked on top of each other, it means the upper events caused the lower events.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="メインセクション" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       <span data-ttu-id="2792d-213">**メイン**セクション</span><span class="sxs-lookup"><span data-stu-id="2792d-213">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2792d-214">レコーディングには大量のデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2792d-214">There is a lot of data in the recording.</span></span>  <span data-ttu-id="2792d-215">1つのイベントにズームするには[ **概要**] の上にカーソルを置くと、 **FPS**、 **CPU**、および **ネット** チャートが含まれているセクションになります。</span><span class="sxs-lookup"><span data-stu-id="2792d-215">To Zoom into a single event; choose, hold, and dragg your cursor over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="2792d-216">**メイン**セクションと [**概要**] タブには、レコーディングの選択した部分に関する情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-216">The **Main** section and **Summary** tab only display information for the selected portion of the recording.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="イベントを拡大する" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       <span data-ttu-id="2792d-218">イベントを拡大する</span><span class="sxs-lookup"><span data-stu-id="2792d-218">Zoom into an event</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="2792d-219">ズームするもう1つの方法として、 **メイン** セクションにフォーカスを移動し、背景またはイベントを選択して、、、、またはを選択し `W` `A` `S` `D` ます。</span><span class="sxs-lookup"><span data-stu-id="2792d-219">Another way to zoom, focus the **Main** section, choose the background or an event, and select `W`, `A`, `S`, or `D`.</span></span>  
    
    1.  <span data-ttu-id="2792d-220">**アニメーションフレームの発生**イベントの右上にある赤い三角形にフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2792d-220">Focus on the red triangle in the top-right of the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="2792d-221">赤い三角形が表示されると、イベントに関連する問題が発生している可能性があることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-221">Whenever you see a red triangle, it is a warning that there may be an issue related to the event.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="2792d-222">[ `requestAnimationFrame()` コールバック][MDNWebRequestAnimationFrame]が実行されるたびに、**アニメーションフレームの発生**イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="2792d-222">The **Animation Frame Fired** event occurs whenever a [`requestAnimationFrame()` callback][MDNWebRequestAnimationFrame] is run.</span></span>  
    
1.  <span data-ttu-id="2792d-223">[ **Animation Frame** ] イベントを選びます。</span><span class="sxs-lookup"><span data-stu-id="2792d-223">Choose the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="2792d-224">[ **概要** ] タブに、そのイベントに関する情報が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2792d-224">The **Summary** tab now shows you information about that event.</span></span>  <span data-ttu-id="2792d-225">[ **公開** ] リンクに注目してください。</span><span class="sxs-lookup"><span data-stu-id="2792d-225">Note the **Reveal** link.</span></span>  <span data-ttu-id="2792d-226">このツールを選ぶと、 **アニメーションフレームの発生** イベントを開始したイベントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-226">After you choose it, DevTools to highlights the event that initiated the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="2792d-227">また、 **app.js:95** のリンクに注目してください。</span><span class="sxs-lookup"><span data-stu-id="2792d-227">Also, focus on the **app.js:95** link.</span></span>  <span data-ttu-id="2792d-228">選択すると、ソースコードの該当する行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-228">After you choose it, the relevant line in the source code is displayed.</span></span>
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="アニメーションフレームの発生イベントに関する詳細情報" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       <span data-ttu-id="2792d-230">**アニメーションフレームの発生**イベントに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="2792d-230">More information about the **Animation Frame Fired** event</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="2792d-231">イベントを選択した後、方向キーを使用してイベントの隣にあるイベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="2792d-231">After selecting an event, use the arrow keys to select the events next to it.</span></span>  
    
1.  <span data-ttu-id="2792d-232">[ **更新** ] イベントには、紫色のイベントがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="2792d-232">Under the **app.update** event, there is a bunch of purple events.</span></span>  <span data-ttu-id="2792d-233">紫色の各イベントの幅が広くなっている場合は、それぞれに赤い三角形が表示されているように見えます。</span><span class="sxs-lookup"><span data-stu-id="2792d-233">If each purple event was wider, it looks as though each one may have a red triangle on it.</span></span>  
1.  <span data-ttu-id="2792d-234">紫色の **レイアウト** イベントのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2792d-234">Choose one of the purple **Layout** events.</span></span>  <span data-ttu-id="2792d-235">DevTools は、[ **概要** ] タブのイベントに関する詳細情報を提供します。 実際には、強制的な折り返しの折り返し (別の word レイアウト \) に関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-235">DevTools provides more information about the event in the **Summary** tab.  Indeed, there is a warning about forced reflows \(another word for layout\).</span></span>  
    
1.  <span data-ttu-id="2792d-236">[**概要**] タブで、[**強制的にレイアウト**] の [ **app.js:71** ] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="2792d-236">In the **Summary** tab, choose the **app.js:71** link under **Layout Forced**.</span></span>  <span data-ttu-id="2792d-237">DevTools は、レイアウトを強制したコード行に移動します。</span><span class="sxs-lookup"><span data-stu-id="2792d-237">DevTools takes you to the line of code that forced the layout.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="強制レイアウトの原因となったコード行" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       <span data-ttu-id="2792d-239">強制レイアウトの原因となったコード行</span><span class="sxs-lookup"><span data-stu-id="2792d-239">The line of code that caused the forced layout</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="2792d-240">コードに問題がある場合は、各アニメーションフレームで、各アイコンのスタイルを変更してから、ページ上の各アイコンの位置を照会します。</span><span class="sxs-lookup"><span data-stu-id="2792d-240">The problem with the code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.</span></span>  <span data-ttu-id="2792d-241">スタイルが変更されているため、各アイコンの位置が変更されたかどうかはブラウザーで認識されないため、新しい位置を計算するにはアイコンを再レイアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2792d-241">Because the styles changed, the browser does not know if each icon position changed, so it has to re-layout the icon in order to compute the new position.</span></span>  <!--  > See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->
    
<!-- todo: add layouts section when available -->

<span data-ttu-id="2792d-242">もっと学ぶことができました。</span><span class="sxs-lookup"><span data-stu-id="2792d-242">That was a lot to learn.</span></span>  <span data-ttu-id="2792d-243">これで、実行時のパフォーマンスを分析するための基本的なワークフローの堅固な基盤ができます。</span><span class="sxs-lookup"><span data-stu-id="2792d-243">You now have a solid foundation in the basic workflow for analyzing runtime performance.</span></span>  <span data-ttu-id="2792d-244">よく出来ました。</span><span class="sxs-lookup"><span data-stu-id="2792d-244">Good job.</span></span>  

### <span data-ttu-id="2792d-245">ボーナス: 最適化されたバージョンを分析する</span><span class="sxs-lookup"><span data-stu-id="2792d-245">Bonus: Analyze the optimized version</span></span>  

<span data-ttu-id="2792d-246">学習したワークフローとツールを使用して、最適化されたコードを有効にし、別のパフォーマンスの記録を取ることで、結果を分析するデモで [ **最適化** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2792d-246">Using the workflows and tools that you just learned, choose **Optimize** on the demo to enable the optimized code, take another performance recording, and then analyze the results.</span></span>  <span data-ttu-id="2792d-247">向上したフレームレートから、 **メイン** セクションの炎グラフのイベントの減少まで、アプリの最適化されたバージョンの動作が大幅に低下し、パフォーマンスが向上することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2792d-247">From the improved framerate to the reduction in events in the flame chart in the **Main** section, you are able to see that the optimized version of the app does much less work, resulting in better performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="2792d-248">最適化されたバージョンでも、 `top` すべてのアイコンのプロパティを操作するため、最適な方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="2792d-248">Even the optimized version is not great, because it manipulates the `top` property of every icon.</span></span>  <span data-ttu-id="2792d-249">さらに良い方法は、合成にのみ適用されるプロパティにすることです。</span><span class="sxs-lookup"><span data-stu-id="2792d-249">A better approach is to stick to properties that only affect compositing.</span></span>  <!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## <span data-ttu-id="2792d-250">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2792d-250">Next steps</span></span>

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

<span data-ttu-id="2792d-251">[パフォーマンス] パネルを使いやすくするために、練習は完璧です。</span><span class="sxs-lookup"><span data-stu-id="2792d-251">To get more comfortable with the Performance panel, practice makes perfect.</span></span>  <span data-ttu-id="2792d-252">ページのプロファイリングを行って、結果を分析してみてください。</span><span class="sxs-lookup"><span data-stu-id="2792d-252">Try profiling your pages and analyzing the results.</span></span>  <span data-ttu-id="2792d-253">結果についての質問がある場合は、[**フィードバックの送信**] アイコンを使用して、[ `Alt` + `Shift` + `I` \ (Windows \)]、[ `Option` + `Shift` + `I` \ (macOS \)]、または [ [devtools] チームにツイート][TwitterEdgeDevtools]します。</span><span class="sxs-lookup"><span data-stu-id="2792d-253">If you have any questions about your results, use the **Send Feedback** icon, select `Alt`+`Shift`+`I` \(Windows\), select `Option`+`Shift`+`I` \(macOS\), or [tweet the DevTools team][TwitterEdgeDevtools].</span></span>  <span data-ttu-id="2792d-254">可能であれば、スクリーンショットまたは再現可能なページへのリンクを含めます。</span><span class="sxs-lookup"><span data-stu-id="2792d-254">Include screenshots or links to reproducible pages, if possible.</span></span>  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="Microsoft Edge DevTools の \* \* フィードバック \* \* アイコン" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   <span data-ttu-id="2792d-256">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="2792d-256">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

<span data-ttu-id="2792d-257">最後に、実行時のパフォーマンスを向上させるためのさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="2792d-257">Last, there are many ways to improve runtime performance.</span></span>  <span data-ttu-id="2792d-258">この記事では、特定のアニメーションのボトルネックに焦点を絞って、パフォーマンスパネルの焦点を絞ったツアーを提供していますが、これは、発生する可能性のある多数のボトルネックの1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="2792d-258">This article focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.</span></span>  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

<!-- links -->

[DevtoolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Microsoft Edge DevTools を使用して Web サイトの速度を最適化する"  

[TwitterEdgeDevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "EdgeDevTools-ツイートの投稿 |Twitter"  

[MDNWebRequestAnimationFrame]: https://developer.mozilla.org/docs/Web/API/window/requestAnimationFrame "Window./アニメーションフレーム \ (\) |MDN"  

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
> <span data-ttu-id="2792d-263">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="2792d-263">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2792d-264">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="2792d-264">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="2792d-266">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="2792d-266">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
