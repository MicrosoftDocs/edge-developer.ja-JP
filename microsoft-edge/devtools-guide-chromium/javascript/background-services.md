---
description: バックグラウンド フェッチ、バックグラウンド同期、通知、およびプッシュ メッセージを DevTools でデバッグMicrosoft Edge方法。
title: DevTools を使用してバックグラウンド Microsoft Edgeをデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4f5f52bcde976cea8432e3160a792438e5603e21
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564197"
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
# <a name="debug-background-services-with-microsoft-edge-devtools"></a><span data-ttu-id="29066-104">DevTools を使用してバックグラウンド Microsoft Edgeをデバッグする</span><span class="sxs-lookup"><span data-stu-id="29066-104">Debug Background Services with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="29066-105">Microsoft Edge \*\*\*\* DevTools の Background Services セクションは、ユーザーが Web サイトを開いていない場合でも、Web サイトが更新プログラムを送受信できる JavaScript API 用のツールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="29066-105">The **Background Services** section of Microsoft Edge DevTools is a collection of tools for the JavaScript APIs that enables your website to send and receive updates even when a user does not have your website open.</span></span>  
<span data-ttu-id="29066-106">バックグラウンド サービスは[バックグラウンド プロセス][WikiBackgroundProcess]と機能的に似ています。</span><span class="sxs-lookup"><span data-stu-id="29066-106">A background service is functionally similar to a [background process][WikiBackgroundProcess].</span></span>  
<span data-ttu-id="29066-107">Microsoft EdgeDevTools は、次の各 API をバックグラウンド サービスと見なします。</span><span class="sxs-lookup"><span data-stu-id="29066-107">Microsoft Edge DevTools considers each of the following APIs to be a background service:</span></span>  

