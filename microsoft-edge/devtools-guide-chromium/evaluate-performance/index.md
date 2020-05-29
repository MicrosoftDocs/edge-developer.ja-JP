---
title: 実行時のパフォーマンスの分析を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bff2d2fb0ff8424303289183ca8c5935ef477381
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611742"
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







# <span data-ttu-id="681e4-103">実行時のパフォーマンスの分析を開始する</span><span class="sxs-lookup"><span data-stu-id="681e4-103">Get Started With Analyzing Runtime Performance</span></span>   



> [!NOTE]
> <span data-ttu-id="681e4-104">ページを読みやすくする方法については、「 [Web サイトの速度を最適化][DevtoolsSpeedGetStarted]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="681e4-104">See [Optimize Website Speed][DevtoolsSpeedGetStarted] to learn how to make your pages load faster.</span></span>  

<span data-ttu-id="681e4-105">実行時のパフォーマンスは、読み込みとは異なり、ページが実行されている場合の実行方法です。</span><span class="sxs-lookup"><span data-stu-id="681e4-105">Runtime performance is how your page performs when it is running, as opposed to loading.</span></span>  <span data-ttu-id="681e4-106">このチュートリアルでは、Microsoft Edge DevTools のパフォーマンスパネルを使って実行時のパフォーマンスを分析する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="681e4-106">This tutorial teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.</span></span>  <span data-ttu-id="681e4-107">このチュートリアルで学習するスキル**は、ページ**の応答、アニメーション、およびアイドルフェーズを分析するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="681e4-107">In terms of the **RAIL** model, the skills you learn in this tutorial are useful for analyzing the Response, Animation, and Idle phases of your page.</span></span>  

<!--todo: add rail link when section is ready -->  

## <span data-ttu-id="681e4-108">使ってみる</span><span class="sxs-lookup"><span data-stu-id="681e4-108">Get started</span></span>   

<span data-ttu-id="681e4-109">このチュートリアルでは、ライブページで DevTools を開き、[パフォーマンス] パネルを使用して、ページ上のパフォーマンスのボトルネックを見つけます。</span><span class="sxs-lookup"><span data-stu-id="681e4-109">In this tutorial, you open DevTools on a live page and use the Performance panel to find a performance bottleneck on the page.</span></span>  

