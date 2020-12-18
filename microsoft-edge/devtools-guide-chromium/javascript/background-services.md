---
description: Microsoft Edge DevTools を使ってバックグラウンド フェッチ、バックグラウンド同期、通知、プッシュ メッセージをデバッグする方法について説明します。
title: Microsoft Edge DevTools を使用してバックグラウンド サービスをデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: df832ed2f56faf6412fd42bc080d8af7705d26d3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230678"
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

# <span data-ttu-id="335c7-104">Microsoft Edge DevTools を使ったバックグラウンド サービスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="335c7-104">Debug Background Services With Microsoft Edge DevTools</span></span>  

<span data-ttu-id="335c7-105">Microsoft Edge DevTools の Background **Services** セクションは、ユーザーが Web サイトを開いていない場合でも、Web サイトで更新プログラムを送受信できる JavaScript API 用のツールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="335c7-105">The **Background Services** section of Microsoft Edge DevTools is a collection of tools for the JavaScript APIs that enables your website to send and receive updates even when a user does not have your website open.</span></span>  
<span data-ttu-id="335c7-106">バックグラウンド サービスは、機能的には [バックグラウンド プロセス][WikiBackgroundProcess] に似ています。</span><span class="sxs-lookup"><span data-stu-id="335c7-106">A background service is functionally similar to a [background process][WikiBackgroundProcess].</span></span>  
<span data-ttu-id="335c7-107">Microsoft Edge DevTools では、次の各 API をバックグラウンド サービスと見なします。</span><span class="sxs-lookup"><span data-stu-id="335c7-107">Microsoft Edge DevTools considers each of the following APIs to be a background service:</span></span>  

