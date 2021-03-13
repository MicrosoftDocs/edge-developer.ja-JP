---
description: Microsoft Edge DevTools の最新の実験的機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 実験
ms.openlocfilehash: 612b3b83aee1ee9035982e58e008395ec3645b2b
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408305"
---
# <a name="experimental-features"></a><span data-ttu-id="740d9-104">試験的機能</span><span class="sxs-lookup"><span data-stu-id="740d9-104">Experimental features</span></span>  

<span data-ttu-id="740d9-105">Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="740d9-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="740d9-106">各機能がリリースされる [前に、テストして](#providing-feedback-on-experimental-features) フィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="740d9-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="740d9-107">実験機能は Microsoft Edge のすべてのチャネルで利用できます。Microsoft Edge Canary チャネルを使用すると、最新の実験機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="740d9-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="740d9-108">実験的な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-108">Turn on experimental features</span></span>  

<span data-ttu-id="740d9-109">Microsoft Edge で \(or off\) 実験機能を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="740d9-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="740d9-110">[DevTools を開きます][DevtoolsOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="740d9-110">[Open DevTools][DevtoolsOpenIndex].</span></span>  
    *   <span data-ttu-id="740d9-111">`Control` + `Shift` + `I` \(Windows, Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="740d9-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="740d9-112">詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevtoolsShortcutsIndex]。</span><span class="sxs-lookup"><span data-stu-id="740d9-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevtoolsShortcutsIndex].</span></span>  
