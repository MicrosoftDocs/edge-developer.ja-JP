---
description: DevTools アニメーション インスペクターでアニメーションMicrosoft Edge変更します。
title: アニメーションの検査
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a695517cb56da057e62293b5ca92b22058602f44
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564218"
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
# <a name="inspect-animations"></a><span data-ttu-id="51c02-104">アニメーションの検査</span><span class="sxs-lookup"><span data-stu-id="51c02-104">Inspect animations</span></span>  

<span data-ttu-id="51c02-105">DevTools アニメーション インスペクターでアニメーションMicrosoft Edge変更します。</span><span class="sxs-lookup"><span data-stu-id="51c02-105">Inspect and modify animations with the Microsoft Edge DevTools Animation Inspector.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="アニメーション インスペクター" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   <span data-ttu-id="51c02-107">アニメーション インスペクター</span><span class="sxs-lookup"><span data-stu-id="51c02-107">animation inspector</span></span>  
:::image-end:::  

### <a name="summary"></a><span data-ttu-id="51c02-108">要約</span><span class="sxs-lookup"><span data-stu-id="51c02-108">Summary</span></span>  

*   <span data-ttu-id="51c02-109">アニメーション インスペクターを開いてアニメーションをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="51c02-109">Capture animations by opening the Animation Inspector.</span></span>  <span data-ttu-id="51c02-110">アニメーション インスペクターは、アニメーションを自動的に検出し、グループに並べ替える。</span><span class="sxs-lookup"><span data-stu-id="51c02-110">The Animation Inspector automatically detects and sorts animations into groups.</span></span>  
*   <span data-ttu-id="51c02-111">アニメーションを検査するには、各アニメーションの速度を低下したり、各アニメーションを再生したり、ソース コードを表示したりします。</span><span class="sxs-lookup"><span data-stu-id="51c02-111">Inspect animations by slowing down each one, replaying each one, or viewing the source code.</span></span>  
*   <span data-ttu-id="51c02-112">タイミング、遅延、期間、またはキーフレーム のオフセットを変更してアニメーションを変更します。</span><span class="sxs-lookup"><span data-stu-id="51c02-112">Modify animations by changing the timing, delay, duration, or keyframe offsets.</span></span>  

## <a name="overview"></a><span data-ttu-id="51c02-113">概要</span><span class="sxs-lookup"><span data-stu-id="51c02-113">Overview</span></span>  

<span data-ttu-id="51c02-114">DevTools Microsoft Edgeインスペクターには、主に 2 つの目的があります。</span><span class="sxs-lookup"><span data-stu-id="51c02-114">The Microsoft Edge DevTools Animation Inspector has two main purposes.</span></span>  

*   <span data-ttu-id="51c02-115">アニメーションの検査。</span><span class="sxs-lookup"><span data-stu-id="51c02-115">Inspecting animations.</span></span>  <span data-ttu-id="51c02-116">アニメーション グループのソース コードの速度を低下、再生、または検査する場合。</span><span class="sxs-lookup"><span data-stu-id="51c02-116">You want to slow down, replay, or inspect the source code for an Animation Group.</span></span>  
*   <span data-ttu-id="51c02-117">アニメーションの変更。</span><span class="sxs-lookup"><span data-stu-id="51c02-117">Modifying animations.</span></span>  <span data-ttu-id="51c02-118">アニメーション グループのタイミング、遅延、期間、またはキーフレーム のオフセットを変更する場合。</span><span class="sxs-lookup"><span data-stu-id="51c02-118">You want to modify the timing, delay, duration, or keyframe offsets of an Animation Group.</span></span>  <span data-ttu-id="51c02-119">ベジエ編集とキーフレーム編集は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="51c02-119">Bezier editing and keyframe editing are currently not supported.</span></span>  

<span data-ttu-id="51c02-120">アニメーション インスペクターは、CSS アニメーション、CSS 切り替え、および Web アニメーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="51c02-120">The Animation Inspector supports CSS animations, CSS transitions, and web animations.</span></span>  `requestAnimationFrame` <span data-ttu-id="51c02-121">アニメーションは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="51c02-121">animations are currently not supported.</span></span>  

