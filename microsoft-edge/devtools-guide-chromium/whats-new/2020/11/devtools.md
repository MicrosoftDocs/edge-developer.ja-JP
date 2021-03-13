---
description: Linux 上の Microsoft Edge、問題ツールの Webhint ヒントの改善、新しいサービス ワーカー デバッグ機能など。
title: DevTools の新機能 (Microsoft Edge 88)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6a36029aa97604b6aea20f232d329ce3805a3144
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408368"
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
# <a name="whats-new-in-devtools-microsoft-edge-88"></a><span data-ttu-id="ac4ab-104">DevTools の新機能 (Microsoft Edge 88)</span><span class="sxs-lookup"><span data-stu-id="ac4ab-104">What's New in DevTools (Microsoft Edge 88)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="microsoft-edge-and-microsoft-edge-driver-now-available-on-linux"></a><span data-ttu-id="ac4ab-105">Microsoft Edge と Microsoft Edge ドライバーが Linux で利用可能に</span><span class="sxs-lookup"><span data-stu-id="ac4ab-105">Microsoft Edge and Microsoft Edge Driver now available on Linux</span></span>  

<!-- Title: Microsoft Edge and Microsoft Edge Driver on Linux  -->  
<!-- Subtitle: Get Microsoft Edge Dev on Ubuntu, Debian, Fedora, and openSUSE distributions and start automating in CI/CD environments with Microsoft Edge Driver. -->  

<span data-ttu-id="ac4ab-106">Microsoft Edge Dev は、Ubuntu、Debian、Fedora、openSUSE の配布でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-106">Microsoft Edge Dev is now supported on Ubuntu, Debian, Fedora, and openSUSE distributions.</span></span>  <span data-ttu-id="ac4ab-107">Microsoft Edge Dev `.deb`または`.rpm`パッケージを [Microsoft Edge Insider サイト][MicrosoftinsiderDownloadPlatformLinux]から直接ダウンロードしてインストールするか、お使いの Linux 配布の標準パッケージ管理ツールを使用します。 </span><span class="sxs-lookup"><span data-stu-id="ac4ab-107">Download and install the Microsoft Edge Dev `.deb` or `.rpm` package directly from the [Microsoft Edge Insider site][MicrosoftinsiderDownloadPlatformLinux] or use the standard package management tools of your Linux distribution.</span></span>  

<span data-ttu-id="ac4ab-108">継続的インテグレーションおよび配信 \(CI/CD\) ソリューションで Linux 環境を使用している場合は、Linux でも Microsoft Edge ドライバーを利用できます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-108">If you are using a Linux environment in your continuous integration and delivery \(CI/CD\) solutions, Microsoft Edge Driver is also available on Linux.</span></span>  <span data-ttu-id="ac4ab-109">Microsoft Edge ドライバーを使用した Microsoft Edge Dev の自動化を開始する方法については、[Microsoft Edge ドライバーのダウンロードページに移動します][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-109">To get started automating Microsoft Edge Dev with Microsoft Edge Driver, navigate to [Microsoft Edge Driver Downloads page][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads].</span></span>  <span data-ttu-id="ac4ab-110">Microsoft Edge ドライバーと共に Microsoft Edge Dev を自動化する方法については、[「テスト オートメーションに WebDriver (Chromium) を使用する」][WebDriverChromiumMain]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-110">For help with automating Microsoft Edge Dev along with Microsoft Edge Driver, navigate to [Use WebDriver (Chromium) for test automation][WebDriverChromiumMain].</span></span>  

:::image type="complex" source="../../media/2020/11/edge-on-linux.msft.png" alt-text="Linux 上の Microsoft Edge の DevTools" lightbox="../../media/2020/11/edge-on-linux.msft.png":::
   <span data-ttu-id="ac4ab-112">Linux 上の Microsoft Edge の DevTools</span><span class="sxs-lookup"><span data-stu-id="ac4ab-112">DevTools in Microsoft Edge on Linux</span></span>  
:::image-end:::  

## <a name="improved-webhint-and-platform-tips-in-the-issues-tool"></a><span data-ttu-id="ac4ab-113">問題ツールの Webhint とプラットフォームのヒントの向上</span><span class="sxs-lookup"><span data-stu-id="ac4ab-113">Improved webhint and platform tips in the Issues tool</span></span>  

<!-- Title: Improvements to Issues tool and webhint integration  -->  
<!-- Subtitle: Categories and third-party filtering make it easier to survey issues in the Issues tool.  Issues surfaced by webhint now have improved code snippets and documentation links to help you fix problems in your website.  -->  

<span data-ttu-id="ac4ab-114">オープン ソース ツールである [webhint][WebhintMain]は、Web サイトとローカル Web ページに対してリアルタイムでのフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-114">An open-source tool, [webhint][WebhintMain], provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="ac4ab-115">[Microsoft Edge バージョン 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel] から、[問題][DevtoolsIssuesIndex]ツールで webhint フィードバックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-115">Starting with [Microsoft Edge version 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel], review webhint feedback in the [Issues][DevtoolsIssuesIndex] tool.</span></span>  <span data-ttu-id="ac4ab-116">**問題**ツールに表示される問題は、次のカテゴリを追加することで簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-116">Issues that appear in the **Issues** tool are now easier to review with the addition of the following categories.</span></span>  

