---
description: すべての 3D ビューとそれを使用する方法について。
title: 3D View (3D ビュー)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bd91939a19f02a426834a85ef92eca388f8f1eda
ms.sourcegitcommit: 5e218b24fb21fcfa9c82b99f17373fed1ba5a21c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "11203971"
---
# <a name="3d-view"></a><span data-ttu-id="edda3-104">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="edda3-104">3D View</span></span>  

<span data-ttu-id="edda3-105">**3D ビューを使用して**、ドキュメント オブジェクト モデル[(DOM)][MDNDocumentObjectModel]または[z-index][MDNZIndex]スタック コンテキストを移動して Web アプリをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="edda3-105">Use the **3D View** to debug your web app by navigating through the [Document Object Model (DOM)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  <span data-ttu-id="edda3-106">この機能を使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="edda3-106">With it, you may complete the following tasks.</span></span>  

*   [<span data-ttu-id="edda3-107">3D パースペクティブに翻訳された Web ページを確認する</span><span class="sxs-lookup"><span data-stu-id="edda3-107">Explore the web page translated into a 3D perspective</span></span>](#3d-dom)  
*   [<span data-ttu-id="edda3-108">z-index スタック コンテキストに基づくデバッグ</span><span class="sxs-lookup"><span data-stu-id="edda3-108">Debug based on z-index stacking context</span></span>](#z-index)  
*   [<span data-ttu-id="edda3-109">複合レイヤーを使用して 3D ビューから Layers ツールの機能にアクセスする</span><span class="sxs-lookup"><span data-stu-id="edda3-109">Access the Layers tool functionality from 3D View with composited layers</span></span>](#composited-layers)  
*   <span data-ttu-id="edda3-110">[DOM ウィンドウまたは z-index ウィンドウ](#changing-your-view) の混乱 [の一部をクリアする](#change-the-scope-of-your-exploration)</span><span class="sxs-lookup"><span data-stu-id="edda3-110">[Clear some of the clutter on the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>  
*   <span data-ttu-id="edda3-111">[DOM の問題や z-index の](#dom-color-type) 問題を最適にデバッグするために [配色を選ぶ](#z-index-color-type)</span><span class="sxs-lookup"><span data-stu-id="edda3-111">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>  

<span data-ttu-id="edda3-112">3D View プロジェクトの初期プロトタイプを確認し、コードを自分で実行する場合は [、[3D ビュー][GithubMicrosoftedgeDevtoolssamples3dview]サンプル] に移動します。</span><span class="sxs-lookup"><span data-stu-id="edda3-112">If you want to explore an early prototype of 3D View project and run the code yourself, navigate to [3D View Sample][GithubMicrosoftedgeDevtoolssamples3dview].</span></span>  

<span data-ttu-id="edda3-113">左側には、デバッグ エクスペリエンスに使用できる 3 つのウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="edda3-113">On the left side, there are three panes that you may use for your debugging experience.</span></span>  

*   <span data-ttu-id="edda3-114">[Z インデックス ウィンドウ](#z-index)。</span><span class="sxs-lookup"><span data-stu-id="edda3-114">The [Z-index](#z-index) pane.</span></span>  <span data-ttu-id="edda3-115">z-index コンテキストを念頭に置いて、Web アプリ内のさまざまな要素を移動します。</span><span class="sxs-lookup"><span data-stu-id="edda3-115">Navigate through the different elements in the web app with the z-index context in mind.</span></span>  <span data-ttu-id="edda3-116">**Z インデックス ウィンドウは**既定のウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="edda3-116">The **Z-index** pane is the default pane.</span></span>  
*   <span data-ttu-id="edda3-117">[3D DOM](#3d-dom)ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="edda3-117">The [3D DOM](#3d-dom) pane.</span></span>  <span data-ttu-id="edda3-118">すべての要素に簡単にアクセスできる DOM 全体を探索します。</span><span class="sxs-lookup"><span data-stu-id="edda3-118">Explore the DOM as a whole with all the elements easily accessible.</span></span>  <span data-ttu-id="edda3-119">ウィンドウにアクセスするには **、Z** インデックス ウィンドウの横にある **DOM ウィンドウを選択** します。</span><span class="sxs-lookup"><span data-stu-id="edda3-119">To access the pane, choose the **DOM** pane next to the **Z-index** pane.</span></span>  
*   <span data-ttu-id="edda3-120">[ [複合レイヤー] ウィンドウ](#composited-layers) 。</span><span class="sxs-lookup"><span data-stu-id="edda3-120">The [Composited Layers](#composited-layers) pane.</span></span>  <span data-ttu-id="edda3-121">別の 3D 要素を追加して、レイヤーの観点からより包括的なエクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="edda3-121">Add another 3D element to create a more comprehensive experience from a layers perspective.</span></span>  <span data-ttu-id="edda3-122">ウィンドウにアクセスするには、DOM ウィンドウの **横にある [複合レイヤー** ] ウィンドウ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="edda3-122">To access the pane, choose the **Composited Layers** pane next to the **DOM** pane.</span></span>  
    
<span data-ttu-id="edda3-123">右側に、Z-index、3D [DOM、](#3d-dom)またはコンポジット レイヤーから選択した項目[が表示されます](#composited-layers)。 [](#z-index)</span><span class="sxs-lookup"><span data-stu-id="edda3-123">On the right side, the canvas displays your selections from the [Z-index](#z-index), [3D DOM](#3d-dom), or [Composited Layers](#composited-layers).</span></span>  

## <a name="navigating-the-canvas"></a><span data-ttu-id="edda3-124">キャンバスの移動</span><span class="sxs-lookup"><span data-stu-id="edda3-124">Navigating the canvas</span></span>  

:::image type="complex" source="../media/3d-view-canvas.msft.png" alt-text="3D ビューのキャンバス" lightbox="../media/3d-view-canvas.msft.png":::
   <span data-ttu-id="edda3-126">3D ビューのキャンバス</span><span class="sxs-lookup"><span data-stu-id="edda3-126">Canvas of 3D View</span></span>  
:::image-end:::  

### <a name="keyboard-shortcuts"></a><span data-ttu-id="edda3-127">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="edda3-127">Keyboard shortcuts</span></span>  

*   <span data-ttu-id="edda3-128">DOM を回転する: 水平方向に回転するには、キーとキー `left-arrow` を `right-arrow` 選択します。</span><span class="sxs-lookup"><span data-stu-id="edda3-128">Rotate the DOM:  To rotate horizontally, select the `left-arrow` and `right-arrow` keys.</span></span>  <span data-ttu-id="edda3-129">垂直方向に回転するには、キーとキー `up-arrow` を `down-arrow` 選択します。</span><span class="sxs-lookup"><span data-stu-id="edda3-129">To rotate vertically, select the `up-arrow` and `down-arrow` keys.</span></span>  
*   <span data-ttu-id="edda3-130">DOM を移動する: 隣接する要素を移動するには、要素を選択し、キーとキー `up-arrow` を選択 `down-arrow` します。</span><span class="sxs-lookup"><span data-stu-id="edda3-130">Navigate the DOM:  To move through the adjacent elements, choose an element and select the `up-arrow` and `down-arrow` keys.</span></span>  

### <a name="mouse-controls"></a><span data-ttu-id="edda3-131">マウス コントロール</span><span class="sxs-lookup"><span data-stu-id="edda3-131">Mouse controls</span></span>  

*   <span data-ttu-id="edda3-132">DOM を回転する: キャンバス空間を選択してドラッグします。</span><span class="sxs-lookup"><span data-stu-id="edda3-132">Rotate the DOM:  Choose and drag around the canvas space.</span></span>  
*   <span data-ttu-id="edda3-133">DOM の周囲をパンする: コンテキスト メニュー \(右クリック\) を開き、DOM を移動する方向にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="edda3-133">Pan around the DOM:  Open the contextual menu \(right-click\) and drag in the direction you want the DOM to move.</span></span>  
*   <span data-ttu-id="edda3-134">ズーム: タッチパッドを 2 本指でドラッグするか、マウスのスクロール ホイールを使用します。</span><span class="sxs-lookup"><span data-stu-id="edda3-134">Zoom:  Drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>  

### <a name="on-screen-controls"></a><span data-ttu-id="edda3-135">オンスクリーン コントロール</span><span class="sxs-lookup"><span data-stu-id="edda3-135">On-screen controls</span></span>  

:::image type="complex" source="../media/3d-view-controls-small.msft.png" alt-text="オンスクリーン コントロール" lightbox="../media/3d-view-controls-small.msft.png":::
   <span data-ttu-id="edda3-137">オンスクリーン コントロール</span><span class="sxs-lookup"><span data-stu-id="edda3-137">On-screen controls</span></span>  
:::image-end:::  

*   <span data-ttu-id="edda3-138">キャンバス ビューを元のビューにリセットする: \*\*\*\* [カメラのリセット] ボタンを選択するか、[カメラの表示と中央に戻**す]** \(横向き更新アイコン\) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="edda3-138">Reset the canvas view to the original view:  Choose the **Reset camera** button, or choose the **Reset elements in view and re-center camera** \(sideways refresh icon\) button.</span></span>  
*   <span data-ttu-id="edda3-139">キャンバスを更新する \(ブラウザーが変更された場合やデバイス エミュレーター ビューに切り替えた場合など\*\*\*\*)。[スナップショットの再取得]\*\*\*\* ボタンを選択するか、[新しいスナップショットを取得] ボタン \(refresh icon\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="edda3-139">Refresh the canvas \(for example, if the browser changed or you switched to a device emulator view\):  Choose the **Retake snapshot** button or choose the **Take new snapshot** button \(refresh icon\).</span></span>  

## <a name="z-index"></a><span data-ttu-id="edda3-140">Z-index</span><span class="sxs-lookup"><span data-stu-id="edda3-140">Z-index</span></span>  

:::image type="complex" source="../media/3d-view-z-index-view-box.msft.png" alt-text="Z-index ビュー" lightbox="../media/3d-view-z-index-view-box.msft.png":::
   <span data-ttu-id="edda3-142">Z-index ビュー</span><span class="sxs-lookup"><span data-stu-id="edda3-142">Z-index view</span></span>  
:::image-end:::  

<span data-ttu-id="edda3-143">Z **インデックス ウィンドウには** **3D DOM** ウィンドウとの共有機能が含まれていますが、ペインには依然として、そのウィンドウに固有の要素があります。</span><span class="sxs-lookup"><span data-stu-id="edda3-143">While the **Z-index** pane has shared features with the **3D DOM** pane, the panes still have elements that are unique to the pane.</span></span>  

### <a name="highlight-elements-with-stacking-context"></a><span data-ttu-id="edda3-144">スタック コンテキストを使用して要素を強調表示する</span><span class="sxs-lookup"><span data-stu-id="edda3-144">Highlight elements with stacking context</span></span>  

<span data-ttu-id="edda3-145">[ **コンテキストを重ね合** った要素を強調表示する] 設定を使用すると、キャンバス上の要素の z-index タグを \(and off\) オンにできます。</span><span class="sxs-lookup"><span data-stu-id="edda3-145">The **Highlight elements with stacking context** setting allows you to turn on \(and off\) the z-index tags for the elements on the canvas.</span></span>  <span data-ttu-id="edda3-146">このチェック ボックスは既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="edda3-146">The checkbox is chosen by default.</span></span>  

### <a name="change-the-scope-of-your-exploration"></a><span data-ttu-id="edda3-147">探索の範囲を変更する</span><span class="sxs-lookup"><span data-stu-id="edda3-147">Change the scope of your exploration</span></span>  

<span data-ttu-id="edda3-148">[ **すべての要素を表示** ] ボタンは、その下の設定を変更した後に DOM のすべての要素を表示する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="edda3-148">The **Show all elements** button is the quickest way to display all the elements of the DOM after changing the settings below it.</span></span>  

<span data-ttu-id="edda3-149">[ **コンテキストをスタックする要素のみを** 表示] ボタンは、コンテキストを積み重ねることなく要素を削除し、DOM をフラット化してナビゲーションを容易にします。</span><span class="sxs-lookup"><span data-stu-id="edda3-149">The **Show only elements with stacking context** button removes elements without stacking context and flattens the DOM for easier navigation.</span></span>  

<span data-ttu-id="edda3-150">[ **選択した要素を分離する** ] ボタンは、基本的に 1 つの 3 つのボタンです。</span><span class="sxs-lookup"><span data-stu-id="edda3-150">The **Isolate selected element** button is essentially three buttons in one.</span></span>  <span data-ttu-id="edda3-151">[選択した要素を分離する\*\*\*\*] ボタンの下には、[\*\*\*\* すべての親を表示する] チェック ボックスと [新しいスタック コンテキストを持つ親のみを保持する] チェック ボックスの下に**2 つのチェック ボックス**があります。</span><span class="sxs-lookup"><span data-stu-id="edda3-151">There are two checkboxes below the **Isolate selected element** button:  The **Show all parents** checkbox and **Keep only parents with new stacking context** checkbox.</span></span>  

<span data-ttu-id="edda3-152">[ **すべての親を表示する]** チェック ボックスは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="edda3-152">The **Show all parents** checkbox is turned on by default.</span></span>  <span data-ttu-id="edda3-153">キャンバスに要素と親を表示するには、要素を選択し、[選択した要素を分離] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="edda3-153">To display the element and any parents on the canvas, choose an element and choose the **Isolate selected element** button.</span></span>  

<span data-ttu-id="edda3-154">キャンバスに新しいスタック コンテキストを持つ要素と親を表示するには、[新しいスタック コンテキスト\*\*\*\* を使用して親のみを保持する] 設定をオンにし、[選択した要素を分離] ボタンを**選択します。**</span><span class="sxs-lookup"><span data-stu-id="edda3-154">To display the element and the parents that have a new stacking context on the canvas, turn on the **Keep only parents with new stacking context** setting and choose the **Isolate selected element** button.</span></span>  

<span data-ttu-id="edda3-155">キャンバスに選択した要素を表示するには、両方の設定をオフにし、[選択した要素を分離] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="edda3-155">To display the element you chose on the canvas, turn off both the settings and choose **Isolate selected element** button.</span></span>  

<span data-ttu-id="edda3-156">**3D DOM**ウィンドウの下部で、[親と同じペイント順序の要素を非表示**にする] チェック ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="edda3-156">At the bottom of the **3D DOM** pane, locate the **Hide elements with the same paint order as their parent** checkbox.</span></span>  <span data-ttu-id="edda3-157">チェック ボックスを選択して選択解除すると、選択に基づいて要素が更新されます。</span><span class="sxs-lookup"><span data-stu-id="edda3-157">Choosing and deselecting the checkbox refreshes the elements based on your choice.</span></span>  <span data-ttu-id="edda3-158">選択すると、ペイント順序を共有する要素は親にフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="edda3-158">If chosen, elements that share paint order are flattened to the parent.</span></span>  

<span data-ttu-id="edda3-159">このオプションは、より複雑な Web ページがキャンバスに作成する混乱の一部をクリアするためのものになります。</span><span class="sxs-lookup"><span data-stu-id="edda3-159">The options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>  

### <a name="z-index-color-type"></a><span data-ttu-id="edda3-160">Z インデックスの色の種類</span><span class="sxs-lookup"><span data-stu-id="edda3-160">Z-index color type</span></span>  

<span data-ttu-id="edda3-161">キャンバス内の DOM に使用できるさまざまな視覚エフェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="edda3-161">The are the different visualizations you may use for the DOM in your canvas.</span></span>  <span data-ttu-id="edda3-162">楽しみのために使うのか、視覚エフェクトを使って DOM をよりよく視覚化するのに役立つのかに関わり、DevTools にはさまざまな色と背景色を使用する**オプションがあります。**</span><span class="sxs-lookup"><span data-stu-id="edda3-162">Whether you use it for fun or because the visualizations help you visualize the DOM better, the DevTools have different colorways and a **Use background color** option.</span></span>  <span data-ttu-id="edda3-163">**Z インデックス ウィンドウは**、**紫から白**、\*\*\*\* 背景色を**3D DOM ウィンドウと共有**します。</span><span class="sxs-lookup"><span data-stu-id="edda3-163">The **Z-index** pane shares the **Purple to White** and **Background Color** with the **3D DOM** pane.</span></span>  <span data-ttu-id="edda3-164">z-index ラベルの視覚的要素が追加された場合、フィードバックによって色オプションの数が減少しました。</span><span class="sxs-lookup"><span data-stu-id="edda3-164">Given the added visual element of the z-index labels, your feedback that led to a reduction in the number of color options.</span></span>  <span data-ttu-id="edda3-165">新しい簡略化により、z-index デバッグ エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="edda3-165">The new simplicity improves the z-index debugging experience.</span></span>  <span data-ttu-id="edda3-166">ラジオ ボタンを使用すると、オプションを切り替え、色の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="edda3-166">The radio buttons allow you to toggle through the options and pick the color type.</span></span>  <span data-ttu-id="edda3-167">色の種類は、プロジェクトに最も適した色か、最も好きな色の種類のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="edda3-167">The color type is either most appropriate for your project or one that you like the most.</span></span>  

## <a name="3d-dom"></a><span data-ttu-id="edda3-168">3D DOM</span><span class="sxs-lookup"><span data-stu-id="edda3-168">3D DOM</span></span>  

:::image type="complex" source="../media/3d-view-dom-purple-box.msft.png" alt-text="DOM ビュー" lightbox="../media/3d-view-dom-purple-box.msft.png":::
   <span data-ttu-id="edda3-170">DOM ビュー</span><span class="sxs-lookup"><span data-stu-id="edda3-170">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="edda3-171">z-index エクスペリエンスではなく、より多くの一般的なデバッグ ビューを使用する場合 **、3D DOM** は DOM の全体的な外観を提供します。</span><span class="sxs-lookup"><span data-stu-id="edda3-171">If you want to take more of a general debugging view, rather than the z-index experience, the **3D DOM** gives an overall look of the DOM.</span></span>  <span data-ttu-id="edda3-172">z-index コンテキストが削除されたので、DOM は、より密接に、クリーンにスタックされます。</span><span class="sxs-lookup"><span data-stu-id="edda3-172">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span>  <span data-ttu-id="edda3-173">**3D DOM**ウィンドウにも同様の機能がありますが、いくつかのニュアンスがあります。</span><span class="sxs-lookup"><span data-stu-id="edda3-173">The **3D DOM** pane has similar functionality, but there are a few nuances.</span></span>  

### <a name="changing-your-view"></a><span data-ttu-id="edda3-174">ビューの変更</span><span class="sxs-lookup"><span data-stu-id="edda3-174">Changing your view</span></span>  

<span data-ttu-id="edda3-175">**[3D DOM]** ウィンドウ\*\*\*\* の [選択した要素を分離する] ボタンには、[子を含**める]** チェック ボックスと [親を含める]**チェック ボックス**があります。</span><span class="sxs-lookup"><span data-stu-id="edda3-175">On the **3D DOM** pane, the **Isolate selected element** button has **Include children** and **Include parents** checkboxes.</span></span>  <span data-ttu-id="edda3-176">どちらのチェック ボックスも既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="edda3-176">Both checkboxes are turned on by default.</span></span>  <span data-ttu-id="edda3-177">つまり、要素を選択した\*\*\*\* 後で [選択した要素を分離] ボタンを選択すると、選択した要素、要素の親、要素の子がキャンバスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="edda3-177">That means if you choose the **Isolate selected element** button after you choose an element, the canvas displays the chosen element, the parents of the element, and the children of the element.</span></span>  <span data-ttu-id="edda3-178">[子を**含める]** 設定を\*\*\*\* オフにし、[選択した要素を分離する] ボタンを再度選択すると、選択した要素と要素の親が表示されます。</span><span class="sxs-lookup"><span data-stu-id="edda3-178">Turn off the **Include children** setting and choose the **Isolate selected element** button again to display the chosen element and the parents of the element.</span></span>  <span data-ttu-id="edda3-179">[子を含める] 設定をオンにし\*\*\*\*、[親を含める] 設定\*\*\*\* をオフにし、[選択した要素を分離する] ボタンを選択すると、要素と子がキャンバスに表示されます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="edda3-179">If you turn on the **Include children** setting and turn off the **Include parents** setting and then choose the **Isolate selected element** button, the canvas displays the element and any children.</span></span>  <span data-ttu-id="edda3-180">両方の設定をオフにし、[選択\*\*\*\* した要素を分離] ボタンを選択すると、キャンバスには以前に選択した要素だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edda3-180">If you turn off both settings and choose the **Isolate selected element** button, the canvas only displays the element you previously chose.</span></span>  

<span data-ttu-id="edda3-181">コントロール ウィンドウの [ページの入れ子レベル] という名前のスライダー **で、** その横に数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="edda3-181">A slider on the control pane named **Nesting level for page** with a number next to it.</span></span>  <span data-ttu-id="edda3-182">数値は、ドキュメントのレイヤー数を示します。</span><span class="sxs-lookup"><span data-stu-id="edda3-182">The number indicates the number of layers for the document.</span></span>  <span data-ttu-id="edda3-183">スライダーを左にドラッグすると、最も外側のレイヤーは、入れ子レベルが設定され、DOM 内の最も遠い背面要素だけが表示されるまではがれ出します `1` 。</span><span class="sxs-lookup"><span data-stu-id="edda3-183">Dragging the slider to the left causes the outermost layers to peel away until you are left with a nesting level set to `1`, which displays only the furthest back element in the DOM.</span></span>  <span data-ttu-id="edda3-184">混乱の一部を削除するには、スライダーをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="edda3-184">To remove some of the clutter, drag the slider.</span></span>  <span data-ttu-id="edda3-185">これは、下位レベルで何が起こっているかを詳しく見るのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="edda3-185">It helps you get a closer look at what is happening in the lower levels.</span></span>  

### <a name="dom-color-type"></a><span data-ttu-id="edda3-186">DOM の色の種類</span><span class="sxs-lookup"><span data-stu-id="edda3-186">DOM color type</span></span>  

<span data-ttu-id="edda3-187">**3D DOM ウィンドウには**、次のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edda3-187">The **3D DOM** pane displays the following options.</span></span>  

*   <span data-ttu-id="edda3-188">3 つの異なるカラーウェイ。</span><span class="sxs-lookup"><span data-stu-id="edda3-188">Three different colorways.</span></span>  
    *   **<span data-ttu-id="edda3-189">ヒートマップ - 紫から白へ</span><span class="sxs-lookup"><span data-stu-id="edda3-189">Heatmap - Purple to White</span></span>**  
    *   **<span data-ttu-id="edda3-190">ヒートマップ - 青から黄色</span><span class="sxs-lookup"><span data-stu-id="edda3-190">Heatmap - Blue to Yellow</span></span>**  
    *   **<span data-ttu-id="edda3-191">ヒートマップ - 虹</span><span class="sxs-lookup"><span data-stu-id="edda3-191">Heatmap - Rainbow</span></span>**  
*   **<span data-ttu-id="edda3-192">背景色を使用する</span><span class="sxs-lookup"><span data-stu-id="edda3-192">Use background color</span></span>**  
*   **<span data-ttu-id="edda3-193">画面テクスチャの使用</span><span class="sxs-lookup"><span data-stu-id="edda3-193">Use screen texture</span></span>**  
    
<span data-ttu-id="edda3-194">[ **画面テクスチャを使用する]** オプションは、デバッグ エクスペリエンスにコンテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="edda3-194">The **Use screen texture** option adds context to your debugging experience.</span></span>  <span data-ttu-id="edda3-195">Web ページのコンテンツを要素に直接表示します。</span><span class="sxs-lookup"><span data-stu-id="edda3-195">It directly displays the content from the webpage onto the elements.</span></span>  

## <a name="composited-layers"></a><span data-ttu-id="edda3-196">複合レイヤー</span><span class="sxs-lookup"><span data-stu-id="edda3-196">Composited layers</span></span>

:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[複合レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="edda3-198">**[コンポジット レイヤー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="edda3-198">**Composited Layers** pane</span></span>
:::image-end:::  

<span data-ttu-id="edda3-199">[ **複合レイヤー] ウィンドウは** 、コンテキストを変更せずにレイヤー ツール **の** 要素を開きます。</span><span class="sxs-lookup"><span data-stu-id="edda3-199">The **Composited Layers** pane opens the elements of the **Layers** tool without changing contexts.</span></span>  <span data-ttu-id="edda3-200">引き続き各レイヤーの詳細にアクセスし、スロー スクロールを下げ、ペイント\*\*\*\*\*\*することができます\*\*。</span><span class="sxs-lookup"><span data-stu-id="edda3-200">You may still access the details of each of the layers and have the **Slow scroll rects** and **Paint**.</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="edda3-201">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="edda3-201">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="edda3-202">Microsoft Edge Devtools チームは、UI に取り組み、フィードバックに基づいて 3D ビューにさらに機能を追加しています。</span><span class="sxs-lookup"><span data-stu-id="edda3-202">The Microsoft Edge Devtools team is working on the UI and adding more functionality to the 3D View based on your feedback.</span></span>  <span data-ttu-id="edda3-203">フィードバックを送信して、Microsoft Edge DevTools の改善に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="edda3-203">Send your feedback to help improve the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="edda3-204">DevTools**で [** フィードバックの送信] アイコンを選択するか、Windows/Linux または macOS で選択し `Alt` + `Shift` + `I` `Option` + `Shift` + `I` 、DevTools に対するフィードバックまたは機能要求を入力します。</span><span class="sxs-lookup"><span data-stu-id="edda3-204">Choose the **Send Feedback** icon in the DevTools or select `Alt`+`Shift`+`I` on Windows/Linux or `Option`+`Shift`+`I` on macOS and enter any feedback or feature requests you have for the DevTools.</span></span>  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D ビュー - MicrosoftEdge/DevToolsSamples |GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
