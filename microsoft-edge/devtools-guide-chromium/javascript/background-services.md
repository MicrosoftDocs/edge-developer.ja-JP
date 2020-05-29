---
title: Microsoft Edge DevTools によるバックグラウンドサービスのデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0ac2a057307a939069cbb3b48ecd38c9de71e5db
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581832"
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





# <span data-ttu-id="7765f-103">Microsoft Edge DevTools によるバックグラウンドサービスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="7765f-103">Debug Background Services With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="7765f-104">Microsoft Edge DevTools の [**バックグラウンドサービス**] セクションは、ユーザーが web サイトを開いていない場合でも web サイトが更新を送受信できるようにする JavaScript api 用のツールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="7765f-104">The **Background Services** section of Microsoft Edge DevTools is a collection of tools for the JavaScript APIs that enables your website to send and receive updates even when a user does not have your website open.</span></span>  
<span data-ttu-id="7765f-105">バックグラウンドサービスは、機能的には [バックグラウンドプロセス] [WikiBackgroundProcess] と似ています。</span><span class="sxs-lookup"><span data-stu-id="7765f-105">A background service is functionally similar to a [background process][WikiBackgroundProcess].</span></span>  
<span data-ttu-id="7765f-106">Microsoft Edge DevTools は、次の各 Api をバックグラウンドサービスと見なします。</span><span class="sxs-lookup"><span data-stu-id="7765f-106">Microsoft Edge DevTools considers each of the following APIs to be a background service:</span></span>  

