---
description: CSS グリッドのデバッグ機能、ネットワーク コンソールを使った要求の編集と再生など。
title: DevTools の新機能 (Microsoft Edge 85)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 9031f817a6079f64352c261a70eb9581213bf8c7
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408319"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-85"></a><span data-ttu-id="5d3f1-104">DevTools の新機能 (Microsoft Edge 85)</span><span class="sxs-lookup"><span data-stu-id="5d3f1-104">What's New In DevTools (Microsoft Edge 85)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="5d3f1-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="5d3f1-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="5d3f1-106">以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="5d3f1-107">DevTools、Microsoft コード拡張機能、その他の新機能を試Visual Studioお知らせをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="5d3f1-108">開発者ツールの最新で最良の機能について最新情報を入手するには、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]をダウンロードして、[Twitter で Microsoft Edge DevTools チームをフォローしますます][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="css-grid-debugging-features"></a><span data-ttu-id="5d3f1-109">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="5d3f1-109">CSS grid debugging features</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   <span data-ttu-id="5d3f1-111">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="5d3f1-111">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-112">Microsoft Edge DevTools チームは、Chrome DevTools チームと Chromium コミュニティと連携して、新しい CSS グリッドのデバッグ機能を DevTools に追加しています。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-112">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span></span>  <span data-ttu-id="5d3f1-113">現在、グリッド線の番号、グリッドのギャップ、拡張グリッド線をページ上にオーバーレイとして表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-113">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span></span>  <span data-ttu-id="5d3f1-114">さらに、グリッド ツールのさらなる改善が間もなく提供されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-114">Plus, more improvements to the grid tools are coming soon.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   <span data-ttu-id="5d3f1-116">CSS グリッドのデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="5d3f1-116">CSS grid debugging features</span></span>
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5d3f1-117">実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOn]を有効にする] に移動し、[新しい CSS グリッド デバッグ機能を有効にする] の横にある**チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-117">To enable the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span></span>  
> 
> <span data-ttu-id="5d3f1-118">サンプルを使用して実験を試す場合は [、CSS グリッド プランナーの例に移動します][CodepenRachelweilYzwBzKM]。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-118">To try out the experiment with a sample, navigate to [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span></span>  

<span data-ttu-id="5d3f1-119">Chromium の問題 [#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-119">Chromium issue [#1047356][CR1047356]</span></span>  

### <a name="edit-and-replay-requests-with-the-network-console"></a><span data-ttu-id="5d3f1-120">ネットワーク コンソールを使用して要求を編集および再生する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-120">Edit and Replay requests with the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   <span data-ttu-id="5d3f1-122">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="5d3f1-122">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-123">**ネットワーク コンソール**を使用して、[ネットワーク ログ][DevtoolsNetworkIndexLogActivity]の要求に対して**編集と再生**を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-123">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="ネットワーク コンソールを使用して NetworkLog で要求を編集して再生する" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   <span data-ttu-id="5d3f1-125">**ネットワーク コンソール**を使用して[NetworkLog][DevtoolsNetworkIndexLogActivity]で要求を編集して再生する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-125">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-126">新しいパネルとして、[DevTools のドロワー][DevtoolsCustomizeIndexDrawer]に **[ネットワーク コンソール]** が開き、HTTP 要求の情報が自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-126">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span></span>  <span data-ttu-id="5d3f1-127">サーバーから返される応答を表示するには、要求 \(必要な場合は\) を編集し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-127">To display the response returned from the server, edit the request \(if needed\) and select **Send**.</span></span>  

<span data-ttu-id="5d3f1-128">また、**[ネットワーク コンソール]** を使用して、DevTools から直接 HTTP 要求を作成して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-128">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="[ネットワーク コンソール] パネル" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   <span data-ttu-id="5d3f1-130">**[ネットワーク コンソール]** パネル</span><span class="sxs-lookup"><span data-stu-id="5d3f1-130">The **Network Console** panel</span></span>  
:::image-end:::  

> [!TIP]
> <span data-ttu-id="5d3f1-131">[DevTools][DevtoolsCustomizeIndexDrawer]**ドロ**ワーの代わりにメインの \(top\) パネルにネットワーク コンソールを表示するには、パネル間で[ツールを移動するに移動します](#move-tools-between-panels)。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-131">To display **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], navigate to [moving tools between panels](#move-tools-between-panels).</span></span>  

> [!NOTE]
> <span data-ttu-id="5d3f1-132">実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOn]を有効にする] に移動し、[ネットワーク コンソールを有効にする] の横にある**チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-132">To enable the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and choose the checkbox next to **Enable Network Console**.</span></span>  
> 
> <span data-ttu-id="5d3f1-133">ネットワーク ログ [を開き、][DevtoolsNetworkIndexLogActivity]コンテキスト メニュー \(右クリック\) を開き、[編集] と [再生] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-133">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  

