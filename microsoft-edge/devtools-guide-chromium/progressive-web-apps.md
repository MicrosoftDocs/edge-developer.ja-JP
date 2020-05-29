---
title: プログレッシブ Web アプリをデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ce389ad10073efd318e5fa4df59d78fd40b7ebeb
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601881"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  





# <span data-ttu-id="63967-103">プログレッシブ Web アプリをデバッグする</span><span class="sxs-lookup"><span data-stu-id="63967-103">Debug Progressive Web Apps</span></span>   



<span data-ttu-id="63967-104">**アプリケーション**パネルを使用して、web アプリマニフェスト、サービスワーカー、service worker キャッシュを検査、変更、およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="63967-104">Use the **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

<span data-ttu-id="63967-105">このガイドでは、**アプリケーション**パネルのプログレッシブ Web アプリ機能についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="63967-105">This guide only discusses the Progressive Web App features of the **Application** panel.</span></span>  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### <span data-ttu-id="63967-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="63967-106">Summary</span></span>  

*   <span data-ttu-id="63967-107">**マニフェスト**ウィンドウを使って web アプリマニフェストを検査し、トリガーをホーム画面イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="63967-107">Use the **Manifest** pane to inspect your web app manifest and trigger Add to Homescreen events.</span></span>  
*   <span data-ttu-id="63967-108">サービスの利用状況に関するタスクの一部 (サービスの登録解除または更新、プッシュイベントのエミュレート、オフラインへの移動、サービスワーカーの停止など) を行うには、[ **Service worker** ] ウィンドウを使います。</span><span class="sxs-lookup"><span data-stu-id="63967-108">Use the **Service Workers** pane for a whole range of service-worker-related tasks, like unregistering or updating a service, emulating push events, going offline, or stopping a service worker.</span></span>  
*   <span data-ttu-id="63967-109">[**キャッシュ記憶域**] ウィンドウからサービスワーカーキャッシュを表示します。</span><span class="sxs-lookup"><span data-stu-id="63967-109">View your service worker cache from the **Cache Storage** pane.</span></span>  
*   <span data-ttu-id="63967-110">サービスワーカーの登録を解除し、[**記憶域のクリア**] ウィンドウから1回ボタンをクリックして、すべての記憶域とキャッシュをクリアします。</span><span class="sxs-lookup"><span data-stu-id="63967-110">Unregister a service worker and clear all storage and caches with a single button click from the **Clear storage** pane.</span></span>  

## <span data-ttu-id="63967-111">Web アプリマニフェスト</span><span class="sxs-lookup"><span data-stu-id="63967-111">Web app manifest</span></span>   

<span data-ttu-id="63967-112">ユーザーが自分のモバイル homescreens にアプリを追加できるようにするには、web アプリマニフェストが必要です。</span><span class="sxs-lookup"><span data-stu-id="63967-112">If you want your users to be able to add your app to their mobile homescreens, you need a web app manifest.</span></span>  <span data-ttu-id="63967-113">マニフェストは、アプリがホーム画面にどのように表示されるかを定義します。ここでは、ホーム画面からの起動時にユーザーに指示し、アプリが起動時にどのように見えるかを示します。</span><span class="sxs-lookup"><span data-stu-id="63967-113">The manifest defines how the app appears on the homescreen, where to direct the user when launching from homescreen, and what the app looks like on launch.</span></span>  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

<span data-ttu-id="63967-114">マニフェストの設定が完了したら、**アプリケーション**パネルの**マニフェスト**ウィンドウを使ってマニフェストを確認できます。</span><span class="sxs-lookup"><span data-stu-id="63967-114">Once you've got your manifest set up, you can use the **Manifest** pane of the **Application** panel to inspect it.</span></span>  

> ##### <span data-ttu-id="63967-115">図 1</span><span class="sxs-lookup"><span data-stu-id="63967-115">Figure 1</span></span>  
> <span data-ttu-id="63967-116">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="63967-116">The **Manifest** Pane</span></span>  
> ![マニフェストウィンドウ][ImageManifest]  

