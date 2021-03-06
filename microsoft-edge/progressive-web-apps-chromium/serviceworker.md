---
title: サービス ワーカーを使用してネットワーク要求とプッシュ通知を管理する
description: サービス ワーカーは、パフォーマンスの向上、さまざまなネットワーク状態への対応、Web アプリケーションとの接続の向上に役立つ Web ワーカーです。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ Web アプリ、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 314acbbd5a2f423c274f92e815b2be4329ace9b8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399135"
---
# <a name="use-service-workers-to-manage-network-requests-and-push-notifications"></a>サービス ワーカーを使用してネットワーク要求とプッシュ通知を管理する

サービス ワーカーは、API を使用してすべてのネットワーク要求を傍受、変更、および応答できる特別な種類の `Fetch` Web ワーカーです。  サービス ワーカーは、API や非同期クライアント側のデータ ストア (リソースを格納するなど `Cache` `IndexedDB` ) にアクセスできます。  

## <a name="registering-a-service-worker"></a>サービス ワーカーの登録  

他の Web ワーカーと同様に、サービス ワーカーは別のファイルに存在する必要があります。 次のコード スニペットに示すように、Service Worker を登録するときにこのファイルを参照します。  

```javascript
if ( "serviceWorker" in navigator ) {
    navigator.serviceWorker.register( "/serviceworker.min.js" );
}
```  

最新のブラウザーでは、Service Workers のサポートレベルが異なります。 そのため、サービス ワーカー関連のコードを実行する前に、オブジェクトの存在を `serviceWorker` テストしてください。 上記のコード スニペットでは、サービス ワーカーがサイトのルートにあるファイルを使用 `serviceworker.min.js` して登録されます。 サービス ワーカーを定義する JavaScript ファイルが、\(Service Worker\のスコープと呼ばれます) を管理する最高レベルのディレクトリに存在することを確認します。  前のコード スニペットでは、ファイルはルートに格納され、Service Worker はドメイン内のすべてのページを管理します。 Service Worker ファイルがディレクトリに格納されている場合、Service Worker のスコープはディレクトリと `js` `js` サブディレクトリになります。  ベスト プラクティスとして、サービス ワーカーの範囲を減らす必要がない限り、サービス ワーカー ファイルをサイトのルートに配置します。  

## <a name="the-service-worker-lifecycle"></a>Service Worker のライフサイクル  

Service Worker のライフサイクルは複数の手順で構成されます。各手順でイベントがトリガーされます。 これらのイベントにリスナーを追加して、アクションを実行するコードを実行できます。 次の一覧は、サービス ワーカーのライフサイクルと関連イベントの大きなレベルのビューを示しています。 

1.  サービス ワーカーを登録します。  
1.  ブラウザーは JavaScript ファイルをダウンロードし、Service Worker をインストールし、イベントをトリガー `install` します。 このイベントを使用して、CSS ファイル、JavaScript ファイル、ロゴ イメージ、オフライン ページなど、重要で長命なファイルを Web サイトから事前に `install` キャッシュできます。  
    
    ```javascript
    self.addEventListener( "install", function( event ){
        console.log( "WORKER: install event in progress." );
    });
    ```  
    
1.  サービス ワーカーがアクティブ化され、イベントがトリガー `activate` されます。  古いキャッシュをクリーンアップするには、このイベントを使用します。  
    
    ```javascript
    self.addEventListener( "activate", event => {
        console.log('WORKER: activate event in progress.');
    });
    ```  
    
1.  サービス ワーカーは、ページが更新された場合、またはユーザーがサイト上の新しいページに移動するときに実行する準備が整いました。 待機せずに Service Worker を実行する場合は、イベント中 `self.skipWaiting()` にメソッドを使用 `install` します。  
    
    ```javascript
    self.addEventListener( "install", event => {
        self.skipWaiting();
        // …
    });
    ```
    
1.  サービス ワーカーが実行中です。     
    
## <a name="using-fetch-in-service-workers"></a>Service Workers でのフェッチの使用  

Service Worker で使用する主なイベントはイベント `fetch` です。  このイベントは、ブラウザーが Service Worker のスコープ内のコンテンツにアクセスしようと試みる `fetch` 度に実行されます。 次のコード スニペットは、フェッチ イベントにリスナーを追加する方法を示しています。  

```javascript
self.addEventListener( "fetch", event => {
  console.log('WORKER: Fetching', event.request);
});
```  

ハンドラー内で、要求がネットワークに送信され、キャッシュからプルされるかどうかを `fetch` 制御できます。  使用する方法は、要求されるリソースの種類、更新頻度、およびアプリケーション固有の他のビジネス ロジックによって異なります。  次に、実行する操作の例を示します。  

*   使用可能な場合は、キャッシュからの応答を返し、それ以外の場合はフォールバックしてネットワーク上でリソースを要求します。  
*   ネットワークからリソースを取得し、コピーをキャッシュし、応答を返します。
*   ユーザーがデータを保存する基本設定を指定できます。 
*   特定のイメージ要求のプレースホルダー イメージを指定します。  
*   サービス ワーカーで直接応答を生成します。  
    
## <a name="push-notifications"></a>プッシュ通知  

サービス ワーカーは、ユーザーに通知をプッシュできます。 プッシュ通知は、しばらく時間が経過した後にアプリケーションに再び参加するようにユーザーに促す場合に役立ちます。 詳細については、「プッシュ通知のチュートリアル [とデモ」に移動します][AzurewebsitesWebpushdemo]。  

## <a name="see-also"></a>関連項目  

Service Workers の詳細については、次の関連トピックの一覧に移動します。  

*   [サービス ワーカーと PWA をオフラインで動作する][MDNPwasMakingOfflineServiceWorkers]  
*   [通知とプッシュを使用して PWA を再エンゲージする方法][MDNPwasMakeReengageablesingNotificationsPush]  
    
<!-- links -->  

[AzurewebsitesWebpushdemo]: https://webpushdemo.azurewebsites.net "Web プッシュ通知| Microsoft Edge デモ"  

[MDNPwasMakingOfflineServiceWorkers]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Offline_Service_workers "サービス ワーカーと一緒に PWA をオフラインで動作する - PWA |MDN"  
[MDNPwasMakeReengageablesingNotificationsPush]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Re-engageable_Notifications_Push "通知とプッシュを使用して PWA を再びエンゲージする方法 - PWA |MDN"  
