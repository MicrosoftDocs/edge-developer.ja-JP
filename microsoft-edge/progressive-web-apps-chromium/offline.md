---
title: プログレッシブ Web アプリでのオフラインおよびネットワーク接続のサポート
description: サポート技術を利用して、さまざまなネットワークの状態を把握するための耐障害性のエクスペリエンスを実現する方法について説明します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ web アプリ、PWA、エッジ、JavaScript、Windows、UWP、Microsoft ストア
ms.openlocfilehash: 58ffb8e9ae596dec4b99143a3061995a6598ce44
ms.sourcegitcommit: d9cc829deb709b0866f6b43a5f4733682ddae5ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "10659308"
---
# プログレッシブ Web アプリでのオフラインおよびネットワーク接続のサポート

多くの場合、web アプリケーションは安定したネットワーク接続に依存しているため、web ベースのソフトウェアへの多大な投資は、組織にとってあまり厳しくありませんでした。 現在、web プラットフォームでは、ネットワーク接続が不安定になった場合や完全にオフラインになった場合でも、ユーザーが作業を続けることができる堅牢なオプションが提供されるようになりました。

## キャッシュを使用して PWAs のパフォーマンスを向上させる

[サービスワーカー][MDNServiceWorker]の導入により、web platform は API を追加して、 `Cache` マネージキャッシュされたリソースへのアクセスを提供します。 この Promise ベースの API を使用すると、開発者は、HTML、CSS、JavaScript、画像、JSON など、多くの web リソースを保存して取得することができます。 通常、キャッシュ API は、サービスワーカーのコンテキスト内で使用されますが、オブジェクトのメインスレッドでも使用でき `window` ます。

API の一般的な用途の1つ `Cache` は、次のコードスニペットに示すように、サービスワーカーのインストール時に重要なリソースを事前にキャッシュすることです。  

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

このコードは、サービスワーカーのライフサイクルイベント中に実行され、キャッシュの `install` 名前が付けら `static-cache` れ、キャッシュへのポインターがある場合に、このメソッドを使って4つのリソースを追加し `addAll()` ます。  このアプローチは、多くの場合、イベント中のキャッシュ取得と組み合わされています。 `fetch`   

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

このコードスニペットは、ブラウザーからこのサイトへの要求が行われるたびに、サービスワーカー内で実行され `fetch` ます。 このイベント内には、要求が HTML ファイルを対象としている場合に実行される条件付きステートメントがあります。 サービスワーカーは、ファイルが既にいずれかのキャッシュに存在するかどうかを確認し `match()` ます (メソッド \ を使用)。 要求がキャッシュ内に存在する場合、キャッシュされた結果が返されます。 存在しない場合、 `fetch` そのリソースの新しい動作が実行されると、後で応答のコピーがキャッシュされ、応答が返されます。 `fetch`ネットワークが利用できないために失敗した場合は、オフラインページがキャッシュから返されます。

この簡単な概要では、プログレッシブ web アプリ (PWA) でキャッシュを使用する方法について説明します。 各 PWA は異なっていて、異なるキャッシュ計画を使用している可能性があります。 コードによって表示が異なる場合があり、同じアプリケーション内のさまざまなルートに異なるキャッシュ計画を使うことができます。

## PWA で IndexedDB を使って構造化データを保存する

`IndexedDB` 構造化データを保存するための API です。 API と似 `Cache` ていますが、非同期でもあります。これは、メインスレッドまたはサービスワーカーなどの Web ワーカーで使用できることを意味します。 API を使って、 `IndexedDB` 大量の構造化データをクライアントに保存するか、暗号化されたメディアオブジェクトなどのバイナリデータを保存します。 詳細については、「 [IndexedDB を使った MDN 入門][MDNIndexeddbApiUsing]」を参照してください。

## PWAs のストレージオプションについて

ユーザーに最適なオフライン操作を提供するために、少量のデータを保存しなければならない場合があります。 このような場合は、web storage のキーと値のペアシステムのシンプルさがニーズを満たしていることがわかります。  

> [!IMPORTANT]
> Web ストレージは同期プロセスであり、サービスワーカーなどのワーカースレッド内では使用できません。 使用頻度が高いと、アプリケーションのパフォーマンスの問題が発生する可能性があります。 