1.  <span data-ttu-id="740d9-113">[設定] [ウィンドウを開][DevToolsCustomizeIndexSettings] きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-113">Open the [Settings][DevToolsCustomizeIndexSettings] pane.</span></span>  
    *   <span data-ttu-id="740d9-114">を選択します `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="740d9-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="740d9-115">詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevtoolsShortcutsIndex]。</span><span class="sxs-lookup"><span data-stu-id="740d9-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevtoolsShortcutsIndex].</span></span>  
1.  <span data-ttu-id="740d9-116">[設定] ウィンドウの左側 **で** 、[実験] **セクションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="740d9-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="[設定] の [実験] ページ" lightbox="../media/experiments-devtools.msft.png":::
       <span data-ttu-id="740d9-118">[ **設定] の** [実験] **ページ**</span><span class="sxs-lookup"><span data-stu-id="740d9-118">The **Experiments** page in **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="740d9-119">[実験 **] ページで** 、利用可能なすべての実験機能の一覧をスクロールし、テストする各機能の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="740d9-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="740d9-120">Microsoft Edge DevTools を閉じて再度開きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-120">Close and reopen Microsoft Edge DevTools.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="740d9-121">実験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="740d9-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="740d9-122">実験機能をオフにするには、[実験] ページ **を** 開き、無効にする実験機能のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="740d9-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <a name="highlighted-experimental-features"></a><span data-ttu-id="740d9-123">強調表示された実験的な機能</span><span class="sxs-lookup"><span data-stu-id="740d9-123">Highlighted experimental features</span></span>  

<span data-ttu-id="740d9-124">次のセクションでは、Microsoft Edge で使用できる新しい実験的機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="740d9-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="740d9-125">試験的機能</span><span class="sxs-lookup"><span data-stu-id="740d9-125">Experimental feature</span></span> | <span data-ttu-id="740d9-126">Microsoft Edge バージョン</span><span class="sxs-lookup"><span data-stu-id="740d9-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="740d9-127">Webhint を有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-127">Enable webhint</span></span>](#enable-webhint) | <span data-ttu-id="740d9-128">85 以降</span><span class="sxs-lookup"><span data-stu-id="740d9-128">85 or later</span></span> |  
| [<span data-ttu-id="740d9-129">ネットワーク コンソールの有効化</span><span class="sxs-lookup"><span data-stu-id="740d9-129">Enable Network Console</span></span>](#enable-network-console) | <span data-ttu-id="740d9-130">85 以降</span><span class="sxs-lookup"><span data-stu-id="740d9-130">85 or later</span></span> |  
| [<span data-ttu-id="740d9-131">ソース オーダー ビューアー</span><span class="sxs-lookup"><span data-stu-id="740d9-131">Source Order Viewer</span></span>](#source-order-viewer) | <span data-ttu-id="740d9-132">86 以降</span><span class="sxs-lookup"><span data-stu-id="740d9-132">86 or later</span></span> |  
| [<span data-ttu-id="740d9-133">3D ビューで複合レイヤーを有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-133">Enable Composited Layers in 3D View</span></span>](#enable-composited-layers-in-3d-view) | <span data-ttu-id="740d9-134">87 以降</span><span class="sxs-lookup"><span data-stu-id="740d9-134">87 or later</span></span> |  
| [<span data-ttu-id="740d9-135">[スタイル] ウィンドウ内で新しいフォント エディター ツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-135">Enable new Font Editor tool within the Styles pane</span></span>](#enable-new-font-editor-tool-within-the-styles-pane) | <span data-ttu-id="740d9-136">89 以降</span><span class="sxs-lookup"><span data-stu-id="740d9-136">89 or later</span></span> |  
| [<span data-ttu-id="740d9-137">CSS Flexbox の新しいデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-137">Enable new CSS Flexbox debugging features</span></span>](#enable-new-css-flexbox-debugging-features) | <span data-ttu-id="740d9-138">89 以降</span><span class="sxs-lookup"><span data-stu-id="740d9-138">89 or later</span></span> |  
| [<span data-ttu-id="740d9-139">[+ ボタン] タブ メニューを有効にして、その他のツールを開く</span><span class="sxs-lookup"><span data-stu-id="740d9-139">Enable + button tab menus to open more tools</span></span>](#enable--button-tab-menus-to-open-more-tools) | <span data-ttu-id="740d9-140">89 以降</span><span class="sxs-lookup"><span data-stu-id="740d9-140">89 or later</span></span> |  
| [<span data-ttu-id="740d9-141">[ようこそ] タブを有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-141">Enable Welcome tab</span></span>](#enable-welcome-tool) | <span data-ttu-id="740d9-142">89 以降</span><span class="sxs-lookup"><span data-stu-id="740d9-142">89 or later</span></span> |  

### <a name="enable-webhint"></a><span data-ttu-id="740d9-143">Webhint を有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-143">Enable webhint</span></span>  

<span data-ttu-id="740d9-144">[webhint][WebhintMain] は、Web サイトとローカル Web ページにリアルタイムのフィードバックを提供するオープン ソース ツールです。</span><span class="sxs-lookup"><span data-stu-id="740d9-144">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="740d9-145">webhint によって提供される [フィードバックの種類][WebhintMain]。</span><span class="sxs-lookup"><span data-stu-id="740d9-145">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="740d9-146">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="740d9-146">accessibility</span></span>  
*   <span data-ttu-id="740d9-147">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="740d9-147">cross-browser compatibility</span></span>  
*   <span data-ttu-id="740d9-148">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="740d9-148">security</span></span>  
*   <span data-ttu-id="740d9-149">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="740d9-149">performance</span></span>  
*   <span data-ttu-id="740d9-150">プログレッシブ Web アプリ (PWA)</span><span class="sxs-lookup"><span data-stu-id="740d9-150">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="740d9-151">その他の一般的な Web 開発の問題</span><span class="sxs-lookup"><span data-stu-id="740d9-151">other common web development issues</span></span>  
    
<span data-ttu-id="740d9-152">[webhint 実験では][WebhintMain]、[問題] パネルに webhint フィードバック[が表示][DevtoolsIssuesIndex]されます。</span><span class="sxs-lookup"><span data-stu-id="740d9-152">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssuesIndex] panel.</span></span>  <span data-ttu-id="740d9-153">問題を選択して、ソリューションドキュメントと影響を受けるリソースの一覧を Web サイトに表示します。</span><span class="sxs-lookup"><span data-stu-id="740d9-153">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="740d9-154">リソース リンクを選択して、DevTools**で関連する** **[ネットワーク**] 、[ソース] 、または **[要素]** ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-154">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../media/experiments-webhint.msft.png":::
   <span data-ttu-id="740d9-156">[問題] パネルの**webhint フィードバック**</span><span class="sxs-lookup"><span data-stu-id="740d9-156">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="enable-network-console"></a><span data-ttu-id="740d9-157">ネットワーク コンソールの有効化</span><span class="sxs-lookup"><span data-stu-id="740d9-157">Enable Network Console</span></span>  

<span data-ttu-id="740d9-158">**ネットワーク コンソール** は、HTTP を使用してネットワークの代理要求を行う実験の作業タイトルです。</span><span class="sxs-lookup"><span data-stu-id="740d9-158">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="740d9-159">ネットワーク コンソールの実験 **を使用して** 、Web API 要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="740d9-159">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="740d9-160">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="740d9-160">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="740d9-161">ネットワーク コンソールを **使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="740d9-161">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="740d9-162">[ネットワーク] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-162">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="740d9-163">変更するネットワーク要求を見つけて再送信します。</span><span class="sxs-lookup"><span data-stu-id="740d9-163">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="740d9-164">コンテキスト メニュー \(右クリック\) を開き、[編集] と [ **再生] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="740d9-164">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="740d9-165">ネットワーク コンソール **が開いたら** 、ネットワーク要求情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="740d9-165">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="740d9-166">[送信 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="740d9-166">Choose **Send**.</span></span>  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="コンソール ドロワーのネットワーク コンソール" lightbox="../media/network-network-console.msft.png":::
   <span data-ttu-id="740d9-168">**コンソール ドロワー\*\*\*\*のネットワーク**コンソール</span><span class="sxs-lookup"><span data-stu-id="740d9-168">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="source-order-viewer"></a><span data-ttu-id="740d9-169">ソース オーダー ビューアー</span><span class="sxs-lookup"><span data-stu-id="740d9-169">Source Order Viewer</span></span>  

<span data-ttu-id="740d9-170">**ソース オーダー ビューアー** は、Web ページ ソース内の要素の順序を表示する実験です。</span><span class="sxs-lookup"><span data-stu-id="740d9-170">**Source Order Viewer** is an experiment that displays the order of elements in the webpage source.</span></span>  <span data-ttu-id="740d9-171">画面の表示順序がソースの順序と異なる場合があります。これはスクリーン リーダーとキーボード のユーザーを混同します。</span><span class="sxs-lookup"><span data-stu-id="740d9-171">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="740d9-172">[ソースオーダー **ビューアー] 実験** を使用して、画面の表示順序とソースの順序の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="740d9-172">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="740d9-173">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="740d9-173">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="740d9-174">ソース オーダー **ビューアーを使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="740d9-174">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="740d9-175">[要素] **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-175">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="740d9-176">引き出し \(bottom\) パネルで [アクセシビリティ] ウィンドウを開きます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="740d9-176">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="740d9-177">[ソース注文 **ビューアー] セクションで** 、[ソースの順序を **表示する] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="740d9-177">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="740d9-178">任意の HTML 要素を強調表示して、Web ページ ソース内の順序をオーバーレイで表示します。</span><span class="sxs-lookup"><span data-stu-id="740d9-178">Highlight any HTML element to display an overlay that the order in the webpage source.</span></span>  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウの [ソースオーダー ビューアー]" lightbox="../media/experiments-source-order-viewer.msft.png":::
   <span data-ttu-id="740d9-180">**[アクセシビリティ] ウィンドウ** の **[ソースオーダー** ビューアー]</span><span class="sxs-lookup"><span data-stu-id="740d9-180">**Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <a name="enable-composited-layers-in-3d-view"></a><span data-ttu-id="740d9-181">3D ビューで複合レイヤーを有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-181">Enable Composited Layers in 3D View</span></span>  

<span data-ttu-id="740d9-182">z-indexes と Document Object Model \(DOM\) と並んでレイヤーを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="740d9-182">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="740d9-183">この機能は、コンテキストを頻繁に切り替えることなくデバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="740d9-183">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="740d9-184">コンテキスト切り替えの削減が大きな問題だと特定しました。</span><span class="sxs-lookup"><span data-stu-id="740d9-184">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="740d9-185">作成するコードが Web アプリに与える影響は必ずしも明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="740d9-185">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="740d9-186">視覚的なデバッグを総合的に行う目的で、3D ビューレイヤーと複合レイヤーが結合されました。</span><span class="sxs-lookup"><span data-stu-id="740d9-186">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  

<span data-ttu-id="740d9-187">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="740d9-187">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="740d9-188">コンポジット レイヤー **を使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="740d9-188">To use **Composited Layers**, complete the following steps.</span></span>  

1.  <span data-ttu-id="740d9-189">ドロワーで **、[3D ビュー] ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="740d9-189">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="740d9-190">[複合 **レイヤー] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-190">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="740d9-191">アプリのすべてのペイントされたレイヤーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="740d9-191">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="740d9-192">独自の Web アプリでこの機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="740d9-192">Try this feature with your own web apps.</span></span>  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="740d9-194">**[コンポジット レイヤー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="740d9-194">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### <a name="enable-new-font-editor-tool-within-the-styles-pane"></a><span data-ttu-id="740d9-195">[スタイル] ウィンドウ内で新しいフォント エディター ツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-195">Enable new Font Editor tool within the Styles pane</span></span>  

<span data-ttu-id="740d9-196">これで、新しいビジュアル フォント エディターを [使用してフォント][DevtoolsInspectStylesEditFonts] を編集できます。</span><span class="sxs-lookup"><span data-stu-id="740d9-196">You may now use the new visual [Font Editor][DevtoolsInspectStylesEditFonts] to edit fonts.</span></span>  <span data-ttu-id="740d9-197">フォントとフォントの特性を定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="740d9-197">Use it define fonts and font characteristics.</span></span>  <span data-ttu-id="740d9-198">ビジュアル フォント エディター **を使用すると** 、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="740d9-198">The visual **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="740d9-199">さまざまなフォント プロパティの単位を切り替える</span><span class="sxs-lookup"><span data-stu-id="740d9-199">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="740d9-200">異なるフォント プロパティのキーワードを切り替える</span><span class="sxs-lookup"><span data-stu-id="740d9-200">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="740d9-201">単位の変換</span><span class="sxs-lookup"><span data-stu-id="740d9-201">Convert units</span></span>  
*   <span data-ttu-id="740d9-202">正確な CSS コードを生成する</span><span class="sxs-lookup"><span data-stu-id="740d9-202">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="740d9-203">実験を有効にしたら、DevTools を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="740d9-203">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="740d9-204">新しいビジュアル フォント エディターを **使用するには、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="740d9-204">To use the new visual **Font Editor**, complete the following steps.</span></span>  

1.  <span data-ttu-id="740d9-205">[要素] **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-205">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="740d9-206">[スタイル] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-206">Open the **Styles** pane.</span></span>  
1.  <span data-ttu-id="740d9-207">[フォント エディター **] アイコンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="740d9-207">Choose the **Font Editor** icon.</span></span>  
    
<span data-ttu-id="740d9-208">新しいビジュアル フォント エディターの詳細については[、DevTools][DevtoolsInspectStylesEditFonts]の [スタイル] ウィンドウの [CSS フォントスタイルと設定の編集] に移動します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="740d9-208">For more information about the new visual **Font Editor**, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="ビジュアル の [フォント エディター] ウィンドウが強調表示されます" lightbox="../media/font-editor-open.msft.png":::
   <span data-ttu-id="740d9-210">ビジュアル の [ **フォント エディター]** ウィンドウが強調表示されます</span><span class="sxs-lookup"><span data-stu-id="740d9-210">The visual **Font Editor** pane is highlighted</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-new-css-flexbox-debugging-features"></a><span data-ttu-id="740d9-211">CSS Flexbox の新しいデバッグ機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-211">Enable new CSS Flexbox debugging features</span></span>  

<span data-ttu-id="740d9-212">この実験的な機能は、CSS Flexbox レイアウトのデバッグに役立つ多くの新しい視覚化を提供します。</span><span class="sxs-lookup"><span data-stu-id="740d9-212">This experimental feature provides many new visualizations to help you debug CSS Flexbox layouts.</span></span>  <span data-ttu-id="740d9-213">最新の実験機能をプレビューするには、 [この実験を有効にし](#turn-on-experimental-features) 、DevTools を再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="740d9-213">To preview the latest experimental features, [turn on this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a><span data-ttu-id="740d9-214">[検査] ツールを使用して Flexbox レイアウトに永続的なオーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="740d9-214">Display persistent overlays on Flexbox layouts with the Inspect tool</span></span>  

<span data-ttu-id="740d9-215">[ **検査** ] ツールを使用すると、Web サイト内の CSS Flexbox レイアウトをマウスでホバーして識別し、視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="740d9-215">The **Inspect** tool provides a quick way to identify and visualize CSS Flexbox layouts in a website by hovering on them with the mouse.</span></span>  <span data-ttu-id="740d9-216">DevTools **の** 左上隅にある ![ [検査 ](../media/inspect-icon.msft.png) \( Inspect \) ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="740d9-216">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="740d9-217">次に、Web サイトのデバッグ中に、flex コンテナーにカーソルを合わせると、flex コンテナーの周囲にアウトラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="740d9-217">Then, while debugging the website, hover on a flex container to display outlines around the flex container.</span></span>  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="検査ツールを使用して Flexbox コンテナーを表示する" lightbox="../media/flexbox-hover.msft.png":::
   <span data-ttu-id="740d9-219">検査ツールを使用して Flexbox コンテナー **を表示** する</span><span class="sxs-lookup"><span data-stu-id="740d9-219">Display Flexbox containers with the **Inspect** tool</span></span>  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a><span data-ttu-id="740d9-220">Flexbox レイアウトに永続的なオーバーレイを表示する</span><span class="sxs-lookup"><span data-stu-id="740d9-220">Display persistent overlays on Flexbox layouts</span></span>  

<span data-ttu-id="740d9-221">Microsoft Edge バージョン 89 以降では、実験的な CSS Flexbox 機能では、Flexbox レイアウトで永続的なオーバーレイを有効にするオプションも提供しています。</span><span class="sxs-lookup"><span data-stu-id="740d9-221">In Microsoft Edge version 89 or later, the experimental CSS Flexbox feature also offers the option to turn on persistent overlays on Flexbox layouts.</span></span>  <span data-ttu-id="740d9-222">永続的なオーバーレイには、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="740d9-222">Persistent overlays provide the following benefits.</span></span>  

*   <span data-ttu-id="740d9-223">永続的なオーバーレイは、スクロール、マウスの移動、DevTools の他の機能の使用時に Web ページに表示されたままです。</span><span class="sxs-lookup"><span data-stu-id="740d9-223">Persistent overlays remain visible on the webpage as you scroll, move your mouse, and use other features of the DevTools.</span></span>
*   <span data-ttu-id="740d9-224">複数の永続的なオーバーレイを同時に使用して、複数の Flexbox レイアウトを一度に確認できます。</span><span class="sxs-lookup"><span data-stu-id="740d9-224">Multiple persistent overlays may be used at the same time, to allow you to review several Flexbox layouts at once.</span></span>  
*   <span data-ttu-id="740d9-225">永続的なオーバーレイは、色構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="740d9-225">Persistent overlays offer color configuration options.</span></span>  
    
<span data-ttu-id="740d9-226">Flexbox レイアウトの永続的なオーバーレイを切り替えるには、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="740d9-226">To toggle persistent overlays on Flexbox layout, use one of following actions.</span></span>  

*   <span data-ttu-id="740d9-227">要素ツール **の DOM ツリー** に表示される Flexbox コンテナーの横にある [Flexbox 楕円] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="740d9-227">Choose the **Flexbox** oval icon next to any Flexbox container displayed in the DOM tree of the **Elements** tool.</span></span>  
*   <span data-ttu-id="740d9-228">[要素] **ツールにある** 新しい [レイアウト] パネルを **開** き、強調表示する各 Flexbox コンテナーの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="740d9-228">Open the new **Layout** panel located in the **Elements** tool, and choose the checkbox next to each Flexbox container you want to highlight.</span></span>  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools の Flex アイコンとレイアウト パネル" lightbox="../media/flexbox-overlay.msft.png":::
   <span data-ttu-id="740d9-230">DevTools **の** Flex アイコンとレイアウト パネル</span><span class="sxs-lookup"><span data-stu-id="740d9-230">Flex icons and **Layout** panel in DevTools</span></span>  
:::image-end:::  

#### <a name="configure-persistent-overlays"></a><span data-ttu-id="740d9-231">永続的なオーバーレイを構成する</span><span class="sxs-lookup"><span data-stu-id="740d9-231">Configure persistent overlays</span></span>  

<span data-ttu-id="740d9-232">CSS グリッドまたは Flexbox レイアウトの永続的オーバーレイのオプションを構成するには、[レイアウト] ウィンドウ **を使用** します。</span><span class="sxs-lookup"><span data-stu-id="740d9-232">To configure options for persistent overlays for CSS grids or Flexbox layouts, use the **Layout** pane.</span></span>  <span data-ttu-id="740d9-233">[ **レイアウト** ] ウィンドウは、[スタイル] ウィンドウと **[** 計算] ウィンドウの横にある **[** 要素] **ツールに** 配置されます。</span><span class="sxs-lookup"><span data-stu-id="740d9-233">The **Layout** pane is located in the **Elements** tool next to the **Styles** and **Computed** panes.</span></span>  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="レイアウト パネル" lightbox="../media/flexbox-layout.msft.png":::
   <span data-ttu-id="740d9-235">レイアウト パネル</span><span class="sxs-lookup"><span data-stu-id="740d9-235">Layout panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable--button-tab-menus-to-open-more-tools"></a><span data-ttu-id="740d9-236">[+ ボタン] タブ メニューを有効にして、その他のツールを開く</span><span class="sxs-lookup"><span data-stu-id="740d9-236">Enable + button tab menus to open more tools</span></span>  

<span data-ttu-id="740d9-237">新しい [その他のツール] **\(** \) アイコンを使用して、その他のツール `+` を開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="740d9-237">You may now open more tools using the new **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="740d9-238">[有効にする] **+** [ボタン] タブ メニューをオンにして、さらに多くのツール実験を開き、DevTools を再読み込みすると、DevTools の上部にあるタブ グループの右側にプラス記号 \( \) が表示されます。 `+`</span><span class="sxs-lookup"><span data-stu-id="740d9-238">After you turn on the **Enable + button tab menus to open more tools** experiment and reload DevTools, a plus sign \(`+`\) displays to the right of the tab group at the top of the DevTools.</span></span>  <span data-ttu-id="740d9-239">タブ バーに追加できるその他のツールの一覧を表示するには、新しい **[** その他のツール] \( `+` \) アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="740d9-239">To display a list of other tools that you may add to the tab bar, choose the new **More Tools** \(`+`\) icon.</span></span>  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="上部ウィンドウの [その他のツール]" lightbox="../media/experiments-more-tools-button.msft.png":::
   <span data-ttu-id="740d9-241">**上部ウィンドウの** [その他のツール]</span><span class="sxs-lookup"><span data-stu-id="740d9-241">**More Tools** in the top pane</span></span>
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-welcome-tool"></a><span data-ttu-id="740d9-242">ウェルカム ツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="740d9-242">Enable Welcome tool</span></span>

<span data-ttu-id="740d9-243">この実験では **、What's New ツールを新** しいウェルカム ツール **に置き換** える。</span><span class="sxs-lookup"><span data-stu-id="740d9-243">This experiment replaces the **What's New** tool with the new **Welcome** tool.</span></span>  <span data-ttu-id="740d9-244">次のコンテンツの更新されたデザインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="740d9-244">It displays a refreshed design for the following content.</span></span>  

*   <span data-ttu-id="740d9-245">開発者向けドキュメントへのリンク</span><span class="sxs-lookup"><span data-stu-id="740d9-245">Links to developer docs</span></span>  
*   <span data-ttu-id="740d9-246">最新の機能</span><span class="sxs-lookup"><span data-stu-id="740d9-246">the latest features</span></span>  
*   <span data-ttu-id="740d9-247">リリース ノート</span><span class="sxs-lookup"><span data-stu-id="740d9-247">release notes</span></span>  
*   <span data-ttu-id="740d9-248">Microsoft Edge DevTools チームに連絡するオプション</span><span class="sxs-lookup"><span data-stu-id="740d9-248">Option to contact the Microsoft Edge DevTools team</span></span>  
    
<span data-ttu-id="740d9-249">ウェルカム **ツールは** 、Microsoft Edge への更新の後に自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="740d9-249">The **Welcome** tool opens automatically after each update to Microsoft Edge.</span></span>  <span data-ttu-id="740d9-250">更新後にウェルカム ツール\*\*\*\* が表示されるのを防ぐには、[ようこそ]\*\*\*\* ツールのタイトルの下にある更新の後、[開く] タブの横にあるチェック ボックス**を**オフにします。</span><span class="sxs-lookup"><span data-stu-id="740d9-250">To prevent the display of the **Welcome** tool after each update, clear the checkbox next to **Open tab after each update** under the **Welcome** tool title.</span></span>  

<span data-ttu-id="740d9-251">元の [What's **New]** ツールを[][DevtoolsCustomizeIndexSettings]使用する場合は、[設定の実験] に移動し、[ようこそ] タブを有効にするの横にあるチェック  >  \*\*\*\*\*\*ボックスをオフにします\*\*。</span><span class="sxs-lookup"><span data-stu-id="740d9-251">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="ウェルカム ツール" lightbox="../media/experiments-welcome.msft.png":::
   <span data-ttu-id="740d9-253">**ウェルカム** ツール</span><span class="sxs-lookup"><span data-stu-id="740d9-253">**Welcome** tool</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a><span data-ttu-id="740d9-254">以前の実験的な機能</span><span class="sxs-lookup"><span data-stu-id="740d9-254">Previous experimental features</span></span>  

*   <span data-ttu-id="740d9-255">Microsoft Edge バージョン 83 以降では[、3D][Devtools3dViewIndex]ビューが使用可能で、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="740d9-255">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="740d9-256">[Microsoft][DevtoolsCustomizeIndex] Edge バージョン 85 以降では、パネル間でタブを移動するサポートを有効にし、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="740d9-256">[Turn on support to move tabs between panels][DevtoolsCustomizeIndex] is now available and turned on by default in Microsoft Edge version 85 or later.</span></span>  
*   <span data-ttu-id="740d9-257">[DevTools の][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode] キーボード ショートカットと Microsoft Visual Studio コードの一致が利用可能で、Microsoft Edge バージョン 86 以降で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="740d9-257">[Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  
*   <span data-ttu-id="740d9-258">[DevTools で任意の][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools] アクションのキーボード ショートカットを編集する機能が利用可能になったので、Microsoft Edge バージョン 89 以降では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="740d9-258">[Edit keyboard shortcuts for any action in the DevTools][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
*   <span data-ttu-id="740d9-259">[新しい CSS グリッド デバッグ機能][DevtoolsCssGrid] を有効にし、Microsoft Edge バージョン 89 以降で既定で有効にしました。</span><span class="sxs-lookup"><span data-stu-id="740d9-259">[Turn on new CSS grid debugging features][DevtoolsCssGrid] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
*   <span data-ttu-id="740d9-260">[エミュレーション: Microsoft][DevtoolsDeviceModeDualScreenAndFoldables] Edge バージョン 90 以降では、デュアル スクリーン モードをサポートし、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="740d9-260">[Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables] is now available and turned on by default in Microsoft Edge version 90 or later.</span></span>  

    
## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="740d9-261">実験的な機能に関するフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="740d9-261">Providing feedback on experimental features</span></span>  

<span data-ttu-id="740d9-262">Microsoft Edge DevTools 実験、または DevTools に関連するその他のフィードバックを提供する。</span><span class="sxs-lookup"><span data-stu-id="740d9-262">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="740d9-263">DevTools の [フィードバック **の送信** ] アイコンを使用してフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="740d9-263">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="740d9-264">ツイートの [@EdgeDevTools][TwitterEdgedevtools]</span><span class="sxs-lookup"><span data-stu-id="740d9-264">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  
    
:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="740d9-266">Microsoft Edge DevTools の **[フィードバックの送信]** アイコン</span><span class="sxs-lookup"><span data-stu-id="740d9-266">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D ビュー | Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "Microsoft Edge DevTools サーバーで CSS グリッドを検査|Microsoft Docs"  
[DevtoolsCustomizeIndex]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ |Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools]: ../customize/shortcuts.md#edit-keyboard-shortcuts-for-any-action-in-the-devtools "DevTools コントロール内の任意のアクションのキーボード ショートカットを編集|Microsoft Docs"  
[DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode]: ../customize/shortcuts.md#match-keyboard-shortcuts-in-the-devtools-to-microsoft-visual-studio-code "DevTools のキーボード ショートカットと Microsoft コード コードのVisual Studio一致|Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools アプリケーションでデバイス モードでモバイル デバイスをシミュレート|Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsIssuesIndex]: ../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevtoolsOpenIndex]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "Microsoft Edge DevTools アプリケーションでデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレート|Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
