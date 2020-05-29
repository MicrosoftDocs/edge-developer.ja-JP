---
description: 3D ビューの概要とその使い方を説明します。
title: 3D View (3D ビュー)
author: erdraud
ms.author: erdraud
ms.date: 11/27/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f2ae80426da71797d4bee4060d33965f04047e19
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569141"
---
# <span data-ttu-id="11ab2-104">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="11ab2-104">3D View</span></span>

<span data-ttu-id="11ab2-105">**3D ビュー**を使用して、[ドキュメントオブジェクトモデル](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)(DOM) または[z インデックス](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index)スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="11ab2-105">Use the **3D View** to debug your web application by navigating through the [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) (DOM) or the [z-index](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index) stacking context.</span></span> <span data-ttu-id="11ab2-106">これにより、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="11ab2-106">With it you can:</span></span> 

- [<span data-ttu-id="11ab2-107">3D perspevtive に変換された web ページを調べる</span><span class="sxs-lookup"><span data-stu-id="11ab2-107">Explore the web page translated into a 3D perspevtive</span></span>](#3d-dom)
- [<span data-ttu-id="11ab2-108">Z インデックススタックのコンテキストに基づいてデバッグする</span><span class="sxs-lookup"><span data-stu-id="11ab2-108">Debug based on z-index stacking context</span></span>](#z-index)
- <span data-ttu-id="11ab2-109">[DOM] ウィンドウまたは [ [z インデックス] ウィンドウ](#change-the-scope-of-your-exploration)[で低優先メールの一部をクリアする](#changing-your-view)</span><span class="sxs-lookup"><span data-stu-id="11ab2-109">[Clear some of the clutter in the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>
- <span data-ttu-id="11ab2-110">適切な DOM 問題または[z インデックスの問題](#z-index-color-type)[をデバッグするための配色パターンを選ぶ](#dom-color-type)</span><span class="sxs-lookup"><span data-stu-id="11ab2-110">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>

<span data-ttu-id="11ab2-111">デバッグエクスペリエンスに使用できるペインは2つあります。</span><span class="sxs-lookup"><span data-stu-id="11ab2-111">There are two panes that you can use for your debugging experience.</span></span>

1. <span data-ttu-id="11ab2-112">**Z インデックス**Z インデックスコンテキストを念頭に置いて、web アプリケーションのさまざまな要素間を移動します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-112">**Z-index** Navigate through the different elements in the web application with the z-index context in mind.</span></span> <span data-ttu-id="11ab2-113">これは既定のウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="11ab2-113">This is the default pane.</span></span>
2. <span data-ttu-id="11ab2-114">**3D DOM**DOM をすべての要素ですぐに確認できます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-114">**3D DOM** Explore the DOM as a whole with all the elements at your fingertips.</span></span> <span data-ttu-id="11ab2-115">このウィンドウにアクセスするには、"Z インデックス" ウィンドウの横にある [DOM] ウィンドウをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11ab2-115">To access this pane, click on the "DOM" pane next to the "Z-index" pane.</span></span>

![3D ビューのキャンバス](./media/canvas.png)

## <span data-ttu-id="11ab2-117">キャンバス内を移動する</span><span class="sxs-lookup"><span data-stu-id="11ab2-117">Navigating the canvas</span></span>

### <span data-ttu-id="11ab2-118">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="11ab2-118">Keyboard shortcuts</span></span>
- <span data-ttu-id="11ab2-119">DOM を回転させる: 左右の方向キーを使用して水平方向に回転し、上下の方向キーを使用して縦方向に回転します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-119">Rotate the DOM: use the left and right arrow keys to rotate horizontally and use the up and down arrow keys to rotate vertically.</span></span>
- <span data-ttu-id="11ab2-120">DOM 内の移動: 要素が選択されている場合は、上下の方向キーを使用して、隣接する要素間を移動することができます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-120">Navigate the DOM: if an element is selected, you can use the up and down arrow keys to move through the elements adjacent</span></span>

### <span data-ttu-id="11ab2-121">マウスコントロール</span><span class="sxs-lookup"><span data-stu-id="11ab2-121">Mouse controls</span></span>
- <span data-ttu-id="11ab2-122">DOM を回転させる: 左クリックして、キャンバス領域をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="11ab2-122">Rotate the DOM: left click and drag around the canvas space.</span></span>
- <span data-ttu-id="11ab2-123">DOM でのパン: DOM を移動する方向に右クリックしてドラッグします。</span><span class="sxs-lookup"><span data-stu-id="11ab2-123">Pan around the DOM: right click and drag in the direction you want the DOM to move.</span></span>
- <span data-ttu-id="11ab2-124">[ズーム]: タッチパッド上で2本の指をドラッグするか、マウスのスクロールホイールを使用します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-124">Zoom: drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>

![オンスクリーンコントロール](./media/controls-small.png)
### <span data-ttu-id="11ab2-126">オンスクリーンコントロール</span><span class="sxs-lookup"><span data-stu-id="11ab2-126">On-screen controls</span></span>
- <span data-ttu-id="11ab2-127">キャンバスビューを元のビューにリセットします。 "カメラのリセット" というラベルの付いたボタンをクリックするか、横にあるアイコンをクリックして、[ビューの要素をリセットし、カメラを再配置する]</span><span class="sxs-lookup"><span data-stu-id="11ab2-127">Reset the canvas view to the original view: click the button labeled "Reset camera," or click on the icon that looks like a sideways refresh button and has "Reset elements in view and re-center camera"</span></span>
- <span data-ttu-id="11ab2-128">キャンバスを更新します (たとえば、ブラウザーが変更された場合、またはデバイスエミュレータービューに切り替えた場合)。 [スナップショットの再受験] と表示されているボタンをクリックするか、[更新] アイコンのようなボタンをクリックすると、ホバーテキストとして "新しいスナップショットを撮ります" というボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11ab2-128">Refresh the canvas (e.g. if the browser changed or you switched to a device emulator view): click on the button that says "Retake snapshot," or click on the button that looks like a refresh icon and has "Take new snapshot" as the hover text.</span></span>

![Z インデックスビュー](./media/z-index-view-box.png)

## <span data-ttu-id="11ab2-130">Z インデックス</span><span class="sxs-lookup"><span data-stu-id="11ab2-130">Z-index</span></span>

<span data-ttu-id="11ab2-131">Z インデックスウィンドウには DOM ペインとの共有機能がありますが、ウィンドウに固有の要素はまだあります。</span><span class="sxs-lookup"><span data-stu-id="11ab2-131">While the Z-index pane has shared features with the DOM pane, they still have elements that are unique to the pane.</span></span>

### <span data-ttu-id="11ab2-132">スタックコンテキストで要素を強調表示する</span><span class="sxs-lookup"><span data-stu-id="11ab2-132">Highlight elements with stacking context</span></span>

<span data-ttu-id="11ab2-133">この設定では、キャンバスの要素の z インデックスタグのオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-133">This setting allows you to toggle the z-index tags on and off for the elements in the canvas.</span></span> <span data-ttu-id="11ab2-134">既定では、このチェックボックスはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="11ab2-134">The checkbox will be selected by default.</span></span>

### <span data-ttu-id="11ab2-135">調査の範囲を変更する</span><span class="sxs-lookup"><span data-stu-id="11ab2-135">Change the scope of your exploration</span></span>

<span data-ttu-id="11ab2-136">[**すべての要素を表示**] ボタンは、次の設定を変更した後で、すべての DOM 要素を表示するための最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="11ab2-136">The **Show all elements** button is the quickest way to display all the DOM's elements after changing the settings below.</span></span>

<span data-ttu-id="11ab2-137">**スタックコンテキストのある要素のみを表示**します。スタックを使わずに要素を削除し、さらに簡単に移動できるように DOM をフラット化します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-137">**Show only elements with stacking context** removes elements without stacking context and flattens the DOM for easier navigation.</span></span>

<span data-ttu-id="11ab2-138">[**選択した要素の分離**] フィルターは、基本的には1つのボタンです。</span><span class="sxs-lookup"><span data-stu-id="11ab2-138">The **Isolate selected element** filter is essentially three buttons in one.</span></span> <span data-ttu-id="11ab2-139">このボタンの下には2つのチェックボックスがあります。1つは "すべての親を表示" と "親のみを新しいスタックコンテキストで保持する" です。</span><span class="sxs-lookup"><span data-stu-id="11ab2-139">There are two checkboxes below this button: one is "Show all parents" and "Keep only parents with new stacking context."</span></span> 

<span data-ttu-id="11ab2-140">[すべての親を表示] チェックボックスは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="11ab2-140">The "Show all parents" checkbox will be checked by default.</span></span> <span data-ttu-id="11ab2-141">[キャンバス] ウィンドウで要素を選択し、[**選択した要素の分離**] をクリックした場合、キャンバスには要素とその親が表示されるだけです。</span><span class="sxs-lookup"><span data-stu-id="11ab2-141">If you select an element in the canvas pane and click on **Isolate selected element**, the canvas will only display the element and its parents.</span></span>

<span data-ttu-id="11ab2-142">[新しいスタックコンテキストで親のみを保持] を選択し、[**選択した要素の分離**] をクリックすると、キャンバスには、新しいスタックコンテキストを持つ親要素と親が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-142">If you select the "Keep only parents with new stacking context," and click on **Isolate selected element**, the canvas will only display the element and the parents that have a new stacking context.</span></span>

<span data-ttu-id="11ab2-143">両方のチェックボックスをオフにして、[**選択した要素の分離**] をクリックした場合、キャンバスには最初の場所で選択した要素のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-143">If you deselect both of the checkboxes and click on **Isolate selected element**, the canvas will only display the element you chose in the first place.</span></span>

<span data-ttu-id="11ab2-144">コントロールパネルの一番下には、**親トグルと同じ描画順序の非表示要素**があります。</span><span class="sxs-lookup"><span data-stu-id="11ab2-144">At the very bottom of the controls panel, there is the **Hide elements with the same paint order as their parent** toggle.</span></span> <span data-ttu-id="11ab2-145">チェックボックスをオンまたはオフにすると、選択した要素に基づいて要素が再読み込みされます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-145">Selecting and deselecting the checkbox will reload the elements based on your selection.</span></span> <span data-ttu-id="11ab2-146">選択すると、ペイントの順序を共有する要素が親にフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-146">If selected, elements that share paint order will be flattened to the parent.</span></span>

<span data-ttu-id="11ab2-147">これらのオプションは、より複雑な web ページを作成して、キャンバスに作成することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="11ab2-147">These options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>

### <span data-ttu-id="11ab2-148">Z インデックスの色の種類</span><span class="sxs-lookup"><span data-stu-id="11ab2-148">Z-index color type</span></span>

<span data-ttu-id="11ab2-149">これらは、キャンバスの DOM で使うことができるさまざまな視覚エフェクトです。</span><span class="sxs-lookup"><span data-stu-id="11ab2-149">These are the different visualizations you can use for the DOM in your canvas.</span></span> <span data-ttu-id="11ab2-150">楽しく使うか、または DOM をより効果的に視覚化するために役立つため、3つの異なる colorways と "背景色" の設定があります。</span><span class="sxs-lookup"><span data-stu-id="11ab2-150">Whether you use it for fun or because they help you visualize the DOM better, we have three different colorways as well as a "background color" setting.</span></span> <span data-ttu-id="11ab2-151">ラジオボタンを使用すると、オプションを切り替えて、プロジェクトに最も適した色の種類 (または最適な色) を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-151">The radio buttons allow you to toggle through the options and pick the color type most appropriate for your project (or that you like the most).</span></span>

![DOM ビュー](./media/dom-purple-box.png)

## <span data-ttu-id="11ab2-153">3D DOM</span><span class="sxs-lookup"><span data-stu-id="11ab2-153">3D DOM</span></span>

<span data-ttu-id="11ab2-154">Z インデックスエクスペリエンスではなく、一般的なデバッグビューを実行する場合、3D DOM は DOM の全体的な外観を提供します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-154">If you want to take more of a general debugging view, rather than the z-index experience, the 3D DOM gives an overall look of the DOM.</span></span> <span data-ttu-id="11ab2-155">Z インデックスコンテキストが削除されたため、DOM はより厳密かつ明確に積み重ねられます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-155">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span> <span data-ttu-id="11ab2-156">このウィンドウには類似した機能もありますが、いくつかの微妙な方法があります。</span><span class="sxs-lookup"><span data-stu-id="11ab2-156">This pane has similar functionality, but there are a few nuances.</span></span>

### <span data-ttu-id="11ab2-157">ビューを変更する</span><span class="sxs-lookup"><span data-stu-id="11ab2-157">Changing your view</span></span>

<span data-ttu-id="11ab2-158">[ **3D DOM** ] ウィンドウの [**選択した要素の分離**] フィルターには、"子の追加" と "親の追加" が含まれています。</span><span class="sxs-lookup"><span data-stu-id="11ab2-158">In the **3D DOM** pane, the **Isolate selected element** filter has "Include children" and "Include parents."</span></span> <span data-ttu-id="11ab2-159">既定では、両方のチェックボックスがオンになっています。これは、キャンバスで要素を選択した後に [**選択した要素を分離**] ボタンをクリックすると、選んだ要素、要素の親、要素の子が表示されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-159">By default both checkboxes are selected, which means that clicking on the **Isolate selected element** button after selecting an element in the canvas would display the element chosen, the element's parents, and the element's children.</span></span> <span data-ttu-id="11ab2-160">[子を含める] チェックボックスをオフにして、[**選択した要素を分離**] ボタンをもう一度クリックすると、選択した要素と要素の親が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-160">Deselecting the "Include children" checkbox and clicking the **Isolate selected element** button again would display the selected element and the element's parents.</span></span> <span data-ttu-id="11ab2-161">[子を含める] チェックボックスをオンにして、[親を含める] チェックボックスをオフにした後、[**選択した要素の分離**] をクリックすると、キャンバスに要素とその子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-161">If you select the "Include children" checkbox and deselect the "Include parents" checkbox before clicking on **Isolate selected element**, the canvas will then display the element and its children.</span></span> <span data-ttu-id="11ab2-162">両方のチェックボックスをオフにして、[**選択した要素の分離**] をクリックした場合、キャンバスには、前に選択した要素のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-162">If you deselect both checkboxes and click on **Isolate selected element**, the canvas will only display the element you previously selected.</span></span>

<span data-ttu-id="11ab2-163">コントロールウィンドウに、その横に数字が表示された [**レベルのネスト**] というスライダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-163">You'll notice a slider in the control pane titled **Nesting level** with a number next to it.</span></span> <span data-ttu-id="11ab2-164">この番号は、文書内のレイヤーの数を示します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-164">The number indicates the number of layers in the document.</span></span> <span data-ttu-id="11ab2-165">スライダーを左にドラッグすると、入れ子のレベルが1になるまで一番外側のレイヤーがはがすかます。 DOM 内の最遠いバック要素のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11ab2-165">Dragging the slider to the left will cause the outermost layers to peel away until you are left with a nesting level of 1, displaying only the furthest back element in the DOM.</span></span> <span data-ttu-id="11ab2-166">こうすることで、低優先メールの一部を削除することができます。これは、下位レベルで何を行っているのかを詳しく見てみたい場合に使います。</span><span class="sxs-lookup"><span data-stu-id="11ab2-166">This allows you to remove some of the clutter if you are trying to get a closer look at what is going on in the lower levels.</span></span>

### <span data-ttu-id="11ab2-167">DOM 色の種類</span><span class="sxs-lookup"><span data-stu-id="11ab2-167">DOM color type</span></span>

<span data-ttu-id="11ab2-168">*紫色から白*に加えて、*青から黄*、*レインボー*、*背景色*のオプションが*表示*されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="11ab2-168">You'll notice that, in addition to the *Purple to White*, *Blue to Yellow*, *Rainbow*, and *Use background color* options, there is *Use screen texture*.</span></span> <span data-ttu-id="11ab2-169">画面のテクスチャは、web ページのコンテンツを要素に直接表示することで、デバッグエクスペリエンスにコンテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-169">The screen texture adds context to your debugging experience by displaying the content from the web page directly onto the elements.</span></span> <span data-ttu-id="11ab2-170">一部の web サイトでは、3D ビューでの画面テクスチャのレンダリングが困難になるため、これはまだ進行中の作業です。</span><span class="sxs-lookup"><span data-stu-id="11ab2-170">This is still a work in progress, as some websites have a harder time rendering their screen texture in the 3D View.</span></span> 

## <span data-ttu-id="11ab2-171">次のステップ</span><span class="sxs-lookup"><span data-stu-id="11ab2-171">Next steps</span></span>

<span data-ttu-id="11ab2-172">Microsoft は、ユーザーからの要求に基づいて、UI を操作し、3D ビューに機能を追加しています。</span><span class="sxs-lookup"><span data-stu-id="11ab2-172">We are working on the UI and adding more functionality to the 3D View based on asks from users like you.</span></span> <span data-ttu-id="11ab2-173">Microsoft Edge DevTools の改善に向けて、フィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="11ab2-173">Please send us your feedback so we can continue improving the Microsoft Edge DevTools for you!</span></span> <span data-ttu-id="11ab2-174">Devtools のフィードバックアイコンをクリックするか、Windows キー (Mac) を押して、 `Alt`  +  `Shift`  +  `I` `Option`  +  `Shift`  +  `I` devtools のフィードバックまたは機能要求を入力します。</span><span class="sxs-lookup"><span data-stu-id="11ab2-174">Simply click the feedback icon in the DevTools or press `Alt` + `Shift` + `I` on Windows (`Option` + `Shift` + `I` on Mac) and enter any feedback or feature requests you have for the DevTools.</span></span>