---
description: このガイドでは、Windows でプログレッシブ web アプリを構築するための PWA の基本とツールの概要について説明します。
title: プログレッシブ Web アプリの使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、PWABuilder、web マニフェスト、サービスワーカー、プッシュ
ms.openlocfilehash: 84d7c753cfece1591348e06b6728939187e37482
ms.sourcegitcommit: ef6d6adae1f4d18a219fa3e17f91b95b40367a40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934906"
---
# プログレッシブ Web アプリの使用を開始する  

プログレッシブ Web アプリ \ (PWAs \) は、ホーム画面のインストール、オフラインサポート、プッシュ通知などのプラットフォームやブラウザーエンジンでのネイティブアプリのような機能によって [段階的に強化][WikiProgressiveEnhancement] された web アプリです。  Microsoft Edge \ (EdgeHTML \) エンジンを搭載した Windows 10 では、ブラウザーウィンドウを [ユニバーサル Windows プラットフォーム][WindowsUwpGetStartedWhat] アプリとして実行することによって、pwas の機能が追加されました。  

このガイドでは、 `localhost` Microsoft Visual Studio といくつかの Pwa ビルダーユーティリティを使って、pwa としてシンプルな web アプリを作成することによって、pwa の基本的な概要を説明します。  完成した製品は、PWAs をサポートするすべてのブラウザーで同様に動作します。  

> [!TIP]
> 既存のサイトを PWA に変換して、Windows 10 およびその他のアプリプラットフォーム用にパッケージ化する簡単な方法については、「 [Pwa ビルダー][PwaBuilder]」を参照してください。  

## 前提条件  

PWAs は、どの web 開発 IDE でも構築できます。  次に示すのは、Windows 開発者エコシステムでの PWA ツールのサポートについて説明する、このガイドの前提条件のみです。  

*   \ (無料版) の [Visual Studio コミュニティ 2017][VisualStudioDownloads]をダウンロードします。  プロフェッショナル、エンタープライズ、または [プレビュー][VisualStudioPreview] の各エディションを使用することもできます。  Visual Studio インストーラーで、次のワークロードを選択します。  
    
    *   **ユニバーサル Windows プラットフォーム開発**  
    *   **Node.js 開発**  

## 基本的な web アプリをセットアップする  

わかりやすくするために、Visual Studio [Node.js とエクスプレスアプリ][VisualStudioNodeJsTutorial] テンプレートを使用して、ページを構成する web アプリを作成し `localhost` `index.html` ます。  これは、PWA として開発する、魅力的で多機能なフル機能の web アプリのプレースホルダーとして考えることができます。  

1.  Visual Studio を起動し、新しいプロジェクトを開始します。  
    *   **ファイル**  > **新規**  > **プロジェクト**  
    *   `Ctrl`+`Shift`+`N`  
1.  [ **JavaScript**] で、[ **Basic Node.js Express 4 アプリケーション**] を選びます。  名前と場所を設定して、 **[OK]** を選択します。  
    
    ![Visual Studio で Node.js Express 4 プロジェクトテンプレートを選択する][ImageVsNodejsExpressTemplate]  
    
1.  新しいプロジェクトが読み込まれたら、[**ビルド**\ (\)] を選択 `Ctrl` + `Shift` + `B` して、「(\) の**デバッグを開始**し `F5` ます。  参照するときにファイルが読み込まれることを確認し `index.html` `http://localhost:1337` ます。  
    
    ![新しいサイトを localhost で実行する][ImageVsNodejsExpressIndex]  

## アプリを PWA にする  

ここで、web アプリの基本的な [PWA 要件][PwaEdgehtmlIndexRequirements] ( *web アプリマニフェスト*、 *HTTPS* 、 *サービスワーカー*) を作成します。  

### Web アプリマニフェスト  

