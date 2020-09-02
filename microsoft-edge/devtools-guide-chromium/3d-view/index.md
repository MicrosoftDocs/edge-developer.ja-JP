---
description: 3D ビューの概要とその使い方を説明します。
title: 3D View (3D ビュー)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ba1125654c46be6ef4da99efc9ba027ba5e40672
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986081"
---
# <span data-ttu-id="2b470-104">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="2b470-104">3D View</span></span>  

<span data-ttu-id="2b470-105">**3D ビュー**を使用して、[ドキュメントオブジェクトモデル (DOM)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="2b470-105">Use the **3D View** to debug your web application by navigating through the [Document Object Model (DOM)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  <span data-ttu-id="2b470-106">これにより、次のタスクを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2b470-106">With it you are able to perform the following tasks.</span></span>  

*   [<span data-ttu-id="2b470-107">3D 視点に変換された web ページを調べる</span><span class="sxs-lookup"><span data-stu-id="2b470-107">Explore the web page translated into a 3D perspective</span></span>](#3d-dom)  
*   [<span data-ttu-id="2b470-108">Z インデックススタックのコンテキストに基づいてデバッグする</span><span class="sxs-lookup"><span data-stu-id="2b470-108">Debug based on z-index stacking context</span></span>](#z-index)  
*   <span data-ttu-id="2b470-109">[[DOM] ウィンドウ](#changing-your-view)または [ [z インデックス] ウィンドウ](#change-the-scope-of-your-exploration)で低優先メールの一部をクリアする</span><span class="sxs-lookup"><span data-stu-id="2b470-109">[Clear some of the clutter on the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>  
*   <span data-ttu-id="2b470-110">適切な DOM 問題または[z インデックスの問題](#z-index-color-type)[をデバッグするための配色パターンを選ぶ](#dom-color-type)</span><span class="sxs-lookup"><span data-stu-id="2b470-110">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>  

<span data-ttu-id="2b470-111">3D ビュープロジェクトの初期プロトタイプを調査して自分でコードを実行する場合は、「 [3D ビューのサンプル][GithubMicrosoftedgeDevtoolssamples3dview]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b470-111">If you want to explore an early prototype of 3D View project and run the code yourself, see [3D View Sample][GithubMicrosoftedgeDevtoolssamples3dview].</span></span>   

<span data-ttu-id="2b470-112">左側に2つのウィンドウがあり、これを使ってデバッグ操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b470-112">On the left side, there are two panes that you are able to use for your debugging experience.</span></span>  

1.  <span data-ttu-id="2b470-113">[Z インデックス](#z-index)ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2b470-113">The [Z-index](#z-index) pane.</span></span>  <span data-ttu-id="2b470-114">Z インデックスコンテキストを念頭に置いて、web アプリケーションのさまざまな要素間を移動します。</span><span class="sxs-lookup"><span data-stu-id="2b470-114">Navigate through the different elements in the web application with the z-index context in mind.</span></span>  <span data-ttu-id="2b470-115">**Z インデックス**ウィンドウは既定のウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="2b470-115">The **Z-index** pane is the default pane.</span></span>  
1.  <span data-ttu-id="2b470-116">[3D DOM](#3d-dom)ペイン。</span><span class="sxs-lookup"><span data-stu-id="2b470-116">The [3D DOM](#3d-dom) pane.</span></span>  <span data-ttu-id="2b470-117">DOM をすべての要素ですぐに確認できます。</span><span class="sxs-lookup"><span data-stu-id="2b470-117">Explore the DOM as a whole with all the elements at your fingertips.</span></span>  <span data-ttu-id="2b470-118">ウィンドウにアクセスするには、[ **Z インデックス**] ウィンドウの横にある [ **DOM** ] ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b470-118">To access the pane, select on the **DOM** pane next to the **Z-index** pane.</span></span>  
    
<span data-ttu-id="2b470-119">右側では、キャンバスには、 [Z インデックス](#z-index) または [3d DOM](#3d-dom)の選択内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-119">On the right side, the canvas displays your selections from the [Z-index](#z-index) or [3D DOM](#3d-dom).</span></span>  

## <span data-ttu-id="2b470-120">キャンバス内を移動する</span><span class="sxs-lookup"><span data-stu-id="2b470-120">Navigating the canvas</span></span>  

:::image type="complex" source="../media/canvas.png" alt-text="3D ビューのキャンバス" lightbox="../media/canvas.png":::
   <span data-ttu-id="2b470-122">3D ビューのキャンバス</span><span class="sxs-lookup"><span data-stu-id="2b470-122">Canvas of 3D View</span></span>  
:::image-end:::  

### <span data-ttu-id="2b470-123">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="2b470-123">Keyboard shortcuts</span></span>  

*   <span data-ttu-id="2b470-124">DOM を回転させる: 水平方向に回転するには、 `left-arrow` キーとキーを押し `right-arrow` ます。</span><span class="sxs-lookup"><span data-stu-id="2b470-124">Rotate the DOM:  To rotate horizontally, press the `left-arrow` and `right-arrow` keys.</span></span>  <span data-ttu-id="2b470-125">縦方向に回転するには、 `up-arrow` キーとキーを押し `down-arrow` ます。</span><span class="sxs-lookup"><span data-stu-id="2b470-125">To rotate vertically, press the `up-arrow` and `down-arrow` keys.</span></span>  
*   <span data-ttu-id="2b470-126">DOM 内を移動する: 隣接する要素間を移動するには、要素を選択して、 `up-arrow` キーとキーを押し `down-arrow` ます。</span><span class="sxs-lookup"><span data-stu-id="2b470-126">Navigate the DOM:  To move through the adjacent elements, select an element and press the `up-arrow` and `down-arrow` keys.</span></span>  

### <span data-ttu-id="2b470-127">マウスコントロール</span><span class="sxs-lookup"><span data-stu-id="2b470-127">Mouse controls</span></span>  

*   <span data-ttu-id="2b470-128">DOM を回転させる: キャンバス領域を選択してドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2b470-128">Rotate the DOM:  Select and drag around the canvas space.</span></span>  
*   <span data-ttu-id="2b470-129">DOM でのパン: コンテキストメニューを開き (\ を右クリックし)、DOM を移動する方向にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2b470-129">Pan around the DOM:  Open the contextual menu \(right-click\) and drag in the direction you want the DOM to move.</span></span>  
*   <span data-ttu-id="2b470-130">[ズーム]: タッチパッド上で2本の指をドラッグするか、マウスのスクロールホイールを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b470-130">Zoom:  Drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>  

### <span data-ttu-id="2b470-131">オンスクリーンコントロール</span><span class="sxs-lookup"><span data-stu-id="2b470-131">On-screen controls</span></span>  

:::image type="complex" source="../media/controls-small.png" alt-text="オンスクリーンコントロール" lightbox="../media/controls-small.png":::
   <span data-ttu-id="2b470-133">オンスクリーンコントロール</span><span class="sxs-lookup"><span data-stu-id="2b470-133">On-screen controls</span></span>  
:::image-end:::  

*   <span data-ttu-id="2b470-134">キャンバスビューを元のビューにリセットします。 [ **カメラのリセット** ] ボタンを選択するか、[ **表示で要素をリセット] と [カメラを再中央揃え** ] (横向き更新アイコン \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b470-134">Reset the canvas view to the original view:  Select the **Reset camera** button, or select the **Reset elements in view and re-center camera** \(sideways refresh icon\) button.</span></span>  
*   <span data-ttu-id="2b470-135">キャンバスを更新します (たとえば、ブラウザーが変更された場合、またはデバイスエミュレータービューに切り替えた場合など)。 [ **スナップショット** の再 **作成** ] ボタンを選択するか、([更新] アイコン \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b470-135">Refresh the canvas \(for example, if the browser changed or you switched to a device emulator view\):  Select the **Retake snapshot** button or select the **Take new snapshot** button \(refresh icon\).</span></span>  

## <span data-ttu-id="2b470-136">Z インデックス</span><span class="sxs-lookup"><span data-stu-id="2b470-136">Z-index</span></span>  

:::image type="complex" source="../media/z-index-view-box.png" alt-text="Z インデックスビュー" lightbox="../media/z-index-view-box.png":::
   <span data-ttu-id="2b470-138">Z インデックスビュー</span><span class="sxs-lookup"><span data-stu-id="2b470-138">Z-index view</span></span>  
:::image-end:::  

<span data-ttu-id="2b470-139">**Z インデックス**ウィンドウには**3d DOM**ウィンドウとの共有機能がありますが、ウィンドウにはウィンドウに固有の要素が残っています。</span><span class="sxs-lookup"><span data-stu-id="2b470-139">While the **Z-index** pane has shared features with the **3D DOM** pane, the panes still have elements that are unique to the pane.</span></span>  

### <span data-ttu-id="2b470-140">スタックコンテキストで要素を強調表示する</span><span class="sxs-lookup"><span data-stu-id="2b470-140">Highlight elements with stacking context</span></span>  

<span data-ttu-id="2b470-141">[ **スタックコンテキストを含む要素の強調表示** ] の設定を使用すると、キャンバスの要素の z インデックスタグをオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b470-141">The **Highlight elements with stacking context** setting allows you to turn on \(and off\) the z-index tags for the elements on the canvas.</span></span>  <span data-ttu-id="2b470-142">既定では、このチェックボックスはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="2b470-142">The checkbox is selected by default.</span></span>  

### <span data-ttu-id="2b470-143">調査の範囲を変更する</span><span class="sxs-lookup"><span data-stu-id="2b470-143">Change the scope of your exploration</span></span>  

<span data-ttu-id="2b470-144">[ **すべての要素を表示** ] ボタンは、下の設定を変更した後で DOM のすべての要素を表示するための最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="2b470-144">The **Show all elements** button is the quickest way to display all the elements of the DOM after changing the settings below.</span></span>  

<span data-ttu-id="2b470-145">[ **スタックコンテキストを含む要素のみを表示** ] ボタンをクリックすると、スタックを重ねずに要素が削除され、簡単に移動できるように DOM がフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-145">The **Show only elements with stacking context** button removes elements without stacking context and flattens the DOM for easier navigation.</span></span>  

<span data-ttu-id="2b470-146">[ **選択した要素の分離** ] ボタンは、基本的には1つのボタンです。</span><span class="sxs-lookup"><span data-stu-id="2b470-146">The **Isolate selected element** button is essentially three buttons in one.</span></span>  <span data-ttu-id="2b470-147">[ **選択した要素を分離** する] ボタンの下には、[ **すべての親を表示** ] チェックボックスと [ **新しいスタックコンテキストを含む親のみを保持** ] チェックボックスの2つのチェックボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="2b470-147">There are two checkboxes below the **Isolate selected element** button:  The **Show all parents** checkbox and **Keep only parents with new stacking context** checkbox.</span></span>  

<span data-ttu-id="2b470-148">既定では、[ **すべての親を表示** ] チェックボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="2b470-148">The **Show all parents** checkbox is selected by default.</span></span>  <span data-ttu-id="2b470-149">[キャンバス] ウィンドウで要素を選択し、[ **選択した要素を分離** ] ボタンを選択すると、キャンバスには要素と親が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-149">If you select an element on the canvas pane and select **Isolate selected element** button, the canvas only displays the element and any parents.</span></span>  

<span data-ttu-id="2b470-150">[ **新しいスタックコンテキストで親のみを保持** する] チェックボックスをオンにして、[ **選択した要素を分離** ] ボタンを選択した場合、キャンバスには、新しいスタックコンテキストを持つ親要素のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-150">If you select the **Keep only parents with new stacking context** checkbox, and select **Isolate selected element** button, the canvas only displays the element and the parents that have a new stacking context.</span></span>  

<span data-ttu-id="2b470-151">両方のチェックボックスをオフにして、[ **選択した要素を分離** ] ボタンを選択した場合、キャンバスには最初の場所で選択した要素のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-151">If you deselect both of the checkboxes and select **Isolate selected element** button, the canvas only displays the element you chose in the first place.</span></span>  

<span data-ttu-id="2b470-152">**3D DOM**パネルの一番下で、[**親と同じ描画順序で要素を非表示**にする] チェックボックスを探します。</span><span class="sxs-lookup"><span data-stu-id="2b470-152">At the very bottom of the **3D DOM** panel, locate the **Hide elements with the same paint order as their parent** checkbox.</span></span>  <span data-ttu-id="2b470-153">チェックボックスをオンまたはオフにすると、選択した要素に基づいて要素が更新されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-153">Selecting and deselecting the checkbox refreshes the elements based on your selection.</span></span>  <span data-ttu-id="2b470-154">選択すると、ペイントの順序を共有する要素が親にフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-154">If selected, elements that share paint order are flattened to the parent.</span></span>  

<span data-ttu-id="2b470-155">このオプションは、より複雑な web ページをカンバスで作成するために使用されている低優先メールの一部をクリアすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="2b470-155">The options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>  

### <span data-ttu-id="2b470-156">Z インデックスの色の種類</span><span class="sxs-lookup"><span data-stu-id="2b470-156">Z-index color type</span></span>  

<span data-ttu-id="2b470-157">は、キャンバスで DOM に使用できるさまざまな視覚エフェクトです。</span><span class="sxs-lookup"><span data-stu-id="2b470-157">The are the different visualizations you may use for the DOM in your canvas.</span></span>  <span data-ttu-id="2b470-158">楽しく使う場合でも、視覚エフェクトでも DOM をより効果的に視覚化できるため、DevTools には3種類の色と **背景色** の設定があります。</span><span class="sxs-lookup"><span data-stu-id="2b470-158">Whether you use it for fun or because the visualizations help you visualize the DOM better, The DevTools has three different colorways as well as a **background color** setting.</span></span>  <span data-ttu-id="2b470-159">ラジオボタンを使用すると、オプションを切り替えたり、プロジェクトに最も適した色の種類を選択したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b470-159">The radio buttons allow you to toggle through the options and pick the color type most appropriate for your project \(or that you like the most\).</span></span>  

## <span data-ttu-id="2b470-160">3D DOM</span><span class="sxs-lookup"><span data-stu-id="2b470-160">3D DOM</span></span>  

:::image type="complex" source="../media/dom-purple-box.png" alt-text="DOM ビュー" lightbox="../media/dom-purple-box.png":::
   <span data-ttu-id="2b470-162">DOM ビュー</span><span class="sxs-lookup"><span data-stu-id="2b470-162">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="2b470-163">Z インデックスエクスペリエンスではなく、一般的なデバッグビューを実行する場合、 **3D dom** は dom の全体的な外観を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b470-163">If you want to take more of a general debugging view, rather than the z-index experience, the **3D DOM** gives an overall look of the DOM.</span></span>  <span data-ttu-id="2b470-164">Z インデックスコンテキストが削除されたため、DOM はより厳密かつ明確に積み重ねられます。</span><span class="sxs-lookup"><span data-stu-id="2b470-164">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span>  <span data-ttu-id="2b470-165">**3D DOM**ウィンドウの機能は似ていますが、いくつかの微妙な点があります。</span><span class="sxs-lookup"><span data-stu-id="2b470-165">The **3D DOM** pane has similar functionality, but there are a few nuances.</span></span>  

### <span data-ttu-id="2b470-166">ビューを変更する</span><span class="sxs-lookup"><span data-stu-id="2b470-166">Changing your view</span></span>  

<span data-ttu-id="2b470-167">[ **3D DOM** ] ウィンドウでは、[ **選択した要素の分離** ] ボタンには [ **子の追加** ] と [親の **追加** ] チェックボックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b470-167">On the **3D DOM** pane, the **Isolate selected element** button has **Include children** and **Include parents** checkboxes.</span></span>  <span data-ttu-id="2b470-168">既定では、両方のチェックボックスがオンになっています。キャンバス上の要素を選択した後に [ **選択した要素の分離** ] ボタンを選ぶと、選択した要素、要素の親、要素の子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-168">By default both checkboxes are selected, which means that selecting the **Isolate selected element** button after selecting an element on the canvas should display the element chosen, the parents of the element, and the children of the element.</span></span>  <span data-ttu-id="2b470-169">[ **子を含める** ] チェックボックスをオフにして、[ **選択した要素を分離** ] ボタンをもう一度選択すると、選んだ要素と要素の親が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-169">Deselecting the **Include children** checkbox and selecting the **Isolate selected element** button again should display the selected element and the parents of the element.</span></span>  <span data-ttu-id="2b470-170">[**子を含める**] チェックボックスをオンにして、[**選択した要素を分離**] ボタンをオンにする前に、[親を**含む**] チェックボックスをオフにした場合、キャンバスには要素と子が表示されます</span><span class="sxs-lookup"><span data-stu-id="2b470-170">If you select the **Include children** checkbox and deselect the **Include parents** checkbox before selecting **Isolate selected element** button, the canvas then displays the element and any children.</span></span>  <span data-ttu-id="2b470-171">両方のチェックボックスをオフにして、[ **選択した要素を分離** ] ボタンを選択した場合、キャンバスには前に選択した要素のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-171">If you deselect both checkboxes and select **Isolate selected element** button, the canvas only displays the element you previously selected.</span></span>  

<span data-ttu-id="2b470-172">コントロールウィンドウのスライダーは、横に数字が表示された **ページの [レベルのネスト]** というタイトルです。</span><span class="sxs-lookup"><span data-stu-id="2b470-172">A slider on the control pane titled **Nesting level for page** with a number next to it.</span></span>  <span data-ttu-id="2b470-173">この番号は、ドキュメントのレイヤー数を示します。</span><span class="sxs-lookup"><span data-stu-id="2b470-173">The number indicates the number of layers for the document.</span></span>  <span data-ttu-id="2b470-174">スライダーを左にドラッグすると、入れ子レベルが1に設定されているため、一番外側のレイヤーがはがすかます。これにより、DOM 内の最も遠いバック要素のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b470-174">Dragging the slider to the left causes the outermost layers to peel away until you are left with a nesting level set to 1, which displays only the furthest back element in the DOM.</span></span>  <span data-ttu-id="2b470-175">スライダーをドラッグすると、低優先メールの一部を削除することができます。これは、下位レベルで何が起こっているのかをもっと詳しく確認しようとしている場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="2b470-175">Dragging the slider allows you to remove some of the clutter if you are trying to get a closer look at what is happening in the lower levels.</span></span>  

### <span data-ttu-id="2b470-176">DOM 色の種類</span><span class="sxs-lookup"><span data-stu-id="2b470-176">DOM color type</span></span>  

<span data-ttu-id="2b470-177">**ヒートマップ-紫から白**、**ヒートマップ ~ イエロー**、**ヒートマップ-レインボー**、および**背景色を使用**するラジオボタンに加えて、画面のテクスチャも**使用**します。</span><span class="sxs-lookup"><span data-stu-id="2b470-177">In addition to the **Heatmap - Purple to White**, **Heatmap - Blue to Yellow**, **Heatmap - Rainbow**, and **Use background color** radio buttons, there is **Use screen texture**.</span></span>  <span data-ttu-id="2b470-178">画面のテクスチャは、web ページのコンテンツを要素に直接表示することで、デバッグエクスペリエンスにコンテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b470-178">The screen texture adds context to your debugging experience by displaying the content from the web page directly onto the elements.</span></span>  <span data-ttu-id="2b470-179">[ **3D DOM** ] ウィンドウでは、[  **色の種類** ] の設定はまだ進行中です。一部の web サイトには、3d ビューでの画面テクスチャのレンダリングが困難であるためです。</span><span class="sxs-lookup"><span data-stu-id="2b470-179">On the **3D DOM** pane, the  **color type** setting is still a work in progress, since some websites have a harder time rendering screen texture in the 3D View.</span></span>  

## <span data-ttu-id="2b470-180">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="2b470-180">Getting in touch with the Microsoft Edge DevTools team</span></span>

<span data-ttu-id="2b470-181">Microsoft Edge Devtools チームは、ユーザーからの要求に基づいて、UI を操作し、3D ビューに機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="2b470-181">The Microsoft Edge Devtools team is working on the UI and adding more functionality to the 3D View based on asks from users like you.</span></span>  <span data-ttu-id="2b470-182">Microsoft Edge DevTools の向上に役立てるため、フィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="2b470-182">Please send your feedback to help improve the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="2b470-183">Devtools でフィードバックアイコンを選択するか、 `Alt` + `Shift` + `I` \ (Windows \) キーを押すか、 `Option` + `Shift` + `I` \ (macOS \) キーを押して、devtools のフィードバックまたは機能要求を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b470-183">Simply select the feedback icon in the DevTools or press `Alt`+`Shift`+`I` \(Windows\) or press `Option`+`Shift`+`I` \(macOS\) and enter any feedback or feature requests you have for the DevTools.</span></span>  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D ビュー-MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメントオブジェクトモデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z インデックス |MDN"  
