---
description: Service Worker の機能強化とそれぞれの使い方について説明します。
title: サービス ワーカーの機能強化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, service worker, PWA
ms.openlocfilehash: 2f32155d1d28d1e65ad29abfe58a414f3e3c6ed7
ms.sourcegitcommit: 661e8def3f27cea381c59ac38954789e736c18f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387278"
---
# <a name="service-worker-improvements"></a><span data-ttu-id="eb0ae-104">サービス ワーカーの機能強化</span><span class="sxs-lookup"><span data-stu-id="eb0ae-104">Service Worker improvements</span></span>  

<span data-ttu-id="eb0ae-105">この記事では、サービス ワーカーを操作するための開発者ツールの改善[][MdnServiceWorkerApi]と、各サービス ワーカーを通過するネットワーク要求について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-105">This article teaches you about improvements to developer tools for working with [service workers][MdnServiceWorkerApi] and the network requests that pass through each one.</span></span>  <span data-ttu-id="eb0ae-106">サービス**ワーカーの機能強化は、[** ネットワーク **]、[アプリケーション**]、および [ソース]**ツールにあります**。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-106">The **service worker improvements** are in the **Network**, **Application**, and **Sources** tools.</span></span>  <span data-ttu-id="eb0ae-107">この機能強化により、以下のタスクが簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-107">The improvements simplify the following tasks.</span></span>  

*   <span data-ttu-id="eb0ae-108">サービス ワーカーのタイムラインに基づいてデバッグします。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-108">Debug based on Service Worker timelines.</span></span>  
    *   <span data-ttu-id="eb0ae-109">ブートストラップの要求の開始と期間。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-109">The start of a request and duration of the bootstrap.</span></span>  
    *   <span data-ttu-id="eb0ae-110">サービス ワーカー登録に更新します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-110">Update to Service worker registration.</span></span>  
    *   <span data-ttu-id="eb0ae-111">フェッチ イベント ハンドラーを使用した [要求の][MdnFetchEvent] ランタイム。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-111">The runtime of a request using the [fetch event][MdnFetchEvent] handler.</span></span>  
    *   <span data-ttu-id="eb0ae-112">クライアントを読み込むすべてのフェッチ イベントのランタイム。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-112">The runtime of all fetch events for loading a client.</span></span>  