[Web アプリマニフェスト][MDNWebAppManifest]は、アプリについて説明する JSON メタデータファイルです。名前、作成者、エントリページの URL、1つまたは複数のアイコンが含まれます。  [標準ベースのスキーマ][W3cWebAppManifest]に従っているため、pcl がサポートされているプラットフォーム、OS、およびデバイスの組み合わせにインストールする1つの web アプリマニフェストのみを提供する必要があります。  Windows エコシステムでは、自分の PWA が [Microsoft Store][PwaEdgehtmlMicrosoftStore]に自動追加の候補として表示されるように、web アプリマニフェストが Bing web インデクサーに通知されます。ここでは、windows 10 アプリとして、約7億のアクティブなユーザーにアクセスできます。  

既存のライブサイトの場合は、 [PWA ビルダー][PwaBuilder]を使って web アプリマニフェストを生成できます。  まだ未公開のプロジェクトであるため、サンプルマニフェストをコピーしてください。  

1.  Visual Studio*ソリューションエクスプローラー*で、*パブリック*フォルダーを右クリックし、[新しいファイルの**追加**...] を選択し  >  **New File...** `manifest.json` て、項目名として指定します。  
1.  ファイルで `manifest.json` 、次のコードをコピーします。  

    ```json
    {
        "dir": "ltr",
        "lang": "en-us",
        "name": "My Sample PWA",
        "scope": "/",
        "display": "browser",
        "start_url": "https://PLACEHOLDER-FOR-PWA-URL",
        "short_name": "SamplePWA",
        "theme_color": "transparent",
        "description": "A sample PWA for testing purposes",
        "orientation": "any",
        "background_color": "transparent",
        "related_applications": [],
        "prefer_related_applications": false,
        "icons": []
    }
    ```  
    
    実際の PWA では、次の手順では、 *名前*、 *start_url*、 *short_name*、 *説明*、 *アイコン* をカスタマイズします (アイコンについては、次の手順で説明します)。  
    
    さまざまなメンバー値と関連の目的について詳しくは、「 [Web アプリマニフェスト][MDNWebAppManifest] のリファレンス」をご覧ください。  
    
1.  次に、 `icons` PWA ビルダーアプリのイメージジェネレーターを使って、空の配列に実際の画像パスを入力します。  
    
    1.  Web ブラウザーを使用して、次の [サンプル 512x512 PWA イメージ][ImagePwa]をダウンロードします。  
    1.  PWA ビルダー [アプリのイメージジェネレーター][PwaBuilderAppImageGenerator]に移動し `pwa.png` て、 **入力イメージ** として保存した画像を選択し、[ **ダウンロード** ] ボタンを選択します。  
    1.  Zip ファイルを**開い**て**抽出**します。  
    1.  Visual Studio ソリューションエクスプローラーで、フォルダーを右クリック `public` し、 **エクスプローラーでフォルダーを開き**ます。  という名前の **新しいフォルダー** を作成 `images` します。  
    1.  抽出した zip からフォルダーにすべてのプラットフォームフォルダー \ (、など) をコピーして、[ `android` `chrome` `windows10` `images` ファイルエクスプローラー] ウィンドウを閉じます。  フォルダーを Visual Studio プロジェクトに追加します (ソリューションエクスプローラーで、フォルダーを右クリックし、 `images` [既存のフォルダーの**追加**] を選択します  >  **Existing folder...** )。  
    1.  抽出した zip からファイルを (Visual Studio または任意のエディターを使って) 開いて、 `icons.json` `"icons": [...]` プロジェクトのファイルに配列をコピーし `manifest.json` ます。  

1.  これで、web アプリマニフェストをアプリに関連付ける必要があります。  `layout.pug`ファイル \ ( `views` フォルダー \) を編集用に開き、[スタイルシート] リンクの直後にこの行を追加します。  \ (単なるノード [pug][PugAttributes] テンプレート略記 `<link rel='manifest' href='/manifest.json'>` )。  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
これまでと同じように、web アプリが、マニフェストとホーム画面対応のアプリのアイコンを提供しています。  アプリ \ ( `F5` \) を実行して、マニフェストを読み込みます。  

