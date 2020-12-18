---
description: このガイドでは、Windows で段階的な Web アプリ (Chromium) を構築するための PWA の基本とツールの概要について説明します。
title: プログレッシブ Web アプリ (Chromium) の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 段階的な Web アプリ, PWA, Edge, Windows, PWABuilder, Web マニフェスト, サービス ワーカー, プッシュ
ms.openlocfilehash: 7ad13f98f54c52891681d7591b21503c9d5825ff
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231224"
---
# プログレッシブ Web アプリ (Chromium) の使用を開始する  

段階的な Web アプリ \(PWAs\) は、徐々に [拡張された Web アプリです][WikiProgressiveEnhancement]。  段階的な機能強化には、インストール、オフライン サポート、プッシュ通知など、アプリのような機能が含まれます。  PWA をアプリ ストア用にパッケージ化することもできます。  可能なアプリ ストアには、Microsoft Store、Google Play、Mac App Store などです。  Microsoft Store は、Windows 10 に組み込みの商用アプリ ストアです。  

次のガイドでは、簡単な Web アプリを作成し、PWA として拡張することで、PWA の基本の概要を説明します。  完成したプロジェクトは、最新のブラウザー間で動作します。  

> [!TIP]
> [PWABuilder を使用して][PwaBuilder]、新しい PWA を作成したり、既存の PWA を拡張したり、アプリ ストア用に PWA をパッケージ化することができます。  

## 前提条件  

*   コード [Visual Studio使用][VisualstudioCodeMain] して、PWA ソース コードを編集します。  
*   ローカル [Node.js][NodejsMain] Web サーバーとして使用します。  
    
## 基本的な Web アプリを作成する  

空の Web アプリを作成するには [、「Node Express App Generator」][ExpressjsApplicationGenerator]の手順に従って、アプリに名前を付します `MySamplePwa` 。  

プロンプトで、次のコマンドを実行します。  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

コマンドは空の Web アプリを作成し、依存関係をインストールします。  

これで、シンプルで機能的な Web アプリが作成されます。  Web アプリを起動するには、次のコマンドを実行します。  

```shell
npm start
```  

次に、新 `http://localhost:3000` しい Web アプリを参照して表示します。  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="localhost での新しい PWA の実行" lightbox="./media/vs-nodejs-express-index.png":::
   localhost での新しい PWA の実行
:::image-end:::

## PWA の構築を開始する  

