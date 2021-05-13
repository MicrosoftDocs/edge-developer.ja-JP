---
description: '[アプリケーション] パネルを使用して、Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグします。'
title: プログレッシブ Web アプリのデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3a0732327aac210e399c438b8d9c34c75a7c2910
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564729"
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
# <a name="debug-progressive-web-apps"></a><span data-ttu-id="0577c-104">プログレッシブ Web アプリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="0577c-104">Debug Progressive Web Apps</span></span>  

<span data-ttu-id="0577c-105">[アプリケーション **] パネル** を使用して、Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="0577c-105">Use the **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

<span data-ttu-id="0577c-106">このガイドでは、[アプリケーション] パネルのプログレッシブ Web アプリ機能についてのみ **説明** します。</span><span class="sxs-lookup"><span data-stu-id="0577c-106">This guide only discusses the Progressive Web App features of the **Application** panel.</span></span>  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### <a name="summary"></a><span data-ttu-id="0577c-107">要約</span><span class="sxs-lookup"><span data-stu-id="0577c-107">Summary</span></span>  

*   <span data-ttu-id="0577c-108">[マニフェスト] **ウィンドウを** 使用して Web アプリ マニフェストを検査し、[ホーム画面に追加] イベントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="0577c-108">Use the **Manifest** pane to inspect your web app manifest and trigger Add to Homescreen events.</span></span>  
*   <span data-ttu-id="0577c-109">サービスの **登録** 解除や更新、プッシュ イベントの表示、オフライン化、サービス ワーカーの停止など、サービス ワーカー関連のタスクの範囲全体に対して、[サービス ワーカー] ウィンドウを使用します。</span><span class="sxs-lookup"><span data-stu-id="0577c-109">Use the **Service Workers** pane for a whole range of service-worker-related tasks, like unregistering or updating a service, emulating push events, going offline, or stopping a service worker.</span></span>  
*   <span data-ttu-id="0577c-110">[キャッシュ] ウィンドウからサービス ワーカー**キャッシュStorage**します。</span><span class="sxs-lookup"><span data-stu-id="0577c-110">View your service worker cache from the **Cache Storage** pane.</span></span>  
*   <span data-ttu-id="0577c-111">サービス ワーカーの登録を解除し、[ストレージのクリア] ウィンドウから選択した 1 つのボタンですべての記憶域と **キャッシュをクリア** します。</span><span class="sxs-lookup"><span data-stu-id="0577c-111">Unregister a service worker and clear all storage and caches with a single button choose from the **Clear storage** pane.</span></span>  
    
## <a name="web-app-manifest"></a><span data-ttu-id="0577c-112">Web アプリ マニフェスト</span><span class="sxs-lookup"><span data-stu-id="0577c-112">Web app manifest</span></span>  

<span data-ttu-id="0577c-113">ユーザーがモバイル ホームスクリーンにアプリを追加するには、Web アプリ マニフェストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0577c-113">If you want your users to be able to add your app to their mobile homescreens, you need a web app manifest.</span></span>  <span data-ttu-id="0577c-114">マニフェストは、アプリがホームスクリーンに表示される方法、ホーム画面から起動するときにユーザーを指示する場所、およびアプリの起動時の外観を定義します。</span><span class="sxs-lookup"><span data-stu-id="0577c-114">The manifest defines how the app appears on the homescreen, where to direct the user when launching from homescreen, and what the app looks like on launch.</span></span>  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

<span data-ttu-id="0577c-115">マニフェストをセットアップした後、アプリケーション パネルの **[マニフェスト**] ウィンドウ\*\*\*\* を使用して検査できます。</span><span class="sxs-lookup"><span data-stu-id="0577c-115">After you have your manifest set up, you may use the **Manifest** pane of the **Application** panel to inspect it.</span></span>  