*   [<span data-ttu-id="ac4ab-117">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="ac4ab-117">Accessibility</span></span>][WebhintUserGuideHintsAccessibility]  
*   [<span data-ttu-id="ac4ab-118">互換性</span><span class="sxs-lookup"><span data-stu-id="ac4ab-118">Compatibility</span></span>][WebhintUserGuideHintsCompatibility]  
*   [<span data-ttu-id="ac4ab-119">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="ac4ab-119">Performance</span></span>][WebhintUserGuideHintsPerformance]  
*   [<span data-ttu-id="ac4ab-120">落とし穴</span><span class="sxs-lookup"><span data-stu-id="ac4ab-120">Pitfalls</span></span>][WebhintUserGuideHintsPitfalls]  
*   [<span data-ttu-id="ac4ab-121">PWA</span><span class="sxs-lookup"><span data-stu-id="ac4ab-121">PWA</span></span>][WebhintUserGuideHintsPwa]  
*   [<span data-ttu-id="ac4ab-122">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ac4ab-122">Security</span></span>][WebhintUserGuideHintsSecurity]  
    
<span data-ttu-id="ac4ab-123">新しいチェックボックスを使用して、サードパーティの問題をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-123">You are now able to filter out third-party issues using a new checkbox.</span></span>  <span data-ttu-id="ac4ab-124">フィルター機能を使用すると、サードパーティ製のライブラリや他のソースからのコードに関連した問題を非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-124">The filter functionality helps you hide issues related to code from third-party libraries or other sources.</span></span>  

<span data-ttu-id="ac4ab-125">[Webhint][WebhintMain] によって表示される問題を確認するために、**問題**ツールに次の情報が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-125">To help you review issues revealed by [webhint][WebhintMain], the **Issues** tool now displays the following information.</span></span>  

*   <span data-ttu-id="ac4ab-126">コード スニペットが改善されました。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-126">Improved code snippets.</span></span>  
*   <span data-ttu-id="ac4ab-127">他の関連パネルへのリンク。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-127">Links to other relevant panels.</span></span>  
*   <span data-ttu-id="ac4ab-128">Web サイトの問題の解決に役立つドキュメントへのリンク。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-128">Links to documentation to help you fix problems in your website.</span></span>  
    
:::image type="complex" source="../../media/2020/11/issues-webhints.msft.png" alt-text="問題ツール" lightbox="../../media/2020/11/issues-webhints.msft.png":::
   <span data-ttu-id="ac4ab-130">**問題** ツール</span><span class="sxs-lookup"><span data-stu-id="ac4ab-130">**Issues** tool</span></span>  
:::image-end:::  

## <a name="composited-layers-are-now-in-3d-view"></a><span data-ttu-id="ac4ab-131">コンポジット レイヤーが 3D ビューに表示される</span><span class="sxs-lookup"><span data-stu-id="ac4ab-131">Composited Layers are now in 3D View</span></span>  

<!-- Title: 3D View is now integrated with Composited Layers  -->  
<!-- Subtitle: Composited Layers are now in 3D View.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="ac4ab-132">Z インデックス値と ドキュメント オブジェクト モデル \(DOM\) と共に、**レイヤー** コンテンツを視覚化できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-132">You may now visualize **Layers** content alongside z-index values and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="ac4ab-133">この機能は、[3D ビュー][Devtools3dViewIndex]と**レイヤー** ツールを頻繁に切り替えることなくデバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-133">This feature helps you debug without switching between the [3D view][Devtools3dViewIndex] and **Layers** tools as often.</span></span>  <span data-ttu-id="ac4ab-134">視覚的なデバッグを総合的に行う目的で、[3D ビューレイヤーと複合レイヤーが結合されました][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-134">For a comprehensive visual debugging experience, the [3D View and Composited Layers are now combined][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView].</span></span>  

:::image type="complex" source="../../media/2020/11/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../../media/2020/11/experiments-layers.msft.png":::
   <span data-ttu-id="ac4ab-136">**[コンポジット レイヤー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="ac4ab-136">**Composited Layers** pane</span></span>  
:::image-end:::  

## <a name="css-variable-definitions-in-styles-pane"></a><span data-ttu-id="ac4ab-137">[スタイル] ウィンドウの CSS 変数の定義</span><span class="sxs-lookup"><span data-stu-id="ac4ab-137">CSS variable definitions in Styles pane</span></span>  

<!-- Title: Jump to CSS variable definitions  -->  
<!-- Subtitle: Choose any CSS variable to navigate directly to the definition in the Styles tool. -->  

<span data-ttu-id="ac4ab-138">**[スタイル]** ウィンドウで、[CSS 変数][MdnUsingCssCustomProperties]が各定義に直接リンクされます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-138">In the **Styles** pane, [CSS variables][MdnUsingCssCustomProperties] now link directly to each definition.</span></span>  <span data-ttu-id="ac4ab-139">CSS 変数の定義を簡単に表示または変更するには、変数を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-139">Choose the variable to easily view or change the CSS variable definition.</span></span>  <span data-ttu-id="ac4ab-140">この例では、DevTools は`body`要素の CSS 属性を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-140">In the example, DevTools displays the CSS attributes for the `body` element.</span></span>  <span data-ttu-id="ac4ab-141">`--theme-body-background`CSS 変数の変数定義を表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-141">To display the variable definition for the `--theme-body-background` CSS variable, complete the following actions.</span></span>  

1.  <span data-ttu-id="ac4ab-142">**[スタイル]** ウィンドウで、`var(--theme-body-background)`を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-142">In the **Styles** pane, choose `var(--theme-body-background)`.</span></span>  
1.  <span data-ttu-id="ac4ab-143">**[スタイル]** ウィンドウに `--theme-body-background`CSS 変数の定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-143">The **Styles** pane now displays the definition of the `--theme-body-background` CSS variable.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support.msft.png" alt-text="スタイルにリンクされた CSS 変数" lightbox="../../media/2020/11/css-variable-support.msft.png":::
         <span data-ttu-id="ac4ab-145">スタイルにリンクされた CSS 変数</span><span class="sxs-lookup"><span data-stu-id="ac4ab-145">CSS variable linked to the style</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support-target.msft.png" alt-text="スタイル ターゲットにリンクされた CSS 変数" lightbox="../../media/2020/11/css-variable-support-target.msft.png":::
         <span data-ttu-id="ac4ab-147">スタイル ターゲットにリンクされた CSS 変数</span><span class="sxs-lookup"><span data-stu-id="ac4ab-147">CSS variable linked to style target</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="service-worker-debugging-improvements"></a><span data-ttu-id="ac4ab-148">サービス ワーカー デバッグの機能強化</span><span class="sxs-lookup"><span data-stu-id="ac4ab-148">Service worker debugging improvements</span></span>  

<!-- Title:  Service worker debugging improvements in the Network, Application, and Sources tools  -->  
<!-- Subtitle:  Making service workers easier to debug for progressive web applications and more.  -->  

<span data-ttu-id="ac4ab-149">[ネットワーク ツール](#network-tool)、[アプリケーション ツール](#application-tool)、および[ソース ツール](#sources-tool)の次の新機能は、[PWA][ProgressiveWebAppsIndex] の構築に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-149">The following new features in the [Network](#network-tool), [Application](#application-tool), and [Sources](#sources-tool) tools help you build your [PWA][ProgressiveWebAppsIndex].</span></span>  <span data-ttu-id="ac4ab-150">サービス ワーカーのデバッグが困難な場合は、次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-150">Use the following features when you have difficulty debugging your service worker.</span></span>  

<span data-ttu-id="ac4ab-151">要求ルーティングは、サービス ワーカーを経由して実行されるネットワーク要求に基づいて、`startup` と `fetch` イベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-151">Request routing displays the `startup` and `fetch` events based on the network requests that run through service workers.</span></span>  <span data-ttu-id="ac4ab-152">タイムラインには、**アプリケーション ツール**または**ネットワーク ツール**からアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-152">The timelines are accessed from either the **Application** or **Network** tool.</span></span>  <span data-ttu-id="ac4ab-153">タイムラインは、サービス ワーカーに問題が発生し、イベントに問題がある場合に表示する場合 `startup` に役立 `fetch` ちます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-153">The timelines help when you are having trouble with service workers and want to display if something is wrong with the `startup` or `fetch` event.</span></span>  

### <a name="application-tool"></a><span data-ttu-id="ac4ab-154">アプリケーション ツール</span><span class="sxs-lookup"><span data-stu-id="ac4ab-154">Application tool</span></span>  

<!-- Title: Open Network tool from the Service Workers pane  -->  
<!-- Subtitle: Display additional context when debugging a service worker.  -->  

<span data-ttu-id="ac4ab-155">新しい **[ネットワーク要求]** リンクを使用して、すべてのサービス ワーカー 要求ルーティング情報を表示 します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-155">View all service worker request routing information with the new **Network requests** link.</span></span>  <span data-ttu-id="ac4ab-156">サービス ワーカーをデバッグするときに追加のコンテキストを表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-156">To display additional context when debugging the service worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="ac4ab-157">\*\*アプリケーション \*\* > **サービス ワーカー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-157">Navigate to **Application** > **Service Workers**.</span></span>  
1.  <span data-ttu-id="ac4ab-158">**[ネットワーク 要求]**.を選びます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-158">Choose **Network requests**.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-requests.msft.png" alt-text="[サービス ワーカー] ウィンドウから、ネットワーク ツールを開く" lightbox="../../media/2020/11/service-worker-application-network-requests.msft.png":::
       <span data-ttu-id="ac4ab-160">**[サービス ワーカー]** ウィンドウから、**ネットワーク** ツールを開く</span><span class="sxs-lookup"><span data-stu-id="ac4ab-160">Open **Network** tool from the **Service Workers** pane</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="ac4ab-161">**ネットワーク ツール**が**ドロワー**で開き、サービス ワーカー関連のすべてのネットワーク要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-161">The **Network** tool opens in the **drawer** and displays all service worker-related network requests.</span></span>  <span data-ttu-id="ac4ab-162">ネットワーク要求は、`is:service-worker-intercepted` を使用してフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-162">The network requests are filtered using `is:service-worker-intercepted`.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-drawer.msft.png" alt-text="ドロワー内のネットワーク ツール" lightbox="../../media/2020/11/service-worker-application-network-drawer.msft.png":::
       <span data-ttu-id="ac4ab-164">**ドロワー**内の**ネットワーク** ツール</span><span class="sxs-lookup"><span data-stu-id="ac4ab-164">**Network** tool in **drawer**</span></span>  
    :::image-end:::
    
1. <span data-ttu-id="ac4ab-165">**ネットワーク** ツールをトップ パネルに戻す場合は、**ドロワー**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-165">To return the **Network** tool to the top panel, close the **drawer**.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-return.msft.png" alt-text="ドロワーを閉じて、ネットワーク ツールを返す" lightbox="../../media/2020/11/service-worker-application-network-return.msft.png":::
       <span data-ttu-id="ac4ab-167">**ドロワー**を閉じて、**ネットワーク ツール**を返す</span><span class="sxs-lookup"><span data-stu-id="ac4ab-167">Close the **drawer** to return **Network** tool</span></span>  
    :::image-end:::  
    
### <a name="network-tool"></a><span data-ttu-id="ac4ab-168">ネットワーク ツール</span><span class="sxs-lookup"><span data-stu-id="ac4ab-168">Network tool</span></span>  

<span data-ttu-id="ac4ab-169">サービス ワーカーを介して実行されるネットワーク要求をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-169">Debug network requests that run through service workers.</span></span>  <span data-ttu-id="ac4ab-170">**アプリケーション** ツールからネットワーク要求を開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-170">You may also open network requests from the **Application** tool.</span></span>  <span data-ttu-id="ac4ab-171">要求ごとに、DevTools はタイミング ウィンドウに次の情報を[[タイミング]][DevtoolsNetworkReferenceViewTimingBreakdownRequest] ウインドウに表示 します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-171">For each request, DevTools display the following information in the [Timing][DevtoolsNetworkReferenceViewTimingBreakdownRequest] pane.</span></span>  

*   <span data-ttu-id="ac4ab-172">ブートストラップの要求の開始と期間。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-172">The start of a request and duration of the bootstrap.</span></span>  
*   <span data-ttu-id="ac4ab-173">サービス ワーカーの登録に対する変更。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-173">Changes to service worker registration.</span></span>  
*   <span data-ttu-id="ac4ab-174">`fetch`イベント ハンドラーのランタイム。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-174">The runtime of a `fetch` event handler.</span></span>  
*   <span data-ttu-id="ac4ab-175">クライアントを読み込むすべての `fetch` イベントのランタイム。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-175">The runtime of all `fetch` events for loading a client.</span></span>  
    
:::image type="complex" source="../../media/2020/11/network-timing-service-worker.msft.png" alt-text="[タイミング] ウィンドウ" lightbox="../../media/2020/11/network-timing-service-worker.msft.png":::
   <span data-ttu-id="ac4ab-177">**[タイミング]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="ac4ab-177">**Timing** pane</span></span>  
:::image-end:::  

### <a name="sources-tool"></a><span data-ttu-id="ac4ab-178">ソース ツール</span><span class="sxs-lookup"><span data-stu-id="ac4ab-178">Sources tool</span></span>  

<span data-ttu-id="ac4ab-179">以前のバージョンの Microsoft Edge では、呼び出し履歴の深さのレベルは、サービス ワーカーの JavaScript コードに制限されています。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-179">In previous versions of Microsoft Edge, the level of depth in the call stack was limited to the JavaScript code in your service worker.</span></span>  <span data-ttu-id="ac4ab-180">Microsoft Edge 88 では、呼び出し履歴に、サービス ワーカーを介して実行される要求を行ったイニシエーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-180">In Microsoft Edge 88, the call stack now displays the initiator of requests that run through your service worker.</span></span>  

<span data-ttu-id="ac4ab-181">要求を行ったイニシエーターを見つけるには、サービス ワーカーで JavaScript コードの呼び出し履歴を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-181">To locate the initiator of the request, use the call stack of your JavaScript code in the service worker.</span></span>  <span data-ttu-id="ac4ab-182">次の図の呼び出し履歴は、サービス ワーカーの JavaScript コードから始まり、元の Web ページ要求への参照を `(index):157` のように表示します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-182">The call stack in the following figures starts with the JavaScript code in your service worker and displays a reference to the original webpage request as `(index):157`.</span></span>  <span data-ttu-id="ac4ab-183">2 番目の図では、参照が選択され、要求を行ったイニシエーターが開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-183">In the second figure, the reference is chosen and opened the initiator that made the request.</span></span>  <span data-ttu-id="ac4ab-184">2 番目の図のイニシエーターは Web ページです。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-184">The initiator in the second figure is the webpage.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png" alt-text="service-worker.js ファイルと呼び出し履歴の強調表示要求の発信者" lightbox="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png":::
         <span data-ttu-id="ac4ab-186">`service-worker.js` ファイルと呼び出し履歴の強調表示要求の発信者</span><span class="sxs-lookup"><span data-stu-id="ac4ab-186">The `service-worker.js` file and call stack highlighting request originator</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-call-stack-target.msft.png" alt-text="(インデックス) Web ページは、要求のイニシエーターです" lightbox="../../media/2020/11/service-worker-sources-call-stack-target.msft.png":::
         <span data-ttu-id="ac4ab-188">`(index)` Web ページは要求のイニシエーターです</span><span class="sxs-lookup"><span data-stu-id="ac4ab-188">The `(index)` webpage is the request initiator</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="copy-property-value-of-a-network-request"></a><span data-ttu-id="ac4ab-189">ネットワーク要求のプロパティ値をコピーする</span><span class="sxs-lookup"><span data-stu-id="ac4ab-189">Copy property value of a network request</span></span>  

<!-- Title: Copy response JSON in Network tool using the contextual menu  -->  
<!-- Subtitle:  The Network tool now has a more consistent UX.  Easily copy the JSON response using the contextual menu.  -->  

<span data-ttu-id="ac4ab-190">**ネットワーク** ツールで、新しい **[値のコピー]** オプションを使用して、ネットワーク要求のプロパティ値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-190">In the **Network** tool, copy the property value of a network request using the new **Copy value** option.</span></span>  <span data-ttu-id="ac4ab-191">プロパティ値は、デコードされた JSON 値としてコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-191">The property value is copied as a decoded JSON value.</span></span>  <span data-ttu-id="ac4ab-192">以前のバージョンの Microsoft Edge では、次のいずれかの操作を使用して値をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-192">In previous versions of Microsoft Edge, you had to copy a value using one of the following actions.</span></span>  

*   <span data-ttu-id="ac4ab-193">テキスト全体を強調表示してコピーします。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-193">Highlight the entire text and copy it.</span></span>  
*   <span data-ttu-id="ac4ab-194">必要に応じ、値をグローバル変数として格納し、DevTools [コンソール][DevtoolsConsoleIndex]からコピー します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-194">Store the value as global variable, as applicable, and copy it from the DevTools [Console][DevtoolsConsoleIndex].</span></span>  
    
<span data-ttu-id="ac4ab-195">プロパティ値をクリップボードにコピーするには、[[書式設定された応答 JSON をクリップボードにコピーする]][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-195">To copy the property value to your clipboard, navigate to [Copy formatted response JSON to the clipboard][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard].</span></span>  <span data-ttu-id="ac4ab-196">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1132084][CR1132084] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-196">To review the history of this feature in the Chromium open-source project, navigate to Issue [1132084][CR1132084].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/copy-property-value.msft.png" alt-text="DevTools のプロパティ値をコピーする" lightbox="../../media/2020/11/copy-property-value.msft.png":::
         <span data-ttu-id="ac4ab-198">DevTools のプロパティ値をコピーする</span><span class="sxs-lookup"><span data-stu-id="ac4ab-198">Copy property value in DevTools</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/paste-property-value.msft.png" alt-text="Microsoft Visual Studio コードでプロパティ値を貼り付ける" lightbox="../../media/2020/11/paste-property-value.msft.png":::
         <span data-ttu-id="ac4ab-200">Microsoft Visual Studio コードでプロパティ値を貼り付ける</span><span class="sxs-lookup"><span data-stu-id="ac4ab-200">Paste property value in Microsoft Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="customize-multi-press-keyboard-shortcuts"></a><span data-ttu-id="ac4ab-201">複数押しのキーボード ショートカットをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="ac4ab-201">Customize multi-press keyboard shortcuts</span></span>  

<!-- Title: Customize multi-press keyboard shortcuts  -->  
<!-- Subtitle: Create custom multi-press keyboard shortcuts in the shortcut editor.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

<span data-ttu-id="ac4ab-202">[Microsoft Edge バージョン 87 以降][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]では、DevTools でいずれのアクションのキーボード ショートカットもカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-202">[Since Microsoft Edge version 87][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings], you may customize keyboard shortcuts for any action in DevTools.</span></span>  <span data-ttu-id="ac4ab-203">Microsoft Edge バージョン 88 では、複数押しのキーボード ショートカットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-203">In Microsoft Edge version 88, you may now create multi-press keyboard shortcuts.</span></span>  <span data-ttu-id="ac4ab-204">DevTools でアクションのショートカットを設定するには、[[設定][DevtoolsCustomizeIndexSettings] > **の実験**] に移動し、[**キーボード ショートカット エディターを有効にする**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-204">To set a shortcut for an action in the DevTools, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="ac4ab-205">ショートカットのカスタマイズと編集の詳細については、「[キーボード ショートカット エディターの試験的機能を有効にする][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-205">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="ac4ab-206">たとえば、赤い強調表示は、[**イベントの記録の開始**] アクション用にカスタマイズされた複数押しの キーボード ショートカットが表示 されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-206">For example, the red highlight displays a multi-press keyboard shortcut customized for the **Start recording events** action.</span></span>  <span data-ttu-id="ac4ab-207">Chromium オープン ソース プロジェクトで、この機能に関するリアルタイムの更新を確認するについては、[問題 #174309][CR174309] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-207">To review real-time updates on this feature in the Chromium open-source project, navigate to [Issue #174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png" alt-text="コード キーボード ショートカット" lightbox="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png":::
   <span data-ttu-id="ac4ab-209">複数押しキーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="ac4ab-209">Multi-press keyboard shortcuts</span></span>  
:::image-end:::  

## <a name="devtools-now-match-browser-language"></a><span data-ttu-id="ac4ab-210">DevTools がブラウザーの言語と一致する</span><span class="sxs-lookup"><span data-stu-id="ac4ab-210">DevTools now match browser language</span></span>  

<span data-ttu-id="ac4ab-211">Microsoft Edge バージョン 87 では、[DevTools の設定][DevtoolsCustomizeIndexSettings]で [**ブラウザーの言語の一致**] 設定をオンにした場合、DevTools はブラウザーの言語と一致しません。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-211">In Microsoft Edge version 87, if you turned on the **Match browser language** setting in [DevTools Settings][DevtoolsCustomizeIndexSettings], DevTools did not match the browser language.</span></span>  <span data-ttu-id="ac4ab-212">Microsoft Edge バージョン 88 では、[**ブラウザーの言語の一致]** 設定をオンにすると、DevTools はブラウザーの言語と一致します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-212">In Microsoft Edge version 88, DevTools now matches the browser language if you turn on the **Match browser language** setting.</span></span>  <span data-ttu-id="ac4ab-213">**ブラウザーの言語の一致** DevTools 設定の詳細については、[「DevTools 言語設定の変更」][DevtoolsCustomizeLocalization]に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-213">For more information about the **Match browser language** DevTools Setting, navigate to [Change DevTools language settings][DevtoolsCustomizeLocalization].</span></span>  

:::image type="complex" source="../../media/2020/11/startpage-devtools-settings-japanese.msft.png" alt-text="日本語でのブラウザーの言語の一致 DevTools 設定" lightbox="../../media/2020/11/startpage-devtools-settings-japanese.msft.png":::
   <span data-ttu-id="ac4ab-215">日本語での**ブラウザーの言語の一致** DevTools 設定 </span><span class="sxs-lookup"><span data-stu-id="ac4ab-215">**Match browser language** DevTools setting in Japanese</span></span>  
:::image-end:::  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="ac4ab-216">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="ac4ab-216">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-css-angle-visualization-tools"></a><span data-ttu-id="ac4ab-217">新しい CSS 角度可視化ツール</span><span class="sxs-lookup"><span data-stu-id="ac4ab-217">New CSS angle visualization tools</span></span>  

<span data-ttu-id="ac4ab-218">DevTools では、CSS 角度デバッグのサポートが向上しました。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-218">DevTools now have better support for CSS angle debugging.</span></span>  <span data-ttu-id="ac4ab-219">ページ上の HTML 要素に CSS 角度が適用されている場合、**[スタイル]** ツールの角度の横に時計アイコンが表示 されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-219">When an HTML element on your page has CSS angle applied to it, a clock icon is displayed next to the angle in the **Styles** tool.</span></span>  <span data-ttu-id="ac4ab-220">クロック オーバーレイを切り替えるには、時計アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-220">To toggle the clock overlay, choose the clock icon.</span></span>  <span data-ttu-id="ac4ab-221">角度を変更するには、時計の任意の場所を選択するか、または針をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-221">To change the angle, choose anywhere in the clock or drag the needle.</span></span>  <span data-ttu-id="ac4ab-222">角度の値を変更するには、マウス ショートカットとキーボード ショートカットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-222">To change the angle value, you may also use mouse and keyboard shortcuts.</span></span>  <!--  To learn more, navigate to [Angle Clock][DevtoolsCssReferenceChangeAngleValueWithAngleClock].  -->  <span data-ttu-id="ac4ab-223">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1126178][CR1126178] および [1138633][CR1138633]に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-223">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1126178][CR1126178] and [1138633][CR1138633].</span></span>  

<!--todo:  add link when css angle clock section exists.  -->  

<span data-ttu-id="ac4ab-224">この例では、次の CSS 角度を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-224">The following CSS angle is used for the example.</span></span>  

```css
background: linear-gradient(100deg, lightblue, pink);
```  

:::image type="complex" source="../../media/2020/11/css-angle.msft.png" alt-text="CSS の角度" lightbox="../../media/2020/11/css-angle.msft.png":::
   <span data-ttu-id="ac4ab-226">CSS の角度</span><span class="sxs-lookup"><span data-stu-id="ac4ab-226">CSS angle</span></span>  
:::image-end:::  

### <a name="simulate-storage-quota-size-in-the-storage-pane"></a><span data-ttu-id="ac4ab-227">[記憶域] ウィンドウで、記憶域クォータのサイズをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="ac4ab-227">Simulate storage quota size in the Storage pane</span></span>  

<span data-ttu-id="ac4ab-228">**[記憶域]** ウィンドウで記憶域クォータのサイズを上書きする場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-228">You may now override storage quota size in the **Storage** pane.</span></span>  <span data-ttu-id="ac4ab-229">この機能を使用すると、ディスクの可用性が低いシナリオで、さまざまなデバイスをシミュレートし、Web サイトまたはアプリの動作をテストできます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-229">This feature allows you to simulate different devices and test the behavior of your website or app in low disk availability scenarios.</span></span>  <span data-ttu-id="ac4ab-230">記憶域クォータをシミュレートするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-230">To simulate the storage quota, complete the following actions.</span></span>  

1.  <span data-ttu-id="ac4ab-231">**アプリケーション**  > **ストレージ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-231">Navigate to **Application** > **Storage**.</span></span>  
1.  <span data-ttu-id="ac4ab-232">**[カスタム ストレージ クォータをシミュレートする]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-232">Turn on the **Simulate custom storage quota** checkbox.</span></span>  
1.  <span data-ttu-id="ac4ab-233">有効な数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-233">Enter a valid number.</span></span>  
    
<span data-ttu-id="ac4ab-234">DevTools でモバイル デバイスや他の機能をエミュレートする方法の詳細については、[「Microsoft Edge DevTools でモバイル デバイスをエミュレートする」][DevtoolsDeviceModeIndex] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-234">For more information about how to emulate mobile devices and other features in the DevTools, navigate to [Emulate mobile devices in Microsoft Edge DevTools ][DevtoolsDeviceModeIndex].</span></span>  <span data-ttu-id="ac4ab-235">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題[945786][CR945786] および [1146985][CR1146985]に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-235">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [945786][CR945786] and [1146985][CR1146985].</span></span>  

:::image type="complex" source="../../media/2020/11/storage-quota.msft.png" alt-text="記憶域クォータのサイズをシミュレートする" lightbox="../../media/2020/11/storage-quota.msft.png":::
   <span data-ttu-id="ac4ab-237">記憶域クォータのサイズをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="ac4ab-237">Simulate storage quota size</span></span>  
:::image-end:::  

### <a name="report-cors-errors-in-the-network-tool"></a><span data-ttu-id="ac4ab-238">ネットワーク ツールで CORS エラーを報告する</span><span class="sxs-lookup"><span data-stu-id="ac4ab-238">Report CORS errors in the Network tool</span></span>  

<span data-ttu-id="ac4ab-239">[「CORS エラー デモ」][GlitchCorsErrors]に移動して、この機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-239">Try out this feature by navigating to [CORS error demo][GlitchCorsErrors].</span></span>  <span data-ttu-id="ac4ab-240">**ネットワーク** ツールを開き、ページを更新して、失敗した CORS ネットワーク要求を確認します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-240">Open the **Network** tool, refresh the page, and observe the failed CORS network request.</span></span>  <span data-ttu-id="ac4ab-241">状態の列には、**CORS エラー**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-241">The status column displays the **CORS error**.</span></span>  <span data-ttu-id="ac4ab-242">エラーの上にホバーすると、ツールヒントにエラー コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-242">When you hover on the error, the tooltip now displays the error code.</span></span>  <span data-ttu-id="ac4ab-243">Microsoft Edge バージョン 87 以前では、DevTools は CORS エラーの一般的な **(失敗)** 状態のみを表示しました。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-243">In Microsoft Edge version 87 and earlier, DevTools only displayed generic **(failed)** status for CORS errors.</span></span>  <span data-ttu-id="ac4ab-244">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1141824][CR1141824] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-244">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1141824][CR1141824].</span></span>  

:::image type="complex" source="../../media/2020/11/cors-err.msft.png" alt-text="CORS エラー" lightbox="../../media/2020/11/cors-err.msft.png":::
   <span data-ttu-id="ac4ab-246">CORS エラー</span><span class="sxs-lookup"><span data-stu-id="ac4ab-246">CORS errors</span></span>  
:::image-end:::  

### <a name="frame-details-view-updates"></a><span data-ttu-id="ac4ab-247">フレーム詳細ビューの更新</span><span class="sxs-lookup"><span data-stu-id="ac4ab-247">Frame details view updates</span></span>  

#### <a name="cross-origin-isolation-information-in-the-frame-details-view"></a><span data-ttu-id="ac4ab-248">フレーム詳細ビューのクロスオリジン分離情報</span><span class="sxs-lookup"><span data-stu-id="ac4ab-248">Cross-origin isolation information in the Frame details view</span></span>  

<span data-ttu-id="ac4ab-249">クロスオリジン分離状態は、**「セキュリティと分離」** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-249">The cross-origin isolated status is now displayed under the **Security & Isolation** section.</span></span>  <span data-ttu-id="ac4ab-250">新しい **「API の可用性」** セクションには、`SharedArrayBuffer`s \(SAB\) の可用性と、バッファーを使用して共有できるかどうかが表示されます`postMessage()`。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-250">The new **API availability** section displays the availability of `SharedArrayBuffer`s \(SAB\) and whether the buffers may be shared using `postMessage()`.</span></span>  <span data-ttu-id="ac4ab-251">SAB と `postMessage()` が現在利用可能な場合、非推奨の警告が表示されますが、コンテキストはクロスオリジン分離されていません。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-251">A deprecation warning displays if the SAB and `postMessage()` is currently available, but the context is not cross-origin isolated.</span></span>  <span data-ttu-id="ac4ab-252">クロスオリジン分離の詳細と、`SharedArrayBuffers`が必要な理由については、[WindowOrWorkerGlobalScope.crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-252">For more information about cross-origin isolation and why it is required for features like `SharedArrayBuffers`, navigate to [WindowOrWorkerGlobalScope.crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated].</span></span>  <span data-ttu-id="ac4ab-253">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1139899][CR1139899] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-253">To review real-time updates of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2020/11/frame-cross-origin-isolated-api.msft.png" alt-text="クロスオリジン情報" lightbox="../../media/2020/11/frame-cross-origin-isolated-api.msft.png":::
   <span data-ttu-id="ac4ab-255">クロスオリジン情報</span><span class="sxs-lookup"><span data-stu-id="ac4ab-255">Cross-origin information</span></span>  
:::image-end:::  

#### <a name="new-web-workers-information-in-the-frame-details-view"></a><span data-ttu-id="ac4ab-256">フレーム詳細ビューの新しい Web ワーカー情報</span><span class="sxs-lookup"><span data-stu-id="ac4ab-256">New Web Workers information in the Frame details view</span></span>  

<span data-ttu-id="ac4ab-257">DevTools では、関連する親フレームの下に Web ワーカーが整理されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-257">DevTools now organizes web workers under the relevant parent frame.</span></span>  <span data-ttu-id="ac4ab-258">たとえば、`someName` フレームが `worker.js` を作成する場合、`worker.js` が**フレーム** リストの下にある `someName` に表示 されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-258">For example, if the `someName` frame creates `worker.js`, then `worker.js` appears under `someName` in the **Frames** list.</span></span>  <span data-ttu-id="ac4ab-259">Web ワーカーの詳細を表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-259">To view the details of the web worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="ac4ab-260">**アプリケーション** ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-260">Open **Application** tool.</span></span>  
1.  <span data-ttu-id="ac4ab-261">Web ワーカーを含むフレームを展開します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-261">Expand a frame that contains web workers.</span></span>  
1.  <span data-ttu-id="ac4ab-262">**[ワーカー]** ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-262">Expand the **Workers** tree.</span></span>  
1.  <span data-ttu-id="ac4ab-263">ワーカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-263">Choose a worker.</span></span>  
    
<span data-ttu-id="ac4ab-264">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1122507][CR1122507] および [1051466][CR1051466]に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-264">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1122507][CR1122507] and [1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/11/application-frames-service-workers.msft.png" alt-text="Web ワーカー情報" lightbox="../../media/2020/11/application-frames-service-workers.msft.png":::
   <span data-ttu-id="ac4ab-266">Web ワーカー情報</span><span class="sxs-lookup"><span data-stu-id="ac4ab-266">Web workers information</span></span>  
:::image-end:::  

#### <a name="display-opener-frame-details-for-opened-windows"></a><span data-ttu-id="ac4ab-267">開いたウィンドウのオープン フレームの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ac4ab-267">Display opener frame details for opened windows</span></span>  

<span data-ttu-id="ac4ab-268">DevTools では、関連する親[フレーム][MdnWindowFrames]の下に開いている [Windows][MdnWindowConstructors] が整理 されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-268">DevTools now organizes opened [Windows][MdnWindowConstructors] under the relevant parent [frame][MdnWindowFrames].</span></span>  <span data-ttu-id="ac4ab-269">たとえば、`top` フレームが `Window` を `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium` に開く場合は、**フレーム** リストの下の `top` に `Window` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-269">For example, if the `top` frame opens a `Window` to `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium`, then the `Window` appears under `top` in the **Frames** list.</span></span>  

<span data-ttu-id="ac4ab-270">**要素**ツールで別の Window を開くためのフレームを表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-270">To reveal the frame responsible for opening another Window in the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="ac4ab-271">**フレーム** ツリーを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-271">Open the **Frames** tree.</span></span>  
1.  <span data-ttu-id="ac4ab-272">**[開いた Windows]** を展開 し、知りたい親フレームの `Window` を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-272">Expand **Opened Windows** and choose the `Window` for the parent frame you want to know.</span></span>  
1.  <span data-ttu-id="ac4ab-273">**[Opener フレーム]** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-273">Choose the **Opener Frame** link.</span></span>  

<span data-ttu-id="ac4ab-274">どのフレームが別の `Window` を開いたのかについての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-274">The details are displayed about which frame caused the opening of another `Window`.</span></span>  <span data-ttu-id="ac4ab-275">**要素**ツールで Opener を表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-275">To reveal the opener in the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="ac4ab-276">**フレーム** ツリーを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-276">Open the **Frames** tree.</span></span>  
1.  <span data-ttu-id="ac4ab-277">開いているウィンドウを選択して `Window` の詳細を開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-277">Choose an opened window to open the `Window` details.</span></span>  
1.  <span data-ttu-id="ac4ab-278">**[Opener フレーム]** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-278">Choose the **Opener Frame** link.</span></span>  
    
<span data-ttu-id="ac4ab-279">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1107766][CR1107766]に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-279">To review the history of this feature in the Chromium open-source project, navigate to Issue [1107766][CR1107766].</span></span>  

:::image type="complex" source="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png" alt-text="開いたフレームの詳細" lightbox="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png":::
   <span data-ttu-id="ac4ab-281">開いたフレームの詳細</span><span class="sxs-lookup"><span data-stu-id="ac4ab-281">Opened frame details</span></span>  
:::image-end:::  

### <a name="copy-stacktrace-for-network-initiator"></a><span data-ttu-id="ac4ab-282">ネットワーク イニシエーターの stacktrace をコピーする</span><span class="sxs-lookup"><span data-stu-id="ac4ab-282">Copy stacktrace for network initiator</span></span>  

<span data-ttu-id="ac4ab-283">stacktrace をクリップボードにコピーするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-283">To copy the stacktrace to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="ac4ab-284">コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-284">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="ac4ab-285">**[コピー]** を選んでから、 > **[stacktrace をコピー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-285">Choose **Copy** > **Copy stacktrace**.</span></span>  
    
<span data-ttu-id="ac4ab-286">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1139615][CR1139615] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-286">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139615][CR1139615].</span></span>

:::image type="complex" source="../../media/2020/11/copy-stacktrace.msft.png" alt-text="stacktrace のコピー" lightbox="../../media/2020/11/copy-stacktrace.msft.png":::
   <span data-ttu-id="ac4ab-288">stacktrace のコピー</span><span class="sxs-lookup"><span data-stu-id="ac4ab-288">Copy stacktrace</span></span>  
:::image-end:::  

### <a name="preview-wasm-variable-value-on-mouseover"></a><span data-ttu-id="ac4ab-289">マウスオーバー時の Wasm 変数値のプレビュー</span><span class="sxs-lookup"><span data-stu-id="ac4ab-289">Preview Wasm variable value on mouseover</span></span>  

<span data-ttu-id="ac4ab-290">この機能を使用して、コードが一時停止した時に WebAssembly \(Wasm\) 変数の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-290">Use this feature to review the value of a WebAssembly \(Wasm\) variable when your code is paused.</span></span>  <span data-ttu-id="ac4ab-291">変数の現在の値を表示するには、変数にホバーします。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-291">To display the current value of a variable, hover on a variable.</span></span>  <span data-ttu-id="ac4ab-292">Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1058836][CR1058836] および [1071432][CR1071432] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-292">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1058836][CR1058836] and [1071432][CR1071432].</span></span>  

:::image type="complex" source="../../media/2020/11/wasm-mouseover.msft.png" alt-text="マウスオーバー時の Wasm 変数のプレビュー" lightbox="../../media/2020/11/wasm-mouseover.msft.png":::
   <span data-ttu-id="ac4ab-294">マウスオーバー時の Wasm 変数のプレビュー</span><span class="sxs-lookup"><span data-stu-id="ac4ab-294">Preview Wasm variable on mouseover</span></span>  
:::image-end:::  

### <a name="consistent-units-of-measurement-for-sizes-of-files-and-memory"></a><span data-ttu-id="ac4ab-295">ファイルとメモリのサイズに対する一貫した測定単位</span><span class="sxs-lookup"><span data-stu-id="ac4ab-295">Consistent units of measurement for sizes of files and memory</span></span>  

<span data-ttu-id="ac4ab-296">DevTools は、ファイルとメモリのサイズを表示するために、`kB` を常に使用します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-296">DevTools now consistently use `kB` for displaying sizes of files and memory.</span></span>  <span data-ttu-id="ac4ab-297">以前の DevTools では、`kB` と `KiB` が混在していました。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-297">Previously DevTools mixed `kB` and `KiB`.</span></span>

*   `kB` <span data-ttu-id="ac4ab-298">またはキロバイト \(10^3 または 1000 バイト\)</span><span class="sxs-lookup"><span data-stu-id="ac4ab-298">or kilobyte \(10^3 or 1000 bytes\)</span></span>  
*   `KiB` <span data-ttu-id="ac4ab-299">またはキビバイト \(2^10 または 1024 バイト\)</span><span class="sxs-lookup"><span data-stu-id="ac4ab-299">or kibibyte \(2^10 or 1024 bytes\)</span></span>  
    
<span data-ttu-id="ac4ab-300">たとえば、**ネットワーク** ツールは以前`kB` をラベルで使用していましたが、計算には `KiB` を使用していました。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-300">For example, the **Network** tool previously used `kB` in the labels, but used `KiB` in calculations.</span></span>  <span data-ttu-id="ac4ab-301">お客様のフィードバックから、この不整合によって混乱が生じることが明らかになりました。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-301">Your feedback showed that this inconsistency caused confusion.</span></span>  <span data-ttu-id="ac4ab-302">Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1035309][CR1035309] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-302">To review the history of this feature in the Chromium open-source project, navigate to Issue [1035309][CR1035309].</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="ac4ab-303">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ac4ab-303">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="ac4ab-304">Windows、Linux、または macOS を使用している場合は、 [既定][MicrosoftEdgePreviewChannels] の開発ブラウザーとして Microsoft Edge プレビュー チャネルの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-304">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="ac4ab-305">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-305">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="ac4ab-306">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="ac4ab-306">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[Devtools3dViewIndex]: /microsoft-edge/devtools-guide-chromium/3d-view/index "3D ビュー | Microsoft Docs"  
[DevtoolsConsoleIndex]: /microsoft-edge/devtools-guide-chromium/console/index "コンソールの概要 | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeLocalization]: /microsoft-edge/devtools-guide-chromium/customize/localization "DevTools の言語設定を変更する | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボード ショートカット エディターを有効にする - 試験的な機能 | microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-composited-layers-in-3d-view "3D ビューで複合レイヤーを有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]: /microsoft-edge/devtools-guide-chromium/network/reference#copy-formatted-response-json-to-the-clipboard "書式設定された応答 JSON をクリップボードにコピーする - ネットワーク分析リファレンス | Microsoft Docs"  
[DevtoolsNetworkReferenceViewTimingBreakdownRequest]: /microsoft-edge/devtools-guide-chromium/network/reference#view-the-timing-breakdown-of-a-request "要求のタイミング ブレークダウンを表示する - ネットワーク分析リファレンス | Microsoft Docs"  
[WebDriverChromiumMain]: /microsoft-edge/webdriver-chromium "テスト自動化に WebDriver (Chromium) を使用する | Microsoft Docs"  

