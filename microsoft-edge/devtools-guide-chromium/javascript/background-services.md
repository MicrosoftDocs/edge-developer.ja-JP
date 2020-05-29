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





# Microsoft Edge DevTools によるバックグラウンドサービスのデバッグ   



Microsoft Edge DevTools の [**バックグラウンドサービス**] セクションは、ユーザーが web サイトを開いていない場合でも web サイトが更新を送受信できるようにする JavaScript api 用のツールのコレクションです。  
バックグラウンドサービスは、機能的には [バックグラウンドプロセス] [WikiBackgroundProcess] と似ています。  
Microsoft Edge DevTools は、次の各 Api をバックグラウンドサービスと見なします。  

*   [バックグラウンドでの取得](#background-fetch)  
*   [バックグラウンド同期](#background-sync)  
*   [通知](#notifications)  
*   [メッセージをプッシュする](#push-messages)  

Microsoft Edge DevTools では、DevTools が開いていない場合でも、3日間はバックグラウンドサービスイベントをログに記録できます。  
これは、イベントが予期したとおりに送受信されるようにするのに役立ちます。  各イベントの詳細も調べることができます。  

> ##### 図 1  
> プッシュメッセージングウィンドウのイベントの詳細の表示  
> ![プッシュメッセージングウィンドウのイベントの詳細の表示][PushDetails]  

## バックグラウンドでの取得   

*バックグラウンドフェッチ API** を使用すると、**サービスワーカー**は、ムービーやポッドキャストなどの大規模なリソースを、バックグラウンドサービスとして確実にダウンロードできます。  DevTools が開いていない場合でも、3日間のバックグラウンドの取り出しイベントをログに記録するには、次の操作を行います。  

<!--Todo: add background fetch api section when available -->  

1.  [DevTools を開き][OpenDevTools]ます。  
1.  **アプリケーション**パネルを開きます。  
1.  [バックグラウンドでの**取得**] ウィンドウを開く。  
    
    > ##### 図 2  
    > [バックグラウンドでの取り出し] ウィンドウ  
    > ![[バックグラウンドでの取り出し] ウィンドウ][FetchEmpty]  
    
1.  [**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。  
   一部のバックグラウンドフェッチアクティビティがトリガーされると、DevTools によってイベントがテーブルに記録されます。  
    
    > ##### 図 3  
    > [バックグラウンドでの取得] ウィンドウのイベントのログ  
    > ![[バックグラウンドでの取得] ウィンドウのイベントのログ][FetchLog]  
    
1.  イベントをクリックすると、テーブルの下の領域に詳細が表示されます。  
    
    > ##### 図 4  
    > [バックグラウンドでの取得] ウィンドウのイベントの詳細の表示  
    > ![[バックグラウンドでの取得] ウィンドウのイベントの詳細の表示][FetchDetails]  

## バックグラウンド同期   

**バックグラウンド同期 API**では、信頼性の高いインターネット接続を再確立した後、オフライン**サービスワーカー**がサーバーにデータを送信できるようにします。  DevTools が開いていない場合でも、3日間のバックグラウンド同期イベントをログに記録するには、次の操作を行います。  

<!--Todo: add background sync api section when available -->  

1.  [DevTools を開き][OpenDevTools]ます。  
1.  **アプリケーション**パネルを開きます。  
1.  [**バックグラウンドの同期**] ウィンドウを開く。  
    
    > ##### 図 5  
    > [バックグラウンドの同期] ウィンドウ  
    > ![[バックグラウンドの同期] ウィンドウ][SyncEmpty]  
    
1.  [**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。  
   一部のバックグラウンド同期アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。  
    
    > ##### 図 6  
    > [バックグラウンド同期] ウィンドウのイベントのログ  
    > ![[バックグラウンド同期] ウィンドウのイベントのログ][SyncLog]  
    
1.  イベントをクリックすると、テーブルの下の領域に詳細が表示されます。  
    
    > ##### 図 7  
    > [バックグラウンド同期] ウィンドウのイベントの詳細を表示する  
    > ![[バックグラウンド同期] ウィンドウのイベントの詳細を表示する][SyncDetails]  
    
## 通知 

**サービスワーカー**がサーバーから[プッシュメッセージ][MDNPush]を受信した後、サービスワーカーは[通知 API][MDNNotifications]を使ってユーザーにデータを表示します。  DevTools が開いていない場合でも、3日間の通知をログに記録するには、次の操作を行います。  

1.  [DevTools を開き][OpenDevTools]ます。  
1.  **アプリケーション**パネルを開きます。  
1.  [**通知**] ウィンドウを開く。  
    
    > ##### 図 8  
    > [通知] ウィンドウ  
    > ![[通知] ウィンドウ][NotificationsEmpty]  
    
1.  [**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。  
   一部の通知アクティビティをトリガーすると、DevTools によってイベントがテーブルに記録されます。  
    
    > ##### 図 9  
    > 通知ウィンドウのイベントのログ  
    > ![通知ウィンドウのイベントのログ][NotificationsLog]  
    
1.  イベントをクリックすると、テーブルの下の領域に詳細が表示されます。  
    
    > ##### 図 10  
    > [通知] ウィンドウのイベントの詳細を表示する  
    > ![[通知] ウィンドウのイベントの詳細を表示する][NotificationsDetails]  
    
## メッセージをプッシュする 

ユーザーにプッシュ通知を表示するには、**サービスワーカー**はまず、[プッシュメッセージ API][MDNPush]を使ってサーバーからデータを受信する必要があります。  サービスワーカーが通知を表示する準備ができたら、[通知 API][MDNNotifications]を使います。  DevTools が開いていない場合でも、3日間、プッシュメッセージをログに記録するには、次の操作を行います。  

1.  [DevTools を開き][OpenDevTools]ます。  
1.  **アプリケーション**パネルを開きます。  
1.  [**プッシュメッセージング**] ウィンドウを開きます。  
    
    > ##### 図 11  
    > [プッシュメッセージング] ウィンドウ  
    > ![[プッシュメッセージング] ウィンドウ][PushEmpty]  

1.  [**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。  
    一部のプッシュメッセージのアクティビティがトリガーされた後、DevTools ではイベントがテーブルに記録されます。  
    
    > ##### 図 12  
    > [プッシュメッセージング] ウィンドウのイベントのログ  
    > ![[プッシュメッセージング] ウィンドウのイベントのログ][PushLog]  

1.  イベントをクリックすると、テーブルの下の領域に詳細が表示されます。  
    
    > ##### 図 13  
    > プッシュメッセージングウィンドウのイベントの詳細の表示  
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
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  
[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