*   <span data-ttu-id="63967-118">マニフェストのソースを確認するには、[**アプリマニフェスト**ラベル] の下のリンクをクリックし `https://airhorner.com/manifest.json` ます ([**図 1**](#figure-1)の場合)。</span><span class="sxs-lookup"><span data-stu-id="63967-118">To look at the manifest source, click the link below **App Manifest** label \(`https://airhorner.com/manifest.json` in [**Figure 1**](#figure-1)]\).</span></span>  
<!-- *   Press the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   <span data-ttu-id="63967-119">[ **Id** ] セクションと [**プレゼンテーション**] セクションには、マニフェストソースからのフィールドが、わかりやすい表示で表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-119">The **Identity** and **Presentation** sections just display fields from the manifest source in a more user-friendly display.</span></span>  
*   <span data-ttu-id="63967-120">[**アイコン**] セクションには、指定したすべてのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-120">The **Icons** section displays every icon that you've specified.</span></span>  

<!--### Simulate Add to Homescreen events   -->

<!--A web app can only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, this criteria can be inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You can test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Clicking on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--![add to desktop shelf][ImageDesktopShelf]  -->

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature cannot yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you can successfully add your app to your desktop shelf, then it'll work for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you can connect a real mobile device to DevTools via **remote debugging**, and then click the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## <span data-ttu-id="63967-121">サービス員</span><span class="sxs-lookup"><span data-stu-id="63967-121">Service workers</span></span>   

<span data-ttu-id="63967-122">サービスワーカーは、今後の web プラットフォームの基本的なテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="63967-122">Service workers are a fundamental technology in the future web platform.</span></span>  <span data-ttu-id="63967-123">これは、ブラウザーで web ページとは別にバックグラウンドで実行されるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="63967-123">They are scripts that the browser runs in the background, separate from a web page.</span></span>  <span data-ttu-id="63967-124">これらのスクリプトを使用すると、プッシュ通知、バックグラウンド同期、オフライン操作など、web ページまたはユーザーの操作を必要としない機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="63967-124">These scripts enable you to access features that don't need a web page or user interaction, like push notifications, background sync, and offline experiences.</span></span>  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  

<!--TODO:  Link to sections when available. -->  

<span data-ttu-id="63967-125">**アプリケーション**パネルの [ **service worker** ] ウィンドウは、サービスワーカーを検査およびデバッグするための devtools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="63967-125">The **Service Workers** pane in the **Application** panel is the main place in DevTools to inspect and debug service workers.</span></span>  

> ##### <span data-ttu-id="63967-126">図 2</span><span class="sxs-lookup"><span data-stu-id="63967-126">Figure 2</span></span>  
> <span data-ttu-id="63967-127">[ **Service worker** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="63967-127">The **Service Workers** Pane</span></span>  
> <span data-ttu-id="63967-128">![Service Worker] ウィンドウ[ImageServiceWorkersPane]</span><span class="sxs-lookup"><span data-stu-id="63967-128">![The Service Workers pane][ImageServiceWorkersPane]</span></span>  

*   <span data-ttu-id="63967-129">現在開いているページに service worker がインストールされている場合は、このウィンドウに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-129">If a service worker is installed to the currently open page, then you'll see it listed on this pane.</span></span>  <span data-ttu-id="63967-130">たとえば、[**図 2**](#figure-2)には、のスコープ用にインストールされた service worker があり `https://weather-pwa-sample.firebaseapp.com` ます。</span><span class="sxs-lookup"><span data-stu-id="63967-130">For example, in [**Figure 2**](#figure-2) there's a service worker installed for the scope of `https://weather-pwa-sample.firebaseapp.com`.</span></span>  
*   <span data-ttu-id="63967-131">[**オフライン**] チェックボックスをオンにすると、devtools がオフラインモードになります。</span><span class="sxs-lookup"><span data-stu-id="63967-131">The **Offline** checkbox puts DevTools into offline mode.</span></span>  <span data-ttu-id="63967-132">これは、**ネットワーク**パネルから利用できるオフラインモードまたは `Go offline` [コマンドメニュー][DevtoolsCommandMenuIndex]のオプションに相当します。</span><span class="sxs-lookup"><span data-stu-id="63967-132">This is equivalent to the offline mode available from the **Network** panel, or the `Go offline` option in the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  
*   <span data-ttu-id="63967-133">**[再読み込み時の更新**] チェックボックスをオンにすると、すべてのページの読み込み時にサービスワーカーの更新が強制されます。</span><span class="sxs-lookup"><span data-stu-id="63967-133">The **Update on reload** checkbox forces the service worker to update on every page load.</span></span>  
*   <span data-ttu-id="63967-134">[**ネットワーク用にバイパス**] チェックボックスをオンにすると、サービスワーカーが無視され、要求されたリソースについてブラウザーがネットワークに移動します。</span><span class="sxs-lookup"><span data-stu-id="63967-134">The **Bypass for network** checkbox bypasses the service worker and forces the browser to go to the network for requested resources.</span></span>  
*   <span data-ttu-id="63967-135">[**更新**] ボタンをクリックすると、指定したサービスワーカーの1回限りの更新が実行されます。</span><span class="sxs-lookup"><span data-stu-id="63967-135">The **Update** button performs a one-time update of the specified service worker.</span></span>  
*   <span data-ttu-id="63967-136">**プッシュ**ボタンは、ペイロード ( **tickle**とも呼ばれます) なしでプッシュ通知をエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="63967-136">The **Push** button emulates a push notification without a payload \(also known as a **tickle**\).</span></span>  
*   <span data-ttu-id="63967-137">[**同期**] ボタンは、バックグラウンド同期イベントをエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="63967-137">The **Sync** button emulates a background sync event.</span></span>  
*   <span data-ttu-id="63967-138">**登録解除**ボタンは、指定されたサービスワーカーの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="63967-138">The **Unregister** button unregisters the specified service worker.</span></span>  <span data-ttu-id="63967-139">1回のボタンクリックで、サービスワーカーの登録を解除し、ストレージとキャッシュをワイプする方法については、「[記憶域をクリア](#clear-storage)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63967-139">Check out [Clear storage](#clear-storage) for a way to unregister a service worker and wipe storage and caches with a single button click.</span></span>  
*   <span data-ttu-id="63967-140">**ソース**行は、現在実行されているサービスワーカーがインストールされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="63967-140">The **Source** line tells you when the currently running service worker was installed.</span></span>  <span data-ttu-id="63967-141">リンクは、サービスワーカーのソースファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="63967-141">The link is the name of the service worker's source file.</span></span>  <span data-ttu-id="63967-142">リンクをクリックすると、サービスワーカーのソースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="63967-142">Clicking on the link sends you to the service worker's source.</span></span>  
*   <span data-ttu-id="63967-143">**ステータス**行は、サービスワーカーの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="63967-143">The **Status** line tells you the status of the service worker.</span></span>  <span data-ttu-id="63967-144">緑のステータスインジケーター ( `#36` [**図 2**](#figure-2)の場合) の横にある ID 番号は、現在アクティブになっているサービスワーカーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="63967-144">The ID number next to the green status indicator \(`#36` in [**Figure 2**](#figure-2)\) is for the currently active Service Worker.</span></span>  <span data-ttu-id="63967-145">状態の横には、[**スタート**] ボタン (サービスワーカーが停止されている場合) または [**停止**] ボタン (サービスワーカーが実行されている場合) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-145">Next to the status you'll see a **start** button \(if the service worker is stopped\) or a **stop** button \(if the service worker is running\).</span></span>  <span data-ttu-id="63967-146">サービスワーカーは、ブラウザーでいつでも停止して開始するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="63967-146">Service workers are designed to be stopped and started by the browser at any time.</span></span>  <span data-ttu-id="63967-147">[**停止**] ボタンを使用してサービスワーカーを明示的に停止すると、そのことがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="63967-147">Explicitly stopping your service worker using the **stop** button can simulate that.</span></span>  <span data-ttu-id="63967-148">サービスワーカーを停止することは、サービスワーカーが再起動したときにコードがどのように動作するかをテストする優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="63967-148">Stopping your service worker is a great way to test how your code behaves when the service worker starts back up again.</span></span>  <span data-ttu-id="63967-149">永続的なグローバル状態についての前提条件に不備があるため、多くの場合、バグが明らかになります。</span><span class="sxs-lookup"><span data-stu-id="63967-149">It frequently reveals bugs due to faulty assumptions about persistent global state.</span></span>  
*   <span data-ttu-id="63967-150">**クライアント**の行には、サービスワーカーのスコープが指定されている起点が示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-150">The **Clients** line tells you the origin that the service worker is scoped to.</span></span>  <span data-ttu-id="63967-151">**フォーカス**ボタンは、ほとんどの場合、[**すべて表示**] チェックボックスをオンにしておくと便利です。</span><span class="sxs-lookup"><span data-stu-id="63967-151">The **focus** button is mostly useful when you've enabled the **show all** checkbox.</span></span>  <span data-ttu-id="63967-152">このチェックボックスがオンになっていると、登録されているすべてのサービスワーカーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-152">When that checkbox is enabled, all registered service workers are listed.</span></span>  <span data-ttu-id="63967-153">別のタブで実行されているサービスワーカーの横にある [**フォーカス**] ボタンをクリックすると、Microsoft Edge ではそのタブにフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="63967-153">If you click on the **focus** button next to a service worker that is running in a different tab, Microsoft Edge focuses on that tab.</span></span>  

<span data-ttu-id="63967-154">サービスワーカーからエラーが発生した場合、[**エラー** ] という名前の新しいラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-154">If the service worker causes any errors, a new label called **Errors** shows up.</span></span>  

<!--![service worker with errors][ImageServiceWorkerErrors]  -->

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## <span data-ttu-id="63967-155">Service worker キャッシュ</span><span class="sxs-lookup"><span data-stu-id="63967-155">Service worker caches</span></span> 

<span data-ttu-id="63967-156">[**キャッシュ記憶域**] ウィンドウには、\ (service Worker)[キャッシュ API][MDNWebCacheAPI]を使用してキャッシュされたリソースの読み取り専用リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-156">The **Cache Storage** pane provides a read-only list of resources that have been cached using the \(service worker\) [Cache API][MDNWebCacheAPI].</span></span>  

> ##### <span data-ttu-id="63967-157">図 3</span><span class="sxs-lookup"><span data-stu-id="63967-157">Figure 3</span></span>  
> <span data-ttu-id="63967-158">[**キャッシュの記憶域**] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="63967-158">The **Cache Storage** Pane</span></span>  
> <span data-ttu-id="63967-159">![キャッシュストレージ] ウィンドウ[ImageServiceWorkersCachePane]</span><span class="sxs-lookup"><span data-stu-id="63967-159">![The Cache Storage Pane][ImageServiceWorkersCachePane]</span></span>  

> [!NOTE]
> <span data-ttu-id="63967-160">初めてキャッシュを開いてリソースを追加するときに、DevTools で変更が検出されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="63967-160">The first time you open a cache and add a resource to it, DevTools might not detect the change.</span></span>  <span data-ttu-id="63967-161">ページを再度読み込むと、キャッシュが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-161">Reload the page and you should see the cache.</span></span>  

<span data-ttu-id="63967-162">2つ以上のキャッシュを開いている場合は、[**キャッシュストレージ**] ドロップダウンの下に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="63967-162">If you've got two or more caches open, you'll see them listed below the **Cache Storage** dropdown.</span></span>  

> ##### <span data-ttu-id="63967-163">図 4</span><span class="sxs-lookup"><span data-stu-id="63967-163">Figure 4</span></span>  
> <span data-ttu-id="63967-164">[**キャッシュ記憶域**] ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="63967-164">The **Cache Storage** dropdown</span></span>  
> <span data-ttu-id="63967-165">![キャッシュストレージ] ドロップダウン[ImageMultipleCaches]</span><span class="sxs-lookup"><span data-stu-id="63967-165">![The Cache Storage dropdown][ImageMultipleCaches]</span></span>  

## <span data-ttu-id="63967-166">クォータ使用量</span><span class="sxs-lookup"><span data-stu-id="63967-166">Quota usage</span></span> 

<span data-ttu-id="63967-167">[キャッシュ記憶域] ウィンドウ内の一部の応答は、"**不透明**" としてマークされることがあります。</span><span class="sxs-lookup"><span data-stu-id="63967-167">Some responses within the Cache Storage pane may be flagged as being "**opaque**".</span></span>  <span data-ttu-id="63967-168">これは、 [CORS][FetchHttpCorsProtocol]が有効になっていない場合に、 **CDN**やリモート API などの別の起点から取得された応答を指します。</span><span class="sxs-lookup"><span data-stu-id="63967-168">This refers to a response retrieved from a different origin, like from a **CDN** or remote API, when [CORS][FetchHttpCorsProtocol] is not enabled.</span></span>  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

<span data-ttu-id="63967-169">クロスドメイン情報の漏えいを防ぐため、記憶域のクォータ制限 (例外がスローされる場合など) を計算するために使用される不透明応答のサイズに大きなパディングが追加され、 `QuotaExceeded` API によって報告され **`navigator.storage`** ます。</span><span class="sxs-lookup"><span data-stu-id="63967-169">In order to avoid leakage of cross-domain information, there's significant padding added to the size of an opaque response used for calculating storage quota limits \(for example whether a `QuotaExceeded` exception is thrown\) and reported by the **`navigator.storage`** API.</span></span>  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

<span data-ttu-id="63967-170">このパディングの詳細はブラウザーによって異なりますが、Microsoft Edge では、単一のキャッシュされた不透明応答の**最小サイズ**は[約 7 mb][ChromiumIssues796060#c17]になります。</span><span class="sxs-lookup"><span data-stu-id="63967-170">The details of this padding vary from browser to browser, but for Microsoft Edge, this means that the **minimum size** that any single cached opaque response contributes to the overall storage usage is [approximately 7 megabytes][ChromiumIssues796060#c17].</span></span>  <span data-ttu-id="63967-171">キャッシュする不透明な応答の数を決定する際には、非透過リソースの実際のサイズに基づいて、より早く記憶域のクォータの制限を超えてしまうため、この点を念頭に置いておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="63967-171">You should keep this in mind when determining how many opaque responses you want to cache, since you could easily exceeded storage quota limitations much sooner than you'd otherwise expect based on the actual size of the opaque resources.</span></span>  

<span data-ttu-id="63967-172">関連ガイド:</span><span class="sxs-lookup"><span data-stu-id="63967-172">Related Guides:</span></span>  

*   [<span data-ttu-id="63967-173">スタックオーバーフロー: 不透明な応答に適用される制限は何ですか?</span><span class="sxs-lookup"><span data-stu-id="63967-173">Stack Overflow: What limitations apply to opaque responses?</span></span>][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->

<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## <span data-ttu-id="63967-174">記憶域をクリアする</span><span class="sxs-lookup"><span data-stu-id="63967-174">Clear storage</span></span> 

<span data-ttu-id="63967-175">[**記憶域のクリア**] ウィンドウは、プログレッシブ web アプリを開発するときに便利な機能です。</span><span class="sxs-lookup"><span data-stu-id="63967-175">The **Clear Storage** pane is a very useful feature when developing progressive web apps.</span></span>  <span data-ttu-id="63967-176">このウィンドウでは、サービスワーカーの登録を解除し、1回のボタンクリックですべてのキャッシュとストレージをクリアすることができます。</span><span class="sxs-lookup"><span data-stu-id="63967-176">This pane lets you unregister service workers and clear all caches and storage with a single button click.</span></span>  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->

<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides 

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->

<!--TODO  -->

 



<!-- image links -->  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/manifest-pane.msft.png "図 1: [マニフェスト] ウィンドウ"  
<!--[ImageDesktopShelf]: /microsoft-edge/devtools-guide-chromium/media/io.msft.png "Add to desktop shelf"  -->
[ImageServiceWorkersPane]:/microsoft-edge/devtools-guide-chromium/media/service-workers-pane.msft.png "図 2: [Service Worker] ウィンドウ  
<!--[ImageServiceWorkerErrors]: /microsoft-edge/devtools-guide-chromium/media/sw-error.msft.png "Service worker with errors"  -->
[ImageServiceWorkersCachePane]:/microsoft-edge/devtools-guide-chromium/media/cache-pane-cache-storage-resources.msft.png "図 3: [キャッシュ記憶域] ウィンドウ  
[ImageMultipleCaches]:/microsoft-edge/devtools-guide-chromium/media/cache-pane-cache-storage.msft.png "図 4:**キャッシュストレージ**のドロップダウン  

<!-- links -->  

[DevtoolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium の問題 796060: 分析コードが html に含まれているときに、キャッシュ記憶域の値が更新されるたびに発生します。"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ-Web Api |MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "スタックオーバーフロー: 不透明な応答に適用される制限は何ですか?"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> <span data-ttu-id="63967-185">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="63967-185">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="63967-186">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="63967-186">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="63967-188">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="63967-188">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