<!--  [DevtoolsCssReferenceChangeAngleValueWithAngleClock]: /microsoft-edge/devtools-guide-chromium/css/reference#change-angle-value-with-the-angle-clock "Change angle value with the Angle Clock - CSS reference | Microsoft Docs"  -->  

[ProgressiveWebAppsIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上のプログレッシブ Web アプリ | Microsoft Docs"  

[WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]: ../10/devtools.md#customize-keyboard-shortcuts-in-settings "[設定] でキーボード ショートカットをカスタマイズする - DevTools の新機能 (Microsoft Edge 87) | Microsoft Docs"  
[WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]: ../06/devtools.md#webhint-feedback-in-the-issues-panel "[問題] パネルの webhint フィードバック - DevTools の新機能 (Microsoft Edge 85) | Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "WebDriver のダウンロード | Microsoft 開発者"  

[MicrosoftinsiderDownloadPlatformLinux]: https://www.microsoftedgeinsider.com/download?platform=linux "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "問題 174309: DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium のバグ"  
[CR945786]: https://crbug.com/945786 "問題 945786: DevTools: navigator.storage.estimate() の上書きを許可する | Chromium のバグ"  
[CR1029427]: https://crbug.com/1029427 "問題 1029427: フロントエンドでのプロトコル メッセージ ディスパッチのパフォーマンス オーバーヘッドを削減する | Chromium のバグ"  
[CR1035309]: https://crbug.com/1035309 "問題 1035309: DevTools は MB をメビバイトではなくメガバイトという意味で一貫して使用する必要があります | Chromium のバグ"  
[CR1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での COOP/COEP デバッグのサポート | Chromium のバグ"  
[CR1058836]: https://crbug.com/1058836 "問題 1058836: Wasm のデバッグに関する UX の問題 | Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "問題 1071432: ☂️ Wasm Basic 開発者のエクスペリエンス | Chromium のバグ"  
[CR1107766]: https://crbug.com/1107766 "問題 1107766: 'window.open()' によって生成されたフレームに関する情報をフレーム ツリーに表示する | Chromium のバグ"  
[CR1122507]: https://crbug.com/1122507 "問題 1122507: フレーム ツリー ビューでの Surface ワーカー情報 | Chromium のバグ"  
[CR1126178]: https://crbug.com/1126178 "問題 1126178: devTools ☂: CSS <タイプ> コンポーネント | Chromium のバグ"  
[CR1130556]: https://crbug.com/1130556 "問題 1130556: DevTools: テスト イメージのフォールバック (エミュレーション) | Chromium のバグ"  
[CR1132084]: https://crbug.com/1132084 "問題 1132084: JSON 要求ペイロードを簡単にコピーする方法がない | Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox ツール | Chromium のバグ"  
[CR1138633]: https://crbug.com/1138633 "問題 1138633: DevTools: CSS <角度> コンポーネントが、時計の背景にあるプロパティの外観を反射している必要がある |Chromium のバグ"  
[CR1139615]: https://crbug.com/1139615 "問題 1139615: ネットワーク イニシエーターがスタック トレースをコピーする機能を提供する必要がある | Chromium のバグ"  
[CR1139899]: https://crbug.com/1139899 "問題 1139899: フレーム詳細ビューでゲート API の可用性を報告する | Chromium のバグ"  
[CR1139945]: https://crbug.com/1139945 "問題 1139945: [スタイル] パネルの flexbox CSS プロパティのアイコン | Chromium のバグ"  
[CR1141824]: https://crbug.com/1141824 "問題 1141824: DevTools で CORS エラー報告を改善する | Chromium のバグ"  
[CR1144090]: https://crbug.com/1144090 "問題 1144090: 要素ツリーに柔軟なスタイルの装飾を追加する | Chromium のバグ"  
[CR1146985]: https://crbug.com/1146985 "問題 1146985: 「Dev Tools」ウィンドウの「ストレージ」セクションのテキスト ボックスに、クリアされたテキストが表示される | Chromium のバグ"  

[GlitchCorsErrors]: https://cors-errors.glitch.me "CORS エラー | Glitch"  

[MdnCors]: https://developer.mozilla.org/docs/Web/HTTP/CORS "クロスオリジン リソース共有 (CORS) | MDN"  
[MdnUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "CSS カスタム プロパティ (変数) を使用する |MDN"  
[MdnWindowConstructors]: https://developer.mozilla.org/docs/Web/API/Window#Constructors "コンストラクター - Window | MDN"  
[MdnWindowFrames]: https://developer.mozilla.org/docs/Web/API/Window/frames "Window.frames |MDN"  
[MdnWindoworworkerglobalscopeCrossoriginisolated]: https://developer.mozilla.org/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated "WindowOrWorkerGlobalScope.crossOriginIsolated | MDN"  

[WebhintMain]: https://webhint.io "webhint"  
[WebhintUserGuideHintsAccessibility]: https://webhint.io/docs/user-guide/hints/accessibility "アクセシビリティ | webhint"  
[WebhintUserGuideHintsCompatibility]: https://webhint.io/docs/user-guide/hints/compatibility "互換性 | webhint"  
[WebhintUserGuideHintsPerformance]: https://webhint.io/docs/user-guide/hints/performance "パフォーマンス | webhint"  
[WebhintUserGuideHintsPitfalls]: https://webhint.io/docs/user-guide/hints/pitfalls "落とし穴 | webhint"  
[WebhintUserGuideHintsPwa]: https://webhint.io/docs/user-guide/hints/pwa "PWA | webhint"  
[WebhintUserGuideHintsSecurity]: https://webhint.io/docs/user-guide/hints/security "セキュリティ | webhint"  

> [!NOTE]
> <span data-ttu-id="ac4ab-359">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-359">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ac4ab-360">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2020/11/devtools/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-360">The original page is found [here](https://developers.google.com/web/updates/2020/11/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ac4ab-362">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ac4ab-362">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
