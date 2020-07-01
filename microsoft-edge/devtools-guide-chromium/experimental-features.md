---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 実験的な機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: 731a289f555870eeff9cdc160965b59925b70c4d
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843951"
---
# <span data-ttu-id="9e5dc-104">実験的な機能</span><span class="sxs-lookup"><span data-stu-id="9e5dc-104">Experimental features</span></span>  

<span data-ttu-id="9e5dc-105">Microsoft Edge DevTools でまだ開発中の実験的な機能を使って、各リリース前に[フィードバック](#providing-feedback-on-experimental-features)をテストして提供することができます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-105">You may use the experimental features that are still under development in the Microsoft Edge DevTools to test and [provide feedback](#providing-feedback-on-experimental-features) before each is released broadly.</span></span>  

<span data-ttu-id="9e5dc-106">Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-106">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="9e5dc-107">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="9e5dc-107">Turn on experimental features</span></span>  

<span data-ttu-id="9e5dc-108">Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-108">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="9e5dc-109">[DevTools を開き][DevtoolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-109">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="9e5dc-110">`Control` + `Shift` + `I` \ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-110">Press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="9e5dc-111">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-111">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="9e5dc-112">[**設定**] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-112">Open the **Settings** pane.</span></span>  
    *   <span data-ttu-id="9e5dc-113">キーを押し `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-113">Press `Shift`+`?`.</span></span>  <span data-ttu-id="9e5dc-114">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-114">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="9e5dc-115">[**設定**] ウィンドウの左側で、[**実験**] セクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-115">On the left side of the **Settings** pane, select the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.png":::
       <span data-ttu-id="9e5dc-117">DevTools の設定での実験の一覧</span><span class="sxs-lookup"><span data-stu-id="9e5dc-117">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9e5dc-118">[**実験**] ページで、使用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-118">On the **Experiments** page, scroll through the list of all available experimental features and select the checkbox next to each features that you want to test.</span></span>  
1.  <span data-ttu-id="9e5dc-119">Microsoft Edge DevTools を閉じてからもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-119">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="9e5dc-120">実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-120">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="9e5dc-121">実験的な機能を無効にするには、[**実験**] ページを開き、無効にする実験的機能のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-121">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="9e5dc-122">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="9e5dc-122">Highlighted experimental features</span></span>  

<span data-ttu-id="9e5dc-123">以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-123">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="9e5dc-124">実験的機能</span><span class="sxs-lookup"><span data-stu-id="9e5dc-124">Experimental feature</span></span> | <span data-ttu-id="9e5dc-125">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="9e5dc-125">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="9e5dc-126">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="9e5dc-126">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="9e5dc-127">85以降</span><span class="sxs-lookup"><span data-stu-id="9e5dc-127">85 or later</span></span> |  
| [<span data-ttu-id="9e5dc-128">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="9e5dc-128">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="9e5dc-129">85以降</span><span class="sxs-lookup"><span data-stu-id="9e5dc-129">85 or later</span></span> |  
| [<span data-ttu-id="9e5dc-130">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="9e5dc-130">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="9e5dc-131">85以降</span><span class="sxs-lookup"><span data-stu-id="9e5dc-131">85 or later</span></span> |  

### <span data-ttu-id="9e5dc-132">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="9e5dc-132">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="9e5dc-133">CSS グリッドレイアウトを含む web サイトをデバッグするときに、ページの視覚エフェクトを向上させます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-133">Improves on-page visualizations when you debug websites that have CSS grid layouts.</span></span>  <span data-ttu-id="9e5dc-134">DevTools の設定では、オーバーレイをさらにカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-134">You may further customize the overlays in DevTools Settings.</span></span>  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.png":::
   <span data-ttu-id="9e5dc-136">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="9e5dc-136">CSS grid debugging feature</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="9e5dc-137">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="9e5dc-137">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="9e5dc-138">通常、**要素**や**ネットワーク**などのツールは、devtools のメイン \ (トップ) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-138">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="9e5dc-139">同様に、 **3D ビュー**や**問題**などのツールは、devtools のドローワ \ (ボトム \) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-139">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="9e5dc-140">この実験が選択されている場合は、タブ上でマウスをポイントし、コンテキストメニューを開き (右クリック \)、[**上へ移動**] または [**下へ移動] を**選択して、ツールを上下のパネル間で移動することができます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-140">When this experiment is selected, you may move tools between the top and bottom panels by hovering on the tab, opening the contextual menu \(right-click\), and selecting **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="9e5dc-141">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-141">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="9e5dc-142">下部パネルの表示と非表示を切り替えるには、キーを押し `Escape` ます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-142">To show or hide the bottom panel, press `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.png":::
   <span data-ttu-id="9e5dc-144">パネル間でタブを移動する</span><span class="sxs-lookup"><span data-stu-id="9e5dc-144">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="9e5dc-145">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="9e5dc-145">Enable webhint</span></span>  

<span data-ttu-id="9e5dc-146">[webhint][WebhintMain]は、アクセシビリティ、クロスブラウザーの互換性、セキュリティ、パフォーマンス、pwas、web サイトのその他の一般的な web 開発の問題に関するフィードバックをリアルタイムで提供するオープンソースツールです。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-146">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="9e5dc-147">この実験では、[[問題][DevtoolsIssues]] パネルの devtools に対する webhint のフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-147">This experiment brings the webhint feedback into DevTools in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="9e5dc-148">この問題を選択すると、問題の解決方法と、web サイト上の影響を受けるリソースの一覧についてのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-148">You may select the issue to see documentation on how to fix the issue and a list of the affected resources on your website.</span></span>  <span data-ttu-id="9e5dc-149">リソースリンクを選んで、DevTools で関連する**ネットワーク**、**ソース**、または**要素**のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-149">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.png":::
   <span data-ttu-id="9e5dc-151">[問題] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="9e5dc-151">webhint feedback in the Issues panel</span></span>  
:::image-end:::      

<!--Available in Microsoft Edge version 85 and later.  -->  

## <span data-ttu-id="9e5dc-152">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="9e5dc-152">Previous experimental features</span></span>  

*   <span data-ttu-id="9e5dc-153">Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3DView]を使用できるようになり、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-153">[3D View][Devtools3DView] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  

## <span data-ttu-id="9e5dc-154">実験的な機能についてフィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="9e5dc-154">Providing feedback on experimental features</span></span>  

<span data-ttu-id="9e5dc-155">Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能に関するフィードバックを提供するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9e5dc-155">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools:</span></span>  

*   <span data-ttu-id="9e5dc-156">DevTools のフィードバックアイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="9e5dc-156">Send your feedback using the Feedback icon in the DevTools</span></span>  
*   <span data-ttu-id="9e5dc-157">[@EdgeDevTools][TwitterEdgedevtools]ツイート</span><span class="sxs-lookup"><span data-stu-id="9e5dc-157">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/devtools-feedback.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン" lightbox="./media/devtools-feedback.png":::
   <span data-ttu-id="9e5dc-159">Microsoft Edge DevTools のフィードバックアイコン</span><span class="sxs-lookup"><span data-stu-id="9e5dc-159">Feedback icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[Devtools3DView]: ./3D-view.md "3D ビュー |Microsoft ドキュメント"  
[DevtoolsIssues]: ./issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット-Microsoft ドキュメント"  
[DevtoolsOpen]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "web ヒント" 
