---
description: サービス ワーカーの管理とデバッグに [サービス ワーカー] パネルを使用する
title: DevTools - デバッガー - サービス ワーカー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, デバッガー, デバッグ, pwa, サービス ワーカー, キャッシュ API
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 99592f787da8bcf89d2e16231aa3f39047b4fc0b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234812"
---
# <span data-ttu-id="c32ae-104">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="c32ae-104">Service Workers</span></span>

<span data-ttu-id="c32ae-105">[ **サービス ワーカー] パネル** には、サイトのサービス ワーカーを管理およびデバッグするためのツールが備え付けられているので、次の作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-105">The **Service Workers** panel has tools for managing and debugging the service workers for your site, to help you:</span></span>

 - <span data-ttu-id="c32ae-106">サイトに関連付けられているすべてのサービス ワーカーの概要と、そのスコープと状態の詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="c32ae-106">Get an overview of all the service workers associated with your site and details of their scope and status</span></span>
 - <span data-ttu-id="c32ae-107">**指定した** スコープのサービス**ワーカー登録**を更新および管理 (登録解除) する</span><span class="sxs-lookup"><span data-stu-id="c32ae-107">**Update** and manage (**Unregister**) the service worker registration for the given scope</span></span>
 - <span data-ttu-id="c32ae-108">**テスト** 通知をプッシュする</span><span class="sxs-lookup"><span data-stu-id="c32ae-108">**Push** a test notification</span></span>
 - <span data-ttu-id="c32ae-109">**停止** /**個々**のサービス ワーカーを開始し、</span><span class="sxs-lookup"><span data-stu-id="c32ae-109">**Stop**/**Start** individual service workers, and</span></span>
 - <span data-ttu-id="c32ae-110">**選択** したサービス ワーカーを別のデバッガー ウィンドウで検査する</span><span class="sxs-lookup"><span data-stu-id="c32ae-110">**Inspect** the selected service worker in a separate debugger window</span></span>

![[サービス ワーカーの概要] ウィンドウ](./media/service_worker.png)

