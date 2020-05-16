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
# <span data-ttu-id="9662a-104">プログレッシブ Web アプリでのオフラインおよびネットワーク接続のサポート</span><span class="sxs-lookup"><span data-stu-id="9662a-104">Offline and network connectivity support in Progressive Web Apps</span></span>

<span data-ttu-id="9662a-105">多くの場合、web アプリケーションは安定したネットワーク接続に依存しているため、web ベースのソフトウェアへの多大な投資は、組織にとってあまり厳しくありませんでした。</span><span class="sxs-lookup"><span data-stu-id="9662a-105">For many years organizations were reluctant to invest heavily in web-based software over native software because web applications depended on stable network connections.</span></span> <span data-ttu-id="9662a-106">現在、web プラットフォームでは、ネットワーク接続が不安定になった場合や完全にオフラインになった場合でも、ユーザーが作業を続けることができる堅牢なオプションが提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9662a-106">Today, the web platform now offers robust options that enable users to continue working, even if the network connection becomes unstable or goes completely offline.</span></span>

## <span data-ttu-id="9662a-107">キャッシュを使用して PWAs のパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="9662a-107">Use the caching to improve performance of PWAs</span></span>

<span data-ttu-id="9662a-108">[サービスワーカー][MDNServiceWorker]の導入により、web platform は API を追加して、 `Cache` マネージキャッシュされたリソースへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9662a-108">With the introduction of [Service Workers][MDNServiceWorker], the web platform added the `Cache` API to provide access to managed cached resources.</span></span> <span data-ttu-id="9662a-109">この Promise ベースの API を使用すると、開発者は、HTML、CSS、JavaScript、画像、JSON など、多くの web リソースを保存して取得することができます。</span><span class="sxs-lookup"><span data-stu-id="9662a-109">This Promise-based API allows developers to store and retrieve many web resources—HTML, CSS, JavaScript, images, JSON, and so on.</span></span> <span data-ttu-id="9662a-110">通常、キャッシュ API は、サービスワーカーのコンテキスト内で使用されますが、オブジェクトのメインスレッドでも使用でき `window` ます。</span><span class="sxs-lookup"><span data-stu-id="9662a-110">Usually, the Cache API is used within the context of a Service Worker, but it is also available in the main thread on the `window` object.</span></span>

<span data-ttu-id="9662a-111">API の一般的な用途の1つ `Cache` は、次のコードスニペットに示すように、サービスワーカーのインストール時に重要なリソースを事前にキャッシュすることです。</span><span class="sxs-lookup"><span data-stu-id="9662a-111">One common use for the `Cache` API is to pre-cache critical resources when a Service Worker is installed, as shown in the following code snippet.</span></span>  

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

<span data-ttu-id="9662a-112">このコードは、サービスワーカーのライフサイクルイベント中に実行され、キャッシュの `install` 名前が付けら `static-cache` れ、キャッシュへのポインターがある場合に、このメソッドを使って4つのリソースを追加し `addAll()` ます。</span><span class="sxs-lookup"><span data-stu-id="9662a-112">This code, which runs during the Service Worker `install` life cycle event, opens a cache named `static-cache` and then, when it has a pointer to the cache, adds four resources to it using the `addAll()` method.</span></span>  <span data-ttu-id="9662a-113">このアプローチは、多くの場合、イベント中のキャッシュ取得と組み合わされています。 `fetch`</span><span class="sxs-lookup"><span data-stu-id="9662a-113">Often the approach is coupled with cache retrieval during a `fetch` event</span></span>   

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

