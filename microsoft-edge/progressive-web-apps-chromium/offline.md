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
# <a name="offline-and-network-connectivity-support-in-progressive-web-apps"></a><span data-ttu-id="70ad8-104">プログレッシブ Web アプリでのオフライン接続とネットワーク接続のサポート</span><span class="sxs-lookup"><span data-stu-id="70ad8-104">Offline and network connectivity support in Progressive Web Apps</span></span>

<span data-ttu-id="70ad8-105">長年にわたり、Web アプリケーションは安定したネットワーク接続に依存していたため、組織はネイティブ ソフトウェアよりも Web ベースのソフトウェアに多額の投資を行うのを消極的でした。</span><span class="sxs-lookup"><span data-stu-id="70ad8-105">For many years organizations were reluctant to invest heavily in web-based software over native software because web applications depended on stable network connections.</span></span> <span data-ttu-id="70ad8-106">現在、Web プラットフォームでは、ネットワーク接続が不安定になったり、完全にオフラインになったりした場合でも、ユーザーが作業を続行できる堅牢なオプションが提供されています。</span><span class="sxs-lookup"><span data-stu-id="70ad8-106">Today, the web platform now offers robust options that enable users to continue working, even if the network connection becomes unstable or goes completely offline.</span></span>

## <a name="use-the-caching-to-improve-performance-of-pwas"></a><span data-ttu-id="70ad8-107">キャッシュを使用して PWA のパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="70ad8-107">Use the caching to improve performance of PWAs</span></span>

<span data-ttu-id="70ad8-108">Service [Workers の導入により][MDNServiceWorker]、Web プラットフォームはマネージ キャッシュ されたリソースへのアクセスを提供する `Cache` API を追加しました。</span><span class="sxs-lookup"><span data-stu-id="70ad8-108">With the introduction of [Service Workers][MDNServiceWorker], the web platform added the `Cache` API to provide access to managed cached resources.</span></span> <span data-ttu-id="70ad8-109">この Promise ベースの API を使用すると、開発者は HTML、CSS、JavaScript、画像、JSON など、多くの Web リソースを格納および取得できます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-109">This Promise-based API allows developers to store and retrieve many web resources—HTML, CSS, JavaScript, images, JSON, and so on.</span></span> <span data-ttu-id="70ad8-110">通常、キャッシュ API は Service Worker のコンテキスト内で使用されますが、オブジェクトのメイン スレッドでも使用 `window` できます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-110">Usually, the Cache API is used within the context of a Service Worker, but it is also available in the main thread on the `window` object.</span></span>

<span data-ttu-id="70ad8-111">API の一般的な使用の 1 つは、次のコード スニペットに示すように、Service Worker のインストール時に重要なリソースを事前に `Cache` キャッシュする方法です。</span><span class="sxs-lookup"><span data-stu-id="70ad8-111">One common use for the `Cache` API is to pre-cache critical resources when a Service Worker is installed, as shown in the following code snippet.</span></span>  

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

<span data-ttu-id="70ad8-112">Service Worker ライフ サイクル イベント中に実行されるこのコードは、という名前のキャッシュを開き、キャッシュへのポインターがある場合は、メソッドを使用して 4 つのリソースを追加 `install` `static-cache` `addAll()` します。</span><span class="sxs-lookup"><span data-stu-id="70ad8-112">This code, which runs during the Service Worker `install` life cycle event, opens a cache named `static-cache` and then, when it has a pointer to the cache, adds four resources to it using the `addAll()` method.</span></span>  <span data-ttu-id="70ad8-113">多くの場合、このアプローチはイベント中にキャッシュ取得と結合 `fetch` されます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-113">Often the approach is coupled with cache retrieval during a `fetch` event</span></span>   

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

