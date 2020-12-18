---
description: このガイドでは、Windows で段階的な Web アプリを構築するための PWA の基本とツールの概要について説明します。
title: 段階的な Web アプリの使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 段階的な Web アプリ, PWA, Edge, Windows, PWABuilder, Web マニフェスト, サービス ワーカー, プッシュ
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9a76399616ab7645b82242b94dd4757b73b37f60
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234348"
---
# 段階的な Web アプリの使用を開始する  

段階的な Web アプリ \(PWA\) は[][WikiProgressiveEnhancement]、ホーム画面から起動するインストール、オフライン サポート、プッシュ通知など、サポート プラットフォームやブラウザー エンジン上のネイティブ アプリのような機能によって段階的に拡張される単純な Web アプリです。  Microsoft Edge \(EdgeHTML\) エンジンを搭載した Windows 10 では、PAS は、ユニバーサル [Windows][WindowsUwpGetStartedWhat] プラットフォーム アプリとしてブラウザー ウィンドウとは別に実行できるという利点があります。  

このガイドでは、Microsoft Visual Studio と一部の PWA Builder ユーティリティを使用して簡単な Web アプリを PWA として構築することで、PWA の基本の概要を `localhost` 説明します。  完成した製品は、PAS をサポートするブラウザーでも同様に動作します。  

> [!TIP]
> 既存のサイトを PWA に変換し、Windows 10 および他のアプリ プラットフォーム用にパッケージ化する簡単な方法については [、PWA Builder を確認してください][PwaBuilder]。  

## 前提条件  

WEB 開発 IDE を使用して PAS を構築できます。  以下は、Windows 開発者エコシステムでの PWA ツール サポートについて説明する、このガイドの前提条件に限定されます。  

*   コミュニティ [2017][VisualStudioDownloads]の \(free\) Visual Studioダウンロードします。  Professional エディション、Enterprise エディション、Preview エディション [を使用][VisualStudioPreview] する場合があります。  新しいVisual Studioから、次のワークロードを選択します。  
    
    *   **ユニバーサル Windows プラットフォーム開発**  
    *   **Node.js開発**  

## 基本的な Web アプリをセットアップする  

簡単にするために、Visual StudioNode.js [ および Express][VisualStudioNodeJsTutorial] アプリ テンプレートを使用して、ページを提供する Web アプリ `localhost` を作成 `index.html` します。  PWA として開発している魅力的でフル機能の Web アプリのプレースホルダーとして、これを想像してください。  

1.  新Visual Studioを起動し、新しいプロジェクトを開始します。  
    *   **ファイル**  > **新規**  > **Project...**  
    *   `Ctrl`+`Shift`+`N`  
1.  **[JavaScript] で、[** 基本] Node.js **Express 4 アプリケーション] を選択します**。  名前と場所を設定し **、[OK] を選択します**。  
    
    ![新しいNode.js Express 4 プロジェクト テンプレートを選択Visual Studio][ImageVsNodejsExpressTemplate]  
    
1.  新しいプロジェクトが読み込まれると、[**ビルド**\( \) ] と [ `Ctrl` + `Shift` + `B` **デバッグの開始**] \( `F5` \) を選択します。  参照するときにファイル `index.html` が読み込まれるのを確認します `http://localhost:1337` 。  
    
    ![localhost での新しいサイトの実行][ImageVsNodejsExpressIndex]  

## アプリを PWA に変換する  

次に、Web アプリの基本的な [PWA][PwaEdgehtmlIndexRequirements] 要件 *(Web アプリ*マニフェスト *、HTTPS、* サービス ワーカー) を *関連付ける必要があります*。  

### Web アプリ マニフェスト  