### <a name="what-is-an-animation-group"></a><span data-ttu-id="51c02-122">アニメーション グループとは</span><span class="sxs-lookup"><span data-stu-id="51c02-122">What is an Animation Group?</span></span>  

<span data-ttu-id="51c02-123">アニメーション グループは、互いに関連付け合う可能性があるアニメーションのグループです。</span><span class="sxs-lookup"><span data-stu-id="51c02-123">An Animation Group is a group of animations that may be related to each other.</span></span>  <span data-ttu-id="51c02-124">現時点では、Web にはグループ アニメーションの実際の概念はないので、モーション デザイナーと開発者は、アニメーションが 1 つの一貫性のある視覚効果としてレンダリングするために、個々のアニメーションを作成して時間を取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c02-124">Currently, the web has no real concept of a group animation, so motion designers and developers have to compose and time individual animations so that the animations render as one coherent visual effect.</span></span>  <span data-ttu-id="51c02-125">アニメーション インスペクターは、開始時刻 \(遅延を除く、および on\) に基づいて関連するアニメーションを予測します。</span><span class="sxs-lookup"><span data-stu-id="51c02-125">The Animation Inspector predicts which animations are related based on start time \(excluding delays, and so on\).</span></span>  <span data-ttu-id="51c02-126">アニメーション インスペクターは、アニメーションを並べてグループ化します。</span><span class="sxs-lookup"><span data-stu-id="51c02-126">The Animation Inspector also groups the animations side-by-side.</span></span>  
<span data-ttu-id="51c02-127">つまり、同じスクリプト ブロックでトリガーされるアニメーションのセットがグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-127">In other words, a set of animations that are all triggered in the same script block are grouped together.</span></span>  <span data-ttu-id="51c02-128">アニメーションが非同期の場合は、別のグループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-128">If an animation is asynchronous, it is placed in a separate group.</span></span>  

## <a name="get-started"></a><span data-ttu-id="51c02-129">作業の開始</span><span class="sxs-lookup"><span data-stu-id="51c02-129">Get started</span></span>  

<span data-ttu-id="51c02-130">アニメーション インスペクターを開く方法は 2 通りあります。</span><span class="sxs-lookup"><span data-stu-id="51c02-130">There are two ways to open the Animation Inspector:</span></span>  

