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
# <a name="use-service-workers-to-manage-network-requests-and-push-notifications"></a><span data-ttu-id="20623-104">サービス ワーカーを使用してネットワーク要求とプッシュ通知を管理する</span><span class="sxs-lookup"><span data-stu-id="20623-104">Use Service Workers to manage network requests and push notifications</span></span>

<span data-ttu-id="20623-105">サービス ワーカーは、API を使用してすべてのネットワーク要求を傍受、変更、および応答できる特別な種類の `Fetch` Web ワーカーです。</span><span class="sxs-lookup"><span data-stu-id="20623-105">Service Workers are a special type of Web Worker with the ability to intercept, modify, and respond to all network requests using the `Fetch` API.</span></span>  <span data-ttu-id="20623-106">サービス ワーカーは、API や非同期クライアント側のデータ ストア (リソースを格納するなど `Cache` `IndexedDB` ) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="20623-106">Service Workers can access the `Cache` API, and asynchronous client-side data stores, such as `IndexedDB`, to store resources.</span></span>  

## <a name="registering-a-service-worker"></a><span data-ttu-id="20623-107">サービス ワーカーの登録</span><span class="sxs-lookup"><span data-stu-id="20623-107">Registering a Service Worker</span></span>  

<span data-ttu-id="20623-108">他の Web ワーカーと同様に、サービス ワーカーは別のファイルに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20623-108">Similar to other Web Workers, Service Workers must exist in a separate file.</span></span> <span data-ttu-id="20623-109">次のコード スニペットに示すように、Service Worker を登録するときにこのファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="20623-109">You reference this file when registering the Service Worker, as shown in the following code snippet.</span></span>  

```javascript
if ( "serviceWorker" in navigator ) {
    navigator.serviceWorker.register( "/serviceworker.min.js" );
}
```  

<span data-ttu-id="20623-110">最新のブラウザーでは、Service Workers のサポートレベルが異なります。</span><span class="sxs-lookup"><span data-stu-id="20623-110">Modern browsers provide different levels of support for Service Workers.</span></span> <span data-ttu-id="20623-111">そのため、サービス ワーカー関連のコードを実行する前に、オブジェクトの存在を `serviceWorker` テストしてください。</span><span class="sxs-lookup"><span data-stu-id="20623-111">As such, it is a good practice to test for the existence of the `serviceWorker` object before running any Service Worker-related code.</span></span> <span data-ttu-id="20623-112">上記のコード スニペットでは、サービス ワーカーがサイトのルートにあるファイルを使用 `serviceworker.min.js` して登録されます。</span><span class="sxs-lookup"><span data-stu-id="20623-112">In the above code snippet, a Service Worker is registered using the `serviceworker.min.js` file located at the root of the site.</span></span> <span data-ttu-id="20623-113">サービス ワーカーを定義する JavaScript ファイルが、\(Service Worker\のスコープと呼ばれます) を管理する最高レベルのディレクトリに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="20623-113">Ensure that the JavaScript file that defines your Service Worker exists in the highest-level directory that you want it to manage \(which is referred to as the scope of the Service Worker\).</span></span>  <span data-ttu-id="20623-114">前のコード スニペットでは、ファイルはルートに格納され、Service Worker はドメイン内のすべてのページを管理します。</span><span class="sxs-lookup"><span data-stu-id="20623-114">In the previous code snippet, the file is stored in the root, and the Service Worker manages all pages in the domain.</span></span> <span data-ttu-id="20623-115">Service Worker ファイルがディレクトリに格納されている場合、Service Worker のスコープはディレクトリと `js` `js` サブディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="20623-115">If the Service Worker file was stored in a `js` directory, the scope of the Service Worker would be the `js` directory and any subdirectories.</span></span>  <span data-ttu-id="20623-116">ベスト プラクティスとして、サービス ワーカーの範囲を減らす必要がない限り、サービス ワーカー ファイルをサイトのルートに配置します。</span><span class="sxs-lookup"><span data-stu-id="20623-116">As a best practice, place the Service Worker file in the root of your site, unless you need to reduce the scope of your Service Worker.</span></span>  

## <a name="the-service-worker-lifecycle"></a><span data-ttu-id="20623-117">Service Worker のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="20623-117">The Service Worker lifecycle</span></span>  