[Web App マニフェストは][MDNWebAppManifest]、名前、作成者、エントリ ページの URL、1 つ以上のアイコンなど、アプリを記述する JSON メタデータ ファイルです。  標準ベースのスキーマに[][W3cWebAppManifest]従うので、PWA をサポートするプラットフォーム、OS、デバイスの組み合わせにインストールする PWA の Web アプリ マニフェストを 1 つしか指定する必要があります。  Windows エコシステムでは、Web アプリ マニフェストが Bing Web インデクサーに対して、PWA が [Microsoft Store][PwaEdgehtmlMicrosoftStore]に自動的に含まれる候補として知らされます。この場合、Windows 10 アプリとしてアクティブな月次ユーザーは 7 億人近くに達する可能性があります。  

既存のライブ サイトの場合は、PWA Builder を使用して Web アプリ マニフェスト [を生成できます][PwaBuilder]。  まだ未発行のプロジェクトである場合は、サンプル マニフェストをコピーします。  

1.  ソリューション エクスプローラー Visual Studio、パブリック フォルダーを右クリックし**、[新しいファイル**** の追加**  >  **...]** を選択し、アイテム名 `manifest.json` として指定します。  
1.  ファイル内 `manifest.json` で、次のコードをコピーします。  

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
    
    実際の PWA では、次の手順では**、名前**、start_url、short_name、*説明*、アイコン*\(* アイコンは次の手順で説明します\) をカスタマイズします。 **  
    
    さまざまなメンバー値と関連する目的の詳細については、Web アプリ マニフェストの [リファレンスを参照][MDNWebAppManifest] してください。  
    
1.  次に、PWA Builder App Image Generator を使用して、空の配列に実際のイメージ `icons` パスを入力します。  
    
    1.  Web ブラウザーを使用して、このサンプル [512x512 PWA イメージをダウンロードします][ImagePwa]。  
    1.  PWA Builder[アプリ][PwaBuilderAppImageGenerator]イメージ ジェネレーターに移動し、入力イメージとして保存したイメージを選択し、[ダウンロード] `pwa.png` ボタン**を選択**します。 ****  
    1.  **zip** ファイル **を開** いて展開します。  
    1.  ソリューション エクスプローラー Visual Studioフォルダーを右クリックし、エクスプローラーでフォルダー `public` **を開きます**。  という名前の **新しいフォルダーを** 作成します `images` 。  
    1.  すべてのプラットフォーム フォルダー \( , など\) を展開した zip からフォルダーにコピーし、エクスプローラー `android` `chrome` `windows10` `images` ウィンドウを閉じます。  Visual Studio プロジェクト \(ソリューション エクスプローラーでフォルダーを右クリックし、[既存のフォルダーの追加] を選択します\) にフォルダーを `images` ****  >  **** 追加します。  
    1.  抽出された zip ファイルの \(Visual Studio エディター\) を開き、配列をプロジェクト `icons.json` `"icons": [...]` `manifest.json` のファイルにコピーします。  

1.  次に、Web アプリ マニフェストをアプリに関連付ける必要があります。  編集用に \(in folder\) ファイルを開き、スタイルシートのリンクの直後にこの行 `layout.pug` `views` を追加します。  \(\の簡単な Node [pug][PugAttributes] テンプレートの簡単な `<link rel='manifest' href='/manifest.json'>` 例です)。  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
これで、Web アプリはマニフェストとホーム画面対応のアプリ アイコンを提供する準備が整いました。  アプリ \( `F5` \) を実行し、マニフェストを読み込もうとします。  

![localhost からの Web アプリ マニフェストの読み込み][ImageVsNodejsExpressManifest]  

アイコンの 1 つ。  

![Square71x71Logo アプリロゴが localhost から読み込み中][ImageVsNodejsExpressIcon]  

アプリをライブ (実際の \) で公開すると、Bing 検索エンジンはアプリを自動パッケージ化し、インストール可能な Windows 10 アプリとして `start_url` [Microsoft Store][PwaEdgehtmlMicrosoftStore] に提出する候補として識別されます。  ファイル上のmanifest.js、Bing がスキャンする段階的 [な Web アプリ][WindowsBlogsPwaEdge] の品質シグナル (以下の項目を含む) が含まれる必要があります。   

