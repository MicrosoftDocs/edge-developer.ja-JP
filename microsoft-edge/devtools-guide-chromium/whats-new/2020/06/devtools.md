---
title: DevTools の新機能 (Microsoft Edge 85)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f569414a95336278c93b1bbafd57153ca902df12
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942191"
---
# <span data-ttu-id="0a833-103">DevTools の新機能 (Microsoft Edge 85)</span><span class="sxs-lookup"><span data-stu-id="0a833-103">What's New In DevTools (Microsoft Edge 85)</span></span>  

## <span data-ttu-id="0a833-104">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="0a833-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="0a833-105">以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。</span><span class="sxs-lookup"><span data-stu-id="0a833-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="0a833-106">DevTools、VS コード拡張機能などで新機能を試すには、お知らせを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a833-106">See the announcements to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="0a833-107">開発者ツールの最新機能と最大の機能をすべて最新の状態に保つには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルをダウンロードし [、Twitter で Microsoft Edge DevTools チームに従います][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="0a833-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="0a833-108">CSS グリッド デバッグ機能</span><span class="sxs-lookup"><span data-stu-id="0a833-108">CSS grid debugging features</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実用的な機能":::
   <span data-ttu-id="0a833-110">実用的な機能</span><span class="sxs-lookup"><span data-stu-id="0a833-110">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-111">Microsoft Edge DevTools チームは Chrome DevTools チームと Chromium コミュニティと共同作業を行い、DevTools に新しい CSS グリッドデッド機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="0a833-111">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span></span>  <span data-ttu-id="0a833-112">グリッド線の番号、グリッド間、および拡張された目盛線をオンページ上の重なりとして表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-112">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span></span>  <span data-ttu-id="0a833-113">また、グリッド ツールの機能の改善が、もちらつもなくリリース予定です。</span><span class="sxs-lookup"><span data-stu-id="0a833-113">Plus, more improvements to the grid tools are coming soon.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS グリッド デバッグ機能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   <span data-ttu-id="0a833-115">CSS グリッド デバッグ機能</span><span class="sxs-lookup"><span data-stu-id="0a833-115">CSS grid debugging features</span></span>
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="0a833-116">実用機能を有効にするには、「 [環境内][DevtoolsExperimentalFeaturesTurnOn] の機能を有効にする」を参照し、[新しい CSS グリッドのデバッグ機能を有効にする] の横にあるチェックボックス **をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="0a833-116">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span></span>  
> 
> <span data-ttu-id="0a833-117">サンプルの試すには [、CSS グリッド計画ツールの例を参照してください][CodepenRachelweilYzwBzKM]。</span><span class="sxs-lookup"><span data-stu-id="0a833-117">To try out the experiment with a sample, see [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span></span>  

<span data-ttu-id="0a833-118">Chromium の [問題#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="0a833-118">Chromium issue [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="0a833-119">ネットワーク本体で要求を編集および再生する</span><span class="sxs-lookup"><span data-stu-id="0a833-119">Edit and Replay requests with the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実用的な機能":::
   <span data-ttu-id="0a833-121">実用的な機能</span><span class="sxs-lookup"><span data-stu-id="0a833-121">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-122">ネットワーク本体を使用して、**ネットワーク**ログ内の要求に対[Network Log][DevtoolsNetworkIndexLogActivity]して編集と再生を**使用できるようになりました**。</span><span class="sxs-lookup"><span data-stu-id="0a833-122">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="NetworkConsole で NetworkLog で要求を編集および再生する" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   <span data-ttu-id="0a833-124">**NetworkConsole**で[NetworkLog で要求を][DevtoolsNetworkIndexLogActivity]編集および再生する</span><span class="sxs-lookup"><span data-stu-id="0a833-124">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-125">新しいパネル **(Network Console** は [DevTools Drawer で開][DevtoolsCustomizeIndexDrawer] き、HTTP 要求の情報が自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-125">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span></span>  <span data-ttu-id="0a833-126">サーバーから返された応答を表示するには、要求 \(必要な場合) を編集し、[送信] を選 **びます**。</span><span class="sxs-lookup"><span data-stu-id="0a833-126">To see the response returned from the server, edit the request \(if needed\) and select **Send**.</span></span>  

<span data-ttu-id="0a833-127">また **、Network Console** を使用して、DevTools から直接 HTTP 要求を作成して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a833-127">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="[ネットワーク本体] パネル" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   <span data-ttu-id="0a833-129">**[ネットワーク本体] パ**ネル</span><span class="sxs-lookup"><span data-stu-id="0a833-129">The **Network Console** panel</span></span>  
:::image-end:::  

> [!TIP]
> <span data-ttu-id="0a833-130">DevTools Drawer ではなくメイン \(top\) パネルに[Network Console を表示するには、パ][DevtoolsCustomizeIndexDrawer]ネル[間のツールを移動してください](#move-tools-between-panels)。 **Network Console**</span><span class="sxs-lookup"><span data-stu-id="0a833-130">To see **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], see [moving tools between panels](#move-tools-between-panels).</span></span>  

> [!NOTE]
> <span data-ttu-id="0a833-131">実用機能を有効にするには、「 [ネットワーク][DevtoolsExperimentalFeaturesTurnOn] 本体を有効にする」の横にあるチェックボックス **をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="0a833-131">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable Network Console**.</span></span>  
> 
> <span data-ttu-id="0a833-132">ネットワーク ログ [を開き][DevtoolsNetworkIndexLogActivity]、コンテキスト メニュー \(右クリック\) を開き、[ **編集と再生] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0a833-132">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and select **Edit and Replay**.</span></span>  

<span data-ttu-id="0a833-133">Chromium の問題はキ [#1093687][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="0a833-133">Chromium issue [#1093687][CR1093687]</span></span>  

### <span data-ttu-id="0a833-134">[タイミング] タブのサービス ワーカーの応答フォーム</span><span class="sxs-lookup"><span data-stu-id="0a833-134">Service worker respondWith events in the Timing tab</span></span>  

<span data-ttu-id="0a833-135">ネットワーク **パネルの** [ **タイミング] タブに** サービス作業者 `respondWith` イベントが含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-135">The **Timing** tab of the **Network** panel now includes `respondWith` service worker events.</span></span>  <span data-ttu-id="0a833-136">サービス `respondWith` の作業者イベントは、ハンドラーの確率が設定されたときに、サービス ワーカー イベント ハンドラーが実行を開始する直前の時間からの期間を `fetch` `respondWith` `fetch` 示します。</span><span class="sxs-lookup"><span data-stu-id="0a833-136">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="ネットワーク パネルの [タイミング] タブにある応答するサービス ワーカー イベント" lightbox="../../media/2020/06/timing-tab.msft.png":::
   <span data-ttu-id="0a833-138">ネットワーク `respondWith` パネルの [**タイミング**]**Network**タブのサービス ワーカー イベント</span><span class="sxs-lookup"><span data-stu-id="0a833-138">The `respondWith` service worker event in the **Timing** tab of the **Network** panel</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-139">返信 **の受信した返信を開き** 、返信から追加情報 (「あなた」、「、そして見つかった `fetch` `CacheStorageCacheName` `serviceWorkerResponseSource` 返信」など) を表示します `ResponseTime` 。</span><span class="sxs-lookup"><span data-stu-id="0a833-139">Expand **Response received** to see additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="受信した応答を追加した返信を表示するには、受信した応答を展開する" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   <span data-ttu-id="0a833-141">返信**の受信した回答を**表示する `fetch`</span><span class="sxs-lookup"><span data-stu-id="0a833-141">Expand **Response received** to see additional information from the `fetch` response</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-142">Chromium[の問題][CR1066579]#1066579</span><span class="sxs-lookup"><span data-stu-id="0a833-142">Chromium issue [#1066579][CR1066579]</span></span>  

### <span data-ttu-id="0a833-143">[問題] パネルのウェーント フィードバック</span><span class="sxs-lookup"><span data-stu-id="0a833-143">webhint feedback in the Issues panel</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実用的な機能":::
   <span data-ttu-id="0a833-145">実用的な機能</span><span class="sxs-lookup"><span data-stu-id="0a833-145">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-146">[Webhint][WebhintMain] はオープン ソース ツールであり、ブラウザーの互換性、セキュリティ、パフォーマンス、PWA、Web サイトのその他の一般的な Web 開発に関する問題に関するリアルタイムのフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="0a833-146">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="0a833-147">[問題] パネルでウェーント フィードバックを [表示することができるようにな][DevtoolsIssues] りました。</span><span class="sxs-lookup"><span data-stu-id="0a833-147">You are now able to see webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="[問題] パネルのウェーント フィードバック" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   <span data-ttu-id="0a833-149">[問題] パネルのウェーント フィードバック</span><span class="sxs-lookup"><span data-stu-id="0a833-149">webhint feedback in the Issues panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="0a833-150">実用機能を有効にするには、「実用 [的な機能を][DevtoolsExperimentalFeaturesTurnOn] 有効にする」を参照し、[ウェーンを有効にする] の横にあるチェック **ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="0a833-150">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable webhint**.</span></span>  
> 
> <span data-ttu-id="0a833-151">[問題 [] パネル][DevtoolsIssues] を開いて、Web ハイートからのフィードバックを表示する。</span><span class="sxs-lookup"><span data-stu-id="0a833-151">Open the [Issues][DevtoolsIssues] panel to see feedback from webhint.</span></span>  

<span data-ttu-id="0a833-152">Chromium の問題 [#1070378][CR1070378]</span><span class="sxs-lookup"><span data-stu-id="0a833-152">Chromium issue [#1070378][CR1070378]</span></span>  

### <span data-ttu-id="0a833-153">パネル間でツールを移動する</span><span class="sxs-lookup"><span data-stu-id="0a833-153">Move tools between panels</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実用的な機能":::
   <span data-ttu-id="0a833-155">実用的な機能</span><span class="sxs-lookup"><span data-stu-id="0a833-155">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-156">通常、要素やネットワークなどのツール**は**、DevTools**Network**のメイン \(top\) パネルでのみ開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a833-156">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="0a833-157">同様に **、3D ビュー**や問題などのツールは、DevTools の [下部\] パネルでのみ開く場合があります。 **Issues**</span><span class="sxs-lookup"><span data-stu-id="0a833-157">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="0a833-158">上下のパネルと下部パネルの間にあるツールを移動して、DevTools レイアウトをカスタマイズできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-158">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="パネル間のタブの移動" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   <span data-ttu-id="0a833-160">パネル間のタブの移動</span><span class="sxs-lookup"><span data-stu-id="0a833-160">Moving tabs between panels</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="0a833-161">実線を有効にするには、「環境内の[Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn]機能を有効にする」を参照し、[サポートを有効にする] の横にあるチェックボックスをオンにして、パネル間の**タブを移動します**。</span><span class="sxs-lookup"><span data-stu-id="0a833-161">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable support to move tabs between panels**.</span></span>  

<span data-ttu-id="0a833-162">Chromium の [問題#897944][CR897944]</span><span class="sxs-lookup"><span data-stu-id="0a833-162">Chromium issue [#897944][CR897944]</span></span>  

### <span data-ttu-id="0a833-163">ネットワーク パネルのイニシア ツールヒントの向上</span><span class="sxs-lookup"><span data-stu-id="0a833-163">Improved Initiator tooltip in the Network panel</span></span>  

<span data-ttu-id="0a833-164">Microsoft Edge 83 と 84 では、リソース要求の原因を示す [イニシアター] 列の[Network Log][DevtoolsNetworkIndexLogActivity]ツールヒント。この列には、水平スクロール バーが表示されたネットワーク ログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-164">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span></span>  <span data-ttu-id="0a833-165">ツールヒント内を横方向にスクロールして要求を開始した通話スタックを見るには、通話スタックのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-165">You were only able to see the call stack that initiated the request by scrolling horizontally in the tooltip.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 のイニシア ツールヒント" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   <span data-ttu-id="0a833-167">Microsoft Edge 84 のイニシア ツールヒント</span><span class="sxs-lookup"><span data-stu-id="0a833-167">The Initiator tooltip in Microsoft Edge 84</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-168">Microsoft Edge 85 以降では、ツールヒントで [イニターの通話の開始] スタックを表示できます。横スクロールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0a833-168">Starting with Microsoft Edge 85, you are now able to see the Initiator call stack in the tooltip without scrolling horizontally.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 のイニシア ツールヒント" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   <span data-ttu-id="0a833-170">Microsoft Edge 85 のイニシア ツールヒント</span><span class="sxs-lookup"><span data-stu-id="0a833-170">The Initiator tooltip in Microsoft Edge 85</span></span>
:::image-end:::  

<span data-ttu-id="0a833-171">Chromium の [問題#1069404][CR1069404]</span><span class="sxs-lookup"><span data-stu-id="0a833-171">Chromium issue [#1069404][CR1069404]</span></span>  

## <span data-ttu-id="0a833-172">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="0a833-172">Announcements from the Chromium project</span></span>  

<span data-ttu-id="0a833-173">次のセクションでは、Microsoft Edge 85 で使用可能な追加機能について、オープン ソース Chromium プロジェクトに投稿された追加機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a833-173">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="0a833-174">CSS イン-JS フレームワーク用のスタイル編集</span><span class="sxs-lookup"><span data-stu-id="0a833-174">Style editing for CSS-in-JS frameworks</span></span>  

<span data-ttu-id="0a833-175">スタイル**ウィンドウでは**[、CSS オブジェクト モデル (CSSOM)][CsswgDraftsCssom] API で作成されたスタイルを編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-175">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span></span>  <span data-ttu-id="0a833-176">多くの CSS インジャンネルおよびライブラリでは、体重の下にある CSSOM API を使用してスタイルを構造化しています。</span><span class="sxs-lookup"><span data-stu-id="0a833-176">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span></span>  

<span data-ttu-id="0a833-177">[作成済みスタイルシート] を使用して JavaScript で追加されたスタイル [を編集できるようになりました][WicgConstructStylesheet]。</span><span class="sxs-lookup"><span data-stu-id="0a833-177">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span></span>  <span data-ttu-id="0a833-178">[[Shadow DOM]][MdnShadowDom]を使用するときに再利用可能なスタイルを作成して配布する新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="0a833-178">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span></span>  

<span data-ttu-id="0a833-179">たとえば `h1` `CSSStyleSheet` 、\(CSSOM API\ で追加されたスタイル) は以前編集できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0a833-179">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span></span>  <span data-ttu-id="0a833-180">スタイルは編集可能になり、[スタイル] ウィンドウ **でスタイルが編集できるようになり** ました。</span><span class="sxs-lookup"><span data-stu-id="0a833-180">The styles are editable now in the **Styles** pane.</span></span>  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="CSSStyleSheet で追加された h1 スタイルの背景プロパティをピンクから薄い色に変更する" lightbox="../../media/2020/06/css-in-js.msft.png":::
   <span data-ttu-id="0a833-182">追加 `background` したスタイルの `h1` プロパティを `CSSStyleSheet` 変更 `pink` `lightblue` する</span><span class="sxs-lookup"><span data-stu-id="0a833-182">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span></span>
:::image-end:::  

<span data-ttu-id="0a833-183">この機能には [、CSS-in-JS を使用するサンプルを試してみてください][CodepenZoherghadyaliAbdgrpz]。</span><span class="sxs-lookup"><span data-stu-id="0a833-183">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span></span>

<span data-ttu-id="0a833-184">Chromium の問題は、chromium [の#946975][CR946975]</span><span class="sxs-lookup"><span data-stu-id="0a833-184">Chromium issue [#946975][CR946975]</span></span>  

### <span data-ttu-id="0a833-185">灯カッパネルの灯 6</span><span class="sxs-lookup"><span data-stu-id="0a833-185">Lighthouse 6 in the Lighthouse panel</span></span>  

<span data-ttu-id="0a833-186">灯 **ェーズ パネ** ルで灯している灯言語は、灯後 6 が実行されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-186">The **Lighthouse** panel is now running Lighthouse 6.</span></span>  <span data-ttu-id="0a833-187">すべての変更の完全な一覧については [、v6.0.0 リリース ノートを参照してください][GithubGoogleChromeLighthouse600]。</span><span class="sxs-lookup"><span data-stu-id="0a833-187">For a full list of all changes, see [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span></span>  

<span data-ttu-id="0a833-188">灯読 6.0 は、レポートに新しい指数を追加します。最大コンテンツ ペイント \(LCP\)、累積レイアウトシフト \(CLS\)、合計ブロック時間 \(TBT\) が追加されました。</span><span class="sxs-lookup"><span data-stu-id="0a833-188">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span></span>  

<span data-ttu-id="0a833-189">パフォーマンス スコアの数式も改善されました。ユーザーの読み込みエクスペリエンスがより適しています。</span><span class="sxs-lookup"><span data-stu-id="0a833-189">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span></span>  

<span data-ttu-id="0a833-190">Chromium の問題 [#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="0a833-190">Chromium issue [#772558][CR772558]</span></span>  

#### <span data-ttu-id="0a833-191">First Meaningful Paint Deprecation</span><span class="sxs-lookup"><span data-stu-id="0a833-191">First Meaningful Paint deprecation</span></span>  

<span data-ttu-id="0a833-192">First Meaningful Paint \(FMP\) は、Lighthouse 6.0 で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="0a833-192">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span></span>  <span data-ttu-id="0a833-193">また、FMP はパフォーマンス パ **ネルから** 削除されました。</span><span class="sxs-lookup"><span data-stu-id="0a833-193">FMP has also been removed from the **Performance** panel.</span></span>  <span data-ttu-id="0a833-194">**最大コンテンツ ペイントは、FMP** に代替えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0a833-194">**Largest Contentful Paint** is the recommended replacement for FMP.</span></span>  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

<span data-ttu-id="0a833-195">Chromium の[問題][CR1096008]は#1096008</span><span class="sxs-lookup"><span data-stu-id="0a833-195">Chromium issue [#1096008][CR1096008]</span></span>  

### <span data-ttu-id="0a833-196">JavaScript の新しい機能のサポート</span><span class="sxs-lookup"><span data-stu-id="0a833-196">Support for new JavaScript features</span></span>  

<span data-ttu-id="0a833-197">DevTools では、一部の JavaScript 言語機能のサポートが改良されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-197">DevTools now has better support for some of the latest JavaScript language features.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="0a833-198">[オートコンプリー][V8DevOptionalChaining] ト</span><span class="sxs-lookup"><span data-stu-id="0a833-198">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0a833-199">本体のプロパティの自動コンプリート**Console**では、オプションのチェーン構文がサポートされるようになりました。たとえば、これ以外にも `name?.` `name.` 、同様に機能します `name[` 。</span><span class="sxs-lookup"><span data-stu-id="0a833-199">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="0a833-200">プライベート フィールドの書式強調表示 [の構文][V8DevClassFieldsPrivate]</span><span class="sxs-lookup"><span data-stu-id="0a833-200">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0a833-201">プライベート クラス フィールドが [ソース] パネルで正しく強調表示され、[ソース] パネルで正しく印刷されるように **な** りました。</span><span class="sxs-lookup"><span data-stu-id="0a833-201">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="0a833-202">ネルルシュ コーロッシュ演算子の [構文][V8DevNullishCoalescing]</span><span class="sxs-lookup"><span data-stu-id="0a833-202">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0a833-203">DevTools は、[ソース] パネルの計算演算子を正しく **印刷** します。</span><span class="sxs-lookup"><span data-stu-id="0a833-203">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="0a833-204">Chromium[の問題][CR1073903]#1073903、#1083214、#1083797 [#1083214][CR1083214] [#1083797][CR1083797]</span><span class="sxs-lookup"><span data-stu-id="0a833-204">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span></span>  

### <span data-ttu-id="0a833-205">マニフェスト ウィンドウの新しいアプリ ショートカット警告</span><span class="sxs-lookup"><span data-stu-id="0a833-205">New app shortcut warnings in the Manifest pane</span></span>  

<span data-ttu-id="0a833-206">**アプリ のショートカットにより** 、ユーザーは Web アプリ内で一般的なまたは推奨タスクをすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="0a833-206">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span></span>  

<!--todo: add App shortcuts when section is live  -->  

<span data-ttu-id="0a833-207">マ **ニフェスト** ウィンドウに、次の条件の警告が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-207">The **Manifest** pane now shows warnings for the following conditions.</span></span>  

* <span data-ttu-id="0a833-208">アプリのショートカット アイコンが 96x96 ピクセル未満</span><span class="sxs-lookup"><span data-stu-id="0a833-208">The app shortcut icons are smaller than 96x96 pixels</span></span>  
* <span data-ttu-id="0a833-209">アプリのショートカット アイコンとマニフェスト アイコンは、\(アイコンが無視されるため\)</span><span class="sxs-lookup"><span data-stu-id="0a833-209">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span></span>  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="アプリのショートカットの警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   <span data-ttu-id="0a833-211">アプリのショートカットの警告</span><span class="sxs-lookup"><span data-stu-id="0a833-211">App shortcut warnings</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-212">Chromium の[問題][CR955497]は#955497</span><span class="sxs-lookup"><span data-stu-id="0a833-212">Chromium issue [#955497][CR955497]</span></span>  

### <span data-ttu-id="0a833-213">[縮された] ウィンドウの一定の表示</span><span class="sxs-lookup"><span data-stu-id="0a833-213">Consistent display of the Computed pane</span></span>  

<span data-ttu-id="0a833-214">[ **要素] パネルの** [ **作業** 結果] ウィンドウでは、すべてのビューポート サイズで一定のウィンドウとして一定のウィンドウとして表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-214">The **Computed** pane in the **Elements** panel now displays consistently as a pane across all viewport sizes.</span></span>  <span data-ttu-id="0a833-215">以前は**Styles\*\*\*\*、DevTools ビューポ**ートの幅が絞り込されていた [スタイル] ウィンドウ内に差し込み印刷されたウィンドウが入ります。</span><span class="sxs-lookup"><span data-stu-id="0a833-215">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span></span>  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="[Computed] ウィンドウは、DevTools が絞り込みの場合でも、一定の個別ウィンドウとして表示される" lightbox="../../media/2020/06/computed-pane.msft.png":::
   <span data-ttu-id="0a833-217">**[Computed]** ウィンドウは、DevTools が絞り込みの場合でも、一定の個別ウィンドウとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-217">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span></span>
:::image-end:::  

<span data-ttu-id="0a833-218">Chromium の問題は、chromium [の#1073899][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="0a833-218">Chromium issue [#1073899][CR1073899]</span></span>  

### <span data-ttu-id="0a833-219">WebAssembly ファイルのバイトコード オフセット</span><span class="sxs-lookup"><span data-stu-id="0a833-219">Bytecode offsets for WebAssembly files</span></span>  

<span data-ttu-id="0a833-220">DevTools では、Wasm disassembly の行数を表示するバイトコード オフセットを使用しました。</span><span class="sxs-lookup"><span data-stu-id="0a833-220">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span></span>  
<span data-ttu-id="0a833-221">行番号を使用すると、バイナリ データを確認する方法が明らかになり、Wasm ランタイム参照の場所に一定性があります。</span><span class="sxs-lookup"><span data-stu-id="0a833-221">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span></span>  

<span data-ttu-id="0a833-222">Chromium の問題 [#1071432][CR1071432]</span><span class="sxs-lookup"><span data-stu-id="0a833-222">Chromium issue [#1071432][CR1071432]</span></span>  

### <span data-ttu-id="0a833-223">[ソース] パネルの行間のコピーと切り取り</span><span class="sxs-lookup"><span data-stu-id="0a833-223">Line-wise copy and cut in Sources Panel</span></span>  

<span data-ttu-id="0a833-224">[ソース] パネル エディターでコピーを実行したり切り取ったり [するとき][DevtoolsSourcesEditCssJavascript]、DevTools はコンテンツの現在の行をコピーまたは切り取ります。</span><span class="sxs-lookup"><span data-stu-id="0a833-224">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesEditCssJavascript], DevTools copies or cuts the current line of content.</span></span>  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="5 行の末尾にカーソルを移動し、DevTools の pen.js から行全体をコピーして VS コードに貼り付けます。" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   <span data-ttu-id="0a833-226">5 行の末尾にカーソルを移動し、DevTools の \*\*pen.jsから行全体をコピーして \*\* [VS コードに貼り付けます][VSCode]。</span><span class="sxs-lookup"><span data-stu-id="0a833-226">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [VS Code][VSCode].</span></span>
:::image-end:::  

<span data-ttu-id="0a833-227">Chromium[の問題][CR800028]#800028</span><span class="sxs-lookup"><span data-stu-id="0a833-227">Chromium issue [#800028][CR800028]</span></span>

### <span data-ttu-id="0a833-228">本体の設定更新</span><span class="sxs-lookup"><span data-stu-id="0a833-228">Console Settings updates</span></span>  

#### <span data-ttu-id="0a833-229">同じ本体メッセージのグループ化を解除する</span><span class="sxs-lookup"><span data-stu-id="0a833-229">Ungroup same console messages</span></span>  

<span data-ttu-id="0a833-230">本 **体設定で** 同様のトグルが適用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-230">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span></span>  <span data-ttu-id="0a833-231">以前は、同様のメッセージに適用されています。</span><span class="sxs-lookup"><span data-stu-id="0a833-231">Previously it just applied to similar messages.</span></span>  

<span data-ttu-id="0a833-232">前に、DevTools は同じグループのようにオフになっていてもメッセージのグループ化 `hello` を解除しませんでした。 **Group similar**</span><span class="sxs-lookup"><span data-stu-id="0a833-232">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span></span>  <span data-ttu-id="0a833-233">これで、メッセージ `hello` はグループ解除されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-233">Now, the `hello` messages are ungrouped.</span></span>  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="同様のグループをオフにすると、Hello メッセージはグループ解除されます。" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   <span data-ttu-id="0a833-235">同 **様のグループをオフ** にすると、メッセージ `hello` はグループ解除されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-235">When **Group similar** is unchecked, the `hello` messages are ungrouped.</span></span>
:::image-end:::  

<span data-ttu-id="0a833-236">本体に重複メッセージを送信するサンプルを試 [してみてください][CodepenZoherghadyaliZyrjgdJ]。</span><span class="sxs-lookup"><span data-stu-id="0a833-236">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span></span>  

<span data-ttu-id="0a833-237">Chromium の問題 [#1082963][CR1082963]</span><span class="sxs-lookup"><span data-stu-id="0a833-237">Chromium issue [#1082963][CR1082963]</span></span>  

### <span data-ttu-id="0a833-238">選択したコンテキストのみの設定を行う</span><span class="sxs-lookup"><span data-stu-id="0a833-238">Persisting Selected context only settings</span></span>  

<span data-ttu-id="0a833-239">本 **体の設定で選択** したコンテキストのみが保存されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-239">The **Selected context only** settings in Console Settings is now persisted.</span></span>  <span data-ttu-id="0a833-240">以前は、設定は、開いてから開いたびに再度開いた度でした。</span><span class="sxs-lookup"><span data-stu-id="0a833-240">Previously the settings were reset every time you closed and reopened DevTools.</span></span>  <span data-ttu-id="0a833-241">この変更により、その他の本体設定オプションと一体で設定が同じになっています。</span><span class="sxs-lookup"><span data-stu-id="0a833-241">The change makes the setting behavior consistent with other Console Settings options.</span></span>  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="選択されたコンテキストのみの設定" lightbox="../../media/2020/06/selected-context.msft.png":::
   <span data-ttu-id="0a833-243">**選択されたコンテキストのみの** 設定</span><span class="sxs-lookup"><span data-stu-id="0a833-243">**Selected context only** setting</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-244">Chromium の問題 [#1055875][CR1055875]</span><span class="sxs-lookup"><span data-stu-id="0a833-244">Chromium issue [#1055875][CR1055875]</span></span>  

### <span data-ttu-id="0a833-245">パフォーマンス パネルの更新</span><span class="sxs-lookup"><span data-stu-id="0a833-245">Performance panel updates</span></span>  

#### <span data-ttu-id="0a833-246">パフォーマンス パネルの JavaScript コンパイル キャッシュ情報</span><span class="sxs-lookup"><span data-stu-id="0a833-246">JavaScript compilation cache information in Performance panel</span></span>  

<span data-ttu-id="0a833-247">[JavaScript のコンパイルキ][V8DevCodeCaching] ャッシュ情報が、パフォーマンス パネルの [概要] タブに常に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-247">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the Summary tab of the Performance panel.</span></span>  <span data-ttu-id="0a833-248">以前は、コード キャッシュが実行されていない場合、DevTools はコード キャッシュに関連するものが何も表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="0a833-248">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span></span>  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript のコンパイル情報" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   <span data-ttu-id="0a833-250">JavaScript のコンパイル情報</span><span class="sxs-lookup"><span data-stu-id="0a833-250">JavaScript compilation cache information</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-251">Chromium の [問題#912581][CR912581]</span><span class="sxs-lookup"><span data-stu-id="0a833-251">Chromium issue [#912581][CR912581]</span></span>  

#### <span data-ttu-id="0a833-252">パフォーマンス パネルのナビゲーションタイミングの調整</span><span class="sxs-lookup"><span data-stu-id="0a833-252">Navigation timing alignment in the Performance panel</span></span>  

<span data-ttu-id="0a833-253">記録 **開始** 時に基づいてルーラーの時間を表示するために使用されるパフォーマンス パネル。</span><span class="sxs-lookup"><span data-stu-id="0a833-253">The **Performance** panel used to show times in the rulers based on when the recording started.</span></span>  <span data-ttu-id="0a833-254">ユーザーがナビゲーションする場合のタイミングが変更されるようになりました。この場合、代わりに DevTools でナビゲーションに対して、ルーラーが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a833-254">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span></span>  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="パフォーマンス パネルでナビゲーションのタイミングを揃える" lightbox="../../media/2020/06/nav-timing.msft.png":::
   <span data-ttu-id="0a833-256">パフォーマンス パネルでナビゲーションのタ **イミングを** 揃える</span><span class="sxs-lookup"><span data-stu-id="0a833-256">Align navigation timing in **Performance** panel</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-257">最初のコンテンツ、最初のコンテンツ ファイント、大きいコンテンツ フル ペイント イベントの時間は、ナビゲーションの開始と相対的に更新され、このタイミングは報告されるタイミングと `DOMContentLoaded` 一致します `PerformanceObserver` 。</span><span class="sxs-lookup"><span data-stu-id="0a833-257">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span></span>  

<span data-ttu-id="0a833-258">Chromium の [問題はc#974550][CR974550]</span><span class="sxs-lookup"><span data-stu-id="0a833-258">Chromium issue [#974550][CR974550]</span></span>  

### <span data-ttu-id="0a833-259">区切り点、条件付き改行ポイント、およびロゴの新しいアイコン</span><span class="sxs-lookup"><span data-stu-id="0a833-259">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="0a833-260">[ **ソース] パ** ネルには、改ページ、条件付きのブレークポイント、およびロゴの新しいデザインがあります。</span><span class="sxs-lookup"><span data-stu-id="0a833-260">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span></span>  <span data-ttu-id="0a833-261">改行ポイントは[VS][VSCode]コードやインクと同様に、破たされた[Visual Studio。][VS]</span><span class="sxs-lookup"><span data-stu-id="0a833-261">Breakpoints are represented by a red circle, just like [VS Code][VSCode] and [Visual Studio][VS].</span></span>  <span data-ttu-id="0a833-262">アイコンは、条件付きの改行ポイントとロックポイントを区別するものに追加されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-262">Icons are added to differentiate conditional breakpoints and logpoints.</span></span>  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="ブレークポイント" lightbox="../../media/2020/06/breakpoints.msft.png":::
   <span data-ttu-id="0a833-264">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="0a833-264">Breakpoints</span></span>  
:::image-end:::  

<span data-ttu-id="0a833-265">Chromium[の問題][CR1041830]#1041830</span><span class="sxs-lookup"><span data-stu-id="0a833-265">Chromium issue [#1041830][CR1041830]</span></span>  

## <span data-ttu-id="0a833-266">Microsoft Edge のプレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="0a833-266">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="0a833-267">Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。</span><span class="sxs-lookup"><span data-stu-id="0a833-267">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="0a833-268">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0a833-268">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="0a833-269">Microsoft Edge DevTools チームとのつながりを手にする</span><span class="sxs-lookup"><span data-stu-id="0a833-269">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "Microsoft Edge DevTools コマンド メニューでコマンドを実行する |Microsoft ドキュメント"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ダイヤルパー - Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "環境の機能を有効にする - 実用的な機能 |Microsoft ドキュメント"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "Microsoft Edge DevTools の問題ツールに関する問題を見つけ、解決する |Microsoft ドキュメント"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "CSS と JavaScript の編集 - ソース パネルの概要 |Microsoft ドキュメント"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワーク アクティビティのログ - Microsoft Edge DevTools でのネットワーク アクティビティの検査 |Microsoft ドキュメント"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS イン-JS フレームワーク用のスタイル編集 |CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "重複メッセージを本体に送信する |CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS グリッド計画ツールの例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR772558]: https://crbug.com/772558 "DevTools:最新バージョンの Lighthouse に更新する |Chromium のバグ"  
[CR800028]: https://crbug.com/800028 "Chrome 更新後に開発者ツール エディターの複製線のショートカット |Chromium のバグ"  
[CR912581]: https://crbug.com/912581 "DevTools/about:tracing に V8 によってコードされたコード付きスクリプトを示します |Chromium のバグ"  
[CR946975]: https://crbug.com/946975 "DevTools スタイルのサイドバーが構造化されたスタイルシートでは機能しません |Chromium のバグ"  
[CR955497]: https://crbug.com/955497 "PWA のアプリ アイコンのショートカット メニュー |Chromium のバグ"  
[CR974550]: https://crbug.com/974550 "Perf パネルと performanceObserver 間のメトリックの不一致 |Chromium のバグ"  
[CR1041830]: https://crbug.com/1041830 "区切り点の色を改善する |Chromium のバグ"  
[CR1055875]: https://crbug.com/1055875 "開発者ツールの開発および再度開いた後に、選択したコンテキストのみの設定は保存されません|Chromium のバグ"  
[CR1066579]: https://crbug.com/1066579 "DevTools:[ネットワーク パネル] の要求ごとの ServiceWorkers フェッチ タイムライン |Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic Developer Experience |Chromium のバグ"  
[CR1073899]: https://crbug.com/1073899 "[コンピュートされたスタイル] タブが応答モードで消えます |Chromium のバグ"  
[CR1073903]: https://crbug.com/1073903 "DevTools: プライベート フィールドの構文 |Chromium のバグ"  
[CR1082963]: https://crbug.com/1082963 "本体の同様のメッセージ動作を無効にできません |Chromium のバグ"  
[CR1083214]: https://crbug.com/1083214 "アンダーンは、オプションのチェーンをサポートしていません |Chromium のバグ"  
[CR1083797]: https://crbug.com/1083797 "ネルルシュ コーローのためにブロークが切れる場合 |Chromium のバグ"  
[CR1096008]: https://crbug.com/1096008 "FMP を削除する |Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/Flexbox/表ツール |Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "合理ネットワーク要求を作成および再再生するためのツール |Chromium のバグ"  
[CR1070378]: https://crbug.com/1070378 "Webhint を DevTools に統合する |Chromium のバグ"  
[CR1069404]: https://crbug.com/1069404 "[開発ツール] ウィジェットのポップアップがすべて絞り込みすぎる |Chromium のバグ"  
[CR897944]: https://crbug.com/897944 "ドラッグ可能なデベロッパネル |Chromium のバグ"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題 - MicrosoftDocs/edge 開発者"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "シャドウの DOM の使用 |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge Preview チャネル"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studioコード"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS オブジェクト モデル (CSSOM) |W3C CSS 作業グループ エディターの下書き"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |チェットを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "Twitter アカウント@EdgeDevTools Twitter アカウント"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "プライベート クラス フィールド - パブリック クラス フィールドとプライベート クラス フィールド |V8.開発"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "JavaScript デベロッパー向けのコード キャッシュ |V8.開発"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish coalescing |V8.開発"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "オプションのチェーン |V8.開発"  

[WebhintMain]: https://webhint.io "Webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "コンストルーラー スタイルシート オブジェクト |Web Incubator CG"

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
> <span data-ttu-id="0a833-318">このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-318">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0a833-319">元のページがここに [あ](https://developers.google.com/web/updates/2020/06/devtools/index) り [、Jecelyn Yeen][JecelynYeen] \(デベロッパーのアドバイト、Chrome DevTools\) によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="0a833-319">The original page is found [here](https://developers.google.com/web/updates/2020/06/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0a833-321">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0a833-321">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
