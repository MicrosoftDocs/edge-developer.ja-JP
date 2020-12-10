---
description: 3D ビューの概要とその使い方を説明します。
title: 3D View (3D ビュー)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bd91939a19f02a426834a85ef92eca388f8f1eda
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203971"
---
# <span data-ttu-id="23154-104">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="23154-104">3D View</span></span>  

<span data-ttu-id="23154-105">**3D ビュー**を使用して、[ドキュメントオブジェクトモデル (DOM)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動し、web アプリをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="23154-105">Use the **3D View** to debug your web app by navigating through the [Document Object Model (DOM)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  <span data-ttu-id="23154-106">この機能を使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="23154-106">With it, you may complete the following tasks.</span></span>  

*   [<span data-ttu-id="23154-107">3D 視点に変換された web ページを調べる</span><span class="sxs-lookup"><span data-stu-id="23154-107">Explore the web page translated into a 3D perspective</span></span>](#3d-dom)  
*   [<span data-ttu-id="23154-108">Z インデックススタックのコンテキストに基づいてデバッグする</span><span class="sxs-lookup"><span data-stu-id="23154-108">Debug based on z-index stacking context</span></span>](#z-index)  
*   [<span data-ttu-id="23154-109">3D ビューからレイヤーツール機能にアクセスして、合成レイヤーを表示する</span><span class="sxs-lookup"><span data-stu-id="23154-109">Access the Layers tool functionality from 3D View with composited layers</span></span>](#composited-layers)  
*   <span data-ttu-id="23154-110">[[DOM] ウィンドウ](#changing-your-view)または [ [z インデックス] ウィンドウ](#change-the-scope-of-your-exploration)で低優先メールの一部をクリアする</span><span class="sxs-lookup"><span data-stu-id="23154-110">[Clear some of the clutter on the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>  
*   <span data-ttu-id="23154-111">適切な DOM 問題または[z インデックスの問題](#z-index-color-type)[をデバッグするための配色パターンを選ぶ](#dom-color-type)</span><span class="sxs-lookup"><span data-stu-id="23154-111">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>  

<span data-ttu-id="23154-112">3D ビュープロジェクトの初期プロトタイプを調査して自分でコードを実行する場合は、「 [3D ビューのサンプル][GithubMicrosoftedgeDevtoolssamples3dview]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="23154-112">If you want to explore an early prototype of 3D View project and run the code yourself, navigate to [3D View Sample][GithubMicrosoftedgeDevtoolssamples3dview].</span></span>  

<span data-ttu-id="23154-113">左側には、次の3つのウィンドウが表示され、デバッグの操作に使用できます。</span><span class="sxs-lookup"><span data-stu-id="23154-113">On the left side, there are three panes that you may use for your debugging experience.</span></span>  

*   <span data-ttu-id="23154-114">[Z インデックス](#z-index)ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="23154-114">The [Z-index](#z-index) pane.</span></span>  <span data-ttu-id="23154-115">Z インデックスコンテキストを念頭に置いて、web アプリのさまざまな要素間を移動します。</span><span class="sxs-lookup"><span data-stu-id="23154-115">Navigate through the different elements in the web app with the z-index context in mind.</span></span>  <span data-ttu-id="23154-116">**Z インデックス**ウィンドウは既定のウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="23154-116">The **Z-index** pane is the default pane.</span></span>  
*   <span data-ttu-id="23154-117">[3D DOM](#3d-dom)ペイン。</span><span class="sxs-lookup"><span data-stu-id="23154-117">The [3D DOM](#3d-dom) pane.</span></span>  <span data-ttu-id="23154-118">すべての要素が簡単にアクセスできるように DOM を全体的に調べます。</span><span class="sxs-lookup"><span data-stu-id="23154-118">Explore the DOM as a whole with all the elements easily accessible.</span></span>  <span data-ttu-id="23154-119">ウィンドウにアクセスするには、[ **Z インデックス**] ウィンドウの横にある [ **DOM** ] ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="23154-119">To access the pane, choose the **DOM** pane next to the **Z-index** pane.</span></span>  
*   <span data-ttu-id="23154-120">[ [合成レイヤー](#composited-layers) ] ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="23154-120">The [Composited Layers](#composited-layers) pane.</span></span>  <span data-ttu-id="23154-121">他の3D 要素を追加して、レイヤーの観点からより包括的なエクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="23154-121">Add another 3D element to create a more comprehensive experience from a layers perspective.</span></span>  <span data-ttu-id="23154-122">ウィンドウにアクセスするには、 **DOM**ウィンドウの横にある [**合成レイヤー** ] ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="23154-122">To access the pane, choose the **Composited Layers** pane next to the **DOM** pane.</span></span>  
    
<span data-ttu-id="23154-123">右側では、キャンバスには、 [Z インデックス](#z-index)、 [3d DOM](#3d-dom)、または [合成レイヤー](#composited-layers)の選択内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23154-123">On the right side, the canvas displays your selections from the [Z-index](#z-index), [3D DOM](#3d-dom), or [Composited Layers](#composited-layers).</span></span>  

## <span data-ttu-id="23154-124">キャンバス内を移動する</span><span class="sxs-lookup"><span data-stu-id="23154-124">Navigating the canvas</span></span>  

:::image type="complex" source="../media/3d-view-canvas.msft.png" alt-text="3D ビューのキャンバス" lightbox="../media/3d-view-canvas.msft.png":::
   <span data-ttu-id="23154-126">3D ビューのキャンバス</span><span class="sxs-lookup"><span data-stu-id="23154-126">Canvas of 3D View</span></span>  
:::image-end:::  

### <span data-ttu-id="23154-127">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="23154-127">Keyboard shortcuts</span></span>  

*   <span data-ttu-id="23154-128">DOM を回転させる: 横方向に回転するには、[] キーを選び `left-arrow` `right-arrow` ます。</span><span class="sxs-lookup"><span data-stu-id="23154-128">Rotate the DOM:  To rotate horizontally, select the `left-arrow` and `right-arrow` keys.</span></span>  <span data-ttu-id="23154-129">垂直方向に回転させるには、とキーを選択し `up-arrow` `down-arrow` ます。</span><span class="sxs-lookup"><span data-stu-id="23154-129">To rotate vertically, select the `up-arrow` and `down-arrow` keys.</span></span>  
*   <span data-ttu-id="23154-130">DOM 内を移動する: 隣接する要素間を移動するには、要素を選択し、[and] キーを選び `up-arrow` `down-arrow` ます。</span><span class="sxs-lookup"><span data-stu-id="23154-130">Navigate the DOM:  To move through the adjacent elements, choose an element and select the `up-arrow` and `down-arrow` keys.</span></span>  

### <span data-ttu-id="23154-131">マウスコントロール</span><span class="sxs-lookup"><span data-stu-id="23154-131">Mouse controls</span></span>  

*   <span data-ttu-id="23154-132">DOM を回転させる: キャンバス領域を選択してドラッグします。</span><span class="sxs-lookup"><span data-stu-id="23154-132">Rotate the DOM:  Choose and drag around the canvas space.</span></span>  
*   <span data-ttu-id="23154-133">DOM でのパン: コンテキストメニューを開き (\ を右クリックし)、DOM を移動する方向にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="23154-133">Pan around the DOM:  Open the contextual menu \(right-click\) and drag in the direction you want the DOM to move.</span></span>  
*   <span data-ttu-id="23154-134">[ズーム]: タッチパッド上で2本の指をドラッグするか、マウスのスクロールホイールを使用します。</span><span class="sxs-lookup"><span data-stu-id="23154-134">Zoom:  Drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>  

### <span data-ttu-id="23154-135">オンスクリーンコントロール</span><span class="sxs-lookup"><span data-stu-id="23154-135">On-screen controls</span></span>  

:::image type="complex" source="../media/3d-view-controls-small.msft.png" alt-text="オンスクリーンコントロール" lightbox="../media/3d-view-controls-small.msft.png":::
   <span data-ttu-id="23154-137">オンスクリーンコントロール</span><span class="sxs-lookup"><span data-stu-id="23154-137">On-screen controls</span></span>  
:::image-end:::  

*   <span data-ttu-id="23154-138">キャンバスビューを元のビューにリセットします。 [ **カメラのリセット** ] ボタンを選択するか、[ **表示で要素をリセット] と [カメラを再中央揃え** ] (横向き更新アイコン \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="23154-138">Reset the canvas view to the original view:  Choose the **Reset camera** button, or choose the **Reset elements in view and re-center camera** \(sideways refresh icon\) button.</span></span>  
*   <span data-ttu-id="23154-139">キャンバスを更新します (たとえば、ブラウザーが変更された場合や、デバイスエミュレータービューに切り替えた場合など)。 [ **スナップショット** の再作成] ボタンを選択するか、[ **新しいスナップショットを撮る** ] ボタン ([更新] アイコン \) を選びます。</span><span class="sxs-lookup"><span data-stu-id="23154-139">Refresh the canvas \(for example, if the browser changed or you switched to a device emulator view\):  Choose the **Retake snapshot** button or choose the **Take new snapshot** button \(refresh icon\).</span></span>  

## <span data-ttu-id="23154-140">Z インデックス</span><span class="sxs-lookup"><span data-stu-id="23154-140">Z-index</span></span>  

:::image type="complex" source="../media/3d-view-z-index-view-box.msft.png" alt-text="Z インデックスビュー" lightbox="../media/3d-view-z-index-view-box.msft.png":::
   <span data-ttu-id="23154-142">Z インデックスビュー</span><span class="sxs-lookup"><span data-stu-id="23154-142">Z-index view</span></span>  
:::image-end:::  

<span data-ttu-id="23154-143">**Z インデックス**ウィンドウには**3d DOM**ウィンドウとの共有機能がありますが、ウィンドウにはウィンドウに固有の要素が残っています。</span><span class="sxs-lookup"><span data-stu-id="23154-143">While the **Z-index** pane has shared features with the **3D DOM** pane, the panes still have elements that are unique to the pane.</span></span>  

### <span data-ttu-id="23154-144">スタックコンテキストで要素を強調表示する</span><span class="sxs-lookup"><span data-stu-id="23154-144">Highlight elements with stacking context</span></span>  

<span data-ttu-id="23154-145">[ **スタックコンテキストを含む要素の強調表示** ] の設定を使用すると、キャンバスの要素の z インデックスタグをオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="23154-145">The **Highlight elements with stacking context** setting allows you to turn on \(and off\) the z-index tags for the elements on the canvas.</span></span>  <span data-ttu-id="23154-146">このチェックボックスは、既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="23154-146">The checkbox is chosen by default.</span></span>  

### <span data-ttu-id="23154-147">調査の範囲を変更する</span><span class="sxs-lookup"><span data-stu-id="23154-147">Change the scope of your exploration</span></span>  

<span data-ttu-id="23154-148">[ **すべての要素を表示** ] ボタンは、その下の設定を変更した後で DOM のすべての要素を表示する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="23154-148">The **Show all elements** button is the quickest way to display all the elements of the DOM after changing the settings below it.</span></span>  

<span data-ttu-id="23154-149">[ **スタックコンテキストを含む要素のみを表示** ] ボタンをクリックすると、スタックを重ねずに要素が削除され、簡単に移動できるように DOM がフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="23154-149">The **Show only elements with stacking context** button removes elements without stacking context and flattens the DOM for easier navigation.</span></span>  

<span data-ttu-id="23154-150">[ **選択した要素の分離** ] ボタンは、基本的には1つのボタンです。</span><span class="sxs-lookup"><span data-stu-id="23154-150">The **Isolate selected element** button is essentially three buttons in one.</span></span>  <span data-ttu-id="23154-151">[ **選択した要素を分離** する] ボタンの下には、[ **すべての親を表示** ] チェックボックスと [ **新しいスタックコンテキストを含む親のみを保持** ] チェックボックスの2つのチェックボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="23154-151">There are two checkboxes below the **Isolate selected element** button:  The **Show all parents** checkbox and **Keep only parents with new stacking context** checkbox.</span></span>  

<span data-ttu-id="23154-152">既定では、[ **すべての親を表示する** ] チェックボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="23154-152">The **Show all parents** checkbox is turned on by default.</span></span>  <span data-ttu-id="23154-153">要素とキャンバス上の親を表示するには、要素を選択し、[ **選択した要素の分離** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="23154-153">To display the element and any parents on the canvas, choose an element and choose the **Isolate selected element** button.</span></span>  

<span data-ttu-id="23154-154">キャンバスに新しいスタックコンテキストを持つ親を表示するには、[ **新しいスタックコンテキストで親のみを保持** する] 設定をオンにして、[ **選択した要素の分離** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="23154-154">To display the element and the parents that have a new stacking context on the canvas, turn on the **Keep only parents with new stacking context** setting and choose the **Isolate selected element** button.</span></span>  

<span data-ttu-id="23154-155">キャンバスで選択した要素を表示するには、[設定] の両方をオフにし、[ **選択した要素の分離** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="23154-155">To display the element you chose on the canvas, turn off both the settings and choose **Isolate selected element** button.</span></span>  

<span data-ttu-id="23154-156">[ **3D DOM** ] ウィンドウの下部で、[ **親と同じ描画順序で要素を非表示** にする] チェックボックスを探します。</span><span class="sxs-lookup"><span data-stu-id="23154-156">At the bottom of the **3D DOM** pane, locate the **Hide elements with the same paint order as their parent** checkbox.</span></span>  <span data-ttu-id="23154-157">チェックボックスをオンまたはオフにすると、選択した要素に基づいて要素が更新されます。</span><span class="sxs-lookup"><span data-stu-id="23154-157">Choosing and deselecting the checkbox refreshes the elements based on your choice.</span></span>  <span data-ttu-id="23154-158">選択すると、ペイントの順序を共有する要素が親にフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="23154-158">If chosen, elements that share paint order are flattened to the parent.</span></span>  

<span data-ttu-id="23154-159">このオプションは、より複雑な web ページをカンバスで作成するために使用されている低優先メールの一部をクリアすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="23154-159">The options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>  

### <span data-ttu-id="23154-160">Z インデックスの色の種類</span><span class="sxs-lookup"><span data-stu-id="23154-160">Z-index color type</span></span>  

<span data-ttu-id="23154-161">は、キャンバスで DOM に使用できるさまざまな視覚エフェクトです。</span><span class="sxs-lookup"><span data-stu-id="23154-161">The are the different visualizations you may use for the DOM in your canvas.</span></span>  <span data-ttu-id="23154-162">楽しいものでも、視覚エフェクトでも DOM をより効果的に視覚化できるため、DevTools にはさまざまな色と **背景色** のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="23154-162">Whether you use it for fun or because the visualizations help you visualize the DOM better, the DevTools have different colorways and a **Use background color** option.</span></span>  <span data-ttu-id="23154-163">**Z インデックス**ウィンドウでは、**紫色と白**、**背景色**が**3d DOM**ウィンドウで共有されます。</span><span class="sxs-lookup"><span data-stu-id="23154-163">The **Z-index** pane shares the **Purple to White** and **Background Color** with the **3D DOM** pane.</span></span>  <span data-ttu-id="23154-164">Z インデックスラベルのビジュアル要素が追加されている場合は、色のオプションの数が減るというフィードバックになります。</span><span class="sxs-lookup"><span data-stu-id="23154-164">Given the added visual element of the z-index labels, your feedback that led to a reduction in the number of color options.</span></span>  <span data-ttu-id="23154-165">新しい単純化により、z インデックスのデバッグエクスペリエンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="23154-165">The new simplicity improves the z-index debugging experience.</span></span>  <span data-ttu-id="23154-166">ラジオボタンを使用すると、オプションを切り替えて、色の種類を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="23154-166">The radio buttons allow you to toggle through the options and pick the color type.</span></span>  <span data-ttu-id="23154-167">色の種類は、プロジェクトに最も適した色または最も適切な色の種類のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="23154-167">The color type is either most appropriate for your project or one that you like the most.</span></span>  

## <span data-ttu-id="23154-168">3D DOM</span><span class="sxs-lookup"><span data-stu-id="23154-168">3D DOM</span></span>  

:::image type="complex" source="../media/3d-view-dom-purple-box.msft.png" alt-text="DOM ビュー" lightbox="../media/3d-view-dom-purple-box.msft.png":::
   <span data-ttu-id="23154-170">DOM ビュー</span><span class="sxs-lookup"><span data-stu-id="23154-170">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="23154-171">Z インデックスエクスペリエンスではなく、一般的なデバッグビューを実行する場合、 **3D dom** は dom の全体的な外観を提供します。</span><span class="sxs-lookup"><span data-stu-id="23154-171">If you want to take more of a general debugging view, rather than the z-index experience, the **3D DOM** gives an overall look of the DOM.</span></span>  <span data-ttu-id="23154-172">Z インデックスコンテキストが削除されたため、DOM はより厳密かつ明確に積み重ねられます。</span><span class="sxs-lookup"><span data-stu-id="23154-172">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span>  <span data-ttu-id="23154-173">**3D DOM**ウィンドウの機能は似ていますが、いくつかの微妙な点があります。</span><span class="sxs-lookup"><span data-stu-id="23154-173">The **3D DOM** pane has similar functionality, but there are a few nuances.</span></span>  

### <span data-ttu-id="23154-174">ビューを変更する</span><span class="sxs-lookup"><span data-stu-id="23154-174">Changing your view</span></span>  

<span data-ttu-id="23154-175">[ **3D DOM** ] ウィンドウでは、[ **選択した要素の分離** ] ボタンには [ **子の追加** ] と [親の **追加** ] チェックボックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="23154-175">On the **3D DOM** pane, the **Isolate selected element** button has **Include children** and **Include parents** checkboxes.</span></span>  <span data-ttu-id="23154-176">両方のチェックボックスは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="23154-176">Both checkboxes are turned on by default.</span></span>  <span data-ttu-id="23154-177">つまり、要素を選択した後に [ **選択した要素の分離** ] ボタンを選択すると、キャンバスには、選択した要素、要素の親、要素の子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23154-177">That means if you choose the **Isolate selected element** button after you choose an element, the canvas displays the chosen element, the parents of the element, and the children of the element.</span></span>  <span data-ttu-id="23154-178">[子を **含める** ] 設定をオフにして、[ **選択した要素の分離** ] ボタンをもう一度選択すると、選択した要素とその親が要素の親として表示されます。</span><span class="sxs-lookup"><span data-stu-id="23154-178">Turn off the **Include children** setting and choose the **Isolate selected element** button again to display the chosen element and the parents of the element.</span></span>  <span data-ttu-id="23154-179">[ **子を含める** ] 設定をオンにして、[ **親を含む** ] 設定をオフにした場合、[ **選択した要素の分離** ] ボタンを選択すると、キャンバスに要素とすべての子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23154-179">If you turn on the **Include children** setting and turn off the **Include parents** setting and then choose the **Isolate selected element** button, the canvas displays the element and any children.</span></span>  <span data-ttu-id="23154-180">両方の設定をオフにして、[ **選択した要素を分離** ] ボタンを選択した場合、キャンバスには以前に選択した要素のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23154-180">If you turn off both settings and choose the **Isolate selected element** button, the canvas only displays the element you previously chose.</span></span>  

<span data-ttu-id="23154-181">横に数字が表示された [ **入れ子のレベル]** という名前のコントロールウィンドウのスライダー。</span><span class="sxs-lookup"><span data-stu-id="23154-181">A slider on the control pane named **Nesting level for page** with a number next to it.</span></span>  <span data-ttu-id="23154-182">この番号は、ドキュメントのレイヤー数を示します。</span><span class="sxs-lookup"><span data-stu-id="23154-182">The number indicates the number of layers for the document.</span></span>  <span data-ttu-id="23154-183">スライダーを左にドラッグすると、入れ子のレベルが [はがすか] に設定されたままになるまで、一番外側のレイヤーが消え `1` ます。</span><span class="sxs-lookup"><span data-stu-id="23154-183">Dragging the slider to the left causes the outermost layers to peel away until you are left with a nesting level set to `1`, which displays only the furthest back element in the DOM.</span></span>  <span data-ttu-id="23154-184">低優先メールを削除するには、スライダーをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="23154-184">To remove some of the clutter, drag the slider.</span></span>  <span data-ttu-id="23154-185">下位レベルで発生していることについて詳しく見ていくことができます。</span><span class="sxs-lookup"><span data-stu-id="23154-185">It helps you get a closer look at what is happening in the lower levels.</span></span>  

### <span data-ttu-id="23154-186">DOM 色の種類</span><span class="sxs-lookup"><span data-stu-id="23154-186">DOM color type</span></span>  

<span data-ttu-id="23154-187">**3D DOM**ウィンドウには、次のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23154-187">The **3D DOM** pane displays the following options.</span></span>  

*   <span data-ttu-id="23154-188">3つの異なる色の使い方。</span><span class="sxs-lookup"><span data-stu-id="23154-188">Three different colorways.</span></span>  
    *   **<span data-ttu-id="23154-189">ヒートマップ-紫 ~ 白</span><span class="sxs-lookup"><span data-stu-id="23154-189">Heatmap - Purple to White</span></span>**  
    *   **<span data-ttu-id="23154-190">ヒートマップ-青から黄</span><span class="sxs-lookup"><span data-stu-id="23154-190">Heatmap - Blue to Yellow</span></span>**  
    *   **<span data-ttu-id="23154-191">ヒートマップ-レインボー</span><span class="sxs-lookup"><span data-stu-id="23154-191">Heatmap - Rainbow</span></span>**  
*   **<span data-ttu-id="23154-192">背景色を使用する</span><span class="sxs-lookup"><span data-stu-id="23154-192">Use background color</span></span>**  
*   **<span data-ttu-id="23154-193">画面のテクスチャを使用する</span><span class="sxs-lookup"><span data-stu-id="23154-193">Use screen texture</span></span>**  
    
<span data-ttu-id="23154-194">[ **画面のテクスチャを使用** ] オプションを使うと、デバッグエクスペリエンスにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="23154-194">The **Use screen texture** option adds context to your debugging experience.</span></span>  <span data-ttu-id="23154-195">Web ページのコンテンツを要素に直接表示します。</span><span class="sxs-lookup"><span data-stu-id="23154-195">It directly displays the content from the webpage onto the elements.</span></span>  

## <span data-ttu-id="23154-196">合成レイヤー</span><span class="sxs-lookup"><span data-stu-id="23154-196">Composited layers</span></span>

:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="合成レイヤーウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="23154-198">**合成レイヤー** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="23154-198">**Composited Layers** pane</span></span>
:::image-end:::  

<span data-ttu-id="23154-199">[ **合成レイヤー** ] ウィンドウを使用すると、コンテキストを変更せずに、 **レイヤー** ツールの要素を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="23154-199">The **Composited Layers** pane opens the elements of the **Layers** tool without changing contexts.</span></span>  <span data-ttu-id="23154-200">各レイヤーの詳細情報にアクセスすることができ、スクロールの **rects** と **ペイント**が遅くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="23154-200">You may still access the details of each of the layers and have the **Slow scroll rects** and **Paint**.</span></span>

## <span data-ttu-id="23154-201">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="23154-201">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="23154-202">Microsoft Edge Devtools チームは、ユーザーのフィードバックに基づいて、UI を操作し、3D ビューに機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="23154-202">The Microsoft Edge Devtools team is working on the UI and adding more functionality to the 3D View based on your feedback.</span></span>  <span data-ttu-id="23154-203">Microsoft Edge DevTools の向上に役立つフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="23154-203">Send your feedback to help improve the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="23154-204">Devtools の [**フィードバックの送信**] アイコンを選択するか、 `Alt` + `Shift` + `I` Windows/Linux または macOS を選択 `Option` + `Shift` + `I` して、devtools のフィードバックまたは機能の要求を入力します。</span><span class="sxs-lookup"><span data-stu-id="23154-204">Choose the **Send Feedback** icon in the DevTools or select `Alt`+`Shift`+`I` on Windows/Linux or `Option`+`Shift`+`I` on macOS and enter any feedback or feature requests you have for the DevTools.</span></span>  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D ビュー-MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメントオブジェクトモデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z インデックス |MDN"  