*   <span data-ttu-id="51c02-131">**[DevTools のカスタマイズと制御] メニューを開**きます。</span><span class="sxs-lookup"><span data-stu-id="51c02-131">Open the **Customize and Control DevTools** menu</span></span>  
    1.  <span data-ttu-id="51c02-132">[その他の **ツール] サブメニュー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="51c02-132">Navigate to the **More tools** sub-menu.</span></span>  
    1.  <span data-ttu-id="51c02-133">[アニメーション **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="51c02-133">Choose **Animations**:</span></span>  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="メイン メニューを使用したアニメーション" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           <span data-ttu-id="51c02-135">**メイン メニュー** を使用したアニメーション</span><span class="sxs-lookup"><span data-stu-id="51c02-135">**Animations** using Main Menu</span></span>  
        :::image-end:::  
        
*   <span data-ttu-id="51c02-136">コマンド メニュー **を開く**</span><span class="sxs-lookup"><span data-stu-id="51c02-136">Open the **Command Menu**</span></span>  
    1.  <span data-ttu-id="51c02-137">「`Drawer: Show Animations`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="51c02-137">Type `Drawer: Show Animations`.</span></span>  
        
<span data-ttu-id="51c02-138">[アニメーション インスペクタ] が [コンソール] ツールの横 **に開** きます。</span><span class="sxs-lookup"><span data-stu-id="51c02-138">The Animation Inspector opens next to the **Console** tool.</span></span>  <span data-ttu-id="51c02-139">アニメーション インスペクターはドロワー ツールですから、任意の DevTools パネルからアニメーション インスペクターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51c02-139">Since the Animation Inspector is a Drawer tool, you may use the Animation Inspector from any DevTools panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="空のアニメーションインスペクター" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   <span data-ttu-id="51c02-141">空のアニメーションインスペクター</span><span class="sxs-lookup"><span data-stu-id="51c02-141">Empty Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="51c02-142">アニメーション インスペクターは、4 つのメイン セクション \(または panes\) にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-142">The Animation Inspector is grouped into four main sections \(or panes\).</span></span>  <span data-ttu-id="51c02-143">このガイドでは、各ウィンドウを次のように参照します。</span><span class="sxs-lookup"><span data-stu-id="51c02-143">This guide refers to each pane as follows:</span></span>  

| <span data-ttu-id="51c02-144">インデックス</span><span class="sxs-lookup"><span data-stu-id="51c02-144">Index</span></span> | <span data-ttu-id="51c02-145">ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="51c02-145">Pane</span></span> | <span data-ttu-id="51c02-146">説明</span><span class="sxs-lookup"><span data-stu-id="51c02-146">Description</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="51c02-147">1</span><span class="sxs-lookup"><span data-stu-id="51c02-147">1</span></span> | **<span data-ttu-id="51c02-148">コントロール</span><span class="sxs-lookup"><span data-stu-id="51c02-148">Controls</span></span>** | <span data-ttu-id="51c02-149">ここから、現在キャプチャされているすべてのアニメーション グループをクリアするか、現在選択されているアニメーション グループの速度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="51c02-149">From here you may clear all currently captured Animation Groups, or change the speed of the currently selected Animation Group.</span></span> |  
| <span data-ttu-id="51c02-150">2</span><span class="sxs-lookup"><span data-stu-id="51c02-150">2</span></span> | **<span data-ttu-id="51c02-151">概要</span><span class="sxs-lookup"><span data-stu-id="51c02-151">Overview</span></span>** | <span data-ttu-id="51c02-152">[詳細] ウィンドウでアニメーション グループを検査および変更するには、ここで [アニメーション グループ] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="51c02-152">Choose an Animation Group here to inspect and modify it in the **Details** pane.</span></span> |  
| <span data-ttu-id="51c02-153">3</span><span class="sxs-lookup"><span data-stu-id="51c02-153">3</span></span> | **<span data-ttu-id="51c02-154">タイムライン</span><span class="sxs-lookup"><span data-stu-id="51c02-154">Timeline</span></span>** | <span data-ttu-id="51c02-155">ここからアニメーションを一時停止して開始するか、アニメーション内の特定のポイントにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="51c02-155">Pause and start an animation from here, or jump to a specific point in the animation.</span></span> |  
| <span data-ttu-id="51c02-156">4</span><span class="sxs-lookup"><span data-stu-id="51c02-156">4</span></span> | **<span data-ttu-id="51c02-157">詳細</span><span class="sxs-lookup"><span data-stu-id="51c02-157">Details</span></span>** | <span data-ttu-id="51c02-158">現在選択されているアニメーション グループを検査および変更します。</span><span class="sxs-lookup"><span data-stu-id="51c02-158">Inspect and modify the currently selected Animation Group.</span></span> |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="注釈付きアニメーションインスペクター" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   <span data-ttu-id="51c02-160">注釈付きアニメーションインスペクター</span><span class="sxs-lookup"><span data-stu-id="51c02-160">Annotated Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="51c02-161">アニメーションをキャプチャするには、アニメーション インスペクターが開いている間にアニメーションをトリガーする操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="51c02-161">To capture an animation, just perform the interaction that triggers the animation while the Animation Inspector is open.</span></span>  <span data-ttu-id="51c02-162">ページの読み込み時にアニメーションがトリガーされた場合は、[アニメーション インスペクター] を開いた状態でページを更新して、アニメーションを検出します。</span><span class="sxs-lookup"><span data-stu-id="51c02-162">If an animation is triggered on page load, refresh the page with the Animation Inspector open to detect the animation.</span></span>  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <a name="inspect-animations"></a><span data-ttu-id="51c02-163">アニメーションの検査</span><span class="sxs-lookup"><span data-stu-id="51c02-163">Inspect animations</span></span>  

<span data-ttu-id="51c02-164">アニメーションをキャプチャした後、再生する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51c02-164">After you capture an animation, there are a few ways to replay it:</span></span>  

*   <span data-ttu-id="51c02-165">[概要] ウィンドウのサムネイルに **カーソルを合わせる** と、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-165">Hover on the thumbnail in the **Overview** pane to view a preview of it.</span></span>  
*   <span data-ttu-id="51c02-166">[概要] ウィンドウ**\([** 詳細] ウィンドウ\に表示される\*\*\*\*) から [アニメーション グループ] を選択し、再生**\(** 再生アイコン ![ \) アイコン ](../media/replay-button-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="51c02-166">Choose the Animation Group from the **Overview** pane \(so that it is displayed in the **Details** pane\) and choose the **replay** \(![replay icon](../media/replay-button-icon.msft.png)\) icon.</span></span>  <span data-ttu-id="51c02-167">アニメーションはビューポートで再生されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-167">The animation is replayed in the viewport.</span></span>  <span data-ttu-id="51c02-168">現在選択 **されているアニメーション** グループのプレビュー速度を変更するには、アニメーション速度 \( アニメーション速度アイコン ![ ](../media/animation-speed-buttons-icon.msft.png) \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="51c02-168">Choose the **animation speed** \(![animation speed icons](../media/animation-speed-buttons-icon.msft.png)\) icons to change the preview speed of the currently selected Animation Group.</span></span>  <span data-ttu-id="51c02-169">赤い垂直バーを使用して現在の位置を変更できます。</span><span class="sxs-lookup"><span data-stu-id="51c02-169">You may use the red vertical bar to change your current position.</span></span>  
*   <span data-ttu-id="51c02-170">赤い垂直バーを選択してドラッグして、ビューポート アニメーションをスクラブします。</span><span class="sxs-lookup"><span data-stu-id="51c02-170">Choose and drag the red vertical bar to scrub the viewport animation.</span></span>  
    
### <a name="view-animation-details"></a><span data-ttu-id="51c02-171">アニメーションの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="51c02-171">View animation details</span></span>  

<span data-ttu-id="51c02-172">アニメーション グループをキャプチャした後、[概要] ウィンドウからアニメーション グループを **選択** して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="51c02-172">After you capture an Animation Group, choose on it from the **Overview** pane to view the details.</span></span>  <span data-ttu-id="51c02-173">[詳細 **] ウィンドウ** では、各アニメーションに行が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="51c02-173">In the **Details** pane each individual animation is assigned the a row.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="アニメーション グループの詳細" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="51c02-175">アニメーション グループの詳細</span><span class="sxs-lookup"><span data-stu-id="51c02-175">Animation Group details</span></span>  
:::image-end:::  

<span data-ttu-id="51c02-176">アニメーションにカーソルを合わせると、ビューポート内でアニメーションが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-176">Hover on an animation to highlight it in the viewport.</span></span>  <span data-ttu-id="51c02-177">[要素] ツールでアニメーションを選択して **選択** します。</span><span class="sxs-lookup"><span data-stu-id="51c02-177">Choose the animation to select it in the **Elements** tool.</span></span>  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="アニメーションにカーソルを合わせると、ビューポートでアニメーションが強調表示されます。" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="51c02-179">アニメーションにカーソルを合わせると、ビューポートでアニメーションが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-179">Hover on the animation to highlight it in viewport</span></span>  
:::image-end:::  

<span data-ttu-id="51c02-180">アニメーションの左端の暗いセクションは定義です。</span><span class="sxs-lookup"><span data-stu-id="51c02-180">The leftmost, darker section of an animation is the definition.</span></span>  <span data-ttu-id="51c02-181">右側の色あせたセクションは、反復を表します。</span><span class="sxs-lookup"><span data-stu-id="51c02-181">The right, more faded section represents iterations.</span></span>  <span data-ttu-id="51c02-182">たとえば、次の図では、セクション 2 とセクション 3 はセクション 1 の反復を表します。</span><span class="sxs-lookup"><span data-stu-id="51c02-182">For example, in the following figure, sections two and three represent iterations of section one.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="アニメーションの反復の図" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   <span data-ttu-id="51c02-184">アニメーションの反復の図</span><span class="sxs-lookup"><span data-stu-id="51c02-184">Diagram of animation iterations</span></span>  
:::image-end:::  

<span data-ttu-id="51c02-185">2 つの要素に同じアニメーションが適用されている場合、アニメーション インスペクターは同じ色を要素に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="51c02-185">If two elements have the same animation applied, the Animation Inspector assigns the same color to the elements.</span></span>  <span data-ttu-id="51c02-186">色はランダムで、意味はありません。</span><span class="sxs-lookup"><span data-stu-id="51c02-186">The color is random and has no significance.</span></span>  <span data-ttu-id="51c02-187">たとえば、次の図では、2 つの要素と同じ `div.cwccw.earlier` アニメーション \( \) が適用されます。要素と同様 `div.cwccw.later` `spinrightleft` `div.ccwcw.earlier` `div.ccwcw.later` です。</span><span class="sxs-lookup"><span data-stu-id="51c02-187">For example, in the following figure, the two elements `div.cwccw.earlier` and `div.cwccw.later` have the same animation \(`spinrightleft`\) applied, as do the `div.ccwcw.earlier` and `div.ccwcw.later` elements.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="色分けされたアニメーション" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   <span data-ttu-id="51c02-189">色分けされたアニメーション</span><span class="sxs-lookup"><span data-stu-id="51c02-189">Color-coded animations</span></span>  
:::image-end:::  

## <a name="modify-animations"></a><span data-ttu-id="51c02-190">アニメーションの変更</span><span class="sxs-lookup"><span data-stu-id="51c02-190">Modify animations</span></span>  

<span data-ttu-id="51c02-191">アニメーション インスペクターを使用してアニメーションを変更するには、3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="51c02-191">There are three ways you are able to modify an animation with the Animation Inspector.</span></span>  

*   <span data-ttu-id="51c02-192">アニメーションの期間。</span><span class="sxs-lookup"><span data-stu-id="51c02-192">Animation duration.</span></span>  
*   <span data-ttu-id="51c02-193">キーフレームのタイミング。</span><span class="sxs-lookup"><span data-stu-id="51c02-193">Keyframe timings.</span></span>  
*   <span data-ttu-id="51c02-194">開始時間の遅延。</span><span class="sxs-lookup"><span data-stu-id="51c02-194">Start time delay.</span></span>  
    
<span data-ttu-id="51c02-195">次の図では、元のアニメーションが表されています。</span><span class="sxs-lookup"><span data-stu-id="51c02-195">In the following figure, the original animation is represented.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="変更前の元のアニメーション" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   <span data-ttu-id="51c02-197">変更前の元のアニメーション</span><span class="sxs-lookup"><span data-stu-id="51c02-197">Original animation before modification</span></span>  
:::image-end:::  

<span data-ttu-id="51c02-198">アニメーションの期間を変更するには、最初または最後の円を選択してドラッグします。</span><span class="sxs-lookup"><span data-stu-id="51c02-198">To change the duration of an animation, choose and drag the first or last circle.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="変更された期間" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   <span data-ttu-id="51c02-200">変更された期間</span><span class="sxs-lookup"><span data-stu-id="51c02-200">Modified duration</span></span>  
:::image-end:::  

<span data-ttu-id="51c02-201">アニメーションでキーフレーム ルールが定義されている場合、これらは白い内側の円として表されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-201">If the animation defines any keyframe rules, then these are represented as white inner circles.</span></span>  <span data-ttu-id="51c02-202">これらの 1 つを選択してドラッグして、キーフレームのタイミングを変更します。</span><span class="sxs-lookup"><span data-stu-id="51c02-202">Choose and drag one of these to change the timing of the keyframe.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="変更されたキーフレーム" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   <span data-ttu-id="51c02-204">変更されたキーフレーム</span><span class="sxs-lookup"><span data-stu-id="51c02-204">Modified keyframe</span></span>  
:::image-end:::  

<span data-ttu-id="51c02-205">アニメーションに遅延を追加するには、円以外の任意の場所を選択してドラッグします。</span><span class="sxs-lookup"><span data-stu-id="51c02-205">To add a delay to an animation, choose and drag it anywhere except the circles.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="変更された遅延" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   <span data-ttu-id="51c02-207">変更された遅延</span><span class="sxs-lookup"><span data-stu-id="51c02-207">Modified delay</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="51c02-208">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="51c02-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="51c02-209">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="51c02-209">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="51c02-210">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="51c02-210">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="51c02-212">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="51c02-212">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