<span data-ttu-id="5d3f1-134">Chromium の問題 [#1093687][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-134">Chromium issue [#1093687][CR1093687]</span></span>  

### <a name="service-worker-respondwith-events-in-the-timing-tab"></a><span data-ttu-id="5d3f1-135">[タイミング] タブのサービス ワーカーのrespondWith イベント</span><span class="sxs-lookup"><span data-stu-id="5d3f1-135">Service worker respondWith events in the Timing tab</span></span>  

<span data-ttu-id="5d3f1-136">ネットワーク **ツールの [** タイミング] **タブに** サービス ワーカー `respondWith` イベントが含まれる。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-136">The **Timing** tab of the **Network** tool now includes `respondWith` service worker events.</span></span>  <span data-ttu-id="5d3f1-137">`respondWith`サービス ワーカー イベントは、サービス ワーカー `fetch` イベント ハンドラーの実行が開始される直前から、`respondWith` ハンドラーの `fetch` Promise が解決されるまでの期間を示します。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-137">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="[ネットワーク] パネルの [タイミング] タブ内の respondWith サービス ワーカー イベント" lightbox="../../media/2020/06/timing-tab.msft.png":::
   <span data-ttu-id="5d3f1-139">ネットワーク `respondWith` ツールの [タイミング]**タブ**のサービス ワーカー イベント</span><span class="sxs-lookup"><span data-stu-id="5d3f1-139">The `respondWith` service worker event in the **Timing** tab of the **Network** tool</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-140">[受信 **した応答] を** 展開して、応答からの追加情報 `fetch` `CacheStorageCacheName` を表示 `serviceWorkerResponseSource` します `ResponseTime` 。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-140">Expand **Response received** to display additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="受信した応答を展開して、フェッチ応答からの追加情報を表示する" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   <span data-ttu-id="5d3f1-142">[受信 **した応答] を** 展開して、応答からの追加情報を表示 `fetch` する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-142">Expand **Response received** to display additional information from the `fetch` response</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-143">Chromium の問題 [#1066579][CR1066579]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-143">Chromium issue [#1066579][CR1066579]</span></span>  

### <a name="webhint-feedback-in-the-issues-panel"></a><span data-ttu-id="5d3f1-144">[問題] パネル内の webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5d3f1-144">webhint feedback in the Issues panel</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   <span data-ttu-id="5d3f1-146">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="5d3f1-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-147">[webhint][WebhintMain] は、アクセシビリティ、ブラウザ間の互換性、セキュリティ、パフォーマンス、PWA、および Web サイトの他の一般的な Web 開発の問題に関するリアルタイムのフィードバックを提供するオープン ソース ツールです。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-147">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="5d3f1-148">[問題] パネルで webhint フィードバック [を確認][DevtoolsIssues] するには。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-148">To review webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   <span data-ttu-id="5d3f1-150">[問題] パネル内の webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5d3f1-150">webhint feedback in the Issues panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5d3f1-151">実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOn]を有効にする] に移動し、[Webhint を有効にする] の横にあるチェック ボックス**をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-151">To enable the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and choose the checkbox next to **Enable webhint**.</span></span>  
> 
> <span data-ttu-id="5d3f1-152">[問題 [] パネルを開][DevtoolsIssues] き、webhint からのフィードバックを表示します。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-152">Open the [Issues][DevtoolsIssues] panel to display feedback from webhint.</span></span>  

<span data-ttu-id="5d3f1-153">Chromium の問題 [#1070378][CR1070378]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-153">Chromium issue [#1070378][CR1070378]</span></span>  

### <a name="move-tools-between-panels"></a><span data-ttu-id="5d3f1-154">パネル間でツールを移動する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-154">Move tools between panels</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   <span data-ttu-id="5d3f1-156">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="5d3f1-156">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-157">通常、**要素**や**ネットワーク**などのツールは、DevTools のメイン (上部) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-157">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="5d3f1-158">同様に、**3D ビュー**や**問題**などのツールは、DevTools のドロワー (下部) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-158">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="5d3f1-159">現在、上と下のパネル間でツールを移動して、DevTools のレイアウトをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-159">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="パネル間でツールを移動する" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   <span data-ttu-id="5d3f1-161">パネル間でツールを移動する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-161">Move tools between panels</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5d3f1-162">実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOn]を有効にする] に移動し、[パネル間でタブを移動するサポートを有効にする] の横にある**チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-162">To enable the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and choose the checkbox next to **Enable support to move tabs between panels**.</span></span>  

<span data-ttu-id="5d3f1-163">Chromium の問題 [#897944][CR897944]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-163">Chromium issue [#897944][CR897944]</span></span>  

### <a name="improved-initiator-tooltip-in-the-network-panel"></a><span data-ttu-id="5d3f1-164">[ネットワーク] パネルでのイニシエーターのヒントの改善</span><span class="sxs-lookup"><span data-stu-id="5d3f1-164">Improved Initiator tooltip in the Network panel</span></span>  

<span data-ttu-id="5d3f1-165">Microsoft Edge 83 および 84 では、[イニシエーター] 列にヒントが表示されます。これにより、[ネットワーク ログ][DevtoolsNetworkIndexLogActivity]には、水平スクロールバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-165">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span></span>  <span data-ttu-id="5d3f1-166">ツールヒントで水平方向にスクロールすることで、要求を開始した呼び出し履歴のみを表示できたのです。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-166">You were only able to display the call stack that initiated the request by scrolling horizontally in the tooltip.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   <span data-ttu-id="5d3f1-168">Microsoft Edge 84 のイニシエーターのヒント</span><span class="sxs-lookup"><span data-stu-id="5d3f1-168">The Initiator tooltip in Microsoft Edge 84</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-169">Microsoft Edge 85 から、水平方向にスクロールすることなく、イニシエーター呼び出し履歴をツールヒントに表示できます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-169">Starting with Microsoft Edge 85, you are now able to display the Initiator call stack in the tooltip without scrolling horizontally.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   <span data-ttu-id="5d3f1-171">Microsoft Edge 85 のイニシエーターのヒント</span><span class="sxs-lookup"><span data-stu-id="5d3f1-171">The Initiator tooltip in Microsoft Edge 85</span></span>
:::image-end:::  

<span data-ttu-id="5d3f1-172">Chromium の問題 [#1069404][CR1069404]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-172">Chromium issue [#1069404][CR1069404]</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="5d3f1-173">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="5d3f1-173">Announcements from the Chromium project</span></span>  

<span data-ttu-id="5d3f1-174">次のセクションでは、オープン ソースの Chromium プロジェクトに寄与した Microsoft Edge 85 で利用できるその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-174">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span></span>  

### <a name="style-editing-for-css-in-js-frameworks"></a><span data-ttu-id="5d3f1-175">CSS-in-JS フレームワークのスタイルの編集</span><span class="sxs-lookup"><span data-stu-id="5d3f1-175">Style editing for CSS-in-JS frameworks</span></span>  

<span data-ttu-id="5d3f1-176">**[スタイル]** ウィンドウで、[CSS オブジェクトモデル (CSSOM)][CsswgDraftsCssom] API を使って作成されたスタイルの編集がより適切にサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-176">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span></span>  <span data-ttu-id="5d3f1-177">多くの CSS-in-JS フレームワークとライブラリは、内部で CSSOM API を使ってスタイルを構築します。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-177">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span></span>  

<span data-ttu-id="5d3f1-178">現在、[Constructable Stylesheets][WicgConstructStylesheet] を使って、JavaScript で追加されたスタイルを編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-178">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span></span>  <span data-ttu-id="5d3f1-179">Constructable Stylesheets は、[Shadow DOM][MdnShadowDom]を使用するときに、再利用可能なスタイルを作成して配布するための新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-179">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span></span>  

<span data-ttu-id="5d3f1-180">たとえば、`CSSStyleSheet` (CSSOM API) で追加された `h1` スタイルは、以前は編集できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-180">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span></span>  <span data-ttu-id="5d3f1-181">スタイルは、[スタイル] パネルで **編集可能** になります。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-181">The styles are editable now in the **Styles** panel.</span></span>  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="CSSStyleSheet で追加された h1 スタイルの background プロパティをピンクからライトブルーに変更する" lightbox="../../media/2020/06/css-in-js.msft.png":::
   <span data-ttu-id="5d3f1-183">`CSSStyleSheet` で追加された `h1` スタイルの `background` プロパティを `pink` から `lightblue` に変更します。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-183">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span></span>
:::image-end:::  

<span data-ttu-id="5d3f1-184">この機能は、[CSS-in-JS を使用するサンプル][CodepenZoherghadyaliAbdgrpz]で試すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-184">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span></span>

<span data-ttu-id="5d3f1-185">Chromium の問題 [#946975][CR946975]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-185">Chromium issue [#946975][CR946975]</span></span>  

### <a name="lighthouse-6-in-the-lighthouse-panel"></a><span data-ttu-id="5d3f1-186">[Lighthouse] パネルの Lighthouse 6</span><span class="sxs-lookup"><span data-stu-id="5d3f1-186">Lighthouse 6 in the Lighthouse panel</span></span>  

<span data-ttu-id="5d3f1-187">**[Lighthouse]** パネルは、現在 Lighthouse 6 を実行しています。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-187">The **Lighthouse** panel is now running Lighthouse 6.</span></span>  <span data-ttu-id="5d3f1-188">すべての変更の完全な一覧については [、v6.0.0][GithubGoogleChromeLighthouse600]リリース ノートに移動します。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-188">For a full list of all changes, navigate to [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span></span>  

<span data-ttu-id="5d3f1-189">Lighthouse 6.0 では、レポートに 3 つの新しい指標が導入されています。最大コンテンツのペイント (LCP)、累積レイアウト シフト (CLS)、および合計ブロッキング時間 (TBT) です。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-189">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span></span>  

<span data-ttu-id="5d3f1-190">また、パフォーマンス スコアの計算式も再重み付けされ、ユーザーの読み込み操作がより適切に反映されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-190">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span></span>  

<span data-ttu-id="5d3f1-191">Chromium の問題 [#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-191">Chromium issue [#772558][CR772558]</span></span>  

#### <a name="first-meaningful-paint-deprecation"></a><span data-ttu-id="5d3f1-192">First Meaningful Paint の廃止</span><span class="sxs-lookup"><span data-stu-id="5d3f1-192">First Meaningful Paint deprecation</span></span>  

<span data-ttu-id="5d3f1-193">Lighthouse 6.0 では、最初の意味のあるペイント (FMP) が廃止されました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-193">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span></span>  <span data-ttu-id="5d3f1-194">FMP は、**[パフォーマンス]** パネルからも削除されています。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-194">FMP has also been removed from the **Performance** panel.</span></span>  <span data-ttu-id="5d3f1-195">**最大コンテンツのペイント**が、推奨される FMP の代替機能です。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-195">**Largest Contentful Paint** is the recommended replacement for FMP.</span></span>  <!--For an explanation of why it was deprecated, navigate to [First Meaningful Paint][WebDevFirstMeaningfulPaint].  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

<span data-ttu-id="5d3f1-196">Chromium の問題 [#1096008][CR1096008]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-196">Chromium issue [#1096008][CR1096008]</span></span>  

### <a name="support-for-new-javascript-features"></a><span data-ttu-id="5d3f1-197">新しい JavaScript 機能のサポート</span><span class="sxs-lookup"><span data-stu-id="5d3f1-197">Support for new JavaScript features</span></span>  

<span data-ttu-id="5d3f1-198">DevTools では、最新の JavaScript 言語機能の一部がより適切にサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-198">DevTools now has better support for some of the latest JavaScript language features.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="5d3f1-199">[optional chaining][V8DevOptionalChaining] 構文のオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="5d3f1-199">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5d3f1-200">**コンソール**内のプロパティのオートコンプリート機能により、optional chaining 構文がサポートされるようになりました。たとえば、`name.` と `name[` に加えて、`name?.` も使えます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-200">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="5d3f1-201">[プライベート フィールド][V8DevClassFieldsPrivate]の構文の強調表示</span><span class="sxs-lookup"><span data-stu-id="5d3f1-201">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5d3f1-202">プライベート クラスのフィールドが、**[ソース]** パネルで適切に強調表示され、整形出力されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-202">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="5d3f1-203">[Nullish 合体演算子][V8DevNullishCoalescing]の構文の強調表示</span><span class="sxs-lookup"><span data-stu-id="5d3f1-203">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5d3f1-204">**[ソース]** パネルで nullish 合体演算子が整形出力されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-204">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="5d3f1-205">Chromium の問題 [#1073903][CR1073903]、 [#1083214][CR1083214]、 [#1083797][CR1083797]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-205">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span></span>  

### <a name="new-app-shortcut-warnings-in-the-manifest-pane"></a><span data-ttu-id="5d3f1-206">[マニフェスト] ウィンドウでの新しいアプリのショートカットの警告</span><span class="sxs-lookup"><span data-stu-id="5d3f1-206">New app shortcut warnings in the Manifest pane</span></span>  

<span data-ttu-id="5d3f1-207">**アプリのショートカット** を使用すると、Web アプリ内で一般的または推奨されるタスクをすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-207">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span></span>  

<!--todo: add App shortcuts when section is live  -->  

<span data-ttu-id="5d3f1-208">**[マニフェスト]** ウィンドウには、次の条件の警告が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-208">The **Manifest** pane now shows warnings for the following conditions.</span></span>  

* <span data-ttu-id="5d3f1-209">アプリのショートカット アイコンが 96 x 96 ピクセルより小さい</span><span class="sxs-lookup"><span data-stu-id="5d3f1-209">The app shortcut icons are smaller than 96x96 pixels</span></span>  
* <span data-ttu-id="5d3f1-210">アプリのショートカット アイコンとマニフェスト アイコンが四角形でない (アイコンが無視されているため)</span><span class="sxs-lookup"><span data-stu-id="5d3f1-210">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span></span>  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="アプリのショートカットの警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   <span data-ttu-id="5d3f1-212">アプリのショートカットの警告</span><span class="sxs-lookup"><span data-stu-id="5d3f1-212">App shortcut warnings</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-213">Chromium の問題 [#955497][CR955497]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-213">Chromium issue [#955497][CR955497]</span></span>  

### <a name="consistent-display-of-the-computed-pane"></a><span data-ttu-id="5d3f1-214">[計算済み] ウィンドウの一貫性のある表示</span><span class="sxs-lookup"><span data-stu-id="5d3f1-214">Consistent display of the Computed pane</span></span>  

<span data-ttu-id="5d3f1-215">[ **要素] ツールの** [計算] **ウィンドウ** が、すべてのビューポート サイズにわたって一貫してウィンドウとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-215">The **Computed** pane in the **Elements** tool now displays consistently as a pane across all viewport sizes.</span></span>  <span data-ttu-id="5d3f1-216">以前は、DevTools ビューポートの幅が狭い場合、**[計算済み]** ウィンドウは、**[スタイル]** ウィンドウ内にマージされました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-216">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span></span>  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="DevTools の幅が狭い場合でも、[計算済み] ウィンドウは個別のウィンドウとして表示されます" lightbox="../../media/2020/06/computed-pane.msft.png":::
   <span data-ttu-id="5d3f1-218">DevTools の幅が狭い場合でも、**[計算済み]** ウィンドウは個別のウィンドウとして常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-218">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span></span>
:::image-end:::  

<span data-ttu-id="5d3f1-219">Chromium の問題 [#1073899][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-219">Chromium issue [#1073899][CR1073899]</span></span>  

### <a name="bytecode-offsets-for-webassembly-files"></a><span data-ttu-id="5d3f1-220">WebAssembly ファイルのバイトコード オフセット</span><span class="sxs-lookup"><span data-stu-id="5d3f1-220">Bytecode offsets for WebAssembly files</span></span>  

<span data-ttu-id="5d3f1-221">DevTools は、Wasm 逆アセンブルの行番号を表示するためにバイトコード オフセットを使用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-221">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span></span>  
<span data-ttu-id="5d3f1-222">行番号によって、バイナリデータを見ていることが明確になり、Wasm ランタイムが場所を参照する方法に一貫性が保たれます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-222">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span></span>  

<span data-ttu-id="5d3f1-223">Chromium の問題 [#1071432][CR1071432]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-223">Chromium issue [#1071432][CR1071432]</span></span>  

### <a name="line-wise-copy-and-cut-in-sources-panel"></a><span data-ttu-id="5d3f1-224">[ソース] パネルでの行ごとのコピーと切り取り</span><span class="sxs-lookup"><span data-stu-id="5d3f1-224">Line-wise copy and cut in Sources Panel</span></span>  

<span data-ttu-id="5d3f1-225">[ソース パネル エディター][DevtoolsSourcesEditCssJavascript]で選択なしでコピーまたは切り取りを実行すると、現在のコンテンツの行がコピーまたは切り取りられます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-225">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesEditCssJavascript], DevTools copies or cuts the current line of content.</span></span>  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="カーソルが 5 行目の最後にある状態で、DevTools の pen.js から行全体をコピーして、Visual Studio Code に貼り付けます。" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   <span data-ttu-id="5d3f1-227">カーソルが 5 行目の最後にある状態で、DevTools の **pen.js** から行全体をコピーして、[Visual Studio Code][VisualStudioCode] に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-227">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [Visual Studio Code][VisualStudioCode].</span></span>
:::image-end:::  

<span data-ttu-id="5d3f1-228">Chromium の問題 [#800028][CR800028]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-228">Chromium issue [#800028][CR800028]</span></span>

### <a name="console-settings-updates"></a><span data-ttu-id="5d3f1-229">コンソールの設定の更新</span><span class="sxs-lookup"><span data-stu-id="5d3f1-229">Console Settings updates</span></span>  

#### <a name="ungroup-same-console-messages"></a><span data-ttu-id="5d3f1-230">同じコンソールのメッセージをグループ解除する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-230">Ungroup same console messages</span></span>  

<span data-ttu-id="5d3f1-231">コンソールの設定の **[類似のグループ化]** 切り替えが、重複するメッセージに適用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-231">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span></span>  <span data-ttu-id="5d3f1-232">以前は単に類似のメッセージに適用されていました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-232">Previously it just applied to similar messages.</span></span>  

<span data-ttu-id="5d3f1-233">たとえば、以前は、**[類似のグループ化]** がオフになっている場合でも、`hello` メッセージはグループ解除されませんでした。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-233">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span></span>  <span data-ttu-id="5d3f1-234">現在、`hello` メッセージはグループ解除されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-234">Now, the `hello` messages are ungrouped.</span></span>  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="[類似のグループ化] がオフの場合、hello メッセージはグループ解除されます。" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   <span data-ttu-id="5d3f1-236">**[類似のグループ化]** がオフの場合、`hello` メッセージはグループ解除されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-236">When **Group similar** is unchecked, the `hello` messages are ungrouped</span></span>
:::image-end:::  

<span data-ttu-id="5d3f1-237">この機能は、[コンソールに重複したメッセージを送信するサンプル][CodepenZoherghadyaliZyrjgdJ]で試すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-237">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span></span>  

<span data-ttu-id="5d3f1-238">Chromium の問題 [#1082963][CR1082963]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-238">Chromium issue [#1082963][CR1082963]</span></span>  

### <a name="persisting-selected-context-only-settings"></a><span data-ttu-id="5d3f1-239">選択されたコンテキストのみの設定を保持する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-239">Persisting Selected context only settings</span></span>  

<span data-ttu-id="5d3f1-240">コンソールの設定で **[選択されたコンテキストのみ]** の設定が保持されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-240">The **Selected context only** settings in Console Settings is now persisted.</span></span>  <span data-ttu-id="5d3f1-241">以前は、DevTools を閉じてもう一度開くたびに、設定はリセットされました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-241">Previously the settings were reset every time you closed and reopened DevTools.</span></span>  <span data-ttu-id="5d3f1-242">この変更により、設定の動作が他のコンソールの設定オプションと一致するようになります。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-242">The change makes the setting behavior consistent with other Console Settings options.</span></span>  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="[選択されたコンテキストのみ] の設定" lightbox="../../media/2020/06/selected-context.msft.png":::
   <span data-ttu-id="5d3f1-244">**[選択されたコンテキストのみ]** の設定</span><span class="sxs-lookup"><span data-stu-id="5d3f1-244">**Selected context only** setting</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-245">Chromium の問題 [#1055875][CR1055875]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-245">Chromium issue [#1055875][CR1055875]</span></span>  

### <a name="performance-panel-updates"></a><span data-ttu-id="5d3f1-246">[パフォーマンス] パネルの更新</span><span class="sxs-lookup"><span data-stu-id="5d3f1-246">Performance panel updates</span></span>  

#### <a name="javascript-compilation-cache-information-in-performance-tool"></a><span data-ttu-id="5d3f1-247">パフォーマンス ツールの JavaScript コンパイル**キャッシュ情報**</span><span class="sxs-lookup"><span data-stu-id="5d3f1-247">JavaScript compilation cache information in **Performance** tool</span></span>  

<span data-ttu-id="5d3f1-248">[JavaScript のコンパイル キャッシュ情報][V8DevCodeCaching] は、パフォーマンス ツールの **[概要** ] パネルに常に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-248">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the **Summary** panel of the **Performance** tool.</span></span>  <span data-ttu-id="5d3f1-249">以前は、コード キャッシュが行われなかった場合、DevTools でコード キャッシュに関連するものは表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-249">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span></span>  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript コンパイルキャッシュ情報" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   <span data-ttu-id="5d3f1-251">JavaScript コンパイルキャッシュ情報</span><span class="sxs-lookup"><span data-stu-id="5d3f1-251">JavaScript compilation cache information</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-252">Chromium の問題 [#912581][CR912581]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-252">Chromium issue [#912581][CR912581]</span></span>  

#### <a name="navigation-timing-alignment-in-the-performance-panel"></a><span data-ttu-id="5d3f1-253">[パフォーマンス] パネルでの移動のタイミングの調整</span><span class="sxs-lookup"><span data-stu-id="5d3f1-253">Navigation timing alignment in the Performance panel</span></span>  

<span data-ttu-id="5d3f1-254">**[パフォーマンス]** パネルでは、記録が開始された時間に基づいてルーラーに時間が表示されていました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-254">The **Performance** panel used to show times in the rulers based on when the recording started.</span></span>  <span data-ttu-id="5d3f1-255">現在、タイミングはユーザーが移動する記録に変更され、移動に関連するルーラー時間が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-255">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span></span>  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="パフォーマンス ツールでナビゲーションのタイミングを調整する" lightbox="../../media/2020/06/nav-timing.msft.png":::
   <span data-ttu-id="5d3f1-257">パフォーマンス ツールでナビゲーションのタイミング **を調整** する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-257">Align navigation timing in **Performance** tool</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-258">`DOMContentLoaded`、First Paint (最初のペイント)、First Contentful Paint (最初のコンテンツのペイント)、最大コンテンツのペイント (Largest Contentful Paint) の各イベントの時間は、移動の開始からの相対的な時間に更新されます。つまり、タイミングは、`PerformanceObserver` によって報告されるタイミングと一致します。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-258">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span></span>  

<span data-ttu-id="5d3f1-259">Chromium の問題 [#974550][CR974550]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-259">Chromium issue [#974550][CR974550]</span></span>  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a><span data-ttu-id="5d3f1-260">ブレークポイント、条件付きブレークポイント、およびログポイントの新しいアイコン</span><span class="sxs-lookup"><span data-stu-id="5d3f1-260">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="5d3f1-261">**[ソース]** パネルには、ブレークポイント、条件付きブレークポイント、およびログポイントの新しいデザインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-261">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span></span>  <span data-ttu-id="5d3f1-262">ブレークポイントは、[Visual Studio Code][VisualStudioCode] と [Visual Studio][VisualStudio]と同様に、赤い円で表されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-262">Breakpoints are represented by a red circle, just like [Visual Studio Code][VisualStudioCode] and [Visual Studio][VisualStudio].</span></span>  <span data-ttu-id="5d3f1-263">条件付きブレークポイントとログポイントを区別するためにアイコンが追加されています。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-263">Icons are added to differentiate conditional breakpoints and logpoints.</span></span>  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="ブレークポイント" lightbox="../../media/2020/06/breakpoints.msft.png":::
   <span data-ttu-id="5d3f1-265">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="5d3f1-265">Breakpoints</span></span>  
:::image-end:::  

<span data-ttu-id="5d3f1-266">Chromium の問題 [#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="5d3f1-266">Chromium issue [#1041830][CR1041830]</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="5d3f1-267">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="5d3f1-267">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="5d3f1-268">Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-268">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="5d3f1-269">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-269">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="5d3f1-270">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="5d3f1-270">Getting in touch with Microsoft Edge DevTools team</span></span>  

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

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"
[VisualStudioCode]: https://code.visualstudio.com/ "Visual Studio Code"  

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
> <span data-ttu-id="5d3f1-319">このページの一部は、[Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更であり、「[Creative Commons Attribution 4.0 International License][CCA4IL]」に記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-319">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5d3f1-320">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2020/06/devtools/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-320">The original page is found [here](https://developers.google.com/web/updates/2020/06/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5d3f1-322">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5d3f1-322">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
