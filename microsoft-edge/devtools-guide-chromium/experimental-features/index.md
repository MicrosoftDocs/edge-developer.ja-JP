---
description: Microsoft Edge DevTools の最新の実験的機能
title: 試験的な機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/15/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 実験
no-loc:
- Enable webhint
- Enable Network Console
- Source Order Viewer
- Enable Composited Layers in 3D View
- Enable new Font Editor tool within the Styles pane
- Enable new CSS Flexbox debugging features
- Enable + button tab menus to open more tools
- Enable Welcome tab
- 3D View
- Turn on support to move tabs between panels
- Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code
- Edit keyboard shortcuts for any action in the DevTools
- Turn on new CSS grid debugging features
- 'Emulation: Support dual screen mode'
ms.openlocfilehash: c76830cb8bbcc597aa026f58e1926cd2f9bc2d62
ms.sourcegitcommit: 2ddfd98d1e871be9c61380a8ca57da398d38bd54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "11439585"
---
# <a name="experimental-features"></a><span data-ttu-id="19df6-104">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="19df6-104">Experimental features</span></span>  

<span data-ttu-id="19df6-105">Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="19df6-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="19df6-106">各機能がリリースされる [前に、テストして](#providing-feedback-on-experimental-features) フィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="19df6-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="19df6-107">実験機能は Microsoft Edge のすべてのチャネルで利用できます。Microsoft Edge Canary チャネルを使用すると、最新の実験機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="19df6-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="19df6-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="19df6-108">Turn on experimental features</span></span>  

