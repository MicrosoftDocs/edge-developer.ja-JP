---
description: サービスの作業者の機能強化とそれぞれの使い方について説明します。
title: サービスワーカーの機能強化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、service worker、PWA
ms.openlocfilehash: 4e1b43235ccd7b108d2aadd1c803aa3276fa1265
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "11190039"
---
# <span data-ttu-id="c3611-104">サービスワーカーの機能強化</span><span class="sxs-lookup"><span data-stu-id="c3611-104">Service Worker improvements</span></span>  

<span data-ttu-id="c3611-105">この記事では、サービスの担当者と、各 [ユーザー][MdnServiceWorkerApi] を通過するネットワーク要求の改善について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3611-105">This article teaches you about improvements to [service workers][MdnServiceWorkerApi] and the network requests that pass through each one.</span></span>  <span data-ttu-id="c3611-106">**Service worker の機能強化**は、**ネットワーク**、**アプリケーション**、**ソース**の各ツールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3611-106">The **service worker improvements** are in the **Network**, **Application**, and **Sources** tools.</span></span>  <span data-ttu-id="c3611-107">この改善には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3611-107">The improvements include the following tasks.</span></span>  

*   <span data-ttu-id="c3611-108">サービスワーカーのタイムラインに基づいてデバッグします。</span><span class="sxs-lookup"><span data-stu-id="c3611-108">Debug based on Service Worker timelines.</span></span>  
    *   <span data-ttu-id="c3611-109">要求の開始とブートストラップの期間。</span><span class="sxs-lookup"><span data-stu-id="c3611-109">The start of a request and duration of the bootstrap.</span></span>  
    *   <span data-ttu-id="c3611-110">サービスワーカー登録に更新します。</span><span class="sxs-lookup"><span data-stu-id="c3611-110">Update to Service worker registration.</span></span>  
    *   <span data-ttu-id="c3611-111">[Fetch イベント][MdnFetchEvent]ハンドラーを使った要求の実行時。</span><span class="sxs-lookup"><span data-stu-id="c3611-111">The runtime of a request using the [fetch event][MdnFetchEvent] handler.</span></span>  
    *   <span data-ttu-id="c3611-112">クライアントを読み込むすべての fetch イベントのランタイム。</span><span class="sxs-lookup"><span data-stu-id="c3611-112">The runtime of all fetch events for loading a client.</span></span>  
