---
description: Microsoft Edge DevTools の最新の実験的機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 実験
ms.openlocfilehash: b366cfeccafe874bc9e76d3b66659122c5d07c69
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398680"
---
# <a name="experimental-features"></a><span data-ttu-id="cf249-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="cf249-104">Experimental features</span></span>  

<span data-ttu-id="cf249-105">Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cf249-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="cf249-106">各機能がリリースされる [前に、テストして](#providing-feedback-on-experimental-features) フィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="cf249-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="cf249-107">実験機能は Microsoft Edge のすべてのチャネルで利用できます。Microsoft Edge Canary チャネルを使用すると、最新の実験機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="cf249-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-108">Turn on experimental features</span></span>  

<span data-ttu-id="cf249-109">Microsoft Edge で \(or off\) 実験機能を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf249-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="cf249-110">[DevTools を開きます][DevtoolsOpenMain]。</span><span class="sxs-lookup"><span data-stu-id="cf249-110">[Open DevTools][DevtoolsOpenMain].</span></span>  
    *   <span data-ttu-id="cf249-111">`Control` + `Shift` + `I` \(Windows, Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="cf249-112">詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="cf249-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="cf249-113">[設定] [ウィンドウを開][DevToolsCustomizeIndexSettings] きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-113">Open the [Settings][DevToolsCustomizeIndexSettings] pane.</span></span>  
    *   <span data-ttu-id="cf249-114">を選択します `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="cf249-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="cf249-115">詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevToolsShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="cf249-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="cf249-116">[設定] ウィンドウの左側 **で** 、[実験] **セクションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="cf249-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="[設定] の [実験] ページ" lightbox="../media/experiments-devtools.msft.png":::
       <span data-ttu-id="cf249-118">[ **設定] の** [実験] **ページ**</span><span class="sxs-lookup"><span data-stu-id="cf249-118">The **Experiments** page in **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cf249-119">[実験 **] ページで** 、利用可能なすべての実験機能の一覧をスクロールし、テストする各機能の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cf249-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="cf249-120">Microsoft Edge DevTools を閉じて再度開きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-120">Close and reopen Microsoft Edge DevTools.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="cf249-121">実験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf249-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="cf249-122">実験機能をオフにするには、[実験] ページ **を** 開き、無効にする実験機能のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="cf249-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <a name="highlighted-experimental-features"></a><span data-ttu-id="cf249-123">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="cf249-123">Highlighted experimental features</span></span>  

<span data-ttu-id="cf249-124">次のセクションでは、Microsoft Edge で使用できる新しい実験的機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf249-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="cf249-125">試験的機能</span><span class="sxs-lookup"><span data-stu-id="cf249-125">Experimental feature</span></span> | <span data-ttu-id="cf249-126">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="cf249-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="cf249-127">Webhint を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-127">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="cf249-128">85 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-128">85 or later</span></span> |  
| [<span data-ttu-id="cf249-129">ネットワーク コンソールの有効化</span><span class="sxs-lookup"><span data-stu-id="cf249-129">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="cf249-130">85 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-130">85 or later</span></span> |  
| [<span data-ttu-id="cf249-131">ソース オーダー ビューアー</span><span class="sxs-lookup"><span data-stu-id="cf249-131">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="cf249-132">86 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-132">86 or later</span></span> |  
| [<span data-ttu-id="cf249-133">キーボード ショートカット エディターを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-133">Enable keyboard shortcut editor</span></span>](#enable-keyboard-shortcut-editor) | <span data-ttu-id="cf249-134">87 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-134">87 or later</span></span> |  
| [<span data-ttu-id="cf249-135">3D ビューで複合レイヤーを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-135">Enable Composited Layers in 3D View</span></span>](#enable-composited-layers-in-3d-view) | <span data-ttu-id="cf249-136">87 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-136">87 or later</span></span> |  
| [<span data-ttu-id="cf249-137">[スタイル] ウィンドウ内で新しいフォント エディター ツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-137">Enable new Font Editor tool within the Styles pane</span></span>](#enable-new-font-editor-tool-within-the-styles-pane) | <span data-ttu-id="cf249-138">89 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-138">89 or later</span></span> |  
| [<span data-ttu-id="cf249-139">CSS Flexbox の新しいデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-139">Enable new CSS Flexbox debugging features</span></span>](#enable-new-css-flexbox-debugging-features) | <span data-ttu-id="cf249-140">89 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-140">89 or later</span></span> |  
| [<span data-ttu-id="cf249-141">[+ ボタン] タブ メニューを有効にして、その他のツールを開く</span><span class="sxs-lookup"><span data-stu-id="cf249-141">Enable + button tab menus to open more tools</span></span>](#enable--button-tab-menus-to-open-more-tools) | <span data-ttu-id="cf249-142">89 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-142">89 or later</span></span> |  
| [<span data-ttu-id="cf249-143">[ようこそ] タブを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-143">Enable Welcome tab</span></span>](#enable-welcome-tool) | <span data-ttu-id="cf249-144">89 以降</span><span class="sxs-lookup"><span data-stu-id="cf249-144">89 or later</span></span> |  

### <a name="enable-new-css-grid-debugging-features"></a><span data-ttu-id="cf249-145">新しい CSS グリッド デバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-145">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="cf249-146">この実験的な機能は、CSS グリッド レイアウトのデバッグに役立つ多数の新しい視覚化を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf249-146">This experimental feature provides a number of new visualizations to help you debug CSS grid layouts.</span></span>  <span data-ttu-id="cf249-147">最新の実験機能をプレビューするには、この [実験を有効にして](#turn-on-experimental-features) DevTools を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="cf249-147">To preview the latest experimental features, [enable this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  <span data-ttu-id="cf249-148">この実験は、Microsoft Edge バージョン 87 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cf249-148">This experiment is on by default in Microsoft Edge version 87 or later.</span></span>  

#### <a name="viewing-on-hover-grid-overlays-with-the-inspect-tool"></a><span data-ttu-id="cf249-149">[検査] ツールを使用してオンホバー グリッド オーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="cf249-149">Viewing on-hover grid overlays with the Inspect tool</span></span>  

<span data-ttu-id="cf249-150">[ **検査** ] ツールを使用すると、Web サイト内の CSS グリッド レイアウトをマウスでホバーして識別し、視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-150">The **Inspect** tool provides a quick way to identify and visualize CSS Grid layouts in a website by hovering over them with the mouse.</span></span>  <span data-ttu-id="cf249-151">DevTools **の** 左上隅にある ![ [検査 ](../media/inspect-icon.msft.png) \( Inspect \) ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-151">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="cf249-152">次に、デバッグする `Grid` Web ページの要素にマウス ポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-152">Then, hover on a `Grid` element on the webpage you are debugging.</span></span>  <span data-ttu-id="cf249-153">アウトラインはグリッドの周囲に表示され、ハッチングはグリッドギャップが存在する場合の位置を示します。</span><span class="sxs-lookup"><span data-stu-id="cf249-153">Outlines are displayed around the grid, and hatching indicates the location of grid gaps if present.</span></span>  

:::image type="complex" source="../media/grid-inspect.msft.png" alt-text="[検査] ツールを使用してグリッドを表示する" lightbox="../media/grid-inspect.msft.png":::
   <span data-ttu-id="cf249-155">[検査] ツールを使用してグリッド **を表示** する</span><span class="sxs-lookup"><span data-stu-id="cf249-155">Viewing grids with the **Inspect** tool</span></span>  
:::image-end:::  

#### <a name="viewing-persistent-grid-overlays"></a><span data-ttu-id="cf249-156">永続的なグリッド オーバーレイの表示</span><span class="sxs-lookup"><span data-stu-id="cf249-156">Viewing persistent grid overlays</span></span>  

<span data-ttu-id="cf249-157">Microsoft Edge バージョン 86 以降では、実験的な CSS グリッド機能では、永続的なグリッド オーバーレイを有効にするオプションも提供しています。</span><span class="sxs-lookup"><span data-stu-id="cf249-157">In Microsoft Edge version 86 or later, the experimental CSS grid feature also offers the option to enable persistent Grid overlays.</span></span>  <span data-ttu-id="cf249-158">永続的なオーバーレイには、いくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="cf249-158">The persistent overlays provide several benefits.</span></span>  

*   <span data-ttu-id="cf249-159">永続的なオーバーレイは、スクロール、マウスの移動、DevTools の他の機能の使用時にページに表示されたままです。</span><span class="sxs-lookup"><span data-stu-id="cf249-159">The persistent overlays remain visible on the page as you scroll, move your mouse, and use other features of the DevTools.</span></span>  
*   <span data-ttu-id="cf249-160">複数の永続的なオーバーレイを同時にオンにすることで、複数のグリッド レイアウトを一度に確認できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-160">Multiple persistent overlays may be turned on at the same time, allowing you to review several grid layouts at once.</span></span>  
*   <span data-ttu-id="cf249-161">永続的なオーバーレイには、グリッド領域の名前の非表示や表示、グリッドギャップ、トラックサイズなど、多くの構成オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="cf249-161">Persistent overlays offer many configuration options, such as hiding or showing names in the grid area, grid gaps, track sizes, and so on.</span></span>  
    
<span data-ttu-id="cf249-162">永続的なグリッド オーバーレイを切り替える 2 つの方法。</span><span class="sxs-lookup"><span data-stu-id="cf249-162">The two ways to toggle a persistent grid overlay.</span></span>  

*   <span data-ttu-id="cf249-163">要素ツール **の DOM** ツリーに表示される Grid 要素の横にあるグリッド楕円アイコンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="cf249-163">Choose the **Grid** oval icon next to any Grid element shown in the DOM tree of the **Elements** tool.</span></span>  
    
    :::image type="complex" source="../media/grid-adorner.msft.png" alt-text="要素ツールのグリッド楕円アイコン" lightbox="../media/grid-adorner.msft.png":::
       <span data-ttu-id="cf249-165">要素ツールのグリッド **楕円** アイコン</span><span class="sxs-lookup"><span data-stu-id="cf249-165">Grid oval icon in **Elements** tool</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="cf249-166">[要素] **ツールにある** 新しいレイアウト パネルを開き、強調表示する各 Grid 要素の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cf249-166">Open the new **Layout** panel located in the Elements tool, and choose the checkbox next to each Grid element you want to highlight.</span></span>  
    
    :::image type="complex" source="../media/grid-layout-zoom.msft.png" alt-text="DevTools のレイアウト パネル" lightbox="../media/grid-layout-zoom.msft.png":::
       <span data-ttu-id="cf249-168">\*\*\*\* DevTools のレイアウト パネル</span><span class="sxs-lookup"><span data-stu-id="cf249-168">**Layout** panel in DevTools</span></span>  
    :::image-end:::  
    
#### <a name="configuring-persistent-overlays"></a><span data-ttu-id="cf249-169">永続的なオーバーレイの構成</span><span class="sxs-lookup"><span data-stu-id="cf249-169">Configuring persistent overlays</span></span>  

<span data-ttu-id="cf249-170">Microsoft Edge バージョン 86 以降では、新しいレイアウト パネルが\*\*\*\*[スタイル]\*\*\*\* パネルと [計算] パネルと並んで [要素] ツール**に配置**されます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cf249-170">In Microsoft Edge version 86 or later, the new **Layout** panel is located in the **Elements** tool alongside the **Styles** and **Computed** panels.</span></span>  <span data-ttu-id="cf249-171">レイアウト **パネルは** 、永続的なオーバーレイの構成オプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf249-171">The **Layout** panel surfaces configuration options for persistent overlays.</span></span>  

:::image type="complex" source="../media/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="../media/experiments-grid.msft.png":::
   <span data-ttu-id="cf249-173">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="cf249-173">CSS grid debugging feature</span></span>  
:::image-end:::  

### <a name="enable-support-to-move-tabs-between-panels"></a><span data-ttu-id="cf249-174">パネル間でタブを移動するサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-174">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="cf249-175">通常、Elements や\*\*\*\*\*\*Network\*\*などのツールは、DevTools の上部にあるメイン パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="cf249-175">Normally, tools such as **Elements** and **Network** may only open in the main panel that is located at the top of the DevTools.</span></span>  <span data-ttu-id="cf249-176">**3D ビュー**や**Issues**のようなツールで、通常は\*\*\*\* DevTools の下部にあるドロワー パネルでのみ開きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-176">Tools like **3D View** and **Issues** which normally only open in the **Drawer** panel that is located at the bottom of the DevTools.</span></span>  <span data-ttu-id="cf249-177">実験を選択した後、上部パネルと下部パネルの間でツールを移動できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-177">After you choose the experiment, you may move tools between the top and bottom panels.</span></span>  <span data-ttu-id="cf249-178">ツールを移動するには、タブにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[上へ移動] または [下へ移動]**を選択します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cf249-178">To move a tool, hover on the tab, open the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="cf249-179">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="cf249-179">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="cf249-180">ドロワー パネルを表示または非表示 **にする** 場合は、 を選択します `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="cf249-180">To display or hide the **Drawer** panel, select `Escape`.</span></span>  

:::image type="complex" source="../media/experiments-move-panels.msft.png" alt-text="パネル間でのツールの移動" lightbox="../media/experiments-move-panels.msft.png":::
   <span data-ttu-id="cf249-182">パネル間でのツールの移動</span><span class="sxs-lookup"><span data-stu-id="cf249-182">Moving tools between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="enable-webhint"></a><span data-ttu-id="cf249-183">Webhint を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-183">Enable webhint</span></span>  

<span data-ttu-id="cf249-184">[webhint][WebhintMain] は、Web サイトとローカル Web ページにリアルタイムのフィードバックを提供するオープン ソース ツールです。</span><span class="sxs-lookup"><span data-stu-id="cf249-184">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="cf249-185">webhint によって提供される [フィードバックの種類][WebhintMain]。</span><span class="sxs-lookup"><span data-stu-id="cf249-185">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="cf249-186">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="cf249-186">accessibility</span></span>  
*   <span data-ttu-id="cf249-187">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="cf249-187">cross-browser compatibility</span></span>  
*   <span data-ttu-id="cf249-188">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="cf249-188">security</span></span>  
*   <span data-ttu-id="cf249-189">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="cf249-189">performance</span></span>  
*   <span data-ttu-id="cf249-190">プログレッシブ Web アプリ (PWA)</span><span class="sxs-lookup"><span data-stu-id="cf249-190">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="cf249-191">その他の一般的な Web 開発の問題</span><span class="sxs-lookup"><span data-stu-id="cf249-191">other common web development issues</span></span>  
    
<span data-ttu-id="cf249-192">[webhint 実験では][WebhintMain]、[問題] パネルに webhint フィードバック[が表示][DevtoolsIssues]されます。</span><span class="sxs-lookup"><span data-stu-id="cf249-192">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="cf249-193">問題を選択して、ソリューションドキュメントと影響を受けるリソースの一覧を Web サイトに表示します。</span><span class="sxs-lookup"><span data-stu-id="cf249-193">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="cf249-194">リソース リンクを選択して、DevTools**で関連する** **[ネットワーク**] 、[ソース] 、または **[要素]** ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-194">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../media/experiments-webhint.msft.png":::
   <span data-ttu-id="cf249-196">[問題] パネルの**webhint フィードバック**</span><span class="sxs-lookup"><span data-stu-id="cf249-196">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="enable-network-console"></a><span data-ttu-id="cf249-197">ネットワーク コンソールの有効化</span><span class="sxs-lookup"><span data-stu-id="cf249-197">Enable Network Console</span></span>  

<span data-ttu-id="cf249-198">**ネットワーク コンソール** は、HTTP を使用してネットワークの代理要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="cf249-198">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="cf249-199">ネットワーク コンソールの実験 **を使用して** 、Web API 要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-199">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="cf249-200">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="cf249-200">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="cf249-201">ネットワーク コンソールを **使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf249-201">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="cf249-202">[ネットワーク] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-202">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="cf249-203">変更するネットワーク要求を見つけて再送信します。</span><span class="sxs-lookup"><span data-stu-id="cf249-203">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="cf249-204">コンテキスト メニュー \(右クリック\) を開き、[編集] と [ **再生] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf249-204">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="cf249-205">ネットワーク コンソール **が開いたら** 、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="cf249-205">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="cf249-206">[送信 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf249-206">Choose **Send**.</span></span>  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="コンソール ドロワーのネットワーク コンソール" lightbox="../media/network-network-console.msft.png":::
   <span data-ttu-id="cf249-208">**コンソール ドロワー\*\*\*\*のネットワーク**コンソール</span><span class="sxs-lookup"><span data-stu-id="cf249-208">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="source-order-viewer"></a><span data-ttu-id="cf249-209">ソース オーダー ビューアー</span><span class="sxs-lookup"><span data-stu-id="cf249-209">Source Order Viewer</span></span>  

<span data-ttu-id="cf249-210">**ソース オーダー ビューアー** は、Web ページ ソース内の要素の順序を表示する実験です。</span><span class="sxs-lookup"><span data-stu-id="cf249-210">**Source Order Viewer** is an experiment that displays the order of elements in the webpage source.</span></span>  <span data-ttu-id="cf249-211">画面の表示順序がソースの順序と異なる場合があります。これはスクリーン リーダーとキーボード のユーザーを混同します。</span><span class="sxs-lookup"><span data-stu-id="cf249-211">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="cf249-212">[ソースオーダー **ビューアー] 実験** を使用して、画面の表示順序とソースの順序の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf249-212">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="cf249-213">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="cf249-213">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="cf249-214">ソース オーダー **ビューアーを使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf249-214">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="cf249-215">[要素] **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-215">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="cf249-216">引き出し \(bottom\) パネルで [アクセシビリティ] ウィンドウを開きます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cf249-216">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="cf249-217">[ソース注文 **ビューアー] セクションで** 、[ソースの順序を **表示する] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="cf249-217">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="cf249-218">任意の HTML 要素を強調表示して、Web ページ ソース内の順序をオーバーレイで表示します。</span><span class="sxs-lookup"><span data-stu-id="cf249-218">Highlight any HTML element to display an overlay that the order in the webpage source.</span></span>  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウの [ソースオーダー ビューアー]" lightbox="../media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="cf249-220">**[アクセシビリティ] ウィンドウ** の **[ソースオーダー** ビューアー]</span><span class="sxs-lookup"><span data-stu-id="cf249-220">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <a name="enable-keyboard-shortcut-editor"></a><span data-ttu-id="cf249-221">キーボード ショートカット エディターを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-221">Enable keyboard shortcut editor</span></span>

<span data-ttu-id="cf249-222">[キーボード **ショートカット エディターの有効化]** 実験を有効にすると、DevTools 内の任意のアクションに合わせてキーボード ショートカットをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="cf249-222">With the **Enable keyboard shortcut editor** experiment turned on, you may customize keyboard shortcuts for any action in the DevTools.</span></span>  <span data-ttu-id="cf249-223">特定のアクションのキーボード ショートカットをカスタマイズするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf249-223">To customize the keyboard shortcut for a specific action, complete the following steps.</span></span>  

1.  <span data-ttu-id="cf249-224">[DevTools を開きます][DevtoolsOpenMain]。</span><span class="sxs-lookup"><span data-stu-id="cf249-224">[Open DevTools][DevtoolsOpenMain].</span></span>  
1.  <span data-ttu-id="cf249-225">[設定 [] を開きます][DevToolsCustomizeIndexSettings]。</span><span class="sxs-lookup"><span data-stu-id="cf249-225">Open [Settings][DevToolsCustomizeIndexSettings].</span></span>  
    *   <span data-ttu-id="cf249-226">を選択します `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="cf249-226">Select `Shift`+`?`.</span></span>  
1.  <span data-ttu-id="cf249-227">[ショートカット] ページ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="cf249-227">Navigate to the **Shortcuts** page.</span></span>  
1.  <span data-ttu-id="cf249-228">カスタマイズするアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-228">Choose the action you want to customize.</span></span>  
1.  <span data-ttu-id="cf249-229">[編集\*\*\*\* \( ![ EditKeyboardShortcut ](../media/edit-keyboard-shortcut-icon.msft.png) \) ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-229">Choose the **Edit** \(![EditKeyboardShortcut](../media/edit-keyboard-shortcut-icon.msft.png)\) icon.</span></span>  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="[設定] の [ショートカット] ページからカスタマイズするアクションを選択します。" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       <span data-ttu-id="cf249-231">[設定] の [ショートカット] ページ **から** カスタマイズするアクションを選択 [します。][DevToolsCustomizeIndexSettings]</span><span class="sxs-lookup"><span data-stu-id="cf249-231">Choose the action to customize from the **Shortcuts** page in [Settings][DevToolsCustomizeIndexSettings]</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cf249-232">キーボードで、アクションにバインドするキーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-232">On the keyboard, select the keys to bind to the action.</span></span>  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="アクションに割り当てるキーを選択する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="cf249-234">アクションに割り当てるキーを選択する</span><span class="sxs-lookup"><span data-stu-id="cf249-234">Choose the keys you want to assign to the action</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cf249-235">新しいキーボード ショートカットを保存するには、チェックマーク \(</span><span class="sxs-lookup"><span data-stu-id="cf249-235">To save your new keyboard shortcut, choose the checkmark \(</span></span>![CheckmarkKeyboardShortcut](../media/checkmark-keyboard-shortcut-icon.msft.png)<span data-ttu-id="cf249-237">\) アイコン。</span><span class="sxs-lookup"><span data-stu-id="cf249-237">\) icon.</span></span>  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="チェックマークアイコンを選択して新しいキーボード ショートカットを保存する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       <span data-ttu-id="cf249-239">チェックマークアイコンを選択して新しいキーボード ショートカットを保存する</span><span class="sxs-lookup"><span data-stu-id="cf249-239">Choose the checkmark icon to save your new keyboard shortcut</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="cf249-240">新しいキーボード ショートカットを選択して、DevTools でアクションをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="cf249-240">Select your new keyboard shortcut to trigger the action in the DevTools.</span></span>  
    
<span data-ttu-id="cf249-241">[ショートカット **] ページで** 、カスタム **キーボード** ショートカット \( ![ CustomKeyboardShortcut \) アイコンに、カスタマイズした ](../media/custom-keyboard-shortcut-icon.msft.png) キーボード ショートカットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf249-241">On the **Shortcuts** page, the **Custom Keyboard Shortcut** \(![CustomKeyboardShortcut](../media/custom-keyboard-shortcut-icon.msft.png)\) icon displays keyboard shortcuts you customized.</span></span>  <span data-ttu-id="cf249-242">すべてのショートカットをリセットするには、[既定のショートカット **を復元する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf249-242">To reset all shortcuts, choose **Restore default shortcuts**.</span></span>  

<span data-ttu-id="cf249-243">アクションのキーボード ショートカットの編集中に変更を破棄するには、X \( ![ XKeyboardShortcut ](../media/discard-changes-keyboard-shortcut-icon.msft.png) \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-243">To discard your changes while you edit the keyboard shortcuts for an action, choose the X \(![XKeyboardShortcut](../media/discard-changes-keyboard-shortcut-icon.msft.png)\) icon.</span></span>  <span data-ttu-id="cf249-244">特定のアクションのショートカットを削除するには、[削除] ショートカット **\(** ![ DeleteKeyboardShortcut ](../media/delete-keyboard-shortcut-icon.msft.png) \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-244">To remove shortcuts for a specific action, choose the **Delete shortcut** \(![DeleteKeyboardShortcut](../media/delete-keyboard-shortcut-icon.msft.png)\) icon.</span></span>  <span data-ttu-id="cf249-245">アクションに複数のショートカットを追加するには、[ショートカットの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf249-245">To add multiple shortcuts for an action, choose **Add a shortcut**.</span></span>  

> [!NOTE]
> <span data-ttu-id="cf249-246">キーボード ショートカットが現在別のアクションに割り当てられている場合は、新しいアクションに保存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf249-246">If a keyboard shortcut is currently assigned to another action, you may not save it for a new action.</span></span>  <span data-ttu-id="cf249-247">最初に、前の操作のキーボード ショートカットを削除してから、新しいアクションに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf249-247">You must first delete the keyboard shortcut for the previous action and then add it to the new action.</span></span>  

<!--Available in Microsoft Edge version 87 and later.  -->  

### <a name="enable-composited-layers-in-3d-view"></a><span data-ttu-id="cf249-248">3D ビューで複合レイヤーを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-248">Enable Composited Layers in 3D View</span></span>  

<span data-ttu-id="cf249-249">z-indexes と Document Object Model \(DOM\) と並んでレイヤーを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-249">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="cf249-250">この機能は、コンテキストを頻繁に切り替えることなくデバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf249-250">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="cf249-251">コンテキスト切り替えの削減が大きな問題だと特定しました。</span><span class="sxs-lookup"><span data-stu-id="cf249-251">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="cf249-252">作成するコードが Web アプリに与える影響は必ずしも明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="cf249-252">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="cf249-253">視覚的なデバッグを総合的に行う目的で、3D ビューレイヤーと複合レイヤーが結合されました。</span><span class="sxs-lookup"><span data-stu-id="cf249-253">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  

<span data-ttu-id="cf249-254">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="cf249-254">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="cf249-255">コンポジット レイヤー **を使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf249-255">To use **Composited Layers**, complete the following steps.</span></span>  

1.  <span data-ttu-id="cf249-256">ドロワーで **、[3D ビュー] ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="cf249-256">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="cf249-257">[複合 **レイヤー] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-257">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="cf249-258">アプリのすべてのペイントされたレイヤーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf249-258">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="cf249-259">独自の Web アプリでこの機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="cf249-259">Try this feature with your own web apps.</span></span>  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="cf249-261">**[コンポジット レイヤー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="cf249-261">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### <a name="enable-new-font-editor-tool-within-the-styles-pane"></a><span data-ttu-id="cf249-262">[スタイル] ウィンドウ内で新しいフォント エディター ツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-262">Enable new Font Editor tool within the Styles pane</span></span>  

<span data-ttu-id="cf249-263">これで、新しいビジュアル フォント エディターを [使用してフォント][DevtoolsInspectStylesEditFonts] を編集できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-263">You may now use the new visual [Font Editor][DevtoolsInspectStylesEditFonts] to edit fonts.</span></span>  <span data-ttu-id="cf249-264">フォントとフォントの特性を定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="cf249-264">Use it define fonts and font characteristics.</span></span>  <span data-ttu-id="cf249-265">ビジュアル フォント エディター **を使用すると** 、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-265">The visual **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="cf249-266">さまざまなフォント プロパティの単位を切り替える</span><span class="sxs-lookup"><span data-stu-id="cf249-266">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="cf249-267">異なるフォント プロパティのキーワードを切り替える</span><span class="sxs-lookup"><span data-stu-id="cf249-267">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="cf249-268">単位の変換</span><span class="sxs-lookup"><span data-stu-id="cf249-268">Convert units</span></span>  
*   <span data-ttu-id="cf249-269">正確な CSS コードを生成する</span><span class="sxs-lookup"><span data-stu-id="cf249-269">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="cf249-270">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="cf249-270">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="cf249-271">新しいビジュアル フォント エディターを **使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf249-271">To use the new visual **Font Editor**, complete the following steps.</span></span>  

1.  <span data-ttu-id="cf249-272">[要素] **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-272">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="cf249-273">[スタイル] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-273">Open the **Styles** pane.</span></span>  
1.  <span data-ttu-id="cf249-274">[フォント エディター **] アイコンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-274">Choose the **Font Editor** icon.</span></span>  
    
<span data-ttu-id="cf249-275">新しいビジュアル フォント エディターの詳細については[、DevTools][DevtoolsInspectStylesEditFonts]の [スタイル] ウィンドウの [CSS フォントスタイルと設定の編集] に移動します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cf249-275">For more information about the new visual **Font Editor**, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="ビジュアル の [フォント エディター] ウィンドウが強調表示されます" lightbox="../media/font-editor-open.msft.png":::
   <span data-ttu-id="cf249-277">ビジュアル の [ **フォント エディター]** ウィンドウが強調表示されます</span><span class="sxs-lookup"><span data-stu-id="cf249-277">The visual **Font Editor** pane is highlighted</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-new-css-flexbox-debugging-features"></a><span data-ttu-id="cf249-278">CSS Flexbox の新しいデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-278">Enable new CSS Flexbox debugging features</span></span>  

<span data-ttu-id="cf249-279">この実験的な機能は、CSS Flexbox レイアウトのデバッグに役立つ多くの新しい視覚化を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf249-279">This experimental feature provides many new visualizations to help you debug CSS Flexbox layouts.</span></span>  <span data-ttu-id="cf249-280">最新の実験機能をプレビューするには、 [この実験を有効にし](#turn-on-experimental-features) 、DevTools を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="cf249-280">To preview the latest experimental features, [turn on this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a><span data-ttu-id="cf249-281">[検査] ツールを使用して Flexbox レイアウトに永続的なオーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="cf249-281">Display persistent overlays on Flexbox layouts with the Inspect tool</span></span>  

<span data-ttu-id="cf249-282">[ **検査** ] ツールを使用すると、Web サイト内の CSS Flexbox レイアウトをマウスでホバーして識別し、視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-282">The **Inspect** tool provides a quick way to identify and visualize CSS Flexbox layouts in a website by hovering on them with the mouse.</span></span>  <span data-ttu-id="cf249-283">DevTools **の** 左上隅にある ![ [検査 ](../media/inspect-icon.msft.png) \( Inspect \) ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-283">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="cf249-284">次に、Web サイトのデバッグ中に、flex コンテナーにカーソルを合わせると、flex コンテナーの周囲にアウトラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf249-284">Then, while debugging the website, hover on a flex container to display outlines around the flex container.</span></span>  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="検査ツールを使用して Flexbox コンテナーを表示する" lightbox="../media/flexbox-hover.msft.png":::
   <span data-ttu-id="cf249-286">検査ツールを使用して Flexbox コンテナー **を表示** する</span><span class="sxs-lookup"><span data-stu-id="cf249-286">Display Flexbox containers with the **Inspect** tool</span></span>  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a><span data-ttu-id="cf249-287">Flexbox レイアウトに永続的なオーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="cf249-287">Display persistent overlays on Flexbox layouts</span></span>  

<span data-ttu-id="cf249-288">Microsoft Edge バージョン 89 以降では、実験的な CSS Flexbox 機能では、Flexbox レイアウトで永続的なオーバーレイを有効にするオプションも提供しています。</span><span class="sxs-lookup"><span data-stu-id="cf249-288">In Microsoft Edge version 89 or later, the experimental CSS Flexbox feature also offers the option to turn on persistent overlays on Flexbox layouts.</span></span>  <span data-ttu-id="cf249-289">永続的なオーバーレイには、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="cf249-289">Persistent overlays provide the following benefits.</span></span>  

*   <span data-ttu-id="cf249-290">永続的なオーバーレイは、スクロール、マウスの移動、DevTools の他の機能の使用時に Web ページに表示されたままです。</span><span class="sxs-lookup"><span data-stu-id="cf249-290">Persistent overlays remain visible on the webpage as you scroll, move your mouse, and use other features of the DevTools.</span></span>
*   <span data-ttu-id="cf249-291">複数の永続的なオーバーレイを同時に使用して、複数の Flexbox レイアウトを一度に確認できます。</span><span class="sxs-lookup"><span data-stu-id="cf249-291">Multiple persistent overlays may be used at the same time, to allow you to review several Flexbox layouts at once.</span></span>  
*   <span data-ttu-id="cf249-292">永続的なオーバーレイは、色構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf249-292">Persistent overlays offer color configuration options.</span></span>  
    
<span data-ttu-id="cf249-293">Flexbox レイアウトの永続的なオーバーレイを切り替えるには、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf249-293">To toggle persistent overlays on Flexbox layout, use one of following actions.</span></span>  

*   <span data-ttu-id="cf249-294">要素ツール **の DOM ツリー** に表示される Flexbox コンテナーの横にある [Flexbox 楕円] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="cf249-294">Choose the **Flexbox** oval icon next to any Flexbox container displayed in the DOM tree of the **Elements** tool.</span></span>  
*   <span data-ttu-id="cf249-295">[要素] **ツールにある** 新しい [レイアウト] パネルを **開** き、強調表示する各 Flexbox コンテナーの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cf249-295">Open the new **Layout** panel located in the **Elements** tool, and choose the checkbox next to each Flexbox container you want to highlight.</span></span>  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools の Flex アイコンとレイアウト パネル" lightbox="../media/flexbox-overlay.msft.png":::
   <span data-ttu-id="cf249-297">DevTools **の** Flex アイコンとレイアウト パネル</span><span class="sxs-lookup"><span data-stu-id="cf249-297">Flex icons and **Layout** panel in DevTools</span></span>  
:::image-end:::  

#### <a name="configure-persistent-overlays"></a><span data-ttu-id="cf249-298">永続的なオーバーレイを構成する</span><span class="sxs-lookup"><span data-stu-id="cf249-298">Configure persistent overlays</span></span>  

<span data-ttu-id="cf249-299">CSS グリッドまたは Flexbox レイアウトの永続的オーバーレイのオプションを構成するには、[レイアウト] ウィンドウ **を使用** します。</span><span class="sxs-lookup"><span data-stu-id="cf249-299">To configure options for persistent overlays for CSS grids or Flexbox layouts, use the **Layout** pane.</span></span>  <span data-ttu-id="cf249-300">[ **レイアウト** ] ウィンドウは、[スタイル] ウィンドウと **[** 計算] ウィンドウの横にある **[** 要素] **ツールに** 配置されます。</span><span class="sxs-lookup"><span data-stu-id="cf249-300">The **Layout** pane is located in the **Elements** tool next to the **Styles** and **Computed** panes.</span></span>  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="レイアウト パネル" lightbox="../media/flexbox-layout.msft.png":::
   <span data-ttu-id="cf249-302">レイアウト パネル</span><span class="sxs-lookup"><span data-stu-id="cf249-302">Layout panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable--button-tab-menus-to-open-more-tools"></a><span data-ttu-id="cf249-303">[+ ボタン] タブ メニューを有効にして、その他のツールを開く</span><span class="sxs-lookup"><span data-stu-id="cf249-303">Enable + button tab menus to open more tools</span></span>  

<span data-ttu-id="cf249-304">新しい [その他のツール] **\(** \) アイコンを使用して、その他のツール `+` を開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf249-304">You may now open more tools using the new **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="cf249-305">[有効にする] **+** [ボタン] タブ メニューをオンにして、さらに多くのツール実験を開き、DevTools を再読み込みすると、DevTools の上部にあるタブ グループの右側にプラス記号 \( \) が表示されます。 `+`</span><span class="sxs-lookup"><span data-stu-id="cf249-305">After you turn on the **Enable + button tab menus to open more tools** experiment and reload DevTools, a plus sign \(`+`\) displays to the right of the tab group at the top of the DevTools.</span></span>  <span data-ttu-id="cf249-306">タブ バーに追加できるその他のツールの一覧を表示するには、新しい **[** その他のツール] \( `+` \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf249-306">To display a list of other tools that you may add to the tab bar, choose the new **More Tools** \(`+`\) icon.</span></span>  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="上部ウィンドウの [その他のツール]" lightbox="../media/experiments-more-tools-button.msft.png":::
   <span data-ttu-id="cf249-308">**上部ウィンドウの** [その他のツール]</span><span class="sxs-lookup"><span data-stu-id="cf249-308">**More Tools** in the top pane</span></span>
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-welcome-tool"></a><span data-ttu-id="cf249-309">ウェルカム ツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf249-309">Enable Welcome tool</span></span>

<span data-ttu-id="cf249-310">この実験では **、What's New ツールを新** しいウェルカム ツール **に置き換** える。</span><span class="sxs-lookup"><span data-stu-id="cf249-310">This experiment replaces the **What's New** tool with the new **Welcome** tool.</span></span>  <span data-ttu-id="cf249-311">次のコンテンツの更新されたデザインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf249-311">It displays a refreshed design for the following content.</span></span>  

*   <span data-ttu-id="cf249-312">開発者向けドキュメントへのリンク</span><span class="sxs-lookup"><span data-stu-id="cf249-312">Links to developer docs</span></span>  
*   <span data-ttu-id="cf249-313">最新の機能</span><span class="sxs-lookup"><span data-stu-id="cf249-313">the latest features</span></span>  
*   <span data-ttu-id="cf249-314">リリース ノート</span><span class="sxs-lookup"><span data-stu-id="cf249-314">release notes</span></span>  
*   <span data-ttu-id="cf249-315">Microsoft Edge DevTools チームに連絡するオプション</span><span class="sxs-lookup"><span data-stu-id="cf249-315">Option to contact the Microsoft Edge DevTools team</span></span>  
    
<span data-ttu-id="cf249-316">ウェルカム **ツールは** 、Microsoft Edge への更新の後に自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="cf249-316">The **Welcome** tool opens automatically after each update to Microsoft Edge.</span></span>  <span data-ttu-id="cf249-317">更新後にウェルカム ツール\*\*\*\* が表示されるのを防ぐには、[ようこそ]\*\*\*\* ツールのタイトルの下にある更新の後、[開く] タブの横にあるチェック ボックス**を**オフにします。</span><span class="sxs-lookup"><span data-stu-id="cf249-317">To prevent the display of the **Welcome** tool after each update, clear the checkbox next to **Open tab after each update** under the **Welcome** tool title.</span></span>  

<span data-ttu-id="cf249-318">元の [What's **New]** ツールを[][DevtoolsCustomizeIndexSettings]使用する場合は、[設定の実験] に移動し、[ようこそ] タブを有効にするの横にあるチェック  >  \*\*\*\*\*\*ボックスをオフにします\*\*。</span><span class="sxs-lookup"><span data-stu-id="cf249-318">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="ウェルカム ツール" lightbox="../media/experiments-welcome.msft.png":::
   <span data-ttu-id="cf249-320">**ウェルカム** ツール</span><span class="sxs-lookup"><span data-stu-id="cf249-320">**Welcome** tool</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a><span data-ttu-id="cf249-321">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="cf249-321">Previous experimental features</span></span>  

*   <span data-ttu-id="cf249-322">Microsoft Edge バージョン 83 以降では[、3D][Devtools3dViewIndex]ビューが使用可能で、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cf249-322">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="cf249-323">[Microsoft][DevtoolsMoveTabs] Edge バージョン 85 以降では、パネル間でタブを移動するサポートを有効にし、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cf249-323">[Turn on support to move tabs between panels][DevtoolsMoveTabs] is now available and turned on by default in Microsoft Edge version 85 or later.</span></span>  
*   <span data-ttu-id="cf249-324">[Microsoft][DevtoolsCustomKeyboardShortcuts] Edge バージョン 86 以降では、[キーボード ショートカットのカスタマイズ] が使用可能になっていて、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cf249-324">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  
*   <span data-ttu-id="cf249-325">[エミュレーション: Microsoft][DevtoolsDeviceModeDualScreenAndFoldables] Edge バージョン 89 以降では、デュアル スクリーン モードをサポートし、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cf249-325">[Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
*   <span data-ttu-id="cf249-326">[新しい CSS グリッド デバッグ機能][DevtoolsCssGrid] を有効にし、Microsoft Edge バージョン 89 以降で既定で有効にしました。</span><span class="sxs-lookup"><span data-stu-id="cf249-326">[Turn on new CSS grid debugging features][DevtoolsCssGrid] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
    
## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="cf249-327">実験的な機能に関するフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="cf249-327">Providing feedback on experimental features</span></span>  

<span data-ttu-id="cf249-328">Microsoft Edge DevTools 実験、または DevTools に関連するその他のフィードバックを提供する。</span><span class="sxs-lookup"><span data-stu-id="cf249-328">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="cf249-329">DevTools の [フィードバック **の送信** ] アイコンを使用してフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="cf249-329">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="cf249-330">ツイートの [@EdgeDevTools][TwitterEdgedevtools]</span><span class="sxs-lookup"><span data-stu-id="cf249-330">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  
    
:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="cf249-332">Microsoft Edge DevTools の **[フィードバックの送信]** アイコン</span><span class="sxs-lookup"><span data-stu-id="cf249-332">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D ビュー | Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "Microsoft Edge DevTools サーバーで CSS グリッドを検査|Microsoft Docs"  
[DevtoolsMoveTabs]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ |Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools アプリケーションでデバイス モードでモバイル デバイスをシミュレート|Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsIssues]: ../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン Web エクスペリエンス|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo エミュレーターの|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモート デスクトップ クライアントの|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy Fold |Samsung"  
[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "Microsoft Edge DevTools アプリケーションでデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレート|Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
