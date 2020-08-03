---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/21/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: 6b3e1c06d6b8ed79054c28df483fcca93e5751d6
ms.sourcegitcommit: 19ef1422733ef1fd051d2b4f0263ce191e8d67bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902859"
---
# <span data-ttu-id="66a41-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="66a41-104">Experimental features</span></span>  

<span data-ttu-id="66a41-105">Microsoft Edge DevTools でまだ開発中の実験的な機能を使って、各リリース前に[フィードバック](#providing-feedback-on-experimental-features)をテストして提供することができます。</span><span class="sxs-lookup"><span data-stu-id="66a41-105">You may use the experimental features that are still under development in the Microsoft Edge DevTools to test and [provide feedback](#providing-feedback-on-experimental-features) before each is released broadly.</span></span>  

<span data-ttu-id="66a41-106">Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。</span><span class="sxs-lookup"><span data-stu-id="66a41-106">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <span data-ttu-id="66a41-107">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-107">Turn on experimental features</span></span>  

<span data-ttu-id="66a41-108">Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="66a41-108">Use the following steps to turn on \(or off\) experimental features in Microsoft Edge.</span></span>  

1.  <span data-ttu-id="66a41-109">[DevTools を開き][DevtoolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="66a41-109">[Open DevTools][DevtoolsOpen].</span></span>  
     *   <span data-ttu-id="66a41-110">[ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="66a41-110">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="66a41-111">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66a41-111">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="66a41-112">[[設定][DevToolsCustomizeSettings]] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="66a41-112">Open the [Settings][DevToolsCustomizeSettings] pane.</span></span>  
    *   <span data-ttu-id="66a41-113">を選択し `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="66a41-113">Select `Shift`+`?`.</span></span>  <span data-ttu-id="66a41-114">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66a41-114">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  
1.  <span data-ttu-id="66a41-115">[**設定**] ウィンドウの左側で、[**実験**] セクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="66a41-115">On the left side of the **Settings** pane, select the **Experiments** section.</span></span>  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.png":::
       <span data-ttu-id="66a41-117">DevTools の設定での実験の一覧</span><span class="sxs-lookup"><span data-stu-id="66a41-117">List of experiments in DevTools Settings</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="66a41-118">[**実験**] ページで、使用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="66a41-118">On the **Experiments** page, scroll through the list of all available experimental features and select the checkbox next to each features that you want to test.</span></span>  
1.  <span data-ttu-id="66a41-119">Microsoft Edge DevTools を閉じてからもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="66a41-119">Close and reopen Microsoft Edge DevTools.</span></span>  

> [!NOTE]
> <span data-ttu-id="66a41-120">実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66a41-120">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="66a41-121">実験的な機能を無効にするには、[**実験**] ページを開き、無効にする実験的機能のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="66a41-121">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <span data-ttu-id="66a41-122">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="66a41-122">Highlighted experimental features</span></span>  

<span data-ttu-id="66a41-123">以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="66a41-123">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="66a41-124">実験的機能</span><span class="sxs-lookup"><span data-stu-id="66a41-124">Experimental feature</span></span> | <span data-ttu-id="66a41-125">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="66a41-125">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="66a41-126">カスタムキーボードショートカットの [設定] タブを有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-126">Enable custom keyboard shortcuts settings tab</span></span>](#enable-custom-keyboard-shortcuts-settings-tab) | <span data-ttu-id="66a41-127">84以降</span><span class="sxs-lookup"><span data-stu-id="66a41-127">84 or later</span></span> |
| [<span data-ttu-id="66a41-128">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-128">Enable new CSS grid debugging features</span></span>](#enable-new-css-grid-debugging-features) | <span data-ttu-id="66a41-129">85以降</span><span class="sxs-lookup"><span data-stu-id="66a41-129">85 or later</span></span> |  
| [<span data-ttu-id="66a41-130">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-130">Enable support to move tabs between panels</span></span>](#enable-support-to-move-tabs-between-panels) | <span data-ttu-id="66a41-131">85以降</span><span class="sxs-lookup"><span data-stu-id="66a41-131">85 or later</span></span> |  
| [<span data-ttu-id="66a41-132">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-132">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="66a41-133">85以降</span><span class="sxs-lookup"><span data-stu-id="66a41-133">85 or later</span></span> | 
| [<span data-ttu-id="66a41-134">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-134">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="66a41-135">85以降</span><span class="sxs-lookup"><span data-stu-id="66a41-135">85 or later</span></span> |

### <span data-ttu-id="66a41-136">カスタムキーボードショートカットの [設定] タブを有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-136">Enable custom keyboard shortcuts settings tab</span></span>

<span data-ttu-id="66a41-137">Devtools での開発ツールでの[キーボードショートカット][DevToolsShortcuts]の[一致を有効][VisualstudioCode]にするための新しい**ショートカット**ページが用意さ[れてい][DevToolsCustomizeSettings]ます。</span><span class="sxs-lookup"><span data-stu-id="66a41-137">Provides a new **Shortcuts** page in [DevTools Settings][DevToolsCustomizeSettings] that enables matching [keyboard shortcuts][DevToolsShortcuts] in the DevTools to [VS Code][VisualstudioCode].</span></span>  

<span data-ttu-id="66a41-138">実験を有効にしたら、[選択] を使用して[Devtools の設定][DevToolsCustomizeSettings]をもう一度開き `Shift` + `?` ます。</span><span class="sxs-lookup"><span data-stu-id="66a41-138">Once you have enabled the experiment, open [DevTools Settings][DevToolsCustomizeSettings] again using select `Shift`+`?`.</span></span>  <span data-ttu-id="66a41-139">[新しい**ショートカット**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="66a41-139">Navigate to the new **Shortcuts** page.</span></span>  <span data-ttu-id="66a41-140">[**標準のショートカットキー**の選択] ドロップダウンで [ **Devtools (既定値)** ] を選び、[ **Visual Studio コード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="66a41-140">Select **DevTools (Default)** in the **Match shortcuts from preset** dropdown and select **Visual Studio Code**.</span></span>  <span data-ttu-id="66a41-141">DevTools のキーボードショートカットは、VS コードで同等のアクションのショートカットと一致するようになりました。</span><span class="sxs-lookup"><span data-stu-id="66a41-141">The keyboard shortcuts in the DevTools now match the shortcuts for equivalent actions in VS Code.</span></span>  

:::image type="complex" source="./media/experiments-keyboard-shortcut.png" alt-text="開発ツールのキーボードショートカットを VS コードに一致させる" lightbox="./media/experiments-keyboard-shortcut.png":::
   <span data-ttu-id="66a41-143">開発ツールのキーボードショートカットを VS コードに一致させる</span><span class="sxs-lookup"><span data-stu-id="66a41-143">Match keyboard shortcuts in the DevTools to VS Code</span></span>
:::image-end:::  

<span data-ttu-id="66a41-144">たとえば、Windows では、 [VS コード][VisualstudioCodeShortcutsKeyboardWindows]でスクリプトを一時停止または実行し続けるためのキーボードショートカットが `F5` あります。</span><span class="sxs-lookup"><span data-stu-id="66a41-144">For example, on Windows the keyboard shortcut for pausing or continuing running a script in [VS Code][VisualstudioCodeShortcutsKeyboardWindows] is `F5`.</span></span>  <span data-ttu-id="66a41-145">**Devtools (既定)** の事前設定を使用すると、devtools の同じショートカットを使うことが `F8` できます。</span><span class="sxs-lookup"><span data-stu-id="66a41-145">With the **DevTools (Default)** preset, the same shortcut in the DevTools is `F8`.</span></span>  <span data-ttu-id="66a41-146">**Visual Studio コード**の事前設定を使用すると、ショートカットも表示され `F5` ます。</span><span class="sxs-lookup"><span data-stu-id="66a41-146">With the **Visual Studio Code** preset, the shortcut is also `F5`.</span></span>  

### <span data-ttu-id="66a41-147">新しい CSS グリッドのデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-147">Enable new CSS grid debugging features</span></span>  

<span data-ttu-id="66a41-148">CSS グリッドレイアウトを含む web サイトをデバッグするときに、ページの視覚エフェクトを向上させます。</span><span class="sxs-lookup"><span data-stu-id="66a41-148">Improves on-page visualizations when you debug websites that have CSS grid layouts.</span></span>  <span data-ttu-id="66a41-149">DevTools の設定では、オーバーレイをさらにカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="66a41-149">You may further customize the overlays in DevTools Settings.</span></span>  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.png":::
   <span data-ttu-id="66a41-151">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="66a41-151">CSS grid debugging feature</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="66a41-152">パネル間でタブを移動できるようにサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-152">Enable support to move tabs between panels</span></span>  

<span data-ttu-id="66a41-153">通常、**要素**や**ネットワーク**などのツールは、devtools のメイン \ (トップ) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="66a41-153">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="66a41-154">同様に、 **3D ビュー**や**問題**などのツールは、devtools のドローワ \ (ボトム \) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="66a41-154">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="66a41-155">実験を選択した場合、タブ上でマウスポインターを移動し、コンテキストメニューを開き (\ 右クリック \)、[**上へ移動**] または [**下へ移動**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="66a41-155">When you choose the experiment, you may move tools between the top and bottom panels by hovering on the tab, opening the contextual menu \(right-click\), and choose **Move to top** or **Move to bottom**.</span></span>   <span data-ttu-id="66a41-156">この実験では、DevTools レイアウトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="66a41-156">This experiment allows you to customize your DevTools layout.</span></span>  <span data-ttu-id="66a41-157">下部パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。</span><span class="sxs-lookup"><span data-stu-id="66a41-157">To show or hide the bottom panel, select `Escape`.</span></span>  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.png":::
   <span data-ttu-id="66a41-159">パネル間でタブを移動する</span><span class="sxs-lookup"><span data-stu-id="66a41-159">Moving tabs between panels</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="66a41-160">Web ヒントを有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-160">Enable webhint</span></span>  

<span data-ttu-id="66a41-161">[webhint][WebhintMain]は、アクセシビリティ、クロスブラウザーの互換性、セキュリティ、パフォーマンス、pwas、web サイトのその他の一般的な web 開発の問題に関するフィードバックをリアルタイムで提供するオープンソースツールです。</span><span class="sxs-lookup"><span data-stu-id="66a41-161">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="66a41-162">[Webhint][WebhintMain]の実験では、webhint のフィードバックが、[[問題][DevtoolsIssues]] パネルの devtools に取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="66a41-162">The [webhint][WebhintMain] experiment brings the webhint feedback into DevTools in the [Issues][DevtoolsIssues] panel.</span></span>  <span data-ttu-id="66a41-163">この問題を選択すると、問題の解決方法と、web サイト上の影響を受けるリソースの一覧についてのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66a41-163">You may select the issue to see documentation on how to fix the issue and a list of the affected resources on your website.</span></span>  <span data-ttu-id="66a41-164">リソースリンクを選んで、DevTools で関連する**ネットワーク**、**ソース**、または**要素**のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="66a41-164">Select a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="./media/experiments-webhint.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.png":::
   <span data-ttu-id="66a41-166">[問題] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="66a41-166">webhint feedback in the Issues panel</span></span>  
:::image-end:::      

<!--Available in Microsoft Edge version 85 and later.  -->  

### <span data-ttu-id="66a41-167">ネットワーク本体を有効にする</span><span class="sxs-lookup"><span data-stu-id="66a41-167">Enable Network Console</span></span>

<span data-ttu-id="66a41-168">**ネットワーク本体**は、HTTP 経由で代理ネットワーク要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="66a41-168">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="66a41-169">**ネットワークコンソール**の実験を使用して、web API 要求を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="66a41-169">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="66a41-170">実験を有効にした後、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="66a41-170">After enabling the experiment, ensure you restart the DevTools.</span></span> <span data-ttu-id="66a41-171">ネットワークコンソールを使用するには:</span><span class="sxs-lookup"><span data-stu-id="66a41-171">To use the Network Console:</span></span>
1.  <span data-ttu-id="66a41-172">[**ネットワーク**] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="66a41-172">Open the **Network** pane.</span></span>
1.  <span data-ttu-id="66a41-173">変更して再送信するネットワーク要求を見つけます。</span><span class="sxs-lookup"><span data-stu-id="66a41-173">Find the network request that you want to change and resend.</span></span>
1.  <span data-ttu-id="66a41-174">コンテキストメニューを開き (\ 右クリック \)、[**編集と再生**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="66a41-174">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span> 
1.  <span data-ttu-id="66a41-175">**ネットワークコンソール**が開いたら、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="66a41-175">When the **Network Console** opens, edit the network request information.</span></span>
1.  <span data-ttu-id="66a41-176">[**送信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="66a41-176">Select **Send**.</span></span>  

:::image type="complex" source="./media/network-network-console.png" alt-text="Console ドローワのネットワーク本体" lightbox="./media/network-network-console.png":::
<span data-ttu-id="66a41-178">Console ドローワのネットワーク本体</span><span class="sxs-lookup"><span data-stu-id="66a41-178">Network Console in the Console drawer</span></span>
:::image-end::: 

<!--Available in Microsoft Edge version 85 and later.  --> 

## <span data-ttu-id="66a41-179">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="66a41-179">Previous experimental features</span></span>  

*   <span data-ttu-id="66a41-180">Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="66a41-180">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  

## <span data-ttu-id="66a41-181">実験的な機能についてフィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="66a41-181">Providing feedback on experimental features</span></span>  

<span data-ttu-id="66a41-182">Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="66a41-182">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="66a41-183">DevTools のフィードバックアイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="66a41-183">Send your feedback using the Feedback icon in the DevTools</span></span>  
*   <span data-ttu-id="66a41-184">[@EdgeDevTools][TwitterEdgedevtools]ツイート</span><span class="sxs-lookup"><span data-stu-id="66a41-184">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  

:::image type="complex" source="./media/devtools-feedback.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン" lightbox="./media/devtools-feedback.png":::
   <span data-ttu-id="66a41-186">Microsoft Edge DevTools のフィードバックアイコン</span><span class="sxs-lookup"><span data-stu-id="66a41-186">Feedback icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D ビュー |Microsoft ドキュメント"  
[DevtoolsIssues]: ./issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  
[DevtoolsOpen]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualstudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio のコードのキーボードショートカット (Windows |) |Visual Studio コード"  

[WebhintMain]: https://webhint.io "web ヒント" 