:::image type="complex" source="../media/manifest-pane.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/manifest-pane.msft.png":::
   <span data-ttu-id="0577c-117">マニフェスト**ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="0577c-117">The **Manifest** Pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="0577c-118">マニフェスト ソースを確認するには、前の図の\*\*\*\* アプリ マニフェスト ラベル \( の下 `https://airhorner.com/manifest.json` にあるリンクを選択します\)。</span><span class="sxs-lookup"><span data-stu-id="0577c-118">To look at the manifest source, choose the link below **App Manifest** label \(`https://airhorner.com/manifest.json` in the previous figure\).</span></span>  
<!-- *   Choose the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   <span data-ttu-id="0577c-119">**[Id]** セクション**と [プレゼンテーション]** セクションでは、マニフェスト ソースのフィールドをユーザーフレンドリーな表示に表示します。</span><span class="sxs-lookup"><span data-stu-id="0577c-119">The **Identity** and **Presentation** sections just display fields from the manifest source in a more user-friendly display.</span></span>  
*   <span data-ttu-id="0577c-120">[ **アイコン]** セクションには、指定したアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-120">The **Icons** section displays every icon that you've specified.</span></span>  
    
<!--### Simulate Add to Homescreen events  -->

<!--A web app may only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, the criteria is potentially inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You may test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Choosing on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--  
:::image type="complex" source="../media/io.msft.png" alt-text="Add to desktop shelf" lightbox="../media/io.msft.png":::
   Add to desktop shelf  
:::image-end:::
-->  

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature may not yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you may successfully add your app to your desktop shelf, then it works for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you may connect a real mobile device to DevTools via **remote debugging**, and then choose the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## <a name="service-workers"></a><span data-ttu-id="0577c-121">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="0577c-121">Service workers</span></span>  

<span data-ttu-id="0577c-122">サービス ワーカーは、将来の Web プラットフォームの基本的なテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="0577c-122">Service workers are a fundamental technology in the future web platform.</span></span>  <span data-ttu-id="0577c-123">これらは、Web ページとは別に、ブラウザーがバックグラウンドで実行するスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="0577c-123">They are scripts that the browser runs in the background, separate from a web page.</span></span>  <span data-ttu-id="0577c-124">スクリプトを使用すると、プッシュ通知、バックグラウンド同期、オフライン エクスペリエンスなど、Web ページやユーザー操作を必要とせずに機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0577c-124">The scripts allow you to access features that without the need of a web page or user interaction, like push notifications, background sync, and offline experiences.</span></span>  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  
    
<!--TODO:  Link to sections when available. -->  

<span data-ttu-id="0577c-125">[ **アプリケーション] パネルの** [ **サービス** ワーカー] ウィンドウは、サービス ワーカーを検査およびデバッグする DevTools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="0577c-125">The **Service Workers** pane in the **Application** panel is the main place in DevTools to inspect and debug service workers.</span></span>  

