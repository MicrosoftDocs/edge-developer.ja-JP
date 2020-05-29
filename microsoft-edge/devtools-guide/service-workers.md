---
description: Service worker パネルを使用して、サービスワーカーの管理とデバッグを行う
title: DevTools-デバッガー-サービスワーカー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、デバッガー、デバッグ、pwa、サービスワーカー、キャッシュ api
ms.custom: seodec18
ms.openlocfilehash: 8e1fa62358657a47ce40d0742f95a76f2586d0c8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569659"
---
# <span data-ttu-id="dc339-104">サービス員</span><span class="sxs-lookup"><span data-stu-id="dc339-104">Service Workers</span></span>

<span data-ttu-id="dc339-105">[ **Service worker** ] パネルには、次のことを支援するために、サイトのサービスワーカーを管理およびデバッグするためのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc339-105">The **Service Workers** panel has tools for managing and debugging the service workers for your site, to help you:</span></span>

 - <span data-ttu-id="dc339-106">サイトに関連付けられているすべてのサービス担当者の概要と、それらのスコープと状態の詳細を把握する</span><span class="sxs-lookup"><span data-stu-id="dc339-106">Get an overview of all the service workers associated with your site and details of their scope and status</span></span>
 - <span data-ttu-id="dc339-107">指定した範囲のサービスワーカーの登録を**更新**および管理する (**登録を解除**する)</span><span class="sxs-lookup"><span data-stu-id="dc339-107">**Update** and manage (**Unregister**) the service worker registration for the given scope</span></span>
 - <span data-ttu-id="dc339-108">テスト通知を**プッシュ**する</span><span class="sxs-lookup"><span data-stu-id="dc339-108">**Push** a test notification</span></span>
 - <span data-ttu-id="dc339-109">**停止** /個々のサービスワーカーを**開始**する</span><span class="sxs-lookup"><span data-stu-id="dc339-109">**Stop**/**Start** individual service workers, and</span></span>
 - <span data-ttu-id="dc339-110">別のデバッガーウィンドウで、選択したサービスワーカーを**検査**します。</span><span class="sxs-lookup"><span data-stu-id="dc339-110">**Inspect** the selected service worker in a separate debugger window</span></span>

![サービスワーカーの概要ウィンドウ](./media/service_worker.png)

<span data-ttu-id="dc339-112">エッジ DevTools でのサービスワーカーのデバッグについては、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc339-112">Please note the following about service worker debugging in Edge DevTools:</span></span>

 - <span data-ttu-id="dc339-113">サービスワーカーをデバッグすると、複数のタブ間でサービスワーカーを共有できるため、ページのツールとは別に、DevTools の新しいインスタンスが起動されます。</span><span class="sxs-lookup"><span data-stu-id="dc339-113">Debugging a service worker will launch a new instance of the  DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span></span>
 - <span data-ttu-id="dc339-114">サービスワーカーがバックグラウンドで実行されていて、アプリのフロントエンドを直接制御していない場合、サービスワーカーデバッガーから[**要素**](./elements.md)と[**エミュレーション**](./emulation.md)パネルは存在しません。</span><span class="sxs-lookup"><span data-stu-id="dc339-114">The [**Elements**](./elements.md) and [**Emulation**](./emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span></span>
 - <span data-ttu-id="dc339-115">現在、サービスワーカーのネットワークトラフィックは、そのワーカーの DevTools デバッグインスタンスからのみ報告され、ページ自体のデバッガーインスタンスからは報告されません。</span><span class="sxs-lookup"><span data-stu-id="dc339-115">Currently network traffic for a service worker is only reported from the  DevTools debugging instance for that worker, and not from the debugger instance for the page itself.</span></span>
 - <span data-ttu-id="dc339-116">DevTools からの**プッシュ**をシミュレートするには、その効果を監視するために、サービスワーカーに*プッシュ*イベントリスナーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc339-116">To simulate a **Push** from the DevTools, you'll need to add a *push* event listener to your service worker in order to observe its effect.</span></span> <span data-ttu-id="dc339-117">次の例では、サービスワーカー**コンソール**の devtools からのテストプッシュメッセージを印刷します。</span><span class="sxs-lookup"><span data-stu-id="dc339-117">The following example will print "Test push message from DevTools" in your service worker **Console**.</span></span>

   ```JavaScript
   self.addEventListener('push', function(event){
       console.log(event.data.text());
   });
   ```

<span data-ttu-id="dc339-118">サービスワーカーを使用する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc339-118">Here are some general things to keep in mind when using service workers:</span></span>

- **<span data-ttu-id="dc339-119">HTTPS のみ。</span><span class="sxs-lookup"><span data-stu-id="dc339-119">HTTPS-only.</span></span>** <span data-ttu-id="dc339-120">サービスワーカーは、HTTP では動作しません。HTTPS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc339-120">Service workers will not work in HTTP; you will need to use HTTPS.</span></span> <span data-ttu-id="dc339-121">ただし、テスト目的でサービスワーカーを登録することはでき `localhost` ます。</span><span class="sxs-lookup"><span data-stu-id="dc339-121">However, you can register service workers on `localhost` for testing purposes.</span></span>

- **<span data-ttu-id="dc339-122">DOM アクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="dc339-122">No DOM access allowed.</span></span>** <span data-ttu-id="dc339-123">Web ワーカーの場合と同様に、ページのオブジェクトモデルにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dc339-123">As with web workers, you don't get access to the page's object model.</span></span> <span data-ttu-id="dc339-124">つまり、ページについて何かを変更する必要がある場合は、ページ [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) からの DOM の変更を処理できるように、サービスワーカーからページを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc339-124">This means that if you need to change something about the page, you'll need to use [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) from the service worker to the page so that you can handle it DOM changes from the page.</span></span>

- **<span data-ttu-id="dc339-125">ページとは別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="dc339-125">Executes separate from page.</span></span>** <span data-ttu-id="dc339-126">これらのスクリプトはページの有効期間に関連付けられていないため、ページと同じコンテキストを共有しないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="dc339-126">Because these scripts are not tied to the lifetime of a page, it's important to understand that they do not share the same context as the page.</span></span> <span data-ttu-id="dc339-127">(前に説明したように) DOM へのアクセス権がないことを除けば、ページで利用可能な同じ変数にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dc339-127">Aside from not having access to the DOM (as stated earlier), they won't have access to the same variables available on the page.</span></span>

- **<span data-ttu-id="dc339-128">*アプリのキャッシュ*を上書きします。</span><span class="sxs-lookup"><span data-stu-id="dc339-128">Overrides *App Cache*.</span></span>** <span data-ttu-id="dc339-129">サービスワーカーが使用されている場合、アプリキャッシュは無視されます。</span><span class="sxs-lookup"><span data-stu-id="dc339-129">App Cache will be ignored when service workers are in use.</span></span> <span data-ttu-id="dc339-130">Service Worker API は、よりきめ細かいコントロールを web 開発者に提供することによって、アプリキャッシュを完全に supplant することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="dc339-130">The Service Worker API is intended to entirely supplant App Cache  by giving more granular control to the web developer.</span></span>

  - **<span data-ttu-id="dc339-131">スクリプトを CDN にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dc339-131">Script can't be on CDN.</span></span>** <span data-ttu-id="dc339-132">サービスワーカー用の JavaScript ファイルは、コンテンツ配信ネットワーク (CDN) でホストすることはできません。ページと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc339-132">The JavaScript file for the service worker can't be hosted on a Content Distribution Network (CDN), it must be on the same domain as the page.</span></span> <span data-ttu-id="dc339-133">ただし、必要に応じて、CDN からスクリプトをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dc339-133">However, if you like, you can import scripts from your CDN.</span></span>

- **<span data-ttu-id="dc339-134">いつでも終了できます。</span><span class="sxs-lookup"><span data-stu-id="dc339-134">Can be terminated any time.</span></span>** <span data-ttu-id="dc339-135">サービスワーカーは、寿命が短く、有効期間がイベントに関連付けられていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dc339-135">Service workers are meant to be short-lived and their lifetime is tied to events.</span></span> <span data-ttu-id="dc339-136">特に、サービスワーカーには、イベントハンドラーの実行を終了する時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="dc339-136">In particular, service workers have a time limit in which they must finish executing their event handlers.</span></span> <span data-ttu-id="dc339-137">また、ブラウザーやオペレーティングシステムが、バッテリー、CPU、またはメモリの消費に影響を与えるサービスワーカーを終了することを選択する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc339-137">In other cases, the browser or the operating system may choose to terminate a service worker that impacts the battery, CPU, or memory consumption.</span></span> <span data-ttu-id="dc339-138">どちらの場合も、別のサービスワーカーインスタンスが処理されているイベントで使用される場合に備えて、サービスワーカースクリプトのグローバル変数に依存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="dc339-138">In either case, avoid relying on global variables in the service worker script in case a different service worker instance is used on a subsequent event that's being handled.</span></span>

- **<span data-ttu-id="dc339-139">非同期要求のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="dc339-139">Only asynchronous requests allowed.</span></span>** <span data-ttu-id="dc339-140">同期 XHR はここでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="dc339-140">Synchronous XHR is not allowed here!</span></span> <span data-ttu-id="dc339-141">どちらも localStorage でもありません。したがって、IndexedDB と、前に説明した新しいキャッシュ API を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc339-141">Neither is localStorage, so it's best to make use of IndexedDB and the new Caches API described earlier.</span></span>

- **<span data-ttu-id="dc339-142">スコープへのサービスワーカーは1:1 です。</span><span class="sxs-lookup"><span data-stu-id="dc339-142">Service worker to scope is 1:1.</span></span>** <span data-ttu-id="dc339-143">スコープごとに1つのサービスワーカーしか作成できません。</span><span class="sxs-lookup"><span data-stu-id="dc339-143">You'll only be able to have one service worker per scope.</span></span> <span data-ttu-id="dc339-144">つまり、既にサービスワーカーを持っているスコープに対して別のサービスワーカーを登録しようとすると、そのサービスワーカーは更新されます。</span><span class="sxs-lookup"><span data-stu-id="dc339-144">That means if you try to register a different service worker for a scope that already has a service worker, that service worker will be updated.</span></span>
