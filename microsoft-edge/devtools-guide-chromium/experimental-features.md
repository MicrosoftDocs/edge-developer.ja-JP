---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/25/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: a5793b6f4b67add313958ad4b8cee01cb7b09dbf
ms.sourcegitcommit: 7e3644e6b1d568ab795168e421c013814efa0073
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996160"
---
# <span data-ttu-id="edc38-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="edc38-104">Experimental features</span></span>  

<span data-ttu-id="edc38-105">Microsoft Edge DevTools でまだ開発中の実験的な機能を使って、各リリース前に [フィードバック](#providing-feedback-on-experimental-features) をテストして提供することができます。</span><span class="sxs-lookup"><span data-stu-id="edc38-105">You may use the experimental features that are still under development in the Microsoft Edge DevTools to test and [provide feedback](#providing-feedback-on-experimental-features) before each is released broadly.</span></span>  

<span data-ttu-id="edc38-106">Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。</span><span class="sxs-lookup"><span data-stu-id="edc38-106">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="edc38-107">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-107">Turn on experimental features</span></span>  

<span data-ttu-id="edc38-108">Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="edc38-108">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="edc38-109">[DevTools を開き][DevtoolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="edc38-109">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="edc38-110">[ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="edc38-110">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="edc38-111">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edc38-111">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="edc38-112">[ [設定][DevToolsCustomizeSettings] ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="edc38-112">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="edc38-113">を選択し `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="edc38-113">Select `Shift`+`?`.</span></span>  <span data-ttu-id="edc38-114">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edc38-114">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="edc38-115">[ **設定** ] ウィンドウの左側で、[ **実験** ] セクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="edc38-115">On the left side of the **Settings** pane, select the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.png":::
       <span data-ttu-id="edc38-117">DevTools の設定での実験の一覧</span><span class="sxs-lookup"><span data-stu-id="edc38-117">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="edc38-118">[ **実験** ] ページで、使用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="edc38-118">On the **Experiments** page, scroll through the list of all available experimental features and select the checkbox next to each features that you want to test.</span></span>  
1.  <span data-ttu-id="edc38-119">Microsoft Edge DevTools を閉じてからもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="edc38-119">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="edc38-120">実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="edc38-120">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="edc38-121">実験的な機能を無効にするには、[ **実験** ] ページを開き、無効にする実験的機能のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="edc38-121">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="edc38-122">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="edc38-122">Highlighted experimental features</span></span>  

<span data-ttu-id="edc38-123">以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="edc38-123">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="edc38-124">実験的機能</span><span class="sxs-lookup"><span data-stu-id="edc38-124">Experimental feature</span></span> | <span data-ttu-id="edc38-125">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="edc38-125">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="edc38-126">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-126">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="edc38-127">85以降</span><span class="sxs-lookup"><span data-stu-id="edc38-127">85 or later</span></span> |  
| [<span data-ttu-id="edc38-128">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-128">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="edc38-129">85以降</span><span class="sxs-lookup"><span data-stu-id="edc38-129">85 or later</span></span> |  
| [<span data-ttu-id="edc38-130">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-130">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="edc38-131">85以降</span><span class="sxs-lookup"><span data-stu-id="edc38-131">85 or later</span></span> |  
| [<span data-ttu-id="edc38-132">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-132">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="edc38-133">85以降</span><span class="sxs-lookup"><span data-stu-id="edc38-133">85 or later</span></span> |  
| [<span data-ttu-id="edc38-134">ソースオーダービューアーを有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-134">Enable Source Order Viewer</span></span>](#enable-source-order-viewer) | <span data-ttu-id="edc38-135">86以降</span><span class="sxs-lookup"><span data-stu-id="edc38-135">86 or later</span></span> |  

### <span data-ttu-id="edc38-136">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-136">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="edc38-137">CSS グリッドレイアウトを含む web サイトをデバッグするときに、ページの視覚エフェクトを向上させます。</span><span class="sxs-lookup"><span data-stu-id="edc38-137">Improves on-page visualizations when you debug websites that have CSS grid layouts.</span></span>  <span data-ttu-id="edc38-138">DevTools の設定では、オーバーレイをさらにカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="edc38-138">You may further customize the overlays in DevTools Settings.</span></span>  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.png":::
   <span data-ttu-id="edc38-140">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="edc38-140">CSS grid debugging feature</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="edc38-141">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-141">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="edc38-142">通常、 **要素** や **ネットワーク** などのツールは、devtools のメイン \ (トップ) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="edc38-142">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="edc38-143">同様に、 **3D ビュー** や **問題** などのツールは、devtools のドローワ \ (ボトム \) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="edc38-143">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="edc38-144">実験を選択した場合、タブ上でマウスポインターを移動し、コンテキストメニューを開き (\ 右クリック \)、[ **上へ移動** ] または [ **下へ移動**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="edc38-144">When you choose the experiment, you may move tools between the top and bottom panels by hovering on the tab, opening the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="edc38-145">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="edc38-145">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="edc38-146">下部パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。</span><span class="sxs-lookup"><span data-stu-id="edc38-146">To show or hide the bottom panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.png":::
   <span data-ttu-id="edc38-148">パネル間でタブを移動する</span><span class="sxs-lookup"><span data-stu-id="edc38-148">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="edc38-149">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-149">Enable webhint</span></span>  

<span data-ttu-id="edc38-150">[webhint][WebhintMain] は、アクセシビリティ、クロスブラウザーの互換性、セキュリティ、パフォーマンス、pwas、web サイトのその他の一般的な web 開発の問題に関するフィードバックをリアルタイムで提供するオープンソースツールです。</span><span class="sxs-lookup"><span data-stu-id="edc38-150">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="edc38-151">[Webhint][WebhintMain]の実験では、webhint のフィードバックが、[[問題][DevtoolsIssues]] パネルの devtools に取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="edc38-151">The [webhint][WebhintMain] experiment brings the webhint feedback into DevTools in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="edc38-152">この問題を選択すると、問題の解決方法と、web サイト上の影響を受けるリソースの一覧についてのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edc38-152">You may select the issue to see documentation on how to fix the issue and a list of the affected resources on your website.</span></span>  <span data-ttu-id="edc38-153">リソースリンクを選んで、DevTools で関連する **ネットワーク**、 **ソース**、または **要素** のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="edc38-153">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.png":::
   <span data-ttu-id="edc38-155">[ **問題** ] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="edc38-155">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="edc38-156">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-156">Enable Network Console</span></span>  

<span data-ttu-id="edc38-157">**ネットワーク本体** は、HTTP 経由で代理ネットワーク要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="edc38-157">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="edc38-158">**ネットワークコンソール**の実験を使用して、web API 要求を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="edc38-158">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="edc38-159">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="edc38-159">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="edc38-160">ネットワークコンソールを使用するには:</span><span class="sxs-lookup"><span data-stu-id="edc38-160">To use the Network Console:</span></span>  

1.  <span data-ttu-id="edc38-161">[ **ネットワーク** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="edc38-161">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="edc38-162">変更して再送信するネットワーク要求を見つけます。</span><span class="sxs-lookup"><span data-stu-id="edc38-162">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="edc38-163">コンテキストメニューを開き (\ 右クリック \)、[ **編集と再生**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="edc38-163">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="edc38-164">**ネットワークコンソール**が開いたら、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="edc38-164">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="edc38-165">[ **送信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="edc38-165">Select **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.png" alt-text="Console ドローワのネットワーク本体" lightbox="./media/network-network-console.png":::
   <span data-ttu-id="edc38-167">**Console**ドローワの**ネットワーク本体**</span><span class="sxs-lookup"><span data-stu-id="edc38-167">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  --> 

### <span data-ttu-id="edc38-168">ソースオーダービューアーを有効にする</span><span class="sxs-lookup"><span data-stu-id="edc38-168">Enable Source Order Viewer</span></span>  

<span data-ttu-id="edc38-169">**ソースオーダービューアー** は、実験の作業タイトルであり、ページソース内の要素の順序を表示します。</span><span class="sxs-lookup"><span data-stu-id="edc38-169">**Source Order Viewer** is the working title of an experiment to display the order of elements in the page source.</span></span>  <span data-ttu-id="edc38-170">**ソース注文ビューアー**を使って、ページ内のアクセシビリティの問題を見つけることができます。これは、画面の表示順序がソースの順序とは異なる場合があります。これは、混乱させるスクリーンリーダーのユーザーであるためです。</span><span class="sxs-lookup"><span data-stu-id="edc38-170">You may use the **Source Order Viewer** experiment to find accessibility issues in your pages since the display order on-screen may differ from the order of the source, which confuses screen reader users.</span></span>  

<span data-ttu-id="edc38-171">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="edc38-171">After enabling the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="edc38-172">ソースオーダービューアーを使用するには:</span><span class="sxs-lookup"><span data-stu-id="edc38-172">To use Source Order Viewer:</span></span>  

1.  <span data-ttu-id="edc38-173">[ **要素** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="edc38-173">Open the **Elements** pane.</span></span>  
1.  <span data-ttu-id="edc38-174">[引き出し] \ (下) パネルで [ **アクセシビリティ** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="edc38-174">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="edc38-175">[ **ソース注文のビューアー** ] セクションで、[ **ソースの順序を表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="edc38-175">Under the **Source Order Viewer** section, select the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="edc38-176">任意の HTML 要素を強調表示して、ページソースの順序でオーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="edc38-176">Highlight any HTML element to display an overlay that the order in the page source.</span></span>  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウのソースオーダービューアー" lightbox="./media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="edc38-178">[**アクセシビリティ**] ウィンドウの**ソースオーダービューアー**</span><span class="sxs-lookup"><span data-stu-id="edc38-178">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## <span data-ttu-id="edc38-179">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="edc38-179">Previous experimental features</span></span>  

*   <span data-ttu-id="edc38-180">Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="edc38-180">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="edc38-181">Microsoft Edge バージョン86以降では、[ショートカット][DevtoolsCustomKeyboardShortcuts]キーをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="edc38-181">[Customize Keyboard Shortcuts][DevtoolsCustomKeyboardShortcuts] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>
## <span data-ttu-id="edc38-182">実験的な機能についてフィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="edc38-182">Providing feedback on experimental features</span></span>  

<span data-ttu-id="edc38-183">Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="edc38-183">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="edc38-184">DevTools のフィードバックの **送信** アイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="edc38-184">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="edc38-185">[@EdgeDevTools][TwitterEdgedevtools]ツイート</span><span class="sxs-lookup"><span data-stu-id="edc38-185">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>   

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="edc38-187">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="edc38-187">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D ビュー |Microsoft ドキュメント"  
[DevtoolsIssues]: ./issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  
[DevtoolsOpen]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  
[DevtoolsCustomKeyboardShortcuts]: ./customize/shortcuts.md "Microsoft Edge DevTools でキーボードショートカットをカスタマイズする |Microsoft ドキュメント"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "web ヒント" 
