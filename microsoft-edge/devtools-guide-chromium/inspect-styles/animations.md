---
title: アニメーションを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6466c7f0e1f8680a2429b565e8022d152d05d733
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570344"
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





# <span data-ttu-id="6af10-103">アニメーションを検査する</span><span class="sxs-lookup"><span data-stu-id="6af10-103">Inspect animations</span></span>   



<span data-ttu-id="6af10-104">Microsoft Edge DevTools のアニメーションのインスペクターを使って、アニメーションの検査と変更を行います。</span><span class="sxs-lookup"><span data-stu-id="6af10-104">Inspect and modify animations with the Microsoft Edge DevTools Animation Inspector.</span></span>  

> ##### <span data-ttu-id="6af10-105">図 1</span><span class="sxs-lookup"><span data-stu-id="6af10-105">Figure 1</span></span>  
> <span data-ttu-id="6af10-106">アニメーションの詳細設定</span><span class="sxs-lookup"><span data-stu-id="6af10-106">Animation inspector</span></span>  
> ![アニメーションの詳細設定][ImageAnimationInspector]  

### <span data-ttu-id="6af10-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6af10-108">Summary</span></span>  

*   <span data-ttu-id="6af10-109">アニメーションインスペクターを開いてアニメーションをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="6af10-109">Capture animations by opening the Animation Inspector.</span></span>  <span data-ttu-id="6af10-110">アニメーションの検査機能により、アニメーションが自動的に検出され、グループに並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="6af10-110">The Animation Inspector automatically detects and sorts animations into groups.</span></span>  
*   <span data-ttu-id="6af10-111">1つずつ減速して、1つずつ再生するか、ソースコードを表示して、アニメーションを検査します。</span><span class="sxs-lookup"><span data-stu-id="6af10-111">Inspect animations by slowing down each one, replaying each one, or viewing the source code.</span></span>  
*   <span data-ttu-id="6af10-112">タイミング、遅延、再生時間、またはキーフレームのオフセットを変更して、アニメーションを変更します。</span><span class="sxs-lookup"><span data-stu-id="6af10-112">Modify animations by changing the timing, delay, duration, or keyframe offsets.</span></span>  

## <span data-ttu-id="6af10-113">概要</span><span class="sxs-lookup"><span data-stu-id="6af10-113">Overview</span></span>   

<span data-ttu-id="6af10-114">Microsoft Edge DevTools アニメーションのインスペクターには、2つの主な目的があります。</span><span class="sxs-lookup"><span data-stu-id="6af10-114">The Microsoft Edge DevTools Animation Inspector has two main purposes.</span></span>  

*   <span data-ttu-id="6af10-115">アニメーションの検査。</span><span class="sxs-lookup"><span data-stu-id="6af10-115">Inspecting animations.</span></span>  <span data-ttu-id="6af10-116">アニメーショングループのソースコードを減速、再生、検査します。</span><span class="sxs-lookup"><span data-stu-id="6af10-116">You want to slow down, replay, or inspect the source code for an Animation Group.</span></span>  
*   <span data-ttu-id="6af10-117">アニメーションの変更。</span><span class="sxs-lookup"><span data-stu-id="6af10-117">Modifying animations.</span></span>  <span data-ttu-id="6af10-118">アニメーショングループのタイミング、遅延、再生時間、またはキーフレームのオフセットを変更します。</span><span class="sxs-lookup"><span data-stu-id="6af10-118">You want to modify the timing, delay, duration, or keyframe offsets of an Animation Group.</span></span>  <span data-ttu-id="6af10-119">ベジエ編集とキーフレーム編集は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6af10-119">Bezier editing and keyframe editing are currently not supported.</span></span>  

<span data-ttu-id="6af10-120">アニメーションのインスペクターでは、CSS アニメーション、CSS 切り替え、web アニメーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6af10-120">The Animation Inspector supports CSS animations, CSS transitions, and web animations.</span></span>  `requestAnimationFrame` <span data-ttu-id="6af10-121">アニメーションは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6af10-121">animations are currently not supported.</span></span>  

