---
title: プログレッシブ Web アプリでのオフライン接続とネットワーク接続のサポート
description: サポート テクノロジを使用して、さまざまなネットワーク条件に対応する回復力のあるエクスペリエンスを作成する方法について学習します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ Web アプリ、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 6b6031aac10161c16195c83496f8d8b5b842628e
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398078"
---
# <a name="offline-and-network-connectivity-support-in-progressive-web-apps"></a>プログレッシブ Web アプリでのオフライン接続とネットワーク接続のサポート

長年にわたり、Web アプリケーションは安定したネットワーク接続に依存していたため、組織はネイティブ ソフトウェアよりも Web ベースのソフトウェアに多額の投資を行うのを消極的でした。 現在、Web プラットフォームでは、ネットワーク接続が不安定になったり、完全にオフラインになったりした場合でも、ユーザーが作業を続行できる堅牢なオプションが提供されています。

## <a name="use-the-caching-to-improve-performance-of-pwas"></a>キャッシュを使用して PWA のパフォーマンスを向上させる

Service [Workers の導入により][MDNServiceWorker]、Web プラットフォームはマネージ キャッシュ されたリソースへのアクセスを提供する `Cache` API を追加しました。 この Promise ベースの API を使用すると、開発者は HTML、CSS、JavaScript、画像、JSON など、多くの Web リソースを格納および取得できます。 通常、キャッシュ API は Service Worker のコンテキスト内で使用されますが、オブジェクトのメイン スレッドでも使用 `window` できます。

API の一般的な使用の 1 つは、次のコード スニペットに示すように、Service Worker のインストール時に重要なリソースを事前に `Cache` キャッシュする方法です。  

```javascript
self.addEventListener( "install", function( event ){
    event.waitUntil(
        caches.open( "static-cache" )
              .then(function( cache ){
            return cache.addAll([
                "/css/main.css",
                "/js/main.js",
                "/img/favicon.png",
                "/offline/"
            ]);
        })
    );
});
```  

Service Worker ライフ サイクル イベント中に実行されるこのコードは、という名前のキャッシュを開き、キャッシュへのポインターがある場合は、メソッドを使用して 4 つのリソースを追加 `install` `static-cache` `addAll()` します。  多くの場合、このアプローチはイベント中にキャッシュ取得と結合 `fetch` されます。   

```javascript
self.addEventListener( "fetch", event => {
    const request = event.request,
                    url = request.url;
    
    // If we are requesting an HTML page.
    if ( request.headers.get("Accept").includes("text/html") ) {
        event.respondWith(
            // Check the cache first to see if the asset exists, and if it does, return the cached asset.
            caches.match( request )
                  .then( cached_result => {
                if ( cached_result ) {
                    return cached_result;
                }
                // If the asset is not in the cache, fallback to a network request for the asset, and proceed to cache the result.
                return fetch( request )
                       .then( response => {
                    const copy = response.clone();
                    // Wait until the response we received is added to the cache.
                    event.waitUntil(
                        caches.open( "pages" )
                              .then( cache => {
                            return cache.put( request, response );
                        });
                    );
                    return response;
                })
                // If the network is unavailable to make a request, pull the offline page out of the cache.
                .catch(() => caches.match( "/offline/" ));
            })
        ); // end respondWith
    } // end if HTML
});
```  

このコード スニペットは、ブラウザーがこのサイトに対して要求を行うたびに、Service Worker `fetch` 内で実行されます。 そのイベント内に、要求が HTML ファイルの場合に実行される条件付きステートメントがあります。 Service Worker は、ファイルがキャッシュ \(method\を使用して) に既に存在するかどうかを `match()` 確認します。 要求がキャッシュに存在する場合は、キャッシュされた結果が返されます。 指定しない場合は、そのリソースの新しいリソースが実行され、応答のコピーが後でキャッシュされ、 `fetch` 応答が返されます。 ネットワークが `fetch` 使用できなくなったため失敗した場合、オフライン ページはキャッシュから返されます。

この簡単な概要は、プログレッシブ Web アプリ (PWA) でキャッシュを使用する方法を示しています。 各 PWA は異なるので、異なるキャッシュ戦略を使用できます。 コードは見た目が異なる場合があります。また、同じアプリケーション内の異なるルートに対して異なるキャッシュ戦略を使用する場合があります。

## <a name="use-indexeddb-in-your-pwa-to-store-structured-data"></a>PWA で IndexedDB を使用して構造化データを格納する

`IndexedDB` は構造化データを格納するための API です。 API と同様に、この API も非同期です。つまり、メイン スレッドまたはサービス ワーカーなどの Web ワーカーで使用 `Cache` できます。 クライアントに大量の構造化データを格納したり、暗号化されたメディア オブジェクトなどのバイナリ データを格納したりするには `IndexedDB` 、API を使用します。 詳細については [、IndexedDB の使用に関する MDN の入門書に移動します][MDNIndexeddbApiUsing]。

## <a name="understand-storage-options-for-pwas"></a>PWA のストレージ オプションについて

ユーザーに優れたオフライン エクスペリエンスを提供するために、少量のデータを保存する必要がある場合があります。 その場合は、Web ストレージのキーと値のペア システムがニーズを満たしているのが簡単です。  