*   [<span data-ttu-id="7765f-107">バックグラウンドでの取得</span><span class="sxs-lookup"><span data-stu-id="7765f-107">Background Fetch</span></span>](#background-fetch)  
*   [<span data-ttu-id="7765f-108">バックグラウンド同期</span><span class="sxs-lookup"><span data-stu-id="7765f-108">Background Sync</span></span>](#background-sync)  
*   [<span data-ttu-id="7765f-109">通知</span><span class="sxs-lookup"><span data-stu-id="7765f-109">Notifications</span></span>](#notifications)  
*   [<span data-ttu-id="7765f-110">メッセージをプッシュする</span><span class="sxs-lookup"><span data-stu-id="7765f-110">Push Messages</span></span>](#push-messages)  

<span data-ttu-id="7765f-111">Microsoft Edge DevTools では、DevTools が開いていない場合でも、3日間はバックグラウンドサービスイベントをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="7765f-111">Microsoft Edge DevTools can log background service events for 3 days, even when DevTools is not open.</span></span>  
<span data-ttu-id="7765f-112">これは、イベントが予期したとおりに送受信されるようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7765f-112">This can help you make sure that events are being sent and received as expected.</span></span>  <span data-ttu-id="7765f-113">各イベントの詳細も調べることができます。</span><span class="sxs-lookup"><span data-stu-id="7765f-113">You can also inspect the details of each event.</span></span>  

> ##### <span data-ttu-id="7765f-114">図 1</span><span class="sxs-lookup"><span data-stu-id="7765f-114">Figure 1</span></span>  
> <span data-ttu-id="7765f-115">プッシュメッセージングウィンドウのイベントの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="7765f-115">Viewing the details of an event in the Push Messaging pane</span></span>  
> ![プッシュメッセージングウィンドウのイベントの詳細の表示][PushDetails]  

## <span data-ttu-id="7765f-117">バックグラウンドでの取得</span><span class="sxs-lookup"><span data-stu-id="7765f-117">Background Fetch</span></span>   

<span data-ttu-id="7765f-118">*バックグラウンドフェッチ API*\* を使用すると、**サービスワーカー**は、ムービーやポッドキャストなどの大規模なリソースを、バックグラウンドサービスとして確実にダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7765f-118">The *Background Fetch API*\* enables a **service worker** to reliably download large resources, like movies or podcasts, as a background service.</span></span>  <span data-ttu-id="7765f-119">DevTools が開いていない場合でも、3日間のバックグラウンドの取り出しイベントをログに記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7765f-119">To log Background Fetch event for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background fetch api section when available -->  

1.  <span data-ttu-id="7765f-120">[DevTools を開き][OpenDevTools]ます。</span><span class="sxs-lookup"><span data-stu-id="7765f-120">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="7765f-121">**アプリケーション**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7765f-121">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="7765f-122">[バックグラウンドでの**取得**] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="7765f-122">Open the **Background Fetch** pane.</span></span>  
    
    > ##### <span data-ttu-id="7765f-123">図 2</span><span class="sxs-lookup"><span data-stu-id="7765f-123">Figure 2</span></span>  
    > <span data-ttu-id="7765f-124">[バックグラウンドでの取り出し] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7765f-124">The Background Fetch pane</span></span>  
    > ![[バックグラウンドでの取り出し] ウィンドウ][FetchEmpty]  
    
1.  <span data-ttu-id="7765f-126">[**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="7765f-126">Click **Record** ![Record][ImageRecordIcon].</span></span>  
   <span data-ttu-id="7765f-127">一部のバックグラウンドフェッチアクティビティがトリガーされると、DevTools によってイベントがテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="7765f-127">After triggering some Background Fetch activity, DevTools logs the events to the table.</span></span>  
    
    > ##### <span data-ttu-id="7765f-128">図 3</span><span class="sxs-lookup"><span data-stu-id="7765f-128">Figure 3</span></span>  
    > <span data-ttu-id="7765f-129">[バックグラウンドでの取得] ウィンドウのイベントのログ</span><span class="sxs-lookup"><span data-stu-id="7765f-129">A log of events in the Background Fetch pane</span></span>  
    > ![[バックグラウンドでの取得] ウィンドウのイベントのログ][FetchLog]  
    
1.  <span data-ttu-id="7765f-131">イベントをクリックすると、テーブルの下の領域に詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7765f-131">Click an event to view its details in the space below the table.</span></span>  
    
    > ##### <span data-ttu-id="7765f-132">図 4</span><span class="sxs-lookup"><span data-stu-id="7765f-132">Figure 4</span></span>  
    > <span data-ttu-id="7765f-133">[バックグラウンドでの取得] ウィンドウのイベントの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="7765f-133">Viewing the details of an event in the Background Fetch pane</span></span>  
    > ![[バックグラウンドでの取得] ウィンドウのイベントの詳細の表示][FetchDetails]  

## <span data-ttu-id="7765f-135">バックグラウンド同期</span><span class="sxs-lookup"><span data-stu-id="7765f-135">Background Sync</span></span>   

<span data-ttu-id="7765f-136">**バックグラウンド同期 API**では、信頼性の高いインターネット接続を再確立した後、オフライン**サービスワーカー**がサーバーにデータを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7765f-136">The **Background Sync API** enables an offline **service worker** to send data to a server once it has re-established a reliable internet connection.</span></span>  <span data-ttu-id="7765f-137">DevTools が開いていない場合でも、3日間のバックグラウンド同期イベントをログに記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7765f-137">To log Background Sync events for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background sync api section when available -->  

1.  <span data-ttu-id="7765f-138">[DevTools を開き][OpenDevTools]ます。</span><span class="sxs-lookup"><span data-stu-id="7765f-138">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="7765f-139">**アプリケーション**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7765f-139">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="7765f-140">[**バックグラウンドの同期**] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="7765f-140">Open the **Background Sync** pane.</span></span>  
    
    > ##### <span data-ttu-id="7765f-141">図 5</span><span class="sxs-lookup"><span data-stu-id="7765f-141">Figure 5</span></span>  
    > <span data-ttu-id="7765f-142">[バックグラウンドの同期] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7765f-142">The Background Sync pane</span></span>  
    > ![[バックグラウンドの同期] ウィンドウ][SyncEmpty]  
    
1.  <span data-ttu-id="7765f-144">[**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="7765f-144">Click **Record** ![Record][ImageRecordIcon].</span></span>  
   <span data-ttu-id="7765f-145">一部のバックグラウンド同期アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="7765f-145">After triggering some Background Sync activity, DevTools logs the events to the table.</span></span>  
    
    > ##### <span data-ttu-id="7765f-146">図 6</span><span class="sxs-lookup"><span data-stu-id="7765f-146">Figure 6</span></span>  
    > <span data-ttu-id="7765f-147">[バックグラウンド同期] ウィンドウのイベントのログ</span><span class="sxs-lookup"><span data-stu-id="7765f-147">A log of events in the Background Sync pane</span></span>  
    > ![[バックグラウンド同期] ウィンドウのイベントのログ][SyncLog]  
    
1.  <span data-ttu-id="7765f-149">イベントをクリックすると、テーブルの下の領域に詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7765f-149">Click an event to view its details in the space below the table.</span></span>  
    
    > ##### <span data-ttu-id="7765f-150">図 7</span><span class="sxs-lookup"><span data-stu-id="7765f-150">Figure 7</span></span>  
    > <span data-ttu-id="7765f-151">[バックグラウンド同期] ウィンドウのイベントの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="7765f-151">Viewing the details of an event in the Background Sync pane</span></span>  
    > ![[バックグラウンド同期] ウィンドウのイベントの詳細を表示する][SyncDetails]  
    
## <span data-ttu-id="7765f-153">通知</span><span class="sxs-lookup"><span data-stu-id="7765f-153">Notifications</span></span> 

<span data-ttu-id="7765f-154">**サービスワーカー**がサーバーから[プッシュメッセージ][MDNPush]を受信した後、サービスワーカーは[通知 API][MDNNotifications]を使ってユーザーにデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="7765f-154">After a **service worker** has received a [Push Message][MDNPush] from a server, the service worker uses the [Notifications API][MDNNotifications] to display the data to a user.</span></span>  <span data-ttu-id="7765f-155">DevTools が開いていない場合でも、3日間の通知をログに記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7765f-155">To log Notifications for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="7765f-156">[DevTools を開き][OpenDevTools]ます。</span><span class="sxs-lookup"><span data-stu-id="7765f-156">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="7765f-157">**アプリケーション**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7765f-157">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="7765f-158">[**通知**] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="7765f-158">Open the **Notifications** pane.</span></span>  
    
    > ##### <span data-ttu-id="7765f-159">図 8</span><span class="sxs-lookup"><span data-stu-id="7765f-159">Figure 8</span></span>  
    > <span data-ttu-id="7765f-160">[通知] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7765f-160">The Notifications pane</span></span>  
    > ![[通知] ウィンドウ][NotificationsEmpty]  
    
1.  <span data-ttu-id="7765f-162">[**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="7765f-162">Click **Record** ![Record][ImageRecordIcon].</span></span>  
   <span data-ttu-id="7765f-163">一部の通知アクティビティをトリガーすると、DevTools によってイベントがテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="7765f-163">After triggering some Notifications activity, DevTools logs the events to the table.</span></span>  
    
    > ##### <span data-ttu-id="7765f-164">図 9</span><span class="sxs-lookup"><span data-stu-id="7765f-164">Figure 9</span></span>  
    > <span data-ttu-id="7765f-165">通知ウィンドウのイベントのログ</span><span class="sxs-lookup"><span data-stu-id="7765f-165">A log of events in the Notifications pane</span></span>  
    > ![通知ウィンドウのイベントのログ][NotificationsLog]  
    
1.  <span data-ttu-id="7765f-167">イベントをクリックすると、テーブルの下の領域に詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7765f-167">Click an event to view its details in the space below the table.</span></span>  
    
    > ##### <span data-ttu-id="7765f-168">図 10</span><span class="sxs-lookup"><span data-stu-id="7765f-168">Figure 10</span></span>  
    > <span data-ttu-id="7765f-169">[通知] ウィンドウのイベントの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="7765f-169">Viewing the details of an event in the Notifications pane</span></span>  
    > ![[通知] ウィンドウのイベントの詳細を表示する][NotificationsDetails]  
    
## <span data-ttu-id="7765f-171">メッセージをプッシュする</span><span class="sxs-lookup"><span data-stu-id="7765f-171">Push Messages</span></span> 

<span data-ttu-id="7765f-172">ユーザーにプッシュ通知を表示するには、**サービスワーカー**はまず、[プッシュメッセージ API][MDNPush]を使ってサーバーからデータを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7765f-172">To display a push notification to a user, a **service worker** must first use the [Push Message API][MDNPush] to receive data from a server.</span></span>  <span data-ttu-id="7765f-173">サービスワーカーが通知を表示する準備ができたら、[通知 API][MDNNotifications]を使います。</span><span class="sxs-lookup"><span data-stu-id="7765f-173">When the service worker is ready to display the notification, it uses the [Notifications API][MDNNotifications].</span></span>  <span data-ttu-id="7765f-174">DevTools が開いていない場合でも、3日間、プッシュメッセージをログに記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7765f-174">To log Push Messages for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="7765f-175">[DevTools を開き][OpenDevTools]ます。</span><span class="sxs-lookup"><span data-stu-id="7765f-175">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="7765f-176">**アプリケーション**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7765f-176">Open the **Application** panel.</span></span>  
1.  <span data-ttu-id="7765f-177">[**プッシュメッセージング**] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="7765f-177">Open the **Push Messaging** pane.</span></span>  
    
    > ##### <span data-ttu-id="7765f-178">図 11</span><span class="sxs-lookup"><span data-stu-id="7765f-178">Figure 11</span></span>  
    > <span data-ttu-id="7765f-179">[プッシュメッセージング] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7765f-179">The Push Messaging pane</span></span>  
    > ![[プッシュメッセージング] ウィンドウ][PushEmpty]  

1.  <span data-ttu-id="7765f-181">[**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="7765f-181">Click **Record** ![Record][ImageRecordIcon].</span></span>  
    <span data-ttu-id="7765f-182">一部のプッシュメッセージのアクティビティがトリガーされた後、DevTools ではイベントがテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="7765f-182">After triggering some Push Message activity, DevTools logs the events to the table.</span></span>  
    
    > ##### <span data-ttu-id="7765f-183">図 12</span><span class="sxs-lookup"><span data-stu-id="7765f-183">Figure 12</span></span>  
    > <span data-ttu-id="7765f-184">[プッシュメッセージング] ウィンドウのイベントのログ</span><span class="sxs-lookup"><span data-stu-id="7765f-184">A log of events in the Push Messaging pane</span></span>  
    > ![[プッシュメッセージング] ウィンドウのイベントのログ][PushLog]  

1.  <span data-ttu-id="7765f-186">イベントをクリックすると、テーブルの下の領域に詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7765f-186">Click an event to view its details in the space below the table.</span></span>  
    
    > ##### <span data-ttu-id="7765f-187">図 13</span><span class="sxs-lookup"><span data-stu-id="7765f-187">Figure 13</span></span>  
    > <span data-ttu-id="7765f-188">プッシュメッセージングウィンドウのイベントの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="7765f-188">Viewing the details of an event in the Push Messaging pane</span></span>  
    > ![プッシュメッセージングウィンドウのイベントの詳細の表示][PushDetails2]  
    
 



<!-- image links -->  

[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png  

[PushDetails]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-push-messaging.msft.png "図 1: プッシュメッセージウィンドウのイベントの詳細の表示"  
[FetchEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-fetch-empty.msft.png "図 2: [バックグラウンドでの取り出し] ウィンドウ"  
[FetchLog]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-fetch.msft.png "図 3: [バックグラウンドでの取り出し] ウィンドウに表示されたイベントのログ"  
[FetchDetails]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-fetch-details.msft.png "図 4: [バックグラウンドでの取得] ウィンドウに表示されたイベントの詳細の表示"  
[SyncEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-sync-empty.msft.png "図 5: [バックグラウンド同期] ウィンドウ"  
[SyncLog]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-sync.msft.png "図 6: [バックグラウンド同期] ウィンドウのイベントのログ"  
[SyncDetails]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-background-sync-details.msft.png "図 7: バックグラウンドの同期ウィンドウのイベントの詳細を表示する"  
[NotificationsEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-notifications-empty.msft.png "図 8: [通知] ウィンドウ"  
[NotificationsLog]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-notifications.msft.png "図 9: 通知ウィンドウのイベントのログ"  
[NotificationsDetails]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-notifications-details.msft.png "図 10: [通知] ウィンドウのイベントの詳細を表示する"  
[PushEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-push-messaging-empty.msft.png "図 11: [プッシュメッセージング] ウィンドウ"  
[PushLog]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-push-messaging.msft.png "図 12: プッシュメッセージングウィンドウのイベントのログ"  
[PushDetails2]: /microsoft-edge/devtools-guide-chromium/media/javascript-application-background-services-push-messaging-details.msft.png "図 13: プッシュメッセージングウィンドウのイベントの詳細の表示"  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open.md "Microsoft Edge (Chromium) 開発者ツールを開く"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "バックグラウンドプロセス-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="7765f-207">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7765f-207">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7765f-208">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="7765f-208">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  
[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7765f-210">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7765f-210">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
