---
description: このガイドでは、Windows でプログレッシブ Web アプリ (Chromium) を構築するための PWA の基本とツールの概要について説明します。
title: プログレッシブ Web アプリ (Chromium) の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、PWABuilder、web マニフェスト、サービスワーカー、プッシュ
ms.openlocfilehash: 065ced3afa8ecd4165325fd4f10a673d86c72fa7
ms.sourcegitcommit: be76feed0d616a96c77ea2748a9f0d6c0c06284b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103925"
---
# プログレッシブ Web アプリ (Chromium) の使用を開始する  

プログレッシブ Web アプリ (PWAs \) は、 [段階的に拡張][WikiProgressiveEnhancement]されている web アプリです。  プログレッシブ機能拡張には、インストール、オフラインサポート、プッシュ通知などのアプリのような機能が含まれています。  アプリストア用の PWA をパッケージ化することもできます。  アプリストアには、Microsoft ストア、Google Play、Mac App Store などが含まれている可能性があります。  Microsoft Store は、Windows 10 に組み込まれた商用アプリストアです。  

次のガイドでは、簡単な web アプリを作成し、それを PWA として拡張することで、PWA の基本的な概要を示します。  完成したプロジェクトは、最新のブラウザーで動作します。  

> [!TIP]
> [PWABuilder][PwaBuilder]を使用して、新しい pwa の作成、既存の pwa の強化、アプリストア用の pwa のパッケージ化を行うことができます。  

## 前提条件  

*   [Visual Studio コード][VisualstudioCodeMain]を使って、PWA ソースコードを編集します。  
*   [Node.js][NodejsMain]をローカル web サーバーとして使用します。  

## 基本的な web アプリを作成する  

空の web アプリを作成するには、 [ノードエクスプレスアプリジェネレーター][ExpressjsApplicationGenerator]の手順に従い、アプリの名前を指定し `MySamplePwa` ます。  

プロンプトが表示されたら、次のコマンドを実行します。  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

このコマンドは、空の web アプリを作成して、依存関係をインストールします。  

これで、簡単で実用的な web アプリを利用できるようになりました。  Web アプリを起動するには、次のコマンドを実行します。  

```shell
npm start
```  

次に、を参照し `http://localhost:3000` て新しい web アプリを表示します。  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/vs-nodejs-express-index.png":::
   新しい PWA を localhost で実行する
:::image-end:::

## PWA の構築を開始する  

