---
description: このガイドでは、Windows でプログレッシブ Web アプリ (Chromium) を構築するための PWA の基本とツールの概要を説明します。
title: プログレッシブ Web アプリ (Chromium) の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/16/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: プログレッシブ Web アプリ、PWA、Edge、Windows、PWABuilder、Web マニフェスト、サービス ワーカー、プッシュ
ms.openlocfilehash: 3023c38790185ca6989f4a487928abc79b1d5a2c
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480196"
---
# <a name="get-started-with-progressive-web-apps-chromium"></a>プログレッシブ Web アプリ (Chromium) の使用を開始する  

プログレッシブ Web アプリ \(PWAs\) は、段階的に拡張される [Web アプリです][WikiProgressiveEnhancement]。  プログレッシブ機能拡張には、インストール、オフライン サポート、プッシュ通知などのアプリのような機能が含まれます。  PWA をアプリ ストア用にパッケージ化することもできます。  可能なアプリ ストアには、Microsoft Store、Google Play、Mac App Store などがあります。  Microsoft Store は、Windows 10 に組み込みの商用アプリ ストアです。  

次のガイドでは、簡単な Web アプリを作成し、PWA として拡張することで、PWA の基本の概要を説明します。  完成したプロジェクトは、最新のブラウザーで動作します。  

> [!TIP]
> [PWABuilder を使用して][PwaBuilder]、新しい PWA の作成、既存の PWA の強化、またはアプリ ストア用の PWA のパッケージ化を行います。  

## <a name="prerequisites"></a>前提条件  

*   PWA [Visual Studioコード][VisualstudioCodeMain] を編集するには、[コード] を使用します。  
*   ローカル [Node.js][NodejsMain] サーバーとして使用します。  
    
## <a name="create-a-basic-web-app"></a>基本的な Web アプリを作成する  

空の Web アプリを作成するには [、「Node Express App Generator」][ExpressjsApplicationGenerator]の手順に従い、アプリの名前を指定します `MySamplePwa` 。  

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

:::image type="complex" source="./media/visual-studio-nodejs-express-index.png" alt-text="localhost で新しい PWA を実行する" lightbox="./media/visual-studio-nodejs-express-index.png":::
   localhost で新しい PWA を実行する  
:::image-end:::  

## <a name="get-started-building-a-pwa"></a>PWA の構築を開始する  