<span data-ttu-id="c32ae-112">Edge DevTools でのサービス ワーカー デバッグについては、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c32ae-112">Please note the following about service worker debugging in Edge DevTools:</span></span>

 - <span data-ttu-id="c32ae-113">サービス ワーカーは複数のタブで共有できるので、サービス ワーカーをデバッグすると、ページのツールとは別に DevTools の新しいインスタンスが起動します。</span><span class="sxs-lookup"><span data-stu-id="c32ae-113">Debugging a service worker will launch a new instance of the  DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span></span>
 - <span data-ttu-id="c32ae-114">要素[**と**](./elements.md)[**エミュレーション**](./emulation.md)パネルは、サービス ワーカーがバックグラウンドで実行され、アプリのフロントエンドを直接制御しなことを考えると、サービス ワーカー デバッガーから離れたものになります。</span><span class="sxs-lookup"><span data-stu-id="c32ae-114">The [**Elements**](./elements.md) and [**Emulation**](./emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span></span>
 - <span data-ttu-id="c32ae-115">現在、サービス ワーカーのネットワーク トラフィックは、そのワーカーの DevTools デバッグ インスタンスからのみ報告され、ページ自体のデバッガー インスタンスからのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-115">Currently network traffic for a service worker is only reported from the  DevTools debugging instance for that worker, and not from the debugger instance for the page itself.</span></span>
 - <span data-ttu-id="c32ae-116">DevTools**からのプッシュ**をシミュレートするには、プッシュ イベント リスナーをサービス\*\* ワーカーに追加して、その効果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32ae-116">To simulate a **Push** from the DevTools, you'll need to add a *push* event listener to your service worker in order to observe its effect.</span></span> <span data-ttu-id="c32ae-117">次の例では、サービス ワーカー コンソールに "DevTools からのプッシュ メッセージのテスト" を出力 **します**。</span><span class="sxs-lookup"><span data-stu-id="c32ae-117">The following example will print "Test push message from DevTools" in your service worker **Console**.</span></span>

   ```JavaScript
   self.addEventListener('push', function(event){
       console.log(event.data.text());
   });
   ```

<span data-ttu-id="c32ae-118">サービス ワーカーを使用する際に注意する必要がある一般的な情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c32ae-118">Here are some general things to keep in mind when using service workers:</span></span>

- **<span data-ttu-id="c32ae-119">HTTPS のみ。</span><span class="sxs-lookup"><span data-stu-id="c32ae-119">HTTPS-only.</span></span>** <span data-ttu-id="c32ae-120">サービス ワーカーは HTTP では動作しません。HTTPS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32ae-120">Service workers will not work in HTTP; you will need to use HTTPS.</span></span> <span data-ttu-id="c32ae-121">ただし、テスト目的でサービス ワーカー `localhost` を登録できます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-121">However, you can register service workers on `localhost` for testing purposes.</span></span>

- **<span data-ttu-id="c32ae-122">DOM へのアクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="c32ae-122">No DOM access allowed.</span></span>** <span data-ttu-id="c32ae-123">Web ワーカーと同様に、ページのオブジェクト モデルにはアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="c32ae-123">As with web workers, you don't get access to the page's object model.</span></span> <span data-ttu-id="c32ae-124">つまり、ページに関する情報を変更する必要がある場合は、ページから DOM の変更を処理できるよう、サービス ワーカーからページに使用する [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32ae-124">This means that if you need to change something about the page, you'll need to use [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) from the service worker to the page so that you can handle it DOM changes from the page.</span></span>

- **<span data-ttu-id="c32ae-125">ページとは別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-125">Executes separate from page.</span></span>** <span data-ttu-id="c32ae-126">これらのスクリプトはページの有効期間に結び付けないので、ページと同じコンテキストを共有しないという点を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c32ae-126">Because these scripts are not tied to the lifetime of a page, it's important to understand that they do not share the same context as the page.</span></span> <span data-ttu-id="c32ae-127">(前に説明したように) DOM にアクセスできないのを除き、ページで使用可能な変数にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c32ae-127">Aside from not having access to the DOM (as stated earlier), they won't have access to the same variables available on the page.</span></span>

- **<span data-ttu-id="c32ae-128">アプリ キャッシュ *を上書きします*。</span><span class="sxs-lookup"><span data-stu-id="c32ae-128">Overrides *App Cache*.</span></span>** <span data-ttu-id="c32ae-129">サービス ワーカーが使用されている場合、アプリ キャッシュは無視されます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-129">App Cache will be ignored when service workers are in use.</span></span> <span data-ttu-id="c32ae-130">サービス ワーカー API は、Web 開発者によりきめ細かく制御することで、アプリ キャッシュを完全に取り替えることを目的とします。</span><span class="sxs-lookup"><span data-stu-id="c32ae-130">The Service Worker API is intended to entirely supplant App Cache  by giving more granular control to the web developer.</span></span>

  - **<span data-ttu-id="c32ae-131">スクリプトを CDN 上に設定できない。</span><span class="sxs-lookup"><span data-stu-id="c32ae-131">Script can't be on CDN.</span></span>** <span data-ttu-id="c32ae-132">サービス ワーカー用の JavaScript ファイルは、コンテンツ配布ネットワーク (CDN) でホストできないので、ページと同じドメイン上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32ae-132">The JavaScript file for the service worker can't be hosted on a Content Distribution Network (CDN), it must be on the same domain as the page.</span></span> <span data-ttu-id="c32ae-133">ただし、必要に合う場合は、CDN からスクリプトをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-133">However, if you like, you can import scripts from your CDN.</span></span>

- **<span data-ttu-id="c32ae-134">いつでも終了できます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-134">Can be terminated any time.</span></span>** <span data-ttu-id="c32ae-135">サービス ワーカーは有効期間が短く、その有効期間はイベントに結び付きます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-135">Service workers are meant to be short-lived and their lifetime is tied to events.</span></span> <span data-ttu-id="c32ae-136">特に、サービス ワーカーには、イベント ハンドラーの実行を完了する必要がある時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="c32ae-136">In particular, service workers have a time limit in which they must finish executing their event handlers.</span></span> <span data-ttu-id="c32ae-137">それ以外の場合、ブラウザーまたはオペレーティング システムは、バッテリ、CPU、またはメモリ消費量に影響を与えるサービス ワーカーを終了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c32ae-137">In other cases, the browser or the operating system may choose to terminate a service worker that impacts the battery, CPU, or memory consumption.</span></span> <span data-ttu-id="c32ae-138">どちらの場合も、処理される後続のイベントで別のサービス ワーカー インスタンスが使用される場合は、サービス ワーカー スクリプトのグローバル変数に依存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="c32ae-138">In either case, avoid relying on global variables in the service worker script in case a different service worker instance is used on a subsequent event that's being handled.</span></span>

- **<span data-ttu-id="c32ae-139">許可されるのは非同期要求のみです。</span><span class="sxs-lookup"><span data-stu-id="c32ae-139">Only asynchronous requests allowed.</span></span>** <span data-ttu-id="c32ae-140">ここでは同期 XHR を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-140">Synchronous XHR is not allowed here!</span></span> <span data-ttu-id="c32ae-141">どちらも localStorage ではないので、IndexedDB と前述の新しいキャッシュ API を利用するのが最善です。</span><span class="sxs-lookup"><span data-stu-id="c32ae-141">Neither is localStorage, so it's best to make use of IndexedDB and the new Caches API described earlier.</span></span>

- **<span data-ttu-id="c32ae-142">スコープが 1:1 のサービス ワーカー。</span><span class="sxs-lookup"><span data-stu-id="c32ae-142">Service worker to scope is 1:1.</span></span>** <span data-ttu-id="c32ae-143">スコープごとに 1 つのサービス ワーカーしか持てない。</span><span class="sxs-lookup"><span data-stu-id="c32ae-143">You'll only be able to have one service worker per scope.</span></span> <span data-ttu-id="c32ae-144">つまり、サービス ワーカーが既に存在するスコープに別のサービス ワーカーを登録すると、そのサービス ワーカーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="c32ae-144">That means if you try to register a different service worker for a scope that already has a service worker, that service worker will be updated.</span></span>