<span data-ttu-id="9662a-114">このコードスニペットは、ブラウザーからこのサイトへの要求が行われるたびに、サービスワーカー内で実行され `fetch` ます。</span><span class="sxs-lookup"><span data-stu-id="9662a-114">The code snippet runs within the Service Worker whenever the browser makes a `fetch` request for this site.</span></span> <span data-ttu-id="9662a-115">このイベント内には、要求が HTML ファイルを対象としている場合に実行される条件付きステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="9662a-115">Within that event, there is a conditional statement that runs if the request is for an HTML file.</span></span> <span data-ttu-id="9662a-116">サービスワーカーは、ファイルが既にいずれかのキャッシュに存在するかどうかを確認し `match()` ます (メソッド \ を使用)。</span><span class="sxs-lookup"><span data-stu-id="9662a-116">The Service Worker checks to see if the file already exists in any cache \(using the `match()` method\).</span></span> <span data-ttu-id="9662a-117">要求がキャッシュ内に存在する場合、キャッシュされた結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="9662a-117">If the request exists in the cache, that cached result is returned.</span></span> <span data-ttu-id="9662a-118">存在しない場合、 `fetch` そのリソースの新しい動作が実行されると、後で応答のコピーがキャッシュされ、応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="9662a-118">If not, a new `fetch` for that resource is run, a copy of the response is cached for later, and the response is returned.</span></span> <span data-ttu-id="9662a-119">`fetch`ネットワークが利用できないために失敗した場合は、オフラインページがキャッシュから返されます。</span><span class="sxs-lookup"><span data-stu-id="9662a-119">If the `fetch` fails because the network is unavailable, the offline page is returned from the cache.</span></span>

<span data-ttu-id="9662a-120">この簡単な概要では、プログレッシブ web アプリ (PWA) でキャッシュを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9662a-120">This simple introduction shows how to use caching in your progressive web app (PWA).</span></span> <span data-ttu-id="9662a-121">各 PWA は異なっていて、異なるキャッシュ計画を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9662a-121">Each PWA is different and may use different caching strategies.</span></span> <span data-ttu-id="9662a-122">コードによって表示が異なる場合があり、同じアプリケーション内のさまざまなルートに異なるキャッシュ計画を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="9662a-122">Your code may look different, and you may use different caching strategies for different routes within the same application.</span></span>

## <span data-ttu-id="9662a-123">PWA で IndexedDB を使って構造化データを保存する</span><span class="sxs-lookup"><span data-stu-id="9662a-123">Use IndexedDB in your PWA to store structured data</span></span>

`IndexedDB` <span data-ttu-id="9662a-124">構造化データを保存するための API です。</span><span class="sxs-lookup"><span data-stu-id="9662a-124">is an API for storing structured data.</span></span> <span data-ttu-id="9662a-125">API と似 `Cache` ていますが、非同期でもあります。これは、メインスレッドまたはサービスワーカーなどの Web ワーカーで使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9662a-125">Similar to the `Cache` API, it is also asynchronous, which means you may use it in the main thread or with Web Workers such as Service Workers.</span></span> <span data-ttu-id="9662a-126">API を使って、 `IndexedDB` 大量の構造化データをクライアントに保存するか、暗号化されたメディアオブジェクトなどのバイナリデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="9662a-126">Use the `IndexedDB` API for storing a significant amount of structured data on the client, or binary data, such as encrypted media objects.</span></span> <span data-ttu-id="9662a-127">詳細については、「 [IndexedDB を使った MDN 入門][MDNIndexeddbApiUsing]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9662a-127">For more information, see [MDN primer on using IndexedDB][MDNIndexeddbApiUsing].</span></span>

## <span data-ttu-id="9662a-128">PWAs のストレージオプションについて</span><span class="sxs-lookup"><span data-stu-id="9662a-128">Understand storage options for PWAs</span></span>

<span data-ttu-id="9662a-129">ユーザーに最適なオフライン操作を提供するために、少量のデータを保存しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9662a-129">Sometimes you may need to store small amounts of data in order to provide a better offline experience for your users.</span></span> <span data-ttu-id="9662a-130">このような場合は、web storage のキーと値のペアシステムのシンプルさがニーズを満たしていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9662a-130">If that is the case, you may find the simplicity of the key-value pair system of web storage meets your needs.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="9662a-131">Web ストレージは同期プロセスであり、サービスワーカーなどのワーカースレッド内では使用できません。</span><span class="sxs-lookup"><span data-stu-id="9662a-131">Web Storage is a synchronous process and is not available for use within worker threads such as Service Workers.</span></span> <span data-ttu-id="9662a-132">使用頻度が高いと、アプリケーションのパフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9662a-132">Heavy usage may create performance issues for your application.</span></span> 