<span data-ttu-id="70ad8-114">このコード スニペットは、ブラウザーがこのサイトに対して要求を行うたびに、Service Worker `fetch` 内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-114">The code snippet runs within the Service Worker whenever the browser makes a `fetch` request for this site.</span></span> <span data-ttu-id="70ad8-115">そのイベント内に、要求が HTML ファイルの場合に実行される条件付きステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="70ad8-115">Within that event, there is a conditional statement that runs if the request is for an HTML file.</span></span> <span data-ttu-id="70ad8-116">Service Worker は、ファイルがキャッシュ \(method\を使用して) に既に存在するかどうかを `match()` 確認します。</span><span class="sxs-lookup"><span data-stu-id="70ad8-116">The Service Worker checks to see if the file already exists in any cache \(using the `match()` method\).</span></span> <span data-ttu-id="70ad8-117">要求がキャッシュに存在する場合は、キャッシュされた結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-117">If the request exists in the cache, that cached result is returned.</span></span> <span data-ttu-id="70ad8-118">指定しない場合は、そのリソースの新しいリソースが実行され、応答のコピーが後でキャッシュされ、 `fetch` 応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-118">If not, a new `fetch` for that resource is run, a copy of the response is cached for later, and the response is returned.</span></span> <span data-ttu-id="70ad8-119">ネットワークが `fetch` 使用できなくなったため失敗した場合、オフライン ページはキャッシュから返されます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-119">If the `fetch` fails because the network is unavailable, the offline page is returned from the cache.</span></span>

<span data-ttu-id="70ad8-120">この簡単な概要は、プログレッシブ Web アプリ (PWA) でキャッシュを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="70ad8-120">This simple introduction shows how to use caching in your progressive web app (PWA).</span></span> <span data-ttu-id="70ad8-121">各 PWA は異なるので、異なるキャッシュ戦略を使用できます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-121">Each PWA is different and may use different caching strategies.</span></span> <span data-ttu-id="70ad8-122">コードは見た目が異なる場合があります。また、同じアプリケーション内の異なるルートに対して異なるキャッシュ戦略を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="70ad8-122">Your code may look different, and you may use different caching strategies for different routes within the same application.</span></span>

## <a name="use-indexeddb-in-your-pwa-to-store-structured-data"></a><span data-ttu-id="70ad8-123">PWA で IndexedDB を使用して構造化データを格納する</span><span class="sxs-lookup"><span data-stu-id="70ad8-123">Use IndexedDB in your PWA to store structured data</span></span>

`IndexedDB` <span data-ttu-id="70ad8-124">は構造化データを格納するための API です。</span><span class="sxs-lookup"><span data-stu-id="70ad8-124">is an API for storing structured data.</span></span> <span data-ttu-id="70ad8-125">API と同様に、この API も非同期です。つまり、メイン スレッドまたはサービス ワーカーなどの Web ワーカーで使用 `Cache` できます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-125">Similar to the `Cache` API, it is also asynchronous, which means you may use it in the main thread or with Web Workers such as Service Workers.</span></span> <span data-ttu-id="70ad8-126">クライアントに大量の構造化データを格納したり、暗号化されたメディア オブジェクトなどのバイナリ データを格納したりするには `IndexedDB` 、API を使用します。</span><span class="sxs-lookup"><span data-stu-id="70ad8-126">Use the `IndexedDB` API for storing a significant amount of structured data on the client, or binary data, such as encrypted media objects.</span></span> <span data-ttu-id="70ad8-127">詳細については [、IndexedDB の使用に関する MDN の入門書に移動します][MDNIndexeddbApiUsing]。</span><span class="sxs-lookup"><span data-stu-id="70ad8-127">For more information, navigate to [MDN primer on using IndexedDB][MDNIndexeddbApiUsing].</span></span>

## <a name="understand-storage-options-for-pwas"></a><span data-ttu-id="70ad8-128">PWA のストレージ オプションについて</span><span class="sxs-lookup"><span data-stu-id="70ad8-128">Understand storage options for PWAs</span></span>

<span data-ttu-id="70ad8-129">ユーザーに優れたオフライン エクスペリエンスを提供するために、少量のデータを保存する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="70ad8-129">Sometimes you may need to store small amounts of data in order to provide a better offline experience for your users.</span></span> <span data-ttu-id="70ad8-130">その場合は、Web ストレージのキーと値のペア システムがニーズを満たしているのが簡単です。</span><span class="sxs-lookup"><span data-stu-id="70ad8-130">If that is the case, you may find the simplicity of the key-value pair system of web storage meets your needs.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="70ad8-131">Web ストレージは同期プロセスであり、Service Workers などのワーカー スレッド内では使用できません。</span><span class="sxs-lookup"><span data-stu-id="70ad8-131">Web Storage is a synchronous process and is not available for use within worker threads such as Service Workers.</span></span> <span data-ttu-id="70ad8-132">使用量が多い場合は、アプリケーションのパフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70ad8-132">Heavy usage may create performance issues for your application.</span></span> 