*   <span data-ttu-id="eb0ae-113">フェッチ イベント ハンドラーの実行時の詳細を確認し、イベント ハンドラーをインストールし、イベント ハンドラーをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-113">Explore the runtime details of fetch event handlers, install event handlers, and activate event handlers.</span></span>  
*   <span data-ttu-id="eb0ae-114">ページ スクリプト情報を使用してフェッチ イベント ハンドラーにステップ [アウトします](#sources)。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-114">Step into and out of fetch event handler with [page script information](#sources).</span></span>  
    
<span data-ttu-id="eb0ae-115">エクスペリエンスは、3 つの異なる開発者ツールにまたがっています。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-115">The experiences span three different developer tools.</span></span>  

1.  <span data-ttu-id="eb0ae-116">ネットワーク [ツール](#network) 。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-116">The [Network](#network) tool.</span></span>  <span data-ttu-id="eb0ae-117">サービス ワーカーを介して実行されるネットワーク要求を選択し、タイミング ツールでサービス ワーカーの対応するタイムラインに **アクセス** します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-117">Choose a network request that runs through a service worker and access the corresponding timeline of the service worker in the **Timing** tool.</span></span>  
1.  <span data-ttu-id="eb0ae-118">アプリケーション [ツール](#application) 。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-118">The [Application](#application) tool.</span></span>  <span data-ttu-id="eb0ae-119">サービス ワーカーをデバッグするには、サービス ワーカー **ツールに移動** します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-119">To debug the service workers, navigate to the **Service Workers** tool.</span></span>  
1.  <span data-ttu-id="eb0ae-120">[ [ソース]](#sources) ツール。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-120">The [Sources](#sources) tool.</span></span>  <span data-ttu-id="eb0ae-121">フェッチ イベント ハンドラーにステップ インするときにページ スクリプト情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-121">Access page script information when stepping into fetch event handlers.</span></span>  
    
## <a name="network"></a><span data-ttu-id="eb0ae-122">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="eb0ae-122">Network</span></span>  

:::image type="complex" source="../media/sw-network-timeline.msft.png" alt-text="ネットワーク ツールのサービス ワーカー タイムライン" lightbox="../media/sw-network-timeline.msft.png":::
   <span data-ttu-id="eb0ae-124">ネットワーク ビュー</span><span class="sxs-lookup"><span data-stu-id="eb0ae-124">Network view</span></span>  
:::image-end:::  

<span data-ttu-id="eb0ae-125">ネットワーク ツールでサービス ワーカーのデバッグ機能に **アクセスするには** 、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-125">To access the service worker debugging features in the **Network** tool, complete one of the following actions.</span></span>  

*   <span data-ttu-id="eb0ae-126">ネットワーク ツールで **直接アクセス** します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-126">Access directly in the **Network** tool.</span></span>  
*   <span data-ttu-id="eb0ae-127">アプリケーション ツール **で開始** します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-127">Started in the **Application** tool.</span></span>  
    
### <a name="request-routing"></a><span data-ttu-id="eb0ae-128">要求ルーティング</span><span class="sxs-lookup"><span data-stu-id="eb0ae-128">Request routing</span></span>  

<span data-ttu-id="eb0ae-129">要求ルーティングを視覚化しやすくするために、タイムラインにサービス ワーカーの起動とフェッチ イベントが `respondWith` 表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-129">To make request routing easier to visualize, timelines now display the service worker start-up and the `respondWith` fetch events.</span></span>  <span data-ttu-id="eb0ae-130">サービス ワーカーを介して渡されたネットワーク要求をデバッグおよび視覚化するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-130">To debug and visualize a network request that passed through a service worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="eb0ae-131">サービス ワーカーを経由したネットワーク要求を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-131">Choose the network request that went through a service worker.</span></span>  
1.  <span data-ttu-id="eb0ae-132">タイミング ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-132">Open the **Timing** tool.</span></span>  
    
### <a name="fetch-events"></a><span data-ttu-id="eb0ae-133">イベントのフェッチ</span><span class="sxs-lookup"><span data-stu-id="eb0ae-133">Fetch events</span></span>  

<span data-ttu-id="eb0ae-134">フェッチ イベントの詳細 `respondWith` については、左側のドロップダウン矢印を選択します `respondWith` 。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-134">To learn more about the `respondWith` fetch events, choose the dropdown arrow to the left of the `respondWith`.</span></span>  <span data-ttu-id="eb0ae-135">元の要求と **受信した応答** の詳細については **、対応する**ドロップダウン矢印を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-135">To find more details about the **Original Request** and **Response Received**, use the corresponding dropdown arrows.</span></span>  

## <a name="application"></a><span data-ttu-id="eb0ae-136">Application</span><span class="sxs-lookup"><span data-stu-id="eb0ae-136">Application</span></span>  

:::image type="complex" source="../media/sw-application-timeline.msft.png" alt-text="アプリケーション ビュー" lightbox="../media/sw-application-timeline.msft.png":::
   <span data-ttu-id="eb0ae-138">アプリケーション ビュー</span><span class="sxs-lookup"><span data-stu-id="eb0ae-138">Application view</span></span>  
:::image-end:::  

### <a name="service-worker-update-timeline"></a><span data-ttu-id="eb0ae-139">サービス ワーカーの更新タイムライン</span><span class="sxs-lookup"><span data-stu-id="eb0ae-139">Service worker update timeline</span></span>  

<span data-ttu-id="eb0ae-140">Microsoft Edge DevTools チームは、サービス ワーカーの更新ライフサイクルを反映するために、アプリケーション ツールにタイムラインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-140">The Microsoft Edge DevTools team added a timeline in the **Application** tool to reflect the update lifecycle of the service worker.</span></span>  <span data-ttu-id="eb0ae-141">インストールイベントとライセンス認証イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-141">It displays the installation and activation events.</span></span>  <span data-ttu-id="eb0ae-142">各イベントには、詳細を示す対応するドロップダウン矢印があります。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-142">Each of the events has a corresponding dropdown arrow to give you more details.</span></span>  

### <a name="request-routing-and-fetch-events"></a><span data-ttu-id="eb0ae-143">ルーティングイベントとフェッチ イベントの要求</span><span class="sxs-lookup"><span data-stu-id="eb0ae-143">Request routing and fetch events</span></span>  

<span data-ttu-id="eb0ae-144">これで、コンソール ドロワーのネットワーク ツールを 使用してサービス ワーカーのタイムラインにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-144">You may now access the service worker timelines through the **Network** tool in the console drawer.</span></span>  <span data-ttu-id="eb0ae-145">この機能は、パフォーマンスを向上し、UI の重複を最小限に抑え、より包括的なデバッグ エクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-145">The feature benefits performance, minimizes UI duplication, and creates a more comprehensive debugging experience.</span></span>  

1.  <span data-ttu-id="eb0ae-146">デバッグ中のサービス ワーカーを開きます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-146">Open the service worker you are debugging.</span></span>  
1.  <span data-ttu-id="eb0ae-147">[ネットワーク] **ボタンを** 選択して、要求ルーティング [エクスペリエンスを開きます](#network)。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-147">Choose the **Network** button to open up the [request routing experience](#network).</span></span>  
1.  <span data-ttu-id="eb0ae-148">イベント要求と **応答情報をフェッチするには、respondWith** ドロップダウンを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-148">Use the **respondWith** dropdowns for fetch event request and response information.</span></span>  

<span data-ttu-id="eb0ae-149">ネットワーク **ツール** には、デバッグ中のサービス ワーカーを経由したネットワーク要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-149">The **Network** tool displays the network requests that went through the service worker you are debugging.</span></span>  <span data-ttu-id="eb0ae-150">自動フィルターは、探索を絞り込む方法です。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-150">The automatic filter is a way to narrow down your exploration.</span></span>

## <a name="sources"></a><span data-ttu-id="eb0ae-151">Sources</span><span class="sxs-lookup"><span data-stu-id="eb0ae-151">Sources</span></span>  

:::image type="complex" source="../media/sw-sources.msft.png" alt-text="DOM ビュー" lightbox="../media/sw-sources.msft.png":::
   <span data-ttu-id="eb0ae-153">DOM ビュー</span><span class="sxs-lookup"><span data-stu-id="eb0ae-153">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="eb0ae-154">スタック情報の詳細を見つけるには、フェッチ ハンドラーでブレーク ポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-154">To find more stack information, set a break point in the fetch handler.</span></span>  <span data-ttu-id="eb0ae-155">詳細は、ページ スクリプトでリソースが要求される場所につながる。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-155">The details lead to where the resource is requested in the page script.</span></span>  <span data-ttu-id="eb0ae-156">デバッガーがフェッチ ハンドラー内で一時停止すると、結合されたスタック情報が右側のパネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-156">When the debugger pauses inside a fetch handler, a combined stack information is displayed in the panel to the right.</span></span>  <span data-ttu-id="eb0ae-157">その後、スタック フレーム内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-157">After that, you may move around in the stack frames.</span></span>  

### <a name="future-work"></a><span data-ttu-id="eb0ae-158">今後の作業</span><span class="sxs-lookup"><span data-stu-id="eb0ae-158">Future work</span></span>  

<span data-ttu-id="eb0ae-159">Microsoft Edge DevTools チームは、キャッシュの詳細をさらに開発し、 [プログレッシブ Web][MdnProgressiveWebApps] アプリケーション開発者向けのサービス ワーカー デバッグ エクスペリエンスを向上させる方法を検討しています。</span><span class="sxs-lookup"><span data-stu-id="eb0ae-159">The Microsoft Edge DevTools team plans to further develop the cache detail and are investigating more ways to improve the service worker debugging experience for [Progressive Web Application][MdnProgressiveWebApps] developers.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="eb0ae-160">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="eb0ae-160">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MdnFetchEvent]: https://developer.mozilla.org/docs/Web/API/FetchEvent "FetchEvent |MDN"  
[MdnProgressiveWebApps]: https://developer.mozilla.org/docs/Web/Progressive_web_apps "プログレッシブ Web アプリ (PWAs) |MDN"  
[MdnServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