<span data-ttu-id="9662a-133">Web Storage には、との2種類があり `localStorage` `sessionStorage` ます。</span><span class="sxs-lookup"><span data-stu-id="9662a-133">There are 2 types of Web Storage: `localStorage` and `sessionStorage`.</span></span> <span data-ttu-id="9662a-134">それぞれは、それを作成したドメインに対して分離された個別のデータストアとして管理されます。</span><span class="sxs-lookup"><span data-stu-id="9662a-134">Each is maintained as a separate data store isolated to the domain that created it.</span></span> `sessionStorage` <span data-ttu-id="9662a-135">閲覧セッションの期間のみ保持されます (たとえば、ブラウザーが開かれている間のみ、更新と復元が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="9662a-135">persists only for the duration of the browsing session (for example, while the browser is open, which includes refresh and restores).</span></span> `localStorage` <span data-ttu-id="9662a-136">データが、コード、ユーザー、ブラウザーによって削除されるまで保持されます (たとえば、利用可能なストレージが限られている場合)。</span><span class="sxs-lookup"><span data-stu-id="9662a-136">persists until the data is removed by the code, the user, or the browser (for example, when there is limited storage available).</span></span> <span data-ttu-id="9662a-137">次のコードスニペットは、の使い方と似ています。これを使う方法を示してい `localStorage` `sessionStorage` ます。</span><span class="sxs-lookup"><span data-stu-id="9662a-137">The following code snippet shows how to use `localStorage`, which is similar to how `sessionStorage` is used.</span></span>

```javascript
var data = {
    title: document.querySelector("[property='og:title']").getAttribute("content"),
    description: document.querySelector( "meta[name='description']" ).getAttribute("content")
};
localStorage.setItem( window.location, JSON.stringify(data) );
```  

<span data-ttu-id="9662a-138">このコードスニペットは、現在のページに関するメタデータを取得し、JavaScript オブジェクトに格納します。</span><span class="sxs-lookup"><span data-stu-id="9662a-138">This code snippet grabs metadata about the current page and stores it in a JavaScript object.</span></span> <span data-ttu-id="9662a-139">次に、メソッドを使用してその値を JSON として保存 `localStorage` `setItem()` し、現在の URL に等しいキーを割り当て `window.location` ます。</span><span class="sxs-lookup"><span data-stu-id="9662a-139">Then it stores that value as JSON in `localStorage` using the `setItem()` method, and assigns a key equal to the current `window.location` URL.</span></span> <span data-ttu-id="9662a-140">メソッドを使用して情報を取得することができ `localStorage` `getItem()` ます。</span><span class="sxs-lookup"><span data-stu-id="9662a-140">You may retrieve the information from `localStorage` using the `getItem()` method.</span></span> 

<span data-ttu-id="9662a-141">次のコードスニペットは、キャッシュされた `localstorage` ページを列挙し、メタデータを抽出して、リンクの一覧の作成などの作業を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9662a-141">The following code snippet shows how to use caching with `localstorage` to enumerate cached pages and extract metadata to perform a task, such as building a list of links.</span></span>

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

<span data-ttu-id="9662a-142">メソッドは、 `insertOfflineLink()` `localStorage.getItem()` 保存されているメタデータを取得するために、要求の URL をメソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="9662a-142">The `insertOfflineLink()` method passes the URL of the request into the `localStorage.getItem()` method to retrieve any stored metadata.</span></span> <span data-ttu-id="9662a-143">取得したデータが存在するかどうかが確認され、存在する場合は、表示するためのマークアップの作成や挿入などの操作をデータに対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="9662a-143">The retrieved data is checked to see if it exists, and if it does, an action can be taken on the data, such as building and inserting the markup to display it.</span></span>

## <span data-ttu-id="9662a-144">PWA のネットワーク接続をテストする</span><span class="sxs-lookup"><span data-stu-id="9662a-144">Test for network connections in your PWA</span></span>

<span data-ttu-id="9662a-145">オフラインで使用するための情報を保存するだけでなく、データを同期したり、ネットワークの状態が変わったことをユーザーに通知したりするために、ネットワーク接続が利用可能になっているかどうかを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="9662a-145">In addition to storing information for offline use, it is helpful to know when a network connection is available in order to synchronize data or inform users that the network status has changed.</span></span> <span data-ttu-id="9662a-146">ネットワーク接続をテストするには、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9662a-146">Use the following options to test for network connectivity.</span></span>

### <span data-ttu-id="9662a-147">ナビゲーター。オンライン</span><span class="sxs-lookup"><span data-stu-id="9662a-147">navigator.onLine</span></span>  

<span data-ttu-id="9662a-148">`navigator.onLine`プロパティは、ネットワークの現在の状態を知ることができるブール値です。</span><span class="sxs-lookup"><span data-stu-id="9662a-148">The `navigator.onLine` property is a boolean that lets you know the current status of the network.</span></span> <span data-ttu-id="9662a-149">値がの場合は、ユーザーがオンラインであるかどうかを示し `true` ます。それ以外の場合は、ユーザーがオフラインになります。</span><span class="sxs-lookup"><span data-stu-id="9662a-149">If the value is `true`, the user is online, otherwise the user is offline.</span></span>

### <span data-ttu-id="9662a-150">オンラインイベントとオフラインイベント</span><span class="sxs-lookup"><span data-stu-id="9662a-150">Online and Offline Events</span></span>  

<span data-ttu-id="9662a-151">ネットワークが利用可能であるかどうかを知ることは有用ですが、ネットワーク接続が変更されたときに対処することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9662a-151">Knowing whether the network is available is helpful, but you may want to take action  when your network connectivity changes.</span></span> <span data-ttu-id="9662a-152">この状況では、ネットワークイベントに応答してリッスンし、操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9662a-152">In this situation, you may want to listen and take action in response to network events.</span></span> <span data-ttu-id="9662a-153">イベントは、、 `window` `document` および要素で、次のコードスニペットのように表示され `document.body` ます。</span><span class="sxs-lookup"><span data-stu-id="9662a-153">The events are available on the `window`, `document`, and `document.body` elements as displayed in the following code snippet.</span></span>

```javascript
window.addEventListener("online",  function(){
    console.log("You are online!");
});
window.addEventListener("offline", function(){
    console.log("Oh no, you lost your network connection.");
});
```  

## <span data-ttu-id="9662a-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="9662a-154">See also</span></span>  

<span data-ttu-id="9662a-155">オフラインシナリオの管理の詳細については、次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9662a-155">To learn more about managing offline scenarios, see the following pages.</span></span>  

*   [<span data-ttu-id="9662a-156">キャッシュ</span><span class="sxs-lookup"><span data-stu-id="9662a-156">Cache</span></span>][MDNCache]  
*   [<span data-ttu-id="9662a-157">IndexedDB</span><span class="sxs-lookup"><span data-stu-id="9662a-157">IndexedDB</span></span>][MDNIndexeddbApi]  
*   [<span data-ttu-id="9662a-158">サービスワーカー</span><span class="sxs-lookup"><span data-stu-id="9662a-158">Service Worker</span></span>][MDNServiceWorker]  
*   [<span data-ttu-id="9662a-159">Web ストレージ</span><span class="sxs-lookup"><span data-stu-id="9662a-159">Web Storage</span></span>][MDNWebStorageApi]  
*   [<span data-ttu-id="9662a-160">ナビゲーター。オンライン</span><span class="sxs-lookup"><span data-stu-id="9662a-160">navigator.onLine</span></span>][MDNNavigatoronline]  
*   [<span data-ttu-id="9662a-161">オンラインイベントとオフラインイベント</span><span class="sxs-lookup"><span data-stu-id="9662a-161">Online and Offline Events</span></span>][MDNNavigatoronlineOfflineEvents]  
*   [<span data-ttu-id="9662a-162">インテントの要求: PWAs のキャッシュ計画</span><span class="sxs-lookup"><span data-stu-id="9662a-162">Request with Intent: Caching Strategies in the Age of PWAs</span></span>][AlistapartRequestIntentCachingStrategiesAgePwas]

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
