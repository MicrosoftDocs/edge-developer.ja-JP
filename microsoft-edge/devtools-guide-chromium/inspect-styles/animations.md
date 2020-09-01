---
title: アニメーションの検査
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a6970d76f4ff70031ef4cc8c6de119a41d1a5b80
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10983402"
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





# <span data-ttu-id="aa1ee-103">アニメーションの検査</span><span class="sxs-lookup"><span data-stu-id="aa1ee-103">Inspect animations</span></span>   



<span data-ttu-id="aa1ee-104">Microsoft Edge DevTools のアニメーションのインスペクターを使って、アニメーションの検査と変更を行います。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-104">Inspect and modify animations with the Microsoft Edge DevTools Animation Inspector.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="アニメーションの詳細設定" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   <span data-ttu-id="aa1ee-106">アニメーションの詳細設定</span><span class="sxs-lookup"><span data-stu-id="aa1ee-106">animation inspector</span></span>  
:::image-end:::  

### <span data-ttu-id="aa1ee-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="aa1ee-107">Summary</span></span>  

*   <span data-ttu-id="aa1ee-108">アニメーションインスペクターを開いてアニメーションをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-108">Capture animations by opening the Animation Inspector.</span></span>  <span data-ttu-id="aa1ee-109">アニメーションの検査機能により、アニメーションが自動的に検出され、グループに並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-109">The Animation Inspector automatically detects and sorts animations into groups.</span></span>  
*   <span data-ttu-id="aa1ee-110">1つずつ減速して、1つずつ再生するか、ソースコードを表示して、アニメーションを検査します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-110">Inspect animations by slowing down each one, replaying each one, or viewing the source code.</span></span>  
*   <span data-ttu-id="aa1ee-111">タイミング、遅延、再生時間、またはキーフレームのオフセットを変更して、アニメーションを変更します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-111">Modify animations by changing the timing, delay, duration, or keyframe offsets.</span></span>  

## <span data-ttu-id="aa1ee-112">概要</span><span class="sxs-lookup"><span data-stu-id="aa1ee-112">Overview</span></span>   

<span data-ttu-id="aa1ee-113">Microsoft Edge DevTools アニメーションのインスペクターには、2つの主な目的があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-113">The Microsoft Edge DevTools Animation Inspector has two main purposes.</span></span>  

*   <span data-ttu-id="aa1ee-114">アニメーションの検査。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-114">Inspecting animations.</span></span>  <span data-ttu-id="aa1ee-115">アニメーショングループのソースコードを減速、再生、検査します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-115">You want to slow down, replay, or inspect the source code for an Animation Group.</span></span>  
*   <span data-ttu-id="aa1ee-116">アニメーションの変更。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-116">Modifying animations.</span></span>  <span data-ttu-id="aa1ee-117">アニメーショングループのタイミング、遅延、再生時間、またはキーフレームのオフセットを変更します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-117">You want to modify the timing, delay, duration, or keyframe offsets of an Animation Group.</span></span>  <span data-ttu-id="aa1ee-118">ベジエ編集とキーフレーム編集は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-118">Bezier editing and keyframe editing are currently not supported.</span></span>  

<span data-ttu-id="aa1ee-119">アニメーションのインスペクターでは、CSS アニメーション、CSS 切り替え、web アニメーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-119">The Animation Inspector supports CSS animations, CSS transitions, and web animations.</span></span>  `requestAnimationFrame` <span data-ttu-id="aa1ee-120">アニメーションは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-120">animations are currently not supported.</span></span>  

### <span data-ttu-id="aa1ee-121">アニメーショングループとは</span><span class="sxs-lookup"><span data-stu-id="aa1ee-121">What is an Animation Group?</span></span>  

<span data-ttu-id="aa1ee-122">アニメーショングループは、互いに関連している可能性のあるアニメーションのグループです。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-122">An Animation Group is a group of animations that may be related to each other.</span></span>  <span data-ttu-id="aa1ee-123">現時点では、web にはグループアニメーションの実際の概念はありません。このため、アニメーションが1つの一貫した視覚効果としてレンダリングされるように、モーションデザイナーと開発者は個々のアニメーションを作成して時間を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-123">Currently, the web has no real concept of a group animation, so motion designers and developers have to compose and time individual animations so that the animations render as one coherent visual effect.</span></span>  <span data-ttu-id="aa1ee-124">アニメーションの設定では、開始時刻 \ (遅延を除く) に基づいて、どのアニメーションが関連しているかが予測されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-124">The Animation Inspector predicts which animations are related based on start time \(excluding delays, and so on\).</span></span>  <span data-ttu-id="aa1ee-125">アニメーションのインスペクターでは、アニメーションを並べてグループ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-125">The Animation Inspector also groups the animations side-by-side.</span></span>  
<span data-ttu-id="aa1ee-126">つまり、同じスクリプトブロックですべてトリガーされる一連のアニメーションは一緒にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-126">In other words, a set of animations that are all triggered in the same script block are grouped together.</span></span>  <span data-ttu-id="aa1ee-127">アニメーションが非同期の場合は、別のグループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-127">If an animation is asynchronous, it is placed in a separate group.</span></span>  

