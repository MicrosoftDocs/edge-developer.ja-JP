---
description: CSS グリッドのデバッグ機能、ネットワーク コンソールを使った要求の編集と再生など。
title: DevTools の新機能 (Microsoft Edge 85)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 01651bdf0f36f7c175f843655c275695a680b6c1
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015462"
---
# <span data-ttu-id="74f35-104">DevTools の新機能 (Microsoft Edge 85)</span><span class="sxs-lookup"><span data-stu-id="74f35-104">What's New In DevTools (Microsoft Edge 85)</span></span>  

## <span data-ttu-id="74f35-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="74f35-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="74f35-106">以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="74f35-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="74f35-107">Visual Studio Code 拡張機能などの新機能を試すには、お知らせを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f35-107">See the announcements to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="74f35-108">開発者ツールの最新で最良の機能について最新情報を入手するには、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]をダウンロードして、[Twitter で Microsoft Edge DevTools チームをフォローしますます][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="74f35-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="74f35-109">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="74f35-109">CSS grid debugging features</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   <span data-ttu-id="74f35-111">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="74f35-111">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-112">Microsoft Edge DevTools チームは、Chrome DevTools チームと Chromium コミュニティと連携して、新しい CSS グリッドのデバッグ機能を DevTools に追加しています。</span><span class="sxs-lookup"><span data-stu-id="74f35-112">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span></span>  <span data-ttu-id="74f35-113">現在、グリッド線の番号、グリッドのギャップ、拡張グリッド線をページ上にオーバーレイとして表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-113">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span></span>  <span data-ttu-id="74f35-114">さらに、グリッド ツールのさらなる改善が間もなく提供されます。</span><span class="sxs-lookup"><span data-stu-id="74f35-114">Plus, more improvements to the grid tools are coming soon.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   <span data-ttu-id="74f35-116">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="74f35-116">CSS grid debugging features</span></span>
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="74f35-117">実験を有効にするには、「[試験的な機能を有効にする][DevtoolsExperimentalFeaturesTurnOn]」を参照して、**[新しい CSS グリッドのデバッグ機能を有効にする]** の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="74f35-117">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span></span>  
> 
> <span data-ttu-id="74f35-118">サンプルを使って実験を試すには、「[CSS グリッド プランナーの例][CodepenRachelweilYzwBzKM]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f35-118">To try out the experiment with a sample, see [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span></span>  

