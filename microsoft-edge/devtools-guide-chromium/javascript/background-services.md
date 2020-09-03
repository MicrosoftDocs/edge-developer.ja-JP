---
description: Microsoft Edge DevTools を使って、バックグラウンドでの取り出し、バックグラウンド同期、通知、プッシュメッセージをデバッグする方法について説明します。
title: Microsoft Edge DevTools によるバックグラウンドサービスのデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1724bd3a5e45734555650c3d46e377161a3a7c65
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992870"
---
<!-- Copyright Kayce Basques 
   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0
       
   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  





# <span data-ttu-id="39441-104">Microsoft Edge DevTools によるバックグラウンドサービスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="39441-104">Debug Background Services With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="39441-105">Microsoft Edge DevTools の [ **バックグラウンドサービス** ] セクションは、ユーザーが web サイトを開いていない場合でも web サイトが更新を送受信できるようにする JavaScript api 用のツールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="39441-105">The **Background Services** section of Microsoft Edge DevTools is a collection of tools for the JavaScript APIs that enables your website to send and receive updates even when a user does not have your website open.</span></span>  
<span data-ttu-id="39441-106">バックグラウンドサービスは、機能的には [バックグラウンドプロセス] [WikiBackgroundProcess] と似ています。</span><span class="sxs-lookup"><span data-stu-id="39441-106">A background service is functionally similar to a [background process][WikiBackgroundProcess].</span></span>  
<span data-ttu-id="39441-107">Microsoft Edge DevTools は、次の各 Api をバックグラウンドサービスと見なします。</span><span class="sxs-lookup"><span data-stu-id="39441-107">Microsoft Edge DevTools considers each of the following APIs to be a background service:</span></span>  

