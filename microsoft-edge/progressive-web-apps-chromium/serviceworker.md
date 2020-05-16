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
# <span data-ttu-id="8ffca-104">サービスワーカーを使ってネットワーク要求とプッシュ通知を管理する</span><span class="sxs-lookup"><span data-stu-id="8ffca-104">Use Service Workers to manage network requests and push notifications</span></span>

<span data-ttu-id="8ffca-105">サービスワーカーは、API を使ってすべてのネットワーク要求を傍受、変更、応答することができる特殊な種類の Web ワーカーです `Fetch` 。</span><span class="sxs-lookup"><span data-stu-id="8ffca-105">Service Workers are a special type of Web Worker with the ability to intercept, modify, and respond to all network requests using the `Fetch` API.</span></span>  <span data-ttu-id="8ffca-106">サービスワーカーは、 `Cache` `IndexedDB` リソースを格納するために、API と非同期クライアント側データストアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-106">Service Workers can access the `Cache` API, and asynchronous client-side data stores, such as `IndexedDB`, to store resources.</span></span>  

## <span data-ttu-id="8ffca-107">サービスワーカーの登録</span><span class="sxs-lookup"><span data-stu-id="8ffca-107">Registering a Service Worker</span></span>  

<span data-ttu-id="8ffca-108">他の Web ワーカーと同様に、サービスワーカーは別のファイル内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ffca-108">Similar to other Web Workers, Service Workers must exist in a separate file.</span></span> <span data-ttu-id="8ffca-109">このファイルは、次のコードスニペットに示すように、サービスワーカーを登録するときに参照します。</span><span class="sxs-lookup"><span data-stu-id="8ffca-109">You reference this file when registering the Service Worker, as shown in the following code snippet.</span></span>  

```javascript
if ( "serviceWorker" in navigator ) {
    navigator.serviceWorker.register( "/serviceworker.min.js" );
}
```  

<span data-ttu-id="8ffca-110">最新のブラウザーには、サービスワーカー向けにさまざまなレベルのサポートが用意しています。</span><span class="sxs-lookup"><span data-stu-id="8ffca-110">Modern browsers provide different levels of support for Service Workers.</span></span> <span data-ttu-id="8ffca-111">このため、 `serviceWorker` サービスワーカーに関連するコードを実行する前に、オブジェクトが存在するかどうかをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ffca-111">As such, it is a good practice to test for the existence of the `serviceWorker` object before running any Service Worker-related code.</span></span> <span data-ttu-id="8ffca-112">上のコードスニペットでは、サービスワーカーは、 `serviceworker.min.js` サイトのルートにあるファイルを使って登録されています。</span><span class="sxs-lookup"><span data-stu-id="8ffca-112">In the above code snippet, a Service Worker is registered using the `serviceworker.min.js` file located at the root of the site.</span></span> <span data-ttu-id="8ffca-113">サービスワーカーを定義する JavaScript ファイルが、管理対象の最上位ディレクトリ (サービスワーカーの範囲として参照されます) に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ffca-113">Ensure that the JavaScript file that defines your Service Worker exists in the highest-level directory that you want it to manage \(which is referred to as the scope of the Service Worker\).</span></span>  <span data-ttu-id="8ffca-114">上のコードスニペットでは、ファイルがルートに保存され、サービスワーカーがドメイン内のすべてのページを管理します。</span><span class="sxs-lookup"><span data-stu-id="8ffca-114">In the above code snippet, the file is stored in the root, and the Service Worker manages all pages in the domain.</span></span> <span data-ttu-id="8ffca-115">サービスワーカーファイルがディレクトリに保存されていた場合 `js` 、サービスワーカーのスコープは `js` ディレクトリとサブディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="8ffca-115">If the Service Worker file was stored in a `js` directory, the scope of the Service Worker would be the `js` directory and any subdirectories.</span></span>  <span data-ttu-id="8ffca-116">サービスワーカーのスコープを減らす必要がある場合を除き、サービスワーカーファイルは、サイトのルートに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ffca-116">As a best practice, place the Service Worker file in the root of your site, unless you need to reduce the scope of your Service Worker.</span></span>  