<span data-ttu-id="19df6-109">Microsoft Edge で \(or off\) 実験機能を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19df6-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="19df6-110">[DevTools を開きます][DevtoolsOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="19df6-110">[Open DevTools][DevtoolsOpenIndex].</span></span>  
    *   <span data-ttu-id="19df6-111">`Control` + `Shift` + `I` \(Windows, Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="19df6-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="19df6-112">詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevtoolsShortcutsIndex]。</span><span class="sxs-lookup"><span data-stu-id="19df6-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevtoolsShortcutsIndex].</span></span>  
1.  <span data-ttu-id="19df6-113">[設定] [ウィンドウを開][DevToolsCustomizeIndexSettings] きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-113">Open the [Settings][DevToolsCustomizeIndexSettings] pane.</span></span>  
    *   <span data-ttu-id="19df6-114">を選択します `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="19df6-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="19df6-115">詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevtoolsShortcutsIndex]。</span><span class="sxs-lookup"><span data-stu-id="19df6-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevtoolsShortcutsIndex].</span></span>  
1.  <span data-ttu-id="19df6-116">[設定] ウィンドウの左側 **で** 、[実験] **セクションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="19df6-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="[設定] の [実験] ページ" lightbox="../media/experiments-devtools.msft.png":::
       <span data-ttu-id="19df6-118">[ **設定] の** [実験] **ページ**</span><span class="sxs-lookup"><span data-stu-id="19df6-118">The **Experiments** page in **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="19df6-119">[実験 **] ページで** 、利用可能なすべての実験機能の一覧をスクロールし、テストする各機能の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="19df6-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="19df6-120">Microsoft Edge DevTools を閉じて再度開きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-120">Close and reopen Microsoft Edge DevTools.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="19df6-121">実験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19df6-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="19df6-122">実験機能をオフにするには、[実験] ページ **を** 開き、無効にする実験機能のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="19df6-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <a name="highlighted-experimental-features"></a><span data-ttu-id="19df6-123">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="19df6-123">Highlighted experimental features</span></span>  

<span data-ttu-id="19df6-124">次のセクションでは、Microsoft Edge で使用できる新しい実験的機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="19df6-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="19df6-125">試験的機能</span><span class="sxs-lookup"><span data-stu-id="19df6-125">Experimental feature</span></span> | <span data-ttu-id="19df6-126">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="19df6-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [Enable webhint](#enable-webhint) | <span data-ttu-id="19df6-127">85 以降</span><span class="sxs-lookup"><span data-stu-id="19df6-127">85 or later</span></span> |  
| [Enable Network Console](#enable-network-console) | <span data-ttu-id="19df6-128">85 以降</span><span class="sxs-lookup"><span data-stu-id="19df6-128">85 or later</span></span> |  
| [Source Order Viewer](#source-order-viewer) | <span data-ttu-id="19df6-129">86 以降</span><span class="sxs-lookup"><span data-stu-id="19df6-129">86 or later</span></span> |  
| [Enable Composited Layers in 3D View](#enable-composited-layers-in-3d-view) | <span data-ttu-id="19df6-130">87 以降</span><span class="sxs-lookup"><span data-stu-id="19df6-130">87 or later</span></span> |  
| [Enable new Font Editor tool within the Styles pane](#enable-new-font-editor-tool-within-the-styles-pane) | <span data-ttu-id="19df6-131">89 以降</span><span class="sxs-lookup"><span data-stu-id="19df6-131">89 or later</span></span> |  
| [Enable new CSS Flexbox debugging features](#enable-new-css-flexbox-debugging-features) | <span data-ttu-id="19df6-132">89 以降</span><span class="sxs-lookup"><span data-stu-id="19df6-132">89 or later</span></span> |  
| [Enable + button tab menus to open more tools](#enable--button-tab-menus-to-open-more-tools) | <span data-ttu-id="19df6-133">89 以降</span><span class="sxs-lookup"><span data-stu-id="19df6-133">89 or later</span></span> |  
| [Enable Welcome tab](#enable-welcome-tab) | <span data-ttu-id="19df6-134">89 以降</span><span class="sxs-lookup"><span data-stu-id="19df6-134">89 or later</span></span> |  

### Enable webhint  

<span data-ttu-id="19df6-135">[webhint][WebhintMain] は、Web サイトとローカル Web ページにリアルタイムのフィードバックを提供するオープン ソース ツールです。</span><span class="sxs-lookup"><span data-stu-id="19df6-135">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="19df6-136">webhint によって提供される [フィードバックの種類][WebhintMain]。</span><span class="sxs-lookup"><span data-stu-id="19df6-136">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="19df6-137">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="19df6-137">accessibility</span></span>  
*   <span data-ttu-id="19df6-138">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="19df6-138">cross-browser compatibility</span></span>  
*   <span data-ttu-id="19df6-139">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="19df6-139">security</span></span>  
*   <span data-ttu-id="19df6-140">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="19df6-140">performance</span></span>  
*   <span data-ttu-id="19df6-141">プログレッシブ Web アプリ (PWA)</span><span class="sxs-lookup"><span data-stu-id="19df6-141">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="19df6-142">その他の一般的な Web 開発の問題</span><span class="sxs-lookup"><span data-stu-id="19df6-142">other common web development issues</span></span>  
    
<span data-ttu-id="19df6-143">[webhint 実験では][WebhintMain]、[問題] パネルに webhint フィードバック[が表示][DevtoolsIssuesIndex]されます。</span><span class="sxs-lookup"><span data-stu-id="19df6-143">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssuesIndex] panel.</span></span>  <span data-ttu-id="19df6-144">問題を選択して、ソリューションドキュメントと影響を受けるリソースの一覧を Web サイトに表示します。</span><span class="sxs-lookup"><span data-stu-id="19df6-144">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="19df6-145">リソース リンクを選択して、DevTools**で関連する** **[ネットワーク**] 、[ソース] 、または **[要素]** ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-145">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../media/experiments-webhint.msft.png":::
   <span data-ttu-id="19df6-147">[問題] パネルの**webhint フィードバック**</span><span class="sxs-lookup"><span data-stu-id="19df6-147">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Enable Network Console  

<span data-ttu-id="19df6-148">**ネットワーク コンソール** は、HTTP を使用してネットワークの代理要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="19df6-148">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="19df6-149">ネットワーク コンソールの実験 **を使用して** 、Web API 要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="19df6-149">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="19df6-150">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="19df6-150">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="19df6-151">ネットワーク コンソールを **使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19df6-151">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="19df6-152">[ネットワーク] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-152">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="19df6-153">変更するネットワーク要求を見つけて再送信します。</span><span class="sxs-lookup"><span data-stu-id="19df6-153">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="19df6-154">コンテキスト メニュー \(右クリック\) を開き、[編集] と [ **再生] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="19df6-154">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="19df6-155">ネットワーク コンソール **が開いたら** 、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="19df6-155">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="19df6-156">[送信 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="19df6-156">Choose **Send**.</span></span>  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="コンソール ドロワーのネットワーク コンソール" lightbox="../media/network-network-console.msft.png":::
   <span data-ttu-id="19df6-158">**コンソール ドロワー\*\*\*\*のネットワーク**コンソール</span><span class="sxs-lookup"><span data-stu-id="19df6-158">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Source Order Viewer  

<span data-ttu-id="19df6-159">**Source Order Viewer** は、Web ページ ソース内の要素の順序を表示する実験です。</span><span class="sxs-lookup"><span data-stu-id="19df6-159">**Source Order Viewer** is an experiment that displays the order of elements in the webpage source.</span></span>  <span data-ttu-id="19df6-160">画面の表示順序がソースの順序と異なる場合があります。これはスクリーン リーダーとキーボード のユーザーを混同します。</span><span class="sxs-lookup"><span data-stu-id="19df6-160">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="19df6-161">実験を使用して、画面の表示順序とソースの順序の違 **Source Order Viewer** いを見つける。</span><span class="sxs-lookup"><span data-stu-id="19df6-161">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="19df6-162">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="19df6-162">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="19df6-163">使用するには **Source Order Viewer** 、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19df6-163">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="19df6-164">[要素] **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-164">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="19df6-165">引き出し \(bottom\) パネルで [アクセシビリティ] ウィンドウを開きます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="19df6-165">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="19df6-166">セクションの **Source Order Viewer** 下で、[ソースの順序を **表示する] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="19df6-166">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="19df6-167">任意の HTML 要素を強調表示して、Web ページ ソース内の順序をオーバーレイで表示します。</span><span class="sxs-lookup"><span data-stu-id="19df6-167">Highlight any HTML element to display an overlay that the order in the webpage source.</span></span>  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text=":::<span data-ttu-id="19df6-168">no-loc(Source Order Viewer)::: in the アクセシビリティ ペイン" lightbox="../media/experiments-source-order-viewer.msft.png"::: **Source Order Viewer** [**アクセシビリティ] ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="19df6-168">no-loc(Source Order Viewer)::: in the Accessibility pane" lightbox="../media/experiments-source-order-viewer.msft.png"::: **Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### Enable Composited Layers in 3D View  

<span data-ttu-id="19df6-169">z-indexes と Document Object Model \(DOM\) と並んでレイヤーを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="19df6-169">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="19df6-170">この機能は、コンテキストを頻繁に切り替えることなくデバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="19df6-170">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="19df6-171">コンテキスト切り替えの削減が大きな問題だと特定しました。</span><span class="sxs-lookup"><span data-stu-id="19df6-171">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="19df6-172">作成するコードが Web アプリに与える影響は必ずしも明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="19df6-172">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="19df6-173">包括的な視覚的なデバッグ エクスペリエンスのために、複合 3D View レイヤーと複合レイヤーが組み合わされました。</span><span class="sxs-lookup"><span data-stu-id="19df6-173">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  

<span data-ttu-id="19df6-174">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="19df6-174">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="19df6-175">コンポジット レイヤー **を使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19df6-175">To use **Composited Layers**, complete the following steps.</span></span>  

1.  <span data-ttu-id="19df6-176">ドロワーで、ツールを選択 **3D View** します。</span><span class="sxs-lookup"><span data-stu-id="19df6-176">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="19df6-177">[複合 **レイヤー] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-177">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="19df6-178">アプリのすべてのペイントされたレイヤーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19df6-178">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="19df6-179">独自の Web アプリでこの機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="19df6-179">Try this feature with your own web apps.</span></span>  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="19df6-181">**[コンポジット レイヤー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="19df6-181">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### Enable new Font Editor tool within the Styles pane  

<span data-ttu-id="19df6-182">これで、新しいビジュアル フォント エディターを [使用してフォント][DevtoolsInspectStylesEditFonts] を編集できます。</span><span class="sxs-lookup"><span data-stu-id="19df6-182">You may now use the new visual [Font Editor][DevtoolsInspectStylesEditFonts] to edit fonts.</span></span>  <span data-ttu-id="19df6-183">フォントとフォントの特性を定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="19df6-183">Use it define fonts and font characteristics.</span></span>  <span data-ttu-id="19df6-184">ビジュアル フォント エディター **を使用すると** 、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="19df6-184">The visual **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="19df6-185">異なるフォント プロパティの単位を切り替える</span><span class="sxs-lookup"><span data-stu-id="19df6-185">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="19df6-186">異なるフォント プロパティのキーワードを切り替える</span><span class="sxs-lookup"><span data-stu-id="19df6-186">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="19df6-187">単位を変換</span><span class="sxs-lookup"><span data-stu-id="19df6-187">Convert units</span></span>  
*   <span data-ttu-id="19df6-188">正確な CSS コードを生成</span><span class="sxs-lookup"><span data-stu-id="19df6-188">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="19df6-189">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="19df6-189">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="19df6-190">新しいビジュアル フォント エディターを **使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19df6-190">To use the new visual **Font Editor**, complete the following steps.</span></span>  

1.  <span data-ttu-id="19df6-191">[要素] **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-191">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="19df6-192">[スタイル] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-192">Open the **Styles** pane.</span></span>  
1.  <span data-ttu-id="19df6-193">[フォント エディター **] アイコンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="19df6-193">Choose the **Font Editor** icon.</span></span>  
    
<span data-ttu-id="19df6-194">新しいビジュアル フォント エディターの詳細については[、DevTools][DevtoolsInspectStylesEditFonts]の [スタイル] ウィンドウの [CSS フォントスタイルと設定の編集] に移動します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="19df6-194">For more information about the new visual **Font Editor**, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="ビジュアル の [フォント エディター] ウィンドウが強調表示されます" lightbox="../media/font-editor-open.msft.png":::
   <span data-ttu-id="19df6-196">ビジュアル の [ **フォント エディター]** ウィンドウが強調表示されます</span><span class="sxs-lookup"><span data-stu-id="19df6-196">The visual **Font Editor** pane is highlighted</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable new CSS Flexbox debugging features  

<span data-ttu-id="19df6-197">この実験的な機能は、CSS Flexbox レイアウトのデバッグに役立つ多くの新しい視覚化を提供します。</span><span class="sxs-lookup"><span data-stu-id="19df6-197">This experimental feature provides many new visualizations to help you debug CSS Flexbox layouts.</span></span>  <span data-ttu-id="19df6-198">最新の実験機能をプレビューするには、 [この実験を有効にし](#turn-on-experimental-features) 、DevTools を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="19df6-198">To preview the latest experimental features, [turn on this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a><span data-ttu-id="19df6-199">[検査] ツールを使用して Flexbox レイアウトに永続的なオーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="19df6-199">Display persistent overlays on Flexbox layouts with the Inspect tool</span></span>  

<span data-ttu-id="19df6-200">[ **検査** ] ツールを使用すると、Web サイト内の CSS Flexbox レイアウトをマウスでホバーして識別し、視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="19df6-200">The **Inspect** tool provides a quick way to identify and visualize CSS Flexbox layouts in a website by hovering on them with the mouse.</span></span>  <span data-ttu-id="19df6-201">DevTools **の** 左上隅にある ![ [検査 ](../media/inspect-icon.msft.png) \( Inspect \) ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="19df6-201">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="19df6-202">次に、Web サイトのデバッグ中に、flex コンテナーにカーソルを合わせると、flex コンテナーの周囲にアウトラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19df6-202">Then, while debugging the website, hover on a flex container to display outlines around the flex container.</span></span>  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="検査ツールを使用して Flexbox コンテナーを表示する" lightbox="../media/flexbox-hover.msft.png":::
   <span data-ttu-id="19df6-204">検査ツールを使用して Flexbox コンテナー **を表示** する</span><span class="sxs-lookup"><span data-stu-id="19df6-204">Display Flexbox containers with the **Inspect** tool</span></span>  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a><span data-ttu-id="19df6-205">Flexbox レイアウトに永続的なオーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="19df6-205">Display persistent overlays on Flexbox layouts</span></span>  

<span data-ttu-id="19df6-206">Microsoft Edge バージョン 89 以降では、実験的な CSS Flexbox 機能では、Flexbox レイアウトで永続的なオーバーレイを有効にするオプションも提供しています。</span><span class="sxs-lookup"><span data-stu-id="19df6-206">In Microsoft Edge version 89 or later, the experimental CSS Flexbox feature also offers the option to turn on persistent overlays on Flexbox layouts.</span></span>  <span data-ttu-id="19df6-207">永続的なオーバーレイには、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="19df6-207">Persistent overlays provide the following benefits.</span></span>  

*   <span data-ttu-id="19df6-208">永続的なオーバーレイは、スクロール、マウスの移動、DevTools の他の機能の使用時に Web ページに表示されたままです。</span><span class="sxs-lookup"><span data-stu-id="19df6-208">Persistent overlays remain visible on the webpage as you scroll, move your mouse, and use other features of the DevTools.</span></span>
*   <span data-ttu-id="19df6-209">複数の永続的なオーバーレイを同時に使用して、複数の Flexbox レイアウトを一度に確認できます。</span><span class="sxs-lookup"><span data-stu-id="19df6-209">Multiple persistent overlays may be used at the same time, to allow you to review several Flexbox layouts at once.</span></span>  
*   <span data-ttu-id="19df6-210">永続的なオーバーレイは、色構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="19df6-210">Persistent overlays offer color configuration options.</span></span>  
    
<span data-ttu-id="19df6-211">Flexbox レイアウトの永続的なオーバーレイを切り替えるには、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="19df6-211">To toggle persistent overlays on Flexbox layout, use one of following actions.</span></span>  

*   <span data-ttu-id="19df6-212">要素ツール **の DOM ツリー** に表示される Flexbox コンテナーの横にある [Flexbox 楕円] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="19df6-212">Choose the **Flexbox** oval icon next to any Flexbox container displayed in the DOM tree of the **Elements** tool.</span></span>  
*   <span data-ttu-id="19df6-213">[要素] **ツールにある** 新しい [レイアウト] パネルを **開** き、強調表示する各 Flexbox コンテナーの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="19df6-213">Open the new **Layout** panel located in the **Elements** tool, and choose the checkbox next to each Flexbox container you want to highlight.</span></span>  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools の Flex アイコンとレイアウト パネル" lightbox="../media/flexbox-overlay.msft.png":::
   <span data-ttu-id="19df6-215">DevTools **の** Flex アイコンとレイアウト パネル</span><span class="sxs-lookup"><span data-stu-id="19df6-215">Flex icons and **Layout** panel in DevTools</span></span>  
:::image-end:::  

#### <a name="configure-persistent-overlays"></a><span data-ttu-id="19df6-216">永続的なオーバーレイを構成する</span><span class="sxs-lookup"><span data-stu-id="19df6-216">Configure persistent overlays</span></span>  

<span data-ttu-id="19df6-217">CSS グリッドまたは Flexbox レイアウトの永続的オーバーレイのオプションを構成するには、[レイアウト] ウィンドウ **を使用** します。</span><span class="sxs-lookup"><span data-stu-id="19df6-217">To configure options for persistent overlays for CSS grids or Flexbox layouts, use the **Layout** pane.</span></span>  <span data-ttu-id="19df6-218">[ **レイアウト** ] ウィンドウは、[スタイル] ウィンドウと **[** 計算] ウィンドウの横にある **[** 要素] **ツールに** 配置されます。</span><span class="sxs-lookup"><span data-stu-id="19df6-218">The **Layout** pane is located in the **Elements** tool next to the **Styles** and **Computed** panes.</span></span>  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="レイアウト パネル" lightbox="../media/flexbox-layout.msft.png":::
   <span data-ttu-id="19df6-220">レイアウト パネル</span><span class="sxs-lookup"><span data-stu-id="19df6-220">Layout panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable + button tab menus to open more tools  

<span data-ttu-id="19df6-221">新しい [その他のツール] **\(** \) アイコンを使用して、その他のツール `+` を開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="19df6-221">You may now open more tools using the new **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="19df6-222">実験を有効にし、DevTools を再読み込みすると、DevTools の上部にあるタブ グループの右側にプラス記号 **Enable + button tab menus to open more tools** `+` \( \) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19df6-222">After you turn on the **Enable + button tab menus to open more tools** experiment and reload DevTools, a plus sign \(`+`\) displays to the right of the tab group at the top of the DevTools.</span></span>  <span data-ttu-id="19df6-223">タブ バーに追加できるその他のツールの一覧を表示するには、新しい **[** その他のツール] \( `+` \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="19df6-223">To display a list of other tools that you may add to the tab bar, choose the new **More Tools** \(`+`\) icon.</span></span>  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="上部ウィンドウの [その他のツール]" lightbox="../media/experiments-more-tools-button.msft.png":::
   <span data-ttu-id="19df6-225">**上部ウィンドウの** [その他のツール]</span><span class="sxs-lookup"><span data-stu-id="19df6-225">**More Tools** in the top pane</span></span>
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable Welcome tab

<span data-ttu-id="19df6-226">この実験では **、What's New ツールを新** しいウェルカム ツール **に置き換** える。</span><span class="sxs-lookup"><span data-stu-id="19df6-226">This experiment replaces the **What's New** tool with the new **Welcome** tool.</span></span>  <span data-ttu-id="19df6-227">次のコンテンツの更新されたデザインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19df6-227">It displays a refreshed design for the following content.</span></span>  

*   <span data-ttu-id="19df6-228">開発者向けドキュメントへのリンク</span><span class="sxs-lookup"><span data-stu-id="19df6-228">Links to developer docs</span></span>  
*   <span data-ttu-id="19df6-229">最新の機能</span><span class="sxs-lookup"><span data-stu-id="19df6-229">the latest features</span></span>  
*   <span data-ttu-id="19df6-230">リリース ノート</span><span class="sxs-lookup"><span data-stu-id="19df6-230">release notes</span></span>  
*   <span data-ttu-id="19df6-231">Microsoft Edge DevTools チームに連絡するオプション</span><span class="sxs-lookup"><span data-stu-id="19df6-231">Option to contact the Microsoft Edge DevTools team</span></span>  
    
<span data-ttu-id="19df6-232">ウェルカム **ツールは** 、Microsoft Edge への更新の後に自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="19df6-232">The **Welcome** tool opens automatically after each update to Microsoft Edge.</span></span>  <span data-ttu-id="19df6-233">更新後にウェルカム ツール\*\*\*\* が表示されるのを防ぐには、[ようこそ]\*\*\*\* ツールのタイトルの下にある更新の後、[開く] タブの横にあるチェック ボックス**を**オフにします。</span><span class="sxs-lookup"><span data-stu-id="19df6-233">To prevent the display of the **Welcome** tool after each update, clear the checkbox next to **Open tab after each update** under the **Welcome** tool title.</span></span>  

<span data-ttu-id="19df6-234">元の [What's **New]** ツールを[][DevtoolsCustomizeIndexSettings]使用する場合は、[設定の実験] に移動し、の横にある  >  \*\*\*\* チェック ボックスをオフにします **Enable Welcome tab** 。</span><span class="sxs-lookup"><span data-stu-id="19df6-234">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="ウェルカム ツール" lightbox="../media/experiments-welcome.msft.png":::
   <span data-ttu-id="19df6-236">**ウェルカム** ツール</span><span class="sxs-lookup"><span data-stu-id="19df6-236">**Welcome** tool</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a><span data-ttu-id="19df6-237">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="19df6-237">Previous experimental features</span></span>  

*   <span data-ttu-id="19df6-238">[3D View][Devtools3dViewIndex] が使用可能になっていて、Microsoft Edge バージョン 83 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="19df6-238">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="19df6-239">[Turn on support to move tabs between panels][DevtoolsCustomizeIndex] が使用可能になっていて、Microsoft Edge バージョン 85 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="19df6-239">[Turn on support to move tabs between panels][DevtoolsCustomizeIndex] is now available and turned on by default in Microsoft Edge version 85 or later.</span></span>  
*   <span data-ttu-id="19df6-240">[Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode] が利用可能で、Microsoft Edge バージョン 86 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="19df6-240">[Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  
*   <span data-ttu-id="19df6-241">[Edit keyboard shortcuts for any action in the DevTools][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools] が使用可能になっていて、Microsoft Edge バージョン 89 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="19df6-241">[Edit keyboard shortcuts for any action in the DevTools][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
*   <span data-ttu-id="19df6-242">[Turn on new CSS grid debugging features][DevtoolsCssGrid] が使用可能になっていて、Microsoft Edge バージョン 89 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="19df6-242">[Turn on new CSS grid debugging features][DevtoolsCssGrid] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
*   <span data-ttu-id="19df6-243">[Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables] が使用可能になっていて、Microsoft Edge バージョン 90 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="19df6-243">[Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables] is now available and turned on by default in Microsoft Edge version 90 or later.</span></span>  

## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="19df6-244">実験的な機能に関するフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="19df6-244">Providing feedback on experimental features</span></span>  

<span data-ttu-id="19df6-245">Microsoft Edge DevTools 実験、または DevTools に関連するその他のフィードバックを提供する。</span><span class="sxs-lookup"><span data-stu-id="19df6-245">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="19df6-246">DevTools の [フィードバック **の送信** ] アイコンを使用してフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="19df6-246">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="19df6-247">ツイートの [@EdgeDevTools][TwitterEdgedevtools]</span><span class="sxs-lookup"><span data-stu-id="19df6-247">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  
    
:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="19df6-249">Microsoft Edge DevTools の **[フィードバックの送信]** アイコン</span><span class="sxs-lookup"><span data-stu-id="19df6-249">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D View |Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "Microsoft Edge DevTools サーバーで CSS グリッドを検査|Microsoft Docs"  
[DevtoolsCustomizeIndex]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ |Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools]: ../customize/shortcuts.md#edit-keyboard-shortcuts-for-any-action-in-the-devtools "DevTools 内の任意のアクションのキーボード ショートカットを編集する |Microsoft Docs"  
[DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode]: ../customize/shortcuts.md#match-keyboard-shortcuts-in-the-devtools-to-microsoft-visual-studio-code "DevTools のキーボード ショートカットを Microsoft コードに一致Visual Studio |Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools アプリケーションでデバイス モードでモバイル デバイスをシミュレート|Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集 | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevtoolsOpenIndex]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "Microsoft Edge DevTools アプリケーションでデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレート|Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
