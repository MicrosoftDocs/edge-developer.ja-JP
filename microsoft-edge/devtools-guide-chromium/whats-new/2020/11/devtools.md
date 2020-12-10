---
description: Linux の Microsoft Edge、問題ツールの web ヒントのヒント、新しいサービスワーカーのデバッグ機能などが改善されました。
title: DevTools の新機能 (Microsoft Edge 88)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 500b64e7b51e0f02c9fcbcb7a83e8273b3a5a0d7
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "11205244"
---
# <span data-ttu-id="f7d86-104">DevTools の新機能 (Microsoft Edge 88)</span><span class="sxs-lookup"><span data-stu-id="f7d86-104">What's New in DevTools (Microsoft Edge 88)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <span data-ttu-id="f7d86-105">Microsoft Edge および Microsoft Edge ドライバーが Linux で利用できるようになりました</span><span class="sxs-lookup"><span data-stu-id="f7d86-105">Microsoft Edge and Microsoft Edge Driver now available on Linux</span></span>  

<!-- Title: Microsoft Edge and Microsoft Edge Driver on Linux  -->  
<!-- Subtitle: Get Microsoft Edge Dev on Ubuntu, Debian, Fedora, and openSUSE distributions and start automating in CI/CD environments with Microsoft Edge Driver. -->  

<span data-ttu-id="f7d86-106">Microsoft Edge Dev は、Ubuntu、Debian、Fedora、openSUSE の配布でサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-106">Microsoft Edge Dev is now supported on Ubuntu, Debian, Fedora, and openSUSE distributions.</span></span>  <span data-ttu-id="f7d86-107">Microsoft edge の開発者 `.deb` または `.rpm` パッケージを [microsoft edge Insider サイト][MicrosoftinsiderDownloadPlatformLinux] から直接ダウンロードしてインストールするか、またはお使いの Linux ディストリビューションの標準パッケージ管理ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-107">Download and install the Microsoft Edge Dev `.deb` or `.rpm` package directly from the [Microsoft Edge Insider site][MicrosoftinsiderDownloadPlatformLinux] or use the standard package management tools of your Linux distribution.</span></span>  

<span data-ttu-id="f7d86-108">継続的インテグレーションと配信 \ (CI/CD \) ソリューションで Linux 環境を使用している場合は、Microsoft Edge ドライバーも Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-108">If you are using a Linux environment in your continuous integration and delivery \(CI/CD\) solutions, Microsoft Edge Driver is also available on Linux.</span></span>  <span data-ttu-id="f7d86-109">Microsoft edge ドライバーを使用した Microsoft Edge の開発を開始するには、 [Microsoft Edge ドライバーのダウンロードページ][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-109">To get started automating Microsoft Edge Dev with Microsoft Edge Driver, navigate to [Microsoft Edge Driver Downloads page][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads].</span></span>  <span data-ttu-id="f7d86-110">Microsoft edge ドライバーと共に Microsoft edge Dev を自動化する方法については、「 [WebDriver (Chromium) を使ってテストオートメーションを使用][WebDriverChromiumMain]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d86-110">For help with automating Microsoft Edge Dev along with Microsoft Edge Driver, navigate to [Use WebDriver (Chromium) for test automation][WebDriverChromiumMain].</span></span>  

:::image type="complex" source="../../media/2020/11/edge-on-linux.msft.png" alt-text="Linux での Microsoft Edge の DevTools" lightbox="../../media/2020/11/edge-on-linux.msft.png":::
   <span data-ttu-id="f7d86-112">Linux での Microsoft Edge の DevTools</span><span class="sxs-lookup"><span data-stu-id="f7d86-112">DevTools in Microsoft Edge on Linux</span></span>  
:::image-end:::  

## <span data-ttu-id="f7d86-113">問題解決ツールの web ヒントとプラットフォームのヒントの改善</span><span class="sxs-lookup"><span data-stu-id="f7d86-113">Improved webhint and platform tips in the Issues tool</span></span>  

<!-- Title: Improvements to Issues tool and webhint integration  -->  
<!-- Subtitle: Categories and third-party filtering make it easier to survey issues in the Issues tool.  Issues surfaced by webhint now have improved code snippets and documentation links to help you fix problems in your website.  -->  

<span data-ttu-id="f7d86-114">オープンソースツールである web [ヒント][WebhintMain]は、web サイトやローカル web ページについてリアルタイムでフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-114">An open-source tool, [webhint][WebhintMain], provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="f7d86-115">[Microsoft Edge バージョン 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]以降では、[[問題][DevtoolsIssuesIndex]] ツールの webhint のフィードバックを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-115">Starting with [Microsoft Edge version 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel], review webhint feedback in the [Issues][DevtoolsIssuesIndex] tool.</span></span>  <span data-ttu-id="f7d86-116">**懸案事項**ツールに表示される問題は、次のカテゴリを追加することで簡単に確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-116">Issues that appear in the **Issues** tool are now easier to review with the addition of the following categories.</span></span>  