## <span data-ttu-id="8ffca-117">サービスワーカーのライフサイクル</span><span class="sxs-lookup"><span data-stu-id="8ffca-117">The Service Worker lifecycle</span></span>  

<span data-ttu-id="8ffca-118">サービスワーカーのライフサイクルは、複数のステップで構成され、各手順でイベントがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-118">The lifecycle of a Service Worker consists of multiple steps, with each step triggering an event.</span></span> <span data-ttu-id="8ffca-119">これらのイベントにリスナーを追加して、操作を実行するためのコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-119">You can add listeners to these events to run code to perform an action.</span></span> <span data-ttu-id="8ffca-120">次の一覧は、service worker のライフサイクルと関連イベントの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="8ffca-120">The following list presents a high-level view of the lifecycle and related events of service workers.</span></span> 

1. <span data-ttu-id="8ffca-121">サービスワーカーを登録します。</span><span class="sxs-lookup"><span data-stu-id="8ffca-121">Register the Service Worker.</span></span>  
1.  <span data-ttu-id="8ffca-122">ブラウザーは、JavaScript ファイルをダウンロードし、サービスワーカーをインストールし、イベントをトリガーし `install` ます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-122">The browser downloads the JavaScript file, installs the Service Worker, and triggers the `install` event.</span></span> <span data-ttu-id="8ffca-123">`install`このイベントを使うと、web サイトから CSS ファイル、JavaScript ファイル、ロゴ画像、オフラインページなど、重要な有効期間が長いファイルを事前にキャッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-123">You can use the `install` event to pre-cache any important and long-lived files, such as CSS files, JavaScript files, logo images, offline pages, and so on from your website.</span></span>  
    
    ```javascript
    self.addEventListener( "install", function( event ){
        console.log( "WORKER: install event in progress." );
    });
    ```  
    
1.  <span data-ttu-id="8ffca-124">サービスワーカーがアクティブになり、イベントがトリガーされ `activate` ます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-124">The Service Worker is activated, which triggers the `activate` event.</span></span>  <span data-ttu-id="8ffca-125">このイベントを使用して、古いキャッシュをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="8ffca-125">Use this event to clean up outdated caches.</span></span>  
    
    ```javascript
    self.addEventListener( "activate", event => {
        console.log('WORKER: activate event in progress.');
    });
    ```  
    
1.  <span data-ttu-id="8ffca-126">サービスワーカーは、ページが更新されたとき、またはユーザーがサイト上の新しいページに移動したときに実行する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="8ffca-126">The Service Worker is ready to run when the page is refreshed or when the user navigates to a new page on the site.</span></span> <span data-ttu-id="8ffca-127">サービスワーカーを待機させずに実行する場合は、 `self.skipWaiting()` イベント中にメソッドを使い `install` ます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-127">If you want to run the Service Worker without waiting, use the `self.skipWaiting()` method during the `install` event.</span></span>  
    
    ```javascript
    self.addEventListener( "install", event => {
        self.skipWaiting();
        // …
    });
    ```
    
1.  <span data-ttu-id="8ffca-128">現在、サービスワーカーを実行しています。</span><span class="sxs-lookup"><span data-stu-id="8ffca-128">The Service Worker is now running.</span></span>     
    
## <span data-ttu-id="8ffca-129">サービスワーカーでの fetch の使用</span><span class="sxs-lookup"><span data-stu-id="8ffca-129">Using fetch in Service Workers</span></span>  

<span data-ttu-id="8ffca-130">サービスワーカーで使用する主なイベントは、 `fetch` イベントです。</span><span class="sxs-lookup"><span data-stu-id="8ffca-130">The main event that you use in a Service Worker is the `fetch` event.</span></span>  <span data-ttu-id="8ffca-131">イベントは、 `fetch` ブラウザーがサービスワーカーのスコープ内でコンテンツにアクセスしようとするたびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-131">The `fetch` event runs every time the browser attempts to access content within the scope of the Service Worker.</span></span> <span data-ttu-id="8ffca-132">次のコードスニペットは、リスナーを fetch イベントに追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8ffca-132">The following code snippet shows how to add a listener to the fetch event.</span></span>  