<span data-ttu-id="20623-118">Service Worker のライフサイクルは複数の手順で構成されます。各手順でイベントがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="20623-118">The lifecycle of a Service Worker consists of multiple steps, with each step triggering an event.</span></span> <span data-ttu-id="20623-119">これらのイベントにリスナーを追加して、アクションを実行するコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="20623-119">You can add listeners to these events to run code to perform an action.</span></span> <span data-ttu-id="20623-120">次の一覧は、サービス ワーカーのライフサイクルと関連イベントの大きなレベルのビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="20623-120">The following list presents a high-level view of the lifecycle and related events of service workers.</span></span> 

1.  <span data-ttu-id="20623-121">サービス ワーカーを登録します。</span><span class="sxs-lookup"><span data-stu-id="20623-121">Register the Service Worker.</span></span>  
1.  <span data-ttu-id="20623-122">ブラウザーは JavaScript ファイルをダウンロードし、Service Worker をインストールし、イベントをトリガー `install` します。</span><span class="sxs-lookup"><span data-stu-id="20623-122">The browser downloads the JavaScript file, installs the Service Worker, and triggers the `install` event.</span></span> <span data-ttu-id="20623-123">このイベントを使用して、CSS ファイル、JavaScript ファイル、ロゴ イメージ、オフライン ページなど、重要で長命なファイルを Web サイトから事前に `install` キャッシュできます。</span><span class="sxs-lookup"><span data-stu-id="20623-123">You can use the `install` event to pre-cache any important and long-lived files, such as CSS files, JavaScript files, logo images, offline pages, and so on from your website.</span></span>  
    
    ```javascript
    self.addEventListener( "install", function( event ){
        console.log( "WORKER: install event in progress." );
    });
    ```  
    
1.  <span data-ttu-id="20623-124">サービス ワーカーがアクティブ化され、イベントがトリガー `activate` されます。</span><span class="sxs-lookup"><span data-stu-id="20623-124">The Service Worker is activated, which triggers the `activate` event.</span></span>  <span data-ttu-id="20623-125">古いキャッシュをクリーンアップするには、このイベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="20623-125">Use this event to clean up outdated caches.</span></span>  
    
    ```javascript
    self.addEventListener( "activate", event => {
        console.log('WORKER: activate event in progress.');
    });
    ```  
    
1.  <span data-ttu-id="20623-126">サービス ワーカーは、ページが更新された場合、またはユーザーがサイト上の新しいページに移動するときに実行する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="20623-126">The Service Worker is ready to run when the page is refreshed or when the user navigates to a new page on the site.</span></span> <span data-ttu-id="20623-127">待機せずに Service Worker を実行する場合は、イベント中 `self.skipWaiting()` にメソッドを使用 `install` します。</span><span class="sxs-lookup"><span data-stu-id="20623-127">If you want to run the Service Worker without waiting, use the `self.skipWaiting()` method during the `install` event.</span></span>  
    
    ```javascript
    self.addEventListener( "install", event => {
        self.skipWaiting();
        // …
    });
    ```
    
1.  <span data-ttu-id="20623-128">サービス ワーカーが実行中です。</span><span class="sxs-lookup"><span data-stu-id="20623-128">The Service Worker is now running.</span></span>     
    
## <a name="using-fetch-in-service-workers"></a><span data-ttu-id="20623-129">Service Workers でのフェッチの使用</span><span class="sxs-lookup"><span data-stu-id="20623-129">Using fetch in Service Workers</span></span>  

<span data-ttu-id="20623-130">Service Worker で使用する主なイベントはイベント `fetch` です。</span><span class="sxs-lookup"><span data-stu-id="20623-130">The main event that you use in a Service Worker is the `fetch` event.</span></span>  <span data-ttu-id="20623-131">このイベントは、ブラウザーが Service Worker のスコープ内のコンテンツにアクセスしようと試みる `fetch` 度に実行されます。</span><span class="sxs-lookup"><span data-stu-id="20623-131">The `fetch` event runs every time the browser attempts to access content within the scope of the Service Worker.</span></span> <span data-ttu-id="20623-132">次のコード スニペットは、フェッチ イベントにリスナーを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="20623-132">The following code snippet shows how to add a listener to the fetch event.</span></span>  

```javascript
self.addEventListener( "fetch", event => {
  console.log('WORKER: Fetching', event.request);
});
```  