<span data-ttu-id="70ad8-133">Web ストレージには、次の 2 種類があります `localStorage` `sessionStorage` 。</span><span class="sxs-lookup"><span data-stu-id="70ad8-133">There are 2 types of Web Storage: `localStorage` and `sessionStorage`.</span></span> <span data-ttu-id="70ad8-134">それぞれが、作成したドメインに分離された個別のデータ ストアとして維持されます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-134">Each is maintained as a separate data store isolated to the domain that created it.</span></span> `sessionStorage` <span data-ttu-id="70ad8-135">閲覧セッションの期間中のみ保持されます (ブラウザーが開いている間など、更新と復元が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="70ad8-135">persists only for the duration of the browsing session (for example, while the browser is open, which includes refresh and restores).</span></span> `localStorage` <span data-ttu-id="70ad8-136">データがコード、ユーザー、またはブラウザーによって削除されるまで保持されます (たとえば、使用できる記憶域が限られている場合)。</span><span class="sxs-lookup"><span data-stu-id="70ad8-136">persists until the data is removed by the code, the user, or the browser (for example, when there is limited storage available).</span></span> <span data-ttu-id="70ad8-137">次のコード スニペットは、使い方に似た使 `localStorage` い方を `sessionStorage` 示しています。</span><span class="sxs-lookup"><span data-stu-id="70ad8-137">The following code snippet shows how to use `localStorage`, which is similar to how `sessionStorage` is used.</span></span>

```javascript
var data = {
    title: document.querySelector("[property='og:title']").getAttribute("content"),
    description: document.querySelector( "meta[name='description']" ).getAttribute("content")
};
localStorage.setItem( window.location, JSON.stringify(data) );
```  

<span data-ttu-id="70ad8-138">このコード スニペットは、現在のページに関するメタデータを取得し、JavaScript オブジェクトに格納します。</span><span class="sxs-lookup"><span data-stu-id="70ad8-138">This code snippet grabs metadata about the current page and stores it in a JavaScript object.</span></span> <span data-ttu-id="70ad8-139">次に、メソッドを使用してその値を JSON として格納し、現在の URL と等しいキー `localStorage` `setItem()` を割り当 `window.location` てる。</span><span class="sxs-lookup"><span data-stu-id="70ad8-139">Then it stores that value as JSON in `localStorage` using the `setItem()` method, and assigns a key equal to the current `window.location` URL.</span></span> <span data-ttu-id="70ad8-140">メソッドを使用して情報 `localStorage` を取得 `getItem()` できます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-140">You may retrieve the information from `localStorage` using the `getItem()` method.</span></span> 

<span data-ttu-id="70ad8-141">次のコード スニペットは、キャッシュを使用してキャッシュされたページを列挙し、メタデータを抽出してタスクを実行する方法 (リンクのリストの作成など) `localstorage` を示しています。</span><span class="sxs-lookup"><span data-stu-id="70ad8-141">The following code snippet shows how to use caching with `localstorage` to enumerate cached pages and extract metadata to perform a task, such as building a list of links.</span></span>

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

<span data-ttu-id="70ad8-142">この `insertOfflineLink()` メソッドは、要求の URL をメソッドに渡して `localStorage.getItem()` 、格納されているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="70ad8-142">The `insertOfflineLink()` method passes the URL of the request into the `localStorage.getItem()` method to retrieve any stored metadata.</span></span> <span data-ttu-id="70ad8-143">取得したデータが存在するかどうかを確認し、存在する場合は、マークアップを作成して表示する挿入など、データに対してアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-143">The retrieved data is checked to see if it exists, and if it does, an action can be taken on the data, such as building and inserting the markup to display it.</span></span>

## <a name="test-for-network-connections-in-your-pwa"></a><span data-ttu-id="70ad8-144">PWA でのネットワーク接続のテスト</span><span class="sxs-lookup"><span data-stu-id="70ad8-144">Test for network connections in your PWA</span></span>