## <span data-ttu-id="aa1ee-128">使ってみる</span><span class="sxs-lookup"><span data-stu-id="aa1ee-128">Get started</span></span>  

<span data-ttu-id="aa1ee-129">アニメーションインスペクターを開くには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-129">There are two ways to open the Animation Inspector:</span></span>  

*   <span data-ttu-id="aa1ee-130">[ **カスタマイズ] および [コントロールの DevTools** ] メニューを開く</span><span class="sxs-lookup"><span data-stu-id="aa1ee-130">Open the **Customize and Control DevTools** menu</span></span>  
    1.  <span data-ttu-id="aa1ee-131">[ **その他のツール** ] サブメニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-131">Navigate to the **More tools** sub-menu.</span></span>  
    1.  <span data-ttu-id="aa1ee-132">[ **アニメーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-132">Select **Animations**:</span></span>  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="メインメニューを使用するアニメーション" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           <span data-ttu-id="aa1ee-134">メインメニューを使用する**アニメーション**</span><span class="sxs-lookup"><span data-stu-id="aa1ee-134">**Animations** using Main Menu</span></span>  
    :::image-end:::  
        
*   <span data-ttu-id="aa1ee-135">**コマンドメニュー**を開く</span><span class="sxs-lookup"><span data-stu-id="aa1ee-135">Open the **Command Menu**</span></span>  
    1.  <span data-ttu-id="aa1ee-136">「`Drawer: Show Animations`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-136">Type `Drawer: Show Animations`.</span></span>  

<span data-ttu-id="aa1ee-137">[アニメーションの設定] が、コンソールドロワーの横にタブとして開きます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-137">The Animation Inspector opens up as a tab next to the Console Drawer.</span></span>  <span data-ttu-id="aa1ee-138">アニメーション検査は [引き出し] タブであるため、任意の DevTools パネルからアニメーションのインスペクターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-138">Since the Animation Inspector is a Drawer tab, you may use the Animation Inspector from any DevTools panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="空のアニメーション検査" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   <span data-ttu-id="aa1ee-140">空のアニメーション検査</span><span class="sxs-lookup"><span data-stu-id="aa1ee-140">Empty Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="aa1ee-141">アニメーションの検査は、4つのメインセクション \ (またはウィンドウ \) にグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-141">The Animation Inspector is grouped into four main sections \(or panes\).</span></span>  <span data-ttu-id="aa1ee-142">このガイドでは、各ウィンドウについて次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-142">This guide refers to each pane as follows:</span></span>  

| | <span data-ttu-id="aa1ee-143">ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="aa1ee-143">Pane</span></span> | <span data-ttu-id="aa1ee-144">説明</span><span class="sxs-lookup"><span data-stu-id="aa1ee-144">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="aa1ee-145">件</span><span class="sxs-lookup"><span data-stu-id="aa1ee-145">1</span></span> | **<span data-ttu-id="aa1ee-146">コントロール</span><span class="sxs-lookup"><span data-stu-id="aa1ee-146">Controls</span></span>** | <span data-ttu-id="aa1ee-147">ここでは、現在キャプチャされているすべてのアニメーショングループをクリアするか、現在選択されているアニメーショングループの速度を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-147">From here you may clear all currently captured Animation Groups, or change the speed of the currently selected Animation Group.</span></span> |  
| <span data-ttu-id="aa1ee-148">両面</span><span class="sxs-lookup"><span data-stu-id="aa1ee-148">2</span></span> | **<span data-ttu-id="aa1ee-149">概要</span><span class="sxs-lookup"><span data-stu-id="aa1ee-149">Overview</span></span>** | <span data-ttu-id="aa1ee-150">ここでアニメーショングループを選択して、 **詳細** ウィンドウで確認して変更します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-150">Select an Animation Group here to inspect and modify it in the **Details** pane.</span></span> |  
| <span data-ttu-id="aa1ee-151">-</span><span class="sxs-lookup"><span data-stu-id="aa1ee-151">3</span></span> | **<span data-ttu-id="aa1ee-152">タイムライン</span><span class="sxs-lookup"><span data-stu-id="aa1ee-152">Timeline</span></span>** | <span data-ttu-id="aa1ee-153">ここからアニメーションを一時停止して開始するか、アニメーション内の特定のポイントにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-153">Pause and start an animation from here, or jump to a specific point in the animation.</span></span> |  
| <span data-ttu-id="aa1ee-154">4d</span><span class="sxs-lookup"><span data-stu-id="aa1ee-154">4</span></span> | **<span data-ttu-id="aa1ee-155">詳細</span><span class="sxs-lookup"><span data-stu-id="aa1ee-155">Details</span></span>** | <span data-ttu-id="aa1ee-156">現在選択されているアニメーショングループを検査して変更します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-156">Inspect and modify the currently selected Animation Group.</span></span> |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="注釈付きアニメーションのインスペクター" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   <span data-ttu-id="aa1ee-158">注釈付きアニメーションのインスペクター</span><span class="sxs-lookup"><span data-stu-id="aa1ee-158">Annotated Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="aa1ee-159">アニメーションをキャプチャするには、アニメーションのインスペクターが開いている状態でアニメーションをトリガーする操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-159">To capture an animation, just perform the interaction that triggers the animation while the Animation Inspector is open.</span></span>  <span data-ttu-id="aa1ee-160">ページの読み込みでアニメーションがトリガーされた場合は、アニメーションインスペクターが開いた状態でページを再読み込みして、アニメーションを検出します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-160">If an animation is triggered on page load, reload the page with the Animation Inspector open to detect the animation.</span></span>  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <span data-ttu-id="aa1ee-161">アニメーションの検査</span><span class="sxs-lookup"><span data-stu-id="aa1ee-161">Inspect animations</span></span>   

<span data-ttu-id="aa1ee-162">アニメーションをキャプチャした後は、いくつかの方法で再生できます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-162">After you capture an animation, there are a few ways to replay it:</span></span>  

*   <span data-ttu-id="aa1ee-163">**概要**ウィンドウのサムネイルにマウスポインターを置くと、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-163">Hover over the thumbnail in the **Overview** pane to view a preview of it.</span></span>  
*   <span data-ttu-id="aa1ee-164">**概要**ウィンドウ (**詳細**ウィンドウに表示されるように) から [アニメーション] グループを選び、 **[再生**] ([ ![ 再生] アイコン ][ImageReplayButtonIcon] \) アイコンを押します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-164">Select the Animation Group from the **Overview** pane \(so that it is displayed in the **Details** pane\) and press the **replay** \(![replay icon][ImageReplayButtonIcon]\) icon.</span></span>  <span data-ttu-id="aa1ee-165">アニメーションはビューポートで再生されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-165">The animation is replayed in the viewport.</span></span>  <span data-ttu-id="aa1ee-166">**animation speed** ![ ][ImageAnimationSpeedButtonsIcon] 現在選択されているアニメーショングループのプレビューの速度を変更するには、[アニメーションの速度] (アニメーションの速度のアイコン) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-166">Click on the **animation speed** \(![animation speed icons][ImageAnimationSpeedButtonsIcon]\) icons to change the preview speed of the currently selected Animation Group.</span></span>  <span data-ttu-id="aa1ee-167">赤い垂直バーを使用して、現在の位置を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-167">You may use the red vertical bar to change your current position.</span></span>  
*   <span data-ttu-id="aa1ee-168">赤い垂直バーをクリックしてドラッグすると、ビューポートのアニメーションがスクラブされます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-168">Click and drag the red vertical bar to scrub the viewport animation.</span></span>  
    
### <span data-ttu-id="aa1ee-169">アニメーションの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="aa1ee-169">View animation details</span></span>  

<span data-ttu-id="aa1ee-170">アニメーショングループをキャプチャしたら、[ **概要** ] ウィンドウでクリックして詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-170">After you capture an Animation Group, click on it from the **Overview** pane to view the details.</span></span>  <span data-ttu-id="aa1ee-171">**詳細**ウィンドウには、個々のアニメーションに1行が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-171">In the **Details** pane each individual animation is assigned the a row.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="アニメーショングループの詳細" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="aa1ee-173">アニメーショングループの詳細</span><span class="sxs-lookup"><span data-stu-id="aa1ee-173">Animation Group details</span></span>  
:::image-end:::  

<span data-ttu-id="aa1ee-174">アニメーションの上にマウスポインターを移動すると、ビューポート内で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-174">Hover over an animation to highlight it in the viewport.</span></span>  <span data-ttu-id="aa1ee-175">アニメーションをクリックして、[ **要素** ] パネルで選択します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-175">Click on the animation to select it in the **Elements** panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="ビューポートでアニメーションをポイントして強調表示する" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="aa1ee-177">ビューポートでアニメーションをポイントして強調表示する</span><span class="sxs-lookup"><span data-stu-id="aa1ee-177">Hover over the animation to highlight it in viewport</span></span>  
:::image-end:::  

<span data-ttu-id="aa1ee-178">アニメーションの左端、濃い色の部分が定義です。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-178">The leftmost, darker section of an animation is the definition.</span></span>  <span data-ttu-id="aa1ee-179">右側の [薄い色] セクションは、反復計算を表します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-179">The right, more faded section represents iterations.</span></span>  <span data-ttu-id="aa1ee-180">たとえば、次の図では、セクション2と3はセクション1のイテレーションを表しています。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-180">For example, in the following figure, sections two and three represent iterations of section one.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="アニメーションの反復計算の図" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   <span data-ttu-id="aa1ee-182">アニメーションの反復計算の図</span><span class="sxs-lookup"><span data-stu-id="aa1ee-182">Diagram of animation iterations</span></span>  
:::image-end:::  

<span data-ttu-id="aa1ee-183">2つの要素に同じアニメーションが適用されている場合、アニメーションのインスペクターでは要素に同じ色が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-183">If two elements have the same animation applied, the Animation Inspector assigns the same color to the elements.</span></span>  <span data-ttu-id="aa1ee-184">色はランダムであり、意味はありません。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-184">The color is random and has no significance.</span></span>  <span data-ttu-id="aa1ee-185">たとえば、次の図では、要素と要素と同様に、2つの要素 `div.cwccw.earlier` と、 `div.cwccw.later` 同じアニメーション \ ( `spinrightleft` \) が適用されてい `div.ccwcw.earlier` `div.ccwcw.later` ます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-185">For example, in the following figure, the two elements `div.cwccw.earlier` and `div.cwccw.later` have the same animation \(`spinrightleft`\) applied, as do the `div.ccwcw.earlier` and `div.ccwcw.later` elements.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="色分けされたアニメーション" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   <span data-ttu-id="aa1ee-187">色分けされたアニメーション</span><span class="sxs-lookup"><span data-stu-id="aa1ee-187">Color-coded animations</span></span>  
:::image-end:::  

## <span data-ttu-id="aa1ee-188">アニメーションの変更</span><span class="sxs-lookup"><span data-stu-id="aa1ee-188">Modify animations</span></span>   

<span data-ttu-id="aa1ee-189">アニメーションインスペクターでアニメーションを変更するには、3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-189">There are three ways you are able to modify an animation with the Animation Inspector.</span></span>  

*   <span data-ttu-id="aa1ee-190">アニメーションの継続時間。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-190">Animation duration.</span></span>  
*   <span data-ttu-id="aa1ee-191">キーフレームのタイミング。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-191">Keyframe timings.</span></span>  
*   <span data-ttu-id="aa1ee-192">開始タイミングの遅延。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-192">Start time delay.</span></span>  
    
<span data-ttu-id="aa1ee-193">次の図では、元のアニメーションが表示されています。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-193">In the following figure, the original animation is represented.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="変更前の元のアニメーション" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   <span data-ttu-id="aa1ee-195">変更前の元のアニメーション</span><span class="sxs-lookup"><span data-stu-id="aa1ee-195">Original animation before modification</span></span>  
:::image-end:::  

<span data-ttu-id="aa1ee-196">アニメーションの継続時間を変更するには、最初または最後の円をクリックしてドラッグします。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-196">To change the duration of an animation, click and drag the first or last circle.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="変更された期間" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   <span data-ttu-id="aa1ee-198">変更された期間</span><span class="sxs-lookup"><span data-stu-id="aa1ee-198">Modified duration</span></span>  
:::image-end:::  

<span data-ttu-id="aa1ee-199">アニメーションでキーフレームルールが定義されている場合は、それらは白色の内側の円として表されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-199">If the animation defines any keyframe rules, then these are represented as white inner circles.</span></span>  <span data-ttu-id="aa1ee-200">いずれかをクリックしてドラッグし、キーフレームのタイミングを変更します。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-200">Click and drag one of these to change the timing of the keyframe.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="変更されたキーフレーム" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   <span data-ttu-id="aa1ee-202">変更されたキーフレーム</span><span class="sxs-lookup"><span data-stu-id="aa1ee-202">Modified keyframe</span></span>  
:::image-end:::  

<span data-ttu-id="aa1ee-203">アニメーションに遅延を追加するには、円以外の任意の場所でクリックしてドラッグします。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-203">To add a delay to an animation, click and drag it anywhere except the circles.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="変更遅延" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   <span data-ttu-id="aa1ee-205">変更遅延</span><span class="sxs-lookup"><span data-stu-id="aa1ee-205">Modified delay</span></span>  
:::image-end:::  

<!--  
  


-->  

<!-- image links -->  

[ImageAnimationSpeedButtonsIcon]: ../media/animation-speed-buttons-icon.msft.png  
[ImageReplayButtonIcon]: ../media/replay-button-icon.msft.png  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="aa1ee-206">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-206">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="aa1ee-207">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-207">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="aa1ee-209">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="aa1ee-209">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