<span data-ttu-id="74f35-119">Chromium の問題 [#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="74f35-119">Chromium issue [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="74f35-120">ネットワーク コンソールを使用して要求を編集および再生する</span><span class="sxs-lookup"><span data-stu-id="74f35-120">Edit and Replay requests with the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   <span data-ttu-id="74f35-122">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="74f35-122">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-123">**ネットワーク コンソール**を使用して、[ネットワーク ログ][DevtoolsNetworkIndexLogActivity]の要求に対して**編集と再生**を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-123">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="ネットワーク コンソールを使用して NetworkLog で要求を編集して再生する" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   <span data-ttu-id="74f35-125">**ネットワーク コンソール**を使用して[NetworkLog][DevtoolsNetworkIndexLogActivity]で要求を編集して再生する</span><span class="sxs-lookup"><span data-stu-id="74f35-125">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-126">新しいパネルとして、[DevTools のドロワー][DevtoolsCustomizeIndexDrawer]に **[ネットワーク コンソール]** が開き、HTTP 要求の情報が自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="74f35-126">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span></span>  <span data-ttu-id="74f35-127">サーバーから返された応答を確認するには、要求を編集し (必要な場合)、**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74f35-127">To see the response returned from the server, edit the request \(if needed\) and select **Send**.</span></span>  

<span data-ttu-id="74f35-128">また、**[ネットワーク コンソール]** を使用して、DevTools から直接 HTTP 要求を作成して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="74f35-128">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="[ネットワーク コンソール] パネル" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   <span data-ttu-id="74f35-130">**[ネットワーク コンソール]** パネル</span><span class="sxs-lookup"><span data-stu-id="74f35-130">The **Network Console** panel</span></span>  
:::image-end:::  

> [!TIP]
> <span data-ttu-id="74f35-131">[DevTools のドロワー][DevtoolsCustomizeIndexDrawer]の代わりに、メイン (上部) パネルに **[ネットワーク コンソール]** を表示するには、「[パネル間でのツールの移動](#move-tools-between-panels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f35-131">To see **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], see [moving tools between panels](#move-tools-between-panels).</span></span>  

> [!NOTE]
> <span data-ttu-id="74f35-132">実験を有効にするには、「[試験的な機能を有効にする][DevtoolsExperimentalFeaturesTurnOn]」を参照して、**[ネットワーク コンソールを有効にする]** の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="74f35-132">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable Network Console**.</span></span>  
> 
> <span data-ttu-id="74f35-133">[ネットワーク ログ][DevtoolsNetworkIndexLogActivity]を開き、コンテキスト メニューを開いて (右クリック)、**[編集と再生]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74f35-133">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and select **Edit and Replay**.</span></span>  

<span data-ttu-id="74f35-134">Chromium の問題 [#1093687][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="74f35-134">Chromium issue [#1093687][CR1093687]</span></span>  

### <span data-ttu-id="74f35-135">[タイミング] タブのサービス ワーカーのrespondWith イベント</span><span class="sxs-lookup"><span data-stu-id="74f35-135">Service worker respondWith events in the Timing tab</span></span>  

<span data-ttu-id="74f35-136">**[ネットワーク]** パネルの **[タイミング]** タブに、`respondWith` サービス ワーカー イベントが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-136">The **Timing** tab of the **Network** panel now includes `respondWith` service worker events.</span></span>  <span data-ttu-id="74f35-137">`respondWith`サービス ワーカー イベントは、サービス ワーカー `fetch` イベント ハンドラーの実行が開始される直前から、`respondWith` ハンドラーの `fetch` Promise が解決されるまでの期間を示します。</span><span class="sxs-lookup"><span data-stu-id="74f35-137">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="[ネットワーク] パネルの [タイミング] タブ内の respondWith サービス ワーカー イベント" lightbox="../../media/2020/06/timing-tab.msft.png":::
   <span data-ttu-id="74f35-139">**[ネットワーク]** パネルの **[タイミング]** タブ内の `respondWith` サービス ワーカー イベント</span><span class="sxs-lookup"><span data-stu-id="74f35-139">The `respondWith` service worker event in the **Timing** tab of the **Network** panel</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-140">**受信した応答**を展開して、`CacheStorageCacheName`、`serviceWorkerResponseSource`、`ResponseTime` などの`fetch` の応答の追加情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="74f35-140">Expand **Response received** to see additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="受信した応答を展開して、フェッチ応答から追加情報を確認する" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   <span data-ttu-id="74f35-142">**受信した応答**を展開して、`fetch` 応答から追加情報を確認する </span><span class="sxs-lookup"><span data-stu-id="74f35-142">Expand **Response received** to see additional information from the `fetch` response</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-143">Chromium の問題 [#1066579][CR1066579]</span><span class="sxs-lookup"><span data-stu-id="74f35-143">Chromium issue [#1066579][CR1066579]</span></span>  

### <span data-ttu-id="74f35-144">[問題] パネル内の webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="74f35-144">webhint feedback in the Issues panel</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   <span data-ttu-id="74f35-146">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="74f35-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-147">[webhint][WebhintMain] は、アクセシビリティ、ブラウザ間の互換性、セキュリティ、パフォーマンス、PWA、および Web サイトの他の一般的な Web 開発の問題に関するリアルタイムのフィードバックを提供するオープン ソース ツールです。</span><span class="sxs-lookup"><span data-stu-id="74f35-147">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="74f35-148">[[問題]][DevtoolsIssues] パネルに webhint のフィードバックが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-148">You are now able to see webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   <span data-ttu-id="74f35-150">[問題] パネル内の webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="74f35-150">webhint feedback in the Issues panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="74f35-151">実験を有効にするには、「[試験的な機能を有効にする][DevtoolsExperimentalFeaturesTurnOn]」を参照して、**[webhint を有効にする]** の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="74f35-151">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable webhint**.</span></span>  
> 
> <span data-ttu-id="74f35-152">[[問題]][DevtoolsIssues] パネルを開いて、webhint からのフィードバックを表示します。</span><span class="sxs-lookup"><span data-stu-id="74f35-152">Open the [Issues][DevtoolsIssues] panel to see feedback from webhint.</span></span>  

<span data-ttu-id="74f35-153">Chromium の問題 [#1070378][CR1070378]</span><span class="sxs-lookup"><span data-stu-id="74f35-153">Chromium issue [#1070378][CR1070378]</span></span>  

### <span data-ttu-id="74f35-154">パネル間でツールを移動する</span><span class="sxs-lookup"><span data-stu-id="74f35-154">Move tools between panels</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   <span data-ttu-id="74f35-156">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="74f35-156">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-157">通常、**要素**や**ネットワーク**などのツールは、DevTools のメイン (上部) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="74f35-157">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="74f35-158">同様に、**3D ビュー**や**問題**などのツールは、DevTools のドロワー (下部) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="74f35-158">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="74f35-159">現在、上と下のパネル間でツールを移動して、DevTools のレイアウトをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-159">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="パネル間でのタブの移動" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   <span data-ttu-id="74f35-161">パネル間でのタブの移動</span><span class="sxs-lookup"><span data-stu-id="74f35-161">Moving tabs between panels</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="74f35-162">実験を有効にするには、「[試験的な機能を有効にする][DevtoolsExperimentalFeaturesTurnOn]」を参照して、**[パネル間でタブを移動できるようにサポートを有効にする]** の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="74f35-162">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable support to move tabs between panels**.</span></span>  

<span data-ttu-id="74f35-163">Chromium の問題 [#897944][CR897944]</span><span class="sxs-lookup"><span data-stu-id="74f35-163">Chromium issue [#897944][CR897944]</span></span>  

### <span data-ttu-id="74f35-164">[ネットワーク] パネルでのイニシエーターのヒントの改善</span><span class="sxs-lookup"><span data-stu-id="74f35-164">Improved Initiator tooltip in the Network panel</span></span>  

<span data-ttu-id="74f35-165">Microsoft Edge 83 および 84 では、[イニシエーター] 列にヒントが表示されます。これにより、[ネットワーク ログ][DevtoolsNetworkIndexLogActivity]には、水平スクロールバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74f35-165">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span></span>  <span data-ttu-id="74f35-166">ヒントを水平方向にスクロールすることでのみ、要求を開始したコール スタックを確認できました。</span><span class="sxs-lookup"><span data-stu-id="74f35-166">You were only able to see the call stack that initiated the request by scrolling horizontally in the tooltip.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   <span data-ttu-id="74f35-168">Microsoft Edge 84 のイニシエーターのヒント</span><span class="sxs-lookup"><span data-stu-id="74f35-168">The Initiator tooltip in Microsoft Edge 84</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-169">Microsoft Edge 85 以降では、水平方向にスクロールしなくても、ヒントでイニシエーターのコール スタックを確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-169">Starting with Microsoft Edge 85, you are now able to see the Initiator call stack in the tooltip without scrolling horizontally.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   <span data-ttu-id="74f35-171">Microsoft Edge 85 のイニシエーターのヒント</span><span class="sxs-lookup"><span data-stu-id="74f35-171">The Initiator tooltip in Microsoft Edge 85</span></span>
:::image-end:::  

<span data-ttu-id="74f35-172">Chromium の問題 [#1069404][CR1069404]</span><span class="sxs-lookup"><span data-stu-id="74f35-172">Chromium issue [#1069404][CR1069404]</span></span>  

## <span data-ttu-id="74f35-173">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="74f35-173">Announcements from the Chromium project</span></span>  

<span data-ttu-id="74f35-174">次のセクションでは、オープン ソースの Chromium プロジェクトに寄与した Microsoft Edge 85 で利用できるその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="74f35-174">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="74f35-175">CSS-in-JS フレームワークのスタイルの編集</span><span class="sxs-lookup"><span data-stu-id="74f35-175">Style editing for CSS-in-JS frameworks</span></span>  

<span data-ttu-id="74f35-176">**[スタイル]** ウィンドウで、[CSS オブジェクトモデル (CSSOM)][CsswgDraftsCssom] API を使って作成されたスタイルの編集がより適切にサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-176">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span></span>  <span data-ttu-id="74f35-177">多くの CSS-in-JS フレームワークとライブラリは、内部で CSSOM API を使ってスタイルを構築します。</span><span class="sxs-lookup"><span data-stu-id="74f35-177">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span></span>  

<span data-ttu-id="74f35-178">現在、[Constructable Stylesheets][WicgConstructStylesheet] を使って、JavaScript で追加されたスタイルを編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-178">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span></span>  <span data-ttu-id="74f35-179">Constructable Stylesheets は、[Shadow DOM][MdnShadowDom]を使用するときに、再利用可能なスタイルを作成して配布するための新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="74f35-179">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span></span>  

<span data-ttu-id="74f35-180">たとえば、`CSSStyleSheet` (CSSOM API) で追加された `h1` スタイルは、以前は編集できませんでした。</span><span class="sxs-lookup"><span data-stu-id="74f35-180">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span></span>  <span data-ttu-id="74f35-181">現在、そのスタイルは **[スタイル]** ウィンドウで編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-181">The styles are editable now in the **Styles** pane.</span></span>  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="CSSStyleSheet で追加された h1 スタイルの background プロパティをピンクからライトブルーに変更する" lightbox="../../media/2020/06/css-in-js.msft.png":::
   <span data-ttu-id="74f35-183">`CSSStyleSheet` で追加された `h1` スタイルの `background` プロパティを `pink` から `lightblue` に変更します。</span><span class="sxs-lookup"><span data-stu-id="74f35-183">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span></span>
:::image-end:::  

<span data-ttu-id="74f35-184">この機能は、[CSS-in-JS を使用するサンプル][CodepenZoherghadyaliAbdgrpz]で試すことができます。</span><span class="sxs-lookup"><span data-stu-id="74f35-184">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span></span>

<span data-ttu-id="74f35-185">Chromium の問題 [#946975][CR946975]</span><span class="sxs-lookup"><span data-stu-id="74f35-185">Chromium issue [#946975][CR946975]</span></span>  

### <span data-ttu-id="74f35-186">[Lighthouse] パネルの Lighthouse 6</span><span class="sxs-lookup"><span data-stu-id="74f35-186">Lighthouse 6 in the Lighthouse panel</span></span>  

<span data-ttu-id="74f35-187">**[Lighthouse]** パネルは、現在 Lighthouse 6 を実行しています。</span><span class="sxs-lookup"><span data-stu-id="74f35-187">The **Lighthouse** panel is now running Lighthouse 6.</span></span>  <span data-ttu-id="74f35-188">すべての変更の一覧については、「[v6.0.0 のリリースノート][GithubGoogleChromeLighthouse600]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f35-188">For a full list of all changes, see [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span></span>  

<span data-ttu-id="74f35-189">Lighthouse 6.0 では、レポートに 3 つの新しい指標が導入されています。最大コンテンツのペイント (LCP)、累積レイアウト シフト (CLS)、および合計ブロッキング時間 (TBT) です。</span><span class="sxs-lookup"><span data-stu-id="74f35-189">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span></span>  

<span data-ttu-id="74f35-190">また、パフォーマンス スコアの計算式も再重み付けされ、ユーザーの読み込み操作がより適切に反映されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-190">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span></span>  

<span data-ttu-id="74f35-191">Chromium の問題 [#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="74f35-191">Chromium issue [#772558][CR772558]</span></span>  

#### <span data-ttu-id="74f35-192">First Meaningful Paint の廃止</span><span class="sxs-lookup"><span data-stu-id="74f35-192">First Meaningful Paint deprecation</span></span>  

<span data-ttu-id="74f35-193">Lighthouse 6.0 では、最初の意味のあるペイント (FMP) が廃止されました。</span><span class="sxs-lookup"><span data-stu-id="74f35-193">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span></span>  <span data-ttu-id="74f35-194">FMP は、**[パフォーマンス]** パネルからも削除されています。</span><span class="sxs-lookup"><span data-stu-id="74f35-194">FMP has also been removed from the **Performance** panel.</span></span>  <span data-ttu-id="74f35-195">**最大コンテンツのペイント**が、推奨される FMP の代替機能です。</span><span class="sxs-lookup"><span data-stu-id="74f35-195">**Largest Contentful Paint** is the recommended replacement for FMP.</span></span>  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

<span data-ttu-id="74f35-196">Chromium の問題 [#1096008][CR1096008]</span><span class="sxs-lookup"><span data-stu-id="74f35-196">Chromium issue [#1096008][CR1096008]</span></span>  

### <span data-ttu-id="74f35-197">新しい JavaScript 機能のサポート</span><span class="sxs-lookup"><span data-stu-id="74f35-197">Support for new JavaScript features</span></span>  

<span data-ttu-id="74f35-198">DevTools では、最新の JavaScript 言語機能の一部がより適切にサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-198">DevTools now has better support for some of the latest JavaScript language features.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="74f35-199">[optional chaining][V8DevOptionalChaining] 構文のオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="74f35-199">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="74f35-200">**コンソール**内のプロパティのオートコンプリート機能により、optional chaining 構文がサポートされるようになりました。たとえば、`name.` と `name[` に加えて、`name?.` も使えます。</span><span class="sxs-lookup"><span data-stu-id="74f35-200">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="74f35-201">[プライベート フィールド][V8DevClassFieldsPrivate]の構文の強調表示</span><span class="sxs-lookup"><span data-stu-id="74f35-201">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="74f35-202">プライベート クラスのフィールドが、**[ソース]** パネルで適切に強調表示され、整形出力されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-202">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="74f35-203">[Nullish 合体演算子][V8DevNullishCoalescing]の構文の強調表示</span><span class="sxs-lookup"><span data-stu-id="74f35-203">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="74f35-204">**[ソース]** パネルで nullish 合体演算子が整形出力されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-204">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="74f35-205">Chromium の問題 [#1073903][CR1073903]、 [#1083214][CR1083214]、 [#1083797][CR1083797]</span><span class="sxs-lookup"><span data-stu-id="74f35-205">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span></span>  

### <span data-ttu-id="74f35-206">[マニフェスト] ウィンドウでの新しいアプリのショートカットの警告</span><span class="sxs-lookup"><span data-stu-id="74f35-206">New app shortcut warnings in the Manifest pane</span></span>  

<span data-ttu-id="74f35-207">**アプリのショートカット** を使用すると、Web アプリ内で一般的または推奨されるタスクをすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="74f35-207">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span></span>  

<!--todo: add App shortcuts when section is live  -->  

<span data-ttu-id="74f35-208">**[マニフェスト]** ウィンドウには、次の条件の警告が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-208">The **Manifest** pane now shows warnings for the following conditions.</span></span>  

* <span data-ttu-id="74f35-209">アプリのショートカット アイコンが 96 x 96 ピクセルより小さい</span><span class="sxs-lookup"><span data-stu-id="74f35-209">The app shortcut icons are smaller than 96x96 pixels</span></span>  
* <span data-ttu-id="74f35-210">アプリのショートカット アイコンとマニフェスト アイコンが四角形でない (アイコンが無視されているため)</span><span class="sxs-lookup"><span data-stu-id="74f35-210">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span></span>  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="アプリのショートカットの警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   <span data-ttu-id="74f35-212">アプリのショートカットの警告</span><span class="sxs-lookup"><span data-stu-id="74f35-212">App shortcut warnings</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-213">Chromium の問題 [#955497][CR955497]</span><span class="sxs-lookup"><span data-stu-id="74f35-213">Chromium issue [#955497][CR955497]</span></span>  

### <span data-ttu-id="74f35-214">[計算済み] ウィンドウの一貫性のある表示</span><span class="sxs-lookup"><span data-stu-id="74f35-214">Consistent display of the Computed pane</span></span>  

<span data-ttu-id="74f35-215">**[要素]**] パネルの **[計算済み]** ウィンドウは、すべてのビューポート サイズのウィンドウとして一貫して表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-215">The **Computed** pane in the **Elements** panel now displays consistently as a pane across all viewport sizes.</span></span>  <span data-ttu-id="74f35-216">以前は、DevTools ビューポートの幅が狭い場合、**[計算済み]** ウィンドウは、**[スタイル]** ウィンドウ内にマージされました。</span><span class="sxs-lookup"><span data-stu-id="74f35-216">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span></span>  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="DevTools の幅が狭い場合でも、[計算済み] ウィンドウは個別のウィンドウとして表示されます" lightbox="../../media/2020/06/computed-pane.msft.png":::
   <span data-ttu-id="74f35-218">DevTools の幅が狭い場合でも、**[計算済み]** ウィンドウは個別のウィンドウとして常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="74f35-218">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span></span>
:::image-end:::  

<span data-ttu-id="74f35-219">Chromium の問題 [#1073899][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="74f35-219">Chromium issue [#1073899][CR1073899]</span></span>  

### <span data-ttu-id="74f35-220">WebAssembly ファイルのバイトコード オフセット</span><span class="sxs-lookup"><span data-stu-id="74f35-220">Bytecode offsets for WebAssembly files</span></span>  

<span data-ttu-id="74f35-221">DevTools は、Wasm 逆アセンブルの行番号を表示するためにバイトコード オフセットを使用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-221">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span></span>  
<span data-ttu-id="74f35-222">行番号によって、バイナリデータを見ていることが明確になり、Wasm ランタイムが場所を参照する方法に一貫性が保たれます。</span><span class="sxs-lookup"><span data-stu-id="74f35-222">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span></span>  

<span data-ttu-id="74f35-223">Chromium の問題 [#1071432][CR1071432]</span><span class="sxs-lookup"><span data-stu-id="74f35-223">Chromium issue [#1071432][CR1071432]</span></span>  

### <span data-ttu-id="74f35-224">[ソース] パネルでの行ごとのコピーと切り取り</span><span class="sxs-lookup"><span data-stu-id="74f35-224">Line-wise copy and cut in Sources Panel</span></span>  

<span data-ttu-id="74f35-225">[ソース パネル エディター][DevtoolsSourcesEditCssJavascript]で選択なしでコピーまたは切り取りを実行すると、現在のコンテンツの行がコピーまたは切り取りられます。</span><span class="sxs-lookup"><span data-stu-id="74f35-225">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesEditCssJavascript], DevTools copies or cuts the current line of content.</span></span>  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="カーソルが 5 行目の最後にある状態で、DevTools の pen.js から行全体をコピーして、Visual Studio Code に貼り付けます。" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   <span data-ttu-id="74f35-227">カーソルが 5 行目の最後にある状態で、DevTools の **pen.js** から行全体をコピーして、[Visual Studio Code][VSCode] に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="74f35-227">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [Visual Studio Code][VSCode].</span></span>
:::image-end:::  

<span data-ttu-id="74f35-228">Chromium の問題 [#800028][CR800028]</span><span class="sxs-lookup"><span data-stu-id="74f35-228">Chromium issue [#800028][CR800028]</span></span>

### <span data-ttu-id="74f35-229">コンソールの設定の更新</span><span class="sxs-lookup"><span data-stu-id="74f35-229">Console Settings updates</span></span>  

#### <span data-ttu-id="74f35-230">同じコンソールのメッセージをグループ解除する</span><span class="sxs-lookup"><span data-stu-id="74f35-230">Ungroup same console messages</span></span>  

<span data-ttu-id="74f35-231">コンソールの設定の **[類似のグループ化]** 切り替えが、重複するメッセージに適用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-231">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span></span>  <span data-ttu-id="74f35-232">以前は単に類似のメッセージに適用されていました。</span><span class="sxs-lookup"><span data-stu-id="74f35-232">Previously it just applied to similar messages.</span></span>  

<span data-ttu-id="74f35-233">たとえば、以前は、**[類似のグループ化]** がオフになっている場合でも、`hello` メッセージはグループ解除されませんでした。</span><span class="sxs-lookup"><span data-stu-id="74f35-233">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span></span>  <span data-ttu-id="74f35-234">現在、`hello` メッセージはグループ解除されます。</span><span class="sxs-lookup"><span data-stu-id="74f35-234">Now, the `hello` messages are ungrouped.</span></span>  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="[類似のグループ化] がオフの場合、hello メッセージはグループ解除されます。" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   <span data-ttu-id="74f35-236">**[類似のグループ化]** がオフの場合、`hello` メッセージはグループ解除されます。</span><span class="sxs-lookup"><span data-stu-id="74f35-236">When **Group similar** is unchecked, the `hello` messages are ungrouped</span></span>
:::image-end:::  

<span data-ttu-id="74f35-237">この機能は、[コンソールに重複したメッセージを送信するサンプル][CodepenZoherghadyaliZyrjgdJ]で試すことができます。</span><span class="sxs-lookup"><span data-stu-id="74f35-237">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span></span>  

<span data-ttu-id="74f35-238">Chromium の問題 [#1082963][CR1082963]</span><span class="sxs-lookup"><span data-stu-id="74f35-238">Chromium issue [#1082963][CR1082963]</span></span>  

### <span data-ttu-id="74f35-239">選択されたコンテキストのみの設定を保持する</span><span class="sxs-lookup"><span data-stu-id="74f35-239">Persisting Selected context only settings</span></span>  

<span data-ttu-id="74f35-240">コンソールの設定で **[選択されたコンテキストのみ]** の設定が保持されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-240">The **Selected context only** settings in Console Settings is now persisted.</span></span>  <span data-ttu-id="74f35-241">以前は、DevTools を閉じてもう一度開くたびに、設定はリセットされました。</span><span class="sxs-lookup"><span data-stu-id="74f35-241">Previously the settings were reset every time you closed and reopened DevTools.</span></span>  <span data-ttu-id="74f35-242">この変更により、設定の動作が他のコンソールの設定オプションと一致するようになります。</span><span class="sxs-lookup"><span data-stu-id="74f35-242">The change makes the setting behavior consistent with other Console Settings options.</span></span>  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="[選択されたコンテキストのみ] の設定" lightbox="../../media/2020/06/selected-context.msft.png":::
   <span data-ttu-id="74f35-244">**[選択されたコンテキストのみ]** の設定</span><span class="sxs-lookup"><span data-stu-id="74f35-244">**Selected context only** setting</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-245">Chromium の問題 [#1055875][CR1055875]</span><span class="sxs-lookup"><span data-stu-id="74f35-245">Chromium issue [#1055875][CR1055875]</span></span>  

### <span data-ttu-id="74f35-246">[パフォーマンス] パネルの更新</span><span class="sxs-lookup"><span data-stu-id="74f35-246">Performance panel updates</span></span>  

#### <span data-ttu-id="74f35-247">[パフォーマンス] パネルの JavaScript コンパイル キャッシュ情報</span><span class="sxs-lookup"><span data-stu-id="74f35-247">JavaScript compilation cache information in Performance panel</span></span>  

<span data-ttu-id="74f35-248">[JavaScript コンパイル キャッシュ情報][V8DevCodeCaching] が、常に [パフォーマンス] パネルの [概要] タブに表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-248">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the Summary tab of the Performance panel.</span></span>  <span data-ttu-id="74f35-249">以前は、コード キャッシュが行われなかった場合、DevTools でコード キャッシュに関連するものは表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="74f35-249">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span></span>  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript コンパイルキャッシュ情報" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   <span data-ttu-id="74f35-251">JavaScript コンパイルキャッシュ情報</span><span class="sxs-lookup"><span data-stu-id="74f35-251">JavaScript compilation cache information</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-252">Chromium の問題 [#912581][CR912581]</span><span class="sxs-lookup"><span data-stu-id="74f35-252">Chromium issue [#912581][CR912581]</span></span>  

#### <span data-ttu-id="74f35-253">[パフォーマンス] パネルでの移動のタイミングの調整</span><span class="sxs-lookup"><span data-stu-id="74f35-253">Navigation timing alignment in the Performance panel</span></span>  

<span data-ttu-id="74f35-254">**[パフォーマンス]** パネルでは、記録が開始された時間に基づいてルーラーに時間が表示されていました。</span><span class="sxs-lookup"><span data-stu-id="74f35-254">The **Performance** panel used to show times in the rulers based on when the recording started.</span></span>  <span data-ttu-id="74f35-255">現在、タイミングはユーザーが移動する記録に変更され、移動に関連するルーラー時間が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74f35-255">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span></span>  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="[パフォーマンス] パネルでの移動のタイミングの調整" lightbox="../../media/2020/06/nav-timing.msft.png":::
   <span data-ttu-id="74f35-257">**[パフォーマンス]** パネルでの移動のタイミングの調整</span><span class="sxs-lookup"><span data-stu-id="74f35-257">Align navigation timing in **Performance** panel</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-258">`DOMContentLoaded`、First Paint (最初のペイント)、First Contentful Paint (最初のコンテンツのペイント)、最大コンテンツのペイント (Largest Contentful Paint) の各イベントの時間は、移動の開始からの相対的な時間に更新されます。つまり、タイミングは、`PerformanceObserver` によって報告されるタイミングと一致します。</span><span class="sxs-lookup"><span data-stu-id="74f35-258">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span></span>  

<span data-ttu-id="74f35-259">Chromium の問題 [#974550][CR974550]</span><span class="sxs-lookup"><span data-stu-id="74f35-259">Chromium issue [#974550][CR974550]</span></span>  

### <span data-ttu-id="74f35-260">ブレークポイント、条件付きブレークポイント、およびログポイントの新しいアイコン</span><span class="sxs-lookup"><span data-stu-id="74f35-260">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="74f35-261">**[ソース]** パネルには、ブレークポイント、条件付きブレークポイント、およびログポイントの新しいデザインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="74f35-261">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span></span>  <span data-ttu-id="74f35-262">ブレークポイントは、[Visual Studio Code][VSCode] と [Visual Studio][VS]と同様に、赤い円で表されます。</span><span class="sxs-lookup"><span data-stu-id="74f35-262">Breakpoints are represented by a red circle, just like [Visual Studio Code][VSCode] and [Visual Studio][VS].</span></span>  <span data-ttu-id="74f35-263">条件付きブレークポイントとログポイントを区別するためにアイコンが追加されています。</span><span class="sxs-lookup"><span data-stu-id="74f35-263">Icons are added to differentiate conditional breakpoints and logpoints.</span></span>  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="ブレークポイント" lightbox="../../media/2020/06/breakpoints.msft.png":::
   <span data-ttu-id="74f35-265">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="74f35-265">Breakpoints</span></span>  
:::image-end:::  

<span data-ttu-id="74f35-266">Chromium の問題 [#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="74f35-266">Chromium issue [#1041830][CR1041830]</span></span>  

## <span data-ttu-id="74f35-267">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="74f35-267">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="74f35-268">Windows または macOS を使用している場合は、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="74f35-268">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="74f35-269">プレビュー チャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="74f35-269">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="74f35-270">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="74f35-270">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する | Microsoft Docs"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - Microsoft Edge DevTools のカスタマイズ | Microsoft Docs"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "試験的な機能を有効にする - 試験的な機能 | Microsoft Docs"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "Microsoft Edge DevTools の問題を見つけて解決するツール | Microsoft Docs"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "CSS と JavaScript を編集する - [ソース] パネルの概要 | Microsoft Docs"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワーク アクティビティをログに記録する - Microsoft Edge DevTools でネットワーク アクティビティを検査する | Microsoft Docs"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS-in-JS フレームワークのスタイルの編集 | CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "重複メッセージをコンソールに送信する | CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS グリッドプランナーの例 | CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR772558]: https://crbug.com/772558 "DevTools: 最新バージョンの Lighthouse を更新する | Chromium のバグ"  
[CR800028]: https://crbug.com/800028 "Chrome の更新後に、開発者ツール エディターの重複した行のショートカットが機能しない | Chromium のバグ"  
[CR912581]: https://crbug.com/912581 "V8 によってコードがキャッシュされたスクリプトが DevTools/about: tracing に公開される | Chromium のバグ"  
[CR946975]: https://crbug.com/946975 "DevTools のスタイル サイドバーが Constructable Stylesheets で機能しない | Chromium のバグ"  
[CR955497]: https://crbug.com/955497 "PWA のアプリ アイコン ショートカット メニュー | Chromium のバグ"  
[CR974550]: https://crbug.com/974550 "[パフォーマンス] パネルと performanceObserver 間の指標の不一致 | Chromium のバグ"  
[CR1041830]: https://crbug.com/1041830 "ブレークポイントの色を改善する | Chromium のバグ"  
[CR1055875]: https://crbug.com/1055875 "開発者ツールを終了してもう一度開いたとき、コンソールの設定で指定した [選択したコンテキストのみ] の値が保持されない | Chromium のバグ"  
[CR1066579]: https://crbug.com/1066579 "DevTools: [ネットワーク] パネルで要求ごとに ServiceWorkers フェッチ タイムラインを表示する | Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic 開発者のエクスペリエンス | Chromium のバグ"  
[CR1073899]: https://crbug.com/1073899 "計算済みのスタイル タブが応答モードで表示されない | Chromium のバグ"  
[CR1073903]: https://crbug.com/1073903 "DevTools: 構文の強調表示がプライベート フィールドで使用できない | Chromium のバグ"  
[CR1082963]: https://crbug.com/1082963 "コンソールの類似メッセージのグループ化の動作を無効にできない | Chromium のバグ"  
[CR1083214]: https://crbug.com/1083214 "acorn で optional chaining がサポートされない | Chromium のバグ"  
[CR1083797]: https://crbug.com/1083797 "nullish 合体演算子が整形出力されない | Chromium のバグ"  
[CR1096008]: https://crbug.com/1096008 "FMP を削除 | Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/フレキシブル ボックス/テーブル ツール | Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "統合ネットワーク要求を作成および再生するためのツールを作成する | Chromium のバグ"  
[CR1070378]: https://crbug.com/1070378 "DevTools に webhint を統合する | Chromium のバグ"  
[CR1069404]: https://crbug.com/1069404 "DevTools ウィジェットのポップアップがすべて狭すぎる | Chromium のバグ"  
[CR897944]: https://crbug.com/897944 "ドラッグ可能な DevTools パネル | Chromium のバグ"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題 - Microsoft Docs/Edge Developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "Shadow DOM を使用する | MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge プレビュー チャネル"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studio Code"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS オブジェクトモデル (CSSOM) | W3C CSS ワーキング グループ エディター ドラフト"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "プライベート クラス フィールド - パブリック クラスとプライベート クラスのフィールド | V8.Dev"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "JavaScript 開発者向けのコード キャッシュ | V8.Dev"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish 合体 | V8.Dev"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "Optional chaining | V8.Dev"  

[WebhintMain]: https://webhint.io "webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "Constructable Stylesheet オブジェクト | Web Incubator CG"

<!--[WebDevLighthouseWhatsNew60]: https://web.dev/lighthouse-whats-new-6.0 "What's New in Lighthouse 6.0 | Web.Dev"  -->  
<!--[WebDevVitalsCoreWeb]: https://web.dev/vitals#core-web-vitals "Core Web Vitals - Web Vitals | Web.Dev"  -->  
<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebFundamentalComponentsShadowdom]: /web/fundamentals/web-components/shadowdom  -->  
<!--[WebDevLcp]: https://web.dev/lcp "Largest Contentful Paint (LCP) | Web.Dev"  -->  
<!--[WebDevFirstMeaningfulPaint]: https://web.dev/first-meaningful-paint "First Meaningful Paint | Web.Dev"  -->  
<!--[WhatsNew201902ConstructableStylesheets]: ../../2019/02/constructable-stylesheets.md "Constructable Stylesheets: seamless reusable styles | Microsoft Docs"  -->  

[TheWebWeWant]: https://webwewant.fyi/ "必要とされる Web"  

> [!NOTE]
> <span data-ttu-id="74f35-319">このページの一部は、[Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更であり、「[Creative Commons Attribution 4.0 International License][CCA4IL]」に記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="74f35-319">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="74f35-320">[Jecelyn Yeen][JecelynYeen] (デベロッパー アドボケイト、Chrome DevTools) によって作成された元のページは、[こちら](https://developers.google.com/web/updates/2020/06/devtools/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="74f35-320">The original page is found [here](https://developers.google.com/web/updates/2020/06/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="74f35-322">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="74f35-322">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