*   <span data-ttu-id="c3611-113">Fetch イベントハンドラーのランタイムの詳細、イベントハンドラーのインストール、イベントハンドラーのアクティブ化について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3611-113">Explore the runtime details of fetch event handlers, install event handlers, and activate event handlers.</span></span>  
*   <span data-ttu-id="c3611-114">[ページスクリプト情報](#sources)を使った fetch イベントハンドラーのステップインとアウト。</span><span class="sxs-lookup"><span data-stu-id="c3611-114">Step into and out of fetch event handler with [page script information](#sources).</span></span>  

<span data-ttu-id="c3611-115">このエクスペリエンスは、3種類の開発者ツールにわたります。</span><span class="sxs-lookup"><span data-stu-id="c3611-115">The experiences span three different developer tools.</span></span>  

1.  <span data-ttu-id="c3611-116">[ネットワーク](#network)ツール。</span><span class="sxs-lookup"><span data-stu-id="c3611-116">The [Network](#network) tool.</span></span>  <span data-ttu-id="c3611-117">サービスワーカーを通じて実行されるネットワーク要求を選択し、 **タイミング** ツールでサービスワーカーの対応するタイムラインにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c3611-117">Choose a network request that runs through a service worker and access the corresponding timeline of the service worker in the **Timing** tool.</span></span>  
1.  <span data-ttu-id="c3611-118">[アプリケーション](#application)ツール。</span><span class="sxs-lookup"><span data-stu-id="c3611-118">The [Application](#application) tool.</span></span>  <span data-ttu-id="c3611-119">サービスワーカーをデバッグするには、 **サービスワーカー** ツールに移動します。</span><span class="sxs-lookup"><span data-stu-id="c3611-119">To debug the service workers, navigate to the **Service Workers** tool.</span></span>  
1.  <span data-ttu-id="c3611-120">[ソース](#sources)ツール。</span><span class="sxs-lookup"><span data-stu-id="c3611-120">The [Sources](#sources) tool.</span></span>  <span data-ttu-id="c3611-121">Fetch イベントハンドラーにステップインするときに、ページのスクリプト情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c3611-121">Access page script information when stepping into fetch event handlers.</span></span>  

## <span data-ttu-id="c3611-122">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="c3611-122">Network</span></span>  

:::image type="complex" source="../media/sw-network-timeline.msft.png" alt-text="ネットワークツールのサービスワーカーのタイムライン" lightbox="../media/sw-network-timeline.msft.png":::
   <span data-ttu-id="c3611-124">ネットワークビュー</span><span class="sxs-lookup"><span data-stu-id="c3611-124">Network view</span></span>  
:::image-end:::  

<span data-ttu-id="c3611-125">**ネットワーク**ツールの service worker デバッグ機能にアクセスするには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3611-125">To access the service worker debugging features in the **Network** tool, complete one of the following actions.</span></span>  

*   <span data-ttu-id="c3611-126">**ネットワーク**ツールで直接アクセスする。</span><span class="sxs-lookup"><span data-stu-id="c3611-126">Access directly in the **Network** tool.</span></span>  
*   <span data-ttu-id="c3611-127">**アプリケーション**ツールで開始されました。</span><span class="sxs-lookup"><span data-stu-id="c3611-127">Started in the **Application** tool.</span></span>  
    
### <span data-ttu-id="c3611-128">ルーティングを要求する</span><span class="sxs-lookup"><span data-stu-id="c3611-128">Request routing</span></span>  

<span data-ttu-id="c3611-129">要求のルーティングをより簡単にするために、タイムラインでは、サービスワーカーの起動時と fetch イベントが表示されるようになりました `respondWith` 。</span><span class="sxs-lookup"><span data-stu-id="c3611-129">To make request routing easier to visualize, timelines now display the service worker start-up and the `respondWith` fetch events.</span></span>  <span data-ttu-id="c3611-130">サービスワーカーを通じて渡されたネットワーク要求をデバッグし、視覚化するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3611-130">To debug and visualize a network request that passed through a service worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="c3611-131">サービスワーカーを通じて行われたネットワーク要求を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3611-131">Choose the network request that went through a service worker.</span></span>  
1.  <span data-ttu-id="c3611-132">**タイミング**ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="c3611-132">Open the **Timing** tool.</span></span>  
    
### <span data-ttu-id="c3611-133">イベントの取得</span><span class="sxs-lookup"><span data-stu-id="c3611-133">Fetch events</span></span>  

<span data-ttu-id="c3611-134">Fetch イベントの詳細については、 `respondWith` の左にあるドロップダウン矢印を選択して `respondWith` ください。</span><span class="sxs-lookup"><span data-stu-id="c3611-134">To learn more about the `respondWith` fetch events, choose the dropdown arrow to the left of the `respondWith`.</span></span>  <span data-ttu-id="c3611-135">受信した **元の要求** と **応答**の詳細については、対応するドロップダウン矢印を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3611-135">To find more details about the **Original Request** and **Response Received**, use the corresponding dropdown arrows.</span></span>  

## <span data-ttu-id="c3611-136">Application</span><span class="sxs-lookup"><span data-stu-id="c3611-136">Application</span></span>  

:::image type="complex" source="../media/sw-application-timeline.msft.png" alt-text="アプリケーションビュー" lightbox="../media/sw-application-timeline.msft.png":::
   <span data-ttu-id="c3611-138">アプリケーションビュー</span><span class="sxs-lookup"><span data-stu-id="c3611-138">Application view</span></span>  
:::image-end:::  

### <span data-ttu-id="c3611-139">サービスワーカーの更新タイムライン</span><span class="sxs-lookup"><span data-stu-id="c3611-139">Service worker update timeline</span></span>  

<span data-ttu-id="c3611-140">Microsoft Edge DevTools チームは、サービスワーカーの更新ライフサイクルを反映するために、 **アプリケーション** ツールにタイムラインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="c3611-140">The Microsoft Edge DevTools team added a timeline in the **Application** tool to reflect the update lifecycle of the service worker.</span></span>  <span data-ttu-id="c3611-141">インストールイベントとライセンス認証イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3611-141">It displays the installation and activation events.</span></span>  <span data-ttu-id="c3611-142">各イベントには、より詳しい情報を提供するためのドロップダウン矢印があります。</span><span class="sxs-lookup"><span data-stu-id="c3611-142">Each of the events has a corresponding dropdown arrow to give you more details.</span></span>  

### <span data-ttu-id="c3611-143">ルーティングイベントとフェッチイベントを要求する</span><span class="sxs-lookup"><span data-stu-id="c3611-143">Request routing and fetch events</span></span>  

<span data-ttu-id="c3611-144">これで、コンソールのドロアーから **ネットワーク** ツールを介してサービスワーカーのタイムラインにアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c3611-144">You may now access the service worker timelines through the **Network** tool in the console drawer.</span></span>  <span data-ttu-id="c3611-145">この機能は、パフォーマンスを向上させると共に、UI の重複を最小限に抑え、より包括的なデバッグエクスペリエンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3611-145">The feature benefits performance, minimizes UI duplication, and creates a more comprehensive debugging experience.</span></span>  

1.  <span data-ttu-id="c3611-146">デバッグしているサービスワーカーを開きます。</span><span class="sxs-lookup"><span data-stu-id="c3611-146">Open the service worker you are debugging.</span></span>  
1.  <span data-ttu-id="c3611-147">[ **ネットワーク** ] ボタンを選んで、 [要求ルーティングエクスペリエンス](#network)を開きます。</span><span class="sxs-lookup"><span data-stu-id="c3611-147">Choose the **Network** button to open up the [request routing experience](#network).</span></span>  
1.  <span data-ttu-id="c3611-148">Fetch イベントの要求と応答の情報については、返答 **Dwith** ドロップダウンを使います。</span><span class="sxs-lookup"><span data-stu-id="c3611-148">Use the **respondWith** dropdowns for fetch event request and response information.</span></span>  

<span data-ttu-id="c3611-149">**ネットワーク**ツールには、デバッグしているサービスワーカーを通じて発生したネットワーク要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3611-149">The **Network** tool displays the network requests that went through the service worker you are debugging.</span></span>  <span data-ttu-id="c3611-150">自動フィルターを使用すると、調査を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c3611-150">The automatic filter is a way to narrow down your exploration.</span></span>

## <span data-ttu-id="c3611-151">Sources</span><span class="sxs-lookup"><span data-stu-id="c3611-151">Sources</span></span>  

:::image type="complex" source="../media/sw-sources.msft.png" alt-text="DOM ビュー" lightbox="../media/sw-sources.msft.png":::
   <span data-ttu-id="c3611-153">DOM ビュー</span><span class="sxs-lookup"><span data-stu-id="c3611-153">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="c3611-154">さらに多くのスタック情報を見つけるには、fetch ハンドラーにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="c3611-154">To find more stack information, set a break point in the fetch handler.</span></span>  <span data-ttu-id="c3611-155">詳細情報は、ページスクリプトでリソースが要求された場所を示します。</span><span class="sxs-lookup"><span data-stu-id="c3611-155">The details lead to where the resource is requested in the page script.</span></span>  <span data-ttu-id="c3611-156">デバッガーが fetch ハンドラー内で一時停止すると、パネルの右側にスタック情報がまとめて表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3611-156">When the debugger pauses inside a fetch handler, a combined stack information is displayed in the panel to the right.</span></span>  <span data-ttu-id="c3611-157">その後は、スタックフレーム内を移動することができます。</span><span class="sxs-lookup"><span data-stu-id="c3611-157">After that, you may move around in the stack frames.</span></span>  

### <span data-ttu-id="c3611-158">今後の作業</span><span class="sxs-lookup"><span data-stu-id="c3611-158">Future work</span></span>  

<span data-ttu-id="c3611-159">Microsoft Edge DevTools チームは、キャッシュの詳細をさらに開発することを計画しており、 [プログレッシブ Web アプリケーション][MdnProgressiveWebApps] 開発者向けのサービスワーカーのデバッグエクスペリエンスを向上させるその他の方法について調査しています。</span><span class="sxs-lookup"><span data-stu-id="c3611-159">The Microsoft Edge DevTools team plans to further develop the cache detail and are investigating more ways to improve the service worker debugging experience for [Progressive Web Application][MdnProgressiveWebApps] developers.</span></span>  

## <span data-ttu-id="c3611-160">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c3611-160">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MdnFetchEvent]: https://developer.mozilla.org/docs/Web/API/FetchEvent "FetchEvent |MDN"  
[MdnProgressiveWebApps]: https://developer.mozilla.org/docs/Web/Progressive_web_apps "プログレッシブ web アプリ (PWAs) |MDN"  
[MdnServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
