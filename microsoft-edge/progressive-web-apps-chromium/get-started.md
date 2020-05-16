---
description: このガイドでは、Windows でプログレッシブ web アプリを構築するための PWA の基本とツールの概要について説明します。
title: プログレッシブ Web アプリ (Chromium) の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、PWABuilder、web マニフェスト、サービスワーカー、プッシュ
ms.openlocfilehash: 6c5fa5d6af8494f33e11a545d5dde1264604c787
ms.sourcegitcommit: 136642396bb8094a535e203067ee429e60d31d25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "10659210"
---
# プログレッシブ Web アプリ (Chromium) の使用を開始する  

プログレッシブ Web アプリ \ (PWAs \) は、インストール、オフラインサポート、プッシュ通知などのアプリのような機能によって[段階的に拡張][WikiProgressiveEnhancement]された web アプリです。  また、Microsoft ストアや Google Play、Mac App Store などのアプリストア用に PWA をパッケージ化することもできます。  Microsoft Store は、Windows 10 に組み込まれた商用アプリストアです。  

次のガイドでは、簡単な web アプリを作成し、それを PWA として拡張することで、PWA の基本的な概要を示します。  完成したプロジェクトは、最新のブラウザーで動作します。  

> [!TIP]
> [PWABuilder][PwaBuilder]を使用して、新しい pwa の作成、既存の pwa の強化、アプリストア用の pwa のパッケージ化を行うことができます。  

## 前提条件  

*   PWA ソースコードを編集するには、 [VS コード][VisualstudioCodeMain]を使います。  
*   ローカル web サーバーとして[node.js][NodejsMain]を使用します。  

## 基本的な web アプリをセットアップする  

空の web アプリを作成するには、[ノードエクスプレスアプリジェネレーター][ExpressjsApplicationGenerator]の手順に従い、アプリの名前を指定し `MySamplePwa` ます。  

プロンプトが表示されたら、次のコマンドを実行します。  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

このコマンドは、空の web アプリを作成して、依存関係をインストールします。  

簡単で実用的な web アプリを使用できるようになりました。  開始するには、次のコマンドを実行します。  

```shell
npm start
```  

次に、を参照し `http://localhost:3000` て新しい web アプリを表示します。  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="新しい PWA を localhost で実行する":::
   新しい PWA を localhost で実行する
:::image-end:::

## PWA の構築を開始する  

