---
description: Microsoft Edge DevTools を使用してバックグラウンド フェッチ、バックグラウンド同期、通知、およびプッシュ メッセージをデバッグする方法。
title: Microsoft Edge DevTools を使用したバックグラウンド サービスのデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 15023098c547d31bf46bd387f849b365c13b38f6
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439529"
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

# <a name="debug-background-services-with-microsoft-edge-devtools"></a>Microsoft Edge DevTools を使用したバックグラウンド サービスのデバッグ  

Microsoft **** Edge DevTools の Background Services セクションは、ユーザーが Web サイトを開いていない場合でも、Web サイトが更新プログラムを送受信できる JavaScript API 用のツールのコレクションです。  
バックグラウンド サービスは[バックグラウンド プロセス][WikiBackgroundProcess]と機能的に似ています。  
Microsoft Edge DevTools では、次の各 API がバックグラウンド サービスと見なされます。  

*   [バックグラウンド フェッチ](#background-fetch)  
*   [バックグラウンド同期](#background-sync)  
*   [通知](#notifications)  
*   [プッシュ メッセージ](#push-messages)  
    
Microsoft Edge DevTools は、DevTools が開いていない場合でも、バックグラウンド サービス イベントを 3 日間ログに記録できます。  
バックグラウンド サービス イベント ログは、イベントが期待通り送信および受信されるのを確認するのに役立ちます。  また、各イベントの詳細を確認できます。  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュ メッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   [**プッシュ メッセージング] ウィンドウ**  
:::image-end:::  

## <a name="background-fetch"></a>バックグラウンド フェッチ  

バックグラウンド フェッチ API******を使用**すると、サービス ワーカーはバックグラウンド サービスとして、映画やポッドキャストなどの大きなリソースを確実にダウンロードできます。  DevTools が開いていない場合でも、バックグラウンド フェッチ イベントを 3 日間記録するには、次の操作を行います。  

<!--Todo: add background fetch api section when available -->  

1.  [DevTools を開きます][OpenDevTools]。  
1.  アプリケーション ツール **を開** きます。  
1.  [バックグラウンド フェッチ **] パネルを開** きます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="[バックグラウンド フェッチ] パネル" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       [ **バックグラウンド フェッチ]** パネル  
    :::image-end:::  
    
1.  **[Record** \( Record ![ ](../media/record-icon.msft.png) \] を選択します)。  
   バックグラウンド フェッチ アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="バックグラウンド フェッチ パネルのイベントのログ" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       バックグラウンド フェッチ パネルの **イベントの** ログ  
    :::image-end:::  
    
1.  イベントを選択して、その詳細を表の下のスペースに表示します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="バックグラウンド フェッチ ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       バックグラウンド フェッチ ウィンドウでイベントの詳細 **を表示** する  
    :::image-end:::  
    
## <a name="background-sync"></a>バックグラウンド同期  

バックグラウンド**同期 API を使用**すると、信頼性の高いインターネット接続が再確立されると、オフライン サービス ワーカーはサーバーにデータを送信できます。 ****  DevTools が開いていない場合でも、バックグラウンド同期イベントを 3 日間記録するには、次のコマンドを実行します。  

<!--Todo: add background sync api section when available -->  

1.  [DevTools を開きます][OpenDevTools]。  
1.  アプリケーション ツール **を開** きます。  
1.  [バックグラウンド **同期] ウィンドウを開** きます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text="[バックグラウンド同期] ウィンドウ" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       [ **バックグラウンド同期]** ウィンドウ  
    :::image-end:::  
    
1.  **[Record** \( Record ![ ](../media/record-icon.msft.png) \] を選択します)。  
   バックグラウンド同期アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="[バックグラウンド同期] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       [バックグラウンド同期] ウィンドウの **イベントの** ログ  
    :::image-end:::  
    
1.  イベントを選択して、その詳細を表の下のスペースに表示します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="[バックグラウンド同期] ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       [バックグラウンド同期] ウィンドウでイベントの **詳細を表示** する  
    :::image-end:::  
    
## <a name="notifications"></a>通知  

サービス ワーカー**がサーバーから**プッシュ[][MDNPush]メッセージを受信した後、サービス ワーカーは[通知 API][MDNNotifications]を使用してデータをユーザーに表示します。  DevTools が開いていない場合でも、通知を 3 日間記録するには、次のコマンドを実行します。  

1.  [DevTools を開きます][OpenDevTools]。  
1.  アプリケーション ツール **を開** きます。  
1.  [通知] **ウィンドウを開** きます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="[通知] ウィンドウ" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       [ **通知]** ウィンドウ  
    :::image-end:::  
    
1.  **[Record** \( Record ![ ](../media/record-icon.msft.png) \] を選択します)。  
   通知アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="[通知] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       [通知] ウィンドウのイベント **の** ログ  
    :::image-end:::  
    
1.  イベントを選択して、その詳細を表の下のスペースに表示します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="[通知] ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       [通知] ウィンドウでイベントの詳細を **表示** する  
    :::image-end:::  
    
## <a name="push-messages"></a>プッシュ メッセージ  

ユーザーにプッシュ通知を表示するには、サービス**** ワーカーが最初にプッシュ メッセージ[API][MDNPush]を使用してサーバーからデータを受信する必要があります。  サービス ワーカーが通知を表示する準備ができたら、通知 API を [使用します][MDNNotifications]。  DevTools が開かなくても、プッシュ メッセージを 3 日間記録するには、次のコマンドを実行します。  

1.  [DevTools を開きます][OpenDevTools]。  
1.  アプリケーション ツール **を開** きます。  
1.  [プッシュ **メッセージング] パネルを開** きます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="[プッシュ メッセージング] ウィンドウを開く" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       [プッシュ **メッセージング] ウィンドウを開** く  
    :::image-end:::  
    
1.  **[Record** \( Record ![ ](../media/record-icon.msft.png) \] を選択します)。  
    一部のプッシュ メッセージ アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュ メッセージング] ウィンドウのイベントのログ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       [プッシュ メッセージング] ウィンドウ **のイベントの** ログ  
    :::image-end:::  
    
1.  表の下のスペースに詳細を表示するイベントを選択します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="[プッシュ メッセージング] ウィンドウでイベントの詳細を表示する" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       [プッシュ メッセージング] ウィンドウでイベントの **詳細を表示** する  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open/index.md "Open Microsoft Edge (Chromium) Developer Tools |Microsoft Docs"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "バックグラウンド プロセス - Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  
[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