シンプルな web アプリを作成したので、PWAs の3つの要件を追加して、それを PWA として拡張します。<!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]-->: [HTTPS](#step-1---use-https)、 [Web アプリマニフェスト](#step-2---create-a-web-app-manifest)、 [サービスワーカー](#step-3---add-a-service-worker)。  

### 手順 1-HTTPS を使用する  

[サービスワーカー][MDNServiceWorkerApi]などの PWA プラットフォームの重要な部分には、HTTPS を使用する必要があります。  PWA が有効になったら、HTTPS URL に公開する必要があります。  

デバッグ目的で、Microsoft Edge でも `http://localhost` PWA api の使用が許可されています。  

[Web アプリをライブサイトとして公開][VisualStudioNodejsTutorialPublishAzureAppService]しますが、サーバーが HTTPS 用に構成されていることを確認します。  たとえば、 [Azure 無料アカウント][AzureCreateFreeAccount]を作成することができます。  [Microsoft Azure App Service][AzureWebApps]でサイトをホストします。既定では HTTPS 経由で提供されます。  

次のガイドを使用し `http://localhost` て、PWA を構築します。  

### 手順 2-Web アプリマニフェストを作成する  

[Web アプリマニフェスト][MDNWebAppManifest]は、アプリに関するメタデータ (名前、説明、アイコンなど) を含む JSON ファイルです。  

Web アプリにアプリマニフェストを追加するには、次の操作を行います。  

1.  Visual Studio のコードで、[**ファイル**を開くフォルダー] を選択し、前に作成した  >  **Open Folder**ディレクトリを選択し `MySamplePwa` ます。  
1.  `Ctrl` + `N` 新しいファイルを作成するには、次のコードスニペットを貼り付けます。  
    
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
1.  という名前の 512 x 512 のアプリアイコンイメージを追加 `icon512.png` `/MySamplePwa/public/images` します。  テスト目的で [サンプルの画像][ImagePwa] を使うことができます。  
1.  Visual Studio のコードで `/public/index.html` 、を開き、次のコードスニペットをタグ内に追加し `<head>` ます。  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### 手順 3-サービスワーカーを追加する  

サービスワーカーは、PWAs の主要なテクノロジであり、オフラインサポート、高度なキャッシュ、実行中のバックグラウンドタスクなどのシナリオを以前からネイティブアプリに限定することができます。  

サービスワーカーは、web アプリからネットワーク要求を傍受するバックグラウンドタスクです。  サービス作業者が、PWA が実行されていない場合でも、タスクの実行を試みます。  タスクには次の操作が含まれます。  

*   キャッシュから要求されたリソースを提供する  
*   プッシュ通知の送信  
*   バックグラウンドフェッチタスクの実行  
*   バッジのアイコン  
*   その他  

サービスワーカーは、特別な JavaScript ファイルで定義されています。  詳細については、「Service Worker と[Service WORKER API][MDNServiceWorkerApi][を使用][MDNUsingServiceWorkers]する」を参照してください。  

プロジェクトでサービスワーカーを構築するには、 [PWA ビルダー][PwaBuilderServiceWorker]から**キャッシュの最初のネットワーク**サービスワーカーレシピを使用します。  

1.  [Pwabuilder.com/serviceworker][PwaBuilderServiceWorker]に移動して、[**キャッシュ-最初のネットワーク**サービス] ワーカーを選択し、[**ダウンロード**] ボタンを選択します。  ダウンロードしたファイルには、次のファイルが含まれます。
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
    
1.  ダウンロードしたファイルを `public` web アプリプロジェクトのフォルダーにコピーします。  
    
1.  Visual Studio のコードで、 `/public/index.html` 次のコードスニペットを開いて、タグ内に追加し `<head>` ます。  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
これで、web アプリにキャッシュから最初の戦略を使用するサービスワーカーが作成されました。  新しいサービスワーカーは、最初に、または必要に応じてネットワークからリソースをフェッチします。  キャッシュされたリソースには、画像、JavaScript、CSS、HTML が含まれます。

次の手順を使用して、サービスワーカーが実行されていることを確認します。  

1.  を使用して web アプリに移動し `http://localhost:3000` ます。  Web アプリを利用できない場合は、次のコマンドを実行します。   
    
    ```shell
    npm start
    ```
    
1.  Microsoft Edge で、 `F12` Microsoft Edge DevTools を選択して開きます。  [ **アプリケーション**] を選択し **てから、サービスワーカー** を表示します。  サービスワーカーが表示されない場合は、ページを更新します。  
     
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/devtools-sw-overview.png":::
       Microsoft Edge DevTools サービスワーカーの概要
    :::image-end:::
    
1.  **キャッシュストレージ**を展開してサービスワーカーキャッシュを表示し、[ **pwabuilder-precache**] を選択します。  サービスワーカーによってキャッシュされたすべてのリソースが表示される必要があります。  サービスワーカーによってキャッシュされたリソースには、アプリのアイコン、アプリマニフェスト、CSS、JavaScript ファイルが含まれます。  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/devtools-cache.png":::
       Microsoft Edge DevTools でのサービスワーカーキャッシュ (F12)
    :::image-end:::
    
1.  PWA をオフラインアプリとして試してみてください。  Microsoft Edge DevTools \ ( `F12` \) で、[ **ネットワーク** ] を選択し、[ **オンライン** 状態] を [ **オフライン**] に変更します。  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/devtools-offline.png":::
       Microsoft Edge DevTools でアプリをオフラインモードに設定する
    :::image-end:::
    
1.  アプリを更新すると、キャッシュからアプリのリソースを提供するためのオフラインメカニズムが表示されます。  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/vs-nodejs-express-index.png":::
       オフラインで実行されている PWA
    :::image-end:::
    
## PWA にプッシュ通知を追加する  

次のタスクを実行して、プッシュ通知をサポートする PWAs を作成することができます。  

1.  [プッシュ API][MDNPushApi]を使用したメッセージサービスの購読  
1.  [通知 API][MDNNotificationsApi]を使用してサービスからメッセージを受信したときにトーストメッセージを表示する  
    
サービスワーカーの場合と同様に、プッシュ通知 Api は標準ベースの Api です。  プッシュ通知 Api はブラウザー間で動作するため、コードはすべてがサポートされているすべての場所で動作する必要があります。  サーバー上のさまざまなブラウザーへのプッシュメッセージの配信について詳しくは、[ [Web-プッシュ][NPMWebPush]] に移動してください。  

以下の手順は、Mozilla が提供する [Service Worker][ServiceWorkerCookbookPushRichDemo] の Web サイトの「プッシュリッチデモ」で採用されています。これには、他にも多くの便利な Web プッシュとサービス worker のレシピが用意されています。  

### 手順 1-VAPID キーを生成する  

プッシュ通知には、PWA クライアントにプッシュメッセージを送信するために、VAPID \ (自主的なアプリケーションサーバー Id) キーが必要です。  オンラインで利用できる VAPID キージェネレーターはいくつかあります ( [vapidkeys.com][VapidkeysMain]など)。  生成後、公開キーと秘密キーを含む JSON オブジェクトを取得する必要があります。  以降の手順については、次のチュートリアルのキーを保存します。  VAPID と WebPush の詳細については、「 [VAPID による Web プッシュ通知の送信][MozillaServicesSendingVapidWebPushNotificationsPush]」を参照してください。  

### 手順 2-プッシュ通知への登録  

サービスワーカーは、PWA でプッシュイベントとトースト通知のやり取りを処理します。  PWA をサーバープッシュ通知に登録するには、次の条件が満たされていることを確認します。  

*   PWA がインストール、アクティブ、登録されている  
*   サブスクリプションタスクを完了するコードは、PWA のメイン UI スレッドにあります。  
*   ネットワーク接続がある場合  
    
新しいプッシュサブスクリプションが作成される前に、Microsoft Edge は、ユーザーが通知を受信できるように PWA 権限を与えられているかどうかを確認します。  許可されていない場合は、ブラウザーからアクセス許可を求められます。  アクセス許可が拒否された場合は、を例外として `registration.pushManager.subscribe` `DOMException` 処理する必要があります。  権限管理の詳細については、「 [Microsoft Edge でのプッシュ通知」][WindowsBlogsWebNotificationsEdge]を参照してください。  

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

詳細については、「 [Pushmanager][MDNPushManager] と [Web-プッシュ][NPMWebPushUsage]」に移動します。  

### 手順 3-プッシュ通知をリッスンする  

PWA でサブスクリプションを作成した後で、プッシュイベントに応答するように、サービスワーカーにハンドラーを追加します。  プッシュイベントは、トースト通知を表示するためにサーバーから送信されます。  トースト通知では、受信したメッセージのデータが表示されます。  次のタスクを実行するには、クリックハンドラーを追加する必要があります。  

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

### 手順 4-試してみる  

PWA のプッシュ通知をテストするには、次の手順を実行します。  

1.  PWA に移動 `http://localhost:3000` します。  サービスワーカーがアクティブになって PWA のプッシュ通知をサブスクライブしようとすると、Microsoft Edge で、PWA に通知を表示することを許可するように求められます。  [ **許可**] を選びます。  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/notification-permission.png":::
       通知を有効にするためのアクセス許可ダイアログ
    :::image-end:::
    
1.  サーバー側のプッシュ通知をシミュレートします。  使用しているブラウザーで PWA が開いたら `http://localhost:3000` 、を選択して `F12` devtools を開きます。  [**アプリケーション**  >  **サービスワーカー**プッシュ] を選択し  >  **Push**て、PWA にテストプッシュ通知を送信します。  
    :::row:::
       :::column span="":::
          プッシュ通知は、タスクバーの近くに表示されます。  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/devtools-push.png":::
             DevTools から通知をプッシュする  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          トースト通知を選択しない場合、またはトースト通知を有効にしない場合は、数秒後に自動的に消去され、Windows アクションセンターでキューに表示されます。  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="新しい PWA を localhost で実行する" lightbox="./media/windows-action-center.png":::
             Windows アクションセンターでの通知 :::image-end:::
       :::column-end:::
    :::row-end:::  
    
## 次のステップ  

次の手順には、実際の PWAs の構築を理解するのに役立つ追加のタスクが含まれています。  

*   プッシュサブスクリプションの管理と保存  
*   ペイロードデータを[暗号化][NPMWebPushEncrypt]する  
*   レスポンシブ デザイン  
*   ディープリンク  
*   [ブラウザ間のテスト][BrowserStackTestEdgeBrowser]  
*   [Web ヒント][Webhint]などの検証およびテストの実施方法を実装する  
   
## 関連項目  

*   [MDN web ドキュメントのプログレッシブ Web アプリ][MDNProgressiveWebApps]  
*   [Dev でのプログレッシブ Web アプリ][WebDevProgressiveWebApps]  
*   [[プログレッシブ Web アプリとしてのハッカーニュースリーダー][HackerNewsProgressiveWebApps] ]: サンプル \ (ハッカーたち News READER) PWA を実装するためのさまざまなフレームワークとパフォーマンスパターンを比較します。  
*   [神話の場合][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [プログレッシブ Web アプリのためのプログレッシブロードマップ][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [プログレッシブ Web アプリでのオフライン投稿][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA&][AaronGustafsonNotebookPwaQa]  
*   [Web でのお賭け][JoretegBlogBettingWeb]  
*   [プログレッシブ Web アプリに名前を付ける][Fberriman20170626NamingProgressiveWebApps]  
*   [フレームワークなしでプログレッシブ Web アプリケーションを設計して構築する (パート 1)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 2)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 3)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "Visual Studio コードを使って Azure に Node.js アプリを展開する |Microsoft ドキュメント"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントの作成 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio コード"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA&"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "プログレッシブ Web アプリのためのプログレッシブロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "神話のお客は新しい Edge エディション"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "エクスプレスアプリケーションジェネレーター |高速" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "プログレッシブ Web アプリに名前を付ける"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "プログレッシブ Web アプリとしてのハッカーニュースリーダー"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web でのお賭け"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "プログレッシブ web アプリ \ (PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービスワーカーを使用する |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "プログレッシブ Web アプリでのオフライン投稿"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "VAPID を Mozilla のプッシュサービス経由で識別された Web プッシュ通知を送信しています。 |Mozilla サービス"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-プッシュ |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "暗号化 (userPublicKey、Userpublickey、payload、contentEncoding)-web-プッシュ |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用状況-web-プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "プログレッシブ Web アプリ"  

[PwaBuilder]: https://www.pwabuilder.com "PWA ビルダー"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービスワーカー |PWA ビルダー"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "充実したデモのプッシュ |ServiceWorker の料理"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークなしでプログレッシブ Web アプリケーションを設計して構築する (パート 1)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 3)"  

[VapidkeysMain]: https://vapidkeys.com "Secure VAPID Key Generator |VapidKeys" 

[Webhint]: https://webhint.io "web ヒント"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "プログレッシブ Web アプリ |web.xml"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "プログレッシブエンハンスメント |Wikipedia"  