Web Storage には、との2種類があり `localStorage` `sessionStorage` ます。 それぞれは、それを作成したドメインに対して分離された個別のデータストアとして管理されます。 `sessionStorage` 閲覧セッションの期間のみ保持されます (たとえば、ブラウザーが開かれている間のみ、更新と復元が含まれます)。 `localStorage` データが、コード、ユーザー、ブラウザーによって削除されるまで保持されます (たとえば、利用可能なストレージが限られている場合)。 次のコードスニペットは、の使い方と似ています。これを使う方法を示してい `localStorage` `sessionStorage` ます。

```javascript
var data = {
    title: document.querySelector("[property='og:title']").getAttribute("content"),
    description: document.querySelector( "meta[name='description']" ).getAttribute("content")
};
localStorage.setItem( window.location, JSON.stringify(data) );
```  

このコードスニペットは、現在のページに関するメタデータを取得し、JavaScript オブジェクトに格納します。 次に、メソッドを使用してその値を JSON として保存 `localStorage` `setItem()` し、現在の URL に等しいキーを割り当て `window.location` ます。 メソッドを使用して情報を取得することができ `localStorage` `getItem()` ます。 

次のコードスニペットは、キャッシュされた `localstorage` ページを列挙し、メタデータを抽出して、リンクの一覧の作成などの作業を実行する方法を示しています。

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

メソッドは、 `insertOfflineLink()` `localStorage.getItem()` 保存されているメタデータを取得するために、要求の URL をメソッドに渡します。 取得したデータが存在するかどうかが確認され、存在する場合は、表示するためのマークアップの作成や挿入などの操作をデータに対して実行できます。

## PWA のネットワーク接続をテストする

オフラインで使用するための情報を保存するだけでなく、データを同期したり、ネットワークの状態が変わったことをユーザーに通知したりするために、ネットワーク接続が利用可能になっているかどうかを知ることができます。 ネットワーク接続をテストするには、次のオプションを使用します。

### ナビゲーター。オンライン  

`navigator.onLine`プロパティは、ネットワークの現在の状態を知ることができるブール値です。 値がの場合は、ユーザーがオンラインであるかどうかを示し `true` ます。それ以外の場合は、ユーザーがオフラインになります。

### オンラインイベントとオフラインイベント  

ネットワークが利用可能であるかどうかを知ることは有用ですが、ネットワーク接続が変更されたときに対処することが必要な場合があります。 この状況では、ネットワークイベントに応答してリッスンし、操作を行うことができます。 イベントは、、 `window` `document` および要素で、次のコードスニペットのように表示され `document.body` ます。

```javascript
window.addEventListener("online",  function(){
    console.log("You are online!");
});
window.addEventListener("offline", function(){
    console.log("Oh no, you lost your network connection.");
});
```  

## 関連項目  

オフラインシナリオの管理の詳細については、次のページを参照してください。  

*   [キャッシュ][MDNCache]  
*   [IndexedDB][MDNIndexeddbApi]  
*   [サービスワーカー][MDNServiceWorker]  
*   [Web ストレージ][MDNWebStorageApi]  
*   [ナビゲーター。オンライン][MDNNavigatoronline]  
*   [オンラインイベントとオフラインイベント][MDNNavigatoronlineOfflineEvents]  
*   [インテントの要求: PWAs のキャッシュ計画][AlistapartRequestIntentCachingStrategiesAgePwas]

<!-- links -->  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNIndexeddbApi]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNIndexeddbApiUsing]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "IndexDb API を使用しています。MDN"  
[MDNServiceWorker]: https://developer.mozilla.org/docs/Web/API/ServiceWorker "ServiceWorker |MDN"  
[MDNWebStorageApi]: https://developer.mozilla.org/docs/Web/API/Web_Storage_API "Web Storage API |MDN"  
[MDNNavigatoronline]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine "NavigatorOnLine |MDN"  
[MDNNavigatoronlineOfflineEvents]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine/Online_and_offline_events "オンラインイベントとオフラインイベント-NavigatorOnLine |MDN"  

[AbookapartGoingOffline]: https://abookapart.com/products/going-offline "Jeremy Keith によるオフラインでの移動本との分解"  

[AlistapartRequestIntentCachingStrategiesAgePwas]: https://alistapart.com/article/request-with-intent-caching-strategies-in-the-age-of-pwas "インテントの要求: PWAs のキャッシュ戦略はアーロン Gustafson |リストの分解"  