シンプルな web アプリを作成したので、PWAs の3つの要件を追加して、それを PWA として拡張します。<!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]-->: [HTTPS](#step-1---use-https)、 [Web アプリマニフェスト](#step-2---create-a-web-app-manifest)、[サービスワーカー](#step-3---add-a-service-worker)。  

### 手順 1-HTTPS を使用する  

[サービスワーカー][MDNServiceWorkerApi]などの PWA プラットフォームの重要な部分には、HTTPS を使用する必要があります。  PWA が有効になったら、HTTPS URL に公開する必要があります。  

デバッグ目的で、Microsoft Edge でも `http://localhost` PWA api の使用が許可されています。  

[Web アプリをライブサイトとして発行][VisualStudioNodejsTutorialPublishAzureAppService]する場合 (たとえば、 [Azure free アカウント][AzureCreateFreeAccount]をセットアップして)、サーバーが HTTPS 用に構成されていることを確認する必要があります。  [Microsoft Azure App Service][AzureWebApps]を使ってサイトをホストしている場合、既定では HTTPS 経由で提供されます。  

次のガイドを使用し `http://localhost` て、PWA を構築します。  

### 手順 2-Web アプリマニフェストを作成する  

[Web アプリマニフェスト][MDNWebAppManifest]は、アプリに関するメタデータ (名前、説明、アイコンなど) を含む JSON ファイルです。  

Web アプリにアプリマニフェストを追加するには、次の操作を行います。  

1.  VS コードで、[**ファイル**を  >  **開く] フォルダーを開い**て、前に作成したディレクトリを選択し `MySamplePwa` ます。  
1.  を押して `Ctrl` + `N` 新しいファイルを作成し、次のコードスニペットに貼り付けます。  
    
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
    
1.  ファイルをとして保存 `/MySamplePwa/public/manifest.json` します。  
1.  という名前の 512 x 512 のアプリアイコンイメージを追加 `icon512.png` `/MySamplePwa/public/images` します。  テスト目的で[サンプルの画像][ImagePwa]を使うことができます。  
1.  VS コードで、 `/public/index.html` を開き、次のコードスニペットをタグ内に追加し `<head>` ます。  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### 手順 3-サービスワーカーを追加する  

サービスワーカーは、PWAs の主要なテクノロジであり、オフラインサポート、高度なキャッシュ、実行中のバックグラウンドタスクなどのシナリオを以前からネイティブアプリに限定することができます。  

サービスワーカーは、web アプリからネットワーク要求を傍受するバックグラウンドタスクです。  ユーザーは、PWA が実行されていない場合でも、キャッシュからの要求されたリソースの提供、プッシュ通知の送信、バックグラウンドフェッチタスクの実行、バッジのアイコンの実行など、タスクを実行します。  サービスワーカーは、特別な JavaScript ファイルで定義されています。  詳細については、「[サービスワーカー][MDNUsingServiceWorkers]と[サービスワーカー API][MDNServiceWorkerApi]の使用」を参照してください。  

プロジェクトでサービスワーカーを構築するには、 [PWA ビルダー][PwaBuilderServiceWorker]から**キャッシュの最初のネットワーク**サービスワーカーレシピを使用します。  

1.  [Pwabuilder.com/serviceworker][PwaBuilderServiceWorker]に移動して、[**キャッシュ-最初のネットワーク**サービス] ワーカーを選択し、[**ダウンロード**] ボタンを選択します。  ダウンロードしたファイルには、次のファイルが含まれます。
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
    
1.  ダウンロードしたファイルを `public` web アプリプロジェクトのフォルダーにコピーします。  
    
1.  VS コードで、 `/public/index.html` 次のコードスニペットを開いて、タグ内に追加し `<head>` ます。  
    
    ```html
    <script src="/pwabuilder-sw-register.js"></script>
    ```  
    
これで、web アプリには、最初にキャッシュからのリソース、JS、CSS、HTML などのリソースを取得し、必要に応じてネットワークにフォールバックする、キャッシュ方式を使うサービスワーカーが用意されました。  

次の手順を使用して、サービスワーカーが実行されていることを確認します。  

1.  を使用して web アプリに移動し `http://localhost:3000` ます。  Web アプリを利用できない場合は、次のコマンドを実行します。   
    
    ```shell
    npm start
    ```
    
1.  Microsoft Edge で、 `F12` Microsoft Edge DevTools を選択して開きます。  [**アプリケーション**] を選択し**てから、サービスワーカー**を表示します。  サービスワーカーが表示されない場合は、ページの更新が必要になることがあります。  
     
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools サービスワーカーの概要":::
       Microsoft Edge DevTools サービスワーカーの概要
    :::image-end:::
    
1.  **キャッシュストレージ**を展開してサービスワーカーキャッシュを表示し、[ **pwabuilder-precache**] を選択します。  アプリのアイコン、アプリマニフェスト、CSS、JavaScript ファイルなど、サービスワーカーによってキャッシュされたすべてのリソースが表示されます。  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools の Service Worker キャッシュ":::
       Microsoft Edge DevTools でのサービスワーカーキャッシュ (F12)
    :::image-end:::
    
1.  PWA をオフラインアプリとして試してみてください。  Microsoft Edge DevTools \ ( `F12` \) で、[**ネットワーク**] を選択し、[**オンライン**状態] を [**オフライン**] に変更します。  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="Microsoft Edge DevTools でアプリをオフラインモードに設定する":::
       Microsoft Edge DevTools でアプリをオフラインモードに設定する
    :::image-end:::
    
1.  アプリを最新の状態に更新すると、アプリのリソースがキャッシュから提供されるため、オフラインで作業していることがわかります。  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="オフラインで実行されている PWA":::
       オフラインで実行されている PWA
    :::image-end:::
    
## PWA にプッシュ通知を追加する  

次のタスクを実行して、プッシュ通知をサポートする PWAs を作成することができます。  

1.  [プッシュ API][MDNPushApi]を使用したメッセージサービスの購読  
1.  [通知 API][MDNNotificationsApi]を使用して、サービスからメッセージが受信されたときにトーストメッセージを表示する  

サービスワーカーの場合と同様に、これらはブラウザー間で動作する標準ベースの Api であるため、このコードを1回記述するだけで、PWAs がサポートされているすべての場所で動作させることができます。  サーバー上のさまざまなブラウザーへのプッシュメッセージの配信の詳細については、 [「Web-プッシュ][NPMWebPush]ソースライブラリ」を参照してください。  

以下の手順は、Mozilla が提供する[Service Worker][ServiceWorkerCookbookPushRichDemo]の Web サイトの「プッシュリッチデモ」で採用されています。これには、他にも多くの便利な Web プッシュとサービス worker のレシピが用意されています。  

### 手順 1-VAPID キーを生成する  

プッシュ通知には、PWA クライアントにプッシュメッセージを送信するために、VAPID \ (自主的なアプリケーションサーバー Id) キーが必要です。  オンラインで利用できる VAPID キージェネレーターはいくつかあります ( [vapidkeys.com][VapidkeysMain]など)。  生成後、公開キーと秘密キーを含む JSON オブジェクトを取得する必要があります。  以降の手順に従ってキーを保存します。次のチュートリアルを実行します。  VAPID と WebPush のしくみの詳細については、「 [Mozilla のプッシュサービス経由で VAPID 識別された Web プッシュ通知を送信][MozillaServicesSendingVapidWebPushNotificationsPush]する」を参照してください。  

### 手順 2-プッシュ通知への登録  

サービスワーカーは、PWA でプッシュイベントとトースト通知のやり取りを処理します。  PWA をサーバープッシュ通知に登録するには、次の条件が満たされていることを確認します。  

*   PWA がインストールされ、アクティブで登録されている  
*   サブスクリプションタスクを実行するコードは、PWA のメイン UI スレッドにあります。  
*   ネットワーク接続がある場合  

新しいプッシュサブスクリプションが作成される前に、Microsoft Edge は、ユーザーが通知を受信できるように PWA 権限を与えられているかどうかを確認します。  許可されていない場合は、ブラウザーからアクセス許可を求められます。  アクセス許可が拒否された場合は、を例外として `registration.pushManager.subscribe` `DOMException` 処理する必要があります。  権限の管理について詳しくは、「 [Microsoft Edge でのプッシュ通知][WindowsBlogsWebNotificationsEdge]」をご覧ください。  

ファイルで `pwabuilder-sw-register.js` 、次のコードスニペットを追加します。  

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

詳細については、「 [Pushmanager][MDNPushManager]と[Web (プッシュ)][NPMWebPushUsage]」をご覧ください。  

### 手順 3-プッシュ通知をリッスンする  

これでサブスクリプションが PWA で設定されたので、プッシュイベント (サーバーから送信) に応答するためのハンドラーをサービスワーカーに追加して、受信メッセージのデータを使ってトースト通知を表示します。  次のいずれかのタスクを実行するには、クリックハンドラーを追加する必要があります。  
*   トースト通知を無視する  
*   開いているウィンドウを開く、フォーカスする、または開く  
*   新しいウィンドウを開いてフォーカスを移動し、PWA クライアントページを表示する  

ファイルで `pwabuilder-sw.js` 、次のハンドラーを追加します。  

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
    
    // This looks to see if the current notification is already open and focuses it.
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

### 手順 4-試してみる  

PWA でプッシュ通知をテストするには、次の手順を実行します。  

1.  PWA に移動 `http://localhost:3000` します。  サービスワーカーがアクティブになって PWA のプッシュ通知をサブスクライブしようとすると、Microsoft Edge で、PWA に通知を表示することを許可するように求められます。  [**許可**] を選びます。  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="通知を有効にするためのアクセス許可ダイアログ":::
       通知を有効にするためのアクセス許可ダイアログ
    :::image-end:::
    
    
1.  サーバー側のプッシュ通知をシミュレートします。  使用しているブラウザーで PWA が開いたら `http://localhost:3000` 、を選択して `F12` devtools を開きます。  [**アプリケーション**  >  **サービスワーカー**プッシュ] を選択し  >  **Push**て、PWA にテストプッシュ通知を送信します。  プッシュ通知はタスクバーの近くに表示されます。  
    
    :::image type="complex" source="./media/devtools-push.png" alt-text="DevTools から通知をプッシュする":::
       DevTools から通知をプッシュする
    :::image-end:::
     
    トースト通知を選択しない場合は、数秒後に表示されなくなり、Windows アクションセンターでキューに入れられます。  
    
    :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows アクションセンターでの通知":::
       Windows アクションセンターでの通知
    :::image-end:::
    
    
## 次のステップ  

次に、現実世界での構築時に学習する追加のタスクを示します。  

*  プッシュサブスクリプションの管理と保存  
*  ペイロードデータを[暗号化][NPMWebPushEncrypt]する  
*  レスポンシブ デザイン  
*  ディープリンク  
*  [ブラウザ間のテスト][BrowserStackTestEdgeBrowser]  
*  [Webhint][Webhint]などのベストプラクティスを実装する  

## 関連項目  

*   [MDN web ドキュメントのプログレッシブ Web アプリ][MDNProgressiveWebApps]。  
*   [Web.config でのプログレッシブ Web アプリ][WebDevProgressiveWebApps]。  
*   [[プログレッシブ Web アプリとしてのハッカーニュースリーダー][HackerNewsProgressiveWebApps] ]: サンプル \ (ハッカーたち News READER) PWA を実装するためのさまざまなフレームワークとパフォーマンスパターンを比較します。  

<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "Azure App Service に発行する-Visual Studio でノード .js と Express アプリを作成する |Microsoft ドキュメント"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントの作成 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio コード"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "エクスプレスアプリケーションジェネレーター |高速" 

[HackerNewsProgressiveWebApps]: https://hnpwa.com "プログレッシブ Web アプリとしてのハッカーニュースリーダー"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "プログレッシブ web アプリ \ (PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービスワーカーを使用する |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "VAPID を Mozilla のプッシュサービス経由で識別された Web プッシュ通知を送信しています。 |Mozilla サービス"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-プッシュ |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "暗号化 (userPublicKey、Userpublickey、payload、contentEncoding)-web-プッシュ |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用状況-web-プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "プログレッシブ Web アプリ"  

[PwaBuilder]: https://www.pwabuilder.com "PWA ビルダー"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービスワーカー |PWA ビルダー"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "充実したデモのプッシュ |ServiceWorker の料理"  

[VapidkeysMain]: https://vapidkeys.com "Secure VAPID Key Generator |VapidKeys" 

[Webhint]: https://sonarwhal.com "web ベストプラクティスのヒントエンジンの web ヒント"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "プログレッシブ Web アプリ |web.xml"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "プログレッシブエンハンスメント |Wikipedia"  