*   [<span data-ttu-id="335c7-108">バックグラウンド フェッチ</span><span class="sxs-lookup"><span data-stu-id="335c7-108">Background Fetch</span></span>](#background-fetch)  
*   [<span data-ttu-id="335c7-109">バックグラウンド同期</span><span class="sxs-lookup"><span data-stu-id="335c7-109">Background Sync</span></span>](#background-sync)  
*   [<span data-ttu-id="335c7-110">通知</span><span class="sxs-lookup"><span data-stu-id="335c7-110">Notifications</span></span>](#notifications)  
*   [<span data-ttu-id="335c7-111">プッシュ メッセージ</span><span class="sxs-lookup"><span data-stu-id="335c7-111">Push Messages</span></span>](#push-messages)  
    
<span data-ttu-id="335c7-112">Microsoft Edge DevTools は、DevTools が開いていない場合でも、バックグラウンド サービス イベントを 3 日間ログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="335c7-112">Microsoft Edge DevTools can log background service events for 3 days, even when DevTools is not open.</span></span>  
<span data-ttu-id="335c7-113">これにより、イベントが期待した通り送信および受信されるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="335c7-113">This can help you make sure that events are being sent and received as expected.</span></span>  <span data-ttu-id="335c7-114">また、各イベントの詳細を検査できます。</span><span class="sxs-lookup"><span data-stu-id="335c7-114">You may also inspect the details of each event.</span></span>  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュ メッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   <span data-ttu-id="335c7-116">[ **プッシュ メッセージング]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="335c7-116">The **Push Messaging** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="335c7-117">バックグラウンド フェッチ</span><span class="sxs-lookup"><span data-stu-id="335c7-117">Background Fetch</span></span>  

<span data-ttu-id="335c7-118">バックグラウンド フェッチ API\*\*\*\*\*\*を使用\*\*すると、サービス ワーカーは、映画やポッドキャストなどの大きなリソースをバックグラウンド サービスとして確実にダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="335c7-118">The **Background Fetch API** enables a **service worker** to reliably download large resources, like movies or podcasts, as a background service.</span></span>  <span data-ttu-id="335c7-119">DevTools が開いていない場合でも、Background Fetch イベントを 3 日間記録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="335c7-119">To log Background Fetch event for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background fetch api section when available -->  

1.  <span data-ttu-id="335c7-120">[DevTools を開きます][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="335c7-120">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="335c7-121">アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="335c7-121">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="335c7-122">バックグラウンド フェッチ **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="335c7-122">Open the **Background Fetch** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="バックグラウンド フェッチ ウィンドウ" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       <span data-ttu-id="335c7-124">バックグラウンド **フェッチ** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="335c7-124">The **Background Fetch** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="335c7-125">Choose **Record** \( ![ Record ][ImageRecordIcon] \).</span><span class="sxs-lookup"><span data-stu-id="335c7-125">Choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="335c7-126">バックグラウンド フェッチ アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="335c7-126">After triggering some Background Fetch activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="バックグラウンド フェッチ ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       <span data-ttu-id="335c7-128">バックグラウンド フェッチ ウィンドウのイベント **の** ログ</span><span class="sxs-lookup"><span data-stu-id="335c7-128">A log of events in the **Background Fetch** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="335c7-129">イベントをクリックすると、テーブルの下のスペースにイベントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="335c7-129">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="バックグラウンド フェッチ ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       <span data-ttu-id="335c7-131">バックグラウンド フェッチ ウィンドウでイベントの詳細 **を表示** する</span><span class="sxs-lookup"><span data-stu-id="335c7-131">View the details of an event in the **Background Fetch** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="335c7-132">バックグラウンド同期</span><span class="sxs-lookup"><span data-stu-id="335c7-132">Background Sync</span></span>  

<span data-ttu-id="335c7-133">バックグラウンド **同期 API を使用** すると **、オフライン** サービス ワーカーは、信頼できるインターネット接続を再確立したサーバーにデータを送信できます。</span><span class="sxs-lookup"><span data-stu-id="335c7-133">The **Background Sync API** enables an offline **service worker** to send data to a server once it has re-established a reliable internet connection.</span></span>  <span data-ttu-id="335c7-134">DevTools が開いていない場合でも、バックグラウンド同期イベントを 3 日間記録するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="335c7-134">To log Background Sync events for 3 days, even when DevTools is not open:</span></span>  

<!--Todo: add background sync api section when available -->  

1.  <span data-ttu-id="335c7-135">[DevTools を開きます][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="335c7-135">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="335c7-136">アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="335c7-136">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="335c7-137">バックグラウンド同期 **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="335c7-137">Open the **Background Sync** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text="[バックグラウンド同期] ウィンドウ" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       <span data-ttu-id="335c7-139">[ **バックグラウンド同期]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="335c7-139">The **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="335c7-140">Choose **Record** \( ![ Record ][ImageRecordIcon] \).</span><span class="sxs-lookup"><span data-stu-id="335c7-140">Choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="335c7-141">バックグラウンド同期アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="335c7-141">After triggering some Background Sync activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="バックグラウンド同期ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       <span data-ttu-id="335c7-143">バックグラウンド同期ウィンドウの **イベントの** ログ</span><span class="sxs-lookup"><span data-stu-id="335c7-143">A log of events in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="335c7-144">イベントをクリックすると、テーブルの下のスペースにイベントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="335c7-144">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="バックグラウンド同期ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       <span data-ttu-id="335c7-146">バックグラウンド同期ウィンドウでイベントの詳細 **を表示** する</span><span class="sxs-lookup"><span data-stu-id="335c7-146">View the details of an event in the **Background Sync** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="335c7-147">通知</span><span class="sxs-lookup"><span data-stu-id="335c7-147">Notifications</span></span>  

<span data-ttu-id="335c7-148">サービス ワーカー **がサーバー** から [プッシュ][MDNPush] メッセージを受信すると、サービス ワーカーは [Notifications API][MDNNotifications] を使用してデータをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="335c7-148">After a **service worker** has received a [Push Message][MDNPush] from a server, the service worker uses the [Notifications API][MDNNotifications] to display the data to a user.</span></span>  <span data-ttu-id="335c7-149">DevTools が開いていない場合でも、通知を 3 日間記録するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="335c7-149">To log Notifications for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="335c7-150">[DevTools を開きます][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="335c7-150">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="335c7-151">アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="335c7-151">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="335c7-152">通知ウィンドウ **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="335c7-152">Open the **Notifications** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="[通知] ウィンドウ" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       <span data-ttu-id="335c7-154">[ **通知]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="335c7-154">The **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="335c7-155">Choose **Record** \( ![ Record ][ImageRecordIcon] \).</span><span class="sxs-lookup"><span data-stu-id="335c7-155">Choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  
   <span data-ttu-id="335c7-156">通知アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。</span><span class="sxs-lookup"><span data-stu-id="335c7-156">After triggering some Notifications activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="通知ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       <span data-ttu-id="335c7-158">通知ウィンドウのイベント **の** ログ</span><span class="sxs-lookup"><span data-stu-id="335c7-158">A log of events in the **Notifications** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="335c7-159">イベントをクリックすると、テーブルの下のスペースにイベントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="335c7-159">Click an event to view its details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="[通知] ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       <span data-ttu-id="335c7-161">[通知] ウィンドウでイベントの詳細を **表示** する</span><span class="sxs-lookup"><span data-stu-id="335c7-161">View the details of an event in the **Notifications** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="335c7-162">プッシュ メッセージ</span><span class="sxs-lookup"><span data-stu-id="335c7-162">Push Messages</span></span>  

<span data-ttu-id="335c7-163">ユーザーにプッシュ通知を表示するには、サービス\*\*\*\* ワーカーはまず、プッシュ メッセージ[API][MDNPush]を使用してサーバーからデータを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="335c7-163">To display a push notification to a user, a **service worker** must first use the [Push Message API][MDNPush] to receive data from a server.</span></span>  <span data-ttu-id="335c7-164">サービス ワーカーは、通知を表示する準備ができたら、Notifications [API を使用します][MDNNotifications]。</span><span class="sxs-lookup"><span data-stu-id="335c7-164">When the service worker is ready to display the notification, it uses the [Notifications API][MDNNotifications].</span></span>  <span data-ttu-id="335c7-165">DevTools が開いていない場合でも、プッシュ メッセージを 3 日間記録するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="335c7-165">To log Push Messages for 3 days, even when DevTools is not open:</span></span>  

1.  <span data-ttu-id="335c7-166">[DevTools を開きます][OpenDevTools]。</span><span class="sxs-lookup"><span data-stu-id="335c7-166">[Open DevTools][OpenDevTools].</span></span>  
1.  <span data-ttu-id="335c7-167">アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="335c7-167">Open the **Application** tool.</span></span>  
1.  <span data-ttu-id="335c7-168">[プッシュ メッセージング **] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="335c7-168">Open the **Push Messaging** pane.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="[プッシュ メッセージング] ウィンドウを開く" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       <span data-ttu-id="335c7-170">[プッシュ メッセージング **] ウィンドウを開** く</span><span class="sxs-lookup"><span data-stu-id="335c7-170">Open the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="335c7-171">Choose **Record** \( ![ Record ][ImageRecordIcon] \).</span><span class="sxs-lookup"><span data-stu-id="335c7-171">Choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  
    <span data-ttu-id="335c7-172">プッシュ メッセージ アクティビティをトリガーした後、DevTools はテーブルにイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="335c7-172">After triggering some Push Message activity, DevTools logs the events to the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュ メッセージング] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       <span data-ttu-id="335c7-174">[プッシュ メッセージング] ウィンドウ **のイベントの** ログ</span><span class="sxs-lookup"><span data-stu-id="335c7-174">A log of events in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="335c7-175">イベントをクリックすると、表の下のスペースに詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="335c7-175">Click an event to view the details in the space below the table.</span></span>  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="[プッシュ メッセージング] ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       <span data-ttu-id="335c7-177">[プッシュ メッセージング] ウィンドウでイベントの **詳細を表示** する</span><span class="sxs-lookup"><span data-stu-id="335c7-177">View the details of an event in the **Push Messaging** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="335c7-178">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="335c7-178">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRecordIcon]: ../media/record-icon.msft.png  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open/index.md "Microsoft Edge (Chromium) 開発者ツールを開く |Microsoft Docs"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "バックグラウンド プロセス - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="335c7-183">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="335c7-183">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="335c7-184">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="335c7-184">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  
[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="335c7-186">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="335c7-186">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