> [!IMPORTANT]
> Web ストレージは同期プロセスであり、Service Workers などのワーカー スレッド内では使用できません。 使用量が多い場合は、アプリケーションのパフォーマンスの問題が発生する可能性があります。 


Web ストレージには、次の 2 種類があります `localStorage` `sessionStorage` 。 それぞれが、作成したドメインに分離された個別のデータ ストアとして維持されます。 `sessionStorage` 閲覧セッションの期間中のみ保持されます (ブラウザーが開いている間など、更新と復元が含まれます)。 `localStorage` データがコード、ユーザー、またはブラウザーによって削除されるまで保持されます (たとえば、使用できる記憶域が限られている場合)。 次のコード スニペットは、使い方に似た使 `localStorage` い方を `sessionStorage` 示しています。

```javascript
var data = {
    title: document.querySelector("[property='og:title']").getAttribute("content"),
    description: document.querySelector( "meta[name='description']" ).getAttribute("content")
};
localStorage.setItem( window.location, JSON.stringify(data) );
```  

このコード スニペットは、現在のページに関するメタデータを取得し、JavaScript オブジェクトに格納します。 次に、メソッドを使用してその値を JSON として格納し、現在の URL と等しいキー `localStorage` `setItem()` を割り当 `window.location` てる。 メソッドを使用して情報 `localStorage` を取得 `getItem()` できます。 

次のコード スニペットは、キャッシュを使用してキャッシュされたページを列挙し、メタデータを抽出してタスクを実行する方法 (リンクのリストの作成など) `localstorage` を示しています。

```javascript
caches.open( "pages" )
      .then( cache => {
    cache.keys()
         .then( keys => {
        if ( keys.length )
        {
            keys.forEach( insertOfflineLink );
        }
    })
});

function insertOfflineLink( request ) {
    var data = JSON.parse( localStorage.getItem( request.url ) );
    // If data exists and this page is not an offline page, assuming that offline pages have the word offline in the URL.
    if ( data && request.url.indexOf('offline') < 0  )
    {
        // Build a link and insert it into the page.
    }
}
```  

この `insertOfflineLink()` メソッドは、要求の URL をメソッドに渡して `localStorage.getItem()` 、格納されているメタデータを取得します。 取得したデータが存在するかどうかを確認し、存在する場合は、マークアップを作成して表示する挿入など、データに対してアクションを実行できます。

## <a name="test-for-network-connections-in-your-pwa"></a>PWA でのネットワーク接続のテスト

オフラインで使用する情報を保存する以外に、データを同期したり、ネットワークの状態が変更されたとユーザーに通知したりするために、ネットワーク接続がいつ利用できるのか確認すると便利です。 ネットワーク接続をテストするには、次のオプションを使用します。

### <a name="navigatoronline"></a>navigator.onLine  

プロパティ `navigator.onLine` は、ネットワークの現在の状態を知るブール値です。 値がである場合 `true` 、ユーザーはオンラインで、それ以外の場合はユーザーはオフラインです。

### <a name="online-and-offline-events"></a>オンラインイベントとオフライン イベント  

ネットワークが利用できるかどうかを知るのは役に立ちますが、ネットワーク接続が変更された場合に対処する必要があります。 このような場合は、ネットワーク イベントに応答してリッスンしてアクションを実行できます。 イベントは、次のコード スニペットに表示される 、、および `window` `document` `document.body` 要素で使用できます。

```javascript
window.addEventListener("online",  function(){
    console.log("You are online!");
});
window.addEventListener("offline", function(){
    console.log("Oh no, you lost your network connection.");
});
```  

## <a name="see-also"></a>関連項目  

オフライン シナリオの管理の詳細については、次のページに移動します。  

*   [キャッシュ][MDNCache]  
*   [IndexedDB][MDNIndexeddbApi]  
*   [サービス ワーカー][MDNServiceWorker]  
*   [Web ストレージ][MDNWebStorageApi]  
*   [navigator.onLine][MDNNavigatoronline]  
*   [オンラインイベントとオフライン イベント][MDNNavigatoronlineOfflineEvents]  
*   [意図を持つ要求: PWA の時代のキャッシュ戦略][AlistapartRequestIntentCachingStrategiesAgePwas]
    
<!-- links -->  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNIndexeddbApi]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNIndexeddbApiUsing]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "IndexDb - IndexDB API の使用|MDN"  
[MDNServiceWorker]: https://developer.mozilla.org/docs/Web/API/ServiceWorker "ServiceWorker |MDN"  
[MDNWebStorageApi]: https://developer.mozilla.org/docs/Web/API/Web_Storage_API "Web ストレージ API |MDN"  
[MDNNavigatoronline]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine "NavigatorOnLine |MDN"  
[MDNNavigatoronlineOfflineEvents]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine/Online_and_offline_events "オンラインイベントとオフライン イベント - NavigatorOnLine |MDN"  

[AbookapartGoingOffline]: https://abookapart.com/products/going-offline "Jeremy Keith |A Book Apart"  

[AlistapartRequestIntentCachingStrategiesAgePwas]: https://alistapart.com/article/request-with-intent-caching-strategies-in-the-age-of-pwas "意図を持つ要求: Aaron Gustafson による PWA の時代のキャッシュ戦略|A List Apart"  