*   [<span data-ttu-id="39441-108">バックグラウンドでの取得</span><span class="sxs-lookup"><span data-stu-id="39441-108">Background Fetch</span></span>](#background-fetch)  
*   [<span data-ttu-id="39441-109">バックグラウンド同期</span><span class="sxs-lookup"><span data-stu-id="39441-109">Background Sync</span></span>](#background-sync)  
*   [<span data-ttu-id="39441-110">通知</span><span class="sxs-lookup"><span data-stu-id="39441-110">Notifications</span></span>](#notifications)  
*   [<span data-ttu-id="39441-111">メッセージをプッシュする</span><span class="sxs-lookup"><span data-stu-id="39441-111">Push Messages</span></span>](#push-messages)  
    
<span data-ttu-id="39441-112">Microsoft Edge DevTools では、DevTools が開いていない場合でも、3日間はバックグラウンドサービスイベントをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="39441-112">Microsoft Edge DevTools can log background service events for 3 days, even when DevTools is not open.</span></span>  
<span data-ttu-id="39441-113">これは、イベントが予期したとおりに送受信されるようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39441-113">This can help you make sure that events are being sent and received as expected.</span></span>  <span data-ttu-id="39441-114">各イベントの詳細も調べることができます。</span><span class="sxs-lookup"><span data-stu-id="39441-114">You may also inspect the details of each event.</span></span>  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="プッシュメッセージングウィンドウのイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   <span data-ttu-id="39441-116">**プッシュメッセージング**ウィンドウのイベントの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="39441-116">View the details of an event in the **Push Messaging** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="39441-117">バックグラウンドでの取得</span><span class="sxs-lookup"><span data-stu-id="39441-117">Background Fetch</span></span>   

<span data-ttu-id="39441-118">*バックグラウンドフェッチ API*\* を使用すると、**サービスワーカー**は、ムービーやポッドキャストなどの大規模なリソースを、バックグラウンドサービスとして確実にダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="39441-118">The *Background Fetch API*\* enables a **service worker** to reliably download large resources, like movies or podcasts, as a background service.</span></span>  <span data-ttu-id="39441-119">DevTools が開いていない場合でも、3日間のバックグラウンドの取り出しイベントをログに記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39441-119">To log Background Fetch event for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background fetch api section when available -->  

1.  <span data-ttu-id="39441-120">[DevTools を開き][OpenDevTools]ます。</span><span class="sxs-lookup"><span data-stu-id="39441-120">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="39441-121">**アプリケーション**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="39441-121">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="39441-122">[バックグラウンドでの **取得** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="39441-122">Open the **Background Fetch** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="[バックグラウンドでの取り出し] ウィンドウ" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       <span data-ttu-id="39441-124">[ **バックグラウンド** での取り出し] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="39441-124">The **Background Fetch** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="39441-125">[ **レコーディング** \ ( ![ レコード ][ImageRecordIcon] \)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39441-125">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="39441-126">一部のバックグラウンドフェッチアクティビティがトリガーされると、DevTools によってイベントがテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="39441-126">After triggering some Background Fetch activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="[バックグラウンドでの取得] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       <span data-ttu-id="39441-128">[バックグラウンドでの **取得** ] ウィンドウのイベントのログ</span><span class="sxs-lookup"><span data-stu-id="39441-128">A log of events in the **Background Fetch** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="39441-129">イベントをクリックすると、テーブルの下の領域に詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39441-129">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="[バックグラウンドでの取得] ウィンドウのイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       <span data-ttu-id="39441-131">[バックグラウンドでの **取得** ] ウィンドウのイベントの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="39441-131">View the details of an event in the **Background Fetch** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="39441-132">バックグラウンド同期</span><span class="sxs-lookup"><span data-stu-id="39441-132">Background Sync</span></span>   

<span data-ttu-id="39441-133">**バックグラウンド同期 API**では、信頼性の高いインターネット接続を再確立した後、オフライン**サービスワーカー**がサーバーにデータを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="39441-133">The **Background Sync API** enables an offline **service worker** to send data to a server once it has re-established a reliable internet connection.</span></span>  <span data-ttu-id="39441-134">DevTools が開いていない場合でも、3日間のバックグラウンド同期イベントをログに記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39441-134">To log Background Sync events for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background sync api section when available -->  

1.  <span data-ttu-id="39441-135">[DevTools を開き][OpenDevTools]ます。</span><span class="sxs-lookup"><span data-stu-id="39441-135">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="39441-136">**アプリケーション**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="39441-136">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="39441-137">[ **バックグラウンドの同期** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="39441-137">Open the **Background Sync** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text="[バックグラウンドの同期] ウィンドウ" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       <span data-ttu-id="39441-139">[ **バックグラウンドの同期** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="39441-139">The **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="39441-140">[ **レコーディング** \ ( ![ レコード ][ImageRecordIcon] \)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39441-140">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="39441-141">一部のバックグラウンド同期アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="39441-141">After triggering some Background Sync activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="[バックグラウンド同期] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       <span data-ttu-id="39441-143">[ **バックグラウンド同期** ] ウィンドウのイベントのログ</span><span class="sxs-lookup"><span data-stu-id="39441-143">A log of events in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="39441-144">イベントをクリックすると、テーブルの下の領域に詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39441-144">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="バックグラウンドの同期ウィンドウのイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       <span data-ttu-id="39441-146">**バックグラウンドの同期**ウィンドウのイベントの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="39441-146">View the details of an event in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="39441-147">通知</span><span class="sxs-lookup"><span data-stu-id="39441-147">Notifications</span></span> 

<span data-ttu-id="39441-148">**サービスワーカー**がサーバーから[プッシュメッセージ][MDNPush]を受信した後、サービスワーカーは[通知 API][MDNNotifications]を使ってユーザーにデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="39441-148">After a **service worker** has received a [Push Message][MDNPush] from a server, the service worker uses the [Notifications API][MDNNotifications] to display the data to a user.</span></span>  <span data-ttu-id="39441-149">DevTools が開いていない場合でも、3日間の通知をログに記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39441-149">To log Notifications for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="39441-150">[DevTools を開き][OpenDevTools]ます。</span><span class="sxs-lookup"><span data-stu-id="39441-150">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="39441-151">**アプリケーション**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="39441-151">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="39441-152">[ **通知** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="39441-152">Open the **Notifications** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="[通知] ウィンドウ" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       <span data-ttu-id="39441-154">[ **通知** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="39441-154">The **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="39441-155">[ **レコーディング** \ ( ![ レコード ][ImageRecordIcon] \)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39441-155">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="39441-156">一部の通知アクティビティをトリガーすると、DevTools によってイベントがテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="39441-156">After triggering some Notifications activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="通知ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       <span data-ttu-id="39441-158">**通知**ウィンドウのイベントのログ</span><span class="sxs-lookup"><span data-stu-id="39441-158">A log of events in the **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="39441-159">イベントをクリックすると、テーブルの下の領域に詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39441-159">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="[通知] ウィンドウのイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       <span data-ttu-id="39441-161">[ **通知** ] ウィンドウのイベントの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="39441-161">View the details of an event in the **Notifications** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="39441-162">メッセージをプッシュする</span><span class="sxs-lookup"><span data-stu-id="39441-162">Push Messages</span></span> 

<span data-ttu-id="39441-163">ユーザーにプッシュ通知を表示するには、 **サービスワーカー** はまず、 [プッシュメッセージ API][MDNPush] を使ってサーバーからデータを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39441-163">To display a push notification to a user, a **service worker** must first use the [Push Message API][MDNPush] to receive data from a server.</span></span>  <span data-ttu-id="39441-164">サービスワーカーが通知を表示する準備ができたら、 [通知 API][MDNNotifications]を使います。</span><span class="sxs-lookup"><span data-stu-id="39441-164">When the service worker is ready to display the notification, it uses the [Notifications API][MDNNotifications].</span></span>  <span data-ttu-id="39441-165">DevTools が開いていない場合でも、3日間、プッシュメッセージをログに記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39441-165">To log Push Messages for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="39441-166">[DevTools を開き][OpenDevTools]ます。</span><span class="sxs-lookup"><span data-stu-id="39441-166">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="39441-167">**アプリケーション**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="39441-167">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="39441-168">[ **プッシュメッセージング** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="39441-168">Open the **Push Messaging** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       <span data-ttu-id="39441-170">[ **プッシュメッセージング** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="39441-170">The **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="39441-171">[ **レコーディング** \ ( ![ レコード ][ImageRecordIcon] \)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39441-171">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
    <span data-ttu-id="39441-172">一部のプッシュメッセージのアクティビティがトリガーされた後、DevTools ではイベントがテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="39441-172">After triggering some Push Message activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュメッセージング] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       <span data-ttu-id="39441-174">[ **プッシュメッセージング** ] ウィンドウのイベントのログ</span><span class="sxs-lookup"><span data-stu-id="39441-174">A log of events in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="39441-175">イベントをクリックすると、テーブルの下の領域に詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39441-175">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="プッシュメッセージングウィンドウのイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       <span data-ttu-id="39441-177">**プッシュメッセージング**ウィンドウのイベントの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="39441-177">View the details of an event in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageRecordIcon]: ../media/record-icon.msft.png  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open.md "Microsoft Edge (Chromium) 開発者ツールを開く |Microsoft ドキュメント"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "バックグラウンドプロセス-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="39441-182">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="39441-182">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="39441-183">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="39441-183">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  
[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="39441-185">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="39441-185">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
