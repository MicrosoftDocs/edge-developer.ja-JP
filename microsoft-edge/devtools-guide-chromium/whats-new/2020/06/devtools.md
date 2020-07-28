---
title: DevTools の新機能 (Microsoft Edge 85)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7b0193d25fb1d081e5746ec1271ca7b9f4e60c23
ms.sourcegitcommit: ad5eb43172280974b8c063867c2097f7c5c0e77d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "10898312"
---
# <span data-ttu-id="23deb-103">DevTools の新機能 (Microsoft Edge 85)</span><span class="sxs-lookup"><span data-stu-id="23deb-103">What's New In DevTools (Microsoft Edge 85)</span></span>  

## <span data-ttu-id="23deb-104">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="23deb-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="23deb-105">以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="23deb-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="23deb-106">このお知らせを参照して、DevTools、VS コード拡張などの新機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="23deb-106">See the announcements to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="23deb-107">開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft edge preview チャネル][MicrosoftEdgePreviewChannels]をダウンロードして、 [Twitter の Microsoft edge devtools チームに従い][EdgeDevToolsTwitterAccount]ます。</span><span class="sxs-lookup"><span data-stu-id="23deb-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="23deb-108">CSS grid のデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="23deb-108">CSS grid debugging features</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="23deb-110">実験的機能</span><span class="sxs-lookup"><span data-stu-id="23deb-110">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-111">Microsoft Edge DevTools チームは、Chrome DevTools チームと Chromium コミュニティと連携して、新しい CSS grid のデバッグ機能を DevTools に追加します。</span><span class="sxs-lookup"><span data-stu-id="23deb-111">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span></span>  <span data-ttu-id="23deb-112">これで、グリッド線の番号、グリッドのギャップ、拡張グリッド線をページ内のオーバーレイとして表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-112">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span></span>  <span data-ttu-id="23deb-113">さらに、グリッドツールの機能がさらに向上しました。</span><span class="sxs-lookup"><span data-stu-id="23deb-113">Plus, more improvements to the grid tools are coming soon.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS grid のデバッグ機能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   <span data-ttu-id="23deb-115">CSS grid のデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="23deb-115">CSS grid debugging features</span></span>
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="23deb-116">実験を有効にするには、「[実験的な機能を][DevtoolsExperimentalFeaturesTurnOn]有効にする」を参照し、[**新しい CSS グリッドのデバッグ機能を有効**にする] の横のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23deb-116">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span></span>  
> 
> <span data-ttu-id="23deb-117">サンプルを使って実験を試すには、「 [CSS グリッドプランナーの例][CodepenRachelweilYzwBzKM]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23deb-117">To try out the experiment with a sample, see [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span></span>  