簡単な Web アプリが作成されたので、PWA として拡張するには、PWA の 3 つの要件を追加します。<!--[3 requirements for PWAs][ArchiveMicrosoftEdgeLegacyDeveloperPWAsIndexRequirements]-->: [HTTPS](#step-1---use-https) [、Web アプリ マニフェスト、](#step-2---create-a-web-app-manifest)および [サービス ワーカー](#step-3---add-a-service-worker)。  

### <a name="step-1---use-https"></a>手順 1 - HTTPS を使用する  

PWA プラットフォームの主要な部分 [(Service Workers][MDNServiceWorkerApi]など) では、HTTPS の使用が必要です。  PWA が公開された場合は、HTTPS URL に発行する必要があります。  

デバッグの目的で、Microsoft Edge では `http://localhost` PWA API の使用も許可されています。  

[Web アプリをライブ サイトとして公開します][VisualStudioNodejsTutorialPublishAzureAppService]が、サーバーが HTTPS 用に構成されていることを確認します。  たとえば、Azure 無料アカウント [を作成できます][AzureCreateFreeAccount]。  Microsoft Azure App Service で [サイトをホスト][AzureWebApps] すると、既定で HTTPS 経由で提供されます。  

次のガイドでは `http://localhost` 、PWA をビルドするために使用します。  

### <a name="step-2---create-a-web-app-manifest"></a>手順 2 - Web アプリ マニフェストを作成する  

[Web アプリ マニフェストは][MDNWebAppManifest]、名前、説明、アイコンなど、アプリに関するメタデータを含む JSON ファイルです。  

アプリ マニフェストを Web アプリに追加するには、次の方法を実行します。  

1.  [Visual Studio] で、[**ファイル**を開くフォルダー]  >  **を**選択し、前に作成 `MySamplePwa` したディレクトリを選択します。  
1.  選択 `Ctrl` + `N` して新しいファイルを作成し、次のコード スニペットに貼り付けます。  
    
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
    
1.  ファイルをとして保存します `/MySamplePwa/public/manifest.json` 。  
1.  にという名前の 512x512 アプリ アイコン イメージを追加 `icon512.png` します `/MySamplePwa/public/images` 。  サンプル イメージは、 [テストの目的](./media/progressive-web-app.png) で使用できます。  
1.  [コードVisual Studio開き `/public/index.html` 、タグ内に次のコード スニペットを追加 `<head>` します。  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <a name="step-3---add-a-service-worker"></a>手順 3 - サービス ワーカーを追加する  

サービス ワーカーは、PWA の主要なテクノロジであり、オフライン サポート、高度なキャッシュ、以前はネイティブ アプリに限定されたバックグラウンド タスクの実行など、シナリオを可能にします。  

サービス ワーカーは、Web アプリからネットワーク要求を傍受するバックグラウンド タスクです。  サービス ワーカーは、PWA が実行されていない場合でもタスクを完了します。  タスクには、次のアクションが含まれます。  

*   キャッシュから要求されたリソースを提供する  
*   プッシュ通知の送信  
*   バックグラウンド フェッチ タスクの実行  
*   バッド アイコン  
*   およびその他  
    
サービス ワーカーは特別な JavaScript ファイルで定義されます。  詳細については、「サービス ワーカーとサービス ワーカー API[の使用][MDNUsingServiceWorkers][」に移動します][MDNServiceWorkerApi]。  

プロジェクトでサービス ワーカーを構築するには、PWA Builder の **キャッシュファースト ネットワーク** サービス ワーカー レシピ [を使用します][PwaBuilderServiceWorker]。  

1.  [キャッシュ] [pwabuilder.com/serviceworker、][PwaBuilderServiceWorker]キャッシュ ファースト ネットワーク サービス ワーカーを **選択** し、[ダウンロード] ボタン **を選択** します。  ダウンロードしたファイルには、次のファイルが含まれます。
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
        
1.  ダウンロードしたファイルを Web アプリ `public` プロジェクトのフォルダーにコピーします。  
1.  [Visual Studioコード] で、次のコード スニペットを開 `/public/index.html` いてタグ内に追加 `<head>` します。  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
これで、キャッシュファースト戦略を使用するサービス ワーカーが Web アプリに追加されます。  新しいサービス ワーカーは、最初にキャッシュから、必要に応じてネットワークからリソースをフェッチします。  キャッシュされたリソースには、イメージ、JavaScript、CSS、HTML が含まれます。

サービス ワーカーが実行されるのを確認するには、次の手順を使用します。  

1.  を使用して Web アプリに移動します `http://localhost:3000` 。  Web アプリが使用できない場合は、次のコマンドを実行します。   
    
    ```shell
    npm start
    ```
    
1.  Microsoft Edge で、Microsoft Edge `F12` DevTools を開く場合に選択します。  [ **アプリケーション]** を選択し **、[サービス ワーカー] を選択** してサービス ワーカーを表示します。  サービス ワーカーが表示されない場合は、ページを更新します。  
    
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools Service Worker の概要" lightbox="./media/devtools-sw-overview.png":::
       Microsoft Edge DevTools Service Worker の概要  
    :::image-end:::  
    
1.  [キャッシュ ストレージ] を展開してサービス ワーカー キャッシュを **表示** し **、[pwabuilder-precache] を選択します**。  サービス ワーカーによってキャッシュされたリソースはすべて表示されます。  サービス ワーカーによってキャッシュされるリソースには、アプリ アイコン、アプリ マニフェスト、CSS、および JavaScript ファイルが含まれます。  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools のサービス ワーカー キャッシュ" lightbox="./media/devtools-cache.png":::
       Microsoft Edge DevTools \(F12\) のサービス ワーカー キャッシュ  
    :::image-end:::  
    
1.  オフライン アプリとして PWA を試してみてください。  Microsoft Edge DevTools \( `F12` \) で、[ **ネットワーク** ] を選択し、[オンライン] 状態 **を [オフライン** ] に **変更します**。  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="Microsoft Edge DevTools でアプリをオフライン モードに設定する" lightbox="./media/devtools-offline.png":::
       Microsoft Edge DevTools でアプリをオフライン モードに設定する  
    :::image-end:::  
    
1.  アプリを更新すると、キャッシュからアプリのリソースを提供するためのオフライン メカニズムが表示されます。  
    
    :::image type="complex" source="./media/visual-studio-nodejs-express-index.png" alt-text="オフラインで実行されている PWA" lightbox="./media/visual-studio-nodejs-express-index.png":::
       オフラインで実行されている PWA  
    :::image-end:::  
    
## <a name="add-push-notifications-to-your-pwa"></a>PWA にプッシュ通知を追加する  

プッシュ通知をサポートする PWA を作成するには、次のタスクを実行します。  

1.  プッシュ API を使用してメッセージング サービスを [サブスクライブする][MDNPushApi]  
1.  通知 API を使用してサービスからメッセージを受信すると、トースト メッセージを [表示する][MDNNotificationsApi]  
    
Service Workers と同様に、プッシュ通知 API は標準ベースの API です。  プッシュ通知 API はブラウザー間で動作します。そのため、コードは、PWA がサポートされているあらゆる場所で動作する必要があります。  サーバー上の別のブラウザーにプッシュ メッセージを配信する方法の詳細については [、「Web-Push」に移動します][NPMWebPush]。  

次の手順は、Mozilla が提供する Service [Worker クック][ServiceWorkerCookbookPushRichDemo] ブックのプッシュ リッチ デモから適用されています。その他の便利な Web プッシュおよびサービス ワーカーのレシピが多数用意されています。  

### <a name="step-1---generate-vapid-keys"></a>手順 1 - VAPID キーを生成する  

PWA クライアントにプッシュ メッセージを送信するには、プッシュ通知に VAPID \(Voluntary Application Server IDENTIFICATION\) キーが必要です。  オンラインで使用可能な VAPID キー ジェネレーターは複数あります[][VapidkeysMain](たとえば、\vapidkeys.com)。  生成後、公開キーとプライベート キーを含む JSON オブジェクトを取得する必要があります。  次のチュートリアルの後の手順のキーを保存します。  VAPID と WebPush の詳細については、Mozilla Push Service を使用して識別された [WebPush 通知の送信に移動します][MozillaServicesSendingVapidWebPushNotificationsPush]。  

### <a name="step-2---subscribe-to-push-notifications"></a>手順 2 - プッシュ通知をサブスクライブする  

サービス ワーカーは、PWA でプッシュ イベントとトースト通知のやり取りを処理します。  PWA をサーバープッシュ通知にサブスクライブするには、次の条件を満たしてください。  

*   PWA がインストール、アクティブ、および登録されている  
*   サブスクリプション タスクを完了するコードは、PWA のメイン UI スレッド上にある  
*   ネットワーク接続がある  
    
新しいプッシュ サブスクリプションを作成する前に、Microsoft Edge は、ユーザーが PWA に通知を受信するアクセス許可を与えたか確認します。  表示されない場合は、ブラウザーからアクセス許可を求めるメッセージが表示されます。  アクセス許可が拒否された場合、処理する必要 `registration.pushManager.subscribe` がある `DOMException` 、 をスローする要求。  アクセス許可の管理の詳細については [、Microsoft Edge の [プッシュ通知] に移動します][WindowsBlogsWebNotificationsEdge]。  

ファイルで `pwabuilder-sw-register.js` 、次のコード スニペットを追加します。  

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

詳細については [、「PushManager」][MDNPushManager] および [「Web-Push」に移動します][NPMWebPushUsage]。  

### <a name="step-3---listen-for-push-notifications"></a>手順 3 - プッシュ通知をリッスンする  

PWA でサブスクリプションを作成したら、プッシュ イベントに応答するハンドラーをサービス ワーカーに追加します。  プッシュ イベントは、トースト通知を表示するためにサーバーから送信されます。  トースト通知には、受信したメッセージのデータが表示されます。  次のタスクを完了するには、ハンドラーを追加する必要 `click` があります。  

*   トースト通知を閉じる  
*   開いているウィンドウを開く、フォーカスする、または開く、フォーカスする  
*   PWA クライアント ページを表示する新しいウィンドウを開いてフォーカスする  
    
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

### <a name="step-4---try-it-out"></a>手順 4 - 試してみる  

PWA のプッシュ通知をテストするには、次の手順を実行します。  

1.  PWA に移動します `http://localhost:3000` 。  サービス ワーカーが PWA をアクティブ化してプッシュ通知にサブスクライブしようとすると、PWA に通知の表示を許可するように求めるメッセージが表示されます。  [許可 **] を選択します**。  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="通知を有効にするアクセス許可ダイアログ" lightbox="./media/notification-permission.png":::
       通知を有効にするアクセス許可ダイアログ  
    :::image-end:::  
    
1.  サーバー側のプッシュ通知をシミュレートします。  ブラウザーで PWA を開 `http://localhost:3000` いた後、選択 `F12` して DevTools を開きます。  [**アプリケーション**  >  **サービス ワーカー プッシュ]**  >  **を選択**して、PWA にテスト プッシュ通知を送信します。  
    
    :::row:::
       :::column span="":::
          プッシュ通知がタスク バーの近くに表示されます。  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="DevTools から通知をプッシュする" lightbox="./media/devtools-push.png":::
             DevTools から通知をプッシュする  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          トースト通知を \(または activate\) を選択しない場合、システムは数秒後に自動的に通知を却下し、Windows アクション センターにキューに入れられます。  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows アクション センターの通知" lightbox="./media/windows-action-center.png":::
             Windows アクション センターの通知  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="next-steps"></a>次の手順  

次の手順には、実際の PWA の構築を理解するのに役立つ追加のタスクが含まれています。  

*   プッシュ サブスクリプションの管理と保存  
*   [ペイロード データ][NPMWebPushEncrypt] の暗号化  
*   レスポンシブ デザイン  
*   ディープリンク  
*   [ブラウザー間のテスト][BrowserStackTestEdgeBrowser]  
*   Webhint などの検証と [テストのプラクティスを実装する][Webhint]  
    
## <a name="see-also"></a>関連項目  

*   [MDN Web ドキュメントのプログレッシブ Web アプリ][MDNProgressiveWebApps]  
*   [プログレッシブ Web Apps on web.dev][WebDevProgressiveWebApps]  
*   [プログレッシブ Web アプリとしてのハッカー][HackerNewsProgressiveWebApps] ニュース リーダー - サンプル \(Hacker News reader\) PWA を実装するためのさまざまなフレームワークとパフォーマンス パターンを比較します。  
*   [ミス バトリング PWA][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [プログレッシブ Web アプリのプログレッシブ ロードマップ][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [プログレッシブ Web アプリを使用したオフライン POST][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA Q&A][AaronGustafsonNotebookPwaQa]  
*   [Web でのベット][JoretegBlogBettingWeb]  
*   [プログレッシブ Web アプリの名前付け][Fberriman20170626NamingProgressiveWebApps]  
*   [フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 1)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 2)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 3)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  

<!-- links -->  

<!--[ArchiveMicrosoftEdgeLegacyDeveloperPWAsIndexRequirements]: /archive/microsoft-edge/legacy/developer/progressive-web-apps/index#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "コード コード Node.jsを使用して Azure にアプリをVisual Studioする|Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントを作成|Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web Apps |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge の Web 通知 |Windows ブログ"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio Code"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA Q&A"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 サーバーでの Microsoft Edge ブラウザーの無料|BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "プログレッシブ Web アプリのプログレッシブ ロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "ミス バスターリング PWA – 新しいエッジ エディション"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express アプリケーション ジェネレーター |Express" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "プログレッシブ Web アプリの名前付け"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "プログレッシブ Web アプリとしてのハッカー ニュース リーダー"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web でのベット"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "プログレッシブ Web アプリ \(PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービス ワーカー の使用|MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "プログレッシブ Web アプリを使用したオフライン POST"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "VAPID を送信すると、Mozilla のプッシュ サービス サービス経由で WebPush 通知が識別|Mozilla Services"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-push |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt(userPublicKey, userAuth, payload, contentEncoding) - web プッシュ |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用法 - Web プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "プログレッシブ Web アプリ"  

[PwaBuilder]: https://www.pwabuilder.com "PWA ビルダー"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "Service Worker |PWA ビルダー"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "Push Rich Demo |ServiceWorker クックブック"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 1)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 3)"  

[VapidkeysMain]: https://vapidkeys.com "Secure VAPID Key Generator |VapidKeys" 

[Webhint]: https://webhint.io "webhint"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "プログレッシブ Web アプリ |web.dev"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "プログレッシブ拡張|Wikipedia"  