*   [<span data-ttu-id="f7d86-117">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="f7d86-117">Accessibility</span></span>][WebhintUserGuideHintsAccessibility]  
*   [<span data-ttu-id="f7d86-118">互換性</span><span class="sxs-lookup"><span data-stu-id="f7d86-118">Compatibility</span></span>][WebhintUserGuideHintsCompatibility]  
*   [<span data-ttu-id="f7d86-119">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="f7d86-119">Performance</span></span>][WebhintUserGuideHintsPerformance]  
*   [<span data-ttu-id="f7d86-120">Pitfalls</span><span class="sxs-lookup"><span data-stu-id="f7d86-120">Pitfalls</span></span>][WebhintUserGuideHintsPitfalls]  
*   [<span data-ttu-id="f7d86-121">PWA</span><span class="sxs-lookup"><span data-stu-id="f7d86-121">PWA</span></span>][WebhintUserGuideHintsPwa]  
*   [<span data-ttu-id="f7d86-122">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f7d86-122">Security</span></span>][WebhintUserGuideHintsSecurity]  
    
<span data-ttu-id="f7d86-123">これで、新しいチェックボックスを使ってサードパーティの問題をフィルター処理できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-123">You are now able to filter out third-party issues using a new checkbox.</span></span>  <span data-ttu-id="f7d86-124">フィルター機能を使用すると、サードパーティのライブラリやその他のソースからのコードに関連する問題を非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-124">The filter functionality helps you hide issues related to code from third-party libraries or other sources.</span></span>  

<span data-ttu-id="f7d86-125">[Webhint][WebhintMain]によって発生した問題を確認するために、**問題**ツールには次の情報が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-125">To help you review issues revealed by [webhint][WebhintMain], the **Issues** tool now displays the following information.</span></span>  

*   <span data-ttu-id="f7d86-126">改善されたコードスニペット。</span><span class="sxs-lookup"><span data-stu-id="f7d86-126">Improved code snippets.</span></span>  
*   <span data-ttu-id="f7d86-127">他の関連パネルへのリンク。</span><span class="sxs-lookup"><span data-stu-id="f7d86-127">Links to other relevant panels.</span></span>  
*   <span data-ttu-id="f7d86-128">Web サイトの問題を解決するのに役立つドキュメントへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="f7d86-128">Links to documentation to help you fix problems in your website.</span></span>  
    
:::image type="complex" source="../../media/2020/11/issues-webhints.msft.png" alt-text="問題ツール" lightbox="../../media/2020/11/issues-webhints.msft.png":::
   <span data-ttu-id="f7d86-130">**問題** ツール</span><span class="sxs-lookup"><span data-stu-id="f7d86-130">**Issues** tool</span></span>  
:::image-end:::  

## <span data-ttu-id="f7d86-131">合成レイヤーが3D ビューに表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="f7d86-131">Composited Layers are now in 3D View</span></span>  

<!-- Title: 3D View is now integrated with Composited Layers  -->  
<!-- Subtitle: Composited Layers are now in 3D View.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

<span data-ttu-id="f7d86-132">これで、 **レイヤー** コンテンツと、z インデックス値、ドキュメントオブジェクトモデル \ (DOM \) を視覚化することができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-132">You may now visualize **Layers** content alongside z-index values and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="f7d86-133">この機能により、 [3d ビュー][Devtools3dViewIndex] と **レイヤー** ツールを頻繁に切り替えることなく、デバッグを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-133">This feature helps you debug without switching between the [3D view][Devtools3dViewIndex] and **Layers** tools as often.</span></span>  <span data-ttu-id="f7d86-134">包括的なビジュアルデバッグエクスペリエンスを実現するために、 [3D ビューレイヤーと合成レイヤーが結合されました][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]。</span><span class="sxs-lookup"><span data-stu-id="f7d86-134">For a comprehensive visual debugging experience, the [3D View and Composited Layers are now combined][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView].</span></span>  

:::image type="complex" source="../../media/2020/11/experiments-layers.msft.png" alt-text="合成レイヤーウィンドウ" lightbox="../../media/2020/11/experiments-layers.msft.png":::
   <span data-ttu-id="f7d86-136">**合成レイヤー** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f7d86-136">**Composited Layers** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="f7d86-137">[スタイル] ウィンドウの CSS 変数の定義</span><span class="sxs-lookup"><span data-stu-id="f7d86-137">CSS variable definitions in Styles pane</span></span>  

<!-- Title: Jump to CSS variable definitions  -->  
<!-- Subtitle: Choose any CSS variable to navigate directly to the definition in the Styles tool. -->  

<span data-ttu-id="f7d86-138">[ **スタイル** ] ウィンドウで、 [CSS 変数][MdnUsingCssCustomProperties] が各定義に直接リンクされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-138">In the **Styles** pane, [CSS variables][MdnUsingCssCustomProperties] now link directly to each definition.</span></span>  <span data-ttu-id="f7d86-139">変数を選択して、CSS 変数定義を簡単に表示したり、変更したりします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-139">Choose the variable to easily view or change the CSS variable definition.</span></span>  <span data-ttu-id="f7d86-140">この例では、DevTools に要素の CSS 属性が表示されて `body` います。</span><span class="sxs-lookup"><span data-stu-id="f7d86-140">In the example, DevTools displays the CSS attributes for the `body` element.</span></span>  <span data-ttu-id="f7d86-141">CSS 変数の変数定義を表示するには `--theme-body-background` 、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-141">To display the variable definition for the `--theme-body-background` CSS variable, complete the following actions.</span></span>  

1.  <span data-ttu-id="f7d86-142">[ **スタイル** ] ウィンドウで、を選択し `var(--theme-body-background)` ます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-142">In the **Styles** pane, choose `var(--theme-body-background)`.</span></span>  
1.  <span data-ttu-id="f7d86-143">[ **スタイル** ] ウィンドウに、CSS 変数の定義が表示されるようになりました `--theme-body-background` 。</span><span class="sxs-lookup"><span data-stu-id="f7d86-143">The **Styles** pane now displays the definition of the `--theme-body-background` CSS variable.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support.msft.png" alt-text="スタイルにリンクされた CSS 変数" lightbox="../../media/2020/11/css-variable-support.msft.png":::
         <span data-ttu-id="f7d86-145">スタイルにリンクされた CSS 変数</span><span class="sxs-lookup"><span data-stu-id="f7d86-145">CSS variable linked to the style</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support-target.msft.png" alt-text="Style ターゲットにリンクされた CSS 変数" lightbox="../../media/2020/11/css-variable-support-target.msft.png":::
         <span data-ttu-id="f7d86-147">Style ターゲットにリンクされた CSS 変数</span><span class="sxs-lookup"><span data-stu-id="f7d86-147">CSS variable linked to style target</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="f7d86-148">サービスワーカーのデバッグ機能の改善</span><span class="sxs-lookup"><span data-stu-id="f7d86-148">Service worker debugging improvements</span></span>  

<!-- Title:  Service worker debugging improvements in the Network, Application, and Sources tools  -->  
<!-- Subtitle:  Making service workers easier to debug for progressive web applications and more.  -->  

<span data-ttu-id="f7d86-149">[ネットワーク](#network-tool)、[アプリケーション](#application-tool)、[ソース](#sources-tool)の各ツールの次の新機能を使うと、 [PWA][ProgressiveWebAppsChromiumIndex]を構築することができます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-149">The following new features in the [Network](#network-tool), [Application](#application-tool), and [Sources](#sources-tool) tools help you build your [PWA][ProgressiveWebAppsChromiumIndex].</span></span>  <span data-ttu-id="f7d86-150">サービスワーカーのデバッグが困難な場合は、次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-150">Use the following features when you have difficulty debugging your service worker.</span></span>  

<span data-ttu-id="f7d86-151">[ルーティングの要求] は、 `startup` `fetch` サービスワーカーによって実行されるネットワーク要求に基づいて、およびイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-151">Request routing displays the `startup` and `fetch` events based on the network requests that run through service workers.</span></span>  <span data-ttu-id="f7d86-152">タイムラインには、 **アプリケーション** または **ネットワーク** ツールからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-152">The timelines are accessed from either the **Application** or **Network** tool.</span></span>  <span data-ttu-id="f7d86-153">タイムラインは、service worker の問題が発生していて、or イベントに何らかの問題があるかどうかを確認したい場合に役立ち `startup` `fetch` ます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-153">The timelines help when you are having trouble with service workers and want to see if something is wrong with the `startup` or `fetch` event.</span></span>  

### <span data-ttu-id="f7d86-154">アプリケーションツール</span><span class="sxs-lookup"><span data-stu-id="f7d86-154">Application tool</span></span>  

<!-- Title: Open Network tool from the Service Workers pane  -->  
<!-- Subtitle: Display additional context when debugging a service worker.  -->  

<span data-ttu-id="f7d86-155">[新しい **ネットワーク要求** ] リンクを使用して、すべてのサービスワーカー要求ルーティング情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-155">View all service worker request routing information with the new **Network requests** link.</span></span>  <span data-ttu-id="f7d86-156">サービスワーカーのデバッグ時に追加のコンテキストを表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-156">To display additional context when debugging the service worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="f7d86-157">**アプリケーション**サービスの担当  >  **者**に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-157">Navigate to **Application** > **Service Workers**.</span></span>  
1.  <span data-ttu-id="f7d86-158">[ **ネットワーク要求**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-158">Choose **Network requests**.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-requests.msft.png" alt-text="[Service Worker] ウィンドウからネットワークツールを開く" lightbox="../../media/2020/11/service-worker-application-network-requests.msft.png":::
       <span data-ttu-id="f7d86-160">[ **Service worker** ] ウィンドウから**ネットワーク**ツールを開く</span><span class="sxs-lookup"><span data-stu-id="f7d86-160">Open **Network** tool from the **Service Workers** pane</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="f7d86-161">[ **ネットワーク** ] ツールが **引き出し** で開き、すべてのサービスワーカー関連のネットワーク要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-161">The **Network** tool opens in the **drawer** and displays all service worker-related network requests.</span></span>  <span data-ttu-id="f7d86-162">ネットワーク要求は、を使ってフィルター処理され `is:service-worker-intercepted` ます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-162">The network requests are filtered using `is:service-worker-intercepted`.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-drawer.msft.png" alt-text="ドロアーのネットワークツール" lightbox="../../media/2020/11/service-worker-application-network-drawer.msft.png":::
       <span data-ttu-id="f7d86-164">**ドロアー**の**ネットワーク**ツール</span><span class="sxs-lookup"><span data-stu-id="f7d86-164">**Network** tool in **drawer**</span></span>  
    :::image-end:::
    
1. <span data-ttu-id="f7d86-165">**ネットワーク**ツールを上のパネルに戻すには、**引き出し**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-165">To return the **Network** tool to the top panel, close the **drawer**.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-return.msft.png" alt-text="ネットワークツールを戻すには、[引き出し] を閉じます。" lightbox="../../media/2020/11/service-worker-application-network-return.msft.png":::
       <span data-ttu-id="f7d86-167">**ネットワーク**ツールを戻すには、[**引き出し**] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-167">Close the **drawer** to return **Network** tool</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f7d86-168">ネットワークツール</span><span class="sxs-lookup"><span data-stu-id="f7d86-168">Network tool</span></span>  

<span data-ttu-id="f7d86-169">サービスワーカーを通じて実行されるネットワーク要求をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-169">Debug network requests that run through service workers.</span></span>  <span data-ttu-id="f7d86-170">また、 **アプリケーション** ツールからネットワーク要求を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-170">You may also open network requests from the **Application** tool.</span></span>  <span data-ttu-id="f7d86-171">各要求について、DevTools では、[ [タイミング][DevtoolsNetworkReferenceViewTimingBreakdownRequest] ] ウィンドウに次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-171">For each request, DevTools display the following information in the [Timing][DevtoolsNetworkReferenceViewTimingBreakdownRequest] pane.</span></span>  

*   <span data-ttu-id="f7d86-172">要求の開始とブートストラップの期間。</span><span class="sxs-lookup"><span data-stu-id="f7d86-172">The start of a request and duration of the bootstrap.</span></span>  
*   <span data-ttu-id="f7d86-173">サービスワーカー登録の変更。</span><span class="sxs-lookup"><span data-stu-id="f7d86-173">Changes to service worker registration.</span></span>  
*   <span data-ttu-id="f7d86-174">イベントハンドラーの実行時 `fetch` 。</span><span class="sxs-lookup"><span data-stu-id="f7d86-174">The runtime of a `fetch` event handler.</span></span>  
*   <span data-ttu-id="f7d86-175">`fetch`クライアントを読み込むすべてのイベントのランタイム。</span><span class="sxs-lookup"><span data-stu-id="f7d86-175">The runtime of all `fetch` events for loading a client.</span></span>  
    
:::image type="complex" source="../../media/2020/11/network-timing-service-worker.msft.png" alt-text="タイミングウィンドウ" lightbox="../../media/2020/11/network-timing-service-worker.msft.png":::
   <span data-ttu-id="f7d86-177">**タイミング** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f7d86-177">**Timing** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="f7d86-178">ソースツール</span><span class="sxs-lookup"><span data-stu-id="f7d86-178">Sources tool</span></span>  

<span data-ttu-id="f7d86-179">以前のバージョンの Microsoft Edge では、コールスタックの深度レベルは、サービスワーカーの JavaScript コードに制限されていました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-179">In previous versions of Microsoft Edge, the level of depth in the call stack was limited to the JavaScript code in your service worker.</span></span>  <span data-ttu-id="f7d86-180">Microsoft Edge 88 では、呼び出し履歴にサービスワーカーを通じて実行される要求のイニシエーターが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-180">In Microsoft Edge 88, the call stack now displays the initiator of requests that run through your service worker.</span></span>  

<span data-ttu-id="f7d86-181">要求のイニシエーターを見つけるには、サービスワーカーの JavaScript コードのコールスタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-181">To locate the initiator of the request, use the call stack of your JavaScript code in the service worker.</span></span>  <span data-ttu-id="f7d86-182">次の図のコールスタックは、サービスワーカーの JavaScript コードから始まり、元の web ページの要求としての参照を表示し `(index):157` ます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-182">The call stack in the following figures starts with the JavaScript code in your service worker and displays a reference to the original webpage request as `(index):157`.</span></span>  <span data-ttu-id="f7d86-183">2番目の図では、参照が選択され、要求を行ったイニシエーターが開かれています。</span><span class="sxs-lookup"><span data-stu-id="f7d86-183">In the second figure, the reference is chosen and opened the initiator that made the request.</span></span>  <span data-ttu-id="f7d86-184">2番目の図のイニシエーターは web ページです。</span><span class="sxs-lookup"><span data-stu-id="f7d86-184">The initiator in the second figure is the webpage.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png" alt-text="要求元の service-worker.js ファイルとコールスタックの強調表示" lightbox="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png":::
         <span data-ttu-id="f7d86-186">要求の送信 `service-worker.js` 元を強調表示したファイルとコールスタック</span><span class="sxs-lookup"><span data-stu-id="f7d86-186">The `service-worker.js` file and call stack highlighting request originator</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-call-stack-target.msft.png" alt-text="(インデックス) web ページが要求の開始者である" lightbox="../../media/2020/11/service-worker-sources-call-stack-target.msft.png":::
         <span data-ttu-id="f7d86-188">`(index)`Web ページが要求の開始者である</span><span class="sxs-lookup"><span data-stu-id="f7d86-188">The `(index)` webpage is the request initiator</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="f7d86-189">ネットワーク要求のプロパティ値をコピーする</span><span class="sxs-lookup"><span data-stu-id="f7d86-189">Copy property value of a network request</span></span>  

<!-- Title: Copy response JSON in Network tool using the contextual menu  -->  
<!-- Subtitle:  The Network tool now has a more consistent UX.  Easily copy the JSON response using the contextual menu.  -->  

<span data-ttu-id="f7d86-190">[ **ネットワーク** ツール] で、[新しい **値のコピー** ] オプションを使用して、ネットワーク要求のプロパティの値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-190">In the **Network** tool, copy the property value of a network request using the new **Copy value** option.</span></span>  <span data-ttu-id="f7d86-191">プロパティ値はデコードされた JSON 値としてコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-191">The property value is copied as a decoded JSON value.</span></span>  <span data-ttu-id="f7d86-192">以前のバージョンの Microsoft Edge では、次のいずれかのアクションを使用して値をコピーする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-192">In previous versions of Microsoft Edge, you had to copy a value using one of the following actions.</span></span>  

*   <span data-ttu-id="f7d86-193">テキスト全体を強調表示してコピーします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-193">Highlight the entire text and copy it.</span></span>  
*   <span data-ttu-id="f7d86-194">該当する場合はグローバル変数として値を保存し、DevTools [コンソール][DevtoolsConsoleIndex]からコピーします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-194">Store the value as global variable, as applicable, and copy it from the DevTools [Console][DevtoolsConsoleIndex].</span></span>  
    
<span data-ttu-id="f7d86-195">プロパティの値をクリップボードにコピーするには、[ [書式設定された応答 JSON をクリップボードにコピー][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-195">To copy the property value to your clipboard, navigate to [Copy formatted response JSON to the clipboard][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard].</span></span>  <span data-ttu-id="f7d86-196">Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、「案件 [1132084][CR1132084]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-196">To review the history of this feature in the Chromium open-source project, navigate to Issue [1132084][CR1132084].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/copy-property-value.msft.png" alt-text="DevTools でのプロパティ値のコピー" lightbox="../../media/2020/11/copy-property-value.msft.png":::
         <span data-ttu-id="f7d86-198">DevTools でのプロパティ値のコピー</span><span class="sxs-lookup"><span data-stu-id="f7d86-198">Copy property value in DevTools</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/paste-property-value.msft.png" alt-text="Visual Studio コードでのプロパティ値の貼り付け" lightbox="../../media/2020/11/paste-property-value.msft.png":::
         <span data-ttu-id="f7d86-200">Visual Studio コードでのプロパティ値の貼り付け</span><span class="sxs-lookup"><span data-stu-id="f7d86-200">Paste property value in Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="f7d86-201">マルチキーボードショートカットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="f7d86-201">Customize multi-press keyboard shortcuts</span></span>  

<!-- Title: Customize multi-press keyboard shortcuts  -->  
<!-- Subtitle: Create custom multi-press keyboard shortcuts in the shortcut editor.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

<span data-ttu-id="f7d86-202">[Microsoft Edge バージョン87以降][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]では、devtools で操作のキーボードショートカットをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-202">[Since Microsoft Edge version 87][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings], you may customize keyboard shortcuts for any action in DevTools.</span></span>  <span data-ttu-id="f7d86-203">Microsoft Edge バージョン88では、複数のキーボードショートカットを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-203">In Microsoft Edge version 88, you may now create multi-press keyboard shortcuts.</span></span>  <span data-ttu-id="f7d86-204">Devtools で操作のショートカットを設定するには、[[設定][DevtoolsCustomizeIndexSettings]の試験] に移動  >  \*\*\*\* し、[**キーボードショートカットエディターを有効**にする] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-204">To set a shortcut for an action in the DevTools, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="f7d86-205">ショートカットのカスタマイズと編集について詳しくは、「 [キーボードショートカットエディターの実験的機能を有効][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d86-205">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="f7d86-206">たとえば、赤色の強調表示は、[記録して **イベントを開始** ] アクション用にカスタマイズされた複数のキーボードショートカットを示しています。</span><span class="sxs-lookup"><span data-stu-id="f7d86-206">For example, the red highlight displays a multi-press keyboard shortcut customized for the **Start recording events** action.</span></span>  <span data-ttu-id="f7d86-207">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[ [問題の #174309][CR174309]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-207">To review real-time updates on this feature in the Chromium open-source project, navigate to [Issue #174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png" alt-text="弦のショートカットキー" lightbox="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png":::
   <span data-ttu-id="f7d86-209">複数のキーボードショートカットを使用する</span><span class="sxs-lookup"><span data-stu-id="f7d86-209">Multi-press keyboard shortcuts</span></span>  
:::image-end:::  

## <span data-ttu-id="f7d86-210">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="f7d86-210">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="f7d86-211">新しい CSS アングル視覚エフェクトツール</span><span class="sxs-lookup"><span data-stu-id="f7d86-211">New CSS angle visualization tools</span></span>  

<span data-ttu-id="f7d86-212">DevTools で CSS アングルデバッギングのサポートが強化されました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-212">DevTools now have better support for CSS angle debugging.</span></span>  <span data-ttu-id="f7d86-213">ページの HTML 要素に CSS アングルが適用されている場合、 **スタイル** ツールの角度の横に時計アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-213">When an HTML element on your page has CSS angle applied to it, a clock icon is displayed next to the angle in the **Styles** tool.</span></span>  <span data-ttu-id="f7d86-214">時計のオーバーレイを切り替えるには、時計アイコンを選びます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-214">To toggle the clock overlay, choose the clock icon.</span></span>  <span data-ttu-id="f7d86-215">角度を変更するには、時計の任意の場所を選ぶか、または針をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-215">To change the angle, choose anywhere in the clock or drag the needle.</span></span>  <span data-ttu-id="f7d86-216">[角度] の値を変更するには、マウスとキーボードのショートカットを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-216">To change the angle value, you may also use mouse and keyboard shortcuts.</span></span>  <!--  To learn more, navigate to [Angle Clock][DevtoolsCssReferenceChangeAngleValueWithAngleClock].  -->  <span data-ttu-id="f7d86-217">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [1126178][CR1126178] および [1138633][CR1138633]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-217">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1126178][CR1126178] and [1138633][CR1138633].</span></span>  

<!--todo:  add link when css angle clock section exists.  -->  

<span data-ttu-id="f7d86-218">この例では、次の CSS アングルが使われています。</span><span class="sxs-lookup"><span data-stu-id="f7d86-218">The following CSS angle is used for the example.</span></span>  

```css
background: linear-gradient(100deg, lightblue, pink);
```  

:::image type="complex" source="../../media/2020/11/css-angle.msft.png" alt-text="CSS アングル" lightbox="../../media/2020/11/css-angle.msft.png":::
   <span data-ttu-id="f7d86-220">CSS アングル</span><span class="sxs-lookup"><span data-stu-id="f7d86-220">CSS angle</span></span>  
:::image-end:::  

### <span data-ttu-id="f7d86-221">[記憶域] ウィンドウで記憶域のクォータサイズをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="f7d86-221">Simulate storage quota size in the Storage pane</span></span>  

<span data-ttu-id="f7d86-222">**ストレージ**ウィンドウでストレージのクォータサイズを上書きできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-222">You may now override storage quota size in the **Storage** pane.</span></span>  <span data-ttu-id="f7d86-223">この機能により、さまざまなデバイスをシミュレートし、ディスク可用性の低いシナリオで web サイトやアプリの動作をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-223">This feature allows you to simulate different devices and test the behavior of your website or app in low disk availability scenarios.</span></span>  <span data-ttu-id="f7d86-224">記憶域のクォータをシミュレートするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-224">To simulate the storage quota, complete the following actions.</span></span>  

1.  <span data-ttu-id="f7d86-225">**アプリケーション**  >  **ストレージ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-225">Navigate to **Application** > **Storage**.</span></span>  
1.  <span data-ttu-id="f7d86-226">[ **カスタム記憶域クォータのシミュレート** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-226">Turn on the **Simulate custom storage quota** checkbox.</span></span>  
1.  <span data-ttu-id="f7d86-227">有効な番号を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f7d86-227">Enter a valid number.</span></span>  
    
<span data-ttu-id="f7d86-228">モバイルデバイスやその他の機能を開発ツールでエミュレートする方法の詳細については、「 [Microsoft Edge DevTools でモバイルデバイスをエミュレートする」 ][DevtoolsDeviceModeIndex]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d86-228">For more information about how to emulate mobile devices and other features in the DevTools, navigate to [Emulate mobile devices in Microsoft Edge DevTools ][DevtoolsDeviceModeIndex].</span></span>  <span data-ttu-id="f7d86-229">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [945786][CR945786] および [1146985][CR1146985]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-229">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [945786][CR945786] and [1146985][CR1146985].</span></span>  

:::image type="complex" source="../../media/2020/11/storage-quota.msft.png" alt-text="記憶域のクォータサイズのシミュレート" lightbox="../../media/2020/11/storage-quota.msft.png":::
   <span data-ttu-id="f7d86-231">記憶域のクォータサイズのシミュレート</span><span class="sxs-lookup"><span data-stu-id="f7d86-231">Simulate storage quota size</span></span>  
:::image-end:::  

### <span data-ttu-id="f7d86-232">ネットワークツールで CORS エラーを報告する</span><span class="sxs-lookup"><span data-stu-id="f7d86-232">Report CORS errors in the Network tool</span></span>  

<span data-ttu-id="f7d86-233">この機能を試すには、「 [CORS エラーデモ][GlitchCorsErrors]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-233">Try out this feature by navigating to [CORS error demo][GlitchCorsErrors].</span></span>  <span data-ttu-id="f7d86-234">**ネットワーク**ツールを開き、ページを更新して、失敗した CORS ネットワーク要求を確認します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-234">Open the **Network** tool, refresh the page, and observe the failed CORS network request.</span></span>  <span data-ttu-id="f7d86-235">[状態の列には、 **CORS エラー**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-235">The status column displays the **CORS error**.</span></span>  <span data-ttu-id="f7d86-236">エラーをポイントすると、ヒントにエラーコードが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-236">When you hover on the error, the tooltip now displays the error code.</span></span>  <span data-ttu-id="f7d86-237">Microsoft Edge バージョン87以前の DevTools では、CORS エラーの一般的な (失敗した) 状態しか表示され **ませんでした** 。</span><span class="sxs-lookup"><span data-stu-id="f7d86-237">In Microsoft Edge version 87 and earlier, DevTools only displayed generic **(failed)** status for CORS errors.</span></span>  <span data-ttu-id="f7d86-238">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題 [1141824][CR1141824]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-238">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1141824][CR1141824].</span></span>  

:::image type="complex" source="../../media/2020/11/cors-err.msft.png" alt-text="CORS エラー" lightbox="../../media/2020/11/cors-err.msft.png":::
   <span data-ttu-id="f7d86-240">CORS エラー</span><span class="sxs-lookup"><span data-stu-id="f7d86-240">CORS errors</span></span>  
:::image-end:::  

### <span data-ttu-id="f7d86-241">フレームの詳細ビューの更新</span><span class="sxs-lookup"><span data-stu-id="f7d86-241">Frame details view updates</span></span>  

#### <span data-ttu-id="f7d86-242">フレームの詳細表示のクロスオリジンの分離情報</span><span class="sxs-lookup"><span data-stu-id="f7d86-242">Cross-origin isolation information in the Frame details view</span></span>  

<span data-ttu-id="f7d86-243">[ **セキュリティ & 分離** ] セクションの下に、クロスオリジン分離ステータスが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-243">The cross-origin isolated status is now displayed under the **Security & Isolation** section.</span></span>  <span data-ttu-id="f7d86-244">[新しい **API の可用性** ] セクションには、 `SharedArrayBuffer` s \ (sab \) の空き時間と、バッファーを使用して共有できるかどうかが表示され `postMessage()` ます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-244">The new **API availability** section displays the availability of `SharedArrayBuffer`s \(SAB\) and whether the buffers may be shared using `postMessage()`.</span></span>  <span data-ttu-id="f7d86-245">非推奨警告は、SAB と現在利用可能な場合に表示され `postMessage()` ますが、コンテキストはクロスオリジン分離されません。</span><span class="sxs-lookup"><span data-stu-id="f7d86-245">A deprecation warning displays if the SAB and `postMessage()` is currently available, but the context is not cross-origin isolated.</span></span>  <span data-ttu-id="f7d86-246">クロスオリジン分離およびそのような機能に必要な理由の詳細については `SharedArrayBuffers` 、「 [WindowOrWorkerGlobalScope][MdnWindoworworkerglobalscopeCrossoriginisolated]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d86-246">For more information about cross-origin isolation and why it is required for features like `SharedArrayBuffers`, navigate to [WindowOrWorkerGlobalScope.crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated].</span></span>  <span data-ttu-id="f7d86-247">Chromium のオープンソースプロジェクトでこの機能のリアルタイムの更新を確認するには、「案件 [1139899][CR1139899]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-247">To review real-time updates of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2020/11/frame-cross-origin-isolated-api.msft.png" alt-text="Cross-origin 情報" lightbox="../../media/2020/11/frame-cross-origin-isolated-api.msft.png":::
   <span data-ttu-id="f7d86-249">Cross-origin 情報</span><span class="sxs-lookup"><span data-stu-id="f7d86-249">Cross-origin information</span></span>  
:::image-end:::  

#### <span data-ttu-id="f7d86-250">フレームの詳細表示の新しい Web ワーカー情報</span><span class="sxs-lookup"><span data-stu-id="f7d86-250">New Web Workers information in the Frame details view</span></span>  

<span data-ttu-id="f7d86-251">DevTools は、web ワーカーを関連する親フレームの下に整理するようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-251">DevTools now organizes web workers under the relevant parent frame.</span></span>  <span data-ttu-id="f7d86-252">たとえば、フレームで作成された場合は、 `someName` `worker.js` `worker.js` [フレーム] の一覧の下に表示され `someName` ます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f7d86-252">For example, if the `someName` frame creates `worker.js`, then `worker.js` appears under `someName` in the **Frames** list.</span></span>  <span data-ttu-id="f7d86-253">Web worker の詳細を表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-253">To view the details of the web worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="f7d86-254">**アプリケーション**ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-254">Open **Application** tool.</span></span>  
1.  <span data-ttu-id="f7d86-255">Web ワーカーを含むフレームを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-255">Expand a frame that contains web workers.</span></span>  
1.  <span data-ttu-id="f7d86-256">[ **社員** ] ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-256">Expand the **Workers** tree.</span></span>  
1.  <span data-ttu-id="f7d86-257">作業者を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-257">Choose a worker.</span></span>  
    
<span data-ttu-id="f7d86-258">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [1122507][CR1122507] および [1051466][CR1051466]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-258">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1122507][CR1122507] and [1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/11/application-frames-service-workers.msft.png" alt-text="Web ワーカー情報" lightbox="../../media/2020/11/application-frames-service-workers.msft.png":::
   <span data-ttu-id="f7d86-260">Web ワーカー情報</span><span class="sxs-lookup"><span data-stu-id="f7d86-260">Web workers information</span></span>  
:::image-end:::  

#### <span data-ttu-id="f7d86-261">開いているウィンドウの opener フレームの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="f7d86-261">Display opener frame details for opened windows</span></span>  

<span data-ttu-id="f7d86-262">DevTools では、開いている [ウィンドウ][MdnWindowConstructors] が関連する親 [フレーム][MdnWindowFrames]の下に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-262">DevTools now organizes opened [Windows][MdnWindowConstructors] under the relevant parent [frame][MdnWindowFrames].</span></span>  <span data-ttu-id="f7d86-263">たとえば、 `top` フレームで `Window` をクリックすると、[ `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium` `Window` フレーム] の一覧の下に表示され `top` ます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f7d86-263">For example, if the `top` frame opens a `Window` to `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium`, then the `Window` appears under `top` in the **Frames** list.</span></span>  

<span data-ttu-id="f7d86-264">[ **要素** ] ツールで別のウィンドウを開くためのフレームを表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-264">To reveal the frame responsible for opening another Window in the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="f7d86-265">[ **フレーム** ] ツリーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-265">Open the **Frames** tree.</span></span>  
1.  <span data-ttu-id="f7d86-266">[ **開い** ているウィンドウ] を展開し、 `Window` 確認したい親フレームのを選びます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-266">Expand **Opened Windows** and choose the `Window` for the parent frame you want to know.</span></span>  
1.  <span data-ttu-id="f7d86-267">[ **Opener Frame** ] リンクを選びます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-267">Choose the **Opener Frame** link.</span></span>  

<span data-ttu-id="f7d86-268">詳細は、別のフレームを開くフレームについて表示され `Window` ます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-268">The details are displayed about which frame caused the opening of another `Window`.</span></span>  <span data-ttu-id="f7d86-269">**Elements**ツールで opener を表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-269">To reveal the opener in the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="f7d86-270">[ **フレーム** ] ツリーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-270">Open the **Frames** tree.</span></span>  
1.  <span data-ttu-id="f7d86-271">開いているウィンドウを選択して詳細を表示し `Window` ます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-271">Choose an opened window to open the `Window` details.</span></span>  
1.  <span data-ttu-id="f7d86-272">[ **Opener Frame** ] リンクを選びます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-272">Choose the **Opener Frame** link.</span></span>  
    
<span data-ttu-id="f7d86-273">Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、「案件 [1107766][CR1107766]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-273">To review the history of this feature in the Chromium open-source project, navigate to Issue [1107766][CR1107766].</span></span>  

:::image type="complex" source="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png" alt-text="開いているフレームの詳細" lightbox="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png":::
   <span data-ttu-id="f7d86-275">開いているフレームの詳細</span><span class="sxs-lookup"><span data-stu-id="f7d86-275">Opened frame details</span></span>  
:::image-end:::  

### <span data-ttu-id="f7d86-276">ネットワークイニシエーターの stacktrace をコピーする</span><span class="sxs-lookup"><span data-stu-id="f7d86-276">Copy stacktrace for network initiator</span></span>  

<span data-ttu-id="f7d86-277">Stacktrace をクリップボードにコピーするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-277">To copy the stacktrace to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="f7d86-278">コンテキストメニューを開きます (\ [\] を右クリックします)。</span><span class="sxs-lookup"><span data-stu-id="f7d86-278">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="f7d86-279">[ **Copy**  >  **copy stacktrace**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-279">Choose **Copy** > **Copy stacktrace**.</span></span>  
    
<span data-ttu-id="f7d86-280">Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、「案件 [1139615][CR1139615]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-280">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139615][CR1139615].</span></span>

:::image type="complex" source="../../media/2020/11/copy-stacktrace.msft.png" alt-text="Stacktrace をコピーする" lightbox="../../media/2020/11/copy-stacktrace.msft.png":::
   <span data-ttu-id="f7d86-282">Stacktrace をコピーする</span><span class="sxs-lookup"><span data-stu-id="f7d86-282">Copy stacktrace</span></span>  
:::image-end:::  

### <span data-ttu-id="f7d86-283">マウスを置いたときの Wasm 変数値のプレビュー</span><span class="sxs-lookup"><span data-stu-id="f7d86-283">Preview Wasm variable value on mouseover</span></span>  

<span data-ttu-id="f7d86-284">この機能を使用すると、コードが一時停止されているときに、(Wasm \) 変数の値を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-284">Use this feature to review the value of a WebAssembly \(Wasm\) variable when your code is paused.</span></span>  <span data-ttu-id="f7d86-285">変数の現在の値を表示するには、変数をポイントします。</span><span class="sxs-lookup"><span data-stu-id="f7d86-285">To display the current value of a variable, hover on a variable.</span></span>  <span data-ttu-id="f7d86-286">Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [1058836][CR1058836] および [1071432][CR1071432]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-286">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1058836][CR1058836] and [1071432][CR1071432].</span></span>  

:::image type="complex" source="../../media/2020/11/wasm-mouseover.msft.png" alt-text="マウスの上に表示される Wasm 変数のプレビュー" lightbox="../../media/2020/11/wasm-mouseover.msft.png":::
   <span data-ttu-id="f7d86-288">マウスの上に表示される Wasm 変数のプレビュー</span><span class="sxs-lookup"><span data-stu-id="f7d86-288">Preview Wasm variable on mouseover</span></span>  
:::image-end:::  

### <span data-ttu-id="f7d86-289">ファイルとメモリのサイズの一定の測定単位</span><span class="sxs-lookup"><span data-stu-id="f7d86-289">Consistent units of measurement for sizes of files and memory</span></span>  

<span data-ttu-id="f7d86-290">DevTools `kB` は、ファイルとメモリのサイズを表示するために一貫して使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-290">DevTools now consistently use `kB` for displaying sizes of files and memory.</span></span>  <span data-ttu-id="f7d86-291">以前の DevTools `kB` と `KiB` の混在。</span><span class="sxs-lookup"><span data-stu-id="f7d86-291">Previously DevTools mixed `kB` and `KiB`.</span></span>

*   `kB` <span data-ttu-id="f7d86-292">またはキロバイト \ (10 ^ 3 または1000バイト)</span><span class="sxs-lookup"><span data-stu-id="f7d86-292">or kilobyte \(10^3 or 1000 bytes\)</span></span>  
*   `KiB` <span data-ttu-id="f7d86-293">または kibibyte \ (2 ^ 10 または1024バイト)</span><span class="sxs-lookup"><span data-stu-id="f7d86-293">or kibibyte \(2^10 or 1024 bytes\)</span></span>  
    
<span data-ttu-id="f7d86-294">たとえば、以前は\*\*\*\* ラベルで使用した `kB` が、計算に使用されたネットワークツールなどです `KiB` 。</span><span class="sxs-lookup"><span data-stu-id="f7d86-294">For example, the **Network** tool previously used `kB` in the labels, but used `KiB` in calculations.</span></span>  <span data-ttu-id="f7d86-295">この不整合により混乱が生じたことがフィードバックに示されました。</span><span class="sxs-lookup"><span data-stu-id="f7d86-295">Your feedback showed that this inconsistency caused confusion.</span></span>  <span data-ttu-id="f7d86-296">Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、「案件 [1035309][CR1035309]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7d86-296">To review the history of this feature in the Chromium open-source project, navigate to Issue [1035309][CR1035309].</span></span>  

## <span data-ttu-id="f7d86-297">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f7d86-297">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="f7d86-298">Windows、Linux、または macOS を使用している場合は、既定の開発ブラウザーとして [Microsoft Edge preview channels] [MicrosoftEdgePreviewChannels] を使うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f7d86-298">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="f7d86-299">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-299">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="f7d86-300">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="f7d86-300">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[Devtools3dViewIndex]: /microsoft-edge/devtools-guide-chromium/3d-view/index "3D ビュー |Microsoft ドキュメント"  
[DevtoolsConsoleIndex]: /microsoft-edge/devtools-guide-chromium/console/index "本体の概要 |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイルデバイスをエミュレートする |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボードショートカットエディターを有効にする-実験的な機能 |microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-composited-layers-in-3d-view "3D ビューでの合成レイヤーの有効化-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]: /microsoft-edge/devtools-guide-chromium/network/reference#copy-formatted-response-json-to-the-clipboard "書式設定された応答の JSON をクリップボードにコピーする-ネットワーク分析のリファレンス |Microsoft ドキュメント"  
[DevtoolsNetworkReferenceViewTimingBreakdownRequest]: /microsoft-edge/devtools-guide-chromium/network/reference#view-the-timing-breakdown-of-a-request "要求のタイミングの内訳を表示する-ネットワーク分析のリファレンス |Microsoft ドキュメント"  
[WebDriverChromiumMain]: /microsoft-edge/webdriver-chromium "テストオートメーションに WebDriver (Chromium) を使います。Microsoft ドキュメント"  

<!--  [DevtoolsCssReferenceChangeAngleValueWithAngleClock]: /microsoft-edge/devtools-guide-chromium/css/reference#change-angle-value-with-the-angle-clock "Change angle value with the Angle Clock - CSS reference | Microsoft Docs"  -->  

[ProgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ |Microsoft ドキュメント"  

[WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/10/devtools#customize-keyboard-shortcuts-in-settings "設定のショートカットキーをカスタマイズする-DevTools の新機能 (Microsoft Edge 87) |Microsoft ドキュメント"  
[WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools#webhint-feedback-in-the-issues-panel "[問題] パネルでの webhint のフィードバック-DevTools の新機能 (Microsoft Edge 85) |Microsoft ドキュメント"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "WebDriver をダウンロード |Microsoft 開発者"  

[MicrosoftinsiderDownloadPlatformLinux]: https://www.microsoftedgeinsider.com/download?platform=linux "Microsoft Edge Insider チャネルをダウンロードする"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio コード"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR174309]: https://crbug.com/174309 "問題 174309: DevTools: キーボードショートカットとキーバインディングのカスタマイズを許可する |Chromium のバグ"  
[CR945786]: https://crbug.com/945786 "問題 945786: DevTools: 「ナビゲーターの上書きを許可する」の推定 () |Chromium のバグ"  
[CR1029427]: https://crbug.com/1029427 "問題 1029427: フロントエンドでのプロトコルメッセージディスパッチのパフォーマンスのオーバーヘッドを削減する |Chromium のバグ"  
[CR1035309]: https://crbug.com/1035309 "問題 1035309: DevTools では、mebibyte ではなく、MB を平均して MB を使用する必要があります。Chromium のバグ"  
[CR1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での CO-OP/COEP のデバッグのサポート |Chromium のバグ"  
[CR1058836]: https://crbug.com/1058836 "問題 1058836: Wasm のデバッグに関する UX の問題 |Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "問題 1071432: ☂️ Wasm Basic 開発者エクスペリエンス |Chromium のバグ"  
[CR1107766]: https://crbug.com/1107766 "問題 1107766: 「window. open ()」 (frame tree) で生成されたフレームについての情報を表示する |Chromium のバグ"  
[CR1122507]: https://crbug.com/1122507 "問題 1122507: フレームツリービューでの Surface worker 情報 |Chromium のバグ"  
[CR1126178]: https://crbug.com/1126178 "問題 1126178: ☂ DevTools: CSS <種類> コンポーネントを入力します。Chromium のバグ"  
[CR1130556]: https://crbug.com/1130556 "問題 1130556: DevTools: テストイメージフォールバック (エミュレーション) |Chromium のバグ"  
[CR1132084]: https://crbug.com/1132084 "問題 1132084: JSON 要求ペイロードを簡単にコピーする方法はありません |Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox のツール |Chromium のバグ"  
[CR1138633]: https://crbug.com/1138633 "問題 1138633: DevTools: CSS <angle> component は、時計の背景に存在するプロパティの外観を反映する必要があります。Chromium のバグ"  
[CR1139615]: https://crbug.com/1139615 "問題 1139615: ネットワークイニシエーターは、スタックトレースをコピーする機能を提供する必要があります。 |Chromium のバグ"  
[CR1139899]: https://crbug.com/1139899 "問題 1139899: フレームの詳細表示でのゲート API の可用性レポート |Chromium のバグ"  
[CR1139945]: https://crbug.com/1139945 "問題 1139945: [スタイル] パネルでの flexbox CSS プロパティのアイコン |Chromium のバグ"  
[CR1141824]: https://crbug.com/1141824 "問題 1141824: DevTools で CORS のエラー報告を改善するChromium のバグ"  
[CR1144090]: https://crbug.com/1144090 "問題 1144090: 柔軟なスタイルの装飾を要素ツリーに追加する |Chromium のバグ"  
[CR1146985]: https://crbug.com/1146985 "問題 1146985: クリアテキストは、「Dev Tools」ウィンドウの「ストレージ」セクションのテキストボックスに引き続き表示されます。Chromium のバグ"  

[GlitchCorsErrors]: https://cors-errors.glitch.me "CORS のエラー |故障"  

[MdnCors]: https://developer.mozilla.org/docs/Web/HTTP/CORS "クロスオリジンリソース共有 (CORS) |MDN"  
[MdnUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "CSS カスタムプロパティ (変数) を使用する |MDN"  
[MdnWindowConstructors]: https://developer.mozilla.org/docs/Web/API/Window#Constructors "コンストラクター-Window |MDN"  
[MdnWindowFrames]: https://developer.mozilla.org/docs/Web/API/Window/frames "ウィンドウ。フレーム |MDN"  
[MdnWindoworworkerglobalscopeCrossoriginisolated]: https://developer.mozilla.org/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated "WindowOrWorkerGlobalScope の分離 |MDN"  

[WebhintMain]: https://webhint.io "web ヒント"  
[WebhintUserGuideHintsAccessibility]: https://webhint.io/docs/user-guide/hints/accessibility "アクセシビリティ |web ヒント"  
[WebhintUserGuideHintsCompatibility]: https://webhint.io/docs/user-guide/hints/compatibility "互換性 |web ヒント"  
[WebhintUserGuideHintsPerformance]: https://webhint.io/docs/user-guide/hints/performance "パフォーマンス |web ヒント"  
[WebhintUserGuideHintsPitfalls]: https://webhint.io/docs/user-guide/hints/pitfalls "落とし穴 |web ヒント"  
[WebhintUserGuideHintsPwa]: https://webhint.io/docs/user-guide/hints/pwa "PWA |web ヒント"  
[WebhintUserGuideHintsSecurity]: https://webhint.io/docs/user-guide/hints/security "セキュリティ |web ヒント"  

> [!NOTE]
> <span data-ttu-id="f7d86-351">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7d86-351">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f7d86-352">元のページは [ここ](https://developers.google.com/web/updates/2020/11/devtools/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。</span><span class="sxs-lookup"><span data-stu-id="f7d86-352">The original page is found [here](https://developers.google.com/web/updates/2020/11/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f7d86-354">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f7d86-354">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