*   `name`  
*   `description`  
*   少なくとも 1 つのアイコン 512px 正方形以上 \(アプリのスプラッシュ画面、ストア登録情報、タイル画像を自動生成するのに十分な解像度の画像ソースを確保するために\)。  

さらに[、HTTPS、サービス](#https)[ワーカーを使用](#service-workers)し[、Microsoft Store ポリシーに準拠します][LegalWindowsAgrementsMicrosoftStorePolicies]。  

### HTTPS  

[サービス][MDNServiceWorkerApi]ワーカーや、サービス ワーカー \(キャッシュ、プッシュ、バックグラウンド同期 API[][MDNCache]など) と一[][MDNSyncManager]緒に動作する他の主要な PWA テクノロジは、セキュリティで保護された接続 (ライブ サイトまたはデバッグ用の[HTTPS)][WikiHttps]でのみ動作します。 [][MDNPushApi] `localhost`  

この Web [アプリを][VisualStudioNodejsTutorialPublishAzureAppService] ライブ サイト \として公開する場合 ( [たとえば、Azure][AzureCreateFreeAccount]無料アカウント \を設定)、サーバーが HTTPS 用に構成されていることを確認する必要があります。  Microsoft Azure [App Service を使用して][AzureWebApps] サイトをホストする場合、既定では HTTPS 経由で提供されます。  

このガイドでは、引き続 `http://localhost` きライブ サイトのプレースホルダーとして使用してください `https://` 。  

### サービス ワーカー  

サービス ワーカーは、PAS の主要なテクノロジです。 サービス ワーカーは、PWA とネットワークの間のプロキシとして機能し、オフライン シナリオを処理し、サーバー プッシュ通知に応答し、バックグラウンド タスクを実行するインストール済みネイティブ アプリとして Web サイトを機能できます。  サービス ワーカーは、新しいパフォーマンス戦略も開始します。  Web サイトのページ読み込みパフォーマンスを微調整するために、サービス ワーカー キャッシュを使用するために完全な Web アプリを実装する必要はありません。  

サービス ワーカーは、Web アプリを起動する通常のスクリプトと共に提供される JavaScript ファイルから実行されるイベント駆動バックグラウンド スレッドです。  サービス ワーカーはメイン UI スレッドで実行されないので[、UI][MDNWorkerPrototypePostMessage]スレッドとワーカー スレッドはイベント ハンドラーを使用して[][MDNDedicatedWorkerGlobalScopePostMessage]通信することができますが、サービス ワーカーは DOM にアクセスできます `postMessage()` `onmessage` 。  

サービス ワーカーをアプリに関連付ける場合は、サイト \(またはサイト内の指定したパス) の URL の生成元に登録します。  登録すると、サービス ワーカー ファイルがユーザー コンピューターにダウンロードされ、インストールされ、アクティブ化されます。  さらに、MDN Web ドキュメントには、サービス[][MDNUsingServiceWorkers]ワーカーの使用に関する包括的なガイドと詳細なサービス ワーカー [API][MDNServiceWorkerApi]リファレンスがあります。  

このチュートリアルでは、PWA Builder のオフライン ページ [サービス ワーカー スクリプトを使用します][PwaBuilderServiceWorker]。  まず、パフォーマンス要件やネットワーク帯域幅など、より多くの機能を備え、スクリプトをカスタマイズします。  Mozilla [が提供する Service Worker Cookbook][ServiceWorkerCookbook]  で、便利なサービス ワーカー キャッシュに関する多くのアイデアを確認します。  

1.  \(default\) オフライン ページ サービス ワーカーを開いて選択し、[サービス ワーカーのダウンロード [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] **] ボタンをクリック**します。 ****  
1.  ダウンロード フォルダーを開き、次の 2 つのファイルをコピーします。  

    *   ServiceWorker1\pwabuilder-sw-register.js  
    *   ServiceWorker1\pwabuilder-sw.js  
    
    ファイルを Web アプリ `public` プロジェクトのフォルダー Visual Studio保存します。  \(ファイルVisual Studioエクスプローラーを開き、フォルダーに移動 `Ctrl` + `O` `public` するために使用します。)  
    
    ソリューション エクスプローラーでファイルを `public/pwabuilder-sw.js` 開き、次の値を変更 `offlineFallbackPage` します `offline.html` 。  
    
    ```javascript
    const offlineFallbackPage = "offline.html";
    ```
    
    これらのファイルの両方のコードを確認して、指定されたページ \( \) をキャッシュし、ネットワーク フェッチが失敗した場合にサービス ワーカーを提供するサービス ワーカーを登録する方法の Gist を取得する価値があります。 `offline.html`  次に、アプリの `offline.html` オフライン機能のプレースホルダーとして単純なページを作成します。  
    
1.  ソリューション エクスプローラーでファイルを開 `views/layout.pug` き、リンク タグの下に次の行を追加します。  
    
    ```html
    script(src='/pwabuilder-sw-register.js' type='module')
    ```  
    
    サイトがサービス ワーカー登録スクリプトを読み込み、実行します。  
    
1.  ソリューション エクスプローラーで、フォルダーを右クリックし、[新しいファイルの `public` 追加****  >  **] を選択します**。 名前を `offline.html` 付け、本文 `<title>` の内容を追加します (例: 次のコード)。  
    
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
    
    この時点で、フォルダーには `public` 3 つの新しいファイルが必要です。  
    
    ![ソリューションのパブリック フォルダーに追加されたファイル][ImageVsNodejsExpressPublic]  
    
1.  ソリューション エクスプローラーでファイルを開き、最後のコマンド \( \) の直前に次の `routes\index.js` コードを追加 `module.exports = router;` します。  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    これにより、アプリはファイル \(サービス ワーカーがオフライン キャッシュ用にフェッチするときに) サービスを提供 `offline.html` するように指示します。  
    
1.  PWA をテストしてください。  \( `Ctrl` + `Shift` + `B` \) をビルドして \( \) を実行し、Web アプリを実行して Microsoft Edge を `F5` 起動し、ページを開 `localhost` きます。  次に、次の手順を実行します。  
    
    1.  Edge DevTools**コンソール**\( \) を開 `Ctrl` + `Shift` + `J` き、サービス ワーカーが登録されたのを確認します。  
    1.  デバッガー パネル **で** 、[Service **Workers]** コントロールを展開し、オリジンをクリックします。  サービス ワーカー **の概要で**、サービス ワーカーがアクティブ化され、実行中になっているか確認します。  
        
        ![Edge DevTools Service Worker の概要][ImageDevtoolsSwOverview]  
        
    1.  [ **キャッシュ] コントロール** を展開し、ページ `offline.html` がキャッシュに入っているのを確認します。  
        
        ![Edge DevTools サービス ワーカー キャッシュ][ImageDevtoolsSwCache]  
        
1.  オフライン アプリとして PWA を試してみる時間です。  In Visual Studio, **Stop Debugging** `Shift` + `F5` \( \) your web app, then open Microsoft Edge \(or refresh\) to the localhost address of your website.  これで、ページ \(サービス ワーカーとオフライン キャッシュ\) を読 `offline.html` み込む必要があります。  
    
    ![offline.htmMicrosoft Edge に http://localhost:1337 読み込まれたファイル][ImageOfflineHtml]  

## プッシュ通知を追加する  

プッシュ [API][MDNPushApi] を使用してメッセージング サービスをサブスクライブし、通知 [API][MDNNotificationsApi] を使用してメッセージの受信時にトースト メッセージを表示するクライアント側のプッシュ通知のサポートを追加することで、PWA をよりアプリに似たものにします。  サービス ワーカーと同様に、これらはクロスブラウザーで動作する標準ベースの API なので、PAP がサポートされているすべての場所で動作するには、コードを 1 回記述する必要があります。  サーバー側では [、Web プッシュ][NPMWebPush] オープン ソース ライブラリを使用して、さまざまなブラウザーにプッシュ メッセージを配信する場合に関係する違いを処理します。  

以下は、Mozilla が提供する Service [Worker Cookbook][ServiceWorkerCookbookPushRichDemo] の Push Rich Demo を基にしています。これは、他の多くの便利な Web プッシュおよびサービス ワーカーのレシピを確認する価値があります。  

### 手順 1 - NPM Web プッシュ ライブラリをインストールする  

ソリューション Visual Studioで、プロジェクトを右クリックし、[対話型ウィンドウ] Node.js **開**きます。 その中に、次のコードを入力します。  

```javascript
.npm install web-push
```  

これにより [、Web プッシュ ライブラリがインストール][NPMWebPush] されます。  次に、ファイルを開き、他の要件ステートメントの後に次の行をファイルの一番上 `index.js` に追加します。  

```javascript
var webpush = require('web-push');
```  

### 手順 2 - サーバーの VAPID キーを生成する  

次に、サーバーが PWA クライアントにプッシュ メッセージを送信するために VAPID \(任意のアプリケーション サーバー識別\) キーを生成する必要があります。  これを行う必要があるのは\(つまり、サーバーに必要な VAPID キーのペアが 1 つだけ\) 1 回だけです。  [対話型Node.jsウィンドウで、次のコードを入力します。  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

出力の結果、公開キーとプライベート キーを含む JSON オブジェクトが作成され、サーバー ロジックにコピーされます。  

ファイルの最後の \( \) 行の直前に、次 `index.js` `module.exports = router` のコードを追加します。  

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

生成した `publicKey` `privateKey` 値と値をコピーします。  アドレスも自由にカスタマイズできます (このサンプルを実行するために必要 `mailto` ありません\)。  

[Mozilla Services][MozillaServicesSendingVapidWebPushNotificationsPush]のエンジニアリング ブログには、VAPID と WebPush の詳細な説明が用意されています。その詳細については、このブログを参照してください。  

### 手順 3 - プッシュ関連のサーバー要求を処理する  

次に、PWA クライアントからのプッシュ関連の要求を処理するルートを設定します。たとえば、VAPID 公開キーの処理や、プッシュを受信するクライアントの登録を含みます。  

実際のシナリオでは、プッシュ通知はサーバー ロジックのイベントから発生する可能性があります。  ここでの作業を簡略化するには、PWA**** ホームページにプッシュ通知ボタンを追加してサーバーからプッシュを生成し、それらの要求を処理するエンドポイント `/sendNotification` \(サーバー ルート\)を追加する必要があります。  

ファイルで、[ `index.js` 手順 2][#step-2---generate-vapid-keys-for-your-server] で追加した VAPID 初期化コードの直後に、次のルートを追加します。  

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

サーバー側のコードを配置して、PWA クライアントのプッシュ通知を実行します。  

### 手順 4 - プッシュ通知をサブスクライブする  

PWA ネットワーク プロキシとしての役割の一環として、サービス ワーカーはプッシュ イベントとトースト通知の操作を処理します。  ただし、最初にサービス ワーカーをセットアップする \(または登録\) の場合と同様に、PWA をサーバー プッシュ通知にサブスクライブすると、PWA のメイン UI スレッドで実行され、ネットワーク接続が必要になります。  プッシュ通知をサブスクライブするにはアクティブなサービス ワーカー登録が必要です。そのため、プッシュ通知をサブスクライブする前に、サービス ワーカーがインストールされアクティブなことを確認する必要があります。  

新しいプッシュ サブスクリプションを作成する前に、Microsoft Edge は、ユーザーが通知を受信するための PWA アクセス許可を付与したのか確認します。  設定されていない場合は、ブラウザーからアクセス許可を求めるメッセージがユーザーに表示されます。  アクセス許可が拒否された場合は、要求がスローされます。そのため、処理 `registration.pushManager.subscribe` `DOMException` する必要があります。  アクセス許可の管理について詳しくは [、Microsoft Edge のプッシュ通知に関するページをご覧ください][WindowsBlogsWebNotificationsEdge]。  

ファイルに `pwabuilder-sw-register.js` 、次のコードを追加します。  

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

API の動作とさまざまな関連オプションの詳細については [、PushManager][MDNPushManager] インターフェイスの MDN ドキュメントと [Web プッシュ][NPMWebPushUsage] ライブラリの NPM ドキュメントを参照してください。  

### 手順 5 - プッシュイベント ハンドラーと notificationclick イベント ハンドラーを設定する  

プッシュ サブスクリプションを設定すると、残りの作業はサービス ワーカーで行います。  まず、サーバーから送信されるプッシュ イベントのハンドラーを設定し、プッシュ データペイロードを表示するトースト通知 \(アクセス許可が付与されている場合\) で応答する必要があります。  次に、トーストのクリック ハンドラーを追加して通知を閉じ、現在開いているウィンドウの一覧を並べ替え、目的の PWA クライアント ページを開く、フォーカスする、またはフォーカスを設定します。  

ファイルに `pwabuilder-sw.js` 、次のハンドラーを追加します。  

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

### 手順 6 - 試してみる  

PWA でプッシュ通知をテストする時間です。  

1.  ブラウザーで `F5` \( \) PWA を実行します。  サービス ワーカー コード \( \) を変更したので、DevTools Debugger \( \) をサービス ワーカーの概要パネルに開き、サービス ワーカーの登録を解除し、ページを再読み込み \( \) して再登録する必要があります (または `pwabuilder-sw.js` `F12` ******** `F5` **[\]** をクリックします)。  実稼働シナリオでは、ブラウザーは定期的にサービス ワーカー更新プログラムをチェックし、バックグラウンドで更新プログラムをインストールします。  すぐに結果を得る場合は、ここに強制的に設定する必要があります。  
    
    サービス ワーカーがアクティブ化し、PWA をサブスクライブして通知をプッシュしようとすると、ページの下部にアクセス許可ダイアログが表示されます。  
    
    ![通知を有効にするためのアクセス許可ダイアログ][ImageNotificationPermission]  
    
    [ **はい]** を選択して、PWA のトースト通知を有効にします。  
    
1.  [サービス ワーカーの概要] ウィンドウで、プッシュ ボタンを  **選択** してみてください。  \(hard-coded "Test push message from DevTools"\) ペイロードを含むトースト通知が表示されます。  
    
    ![DevTools からの通知のプッシュ][ImageDevtoolsPush]  
    
1.  次に、PWA のホーム **ページ** で [通知の送信] ボタンを選択してみてください。  今回は、サーバーからのペイロードを含むトーストが表示されます。  
    
    ![PWA サーバーから通知をプッシュする][ImagePwaPush]  
    
    トースト通知を \(または activate\) クリックしない場合は、数秒後に閉じ、Windows アクション センターでキューに登録されます。  
    
    ![Windows アクション センターでの通知][ImageWindowsActionCenter]  
    
    PWA プッシュ通知の基本を使用できます。  実際のアプリでは、次の手順は、プッシュ サブスクリプションを管理および保存し、ネットワークを通して[][NPMWebPushEncrypt]送信されるペイロード データを適切に暗号化する方法で実装されます。  
    
## 追加情報  

このガイドでは、Visual Studio、PWA Builder、Edge DevTools など、段階的 Web App と Microsoft PWA 開発ツールの基本的な構造について説明しました。  

もちろん、レスポンシブ デザイン、ディープ リンク、クロスブラウザー テスト、その他のベスト プラクティス[(アプリ][Webhint]の機能は言うまでもなく[][BrowserStackTestEdgeBrowser]\) など、ここに記載されている以上の優れた[PWA][PwaEdgehtmlIndexRequirements]を作成する方法は他に多く含まれていますが、このガイドでは、PWA の基本と入門に関するアイデアをしっかりと紹介しています。  Windows を使用した PWA 開発に関してさらに質問がある場合や、Visual Studioご質問がある場合は、コメントを残してください。  

他の PWA ガイドを確認して、顧客エンゲージメントを向上し、OS と統合されたよりシームレスなアプリ エクスペリエンスを提供する方法について学習します。  

*   [Windows の調整][PwaEdgehtmlWindowsFeatures]。 単純な機能検出を使用すると、Windows 10 のネイティブ API **(Windows** スタート メニューのタイル通知やタスク バージャンプリストをカスタマイズする API や、写真、音楽、カレンダーなどのユーザー リソースを操作する \(アクセス許可時\) など) を使って、Windows 10 ユーザー向け PWA を徐々に強化できます。  
*   [Microsoft Store の PAS][PwaEdgehtmlMicrosoftStore]。  アプリ ストアの配布の利点と、PWA を提出する方法について詳しくは、以下をご覧ください。  

## 関連項目  

*   [MDN Web ドキュメントの段階的な Web アプリ][MDNProgressiveWebApps] - 段階的な Web アプリの優れたガイド。  
*   [Web.dev 上の段階的な Web][WebDevProgressiveWebApps] アプリ - 段階的な Web アプリの優れたガイド。  
*   [段階的な Web アプリの機能][ProgressiveWebApps] - PAS の実際の例を紹介します。  
*   [段階的な Web][HackerNewsProgressiveWebApps] アプリとしてのハッカーニュース リーダー - サンプル \(Hacker News reader\) PWA を実装するためのさまざまなフレームワークとパフォーマンス パターンを比較します。  

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

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "要件 - Windows の段階的な Web アプリ \(EdgeHTML\) |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps/microsoft-store.md "Microsoft Store の段階的な Web アプリ \(EdgeHTML\)|Microsoft Docs"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps/windows-features.md "Windows 用に PWA \(EdgeHTML\) を調整する |Microsoft Docs"  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store ポリシー |Microsoft Docs"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "チュートリアル: Node.js アプリと Express アプリを作成Visual Studio |Microsoft Docs"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "Azure App Service に発行する - Node.jsアプリと Express アプリを作成Visual Studio |Microsoft Docs"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "ユニバーサル Windows プラットフォーム \(UWP\) アプリとは |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントを作成する |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "Microsoft Edge と Windows 10 への段階的な Web アプリの歓迎 |Windows ブログ"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "ダウンロード |Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "無料の開発者ソフトウェア & サービス |Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio プレビュー"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "段階的な Web アプリとしてのハッカーニュースリーダー"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "Cache |MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope.postMessage\(\) |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "段階的な Web アプリ \(PAS) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "サービス ワーカー API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービス ワーカーの使用 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "Worker.prototype.postMessage\(\) |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "Mozilla のプッシュ サービスを介して VAPID によって識別された WebPush 通知を送信する |Mozilla Services"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-push |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt(userPublicKey, userAuth, payload, contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用法 - Web プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "段階的な Web アプリ"  

[PugAttributes]: https://pugjs.org/language/attributes.html "属性 |Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA Builder"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "アプリ イメージ ジェネレーター"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービス ワーカー |PWA Builder"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker Cookbook"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "プッシュ リッチ デモ |ServiceWorker Cookbook"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web アプリ マニフェスト |W3C"  

[Webhint]: https://sonarwhal.com "webhint は、Web のベスト プラクティスに関するヒントエンジンです。" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Web ワーカーの使用" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "段階的な Web アプリ |web.dev"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS |Wikipedia"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "段階的な機能強化 |Wikipedia"  
