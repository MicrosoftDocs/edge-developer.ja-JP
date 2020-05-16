---
title: サービスワーカーを使ってネットワーク要求とプッシュ通知を管理する
description: サービスワーカーは、パフォーマンスの向上、さまざまなネットワークの状態への対応、web アプリケーションとの接続性の向上に役立つ Web ワーカーです。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ web アプリ、PWA、エッジ、JavaScript、Windows、UWP、Microsoft ストア
ms.openlocfilehash: 9bf573b668ade351716b69965f653e05857c32ec
ms.sourcegitcommit: d9cc829deb709b0866f6b43a5f4733682ddae5ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "10659301"
---
# サービスワーカーを使ってネットワーク要求とプッシュ通知を管理する

サービスワーカーは、API を使ってすべてのネットワーク要求を傍受、変更、応答することができる特殊な種類の Web ワーカーです `Fetch` 。  サービスワーカーは、 `Cache` `IndexedDB` リソースを格納するために、API と非同期クライアント側データストアにアクセスできます。  

## サービスワーカーの登録  

他の Web ワーカーと同様に、サービスワーカーは別のファイル内に存在する必要があります。 このファイルは、次のコードスニペットに示すように、サービスワーカーを登録するときに参照します。  

```javascript
if ( "serviceWorker" in navigator ) {
    navigator.serviceWorker.register( "/serviceworker.min.js" );
}
```  

最新のブラウザーには、サービスワーカー向けにさまざまなレベルのサポートが用意しています。 このため、 `serviceWorker` サービスワーカーに関連するコードを実行する前に、オブジェクトが存在するかどうかをテストすることをお勧めします。 上のコードスニペットでは、サービスワーカーは、 `serviceworker.min.js` サイトのルートにあるファイルを使って登録されています。 サービスワーカーを定義する JavaScript ファイルが、管理対象の最上位ディレクトリ (サービスワーカーの範囲として参照されます) に存在することを確認します。  上のコードスニペットでは、ファイルがルートに保存され、サービスワーカーがドメイン内のすべてのページを管理します。 サービスワーカーファイルがディレクトリに保存されていた場合 `js` 、サービスワーカーのスコープは `js` ディレクトリとサブディレクトリになります。  サービスワーカーのスコープを減らす必要がある場合を除き、サービスワーカーファイルは、サイトのルートに配置することをお勧めします。  

## サービスワーカーのライフサイクル  

サービスワーカーのライフサイクルは、複数のステップで構成され、各手順でイベントがトリガーされます。 これらのイベントにリスナーを追加して、操作を実行するためのコードを実行できます。 次の一覧は、service worker のライフサイクルと関連イベントの概要を示しています。 

1. サービスワーカーを登録します。  
1.  ブラウザーは、JavaScript ファイルをダウンロードし、サービスワーカーをインストールし、イベントをトリガーし `install` ます。 `install`このイベントを使うと、web サイトから CSS ファイル、JavaScript ファイル、ロゴ画像、オフラインページなど、重要な有効期間が長いファイルを事前にキャッシュすることができます。  
    
    ```javascript
    self.addEventListener( "install", function( event ){
        console.log( "WORKER: install event in progress." );
    });
    ```  
    
1.  サービスワーカーがアクティブになり、イベントがトリガーされ `activate` ます。  このイベントを使用して、古いキャッシュをクリーンアップします。  
    
    ```javascript
    self.addEventListener( "activate", event => {
        console.log('WORKER: activate event in progress.');
    });
    ```  
    
1.  サービスワーカーは、ページが更新されたとき、またはユーザーがサイト上の新しいページに移動したときに実行する準備ができています。 サービスワーカーを待機させずに実行する場合は、 `self.skipWaiting()` イベント中にメソッドを使い `install` ます。  
    
    ```javascript
    self.addEventListener( "install", event => {
        self.skipWaiting();
        // …
    });
    ```
    
1.  現在、サービスワーカーを実行しています。     
    
## サービスワーカーでの fetch の使用  

サービスワーカーで使用する主なイベントは、 `fetch` イベントです。  イベントは、 `fetch` ブラウザーがサービスワーカーのスコープ内でコンテンツにアクセスしようとするたびに実行されます。 次のコードスニペットは、リスナーを fetch イベントに追加する方法を示しています。  

```javascript
self.addEventListener( "fetch", event => {
  console.log('WORKER: Fetching', event.request);
});
```  

ハンドラー内で、 `fetch` 要求がネットワークに送られるか、キャッシュから取得するかなどを制御できます。  目的のアプローチは、要求されているリソースの種類、更新頻度、およびアプリケーションに固有の他のビジネスロジックによって異なります。  次に、実行できる操作の例をいくつか示します。  

*   可能であれば、キャッシュから応答を返します。それ以外の場合は、ネットワーク経由でリソースを要求するためにフォールバックします。  
*   ネットワークからリソースを取得し、コピーをキャッシュして、応答を返します。
*   ユーザーがデータを保存するための環境設定を指定できるようにします。 
*   特定の画像要求のプレースホルダー画像を指定します。  
*   サービスワーカーで直接応答を生成します。  

## プッシュ通知  

サービスワーカーは通知をユーザーにプッシュすることができます。 プッシュ通知は、一定の時間が経過した後に、ユーザーにアプリケーションの再利用を促すために役立ちます。 詳細については、「[プッシュ通知のチュートリアルとデモ][AzurewebsitesWebpushdemo]」を参照してください。  

## 関連項目  

サービスワーカーの詳細については、次の関連するトピックの一覧を参照してください。  

*   [Service worker で PWAs をオフライン作業する][MDNPwasMakingOfflineServiceWorkers]  
*   [通知とプッシュを使用して PWAs を再作成する方法][MDNPwasMakeReengageablesingNotificationsPush]  

<!-- links -->  

[AzurewebsitesWebpushdemo]: https://webpushdemo.azurewebsites.net "Web プッシュ通知 | Microsoft Edge のデモ"  

[MDNPwasMakingOfflineServiceWorkers]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Offline_Service_workers "サービスワーカーで PWAs をオフラインで操作しました-PWAs |MDN"  
[MDNPwasMakeReengageablesingNotificationsPush]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Re-engageable_Notifications_Push "通知を使って PWAs を再設定する方法とプッシュ-PWAs の使い方 |MDN"  