*   [<span data-ttu-id="29066-108">バックグラウンド フェッチ</span><span class="sxs-lookup"><span data-stu-id="29066-108">Background Fetch</span></span>](#background-fetch)  
*   [<span data-ttu-id="29066-109">バックグラウンド同期</span><span class="sxs-lookup"><span data-stu-id="29066-109">Background Sync</span></span>](#background-sync)  
*   [<span data-ttu-id="29066-110">通知</span><span class="sxs-lookup"><span data-stu-id="29066-110">Notifications</span></span>](#notifications)  
*   [<span data-ttu-id="29066-111">プッシュ メッセージ</span><span class="sxs-lookup"><span data-stu-id="29066-111">Push Messages</span></span>](#push-messages)  
    
<span data-ttu-id="29066-112">Microsoft EdgeDevTools は、DevTools が開かなくても、バックグラウンド サービス イベントを 3 日間ログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="29066-112">Microsoft Edge DevTools may log background service events for 3 days, even when DevTools is not open.</span></span>  
<span data-ttu-id="29066-113">バックグラウンド サービス イベント ログは、イベントが期待通り送信および受信されるのを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="29066-113">The background service events log may help you make sure that events are being sent and received as expected.</span></span>  <span data-ttu-id="29066-114">また、各イベントの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="29066-114">You may also inspect the details of each event.</span></span>  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュ メッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   <span data-ttu-id="29066-116">[**プッシュ メッセージング] ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="29066-116">The **Push Messaging** pane</span></span>  
:::image-end:::  

## <a name="background-fetch"></a><span data-ttu-id="29066-117">バックグラウンド フェッチ</span><span class="sxs-lookup"><span data-stu-id="29066-117">Background Fetch</span></span>  

<span data-ttu-id="29066-118">バックグラウンド フェッチ API\*\*\*\*\*\*を使用\*\*すると、サービス ワーカーはバックグラウンド サービスとして、映画やポッドキャストなどの大きなリソースを確実にダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="29066-118">The **Background Fetch API** enables a **service worker** to reliably download large resources, like movies or podcasts, as a background service.</span></span>  <span data-ttu-id="29066-119">DevTools が開いていない場合でも、バックグラウンド フェッチ イベントを 3 日間記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="29066-119">To log Background Fetch event for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background fetch api section when available -->  

1.  <span data-ttu-id="29066-120">[DevTools を開きます][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="29066-120">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="29066-121">アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="29066-121">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="29066-122">[バックグラウンド フェッチ **] パネルを開** きます。</span><span class="sxs-lookup"><span data-stu-id="29066-122">Open the **Background Fetch** panel.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="[バックグラウンド フェッチ] パネル" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       <span data-ttu-id="29066-124">[ **バックグラウンド フェッチ]** パネル</span><span class="sxs-lookup"><span data-stu-id="29066-124">The **Background Fetch** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="29066-125">**[Record** \( Record ![ ](../media/record-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="29066-125">Choose **Record** \(![Record](../media/record-icon.msft.png)\).</span></span>  
   <span data-ttu-id="29066-126">バックグラウンド フェッチ アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="29066-126">After triggering some Background Fetch activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="バックグラウンド フェッチ パネルのイベントのログ" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       <span data-ttu-id="29066-128">バックグラウンド フェッチ パネルの **イベントの** ログ</span><span class="sxs-lookup"><span data-stu-id="29066-128">A log of events in the **Background Fetch** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="29066-129">イベントを選択して、その詳細を表の下のスペースに表示します。</span><span class="sxs-lookup"><span data-stu-id="29066-129">Choose an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="バックグラウンド フェッチ ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       <span data-ttu-id="29066-131">バックグラウンド フェッチ ウィンドウでイベントの詳細 **を表示** する</span><span class="sxs-lookup"><span data-stu-id="29066-131">View the details of an event in the **Background Fetch** pane</span></span>  
    :::image-end:::  
    
## <a name="background-sync"></a><span data-ttu-id="29066-132">バックグラウンド同期</span><span class="sxs-lookup"><span data-stu-id="29066-132">Background Sync</span></span>  

<span data-ttu-id="29066-133">バックグラウンド**同期 API を使用**すると、信頼性の高いインターネット接続が再確立されると、オフライン サービス ワーカーはサーバーにデータを送信できます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="29066-133">The **Background Sync API** enables an offline **service worker** to send data to a server once it has re-established a reliable internet connection.</span></span>  <span data-ttu-id="29066-134">DevTools が開いていない場合でも、バックグラウンド同期イベントを 3 日間記録するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="29066-134">To log Background Sync events for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background sync api section when available -->  

1.  <span data-ttu-id="29066-135">[DevTools を開きます][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="29066-135">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="29066-136">アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="29066-136">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="29066-137">[バックグラウンド **同期] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="29066-137">Open the **Background Sync** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text="[バックグラウンド同期] ウィンドウ" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       <span data-ttu-id="29066-139">[ **バックグラウンド同期]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="29066-139">The **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="29066-140">**[Record** \( Record ![ ](../media/record-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="29066-140">Choose **Record** \(![Record](../media/record-icon.msft.png)\).</span></span>  
   <span data-ttu-id="29066-141">バックグラウンド同期アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="29066-141">After triggering some Background Sync activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="[バックグラウンド同期] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       <span data-ttu-id="29066-143">[バックグラウンド同期] ウィンドウの **イベントの** ログ</span><span class="sxs-lookup"><span data-stu-id="29066-143">A log of events in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="29066-144">イベントを選択して、その詳細を表の下のスペースに表示します。</span><span class="sxs-lookup"><span data-stu-id="29066-144">Choose an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="[バックグラウンド同期] ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       <span data-ttu-id="29066-146">[バックグラウンド同期] ウィンドウでイベントの **詳細を表示** する</span><span class="sxs-lookup"><span data-stu-id="29066-146">View the details of an event in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
## <a name="notifications"></a><span data-ttu-id="29066-147">通知</span><span class="sxs-lookup"><span data-stu-id="29066-147">Notifications</span></span>  

<span data-ttu-id="29066-148">サービス ワーカー**がサーバーから**プッシュ[][MDNPush]メッセージを受信した後、サービス ワーカーは[通知 API][MDNNotifications]を使用してデータをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="29066-148">After a **service worker** has received a [Push Message][MDNPush] from a server, the service worker uses the [Notifications API][MDNNotifications] to display the data to a user.</span></span>  <span data-ttu-id="29066-149">DevTools が開いていない場合でも、通知を 3 日間記録するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="29066-149">To log Notifications for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="29066-150">[DevTools を開きます][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="29066-150">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="29066-151">アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="29066-151">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="29066-152">[通知] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="29066-152">Open the **Notifications** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="[通知] ウィンドウ" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       <span data-ttu-id="29066-154">[ **通知]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="29066-154">The **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="29066-155">**[Record** \( Record ![ ](../media/record-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="29066-155">Choose **Record** \(![Record](../media/record-icon.msft.png)\).</span></span>  
   <span data-ttu-id="29066-156">通知アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="29066-156">After triggering some Notifications activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="[通知] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       <span data-ttu-id="29066-158">[通知] ウィンドウのイベント **の** ログ</span><span class="sxs-lookup"><span data-stu-id="29066-158">A log of events in the **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="29066-159">イベントを選択して、その詳細を表の下のスペースに表示します。</span><span class="sxs-lookup"><span data-stu-id="29066-159">Choose an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="[通知] ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       <span data-ttu-id="29066-161">[通知] ウィンドウでイベントの詳細を **表示** する</span><span class="sxs-lookup"><span data-stu-id="29066-161">View the details of an event in the **Notifications** pane</span></span>  
    :::image-end:::  
    
## <a name="push-messages"></a><span data-ttu-id="29066-162">プッシュ メッセージ</span><span class="sxs-lookup"><span data-stu-id="29066-162">Push Messages</span></span>  

<span data-ttu-id="29066-163">ユーザーにプッシュ通知を表示するには、サービス\*\*\*\* ワーカーが最初にプッシュ メッセージ[API][MDNPush]を使用してサーバーからデータを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29066-163">To display a push notification to a user, a **service worker** must first use the [Push Message API][MDNPush] to receive data from a server.</span></span>  <span data-ttu-id="29066-164">サービス ワーカーが通知を表示する準備ができたら、通知 API を [使用します][MDNNotifications]。</span><span class="sxs-lookup"><span data-stu-id="29066-164">When the service worker is ready to display the notification, it uses the [Notifications API][MDNNotifications].</span></span>  <span data-ttu-id="29066-165">DevTools が開かなくても、プッシュ メッセージを 3 日間記録するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="29066-165">To log Push Messages for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="29066-166">[DevTools を開きます][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="29066-166">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="29066-167">アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="29066-167">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="29066-168">[プッシュ **メッセージング] パネルを開** きます。</span><span class="sxs-lookup"><span data-stu-id="29066-168">Open the **Push Messaging** panel.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="[プッシュ メッセージング] ウィンドウを開く" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       <span data-ttu-id="29066-170">[プッシュ **メッセージング] ウィンドウを開** く</span><span class="sxs-lookup"><span data-stu-id="29066-170">Open the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="29066-171">**[Record** \( Record ![ ](../media/record-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="29066-171">Choose **Record** \(![Record](../media/record-icon.msft.png)\).</span></span>  
    <span data-ttu-id="29066-172">一部のプッシュ メッセージ アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="29066-172">After triggering some Push Message activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュ メッセージング] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       <span data-ttu-id="29066-174">[プッシュ メッセージング] ウィンドウ **のイベントの** ログ</span><span class="sxs-lookup"><span data-stu-id="29066-174">A log of events in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="29066-175">表の下のスペースに詳細を表示するイベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="29066-175">Choose an event to view the details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="[プッシュ メッセージング] ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       <span data-ttu-id="29066-177">[プッシュ メッセージング] ウィンドウでイベントの **詳細を表示** する</span><span class="sxs-lookup"><span data-stu-id="29066-177">View the details of an event in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="29066-178">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="29066-178">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open/index.md "開発者Microsoft Edge (Chromium) 開発者向けツール を開|Microsoft Docs"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "バックグラウンド プロセス - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="29066-183">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="29066-183">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="29066-184">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="29066-184">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  
[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="29066-186">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="29066-186">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