簡単な Web アプリが作成されたので、PWA として PWA として拡張するには、PWA の 3 つの要件を追加します。<!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]-->: [HTTPS、Web](#step-1---use-https)[アプリ マニフェスト、](#step-2---create-a-web-app-manifest)および[サービス ワーカー](#step-3---add-a-service-worker)。  

### 手順 1 - HTTPS を使用する  

サービス ワーカーなど、PWA プラットフォームの主要な部分 [では][MDNServiceWorkerApi]HTTPS を使用する必要があります。  PWA が有効な場合は、HTTPS URL に発行する必要があります。  

デバッグの目的で、Microsoft Edge は PWA API の `http://localhost` 使用も許可します。  

[Web アプリをライブ サイトとして発行しますが][VisualStudioNodejsTutorialPublishAzureAppService]、サーバーが HTTPS 用に構成されていることを確認します。  たとえば、Azure 無料アカウント [を作成できます][AzureCreateFreeAccount]。  Microsoft Azure App Service で [サイトをホスト][AzureWebApps] すると、既定で HTTPS 経由で提供されます。  

次のガイドでは `http://localhost` 、PWA の構築に使用します。  

### 手順 2 - Web アプリ マニフェストを作成する  

[Web アプリ マニフェストは][MDNWebAppManifest]、名前、説明、アイコンなど、アプリに関するメタデータを含む JSON ファイルです。  

アプリ マニフェストを Web アプリに追加するには:  

1.  [Visual Studioコード] で、[**ファイル**を  >  **開くフォルダー] を**選択し、前に作成 `MySamplePwa` したディレクトリを選択します。  
1.  新 `Ctrl` + `N` しいファイルを作成するために選択し、次のコード スニペットに貼り付けます。  
    
    ```json
    {
        "lang": "en-us",
        "name": "My Sample PWA",
        "short_name": "SamplePWA",
        "description": "A sample PWA for testing purposes",
        "start_url": "/",
        "background_color": "#2f3d58",
        "theme_color": "#2f3d58",        
        "orientation": "any",
        "display": "standalone",
        "icons": [
            {
                "src": "/icon512.png",
                "sizes": "512x512"
            }
        ]
    }
    ```  
    
1.  ファイルを次のように保存します `/MySamplePwa/public/manifest.json` 。  
1.  Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images` .  サンプル イメージは、 [テスト目的][ImagePwa] で使用できます。  
1.  コードVisual Studio開き `/public/index.html` 、タグ内に次のコード スニペットを追加 `<head>` します。  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### 手順 3 - サービス ワーカーを追加する  

サービス ワーカーは PAS の主要なテクノロジであり、オフライン サポート、高度なキャッシュ、以前はネイティブ アプリに限定されたバックグラウンド タスクの実行のようなシナリオを実現します。  

サービス ワーカーは、Web アプリからのネットワーク要求を傍受するバックグラウンド タスクです。  サービス ワーカーは、PWA が実行されていない場合でもタスクの完了を試みる。  タスクには、次のアクションが含まれます。  

*   キャッシュから要求されたリソースの提供  
*   プッシュ通知の送信  
*   バックグラウンド フェッチ タスクの実行  
*   バグアイコン  
*   その他  
    
サービス ワーカーは、特別な JavaScript ファイルで定義されます。  詳細については、「サービス ワーカーと [サービス][MDNUsingServiceWorkers] ワーカー API を使用する [」に移動します][MDNServiceWorkerApi]。  

プロジェクトでサービス ワーカーを作成するには[、PWA Builder][PwaBuilderServiceWorker]の**キャッシュ**ファースト ネットワーク サービス ワーカー レシピを使用します。  

1.  キャッシュ に [pwabuilder.com/serviceworker、][PwaBuilderServiceWorker]キャッシュファースト ネットワーク サービス ワーカー **を** 選択して、[ダウンロード] ボタン **を選択** します。  ダウンロードしたファイルには、次のファイルが含まれます。
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
        
1.  ダウンロードしたファイルを Web アプリ `public` プロジェクトのフォルダーにコピーします。  
1.  [Visual Studioコード] で、タグ `/public/index.html` 内で次のコード スニペットを開いて追加 `<head>` します。  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
これで、Web アプリに、キャッシュファースト戦略を使用するサービス ワーカーが追加されます。  新しいサービス ワーカーは、最初にキャッシュからリソースをフェッチし、必要に応じてネットワークからのみリソースをフェッチします。  キャッシュされたリソースには、画像、JavaScript、CSS、HTML が含まれます。

次の手順を使用して、サービス ワーカーが実行されるのを確認します。  

1.  使用して Web アプリに移動します `http://localhost:3000` 。  Web アプリが使用できない場合は、次のコマンドを実行します。   
    
    ```shell
    npm start
    ```
    
1.  Microsoft Edge で `F12` 、Microsoft Edge DevTools を開くことを選択します。  [ **アプリケーション]** を選択し、[ **サービス ワーカー] を** 選択してサービス ワーカーを表示します。  サービス ワーカーが表示されない場合は、ページを更新します。  
    
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools Service Worker の概要" lightbox="./media/devtools-sw-overview.png":::
       Microsoft Edge DevTools Service Worker の概要
    :::image-end:::
    
1.  [キャッシュ ストレージ] を展開**** し **、pwabuilder-precache**を選択して、サービス ワーカー キャッシュを表示します。  サービス ワーカーによってキャッシュされたリソースすべてが表示されます。  サービス ワーカーによってキャッシュされるリソースには、アプリ アイコン、アプリ マニフェスト、CSS、JavaScript ファイルが含まれます。  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools のサービス ワーカー キャッシュ" lightbox="./media/devtools-cache.png":::
       Microsoft Edge DevTools のサービス ワーカー キャッシュ (F12)
    :::image-end:::
    
1.  オフライン アプリとして PWA を試してください。  Microsoft Edge DevTools \( \) で、[ネットワーク] を選択し、[オンライン] の状態を `F12` [**オフライン**] に**変更します**。 ****  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="Microsoft Edge DevTools でアプリをオフライン モードに設定する" lightbox="./media/devtools-offline.png":::
       Microsoft Edge DevTools でアプリをオフライン モードに設定する
    :::image-end:::
    
1.  アプリを更新すると、キャッシュからアプリのリソースを提供するためのオフライン メカニズムが表示されます。  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="オフラインで実行されている PWA" lightbox="./media/vs-nodejs-express-index.png":::
       オフラインで実行されている PWA
    :::image-end:::
    
## PWA にプッシュ通知を追加する  

プッシュ通知をサポートする PAS を作成するには、次のタスクを実行します。  

1.  プッシュ API を使用してメッセージング サービスを [サブスクライブする][MDNPushApi]  
1.  Notifications API を使用してサービスからメッセージを受信するとトースト メッセージを [表示する][MDNNotificationsApi]  
    
サービス ワーカーと同様に、プッシュ通知 API は標準ベースの API です。  プッシュ通知 API はブラウザー間で機能します。したがって、コードは PAP がサポートされているあらゆる場所で動作する必要があります。  サーバー上の異なるブラウザーにプッシュ メッセージを配信する方法の詳細については [、Web プッシュに移動します][NPMWebPush]。  

次の手順は、Mozilla が提供する Service [Worker Cookbook][ServiceWorkerCookbookPushRichDemo] の Push Rich Demo から作成された手順です。Mozilla には、他にも便利な Web プッシュとサービス ワーカーのレシピが多数用意されています。  

### 手順 1 - VAPID キーを生成する  

プッシュ通知では、PWA クライアントにプッシュ メッセージを送信するために VAPID \(任意のアプリケーション サーバー識別\) キーが必要です。  オンラインで利用可能な VAPID キー ジェネレーターは複数あります (たとえば、vapidkeys.com [\)。][VapidkeysMain]  生成後、公開キーとプライベート キーを含む JSON オブジェクトを取得する必要があります。  次のチュートリアルの後の手順で使用するキーを保存します。  VAPID と WebPush の詳細については [、Mozilla Push Service][MozillaServicesSendingVapidWebPushNotificationsPush]を使用して VAPID が識別した WebPush 通知の送信に移動します。  

### 手順 2 - プッシュ通知をサブスクライブする  

サービス ワーカーは、PWA でプッシュ イベントとトースト通知の操作を処理します。  PWA をサーバー プッシュ通知にサブスクライブするには、次の条件が満たされている必要があります。  

*   PWA がインストール、アクティブ、および登録されている  
*   サブスクリプション タスクを完了するコードが PWA のメイン UI スレッドにある  
*   ネットワーク接続がある  
    
新しいプッシュ サブスクリプションを作成する前に、Microsoft Edge は、ユーザーが通知を受信するための PWA アクセス許可を付与した場合に確認します。  アクセス許可が設定されていない場合、ユーザーはブラウザーからアクセス許可を求めるメッセージが表示されます。  アクセス許可が拒否された場合、要求は処理 `registration.pushManager.subscribe` `DOMException` する必要があります。  アクセス許可管理の詳細については [、Microsoft Edge のプッシュ通知に移動します][WindowsBlogsWebNotificationsEdge]。  

ファイルに `pwabuilder-sw-register.js` 、次のコード スニペットを追加します。  

```javascript
// Ask the user for permission to send push notifications.
navigator.serviceWorker.ready
    .then(function (registration) {
        // Check if the user has an existing subscription
        return registration.pushManager.getSubscription()
            .then(function (subscription) {
                if (subscription) {
                    return subscription;
                }
                
                const vapidPublicKey = "PASTE YOUR PUBLIC VAPID KEY HERE";             
                return registration.pushManager.subscribe({
                    userVisibleOnly: true,
                    applicationServerKey: urlBase64ToUint8Array(vapidPublicKey)
                });
            });
    });

// Utility function for browser interoperability
function urlBase64ToUint8Array(base64String) {
    var padding = '='.repeat((4 - base64String.length % 4) % 4);
    var base64 = (base64String + padding)
        .replace(/\-/g, '+')
        .replace(/_/g, '/');
        
    var rawData = window.atob(base64);
    var outputArray = new Uint8Array(rawData.length);
    
    for (var i = 0; i < rawData.length; ++i) {
        outputArray[i] = rawData.charCodeAt(i);
    }
    return outputArray;
}
```  

詳細については [、PushManager][MDNPushManager] と [Web プッシュに移動します][NPMWebPushUsage]。  

### 手順 3 - プッシュ通知をリッスンする  

PWA でサブスクリプションを作成したら、プッシュ イベントに応答するハンドラーをサービス ワーカーに追加します。  プッシュ イベントは、トースト通知を表示するためにサーバーから送信されます。  トースト通知は、受信したメッセージのデータを表示します。  次のタスクを完了するには、クリック ハンドラーを追加する必要があります。  

*   トースト通知を閉じる  
*   開く、フォーカスする、開く、フォーカスを設定する  
*   PWA クライアント ページを表示するために新しいウィンドウを開いてフォーカスを設定する  
    
ファイルに `pwabuilder-sw.js` 、次のハンドラーを追加します。  

```javascript
// Respond to a server push with a user notification.
self.addEventListener('push', function (event) {
    if (Notification.permission === "granted") {
        const notificationText = event.data.text();
        const showNotification = self.registration.showNotification('Sample PWA', {
            body: notificationText,
            icon: 'images/icon512.png'
        });
        // Ensure the toast notification is displayed before exiting the function.
        event.waitUntil(showNotification);
    }
});

// Respond to the user selecting the toast notification.
self.addEventListener('notificationclick', function (event) {
    console.log('On notification click: ', event.notification.tag);
    event.notification.close();
    
    // This attempts to display the current notification if it is already open and then focuses on it.
    event.waitUntil(clients.matchAll({
        type: 'window'
    }).then(function (clientList) {
        for (var i = 0; i < clientList.length; i++) {
            var client = clientList[i];
            if (client.url == 'http://localhost:1337/' && 'focus' in client)
                return client.focus();
        }
        if (clients.openWindow)
            return clients.openWindow('/');
    }));
});
```  

### 手順 4 - 試してみる  

PWA のプッシュ通知をテストするには、次の手順を実行します。  

1.  PWA に移動します `http://localhost:3000` 。  サービス ワーカーがアクティブ化し、PWA をサブスクライブして通知をプッシュしようとすると、Microsoft Edge は PWA に通知の表示を許可するように求めるメッセージを表示します。  [許可 **] を選択します**。  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="通知を有効にするためのアクセス許可ダイアログ" lightbox="./media/notification-permission.png":::
       通知を有効にするためのアクセス許可ダイアログ
    :::image-end:::
    
1.  サーバー側プッシュ通知をシミュレートします。  ブラウザーで PWA を開 `http://localhost:3000` いた後 `F12` 、DevTools を開くことを選択します。  [**アプリケーション**  >  **サービス ワーカー プッシュ]**  >  **を選択**して、テスト プッシュ通知を PWA に送信します。  
    
    :::row:::
       :::column span="":::
          プッシュ通知はタスク バーの近くに表示されます。  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="DevTools からの通知のプッシュ" lightbox="./media/devtools-push.png":::
             DevTools からの通知のプッシュ  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          トースト通知を \(または activate\) 選択しない場合、システムは数秒後に自動的に通知を閉じ、Windows アクション センターでキューに入れられます。  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows アクション センターでの通知" lightbox="./media/windows-action-center.png":::
             Windows アクション センターでの通知 :::image-end:::
       :::column-end:::
    :::row-end:::  
    
## 次のステップ  

以下の手順には、実際の PAS の構築を理解するのに役立つ追加のタスクが含まれています。  

*   プッシュ サブスクリプションの管理と保存  
*   [ペイロード データ][NPMWebPushEncrypt] を暗号化する  
*   レスポンシブ デザイン  
*   ディープ リンク  
*   [クロスブラウザー テスト][BrowserStackTestEdgeBrowser]  
*   Webhint などの検証とテストのプラクティス [を実装する][Webhint]  
    
## 関連項目  

*   [MDN Web ドキュメント上の段階的な Web アプリ][MDNProgressiveWebApps]  
*   [Web.dev 上の段階的な Web アプリ][WebDevProgressiveWebApps]  
*   [段階的な Web][HackerNewsProgressiveWebApps] アプリとしてのハッカーニュース リーダー - サンプル \(Hacker News reader\) PWA を実装するためのさまざまなフレームワークとパフォーマンス パターンを比較します。  
*   [1000,000][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [段階的な Web アプリの段階的なロードマップ][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [段階的な Web アプリを使用したオフライン POS][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA Q&A][AaronGustafsonNotebookPwaQa]  
*   [Web 上で楽しむ][JoretegBlogBettingWeb]  
*   [段階的な Web アプリの名前付け][Fberriman20170626NamingProgressiveWebApps]  
*   [フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 1)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 2)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 3)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "コードをNode.jsして Azure にアプリをVisual Studioする |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントを作成する |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio Code"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA Q&A"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "段階的な Web アプリの段階的なロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "新しい Edge Edition の機能を提供する PAS"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express アプリケーション ジェネレーター |Express" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "段階的な Web アプリの名前付け"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "段階的な Web アプリとしてのハッカーニュースリーダー"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web 上で楽しむ"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "段階的な Web アプリ \(PAS) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "サービス ワーカー API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービス ワーカーの使用 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "段階的な Web アプリを使用したオフライン POS"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "Mozilla のプッシュ サービスを介して VAPID によって識別された WebPush 通知を送信する |Mozilla Services"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-push |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt(userPublicKey, userAuth, payload, contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用法 - Web プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "段階的な Web アプリ"  

[PwaBuilder]: https://www.pwabuilder.com "PWA Builder"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービス ワーカー |PWA Builder"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "プッシュ リッチ デモ |ServiceWorker Cookbook"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 1)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 3)"  

[VapidkeysMain]: https://vapidkeys.com "Secure VAPID Key Generator |VapidKeys" 

[Webhint]: https://webhint.io "webhint"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "段階的な Web アプリ |web.dev"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "段階的な機能強化 |Wikipedia"  