1.  <span data-ttu-id="681e4-110">**InPrivate モード**で Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="681e4-110">Open Microsoft Edge in **InPrivate Mode**.</span></span>  <span data-ttu-id="681e4-111">InPrivate モードでは、Microsoft Edge がクリーンな状態で実行されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-111">InPrivate Mode ensures that Microsoft Edge runs in a clean state.</span></span>  <span data-ttu-id="681e4-112">たとえば、多くの拡張機能がインストールされている場合は、これらの拡張機能によってパフォーマンスの測定値にノイズが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="681e4-112">For example, if you have a lot of extensions installed, those extensions might create noise in your performance measurements.</span></span>  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  <span data-ttu-id="681e4-113">InPrivate ウィンドウに次のページを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="681e4-113">Load the following page in your InPrivate window.</span></span>  <span data-ttu-id="681e4-114">このデモでは、プロファイルを作成しています。</span><span class="sxs-lookup"><span data-stu-id="681e4-114">This is the demo that you're going to profile.</span></span>  <span data-ttu-id="681e4-115">ページには、上下に移動する小さなアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-115">The page shows a bunch of little icons moving up and down.</span></span>  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/jank/
    ```  
    
1.  <span data-ttu-id="681e4-116">[ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を押して、devtools を開きます。</span><span class="sxs-lookup"><span data-stu-id="681e4-116">Press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.</span></span>  
    
    > ###### <span data-ttu-id="681e4-117">図 1</span><span class="sxs-lookup"><span data-stu-id="681e4-117">Figure 1</span></span>  
    > <span data-ttu-id="681e4-118">左側のデモと、右側の DevTools</span><span class="sxs-lookup"><span data-stu-id="681e4-118">The demo on the left, and DevTools on the right</span></span>  
    > ![左側のデモと、右側の DevTools][ImageGetStarted]  
    
    > [!NOTE]
    > <span data-ttu-id="681e4-120">このスクリーンショットの残りの部分については、「DevTools [」が別のウィンドウにドッキング][DevtoolsCustomizePlacement]されていないため、内容をより詳しく確認できます。</span><span class="sxs-lookup"><span data-stu-id="681e4-120">For the rest of the screenshots, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] so that you can see the contents better.</span></span>  
    
### <span data-ttu-id="681e4-121">モバイル CPU のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="681e4-121">Simulate a mobile CPU</span></span>  

<span data-ttu-id="681e4-122">モバイルデバイスは、デスクトップとノート pc よりも CPU の消費電力が非常に少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="681e4-122">Mobile devices have much less CPU power than desktops and laptops.</span></span>  <span data-ttu-id="681e4-123">ページをプロファイルするたびに、CPU 調整を使って、ページがモバイルデバイスでどのように動作するかをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="681e4-123">Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.</span></span>  

1.  <span data-ttu-id="681e4-124">DevTools で、[**パフォーマンス**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="681e4-124">In DevTools, click the **Performance** tab.</span></span>  
1.  <span data-ttu-id="681e4-125">[**スクリーンショット**] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="681e4-125">Make sure that the **Screenshots** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="681e4-126">「**キャプチャ設定**」「 ![ キャプチャ設定」をクリックし ][ImageCaptureSettingsIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="681e4-126">Click **Capture Settings** ![Capture Settings][ImageCaptureSettingsIcon].</span></span>  <span data-ttu-id="681e4-127">DevTools は、パフォーマンス指標のキャプチャに関連する設定を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="681e4-127">DevTools reveals settings related to how it captures performance metrics.</span></span>  
1.  <span data-ttu-id="681e4-128">**CPU**の場合は、[ **4 倍速減速**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="681e4-128">For **CPU**, select **4x slowdown**.</span></span>  <span data-ttu-id="681e4-129">DevTools では、CPU が通常より4倍遅くなるように CPU を調整します。</span><span class="sxs-lookup"><span data-stu-id="681e4-129">DevTools throttles your CPU so that it is 4 times slower than usual.</span></span>  
    
    > ###### <span data-ttu-id="681e4-130">図 2</span><span class="sxs-lookup"><span data-stu-id="681e4-130">Figure 2</span></span>  
    > <span data-ttu-id="681e4-131">CPU 調整</span><span class="sxs-lookup"><span data-stu-id="681e4-131">CPU throttling</span></span>  
    > ![CPU 調整][ImageCPUThrottling]  
    
    > [!NOTE]
    > <span data-ttu-id="681e4-133">他のページをテストする場合、ローエンドのモバイルデバイスで正常に動作することを確認するには、CPU の調整を**6x の遅延**に設定します。</span><span class="sxs-lookup"><span data-stu-id="681e4-133">When testing other pages, if you want to ensure that they work well on low-end mobile devices, set CPU Throttling to **6x slowdown**.</span></span>  <span data-ttu-id="681e4-134">このデモは、6x の速度ではうまく機能しません。そのため、説明のために4倍速の速度を使います。</span><span class="sxs-lookup"><span data-stu-id="681e4-134">This demo doesn't work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.</span></span>  
    
### <span data-ttu-id="681e4-135">デモを設定する</span><span class="sxs-lookup"><span data-stu-id="681e4-135">Set up the demo</span></span>  

<span data-ttu-id="681e4-136">この web サイトのすべてのリーダーで一貫して動作するランタイムパフォーマンスデモを作成するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="681e4-136">It is hard to create a runtime performance demo that works consistently for all readers of this website.</span></span>  <span data-ttu-id="681e4-137">このセクションでは、特定のセットアップに関係なく、デモをカスタマイズして、このチュートリアルで説明しているスクリーンショットと説明との一貫性を保つことができます。</span><span class="sxs-lookup"><span data-stu-id="681e4-137">This section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions you see in this tutorial, regardless of your particular setup.</span></span>

1.  <span data-ttu-id="681e4-138">青色のアイコンが以前よりも著しく遅くなるまで、[ **10 を追加**] をクリックしたままにします。</span><span class="sxs-lookup"><span data-stu-id="681e4-138">Keep clicking **Add 10** until the blue icons move noticeably slower than before.</span></span>  <span data-ttu-id="681e4-139">ハイエンドのコンピューターでは、20回のクリックがかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="681e4-139">On a high-end machine, it may take about 20 clicks.</span></span>  
1.  <span data-ttu-id="681e4-140">[**最適化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="681e4-140">Click **Optimize**.</span></span>  <span data-ttu-id="681e4-141">青いアイコンが速く、スムーズに移動します。</span><span class="sxs-lookup"><span data-stu-id="681e4-141">The blue icons should move faster and more smoothly.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="681e4-142">最適化されたバージョンと最適化されていないバージョンの違いがはっきりしない場合は、[ **10 回減算**] をクリックして、もう一度試してみてください。</span><span class="sxs-lookup"><span data-stu-id="681e4-142">If you don't see a noticeable difference between the optimized and un-optimized versions, try clicking **Subtract 10** a few times and trying again.</span></span>  
    > <span data-ttu-id="681e4-143">追加した青色のアイコンが多すぎる場合は、CPU を最大にするだけで、2つのバージョンの結果に大きな違いが表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="681e4-143">If you add too many blue icons, you're just going to max out the CPU and you're not going to see a major difference in the results for the two versions.</span></span>  

1.  <span data-ttu-id="681e4-144">[**最適化の取り消し**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="681e4-144">Click **Un-Optimize**.</span></span>  <span data-ttu-id="681e4-145">青いアイコンは遅くなり、さらに jank が増えます。</span><span class="sxs-lookup"><span data-stu-id="681e4-145">The blue icons move slower and with more jank again.</span></span>  

### <span data-ttu-id="681e4-146">実行時のパフォーマンスを記録する</span><span class="sxs-lookup"><span data-stu-id="681e4-146">Record runtime performance</span></span>   

<span data-ttu-id="681e4-147">最適化されたバージョンのページを実行すると、青色のアイコンが速く移動します。</span><span class="sxs-lookup"><span data-stu-id="681e4-147">When you ran the optimized version of the page, the blue icons move faster.</span></span>  
<span data-ttu-id="681e4-148">それはどうしてですか。</span><span class="sxs-lookup"><span data-stu-id="681e4-148">Why is that?</span></span>  <span data-ttu-id="681e4-149">どちらのバージョンでも、同じ時間の間隔でアイコンを移動することが想定されています。</span><span class="sxs-lookup"><span data-stu-id="681e4-149">Both versions are supposed to move the icons the same amount of space in the same amount of time.</span></span>  <span data-ttu-id="681e4-150">最適化されていないバージョンのパフォーマンスのボトルネックを検出する方法については、パフォーマンスパネルで記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="681e4-150">Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.</span></span>  

1.  <span data-ttu-id="681e4-151">DevTools で、[**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="681e4-151">In DevTools, click **Record** ![Record][ImageRecordIcon].</span></span>  
    <span data-ttu-id="681e4-152">DevTools は、ページが実行されたときにパフォーマンスのメトリックをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="681e4-152">DevTools captures performance metrics as the page runs.</span></span>  
    
    > ###### <span data-ttu-id="681e4-153">図 3</span><span class="sxs-lookup"><span data-stu-id="681e4-153">Figure 3</span></span> 
    > <span data-ttu-id="681e4-154">ページのプロファイリング</span><span class="sxs-lookup"><span data-stu-id="681e4-154">Profiling the page</span></span>  
    > ![ページのプロファイリング][ImagePageProfiling]  
    
1.  <span data-ttu-id="681e4-156">数秒待ってください。</span><span class="sxs-lookup"><span data-stu-id="681e4-156">Wait a few seconds.</span></span>  
1.  <span data-ttu-id="681e4-157">[**停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="681e4-157">Click **Stop**.</span></span>  <span data-ttu-id="681e4-158">DevTools は記録を停止し、データを処理して、パフォーマンスパネルに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="681e4-158">DevTools stops recording, processes the data, then displays the results on the Performance panel.</span></span>  
    
    > ###### <span data-ttu-id="681e4-159">図 4</span><span class="sxs-lookup"><span data-stu-id="681e4-159">Figure 4</span></span>  
    > <span data-ttu-id="681e4-160">プロファイルの結果</span><span class="sxs-lookup"><span data-stu-id="681e4-160">The results of the profile</span></span>  
    > ![プロファイルの結果][ImageProfileResults]  

<span data-ttu-id="681e4-162">これは、データ量が圧倒的であるということです。</span><span class="sxs-lookup"><span data-stu-id="681e4-162">Wow, that is an overwhelming amount of data.</span></span>  <span data-ttu-id="681e4-163">ご安心ください。すぐに、すべての意味がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="681e4-163">Don't worry, it'll all make more sense shortly.</span></span>  

## <span data-ttu-id="681e4-164">結果を分析する</span><span class="sxs-lookup"><span data-stu-id="681e4-164">Analyze the results</span></span>   

<span data-ttu-id="681e4-165">ページのパフォーマンスの記録が完了したら、ページのパフォーマンスの低下を測定して、何かの原因を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="681e4-165">Once you've got a recording the performance of the page, you can measure how poor the performance of the page is, and find the any causes.</span></span>  

### <span data-ttu-id="681e4-166">1秒あたりのフレーム数の分析</span><span class="sxs-lookup"><span data-stu-id="681e4-166">Analyze frames per second</span></span>  

<span data-ttu-id="681e4-167">アニメーションのパフォーマンスを測定するための主な指標は、1秒あたりのフレーム数 (FPS) です。</span><span class="sxs-lookup"><span data-stu-id="681e4-167">The main metric for measuring the performance of any animation is frames per second \(FPS\).</span></span>  <span data-ttu-id="681e4-168">アニメーションが 60 FPS で実行されている場合は、ユーザーが満足しています。</span><span class="sxs-lookup"><span data-stu-id="681e4-168">Users are happy when animations run at 60 FPS.</span></span>  

1.  <span data-ttu-id="681e4-169">**FPS**グラフを確認します。</span><span class="sxs-lookup"><span data-stu-id="681e4-169">Look at the **FPS** chart.</span></span>  <span data-ttu-id="681e4-170">**FPS**の上に赤色のバーが表示されている場合は、ユーザーエクスペリエンスが損なわれる可能性が低いため、フレームレートが低下していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="681e4-170">Whenever you see a red bar above **FPS**, it means that the framerate dropped so low that it is probably harming the user experience.</span></span>  <span data-ttu-id="681e4-171">一般に、緑色のバーが大きくなるほど、FPS は高くなります。</span><span class="sxs-lookup"><span data-stu-id="681e4-171">In general, the higher the green bar, the higher the FPS.</span></span>  
    
    > ###### <span data-ttu-id="681e4-172">図 5</span><span class="sxs-lookup"><span data-stu-id="681e4-172">Figure 5</span></span>  
    > <span data-ttu-id="681e4-173">FPS グラフ</span><span class="sxs-lookup"><span data-stu-id="681e4-173">The FPS chart</span></span>  
    > ![FPS グラフ][ImageFPSChart]  

1.  <span data-ttu-id="681e4-175">**FPS**グラフの下には、 **CPU**グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-175">Below the **FPS** chart you see the **CPU** chart.</span></span>  <span data-ttu-id="681e4-176">**CPU**グラフの色は、[パフォーマンス] パネルの下部にある [**概要**] タブの色に対応しています。</span><span class="sxs-lookup"><span data-stu-id="681e4-176">The colors in the **CPU** chart correspond to the colors in the **Summary** tab, at the bottom of the Performance panel.</span></span>  <span data-ttu-id="681e4-177">**Cpu**グラフが色がいっぱいになっているということは、記録中に cpu が最大化されていたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="681e4-177">The fact that the **CPU** chart is full of color means that the CPU was maxed out during the recording.</span></span>  <span data-ttu-id="681e4-178">長期間にわたって CPU が不足している場合は、作業を軽減する方法を見つけるための手掛かりとなります。</span><span class="sxs-lookup"><span data-stu-id="681e4-178">Whenever you see the CPU maxed out for long periods, it is a cue to find ways to do less work.</span></span>  
    
    > ###### <span data-ttu-id="681e4-179">図 6</span><span class="sxs-lookup"><span data-stu-id="681e4-179">Figure 6</span></span>  
    > <span data-ttu-id="681e4-180">[CPU グラフ] と [概要] タブ</span><span class="sxs-lookup"><span data-stu-id="681e4-180">The CPU chart and Summary tab</span></span>  
    > ![[CPU グラフ] と [概要] タブ][ImageCPUSummary]  

1.  <span data-ttu-id="681e4-182">**FPS**、 **CPU**、または**ネット**チャートの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="681e4-182">Hover your mouse over the **FPS**, **CPU**, or **NET** charts.</span></span>  <span data-ttu-id="681e4-183">[DevTools] は、現時点でのページのスクリーンショットを示します。</span><span class="sxs-lookup"><span data-stu-id="681e4-183">DevTools shows a screenshot of the page at that point in time.</span></span>  <span data-ttu-id="681e4-184">マウスを左または右に移動して、記録を再生します。</span><span class="sxs-lookup"><span data-stu-id="681e4-184">Move your mouse left and right to replay the recording.</span></span>  <span data-ttu-id="681e4-185">これはスクラブと呼ばれ、アニメーションの進行状況を手動で分析するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="681e4-185">This is called scrubbing, and it is useful for manually analyzing the progression of animations.</span></span>  
    
    > ###### <span data-ttu-id="681e4-186">図 7</span><span class="sxs-lookup"><span data-stu-id="681e4-186">Figure 7</span></span>  
    > <span data-ttu-id="681e4-187">記録の2500ms マークの周りのページのスクリーンショットを表示する</span><span class="sxs-lookup"><span data-stu-id="681e4-187">Viewing a screenshot of the page around the 2500ms mark of the recording</span></span>  
    > ![記録の2500ms マークの周りのページのスクリーンショットを表示する][ImageViewingScreenshot]  

1.  <span data-ttu-id="681e4-189">[**フレーム**] セクションで、緑色の四角形のいずれかにマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="681e4-189">In the **Frames** section, hover your mouse over one of the green squares.</span></span>  <span data-ttu-id="681e4-190">DevTools には、特定のフレームの FPS が表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-190">DevTools shows you the FPS for that particular frame.</span></span>  <span data-ttu-id="681e4-191">各フレームは、60 FPS のターゲットよりも適切な場合があります。</span><span class="sxs-lookup"><span data-stu-id="681e4-191">Each frame is probably well below the target of 60 FPS.</span></span>  
    
    > ###### <span data-ttu-id="681e4-192">図 8</span><span class="sxs-lookup"><span data-stu-id="681e4-192">Figure 8</span></span>  
    > <span data-ttu-id="681e4-193">フレーム上のマウスポインター</span><span class="sxs-lookup"><span data-stu-id="681e4-193">Hovering over a frame</span></span>  
    > ![フレーム上のマウスポインター][ImageFrameHover]  

<span data-ttu-id="681e4-195">もちろん、このデモでは、ページが適切に動作していないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="681e4-195">Of course, with this demo, it is pretty obvious that the page is not performing well.</span></span>  <span data-ttu-id="681e4-196">実際のシナリオでは、このことが明確ではない場合もあります。そのため、これらのすべてのツールを使って測定を行うと便利です。</span><span class="sxs-lookup"><span data-stu-id="681e4-196">But in real scenarios, it may not be so clear, so having all of these tools to make measurements comes in handy.</span></span>  

#### <span data-ttu-id="681e4-197">ボーナス: FPS メーターを開く</span><span class="sxs-lookup"><span data-stu-id="681e4-197">Bonus: Open the FPS meter</span></span>  

<span data-ttu-id="681e4-198">もう1つの便利なツールは FPS メーターで、ページの実行時に FPS に対してリアルタイムの推定値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-198">Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.</span></span>  

1.  <span data-ttu-id="681e4-199">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="681e4-199">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="681e4-200">`Rendering`コマンドメニューで入力を開始し、[**レンダリングの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="681e4-200">Start typing `Rendering` in the Command Menu and select **Show Rendering**.</span></span>  
1.  <span data-ttu-id="681e4-201">[**レンダリング**] タブで、[ **FPS メーター**] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="681e4-201">In the **Rendering** tab, enable **FPS Meter**.</span></span>  <span data-ttu-id="681e4-202">新しいオーバーレイがビューポートの右上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-202">A new overlay appears in the top-right of your viewport.</span></span>  
    
    > ###### <span data-ttu-id="681e4-203">図 9</span><span class="sxs-lookup"><span data-stu-id="681e4-203">Figure 9</span></span>  
    > <span data-ttu-id="681e4-204">FPS メーター</span><span class="sxs-lookup"><span data-stu-id="681e4-204">The FPS meter</span></span>  
    > ![FPS メーター][ImageFPSMeter]  

1.  <span data-ttu-id="681e4-206">**FPS メーター**を無効にし、を押して [ `Escape` **レンダリング**] タブを閉じます。 このチュートリアルでは使用しません。</span><span class="sxs-lookup"><span data-stu-id="681e4-206">Disable the **FPS Meter** and press `Escape` to close the **Rendering** tab.  You won't be using it in this tutorial.</span></span>  

### <span data-ttu-id="681e4-207">ボトルネックを見つける</span><span class="sxs-lookup"><span data-stu-id="681e4-207">Find the bottleneck</span></span>  

<span data-ttu-id="681e4-208">これで、アニメーションが正常に動作していないことを測定し、確認しました。次に、その理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="681e4-208">Now that you've measured and verified that the animation is not performing well, the next question to answer is:  why?</span></span>  

1.  <span data-ttu-id="681e4-209">[概要] タブに注目してください。 イベントが選択されていない場合、このタブにはアクティビティの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-209">Note the summary tab.  When no events are selected, this tab shows you a breakdown of activity.</span></span>  <span data-ttu-id="681e4-210">このページでは、ほとんどの時間のレンダリングに費やされています。</span><span class="sxs-lookup"><span data-stu-id="681e4-210">The page spent most of its time rendering.</span></span>  <span data-ttu-id="681e4-211">パフォーマンスは、作業を軽減することを目的としているため、目標は、作業のレンダリングに費やされる時間を減らすことです。</span><span class="sxs-lookup"><span data-stu-id="681e4-211">Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.</span></span>  
    
    > ###### <span data-ttu-id="681e4-212">図 10</span><span class="sxs-lookup"><span data-stu-id="681e4-212">Figure 10</span></span>  
    > <span data-ttu-id="681e4-213">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="681e4-213">The Summary tab</span></span>  
    > ![[概要] タブ][ImageSummaryTab]  

1.  <span data-ttu-id="681e4-215">**メイン**セクションを展開する。</span><span class="sxs-lookup"><span data-stu-id="681e4-215">Expand the **Main** section.</span></span>  <span data-ttu-id="681e4-216">DevTools には、時間の経過に伴うメインスレッドでのアクティビティを示す炎のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-216">DevTools shows you a flame chart of activity on the main thread, over time.</span></span>  <span data-ttu-id="681e4-217">X 軸は、時間の経過に伴う記録を表します。</span><span class="sxs-lookup"><span data-stu-id="681e4-217">The x-axis represents the recording, over time.</span></span>  <span data-ttu-id="681e4-218">各バーはイベントを表します。</span><span class="sxs-lookup"><span data-stu-id="681e4-218">Each bar represents an event.</span></span>  <span data-ttu-id="681e4-219">広いバーは、イベントが長くなったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="681e4-219">A wider bar means that event took longer.</span></span>  <span data-ttu-id="681e4-220">Y 軸は、呼び出しスタックを表します。</span><span class="sxs-lookup"><span data-stu-id="681e4-220">The y-axis represents the call stack.</span></span>  <span data-ttu-id="681e4-221">互いに重なり合っているイベントが表示される場合は、上位のイベントによって下位のイベントが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="681e4-221">When you see events stacked on top of each other, it means the upper events caused the lower events.</span></span>  
    
    > ##### <span data-ttu-id="681e4-222">図 11</span><span class="sxs-lookup"><span data-stu-id="681e4-222">Figure 11</span></span>  
    > <span data-ttu-id="681e4-223">メインセクション</span><span class="sxs-lookup"><span data-stu-id="681e4-223">The Main section</span></span>  
    > ![メインセクション][ImageMainSection]  

1.  <span data-ttu-id="681e4-225">レコーディングには大量のデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="681e4-225">There is a lot of data in the recording.</span></span>  <span data-ttu-id="681e4-226">1つのイベントを拡大表示するには、[**概要**] の上にマウスポインターを合わせてドラッグします。これは、 **FPS**、 **CPU**、および**NET**グラフを含むセクションです。</span><span class="sxs-lookup"><span data-stu-id="681e4-226">Zoom in on a single event by clicking, holding, and dragging your mouse over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="681e4-227">**メイン**セクションと [**概要**] タブには、レコーディングの選択した部分に関する情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-227">The **Main** section and **Summary** tab only display information for the selected portion of the recording.</span></span>  
    
    > ###### <span data-ttu-id="681e4-228">図 12</span><span class="sxs-lookup"><span data-stu-id="681e4-228">Figure 12</span></span>  
    > <span data-ttu-id="681e4-229">1つのイベントを拡大する</span><span class="sxs-lookup"><span data-stu-id="681e4-229">Zoomed in on a single event</span></span>  
    > ![イベントを拡大する][ImageZoomedAnimation]  
    
    > [!NOTE]
    > <span data-ttu-id="681e4-231">ズームするもう1つの方法は**Main** 、背景をクリックするかイベントを選択して、、、 `W` `A` `S` 、およびキーを押して、メインセクションにフォーカスを移動することです `D` 。</span><span class="sxs-lookup"><span data-stu-id="681e4-231">Another way to zoom is to focus the **Main** section by clicking its background or selecting an event, and then press the `W`, `A`, `S`, and `D` keys.</span></span>  
    
    1.  <span data-ttu-id="681e4-232">**アニメーションフレームの発生**イベントの右上にある赤い三角形に注目してください。</span><span class="sxs-lookup"><span data-stu-id="681e4-232">Note the red triangle in the top-right of the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="681e4-233">赤い三角形が表示された場合は、このイベントに関連する問題が発生している可能性があることを示す警告です。</span><span class="sxs-lookup"><span data-stu-id="681e4-233">Whenever you see a red triangle, it is a warning that there may be an issue related to this event.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="681e4-234">[ `requestAnimationFrame()` コールバック][MDNWebRequestAnimationFrame]が実行されるたびに、**アニメーションフレームの発生**イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="681e4-234">The **Animation Frame Fired** event occurs whenever a [`requestAnimationFrame()` callback][MDNWebRequestAnimationFrame] is run.</span></span>  
    
1.  <span data-ttu-id="681e4-235">[ **Animation Frame** ] イベントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="681e4-235">Click the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="681e4-236">[**概要**] タブに、そのイベントに関する情報が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="681e4-236">The **Summary** tab now shows you information about that event.</span></span>  <span data-ttu-id="681e4-237">[**公開**] リンクに注目してください。</span><span class="sxs-lookup"><span data-stu-id="681e4-237">Note the **Reveal** link.</span></span>  <span data-ttu-id="681e4-238">このボタンをクリックすると、DevTools によって、**アニメーションフレームの発生**イベントを開始したイベントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-238">Clicking that causes DevTools to highlight the event that initiated the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="681e4-239">また、 **「.js:95** 」というリンクも確認してください。</span><span class="sxs-lookup"><span data-stu-id="681e4-239">Also note the **app.js:95** link.</span></span>  <span data-ttu-id="681e4-240">これをクリックすると、ソースコード内の関連する行にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="681e4-240">Clicking that jumps you to the relevant line in the source code.</span></span>
    
    > ##### <span data-ttu-id="681e4-241">図 13</span><span class="sxs-lookup"><span data-stu-id="681e4-241">Figure 13</span></span>  
    > <span data-ttu-id="681e4-242">アニメーションフレームの発生イベントに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="681e4-242">More information about the Animation Frame Fired event</span></span>  
    > ![アニメーションフレームの発生イベントに関する詳細情報][ImageAnimationFrameFired]  
    
    > [!NOTE]
    > <span data-ttu-id="681e4-244">イベントを選択した後、方向キーを使用してイベントの隣にあるイベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="681e4-244">After selecting an event, use the arrow keys to select the events next to it.</span></span>  

1.  <span data-ttu-id="681e4-245">[**更新**] イベントには、紫色のイベントがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="681e4-245">Under the **app.update** event, there is a bunch of purple events.</span></span>  <span data-ttu-id="681e4-246">幅が広くなっている場合は、それぞれに赤い三角形が表示されているように見えます。</span><span class="sxs-lookup"><span data-stu-id="681e4-246">If they were wider, it looks as though each one might have a red triangle on it.</span></span>  <span data-ttu-id="681e4-247">ここで紫色の**レイアウト**イベントを1つクリックします。</span><span class="sxs-lookup"><span data-stu-id="681e4-247">Click one of the purple **Layout** events now.</span></span>  <span data-ttu-id="681e4-248">DevTools は、[**概要**] タブのイベントに関する詳細情報を提供します。 実際には、強制的な折り返しの折り返し (別の word レイアウト \) に関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-248">DevTools provides more information about the event in the **Summary** tab.  Indeed, there is a warning about forced reflows \(another word for layout\).</span></span>  

1.  <span data-ttu-id="681e4-249">[**概要**] タブで、[**レイアウトの強制**] の下の [ **.js:71** ] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="681e4-249">In the **Summary** tab, click the **app.js:71** link under **Layout Forced**.</span></span>  <span data-ttu-id="681e4-250">DevTools は、レイアウトを強制したコード行に移動します。</span><span class="sxs-lookup"><span data-stu-id="681e4-250">DevTools takes you to the line of code that forced the layout.</span></span>  
    
    > ##### <span data-ttu-id="681e4-251">図 14</span><span class="sxs-lookup"><span data-stu-id="681e4-251">Figure 14</span></span>  
    > <span data-ttu-id="681e4-252">強制レイアウトの原因となったコード行</span><span class="sxs-lookup"><span data-stu-id="681e4-252">The line of code that caused the forced layout</span></span>  
    > ![強制レイアウトの原因となったコード行][ImageForcedLayoutSRC]  
    
    > [!NOTE]
    > <span data-ttu-id="681e4-254">このコードの問題は、アニメーションフレームごとに、各アイコンのスタイルが変更され、ページ上の各アイコンの位置が照会されることです。</span><span class="sxs-lookup"><span data-stu-id="681e4-254">The problem with this code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.</span></span>  <span data-ttu-id="681e4-255">スタイルが変更されているため、各アイコンの位置が変更されたかどうかはブラウザーでは認識されないため、アイコンの位置を計算するには、アイコンのレイアウトを再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="681e4-255">Because the styles changed, the browser doesn't know if each icon position changed, so it has to re-layout the icon in order to compute its position.</span></span>  <!--  See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->

<!-- todo: add layouts section when available -->

<span data-ttu-id="681e4-256">Phew!</span><span class="sxs-lookup"><span data-stu-id="681e4-256">Phew!</span></span>  <span data-ttu-id="681e4-257">これは非常に多くのユーザーを対象としていますが、実行時のパフォーマンスを分析するための基本的なワークフローの基礎として確固としています。</span><span class="sxs-lookup"><span data-stu-id="681e4-257">That was a lot to take in, but you now have a solid foundation in the basic workflow for analyzing runtime performance.</span></span>  <span data-ttu-id="681e4-258">よく出来ました。</span><span class="sxs-lookup"><span data-stu-id="681e4-258">Good job.</span></span>  

### <span data-ttu-id="681e4-259">ボーナス: 最適化されたバージョンを分析する</span><span class="sxs-lookup"><span data-stu-id="681e4-259">Bonus: Analyze the optimized version</span></span>  

<span data-ttu-id="681e4-260">学習したワークフローとツールを使用して、最適化されたコードを有効にして、別のパフォーマンスの記録を取ることで、結果を分析するデモの [**最適化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="681e4-260">Using the workflows and tools that you just learned, click **Optimize** on the demo to enable the optimized code, take another performance recording, and then analyze the results.</span></span>  <span data-ttu-id="681e4-261">向上したフレームレートから、**メイン**セクションの炎グラフのイベントの減少まで、最適化されたバージョンのアプリの動作が大幅に低下することを確認できます。その結果、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="681e4-261">From the improved framerate to the reduction in events in the flame chart in the **Main** section, you can see that the optimized version of the app does much less work, resulting in better performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="681e4-262">この "最適化された" バージョンでも、 `top` 各アイコンのプロパティを操作しているので、それほど便利ではありません。</span><span class="sxs-lookup"><span data-stu-id="681e4-262">Even this "optimized" version isn't that great, because it still manipulates the `top` property of each icon.</span></span>  <span data-ttu-id="681e4-263">さらに良い方法は、合成にのみ適用されるプロパティにすることです。</span><span class="sxs-lookup"><span data-stu-id="681e4-263">A better approach is to stick to properties that only affect compositing.</span></span>  
<!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## <span data-ttu-id="681e4-264">次のステップ</span><span class="sxs-lookup"><span data-stu-id="681e4-264">Next steps</span></span>

<!--The foundation for understanding performance is the RAIL model.  This model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

<span data-ttu-id="681e4-265">[パフォーマンス] パネルを使いやすくするために、練習は完璧です。</span><span class="sxs-lookup"><span data-stu-id="681e4-265">To get more comfortable with the Performance panel, practice makes perfect.</span></span>  <span data-ttu-id="681e4-266">独自のページをプロファイリングして、結果を分析してみてください。</span><span class="sxs-lookup"><span data-stu-id="681e4-266">Try profiling your own pages and analyzing the results.</span></span>  <span data-ttu-id="681e4-267">結果について質問がある場合は、[**フィードバック**] アイコンを使用するか `Alt`  +  `Shift`  +  `I` ( `Option`  +  `Shift`  +  `I` macOS の場合)、または[ツイート][TwitterEdgeDevtools]をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="681e4-267">If you have any questions about your results, use the **Feedback** icon, press `Alt` + `Shift` + `I` on Windows (`Option` + `Shift` + `I` on macOS), or [tweet at us][TwitterEdgeDevtools].</span></span>  <span data-ttu-id="681e4-268">可能であれば、スクリーンショットまたは再現可能なページへのリンクを含めます。</span><span class="sxs-lookup"><span data-stu-id="681e4-268">Include screenshots or links to reproducible pages, if possible.</span></span>

> ##### <span data-ttu-id="681e4-269">図 15</span><span class="sxs-lookup"><span data-stu-id="681e4-269">Figure 15</span></span>
> <span data-ttu-id="681e4-270">Microsoft Edge DevTools の**フィードバック**アイコン</span><span class="sxs-lookup"><span data-stu-id="681e4-270">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
> ![Microsoft Edge DevTools の \* \* フィードバック \* \* アイコン][ImageFeedbackIcon]

<!-- To really master runtime performance, you've got to learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

<span data-ttu-id="681e4-272">最後に、実行時のパフォーマンスを向上させるためのさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="681e4-272">Last, there are many ways to improve runtime performance.</span></span>  <span data-ttu-id="681e4-273">このチュートリアルでは、1つの特定のアニメーションのボトルネックに重点を置いて、[パフォーマンス] パネルのフォーカスツアーを提供していますが、発生する可能性のある多数のボトルネックの1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="681e4-273">This tutorial focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.</span></span>  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

<!-- image links -->  

[ImageCaptureSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png  

[ImageGetStarted]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-get-started-side-by-side.msft.png "図 1: 左側のデモと右側の DevTools"  
[ImageCPUThrottling]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-settings.msft.png "図 2: CPU 調整"  
[ImagePageProfiling]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-profiling.msft.png "図 3: ページのプロファイリング"  
[ImageProfileResults]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-results.msft.png "図 4: プロファイルの結果"  
[ImageFPSChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-fps-chart.msft.png "図 5: FPS グラフ"  
[ImageCPUSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-cpu-chart.msft.png "図 6: 青色で囲まれた [CPU グラフ] と [概要] タブ"  
[ImageViewingScreenshot]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-screenshot-hover.msft.png "図 7: 記録の2500ms マークの周りのページのスクリーンショットの表示"  
[ImageFrameHover]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frame-hover.msft.png "図 8: フレーム上のマウスポインター"  
[ImageFPSMeter]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-fps-meter-overlay.msft.png "図 9: FPS メーター"  
[ImageSummaryTab]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-tab.msft.png "図 10: [概要] タブ"  
[ImageMainSection]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main.msft.png "図 11: メインセクション"  
[ImageZoomedAnimation]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-zoomed.msft.png "図 12: 1 つのアニメーションフレームの発生イベントを拡大する"  
[ImageAnimationFrameFired]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-animation-frame-fired.msft.png "図 13: アニメーションフレームの発生イベントに関する詳細情報"  
[ImageForcedLayoutSRC]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-sources-app-update.msft.png "図 14: 強制レイアウトの原因となったコード行"  
[ImageFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-feedback-icon.msft.png "図 15: Microsoft Edge DevTools の * * フィードバック * * アイコン"

<!-- links -->

[DevtoolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DevtoolsSpeedGetStarted]: /microsoft-edge/devtools-guide-chromium/speed/get-started "Microsoft Edge DevTools を使用して Web サイトの速度を最適化する"  

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
> <span data-ttu-id="681e4-293">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="681e4-293">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="681e4-294">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="681e4-294">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="681e4-296">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="681e4-296">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