<span data-ttu-id="70ad8-145">オフラインで使用する情報を保存する以外に、データを同期したり、ネットワークの状態が変更されたとユーザーに通知したりするために、ネットワーク接続がいつ利用できるのか確認すると便利です。</span><span class="sxs-lookup"><span data-stu-id="70ad8-145">In addition to storing information for offline use, it is helpful to know when a network connection is available in order to synchronize data or inform users that the network status has changed.</span></span> <span data-ttu-id="70ad8-146">ネットワーク接続をテストするには、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="70ad8-146">Use the following options to test for network connectivity.</span></span>

### <a name="navigatoronline"></a><span data-ttu-id="70ad8-147">navigator.onLine</span><span class="sxs-lookup"><span data-stu-id="70ad8-147">navigator.onLine</span></span>  

<span data-ttu-id="70ad8-148">プロパティ `navigator.onLine` は、ネットワークの現在の状態を知るブール値です。</span><span class="sxs-lookup"><span data-stu-id="70ad8-148">The `navigator.onLine` property is a boolean that lets you know the current status of the network.</span></span> <span data-ttu-id="70ad8-149">値がである場合 `true` 、ユーザーはオンラインで、それ以外の場合はユーザーはオフラインです。</span><span class="sxs-lookup"><span data-stu-id="70ad8-149">If the value is `true`, the user is online, otherwise the user is offline.</span></span>

### <a name="online-and-offline-events"></a><span data-ttu-id="70ad8-150">オンラインイベントとオフライン イベント</span><span class="sxs-lookup"><span data-stu-id="70ad8-150">Online and Offline Events</span></span>  

<span data-ttu-id="70ad8-151">ネットワークが利用できるかどうかを知るのは役に立ちますが、ネットワーク接続が変更された場合に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70ad8-151">Knowing whether the network is available is helpful, but you may want to take action  when your network connectivity changes.</span></span> <span data-ttu-id="70ad8-152">このような場合は、ネットワーク イベントに応答してリッスンしてアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-152">In this situation, you may want to listen and take action in response to network events.</span></span> <span data-ttu-id="70ad8-153">イベントは、次のコード スニペットに表示される 、、および `window` `document` `document.body` 要素で使用できます。</span><span class="sxs-lookup"><span data-stu-id="70ad8-153">The events are available on the `window`, `document`, and `document.body` elements as displayed in the following code snippet.</span></span>

```javascript
window.addEventListener("online",  function(){
    console.log("You are online!");
});
window.addEventListener("offline", function(){
    console.log("Oh no, you lost your network connection.");
});
```  

## <a name="see-also"></a><span data-ttu-id="70ad8-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="70ad8-154">See also</span></span>  

<span data-ttu-id="70ad8-155">オフライン シナリオの管理の詳細については、次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="70ad8-155">To learn more about managing offline scenarios, navigate to the following pages.</span></span>  

*   [<span data-ttu-id="70ad8-156">キャッシュ</span><span class="sxs-lookup"><span data-stu-id="70ad8-156">Cache</span></span>][MDNCache]  
*   [<span data-ttu-id="70ad8-157">IndexedDB</span><span class="sxs-lookup"><span data-stu-id="70ad8-157">IndexedDB</span></span>][MDNIndexeddbApi]  
*   [<span data-ttu-id="70ad8-158">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="70ad8-158">Service Worker</span></span>][MDNServiceWorker]  
*   [<span data-ttu-id="70ad8-159">Web ストレージ</span><span class="sxs-lookup"><span data-stu-id="70ad8-159">Web Storage</span></span>][MDNWebStorageApi]  
*   [<span data-ttu-id="70ad8-160">navigator.onLine</span><span class="sxs-lookup"><span data-stu-id="70ad8-160">navigator.onLine</span></span>][MDNNavigatoronline]  
*   [<span data-ttu-id="70ad8-161">オンラインイベントとオフライン イベント</span><span class="sxs-lookup"><span data-stu-id="70ad8-161">Online and Offline Events</span></span>][MDNNavigatoronlineOfflineEvents]  
*   [<span data-ttu-id="70ad8-162">意図を持つ要求: PWA の時代のキャッシュ戦略</span><span class="sxs-lookup"><span data-stu-id="70ad8-162">Request with Intent: Caching Strategies in the Age of PWAs</span></span>][AlistapartRequestIntentCachingStrategiesAgePwas]
    
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