```javascript
self.addEventListener( "fetch", event => {
  console.log('WORKER: Fetching', event.request);
});
```  

<span data-ttu-id="8ffca-133">ハンドラー内で、 `fetch` 要求がネットワークに送られるか、キャッシュから取得するかなどを制御できます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-133">Within the `fetch` handler, you may control whether a request goes to the network, pulls from the cache, and so on.</span></span>  <span data-ttu-id="8ffca-134">目的のアプローチは、要求されているリソースの種類、更新頻度、およびアプリケーションに固有の他のビジネスロジックによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8ffca-134">The approach you take likely varies based upon the type of resource being requested, how frequently it is updated, and other business logic unique to your application.</span></span>  <span data-ttu-id="8ffca-135">次に、実行できる操作の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="8ffca-135">Here are a few examples of what you may do:</span></span>  

*   <span data-ttu-id="8ffca-136">可能であれば、キャッシュから応答を返します。それ以外の場合は、ネットワーク経由でリソースを要求するためにフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="8ffca-136">If available, return a response from the cache, otherwise fallback to request the resource over the network.</span></span>  
*   <span data-ttu-id="8ffca-137">ネットワークからリソースを取得し、コピーをキャッシュして、応答を返します。</span><span class="sxs-lookup"><span data-stu-id="8ffca-137">Fetch a resource from the network, cache a copy, and return the response.</span></span>
*   <span data-ttu-id="8ffca-138">ユーザーがデータを保存するための環境設定を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ffca-138">Allow user's to specify a preference to save data.</span></span> 
*   <span data-ttu-id="8ffca-139">特定の画像要求のプレースホルダー画像を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ffca-139">Supply a placeholder image for certain image requests.</span></span>  
*   <span data-ttu-id="8ffca-140">サービスワーカーで直接応答を生成します。</span><span class="sxs-lookup"><span data-stu-id="8ffca-140">Generate a response directly in the Service Worker.</span></span>  

## <span data-ttu-id="8ffca-141">プッシュ通知</span><span class="sxs-lookup"><span data-stu-id="8ffca-141">Push Notifications</span></span>  

<span data-ttu-id="8ffca-142">サービスワーカーは通知をユーザーにプッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-142">Service workers can push notifications to users.</span></span> <span data-ttu-id="8ffca-143">プッシュ通知は、一定の時間が経過した後に、ユーザーにアプリケーションの再利用を促すために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8ffca-143">Push Notifications are helpful to prompt users to re-engage with your application after some time has elapsed.</span></span> <span data-ttu-id="8ffca-144">詳細については、「[プッシュ通知のチュートリアルとデモ][AzurewebsitesWebpushdemo]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ffca-144">For more information, see [Push Notifications walkthrough and demo][AzurewebsitesWebpushdemo].</span></span>  

## <span data-ttu-id="8ffca-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ffca-145">See also</span></span>  

<span data-ttu-id="8ffca-146">サービスワーカーの詳細については、次の関連するトピックの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ffca-146">To learn more about Service Workers, see the following list of related topics.</span></span>  

*   [<span data-ttu-id="8ffca-147">Service worker で PWAs をオフライン作業する</span><span class="sxs-lookup"><span data-stu-id="8ffca-147">Making PWAs work offline with Service workers</span></span>][MDNPwasMakingOfflineServiceWorkers]  
*   [<span data-ttu-id="8ffca-148">通知とプッシュを使用して PWAs を再作成する方法</span><span class="sxs-lookup"><span data-stu-id="8ffca-148">How to make PWAs re-engageable using Notifications and Push</span></span>][MDNPwasMakeReengageablesingNotificationsPush]  

<!-- links -->  

[AzurewebsitesWebpushdemo]: https://webpushdemo.azurewebsites.net "Web プッシュ通知 | Microsoft Edge のデモ"  

[MDNPwasMakingOfflineServiceWorkers]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Offline_Service_workers "サービスワーカーで PWAs をオフラインで操作しました-PWAs |MDN"  
[MDNPwasMakeReengageablesingNotificationsPush]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Re-engageable_Notifications_Push "通知を使って PWAs を再設定する方法とプッシュ-PWAs の使い方 |MDN"  