![Localhost からの Web アプリマニフェストの読み込み][ImageVsNodejsExpressManifest]  

アイコンの1つを選びます。  

![Localhost からの Square71x71Logo アプリロゴの読み込み][ImageVsNodejsExpressIcon]  

(実際の \) アプリを公開している場合 `start_url` 、Bing 検索エンジンは、インストール可能な Windows 10 アプリとして [Microsoft Store への自動パッケージと申請][PwaEdgehtmlMicrosoftStore] の候補として識別されるようになりました。  ファイルの manifest.jsには、次の項目を含む Bing スキャン用の [プログレッシブ Web アプリの品質シグナル][WindowsBlogsPwaEdge] が含まれていることを確認します。   

*   `name`  
*   `description`  
*   少なくとも1つのアイコン (512 px 四方以上) \ (アプリのスプラッシュ画面を自動生成するための十分な解像度の画像ソース、ストア登録情報、タイル画像など)。  

さらに、 [HTTPS](#https)、 [サービス員](#service-workers)、 [Microsoft ストアのポリシー][LegalWindowsAgrementsMicrosoftStorePolicies]に準拠することもできます。  

### HTTPS  

[サービスワーカーと、][MDNServiceWorkerApi] service Worker ( [キャッシュ][MDNCache]、 [プッシュ][MDNPushApi]、 [バックグラウンド同期][MDNSyncManager] api など) で動作する PWA テクノロジはセキュリティで保護された接続にのみ機能します。これは、ライブサイトまたはデバッグ目的で [HTTPS][WikiHttps] を意味 `localhost` します。  

[この web アプリを実際のサイトとして発行][VisualStudioNodejsTutorialPublishAzureAppService]する場合 (たとえば、 [Azure free アカウント][AzureCreateFreeAccount]をセットアップした場合) は、サーバーが HTTPS 用に構成されていることを確認する必要があります。  [Microsoft Azure App Service][AzureWebApps]を使ってサイトをホストしている場合、既定では HTTPS 経由で提供されます。  

このガイドでは、稼働中の `http://localhost` ライブサイトのプレースホルダーとして引き続き使用 `https://` します。  

### サービス ワーカー  

サービスワーカーは、PWAs の主要テクノロジです。 サービスワーカーは、PWA とネットワークの間のプロキシとして機能し、web サイトが、オフラインシナリオを処理し、サーバープッシュ通知に応答し、バックグラウンドタスクを実行するインストール済みのネイティブアプリとして機能することを可能にします。  サービス担当者には、新しいパフォーマンス戦略も開かれます。  Web サイトのページ読み込みパフォーマンスを微調整するために、サービスワーカーキャッシュを使用するために、完全な web アプリを実装する必要はありません。  

サービスワーカーは、web アプリを起動する通常のスクリプトと共に対応する JavaScript ファイルから実行されるイベント駆動型のバックグラウンドスレッドです。  サービスワーカーはメイン UI スレッドでは実行されないため、 [ui スレッド][MDNWorkerPrototypePostMessage] と [ワーカースレッド][MDNDedicatedWorkerGlobalScopePostMessage] は、 `postMessage()` およびイベントハンドラーを使って通信できますが、その場合、サービスワーカーには DOM アクセスはありません `onmessage` 。  

サービスワーカーを、サイトの URL の起点 (またはその中の指定したパス) に登録することで、アプリに関連付けます。  登録が完了すると、service worker ファイルが、ユーザーのコンピューターにダウンロード、インストール、アクティブ化されます。  さらに、MDN web ドキュメントには、 [サービスワーカー][MDNUsingServiceWorkers] と詳細な [service worker API][MDNServiceWorkerApi] リファレンスの包括的なガイドが含まれています。  

このチュートリアルでは、 [PWA ビルダー][PwaBuilderServiceWorker]でオフラインページサービスワーカースクリプトを使用します。  パフォーマンス要件、ネットワーク帯域幅などに応じて、より多くの機能を備えたスクリプトをカスタマイズします。  Mozilla が提供する [サービス][ServiceWorkerCookbook]  の担当者を確認して、いくつかの便利なサービス作業者のキャッシュアイデアを確認してください。  

1.  [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker]\ (既定の)**オフラインページ**サービスワーカーを開いて選択し、[**サービスワーカーのダウンロード**] ボタンをクリックします。  
1.  [ダウンロード] フォルダーを開いて、次の2つのファイルをコピーします。  

    *   ServiceWorker1\pwabuilder-sw-register.js  
    *   ServiceWorker1\pwabuilder-sw.js  
    
    `public`Visual Studio web app プロジェクトのフォルダーにファイルを保存します。  \ (Visual Studio から、エクスプローラーを使っ `Ctrl` + `O` てプロジェクトを開き、フォルダーに移動し `public` ます)。  
    
    ソリューションエクスプローラーで、 `public/pwabuilder-sw.js` ファイルを開き、の値 `offlineFallbackPage` をに変更し `offline.html` ます。  
    
    ```javascript
    const offlineFallbackPage = "offline.html";
    ```
    
    この2つのファイルの両方のコードを確認して、指定したページをキャッシュし、ネットワークの取得に失敗したときにそのサービスを提供するサービスワーカーを登録する方法について説明し `offline.html` ます。  次に、 `offline.html` アプリのオフライン機能のプレースホルダーとして簡単なページを作成します。  
    
1.  ソリューションエクスプローラーで、 `views/layout.pug` ファイルを開き、リンクタグの下に次の行を追加します。  
    
    ```html
    script(src='/pwabuilder-sw-register.js' type='module')
    ```  
    
    サイトがサービスワーカー登録スクリプトを読み込んで実行します。  
    
1.  ソリューションエクスプローラーで、フォルダーを右クリックし、 `public` [ **Add**  >  **新しいファイル**の追加...] を選択します。 次のコードのように、その名前を入力し、 `offline.html` `<title>` 本文の内容をいくつか追加します。  
    
    ```html
    <!DOCTYPE html>
    
    <html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title>Offline mode</title>
    </head>
    <body>
        You are now offline.
    </body>
    </html>
    ```  
    
    この時点で、フォルダーには `public` 3 つの新しいファイルが含まれている必要があります。  
    
    ![ソリューションのパブリックフォルダーに追加されたファイル][ImageVsNodejsExpressPublic]  
    
1.  ソリューションエクスプローラーで、 `routes\index.js` ファイルを開き、最後のコマンド \ (\) の直前に次のコードを追加し `module.exports = router;` ます。  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    これにより、アプリは `offline.html` (サービスワーカーがオフラインキャッシュ用にファイルを取得するときに) ファイルを提供するように指示されます。  
    
1.  PWA をテストする  `Ctrl` + `Shift` + `B` Microsoft Edge を起動してページを開くには、\ (\) をビルドし、 `F5` web アプリを実行し `localhost` ます。  次に、次の手順を実行します。  
    
    1.  Edge devtools**コンソール**\ ( `Ctrl` + `Shift` + `J` \) を開き、サービスワーカーが登録されていることを確認します。  
    1.  **デバッガ**パネルで、[ **Service worker** ] コントロールを展開し、原点をクリックします。  **サービスワーカーの概要**で、サービスワーカーがアクティブ化され、実行されていることを確認します。  
        
        ![Edge DevTools サービスワーカーの概要][ImageDevtoolsSwOverview]  
        
    1.  **キャッシュ**コントロールを展開して、 `offline.html` ページがキャッシュされていることを確認します。  
        
        ![Edge DevTools サービスワーカーキャッシュ][ImageDevtoolsSwCache]  
        
1.  PWA をオフラインアプリとして試す時間  Visual Studio で、web アプリの**デバッグを停止** `Shift` + `F5` して、Microsoft Edge \ (または [更新]) を web サイトの localhost アドレスに開きます。  これでページを読み込むことが `offline.html` できます (サービスワーカーとオフラインキャッシュに感謝します)。  
    
    ![http://localhost:1337Microsoft Edge で offline.html を読み込む][ImageOfflineHtml]  

## プッシュ通知を追加する  

PWA をさらにアプリにするには、 [プッシュ API][MDNPushApi] を使ってメッセージサービスをサブスクライブするプッシュ通知のクライアント側サポートを追加し、 [通知 API][MDNNotificationsApi] を使ってメッセージの受信時にトーストメッセージを表示します。  サービスワーカーの場合と同様に、これらはブラウザー間で動作する標準ベースの Api であるため、コードを1回記述するだけで、すべての機能がサポートされます。  サーバー側で、 [Web プッシュ][NPMWebPush] ソースライブラリを使って、さまざまなブラウザーへのプッシュメッセージの配信に関連する違いを処理します。  

以下は、Mozilla が提供する [Service Worker][ServiceWorkerCookbookPushRichDemo] のレシピのプッシュリッチデモに適用されています。これは、その他多くの便利な Web プッシュとサービス worker のレシピを確認するのに役立ちます。  

### 手順 1-NPM web プッシュライブラリをインストールする  

Visual Studio ソリューションエクスプローラーで、プロジェクトを右クリックし **Node.js 対話型のウィンドウを開く]** をクリックします。 次のコードを入力します。  

```javascript
.npm install web-push
```  

これに [より、Web プッシュ][NPMWebPush] ライブラリがインストールされます。  次に、 `index.js` ファイルを開き、他の要件ステートメントの後に、ファイルの先頭に次の行を追加します。  

```javascript
var webpush = require('web-push');
```  

### 手順 2-サーバーの VAPID キーを生成する  

次に、プッシュメッセージを PWA クライアントに送信するために、サーバーに対して VAPID を生成する必要があります。  この操作は1回だけ実行する必要があります (つまり、サーバーでは VAPID keys の1つのペアしか必要ありません)。  対話型の Node.js ウィンドウで、次のコードを入力します。  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

出力結果として、公開キーと秘密キーを含む JSON オブジェクトが作成され、サーバーロジックにコピーされます。  

ファイルの `index.js` 最終 \ (\) の直前に、 `module.exports = router` 次のコードを追加します。  

```javascript
const vapidKeys = {
    publicKey: '',
    privateKey: ''
};

webpush.setVapidDetails(
    'mailto:pwa@example.com',
    vapidKeys.publicKey,
    vapidKeys.privateKey
);
```  

`publicKey`生成した and 値をコピーし `privateKey` ます。  アドレスは自由にカスタマイズでき `mailto` ます (ただし、このサンプルを実行するためには必須ではありません)。  

[Mozilla サービスエンジニアリングのブログ][MozillaServicesSendingVapidWebPushNotificationsPush]では、バックグラウンドでの機能について詳しく知りたい場合は、VAPID と webpush の優れた explainer をご利用ください。  

### 手順 3-プッシュ関連のサーバー要求を処理する  

それでは、VAPID 公開キーの提供、プッシュを受け取るクライアントの登録など、PWA クライアントからプッシュ関連の要求を処理するためのルートをセットアップします。  

実際のシナリオでは、プッシュ通知はサーバーロジックのイベントから発生する可能性があります。  ここで簡単にするために、PWA のホームページに **プッシュ通知** ボタンを追加して、skype のサーバーからプッシュを生成したり、 `/sendNotification` これらの要求を処理するためのエンドポイント \ (サーバールート) を作成したりする必要があります。  

ファイル内に `index.js` 、追加した VAPID 初期化コードの直後に、[手順 2 #step] から [---の VAPID キーを生成します] の後に次のルートを追加します。  

```javascript
router.get('/vapidPublicKey', function (req, res) {
    res.send(vapidKeys.publicKey);
});

router.post('/register', function (req, res) {
    // A real world application stores the subscription info.
    res.sendStatus(201);
});

router.post('/sendNotification', function (req, res) {
    const subscription = req.body.subscription;
    const payload = 'payload';
    const options = null;
    
    webpush.sendNotification(subscription, payload, options)
        .then(function () {
            res.sendStatus(201);
        })
        .catch(function (error) {
            res.sendStatus(500);
            console.log(error);
        });
});
```  

サーバー側のコードが配置されている場合は、PWA クライアントでプッシュ通知を plumb します。  

### 手順 4-プッシュ通知への登録  

サービスワーカーは PWA ネットワークプロキシとしての役割の一部として、プッシュイベントとトースト通知操作を処理します。  ただし、初めて (または \ を登録する) サービスワーカーを設定するときに、PWA のプッシュ通知が pwa のメイン UI スレッドで行われ、ネットワーク接続が必要になります。  プッシュ通知をサブスクライブするには、アクティブなサービスワーカーの登録が必要であるため、まずサービスワーカーがインストールされてアクティブであることを確認してから、プッシュ通知にサブスクライブしてください。  

新しいプッシュサブスクリプションが作成される前に、Microsoft Edge では、ユーザーが通知を受信できるように PWA 権限を付与しているかどうかを確認します。  許可されていない場合は、ブラウザーからアクセス許可を求められます。  アクセス許可が拒否された場合は、a を例外とし `registration.pushManager.subscribe` `DOMException` て処理する必要があります。  権限の管理について詳しくは、「 [Microsoft Edge でのプッシュ通知][WindowsBlogsWebNotificationsEdge]」をご覧ください。  

ファイルに `pwabuilder-sw-register.js` 次のコードを追加します。  

```javascript
// Subscribe this PWA to push notifications from the server
navigator.serviceWorker.ready
    .then(function (registration) {
        // Check if the user has an existing subscription
        return registration.pushManager.getSubscription()
            .then(async function (subscription) {
                if (subscription) {
                    return subscription;
                }
                
                // Otherwise subscribe with the server public key
                const response = await fetch('./vapidPublicKey');
                const vapidPublicKey = await response.text();
                const convertedVapidKey = urlBase64ToUint8Array(vapidPublicKey);
                
                return registration.pushManager.subscribe({
                    userVisibleOnly: true,
                    applicationServerKey: convertedVapidKey
                });
            });
    }).then(function (subscription) {
        // Send the subscription details to the server
        fetch('./register', {
            method: 'post',
            headers: {
                'Content-type': 'application/json'
            },
            body: JSON.stringify({
                subscription: subscription
            }),
        });
        
        // Create a button to mimic server pushes for testing purposes
        var button = document.createElement('input');
        button.type = 'button';
        button.id = 'notify';
        button.value = 'Send Notification';
        document.body.appendChild(button);
        document.getElementById('notify').addEventListener('click', function () {
            fetch('./sendNotification', {
                method: 'post',
                headers: {
                    'Content-type': 'application/json'
                },
                body: JSON.stringify({
                    subscription: subscription
                }),
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

Api のしくみおよび関連するさまざまなオプションの詳細については、 [「][NPMWebPushUsage] office online ライブラリの[pushmanager][MDNPushManager]インターフェイスと NPM ドキュメント」の MDN ドキュメントを確認してください。  

### 手順 5-プッシュと notificationclick クリックイベントハンドラーを設定する  

プッシュサブスクリプションを設定すると、残りの作業はサービスワーカーで行われます。  最初に、プッシュデータペイロードを表示する、サーバー側で送信されたプッシュイベントのハンドラーを設定して、トースト通知によって応答します (権限が付与されている場合)。  次に、トーストのクリックハンドラーを追加して通知を消去し、現在開いているウィンドウの一覧を並べ替えて、意図した PWA クライアントページを開き、フォーカスして、フォーカスを移動します。  

ファイルで `pwabuilder-sw.js` 、次のハンドラーを追加します。  

```javascript
//Respond to a server push with a user notification
self.addEventListener('push', function (event) {
    if ("granted" === Notification.permission) {
        var payload = event.data ? event.data.text() : 'no payload';
        const promiseChain = self.registration.showNotification('Sample PWA', {
            body: payload,
            icon: 'images/windows10/Square44x44Logo.scale-100.png'
        });
        //Ensure the toast notification is displayed before exiting this function
        event.waitUntil(promiseChain);
    }
});
    
//Respond to the user clicking the toast notification
self.addEventListener('notificationclick', function (event) {
    console.log('On notification click: ', event.notification.tag);
    event.notification.close();
    
    // This looks to see if the current is already open and focuses it
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

### 手順 6-お試しください  

PWA でプッシュ通知をテストする時間  

1.  `F5`ブラウザーで PWA (\) を実行します。  サービスワーカーコード \ (\) を変更したので `pwabuilder-sw.js` 、DevTools デバッガー \ ( `F12` \) を **サービスワーカーの概要** パネルに開いて、サービスワーカーの **登録を解除** し `F5` 、ページを再登録する必要があります (または、[ **更新**] をクリックします)。  運用シナリオでは、ブラウザーは、service worker の更新プログラムが定期的にチェックされ、バックグラウンドで更新プログラムをインストールすることを確認します。  すぐに結果が得られるように、ここで強制する必要があります。  
    
    サービスワーカーがアクティブ化して PWA のプッシュ通知をサブスクライブしようとすると、ページの下部に [アクセス許可] ダイアログが表示されます。  
    
    ![通知を有効にするためのアクセス許可ダイアログ][ImageNotificationPermission]  
    
    **[はい]** を選択して、PWA のトースト通知を有効にします。  
    
1.  [Service Worker の概要] ウィンドウで、[  **プッシュ** ] ボタンを選択します。  \ (DevTools "\) ペイロードからのハードコード付きの" テストプッシュメッセージ "というトースト通知が表示されます。  
    
    ![DevTools から通知をプッシュする][ImageDevtoolsPush]  
    
1.  次に、PWA のホームページで [ **通知の送信** ] ボタンを選択します。  今回は、サーバーからのペイロードを使ってトーストが表示されます。  
    
    ![PWA サーバーから通知をプッシュする][ImagePwaPush]  
    
    トースト通知をオンにしない場合は、数秒後に非表示になり、Windows アクションセンターでキューに入れられます。  
    
    ![Windows アクションセンターでの通知][ImageWindowsActionCenter]  
    
    PWA プッシュ通知の基本的な機能があります。  実際のアプリでは、次の手順は、プッシュサブスクリプションを管理および保存し、ネットワーク経由で送信されるペイロードデータを適切に [暗号化][NPMWebPushEncrypt] する方法で実装されています。  
    
## 追加情報  

このガイドでは、Visual Studio、PWA ビルダー、Edge DevTools などのプログレッシブ Web アプリと Microsoft PWA 開発ツールの基本的な構造について説明します。  

もちろん、お客様には、応答性の高いデザイン、ディープリンク、[クロスブラウザーテスト][BrowserStackTestEdgeBrowser]などの[ベストプラクティス][Webhint](アプリの機能については説明しません) を含めて、ここで紹介した機能以外にも[pwa][PwaEdgehtmlIndexRequirements]を追加する必要があります。このガイドでは、pwa の基本的な概要と作業開始について説明します。  Windows または Visual Studio での PWA 開発についてさらに質問がある場合は、コメントを残してください。  

他の PWA ガイドを確認して、カスタマーエンゲージメントを向上させ、OS に統合されたアプリのエクスペリエンスをさらに向上させる方法について説明します。  

*   [Windows の調整][PwaEdgehtmlWindowsFeatures]。 簡単な機能の検出を使用すると、windows 10 ユーザー向けの PWA (Windows の [ **スタート** ] メニューのタイル通知とタスクバーの jumplists をカスタマイズするための方法、および \ (許可されている場合)、写真、音楽、予定表などのユーザーリソースの操作などの、windows 10 を実行しているユーザーを段階的に強化できます。  
*   [Microsoft ストアで Pwas][PwaEdgehtmlMicrosoftStore]。  アプリストアの配布の利点と PWA の提出方法について説明します。  

## 関連項目  

*   [MDN web ドキュメントのプログレッシブ Web アプリ][MDNProgressiveWebApps] -プログレッシブ web アプリに関する優れたガイドです。  
*   プログレッシブ web アプリ向けの[プログレッシブ][WebDevProgressiveWebApps]web アプリ。プログレッシブ web アプリでの優れたガイドです。  
*   [プログレッシブ Web アプリ][ProgressiveWebApps] は、pwas の現実世界の例を示しています。  
*   [[プログレッシブ Web アプリとしてのハッカーニュースリーダー][HackerNewsProgressiveWebApps] ]: サンプル \ (ハッカーたち News READER) PWA を実装するためのさまざまなフレームワークとパフォーマンスパターンを比較します。  

<!-- image links -->  

[ImageDevtoolsPush]: ./media/devtools-push.png  
[ImageDevtoolsSwCache]: ./media/devtools-cache.png  
[ImageDevtoolsSwOverview]: ./media/devtools-sw-overview.png  
[ImageNotificationPermission]: ./media/notification-permission.png  
[ImageOfflineHtml]: ./media/offline-html.png  
[ImagePwa]: ./media/pwa.png  
[ImagePwaPush]: ./media/pwa-push.png  
[ImageVsNodejsExpressIcon]: ./media/vs-nodejs-express-icon.png  
[ImageVsNodejsExpressIndex]: ./media/vs-nodejs-express-index.png  
[ImageVsNodejsExpressManifest]: ./media/vs-nodejs-express-manifest.png  
[ImageVsNodejsExpressPublic]: ./media/vs-nodejs-express-public.png  
[ImageVsNodejsExpressTemplate]: ./media/vs-nodejs-express-template.png  
[ImageWindowsActionCenter]: ./media/windows-action-center.png  

<!-- links -->  

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "要件-プログレッシブ Web アプリ \ (EdgeHTML) Windows"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store でのプログレッシブ Web アプリ \ (EdgeHTML)"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps-edgehtml/windows-features.md "Windows 用の PWA \ (EdgeHTML) をカスタマイズする"  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store のポリシー |Microsoft ドキュメント"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "チュートリアル: Visual Studio で Node.js と Express アプリを作成する |Microsoft ドキュメント"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "Azure App Service に発行する-Visual Studio で Node.js と Express App を作成する |Microsoft ドキュメント"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか? |Microsoft ドキュメント"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントの作成 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "Microsoft Edge と Windows 10 へのプログレッシブ Web アプリのウェルカム |Windows ブログ"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "ダウンロード |Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "無料の開発者向けソフトウェア & サービス |Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio Preview"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "プログレッシブ Web アプリとしてのハッカーニュースリーダー"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope postMessage \ (\) |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "プログレッシブ web アプリ \ (PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービスワーカーを使用する |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "PostMessage \ (\) |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "VAPID を Mozilla のプッシュサービス経由で識別された Web プッシュ通知を送信しています。 |Mozilla サービス"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-プッシュ |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "暗号化 (userPublicKey、Userpublickey、payload、contentEncoding)-web-プッシュ |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用状況-web-プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "プログレッシブ Web アプリ"  

[PugAttributes]: https://pugjs.org/language/attributes.html "属性 |Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA ビルダー"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "アプリのイメージジェネレーター"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービスワーカー |PWA ビルダー"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker の料理"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "充実したデモのプッシュ |ServiceWorker の料理"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web アプリマニフェスト |勧告"  

[Webhint]: https://sonarwhal.com "web ベストプラクティスのヒントエンジンの web ヒント" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Web ワーカーの使用" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "プログレッシブ Web アプリ |web.xml"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS |Wikipedia"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "プログレッシブエンハンスメント |Wikipedia"  