### <span data-ttu-id="6af10-122">アニメーショングループとは</span><span class="sxs-lookup"><span data-stu-id="6af10-122">What is an Animation Group?</span></span>  

<span data-ttu-id="6af10-123">アニメーショングループは、互いに関連している可能性のあるアニメーションのグループです。</span><span class="sxs-lookup"><span data-stu-id="6af10-123">An Animation Group is a group of animations that may be related to each other.</span></span>  <span data-ttu-id="6af10-124">現時点では、web にはグループアニメーションの実際の概念はありません。このため、アニメーションが1つの一貫した視覚効果としてレンダリングされるように、モーションデザイナーと開発者は個々のアニメーションを作成して時間を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6af10-124">Currently, the web has no real concept of a group animation, so motion designers and developers have to compose and time individual animations so that the animations render as one coherent visual effect.</span></span>  <span data-ttu-id="6af10-125">アニメーションの設定では、開始時刻 \ (遅延を除く) に基づいて、どのアニメーションが関連しているかが予測されます。</span><span class="sxs-lookup"><span data-stu-id="6af10-125">The Animation Inspector predicts which animations are related based on start time \(excluding delays, and so on\).</span></span>  <span data-ttu-id="6af10-126">アニメーションのインスペクターでは、アニメーションを並べてグループ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="6af10-126">The Animation Inspector also groups the animations side-by-side.</span></span>  
<span data-ttu-id="6af10-127">つまり、同じスクリプトブロックですべてトリガーされる一連のアニメーションは一緒にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="6af10-127">In other words, a set of animations that are all triggered in the same script block are grouped together.</span></span>  <span data-ttu-id="6af10-128">アニメーションが非同期の場合は、別のグループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6af10-128">If an animation is asynchronous, it is placed in a separate group.</span></span>  

## <span data-ttu-id="6af10-129">使ってみる</span><span class="sxs-lookup"><span data-stu-id="6af10-129">Get started</span></span>  

<span data-ttu-id="6af10-130">アニメーションインスペクターを開くには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6af10-130">There are two ways to open the Animation Inspector:</span></span>  