<span data-ttu-id="23deb-118">Chromium の問題[#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="23deb-118">Chromium issue [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="23deb-119">ネットワークコンソールを使用して要求を編集および再生する</span><span class="sxs-lookup"><span data-stu-id="23deb-119">Edit and Replay requests with the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="23deb-121">実験的機能</span><span class="sxs-lookup"><span data-stu-id="23deb-121">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-122">ネットワーク**コンソール**を使用して、[ネットワークログ][DevtoolsNetworkIndexLogActivity]の要求に対して**編集と再生**を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-122">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="ネットワークコンソールを使用して NetworkLog で要求を編集して再生する" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   <span data-ttu-id="23deb-124">**ネットワークコンソール**を使用して[networklog][DevtoolsNetworkIndexLogActivity]で要求を編集して再生する</span><span class="sxs-lookup"><span data-stu-id="23deb-124">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-125">新しいパネルとして、[ [Devtools] ドロアー][DevtoolsCustomizeIndexDrawer]に**ネットワークコンソール**が開き、HTTP 要求の情報が自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-125">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span></span>  <span data-ttu-id="23deb-126">サーバーから返された応答を確認するには、要求を編集し (必要な場合)、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23deb-126">To see the response returned from the server, edit the request \(if needed\) and select **Send**.</span></span>  

<span data-ttu-id="23deb-127">また、**ネットワークコンソール**を使用して、devtools から直接 HTTP 要求を作成して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="23deb-127">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="ネットワークコンソールパネル" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   <span data-ttu-id="23deb-129">**ネットワークコンソール**パネル</span><span class="sxs-lookup"><span data-stu-id="23deb-129">The **Network Console** panel</span></span>  
:::image-end:::  

> [!TIP]
> <span data-ttu-id="23deb-130">[ [Devtools] ドロアー][DevtoolsCustomizeIndexDrawer]の代わりに、メインの \ (上部 \) パネルで**ネットワークコンソール**を表示するには、「[パネル間でのツールの移動](#move-tools-between-panels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23deb-130">To see **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], see [moving tools between panels](#move-tools-between-panels).</span></span>  

> [!NOTE]
> <span data-ttu-id="23deb-131">実験を有効にするには、「[実験的な機能を][DevtoolsExperimentalFeaturesTurnOn]有効にする」を参照し、[**ネットワーク本体を有効**にする] の横のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23deb-131">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable Network Console**.</span></span>  
> 
> <span data-ttu-id="23deb-132">[ネットワークログ][DevtoolsNetworkIndexLogActivity]を開き、コンテキストメニューを開き (\ を右クリック)、[**編集と再生**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23deb-132">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and select **Edit and Replay**.</span></span>  

<span data-ttu-id="23deb-133">Chromium の問題[#1093687][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="23deb-133">Chromium issue [#1093687][CR1093687]</span></span>  

### <span data-ttu-id="23deb-134">[タイミング] タブのイベントを使用したサービスワーカーの返信</span><span class="sxs-lookup"><span data-stu-id="23deb-134">Service worker respondWith events in the Timing tab</span></span>  

<span data-ttu-id="23deb-135">[**ネットワーク**] パネルの [**タイミング**] タブに、サービスワーカーイベントが表示されるようになりました `respondWith` 。</span><span class="sxs-lookup"><span data-stu-id="23deb-135">The **Timing** tab of the **Network** panel now includes `respondWith` service worker events.</span></span>  <span data-ttu-id="23deb-136">`respondWith`サービスワーカーイベントは、 `fetch` `respondWith` ハンドラーの promise が決済された時点までのサービスワーカーイベントハンドラーの開始時刻からの時間を示し `fetch` ます。</span><span class="sxs-lookup"><span data-stu-id="23deb-136">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="[ネットワーク] パネルの [タイミング] タブにある [サービスワーカーイベント]" lightbox="../../media/2020/06/timing-tab.msft.png":::
   <span data-ttu-id="23deb-138">[ `respondWith` **ネットワーク**] パネルの [**タイミング**] タブのサービスワーカーイベント</span><span class="sxs-lookup"><span data-stu-id="23deb-138">The `respondWith` service worker event in the **Timing** tab of the **Network** panel</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-139">[**返信の受信**] を展開して、、、、などの返信の追加情報を表示し `fetch` `CacheStorageCacheName` `serviceWorkerResponseSource` `ResponseTime` ます。</span><span class="sxs-lookup"><span data-stu-id="23deb-139">Expand **Response received** to see additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="[返信の受信] を展開して、フェッチ応答から追加情報を確認する" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   <span data-ttu-id="23deb-141">[**返信の受信**] を展開して、応答から追加情報を確認する `fetch`</span><span class="sxs-lookup"><span data-stu-id="23deb-141">Expand **Response received** to see additional information from the `fetch` response</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-142">Chromium の問題[#1066579][CR1066579]</span><span class="sxs-lookup"><span data-stu-id="23deb-142">Chromium issue [#1066579][CR1066579]</span></span>  

### <span data-ttu-id="23deb-143">[問題] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="23deb-143">webhint feedback in the Issues panel</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="23deb-145">実験的機能</span><span class="sxs-lookup"><span data-stu-id="23deb-145">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-146">[webhint][WebhintMain]は、アクセシビリティ、クロスブラウザーの互換性、セキュリティ、パフォーマンス、pwas、web サイトのその他の一般的な web 開発の問題に関するフィードバックをリアルタイムで提供するオープンソースツールです。</span><span class="sxs-lookup"><span data-stu-id="23deb-146">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="23deb-147">これで、[[問題][DevtoolsIssues]] パネルに webhint のフィードバックが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="23deb-147">You are now able to see webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   <span data-ttu-id="23deb-149">[問題] パネルでの webhint のフィードバック</span><span class="sxs-lookup"><span data-stu-id="23deb-149">webhint feedback in the Issues panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="23deb-150">実験を有効にするには、「[実験的な機能][DevtoolsExperimentalFeaturesTurnOn]を有効にする」を参照し、[ **Webhint を有効**にする] の横のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23deb-150">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable webhint**.</span></span>  
> 
> <span data-ttu-id="23deb-151">[[問題][DevtoolsIssues]] パネルを開いて、web ヒントからのフィードバックを表示します。</span><span class="sxs-lookup"><span data-stu-id="23deb-151">Open the [Issues][DevtoolsIssues] panel to see feedback from webhint.</span></span>  

<span data-ttu-id="23deb-152">Chromium の問題[#1070378][CR1070378]</span><span class="sxs-lookup"><span data-stu-id="23deb-152">Chromium issue [#1070378][CR1070378]</span></span>  

### <span data-ttu-id="23deb-153">パネル間の移動ツール</span><span class="sxs-lookup"><span data-stu-id="23deb-153">Move tools between panels</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   <span data-ttu-id="23deb-155">実験的機能</span><span class="sxs-lookup"><span data-stu-id="23deb-155">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-156">通常、**要素**や**ネットワーク**などのツールは、devtools のメイン \ (トップ) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="23deb-156">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="23deb-157">同様に、 **3D ビュー**や**問題**などのツールは、devtools のドローワ \ (ボトム \) パネルでのみ開くことができます。</span><span class="sxs-lookup"><span data-stu-id="23deb-157">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="23deb-158">これで、[上] と [下] パネルの間でツールを移動して、DevTools のレイアウトをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-158">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="パネル間でタブを移動する" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   <span data-ttu-id="23deb-160">パネル間でタブを移動する</span><span class="sxs-lookup"><span data-stu-id="23deb-160">Moving tabs between panels</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="23deb-161">実験を有効にするには、「[実験的な機能][DevtoolsExperimentalFeaturesTurnOn]を有効にする」のチェックボックスをオンにし、[**サポートを有効**にする] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23deb-161">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable support to move tabs between panels**.</span></span>  

<span data-ttu-id="23deb-162">Chromium の問題[#897944][CR897944]</span><span class="sxs-lookup"><span data-stu-id="23deb-162">Chromium issue [#897944][CR897944]</span></span>  

### <span data-ttu-id="23deb-163">[ネットワーク] パネルでのイニシエーターのヒントの改善</span><span class="sxs-lookup"><span data-stu-id="23deb-163">Improved Initiator tooltip in the Network panel</span></span>  

<span data-ttu-id="23deb-164">Microsoft Edge 83 および84では、[イニシエーター] 列のツールチップが表示されます。これにより、[ネットワークログ][DevtoolsNetworkIndexLogActivity]には、水平スクロールバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-164">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span></span>  <span data-ttu-id="23deb-165">要求を開始したコールスタックを表示できるのは、ヒントを水平方向にスクロールすることだけです。</span><span class="sxs-lookup"><span data-stu-id="23deb-165">You were only able to see the call stack that initiated the request by scrolling horizontally in the tooltip.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   <span data-ttu-id="23deb-167">Microsoft Edge 84 のイニシエーターのヒント</span><span class="sxs-lookup"><span data-stu-id="23deb-167">The Initiator tooltip in Microsoft Edge 84</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-168">Microsoft Edge 85 以降では、水平方向にスクロールしなくても、ツールヒントでイニシエーターのコールスタックを確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-168">Starting with Microsoft Edge 85, you are now able to see the Initiator call stack in the tooltip without scrolling horizontally.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   <span data-ttu-id="23deb-170">Microsoft Edge 85 のイニシエーターのヒント</span><span class="sxs-lookup"><span data-stu-id="23deb-170">The Initiator tooltip in Microsoft Edge 85</span></span>
:::image-end:::  

<span data-ttu-id="23deb-171">Chromium の問題[#1069404][CR1069404]</span><span class="sxs-lookup"><span data-stu-id="23deb-171">Chromium issue [#1069404][CR1069404]</span></span>  

## <span data-ttu-id="23deb-172">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="23deb-172">Announcements from the Chromium project</span></span>  

<span data-ttu-id="23deb-173">次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 85 で利用可能なその他の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="23deb-173">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="23deb-174">CSS イン JS フレームワークのスタイルの編集</span><span class="sxs-lookup"><span data-stu-id="23deb-174">Style editing for CSS-in-JS frameworks</span></span>  

<span data-ttu-id="23deb-175">[**スタイル**] ウィンドウで、 [CSS オブジェクトモデル (cssom)][CsswgDraftsCssom] api を使って作成されたスタイルの編集がさらにサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-175">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span></span>  <span data-ttu-id="23deb-176">CSS 内の多くのフレームワークとライブラリでは、内部の CSSOM Api を使ってスタイルを構築しています。</span><span class="sxs-lookup"><span data-stu-id="23deb-176">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span></span>  

<span data-ttu-id="23deb-177">構築した[表スタイルシート][WicgConstructStylesheet]を使って、JavaScript で追加したスタイルを編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-177">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span></span>  <span data-ttu-id="23deb-178">構築された表スタイルシートは、[シャドウ DOM][MdnShadowDom]を使用するときに、再利用可能なスタイルを作成して配布するための新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="23deb-178">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span></span>  

<span data-ttu-id="23deb-179">たとえば、 `h1` `CSSStyleSheet` \ (Cssom api \) で追加されたスタイルは、以前は編集できませんでした。</span><span class="sxs-lookup"><span data-stu-id="23deb-179">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span></span>  <span data-ttu-id="23deb-180">スタイルは、[**スタイル**] ウィンドウで編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-180">The styles are editable now in the **Styles** pane.</span></span>  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="CSSStyleSheet によって追加された h1 スタイルの background プロパティをピンクからライトブルーに変更する" lightbox="../../media/2020/06/css-in-js.msft.png":::
   <span data-ttu-id="23deb-182">`background` `h1` From からに追加されたスタイルのプロパティを変更 `CSSStyleSheet` `pink` `lightblue` します。</span><span class="sxs-lookup"><span data-stu-id="23deb-182">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span></span>
:::image-end:::  

<span data-ttu-id="23deb-183">この機能を試すには、 [CSS IN JS を使用するサンプル][CodepenZoherghadyaliAbdgrpz]が含まれています。</span><span class="sxs-lookup"><span data-stu-id="23deb-183">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span></span>

<span data-ttu-id="23deb-184">Chromium の問題[#946975][CR946975]</span><span class="sxs-lookup"><span data-stu-id="23deb-184">Chromium issue [#946975][CR946975]</span></span>  

### <span data-ttu-id="23deb-185">Lighthouse パネルの Lighthouse 6</span><span class="sxs-lookup"><span data-stu-id="23deb-185">Lighthouse 6 in the Lighthouse panel</span></span>  

<span data-ttu-id="23deb-186">**Lighthouse** panel は、現在 Lighthouse 6 を実行しています。</span><span class="sxs-lookup"><span data-stu-id="23deb-186">The **Lighthouse** panel is now running Lighthouse 6.</span></span>  <span data-ttu-id="23deb-187">すべての変更の一覧については、「 [v 6.0.0 のリリースノート][GithubGoogleChromeLighthouse600]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23deb-187">For a full list of all changes, see [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span></span>  

<span data-ttu-id="23deb-188">Lighthouse 6.0 は、レポートに最大3つの新しいメトリックを導入します。これは、最大 Contentful 塗料 (LCP \)、累積レイアウトシフト \ (CLS \)、ブロック時間の合計 (TBT \) です。</span><span class="sxs-lookup"><span data-stu-id="23deb-188">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span></span>  

<span data-ttu-id="23deb-189">また、パフォーマンススコアの計算式も再重み付けされ、ユーザーの読み込み操作がより適切に反映されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-189">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span></span>  

<span data-ttu-id="23deb-190">Chromium の問題[#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="23deb-190">Chromium issue [#772558][CR772558]</span></span>  

#### <span data-ttu-id="23deb-191">最初の有意義な塗料の廃止</span><span class="sxs-lookup"><span data-stu-id="23deb-191">First Meaningful Paint deprecation</span></span>  

<span data-ttu-id="23deb-192">Lighthouse 6.0 では、最初の有意義な塗料 \ (FMP \) は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="23deb-192">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span></span>  <span data-ttu-id="23deb-193">FMP は、**パフォーマンス**パネルからも削除されています。</span><span class="sxs-lookup"><span data-stu-id="23deb-193">FMP has also been removed from the **Performance** panel.</span></span>  <span data-ttu-id="23deb-194">**最大のコンテンツ**は、FMP に推奨される代替機能です。</span><span class="sxs-lookup"><span data-stu-id="23deb-194">**Largest Contentful Paint** is the recommended replacement for FMP.</span></span>  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

<span data-ttu-id="23deb-195">Chromium の問題[#1096008][CR1096008]</span><span class="sxs-lookup"><span data-stu-id="23deb-195">Chromium issue [#1096008][CR1096008]</span></span>  

### <span data-ttu-id="23deb-196">新しい JavaScript 機能のサポート</span><span class="sxs-lookup"><span data-stu-id="23deb-196">Support for new JavaScript features</span></span>  

<span data-ttu-id="23deb-197">DevTools では、最新の JavaScript 言語機能の一部がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-197">DevTools now has better support for some of the latest JavaScript language features.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="23deb-198">[オプションのチェーン][V8DevOptionalChaining]構文のオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="23deb-198">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="23deb-199">**コンソール**内のプロパティのオートコンプリート機能により、オプションのチェーン構文がサポートされるようになりました。たとえば、との組み合わせ `name?.` でも動作するようになりました `name.` `name[` 。</span><span class="sxs-lookup"><span data-stu-id="23deb-199">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="23deb-200">[プライベートフィールド][V8DevClassFieldsPrivate]の構文強調表示</span><span class="sxs-lookup"><span data-stu-id="23deb-200">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="23deb-201">プライベートクラスのフィールドが適切に強調表示されるようになり、[**ソース**] パネルできれいに印刷されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-201">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="23deb-202">[Nullish 合体演算子][V8DevNullishCoalescing]の構文の強調表示</span><span class="sxs-lookup"><span data-stu-id="23deb-202">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="23deb-203">DevTools では、[**ソース**] パネルで nullish 合体演算子が適切に印刷されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-203">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="23deb-204">Chromium の問題[#1073903][CR1073903]、 [#1083214][CR1083214]、 [#1083797][CR1083797]</span><span class="sxs-lookup"><span data-stu-id="23deb-204">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span></span>  

### <span data-ttu-id="23deb-205">[マニフェスト] ウィンドウでの新しいアプリのショートカットの警告</span><span class="sxs-lookup"><span data-stu-id="23deb-205">New app shortcut warnings in the Manifest pane</span></span>  

<span data-ttu-id="23deb-206">**アプリのショートカット**を使用すると、web アプリ内で一般的または推奨されるタスクをすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="23deb-206">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span></span>  

<!--todo: add App shortcuts when section is live  -->  

<span data-ttu-id="23deb-207">**マニフェスト**ウィンドウには、次の条件の警告が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-207">The **Manifest** pane now shows warnings for the following conditions.</span></span>  

* <span data-ttu-id="23deb-208">アプリのショートカットアイコンが 96 x 96 ピクセルより小さい</span><span class="sxs-lookup"><span data-stu-id="23deb-208">The app shortcut icons are smaller than 96x96 pixels</span></span>  
* <span data-ttu-id="23deb-209">アプリのショートカットアイコンとマニフェストアイコンは、(アイコンが無視されているため) 四角形ではありません。</span><span class="sxs-lookup"><span data-stu-id="23deb-209">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span></span>  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="アプリのショートカットの警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   <span data-ttu-id="23deb-211">アプリのショートカットの警告</span><span class="sxs-lookup"><span data-stu-id="23deb-211">App shortcut warnings</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-212">Chromium の問題[#955497][CR955497]</span><span class="sxs-lookup"><span data-stu-id="23deb-212">Chromium issue [#955497][CR955497]</span></span>  

### <span data-ttu-id="23deb-213">計算されたウィンドウの一貫性のある表示</span><span class="sxs-lookup"><span data-stu-id="23deb-213">Consistent display of the Computed pane</span></span>  

<span data-ttu-id="23deb-214">[**要素**] パネルの**計算**ウィンドウは、すべてのビューポートサイズのウィンドウとして一貫して表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-214">The **Computed** pane in the **Elements** panel now displays consistently as a pane across all viewport sizes.</span></span>  <span data-ttu-id="23deb-215">以前は、DevTools ビューポートの幅が狭い場合に、[**スタイル**] ウィンドウ内にマージされた**計算**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="23deb-215">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span></span>  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="DevTools が限定されている場合でも、計算ウィンドウは個別のウィンドウとして表示されます" lightbox="../../media/2020/06/computed-pane.msft.png":::
   <span data-ttu-id="23deb-217">この**ウィンドウは、** devtools が限定されている場合でも、個別のウィンドウとして常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-217">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span></span>
:::image-end:::  

<span data-ttu-id="23deb-218">Chromium の問題[#1073899][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="23deb-218">Chromium issue [#1073899][CR1073899]</span></span>  

### <span data-ttu-id="23deb-219">Webasfiles のバイトコードオフセット</span><span class="sxs-lookup"><span data-stu-id="23deb-219">Bytecode offsets for WebAssembly files</span></span>  

<span data-ttu-id="23deb-220">DevTools では、Wasm 逆アセンブルの行番号を表示するためにバイトコードオフセットを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-220">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span></span>  
<span data-ttu-id="23deb-221">行番号によって、バイナリデータを見ているかどうかがわかりやすくなり、Wasm ランタイムが位置情報を参照する方法に一貫性が保たれます。</span><span class="sxs-lookup"><span data-stu-id="23deb-221">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span></span>  

<span data-ttu-id="23deb-222">Chromium の問題[#1071432][CR1071432]</span><span class="sxs-lookup"><span data-stu-id="23deb-222">Chromium issue [#1071432][CR1071432]</span></span>  

### <span data-ttu-id="23deb-223">[ソース] パネルでの線ごとのコピーと切り取り</span><span class="sxs-lookup"><span data-stu-id="23deb-223">Line-wise copy and cut in Sources Panel</span></span>  

<span data-ttu-id="23deb-224">[ソースパネルエディター][DevtoolsSourcesEditCssJavascript]で選択なしでコピーまたは切り取りを実行すると、devtools で現在のコンテンツの行がコピーまたは切り取りられます。</span><span class="sxs-lookup"><span data-stu-id="23deb-224">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesEditCssJavascript], DevTools copies or cuts the current line of content.</span></span>  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="カーソルが行5の最後にある状態で、DevTools の pen.js から行全体をコピーして、VS コードに貼り付けます。" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   <span data-ttu-id="23deb-226">カーソルが行5の最後にある状態で、DevTools の**pen.js**から行全体をコピーして、 [VS コード][VSCode]に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="23deb-226">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [VS Code][VSCode].</span></span>
:::image-end:::  

<span data-ttu-id="23deb-227">Chromium の問題[#800028][CR800028]</span><span class="sxs-lookup"><span data-stu-id="23deb-227">Chromium issue [#800028][CR800028]</span></span>

### <span data-ttu-id="23deb-228">本体の設定の更新</span><span class="sxs-lookup"><span data-stu-id="23deb-228">Console Settings updates</span></span>  

#### <span data-ttu-id="23deb-229">同じ本体のメッセージをグループ解除する</span><span class="sxs-lookup"><span data-stu-id="23deb-229">Ungroup same console messages</span></span>  

<span data-ttu-id="23deb-230">[コンソール設定] の [**同様のグループ]** が、重複するメッセージに適用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-230">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span></span>  <span data-ttu-id="23deb-231">以前は同様のメッセージに適用されました。</span><span class="sxs-lookup"><span data-stu-id="23deb-231">Previously it just applied to similar messages.</span></span>  

<span data-ttu-id="23deb-232">たとえば、前の例で `hello` は、グループの同様のチェックマークがオフになっているにもかかわらず、DevTools がメッセージのグループ**化**を解除しました。</span><span class="sxs-lookup"><span data-stu-id="23deb-232">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span></span>  <span data-ttu-id="23deb-233">これで、 `hello` メッセージはグループ解除されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-233">Now, the `hello` messages are ungrouped.</span></span>  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="[グループ類似] がオフの場合、hello メッセージはグループ解除されます。" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   <span data-ttu-id="23deb-235">[**グループ類似]** がオフの場合、 `hello` メッセージはグループ解除されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-235">When **Group similar** is unchecked, the `hello` messages are ungrouped.</span></span>
:::image-end:::  

<span data-ttu-id="23deb-236">この機能については、[コンソールに重複したメッセージを送信するサンプル][CodepenZoherghadyaliZyrjgdJ]を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="23deb-236">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span></span>  

<span data-ttu-id="23deb-237">Chromium の問題[#1082963][CR1082963]</span><span class="sxs-lookup"><span data-stu-id="23deb-237">Chromium issue [#1082963][CR1082963]</span></span>  

### <span data-ttu-id="23deb-238">選択されたコンテキストのみの設定を保持する</span><span class="sxs-lookup"><span data-stu-id="23deb-238">Persisting Selected context only settings</span></span>  

<span data-ttu-id="23deb-239">コンソール設定で**選択されたコンテキストのみ**の設定が保持されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-239">The **Selected context only** settings in Console Settings is now persisted.</span></span>  <span data-ttu-id="23deb-240">以前は、DevTools を閉じてもう一度開くたびに、設定はリセットされました。</span><span class="sxs-lookup"><span data-stu-id="23deb-240">Previously the settings were reset every time you closed and reopened DevTools.</span></span>  <span data-ttu-id="23deb-241">この変更により、設定動作は、他の本体の設定オプションと一貫性が保たれます。</span><span class="sxs-lookup"><span data-stu-id="23deb-241">The change makes the setting behavior consistent with other Console Settings options.</span></span>  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="選択されたコンテキストのみの設定" lightbox="../../media/2020/06/selected-context.msft.png":::
   <span data-ttu-id="23deb-243">**選択されたコンテキストのみ**の設定</span><span class="sxs-lookup"><span data-stu-id="23deb-243">**Selected context only** setting</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-244">Chromium の問題[#1055875][CR1055875]</span><span class="sxs-lookup"><span data-stu-id="23deb-244">Chromium issue [#1055875][CR1055875]</span></span>  

### <span data-ttu-id="23deb-245">パフォーマンスパネルの更新</span><span class="sxs-lookup"><span data-stu-id="23deb-245">Performance panel updates</span></span>  

#### <span data-ttu-id="23deb-246">パフォーマンスパネルの JavaScript コンパイルキャッシュ情報</span><span class="sxs-lookup"><span data-stu-id="23deb-246">JavaScript compilation cache information in Performance panel</span></span>  

<span data-ttu-id="23deb-247">[JavaScript コンパイルキャッシュ情報][V8DevCodeCaching]が、常に [パフォーマンス] パネルの [概要] タブに表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-247">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the Summary tab of the Performance panel.</span></span>  <span data-ttu-id="23deb-248">以前は、コードキャッシュが行われなかった場合、DevTools でコードキャッシュに関連するものは表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="23deb-248">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span></span>  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript コンパイルキャッシュ情報" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   <span data-ttu-id="23deb-250">JavaScript コンパイルキャッシュ情報</span><span class="sxs-lookup"><span data-stu-id="23deb-250">JavaScript compilation cache information</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-251">Chromium の問題[#912581][CR912581]</span><span class="sxs-lookup"><span data-stu-id="23deb-251">Chromium issue [#912581][CR912581]</span></span>  

#### <span data-ttu-id="23deb-252">パフォーマンスパネルでのナビゲーションのタイミングの配置</span><span class="sxs-lookup"><span data-stu-id="23deb-252">Navigation timing alignment in the Performance panel</span></span>  

<span data-ttu-id="23deb-253">[**パフォーマンス**] パネルでは、録画が開始されたタイミングに基づいてルーラーに時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-253">The **Performance** panel used to show times in the rulers based on when the recording started.</span></span>  <span data-ttu-id="23deb-254">これで、ユーザーが移動する記録のタイミングが変更されました。これで、DevTools でナビゲーションに対するルーラーの時間が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23deb-254">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span></span>  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="[パフォーマンス] パネルでのナビゲーションのタイミングの調整" lightbox="../../media/2020/06/nav-timing.msft.png":::
   <span data-ttu-id="23deb-256">[**パフォーマンス**] パネルでのナビゲーションのタイミングの調整</span><span class="sxs-lookup"><span data-stu-id="23deb-256">Align navigation timing in **Performance** panel</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-257">`DOMContentLoaded`最初の塗料、First Contentful 塗りつぶしの塗料、および最大の contentful ような塗料イベントは、ナビゲーションの開始からの相対的な時間に更新されます。つまり、タイミングは、によって報告されるタイミングと一致し `PerformanceObserver` ます。</span><span class="sxs-lookup"><span data-stu-id="23deb-257">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span></span>  

<span data-ttu-id="23deb-258">Chromium の問題[#974550][CR974550]</span><span class="sxs-lookup"><span data-stu-id="23deb-258">Chromium issue [#974550][CR974550]</span></span>  

### <span data-ttu-id="23deb-259">ブレークポイント、条件付きブレークポイント、および logpoints の新しいアイコン</span><span class="sxs-lookup"><span data-stu-id="23deb-259">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="23deb-260">[**ソース**] パネルには、ブレークポイント、条件付きブレークポイント、および logpoints の新しいデザインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="23deb-260">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span></span>  <span data-ttu-id="23deb-261">ブレークポイントは、 [VS コード][VSCode]と[Visual Studio][VS]と同様に、赤い円で表されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-261">Breakpoints are represented by a red circle, just like [VS Code][VSCode] and [Visual Studio][VS].</span></span>  <span data-ttu-id="23deb-262">条件付きブレークポイントと logpoints を区別するためにアイコンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-262">Icons are added to differentiate conditional breakpoints and logpoints.</span></span>  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="ブレークポイント" lightbox="../../media/2020/06/breakpoints.msft.png":::
   <span data-ttu-id="23deb-264">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="23deb-264">Breakpoints</span></span>  
:::image-end:::  

<span data-ttu-id="23deb-265">Chromium の問題[#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="23deb-265">Chromium issue [#1041830][CR1041830]</span></span>  

## <span data-ttu-id="23deb-266">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="23deb-266">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="23deb-267">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels]を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="23deb-267">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="23deb-268">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23deb-268">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="23deb-269">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="23deb-269">Getting in touch with Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="23deb-270">次のオプションを使用して、投稿の新機能や変更点、または DevTools に関連するその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="23deb-270">Use the following options to discuss the new features and changes in the post, or anything else related to DevTools.</span></span>  

* <span data-ttu-id="23deb-271">DevTools の**フィードバック**アイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="23deb-271">Send your feedback using the **Feedback** icon in the DevTools</span></span>  
* <span data-ttu-id="23deb-272">[@EdgeDevTools][PostTweetEdgeDevTools]ツイート</span><span class="sxs-lookup"><span data-stu-id="23deb-272">Tweet at [@EdgeDevTools][PostTweetEdgeDevTools]</span></span>  
* <span data-ttu-id="23deb-273">[目的の Web サイト][TheWebWeWant]に提案を送信する</span><span class="sxs-lookup"><span data-stu-id="23deb-273">Submit a suggestion to [The Web We Want][TheWebWeWant]</span></span>  
* <span data-ttu-id="23deb-274">[エッジ開発者][GitHubMicrosoftDocsEdgeDeveloperNewIssue]リポジトリでこのページのファイルのバグを修正します。</span><span class="sxs-lookup"><span data-stu-id="23deb-274">File bugs on this page in the [edge-developer][GitHubMicrosoftDocsEdgeDeveloperNewIssue] repository</span></span>  

:::image type="complex" source="../../media/2020/05/feedback-icon.msft.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン" lightbox="../../media/2020/05/feedback-icon.msft.png":::
  <span data-ttu-id="23deb-276">Microsoft Edge DevTools の**フィードバック**アイコン</span><span class="sxs-lookup"><span data-stu-id="23deb-276">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドローワ-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "実験的な機能を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "CSS と JavaScript の編集-ソースパネルの概要 |Microsoft ドキュメント"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワークアクティビティのログ-Microsoft Edge DevTools でネットワークアクティビティを検査するMicrosoft ドキュメント"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS イン JS フレームワークのスタイルの編集 |CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "重複メッセージをコンソールに送信 |CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS グリッドプランナーの例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR772558]: https://crbug.com/772558 "DevTools: 最新バージョンの Lighthouse を更新する |Chromium のバグ"  
[CR800028]: https://crbug.com/800028 "Chrome の更新後に、開発者ツールエディターの重複した行のショートカットが機能しないChromium のバグ"  
[CR912581]: https://crbug.com/912581 "V8 によってコードがキャッシュされていたスクリプトを、DevTools/about: tracing | に公開します。Chromium のバグ"  
[CR946975]: https://crbug.com/946975 "DevTools のスタイルサイドバーは、構築されたスタイルシートに対応していません。Chromium のバグ"  
[CR955497]: https://crbug.com/955497 "PWAs のアプリアイコンショートカットメニュー |Chromium のバグ"  
[CR974550]: https://crbug.com/974550 "パフォーマンスパネルとパフォーマンスオブザーバーの間のメトリックの不一致 |Chromium のバグ"  
[CR1041830]: https://crbug.com/1041830 "ブレークポイントの色を改善する |Chromium のバグ"  
[CR1055875]: https://crbug.com/1055875 "開発者ツールを終了してもう一度開くと、選択したコンテキストのみのコンソール設定の値が保持されません。Chromium のバグ"  
[CR1066579]: https://crbug.com/1066579 "DevTools: ServiceWorkers の表示 [ネットワークパネル] での要求ごとのタイムラインの取得 |Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic 開発者エクスペリエンス |Chromium のバグ"  
[CR1073899]: https://crbug.com/1073899 "[計算されたスタイル] タブが応答モードで表示されなくなります。Chromium のバグ"  
[CR1073903]: https://crbug.com/1073903 "DevTools: 構文の強調表示は、プライベートフィールドでは使用できません。Chromium のバグ"  
[CR1082963]: https://crbug.com/1082963 "本体のグループ類似メッセージの動作を無効にすることはできません |Chromium のバグ"  
[CR1083214]: https://crbug.com/1083214 "acorn はオプションのチェーンをサポートしていません |Chromium のバグ"  
[CR1083797]: https://crbug.com/1083797 "Nullish 合体については、非常に印刷されませんでした |Chromium のバグ"  
[CR1096008]: https://crbug.com/1096008 "FMP を削除 |Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table ツーリング |Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "代理ネットワーク要求を作成および再生するためのツールを作成する |Chromium のバグ"  
[CR1070378]: https://crbug.com/1070378 "DevTools への web ヒントの統合 |Chromium のバグ"  
[CR1069404]: https://crbug.com/1069404 "[開発ツール] ウィジェットのポップアップがすべて狭すぎます。Chromium のバグ"  
[CR897944]: https://crbug.com/897944 "ドラッグ可能になった devtool パネル |Chromium のバグ"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v 6.0.0-GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題-Microsoft のドキュメント/エッジ-開発者"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "Shadow DOM を使用する |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge Preview チャネル"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studio コード"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS オブジェクトモデル (CSSOM) |W3C CSS ワーキンググループエディターの下書き"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "プライベートクラスフィールド-パブリックとプライベートクラスのフィールド |V8.者"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "JavaScript 開発者向けのコードキャッシュ |V8.者"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish 合体 |V8.者"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "オプションのチェーン |V8.者"  

[WebhintMain]: https://webhint.io "web ヒント"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "構築方法の表スタイルオブジェクト |Web Incubator CG"

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

[TheWebWeWant]: https://webwewant.fyi/ "必要な Web"  

> [!NOTE]
> <span data-ttu-id="23deb-325">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="23deb-325">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="23deb-326">元のページは[ここ](https://developers.google.com/web/updates/2020/06/devtools/index)にあり、 [Jecelyn][JecelynYeen]で作成されています (開発者の代表者、Chrome devtools \)。</span><span class="sxs-lookup"><span data-stu-id="23deb-326">The original page is found [here](https://developers.google.com/web/updates/2020/06/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="23deb-328">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="23deb-328">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