:::image type="complex" source="../media/service-workers-pane.msft.png" alt-text="[サービス ワーカー] ウィンドウ" lightbox="../media/service-workers-pane.msft.png":::
   <span data-ttu-id="0577c-127">[ **サービス ワーカー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0577c-127">The **Service Workers** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="0577c-128">サービス ワーカーが現在開いているページにインストールされている場合は、このウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-128">If a service worker is installed to the currently open page, then it is listed on this pane.</span></span>  <span data-ttu-id="0577c-129">たとえば、前の図では、 のスコープにサービス ワーカーがインストールされています `https://weather-pwa-sample.firebaseapp.com` 。</span><span class="sxs-lookup"><span data-stu-id="0577c-129">For example, in the previous figure, there is a service worker installed for the scope of `https://weather-pwa-sample.firebaseapp.com`.</span></span>  
*   <span data-ttu-id="0577c-130">[ **オフライン]** チェック ボックスをオンにすると、DevTools はオフライン モードになります。</span><span class="sxs-lookup"><span data-stu-id="0577c-130">The **Offline** checkbox puts DevTools into offline mode.</span></span>  <span data-ttu-id="0577c-131">これは、ネットワーク ツールで使用できるオフライン\*\*\*\* モード、またはコマンド `Go offline` メニューのオプションと[同じです][DevtoolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="0577c-131">This is equivalent to the offline mode available from the **Network** tool, or the `Go offline` option in the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  
*   <span data-ttu-id="0577c-132">[再 **読み込み時に更新** ] チェック ボックスをオンにすると、サービス ワーカーはページの読み込みごとに強制的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-132">The **Update on reload** checkbox forces the service worker to update on every page load.</span></span>  
*   <span data-ttu-id="0577c-133">[ **ネットワークのバイパス]** チェック ボックスは、サービス ワーカーをバイパスし、要求されたリソースのネットワークにブラウザーを強制的に移動します。</span><span class="sxs-lookup"><span data-stu-id="0577c-133">The **Bypass for network** checkbox bypasses the service worker and forces the browser to go to the network for requested resources.</span></span>  
*   <span data-ttu-id="0577c-134">[ **更新]** ボタンは、指定したサービス ワーカーの 1 回の更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="0577c-134">The **Update** button performs a one-time update of the specified service worker.</span></span>  
*   <span data-ttu-id="0577c-135">プッシュ **ボタン** は、ペイロード \(くすぐり \とも呼ばれる) なしでプッシュ通知を **エミュレート**します。</span><span class="sxs-lookup"><span data-stu-id="0577c-135">The **Push** button emulates a push notification without a payload \(also known as a **tickle**\).</span></span>  
*   <span data-ttu-id="0577c-136">[ **同期]** ボタンは、バックグラウンド同期イベントをエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="0577c-136">The **Sync** button emulates a background sync event.</span></span>  
*   <span data-ttu-id="0577c-137">[ **登録解除** ] ボタンは、指定したサービス ワーカーの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="0577c-137">The **Unregister** button unregisters the specified service worker.</span></span>  <span data-ttu-id="0577c-138">サービス ワーカー [の登録を](#clear-storage) 解除し、1 つのボタンでストレージとキャッシュをワイプする方法については、「ストレージをクリアする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0577c-138">Check out [Clear storage](#clear-storage) for a way to unregister a service worker and wipe storage and caches with a single button choose.</span></span>  
*   <span data-ttu-id="0577c-139">[ **ソース]** 行は、現在実行中のサービス ワーカーがインストールされた時間を示します。</span><span class="sxs-lookup"><span data-stu-id="0577c-139">The **Source** line tells you when the currently running service worker was installed.</span></span>  <span data-ttu-id="0577c-140">リンクは、サービス ワーカーのソース ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="0577c-140">The link is the name of the source file of the service worker.</span></span>  <span data-ttu-id="0577c-141">リンクを選択すると、サービス ワーカーのソースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-141">Choosing on the link sends you to the source of the service worker.</span></span>  
*   <span data-ttu-id="0577c-142">[ **状態]** 行には、サービス ワーカーの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-142">The **Status** line tells you the status of the service worker.</span></span>  <span data-ttu-id="0577c-143">緑の状態インジケーター \( 前の図\) の横にある ID 番号は、現在アクティブ `#36` なサービス ワーカー用です。</span><span class="sxs-lookup"><span data-stu-id="0577c-143">The ID number next to the green status indicator \(`#36` in previous figure\) is for the currently active Service Worker.</span></span>  <span data-ttu-id="0577c-144">状態の横には、開始\*\*\*\* ボタン \(サービス ワーカーが停止している場合\) または\*\*\*\* 停止ボタン \(サービス ワーカーが実行されている場合\) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-144">Next to the status, a **start** button \(if the service worker is stopped\) or a **stop** button \(if the service worker is running\) is displayed.</span></span>  <span data-ttu-id="0577c-145">サービス ワーカーは、いつでもブラウザーによって停止および開始するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="0577c-145">Service workers are designed to be stopped and started by the browser at any time.</span></span>  <span data-ttu-id="0577c-146">停止ボタンを使用してサービス ワーカーを明示的に **停止** すると、その操作をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="0577c-146">Explicitly stopping your service worker using the **stop** button may simulate that.</span></span>  <span data-ttu-id="0577c-147">サービス ワーカーを停止すると、サービス ワーカーが再びバックアップを開始するときにコードがどのように動作するのかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="0577c-147">Stopping your service worker is a great way to test how your code behaves when the service worker starts back up again.</span></span>  <span data-ttu-id="0577c-148">これは、永続的なグローバル状態に関する誤った仮定によるバグを頻繁に明らかにします。</span><span class="sxs-lookup"><span data-stu-id="0577c-148">It frequently reveals bugs due to faulty assumptions about persistent global state.</span></span>  
*   <span data-ttu-id="0577c-149">[ **クライアント]** 行には、サービス ワーカーのスコープが設定されている起点が示されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-149">The **Clients** line tells you the origin that the service worker is scoped to.</span></span>  <span data-ttu-id="0577c-150">フォーカス **ボタンは** 、[すべて表示] チェック ボックスを有効にした場合 **に主に便利** です。</span><span class="sxs-lookup"><span data-stu-id="0577c-150">The **focus** button is mostly useful when you've enabled the **show all** checkbox.</span></span>  <span data-ttu-id="0577c-151">このチェック ボックスを有効にすると、登録されているサービス ワーカーすべてが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-151">When that checkbox is enabled, all registered service workers are listed.</span></span>  <span data-ttu-id="0577c-152">別のタブで実行**されている**サービス ワーカーの横にあるフォーカス ボタンを選択した場合は、そのMicrosoft Edgeにフォーカスを当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0577c-152">If you choose on the **focus** button next to a service worker that is running in a different tab, Microsoft Edge focuses on that tab.</span></span>  
    
<span data-ttu-id="0577c-153">サービス ワーカーがエラーを発生すると、Errors という名前の新しいラベル **が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-153">If the service worker causes any errors, a new label called **Errors** shows up.</span></span>  

<!--  
:::image type="complex" source="../media/sw-error.msft.png" alt-text="Service worker with errors" lightbox="../media/sw-error.msft.png":::
   Service worker with errors  
:::image-end:::
-->  

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## <a name="service-worker-caches"></a><span data-ttu-id="0577c-154">サービス ワーカー キャッシュ</span><span class="sxs-lookup"><span data-stu-id="0577c-154">Service worker caches</span></span>  

<span data-ttu-id="0577c-155">[**キャッシュ Storage]** ウィンドウには、\(service worker\) キャッシュ API を使用してキャッシュされたリソースの読み取り専用[リストが表示されます][MDNWebCacheAPI]。</span><span class="sxs-lookup"><span data-stu-id="0577c-155">The **Cache Storage** pane provides a read-only list of resources that have been cached using the \(service worker\) [Cache API][MDNWebCacheAPI].</span></span>  

:::image type="complex" source="../media/cache-pane-cache-storage-resources.msft.png" alt-text="[キャッシュ] ウィンドウStorageウィンドウ" lightbox="../media/cache-pane-cache-storage-resources.msft.png":::
   <span data-ttu-id="0577c-157">[**キャッシュ] ウィンドウStorage**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0577c-157">The **Cache Storage** Pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="0577c-158">キャッシュを初めて開いてリソースを追加すると、DevTools によって変更が検出されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0577c-158">The first time you open a cache and add a resource to it, DevTools may not detect the change.</span></span>  <span data-ttu-id="0577c-159">ページを更新し、キャッシュを表示します。</span><span class="sxs-lookup"><span data-stu-id="0577c-159">Refresh the page and to display the cache.</span></span>  

<span data-ttu-id="0577c-160">2 つ以上のキャッシュを開いている場合は、次の [キャッシュ] ドロップダウンの下**Storage**表示されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-160">If you have two or more caches open, the caches display under the following **Cache Storage** dropdown.</span></span>  

:::image type="complex" source="../media/cache-pane-cache-storage.msft.png" alt-text="[キャッシュ] Storageドロップダウン" lightbox="../media/cache-pane-cache-storage.msft.png":::
   <span data-ttu-id="0577c-162">[**キャッシュ] Storage**ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="0577c-162">The **Cache Storage** dropdown</span></span>  
:::image-end:::  

## <a name="quota-usage"></a><span data-ttu-id="0577c-163">クォータ使用量</span><span class="sxs-lookup"><span data-stu-id="0577c-163">Quota usage</span></span>  

<span data-ttu-id="0577c-164">[キャッシュ] ウィンドウ内の**一部Storage**が "不透明" としてフラグ付けされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0577c-164">Some responses within the **Cache Storage** pane may be flagged as being "opaque".</span></span>  <span data-ttu-id="0577c-165">これは[、CORS][FetchHttpCorsProtocol]が有効になっていない場合に、別のオリジン **(CDN** API やリモート API など) から取得された応答を指します。</span><span class="sxs-lookup"><span data-stu-id="0577c-165">This refers to a response retrieved from a different origin, like from a **CDN** or remote API, when [CORS][FetchHttpCorsProtocol] is not enabled.</span></span>  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

<span data-ttu-id="0577c-166">クロスドメイン情報の漏洩を回避するために、ストレージ クォータ制限の計算に使用される不透明な応答のサイズに大きな埋め込み (たとえば、例外がスロー `QuotaExceeded` されるかどうか\) が `navigator.storage` 追加され、API によって報告されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-166">In order to avoid leakage of cross-domain information, significant padding is added to the size of an opaque response used for calculating storage quota limits \(for example whether a `QuotaExceeded` exception is thrown\) and reported by the `navigator.storage` API.</span></span>  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

<span data-ttu-id="0577c-167">このパディングの詳細はブラウザーによって異なりますが、Microsoft Edge の場合、キャッシュされた 1\*\*\*\* 回の不透明応答がストレージ全体の使用量に与える最小サイズは約[7 メガバイト][ChromiumIssues796060#c17]です。</span><span class="sxs-lookup"><span data-stu-id="0577c-167">The details of this padding vary from browser to browser, but for Microsoft Edge, this means that the **minimum size** that any single cached opaque response contributes to the overall storage usage is [approximately 7 megabytes][ChromiumIssues796060#c17].</span></span>  <span data-ttu-id="0577c-168">キャッシュする不透明な応答の数を決定する場合は、不透明なリソースの実際のサイズに基づいて、ストレージ クォータの制限をはるかに早く超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0577c-168">Remember the padding when determining how many opaque responses you want to cache, since you may easily exceed storage quota limitations much sooner than you otherwise expect based on the actual size of the opaque resources.</span></span>  

<span data-ttu-id="0577c-169">関連ガイド:</span><span class="sxs-lookup"><span data-stu-id="0577c-169">Related Guides:</span></span>  

*   [<span data-ttu-id="0577c-170">スタック オーバーフロー: 不透明な応答に適用される制限</span><span class="sxs-lookup"><span data-stu-id="0577c-170">Stack Overflow: What limitations apply to opaque responses?</span></span>][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->
    
<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## <a name="clear-storage"></a><span data-ttu-id="0577c-171">ストレージのクリア</span><span class="sxs-lookup"><span data-stu-id="0577c-171">Clear storage</span></span>  

<span data-ttu-id="0577c-172">[Clear **Storage]** ウィンドウは、プログレッシブ Web アプリを開発するときに非常に便利な機能です。</span><span class="sxs-lookup"><span data-stu-id="0577c-172">The **Clear Storage** pane is a very useful feature when developing progressive web apps.</span></span>  <span data-ttu-id="0577c-173">このウィンドウでは、サービス ワーカーの登録を解除し、1 つのボタンですべてのキャッシュとストレージをクリアできます。</span><span class="sxs-lookup"><span data-stu-id="0577c-173">This pane lets you unregister service workers and clear all caches and storage with a single button choose.</span></span>  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->
    
<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides   

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="0577c-174">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="0577c-174">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium問題 796060: Analytics コードが html 内にあるStorage更新ごとにキャッシュの値が上昇する"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ - Web API |MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "スタック オーバーフロー: 不透明な応答に適用される制限"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> <span data-ttu-id="0577c-179">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0577c-179">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0577c-180">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="0577c-180">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0577c-182">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0577c-182">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