<span data-ttu-id="20623-133">ハンドラー内で、要求がネットワークに送信され、キャッシュからプルされるかどうかを `fetch` 制御できます。</span><span class="sxs-lookup"><span data-stu-id="20623-133">Within the `fetch` handler, you may control whether a request goes to the network, pulls from the cache, and so on.</span></span>  <span data-ttu-id="20623-134">使用する方法は、要求されるリソースの種類、更新頻度、およびアプリケーション固有の他のビジネス ロジックによって異なります。</span><span class="sxs-lookup"><span data-stu-id="20623-134">The approach you take likely varies based upon the type of resource being requested, how frequently it is updated, and other business logic unique to your application.</span></span>  <span data-ttu-id="20623-135">次に、実行する操作の例を示します。</span><span class="sxs-lookup"><span data-stu-id="20623-135">Here are a few examples of what you may do:</span></span>  

*   <span data-ttu-id="20623-136">使用可能な場合は、キャッシュからの応答を返し、それ以外の場合はフォールバックしてネットワーク上でリソースを要求します。</span><span class="sxs-lookup"><span data-stu-id="20623-136">If available, return a response from the cache, otherwise fallback to request the resource over the network.</span></span>  
*   <span data-ttu-id="20623-137">ネットワークからリソースを取得し、コピーをキャッシュし、応答を返します。</span><span class="sxs-lookup"><span data-stu-id="20623-137">Fetch a resource from the network, cache a copy, and return the response.</span></span>
*   <span data-ttu-id="20623-138">ユーザーがデータを保存する基本設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="20623-138">Allow user's to specify a preference to save data.</span></span> 
*   <span data-ttu-id="20623-139">特定のイメージ要求のプレースホルダー イメージを指定します。</span><span class="sxs-lookup"><span data-stu-id="20623-139">Supply a placeholder image for certain image requests.</span></span>  
*   <span data-ttu-id="20623-140">サービス ワーカーで直接応答を生成します。</span><span class="sxs-lookup"><span data-stu-id="20623-140">Generate a response directly in the Service Worker.</span></span>  
    
## <a name="push-notifications"></a><span data-ttu-id="20623-141">プッシュ通知</span><span class="sxs-lookup"><span data-stu-id="20623-141">Push Notifications</span></span>  

<span data-ttu-id="20623-142">サービス ワーカーは、ユーザーに通知をプッシュできます。</span><span class="sxs-lookup"><span data-stu-id="20623-142">Service workers can push notifications to users.</span></span> <span data-ttu-id="20623-143">プッシュ通知は、しばらく時間が経過した後にアプリケーションに再び参加するようにユーザーに促す場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20623-143">Push Notifications are helpful to prompt users to re-engage with your application after some time has elapsed.</span></span> <span data-ttu-id="20623-144">詳細については、「プッシュ通知のチュートリアル [とデモ」に移動します][AzurewebsitesWebpushdemo]。</span><span class="sxs-lookup"><span data-stu-id="20623-144">For more information, navigate to [Push Notifications walkthrough and demo][AzurewebsitesWebpushdemo].</span></span>  

## <a name="see-also"></a><span data-ttu-id="20623-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="20623-145">See also</span></span>  

<span data-ttu-id="20623-146">Service Workers の詳細については、次の関連トピックの一覧に移動します。</span><span class="sxs-lookup"><span data-stu-id="20623-146">To learn more about Service Workers, navigate to the following list of related topics.</span></span>  

*   [<span data-ttu-id="20623-147">サービス ワーカーと PWA をオフラインで動作する</span><span class="sxs-lookup"><span data-stu-id="20623-147">Making PWAs work offline with Service workers</span></span>][MDNPwasMakingOfflineServiceWorkers]  
*   [<span data-ttu-id="20623-148">通知とプッシュを使用して PWA を再エンゲージする方法</span><span class="sxs-lookup"><span data-stu-id="20623-148">How to make PWAs re-engageable using Notifications and Push</span></span>][MDNPwasMakeReengageablesingNotificationsPush]  
    
<!-- links -->  

[AzurewebsitesWebpushdemo]: https://webpushdemo.azurewebsites.net "Web プッシュ通知| Microsoft Edge デモ"  

[MDNPwasMakingOfflineServiceWorkers]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Offline_Service_workers "サービス ワーカーと一緒に PWA をオフラインで動作する - PWA |MDN"  
[MDNPwasMakeReengageablesingNotificationsPush]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Re-engageable_Notifications_Push "通知とプッシュを使用して PWA を再びエンゲージする方法 - PWA |MDN"  