*   <span data-ttu-id="6af10-131">[**カスタマイズ] および [コントロールの DevTools** ] メニューを開く</span><span class="sxs-lookup"><span data-stu-id="6af10-131">Open the **Customize and Control DevTools** menu</span></span>  
    1.  <span data-ttu-id="6af10-132">[**その他のツール**] サブメニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="6af10-132">Navigate to the **More tools** sub-menu.</span></span>  
    1.  <span data-ttu-id="6af10-133">[**アニメーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6af10-133">Select **Animations**:</span></span>  
        
        > ##### <span data-ttu-id="6af10-134">図 2</span><span class="sxs-lookup"><span data-stu-id="6af10-134">Figure 2</span></span>  
        > <span data-ttu-id="6af10-135">メインメニューを使ったアニメーション</span><span class="sxs-lookup"><span data-stu-id="6af10-135">Animations via Main Menu</span></span>  
        > ![メインメニューを使ったアニメーション][ImageAnimationsViaMainMenu]  
        
*   <span data-ttu-id="6af10-137">**コマンドメニュー**を開く</span><span class="sxs-lookup"><span data-stu-id="6af10-137">Open the **Command Menu**</span></span>  
    1.  <span data-ttu-id="6af10-138">「`Drawer: Show Animations`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6af10-138">Type `Drawer: Show Animations`.</span></span>  

<span data-ttu-id="6af10-139">[アニメーションの設定] が、コンソールドロワーの横にタブとして開きます。</span><span class="sxs-lookup"><span data-stu-id="6af10-139">The Animation Inspector opens up as a tab next to the Console Drawer.</span></span>  <span data-ttu-id="6af10-140">アニメーション検査は [引き出し] タブであるため、任意の DevTools パネルからアニメーションのインスペクターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6af10-140">Since the Animation Inspector is a Drawer tab, you may use the Animation Inspector from any DevTools panel.</span></span>  

> ##### <span data-ttu-id="6af10-141">図 3</span><span class="sxs-lookup"><span data-stu-id="6af10-141">Figure 3</span></span>  
> <span data-ttu-id="6af10-142">空のアニメーション検査</span><span class="sxs-lookup"><span data-stu-id="6af10-142">Empty Animation Inspector</span></span>  
> ![空のアニメーション検査][ImageEmptyAnimationInspector]  

<span data-ttu-id="6af10-144">アニメーションの検査は、4つのメインセクション \ (またはウィンドウ \) にグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="6af10-144">The Animation Inspector is grouped into four main sections \(or panes\).</span></span>  <span data-ttu-id="6af10-145">このガイドでは、各ウィンドウについて次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="6af10-145">This guide refers to each pane as follows:</span></span>  

| | <span data-ttu-id="6af10-146">ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="6af10-146">Pane</span></span> | <span data-ttu-id="6af10-147">説明</span><span class="sxs-lookup"><span data-stu-id="6af10-147">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="6af10-148">件</span><span class="sxs-lookup"><span data-stu-id="6af10-148">1</span></span> | **<span data-ttu-id="6af10-149">コントロール</span><span class="sxs-lookup"><span data-stu-id="6af10-149">Controls</span></span>** | <span data-ttu-id="6af10-150">ここでは、現在キャプチャされているすべてのアニメーショングループをクリアするか、現在選択されているアニメーショングループの速度を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6af10-150">From here you may clear all currently captured Animation Groups, or change the speed of the currently selected Animation Group.</span></span> |  
| <span data-ttu-id="6af10-151">両面</span><span class="sxs-lookup"><span data-stu-id="6af10-151">2</span></span> | **<span data-ttu-id="6af10-152">概要</span><span class="sxs-lookup"><span data-stu-id="6af10-152">Overview</span></span>** | <span data-ttu-id="6af10-153">ここでアニメーショングループを選択して、**詳細**ウィンドウで確認して変更します。</span><span class="sxs-lookup"><span data-stu-id="6af10-153">Select an Animation Group here to inspect and modify it in the **Details** pane.</span></span> |  
| <span data-ttu-id="6af10-154">-</span><span class="sxs-lookup"><span data-stu-id="6af10-154">3</span></span> | **<span data-ttu-id="6af10-155">タイムライン</span><span class="sxs-lookup"><span data-stu-id="6af10-155">Timeline</span></span>** | <span data-ttu-id="6af10-156">ここからアニメーションを一時停止して開始するか、アニメーション内の特定のポイントにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="6af10-156">Pause and start an animation from here, or jump to a specific point in the animation.</span></span> |  
| <span data-ttu-id="6af10-157">4d</span><span class="sxs-lookup"><span data-stu-id="6af10-157">4</span></span> | **<span data-ttu-id="6af10-158">詳細</span><span class="sxs-lookup"><span data-stu-id="6af10-158">Details</span></span>** | <span data-ttu-id="6af10-159">現在選択されているアニメーショングループを検査して変更します。</span><span class="sxs-lookup"><span data-stu-id="6af10-159">Inspect and modify the currently selected Animation Group.</span></span> |  

> ##### <span data-ttu-id="6af10-160">図 4</span><span class="sxs-lookup"><span data-stu-id="6af10-160">Figure 4</span></span>  
> <span data-ttu-id="6af10-161">注釈付きアニメーションのインスペクター</span><span class="sxs-lookup"><span data-stu-id="6af10-161">Annotated Animation Inspector</span></span>  
> ![注釈付きアニメーションのインスペクター][ImageAnnotatedAnimationInspector]  

<span data-ttu-id="6af10-163">アニメーションをキャプチャするには、アニメーションのインスペクターが開いている状態でアニメーションをトリガーする操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6af10-163">To capture an animation, just perform the interaction that triggers the animation while the Animation Inspector is open.</span></span>  <span data-ttu-id="6af10-164">ページの読み込みでアニメーションがトリガーされた場合は、アニメーションインスペクターが開いた状態でページを再読み込みして、アニメーションを検出します。</span><span class="sxs-lookup"><span data-stu-id="6af10-164">If an animation is triggered on page load, reload the page with the Animation Inspector open to detect the animation.</span></span>  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <span data-ttu-id="6af10-165">アニメーションを検査する</span><span class="sxs-lookup"><span data-stu-id="6af10-165">Inspect animations</span></span>   

<span data-ttu-id="6af10-166">アニメーションをキャプチャした後は、いくつかの方法で再生できます。</span><span class="sxs-lookup"><span data-stu-id="6af10-166">After you capture an animation, there are a few ways to replay it:</span></span>  

*   <span data-ttu-id="6af10-167">**概要**ウィンドウのサムネイルにマウスポインターを置くと、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6af10-167">Hover over the thumbnail in the **Overview** pane to view a preview of it.</span></span>  
*   <span data-ttu-id="6af10-168">(**詳細**ウィンドウに表示されるように) [**概要**] ウィンドウで [アニメーション] グループを選び、 **[再生** ![ 再生] アイコンを押し ][ImageReplayButtonIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="6af10-168">Select the Animation Group from the **Overview** pane \(so that it is displayed in the **Details** pane\) and press the **replay** ![replay icon][ImageReplayButtonIcon] icon.</span></span>  <span data-ttu-id="6af10-169">アニメーションはビューポートで再生されます。</span><span class="sxs-lookup"><span data-stu-id="6af10-169">The animation is replayed in the viewport.</span></span>  <span data-ttu-id="6af10-170">アニメーション**速度**のアニメーション速度のアイコンをクリックして、 ![ ][ImageAnimationSpeedButtonsIcon] 現在選択されているアニメーショングループのプレビューの速度を変更します。</span><span class="sxs-lookup"><span data-stu-id="6af10-170">Click on the **animation speed** ![animation speed icons][ImageAnimationSpeedButtonsIcon] icons to change the preview speed of the currently selected Animation Group.</span></span>  <span data-ttu-id="6af10-171">赤い垂直バーを使用して、現在の位置を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6af10-171">You may use the red vertical bar to change your current position.</span></span>  
*   <span data-ttu-id="6af10-172">赤い垂直バーをクリックしてドラッグすると、ビューポートのアニメーションがスクラブされます。</span><span class="sxs-lookup"><span data-stu-id="6af10-172">Click and drag the red vertical bar to scrub the viewport animation.</span></span>  

### <span data-ttu-id="6af10-173">アニメーションの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="6af10-173">View animation details</span></span>  

<span data-ttu-id="6af10-174">アニメーショングループをキャプチャしたら、[**概要**] ウィンドウでクリックして詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="6af10-174">After you capture an Animation Group, click on it from the **Overview** pane to view the details.</span></span>  <span data-ttu-id="6af10-175">**詳細**ウィンドウには、個々のアニメーションに1行が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6af10-175">In the **Details** pane each individual animation is assigned the a row.</span></span>  

> ##### <span data-ttu-id="6af10-176">図 5</span><span class="sxs-lookup"><span data-stu-id="6af10-176">Figure 5</span></span>  
> <span data-ttu-id="6af10-177">アニメーショングループの詳細</span><span class="sxs-lookup"><span data-stu-id="6af10-177">Animation Group details</span></span>  
> ![アニメーショングループの詳細][ImageAnimationGroupDetails]  

<span data-ttu-id="6af10-179">アニメーションの上にマウスポインターを移動すると、ビューポート内で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="6af10-179">Hover over an animation to highlight it in the viewport.</span></span>  <span data-ttu-id="6af10-180">アニメーションをクリックして、[**要素**] パネルで選択します。</span><span class="sxs-lookup"><span data-stu-id="6af10-180">Click on the animation to select it in the **Elements** panel.</span></span>  

> ##### <span data-ttu-id="6af10-181">図 6</span><span class="sxs-lookup"><span data-stu-id="6af10-181">Figure 6</span></span>  
> <span data-ttu-id="6af10-182">ビューポートでアニメーションをポイントして強調表示する</span><span class="sxs-lookup"><span data-stu-id="6af10-182">Hover over the animation to highlight it in viewport</span></span>  
> ![ビューポートでアニメーションをポイントして強調表示する][ImageHoverOverAnimationHighlightViewport]  

<span data-ttu-id="6af10-184">アニメーションの左端、濃い色の部分が定義です。</span><span class="sxs-lookup"><span data-stu-id="6af10-184">The leftmost, darker section of an animation is the definition.</span></span>  <span data-ttu-id="6af10-185">右側の [薄い色] セクションは、反復計算を表します。</span><span class="sxs-lookup"><span data-stu-id="6af10-185">The right, more faded section represents iterations.</span></span>  <span data-ttu-id="6af10-186">たとえば、[図 7](#figure-7)では、セクション2と3はセクション1のイテレーションを表します。</span><span class="sxs-lookup"><span data-stu-id="6af10-186">For example, in [Figure 7](#figure-7), sections two and three represent iterations of section one.</span></span>  

> ##### <span data-ttu-id="6af10-187">図 7</span><span class="sxs-lookup"><span data-stu-id="6af10-187">Figure 7</span></span>  
> <span data-ttu-id="6af10-188">アニメーションの反復計算の図</span><span class="sxs-lookup"><span data-stu-id="6af10-188">Diagram of animation iterations</span></span>  
> ![アニメーションの反復計算の図][ImageDiagramAnimationIterations]  

<span data-ttu-id="6af10-190">2つの要素に同じアニメーションが適用されている場合、アニメーションのインスペクターでは要素に同じ色が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6af10-190">If two elements have the same animation applied, the Animation Inspector assigns the same color to the elements.</span></span>  <span data-ttu-id="6af10-191">色はランダムであり、意味はありません。</span><span class="sxs-lookup"><span data-stu-id="6af10-191">The color is random and has no significance.</span></span>  <span data-ttu-id="6af10-192">たとえば、[図 8](#figure-8)の2つの要素 `div.cwccw.earlier` と、要素との間に `div.cwccw.later` 同じアニメーション \ ( `spinrightleft` \) が適用されてい `div.ccwcw.earlier` `div.ccwcw.later` ます。</span><span class="sxs-lookup"><span data-stu-id="6af10-192">For example, in [Figure 8](#figure-8) the two elements `div.cwccw.earlier` and `div.cwccw.later` have the same animation \(`spinrightleft`\) applied, as do the `div.ccwcw.earlier` and `div.ccwcw.later` elements.</span></span>  

> ##### <span data-ttu-id="6af10-193">図 8</span><span class="sxs-lookup"><span data-stu-id="6af10-193">Figure 8</span></span>  
> <span data-ttu-id="6af10-194">色分けされたアニメーション</span><span class="sxs-lookup"><span data-stu-id="6af10-194">Color-coded animations</span></span>  
> ![色分けされたアニメーション][ImageColorCodedAnimations]  

## <span data-ttu-id="6af10-196">アニメーションの変更</span><span class="sxs-lookup"><span data-stu-id="6af10-196">Modify animations</span></span>   

<span data-ttu-id="6af10-197">アニメーションインスペクターでアニメーションを変更するには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6af10-197">There are three ways you are able to modify an animation with the Animation Inspector:</span></span>  

*   <span data-ttu-id="6af10-198">アニメーションの継続時間。</span><span class="sxs-lookup"><span data-stu-id="6af10-198">Animation duration.</span></span>  
*   <span data-ttu-id="6af10-199">キーフレームのタイミング。</span><span class="sxs-lookup"><span data-stu-id="6af10-199">Keyframe timings.</span></span>  
*   <span data-ttu-id="6af10-200">開始タイミングの遅延。</span><span class="sxs-lookup"><span data-stu-id="6af10-200">Start time delay.</span></span>  

<span data-ttu-id="6af10-201">このセクションでは、[図 9](#figure-9)は元のアニメーションを表していることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="6af10-201">For this section suppose that [Figure 9](#figure-9) represents the original animation:</span></span>  

> ##### <span data-ttu-id="6af10-202">図 9</span><span class="sxs-lookup"><span data-stu-id="6af10-202">Figure 9</span></span>  
> <span data-ttu-id="6af10-203">変更前の元のアニメーション</span><span class="sxs-lookup"><span data-stu-id="6af10-203">Original animation before modification</span></span>  
> ![変更前の元のアニメーション][ImageOriginalAnimationBeforeModification]  

<span data-ttu-id="6af10-205">アニメーションの継続時間を変更するには、最初または最後の円をクリックしてドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6af10-205">To change the duration of an animation, click and drag the first or last circle.</span></span>  

> ##### <span data-ttu-id="6af10-206">図 10</span><span class="sxs-lookup"><span data-stu-id="6af10-206">Figure 10</span></span>  
> <span data-ttu-id="6af10-207">変更された期間</span><span class="sxs-lookup"><span data-stu-id="6af10-207">Modified duration</span></span>  
> ![変更された期間][ImageModifiedDuration]  

<span data-ttu-id="6af10-209">アニメーションでキーフレームルールが定義されている場合は、それらは白色の内側の円として表されます。</span><span class="sxs-lookup"><span data-stu-id="6af10-209">If the animation defines any keyframe rules, then these are represented as white inner circles.</span></span>  <span data-ttu-id="6af10-210">いずれかをクリックしてドラッグし、キーフレームのタイミングを変更します。</span><span class="sxs-lookup"><span data-stu-id="6af10-210">Click and drag one of these to change the timing of the keyframe.</span></span>  

> ##### <span data-ttu-id="6af10-211">図 11</span><span class="sxs-lookup"><span data-stu-id="6af10-211">Figure 11</span></span>  
> <span data-ttu-id="6af10-212">変更されたキーフレーム</span><span class="sxs-lookup"><span data-stu-id="6af10-212">Modified keyframe</span></span>  
> ![変更されたキーフレーム][ImageModifiedKeyframe]  

<span data-ttu-id="6af10-214">アニメーションに遅延を追加するには、円以外の任意の場所でクリックしてドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6af10-214">To add a delay to an animation, click and drag it anywhere except the circles.</span></span>  

> ##### <span data-ttu-id="6af10-215">図 12</span><span class="sxs-lookup"><span data-stu-id="6af10-215">Figure 12</span></span>  
> <span data-ttu-id="6af10-216">変更遅延</span><span class="sxs-lookup"><span data-stu-id="6af10-216">Modified delay</span></span>  
> ![変更遅延][ImageModifiedDelay]  

<!--   -->  



<!-- image links -->  

[ImageAnimationSpeedButtonsIcon]: /microsoft-edge/devtools-guide-chromium/media/animation-speed-buttons-icon.msft.png  
[ImageReplayButtonIcon]: /microsoft-edge/devtools-guide-chromium/media/replay-button-icon.msft.png  

[ImageAnimationInspector]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-drawer-animations-completed.msft.png "図 1: アニメーションインスペクター"  
[ImageAnimationsViaMainMenu]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-more-tools-animations.msft.png "図 2: メインメニューを使ったアニメーション"  
[ImageEmptyAnimationInspector]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-drawer-animations.msft.png "図 3: 空のアニメーションインスペクター"  
[ImageAnnotatedAnimationInspector]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png "図 4: 注釈付きアニメーションのインスペクター"  
[ImageAnimationGroupDetails]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png "図 5: アニメーショングループの詳細"  
[ImageHoverOverAnimationHighlightViewport]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png "図 6: ビューポートでアニメーションをポイントして強調表示する"  
[ImageDiagramAnimationIterations]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-display-animations-highlight.msft.png "図 7: アニメーションの反復の図"  
[ImageColorCodedAnimations]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-display-animations.msft.png "図 8: 色分けされたアニメーション"  
[ImageOriginalAnimationBeforeModification]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-spin-animations-console-animations.msft.png "図 9: 変更前の元のアニメーション"  
[ImageModifiedDuration]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png "図 10: 変更された期間"  
[ImageModifiedKeyframe]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png "図 11: 変更されたキーフレーム"  
[ImageModifiedDelay]: /microsoft-edge/devtools-guide-chromium/media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png "図 12: 変更の遅延"  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="6af10-230">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6af10-230">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6af10-231">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="6af10-231">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6af10-233">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6af10-233">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
