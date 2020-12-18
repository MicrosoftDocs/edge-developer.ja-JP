---
description: アプリケーション パネルを使用して、Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグします。
title: 段階的な Web アプリのデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 79edf4b04c85db33e89d18ec1832138a61f4f884
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234376"
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

# <span data-ttu-id="b67d8-104">段階的な Web アプリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="b67d8-104">Debug Progressive Web Apps</span></span>  

<span data-ttu-id="b67d8-105">アプリケーション パネル **を使用** して、Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="b67d8-105">Use the **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

<span data-ttu-id="b67d8-106">このガイドでは、アプリケーション パネルの段階的な Web App 機能についての **み説明** します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-106">This guide only discusses the Progressive Web App features of the **Application** panel.</span></span>  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### <span data-ttu-id="b67d8-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="b67d8-107">Summary</span></span>  

*   <span data-ttu-id="b67d8-108">マニフェスト ウィンドウ **を使用** して、Web アプリマニフェストを検査し、ホーム画面に追加イベントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="b67d8-108">Use the **Manifest** pane to inspect your web app manifest and trigger Add to Homescreen events.</span></span>  
*   <span data-ttu-id="b67d8-109">サービスワーカー **ウィンドウ** は、サービスの登録解除や更新、プッシュ イベントのモデル化、オフライン化、サービス ワーカーの停止など、サービス ワーカー関連の全範囲のタスクに使用します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-109">Use the **Service Workers** pane for a whole range of service-worker-related tasks, like unregistering or updating a service, emulating push events, going offline, or stopping a service worker.</span></span>  
*   <span data-ttu-id="b67d8-110">[キャッシュ ストレージ] ウィンドウからサービス ワーカー **キャッシュを表示** します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-110">View your service worker cache from the **Cache Storage** pane.</span></span>  
*   <span data-ttu-id="b67d8-111">サービス ワーカーの登録を解除し、[ストレージのクリア] ウィンドウから 1 回クリックしてすべてのストレージと **キャッシュをクリア** します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-111">Unregister a service worker and clear all storage and caches with a single button click from the **Clear storage** pane.</span></span>  
    
## <span data-ttu-id="b67d8-112">Web アプリ マニフェスト</span><span class="sxs-lookup"><span data-stu-id="b67d8-112">Web app manifest</span></span>  

<span data-ttu-id="b67d8-113">ユーザーがモバイル ホーム画面にアプリを追加するには、Web アプリ マニフェストが必要です。</span><span class="sxs-lookup"><span data-stu-id="b67d8-113">If you want your users to be able to add your app to their mobile homescreens, you need a web app manifest.</span></span>  <span data-ttu-id="b67d8-114">マニフェストは、アプリがホーム画面に表示される方法、ホーム画面から起動するときにユーザーを指示する場所、アプリの起動時の外観を定義します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-114">The manifest defines how the app appears on the homescreen, where to direct the user when launching from homescreen, and what the app looks like on launch.</span></span>  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

<span data-ttu-id="b67d8-115">マニフェストを設定した後、アプリケーション パネルの **マニフェスト** ウィンドウを使用して **マニフェストを検査** できます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-115">After you have your manifest set up, you can use the **Manifest** pane of the **Application** panel to inspect it.</span></span>  

:::image type="complex" source="../media/manifest-pane.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/manifest-pane.msft.png":::
   <span data-ttu-id="b67d8-117">マニフェスト\*\*\*\* ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b67d8-117">The **Manifest** Pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="b67d8-118">マニフェスト ソースを確認するには、アプリ マニフェスト\*\*\*\* ラベル \( 前の図の \) の下の `https://airhorner.com/manifest.json` リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b67d8-118">To look at the manifest source, click the link below **App Manifest** label \(`https://airhorner.com/manifest.json` in the previous figure\).</span></span>  
<!-- *   Press the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   <span data-ttu-id="b67d8-119">Identity **セクション** と **Presentation セクション** では、マニフェスト ソースのフィールドを、より使い分け的な表示に表示します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-119">The **Identity** and **Presentation** sections just display fields from the manifest source in a more user-friendly display.</span></span>  
*   <span data-ttu-id="b67d8-120">[ **アイコン]** セクションには、指定したアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-120">The **Icons** section displays every icon that you've specified.</span></span>  
    
<!--### Simulate Add to Homescreen events  -->

<!--A web app can only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, this criteria can be inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You can test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Clicking on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--  
:::image type="complex" source="../media/io.msft.png" alt-text="Add to desktop shelf" lightbox="../media/io.msft.png":::
   Add to desktop shelf  
:::image-end:::
-->  

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature cannot yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you can successfully add your app to your desktop shelf, then it'll work for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you can connect a real mobile device to DevTools via **remote debugging**, and then click the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## <span data-ttu-id="b67d8-121">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="b67d8-121">Service workers</span></span>  

<span data-ttu-id="b67d8-122">サービス ワーカーは、将来の Web プラットフォームの基本的なテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="b67d8-122">Service workers are a fundamental technology in the future web platform.</span></span>  <span data-ttu-id="b67d8-123">これらは、Web ページとは別に、ブラウザーがバックグラウンドで実行されるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="b67d8-123">They are scripts that the browser runs in the background, separate from a web page.</span></span>  <span data-ttu-id="b67d8-124">これらのスクリプトを使用すると、プッシュ通知、バックグラウンド同期、オフライン エクスペリエンスなど、Web ページやユーザー操作を必要としない機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-124">These scripts enable you to access features that don't need a web page or user interaction, like push notifications, background sync, and offline experiences.</span></span>  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  
    
<!--TODO:  Link to sections when available. -->  

<span data-ttu-id="b67d8-125">アプリケーション**パネルの [** サービス\*\*\*\* ワーカー] ウィンドウは、サービス ワーカーを検査およびデバッグする DevTools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="b67d8-125">The **Service Workers** pane in the **Application** panel is the main place in DevTools to inspect and debug service workers.</span></span>  

:::image type="complex" source="../media/service-workers-pane.msft.png" alt-text="[サービス ワーカー] ウィンドウ" lightbox="../media/service-workers-pane.msft.png":::
   <span data-ttu-id="b67d8-127">[ **サービス ワーカー]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b67d8-127">The **Service Workers** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="b67d8-128">サービス ワーカーが現在開いているページにインストールされている場合、このウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-128">If a service worker is installed to the currently open page, then you'll see it listed on this pane.</span></span>  <span data-ttu-id="b67d8-129">たとえば、前の図では、次の範囲のサービス ワーカーがインストールされています `https://weather-pwa-sample.firebaseapp.com` 。</span><span class="sxs-lookup"><span data-stu-id="b67d8-129">For example, in the previous figure, there is a service worker installed for the scope of `https://weather-pwa-sample.firebaseapp.com`.</span></span>  
*   <span data-ttu-id="b67d8-130">[ **オフライン]** チェック ボックスをオンにすると、DevTools はオフライン モードになります。</span><span class="sxs-lookup"><span data-stu-id="b67d8-130">The **Offline** checkbox puts DevTools into offline mode.</span></span>  <span data-ttu-id="b67d8-131">これは、[ネットワーク] パネルから使用できるオフライン\*\*\*\* モード、またはコマンド メニュー `Go offline` のオプションと[同じです][DevtoolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="b67d8-131">This is equivalent to the offline mode available from the **Network** panel, or the `Go offline` option in the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  
*   <span data-ttu-id="b67d8-132">[再 **読み込み時に** 更新] チェック ボックスをオンにすると、サービス ワーカーはページの読み込みごとに強制的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-132">The **Update on reload** checkbox forces the service worker to update on every page load.</span></span>  
*   <span data-ttu-id="b67d8-133">[ **ネットワークのバイパス] チェック** ボックスは、サービス ワーカーをバイパスし、要求されたリソースのネットワークにブラウザーを強制的に移動します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-133">The **Bypass for network** checkbox bypasses the service worker and forces the browser to go to the network for requested resources.</span></span>  
*   <span data-ttu-id="b67d8-134">[ **更新]** ボタンは、指定したサービス ワーカーの 1 回の更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-134">The **Update** button performs a one-time update of the specified service worker.</span></span>  
*   <span data-ttu-id="b67d8-135">プッシュ **ボタン** は、ペイロード \(ティック \ とも呼ばれる) なしでプッシュ通知 **をエミュレート**します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-135">The **Push** button emulates a push notification without a payload \(also known as a **tickle**\).</span></span>  
*   <span data-ttu-id="b67d8-136">[ **同期]** ボタンは、バックグラウンド同期イベントをエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="b67d8-136">The **Sync** button emulates a background sync event.</span></span>  
*   <span data-ttu-id="b67d8-137">[ **登録解除]** ボタンは、指定したサービス ワーカーの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-137">The **Unregister** button unregisters the specified service worker.</span></span>  <span data-ttu-id="b67d8-138">サービス ワーカー [の登録を](#clear-storage) 解除し、1 回のボタン クリックでストレージとキャッシュをワイプする方法については、「ストレージのクリア」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b67d8-138">Check out [Clear storage](#clear-storage) for a way to unregister a service worker and wipe storage and caches with a single button click.</span></span>  
*   <span data-ttu-id="b67d8-139">[ **ソース]** 行は、現在実行中のサービス ワーカーがインストールされた時間を示します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-139">The **Source** line tells you when the currently running service worker was installed.</span></span>  <span data-ttu-id="b67d8-140">リンクは、サービス ワーカーのソース ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="b67d8-140">The link is the name of the service worker's source file.</span></span>  <span data-ttu-id="b67d8-141">リンクをクリックすると、サービス ワーカーのソースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-141">Clicking on the link sends you to the service worker's source.</span></span>  
*   <span data-ttu-id="b67d8-142">[ **状態]** 行は、サービス ワーカーの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-142">The **Status** line tells you the status of the service worker.</span></span>  <span data-ttu-id="b67d8-143">緑色のステータス インジケーター \( 前の図\) の横にある ID 番号は、現在アクティブ `#36` なサービス ワーカー用です。</span><span class="sxs-lookup"><span data-stu-id="b67d8-143">The ID number next to the green status indicator \(`#36` in previous figure\) is for the currently active Service Worker.</span></span>  <span data-ttu-id="b67d8-144">状態の横には、開始ボタン \(サービス ワーカーが停止している場合\) または停止ボタン\*\*\*\* \(サービス ワーカーが実行中の場合\) が表示されます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b67d8-144">Next to the status you'll see a **start** button \(if the service worker is stopped\) or a **stop** button \(if the service worker is running\).</span></span>  <span data-ttu-id="b67d8-145">サービス ワーカーは、いつでもブラウザーによって停止および開始するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b67d8-145">Service workers are designed to be stopped and started by the browser at any time.</span></span>  <span data-ttu-id="b67d8-146">停止ボタンを使用してサービス ワーカーを明示的に **停止** すると、その動作をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-146">Explicitly stopping your service worker using the **stop** button can simulate that.</span></span>  <span data-ttu-id="b67d8-147">サービス ワーカーを停止すると、サービス ワーカーが再び起動するときにコードがどのように動作するのかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-147">Stopping your service worker is a great way to test how your code behaves when the service worker starts back up again.</span></span>  <span data-ttu-id="b67d8-148">永続的なグローバル状態に関する誤った前提により、バグが頻繁に明らかになります。</span><span class="sxs-lookup"><span data-stu-id="b67d8-148">It frequently reveals bugs due to faulty assumptions about persistent global state.</span></span>  
*   <span data-ttu-id="b67d8-149">[ **クライアント]** 行は、サービス ワーカーのスコープが設定されている発生元を示します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-149">The **Clients** line tells you the origin that the service worker is scoped to.</span></span>  <span data-ttu-id="b67d8-150">フォーカス **ボタンは** 、[すべての表示] チェック ボックスを有効にした場合 **に最も便利** です。</span><span class="sxs-lookup"><span data-stu-id="b67d8-150">The **focus** button is mostly useful when you've enabled the **show all** checkbox.</span></span>  <span data-ttu-id="b67d8-151">このチェック ボックスを有効にすると、登録されているサービス ワーカーすべてが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-151">When that checkbox is enabled, all registered service workers are listed.</span></span>  <span data-ttu-id="b67d8-152">別のタブで実行\*\*\*\* されているサービス ワーカーの横にあるフォーカス ボタンをクリックすると、Microsoft Edge ではそのタブに焦点が当てられています。</span><span class="sxs-lookup"><span data-stu-id="b67d8-152">If you click on the **focus** button next to a service worker that is running in a different tab, Microsoft Edge focuses on that tab.</span></span>  
    
<span data-ttu-id="b67d8-153">サービス ワーカーがエラーを発生すると、Errors という新しいラベル **が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-153">If the service worker causes any errors, a new label called **Errors** shows up.</span></span>  

<!--  
:::image type="complex" source="../media/sw-error.msft.png" alt-text="Service worker with errors" lightbox="../media/sw-error.msft.png":::
   Service worker with errors  
:::image-end:::
-->  

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## <span data-ttu-id="b67d8-154">サービス ワーカー キャッシュ</span><span class="sxs-lookup"><span data-stu-id="b67d8-154">Service worker caches</span></span>  

<span data-ttu-id="b67d8-155">[ **キャッシュ ストレージ]** ウィンドウには、\(サービス ワーカー\) キャッシュ API を使用してキャッシュされたリソースの読み取り専用リストが [表示されます][MDNWebCacheAPI]。</span><span class="sxs-lookup"><span data-stu-id="b67d8-155">The **Cache Storage** pane provides a read-only list of resources that have been cached using the \(service worker\) [Cache API][MDNWebCacheAPI].</span></span>  

:::image type="complex" source="../media/cache-pane-cache-storage-resources.msft.png" alt-text="[キャッシュストレージ] ウィンドウ" lightbox="../media/cache-pane-cache-storage-resources.msft.png":::
   <span data-ttu-id="b67d8-157">[ **キャッシュストレージ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b67d8-157">The **Cache Storage** Pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="b67d8-158">初めてキャッシュを開いてリソースを追加すると、DevTools が変更を検出しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b67d8-158">The first time you open a cache and add a resource to it, DevTools might not detect the change.</span></span>  <span data-ttu-id="b67d8-159">ページを再読み込みすると、キャッシュが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-159">Reload the page and you should see the cache.</span></span>  

<span data-ttu-id="b67d8-160">2 つ以上のキャッシュを開いている場合は、[キャッシュ ストレージ] ドロップダウンの下にキャッシュ **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-160">If you have two or more caches open, you'll see them listed below the **Cache Storage** dropdown.</span></span>  

:::image type="complex" source="../media/cache-pane-cache-storage.msft.png" alt-text="[キャッシュ ストレージ] ドロップダウン" lightbox="../media/cache-pane-cache-storage.msft.png":::
   <span data-ttu-id="b67d8-162">[ **キャッシュ ストレージ]** ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="b67d8-162">The **Cache Storage** dropdown</span></span>  
:::image-end:::  

## <span data-ttu-id="b67d8-163">クォータの使用状況</span><span class="sxs-lookup"><span data-stu-id="b67d8-163">Quota usage</span></span>  

<span data-ttu-id="b67d8-164">[キャッシュ ストレージ] ウィンドウ **内の一部の** 応答は、"不透明" としてフラグが設定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b67d8-164">Some responses within the **Cache Storage** pane may be flagged as being "opaque".</span></span>  <span data-ttu-id="b67d8-165">これは[、CORS][FetchHttpCorsProtocol]が有効になっていない場合に **、CDN**やリモート API など、別の配信元から取得された応答を指します。</span><span class="sxs-lookup"><span data-stu-id="b67d8-165">This refers to a response retrieved from a different origin, like from a **CDN** or remote API, when [CORS][FetchHttpCorsProtocol] is not enabled.</span></span>  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

<span data-ttu-id="b67d8-166">クロスドメイン情報の漏洩を回避するために、ストレージ クォータの制限 \(例外がスローされたかどうかなど) を計算するために使用される不透明な応答のサイズに大幅なパディングが追加され `QuotaExceeded` 、API によって報告されます。 `navigator.storage`</span><span class="sxs-lookup"><span data-stu-id="b67d8-166">In order to avoid leakage of cross-domain information, there's significant padding added to the size of an opaque response used for calculating storage quota limits \(for example whether a `QuotaExceeded` exception is thrown\) and reported by the `navigator.storage` API.</span></span>  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

<span data-ttu-id="b67d8-167">このパディングの詳細はブラウザーによって異なりますが、Microsoft Edge の場合、単\*\*\*\* 一キャッシュされた不透明な応答が記憶域全体の使用量に与える最小サイズは約[7 MB][ChromiumIssues796060#c17]です。</span><span class="sxs-lookup"><span data-stu-id="b67d8-167">The details of this padding vary from browser to browser, but for Microsoft Edge, this means that the **minimum size** that any single cached opaque response contributes to the overall storage usage is [approximately 7 megabytes][ChromiumIssues796060#c17].</span></span>  <span data-ttu-id="b67d8-168">これは、キャッシュする不透明な応答の数を決定する際に念頭に置く必要があります。これは、ストレージ クォータの制限を、不透明なリソースの実際のサイズに基づいて予想するよりもずっと早く簡単に超過する可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="b67d8-168">You should keep this in mind when determining how many opaque responses you want to cache, since you could easily exceeded storage quota limitations much sooner than you'd otherwise expect based on the actual size of the opaque resources.</span></span>  

<span data-ttu-id="b67d8-169">関連ガイド:</span><span class="sxs-lookup"><span data-stu-id="b67d8-169">Related Guides:</span></span>  

*   [<span data-ttu-id="b67d8-170">スタック オーバーフロー: 不透明な応答に適用される制限</span><span class="sxs-lookup"><span data-stu-id="b67d8-170">Stack Overflow: What limitations apply to opaque responses?</span></span>][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->
    
<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## <span data-ttu-id="b67d8-171">ストレージのクリア</span><span class="sxs-lookup"><span data-stu-id="b67d8-171">Clear storage</span></span>  

<span data-ttu-id="b67d8-172">[ **ストレージのクリア]** ウィンドウは、段階的な Web アプリを開発するときに非常に便利な機能です。</span><span class="sxs-lookup"><span data-stu-id="b67d8-172">The **Clear Storage** pane is a very useful feature when developing progressive web apps.</span></span>  <span data-ttu-id="b67d8-173">このウィンドウでは、サービス ワーカーの登録を解除し、ボタンを 1 回クリックしてすべてのキャッシュとストレージをクリアできます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-173">This pane lets you unregister service workers and clear all caches and storage with a single button click.</span></span>  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->
    
<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides   

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->
    
## <span data-ttu-id="b67d8-174">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="b67d8-174">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する |Microsoft Docs"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium の問題 796060: 分析コードが html 内にある場合、更新ごとにキャッシュ ストレージの値が増加する"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ - Web API |MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "スタック オーバーフロー: 不透明な応答に適用される制限"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> <span data-ttu-id="b67d8-179">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="b67d8-179">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b67d8-180">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="b67d8-180">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b67d8-182">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b67d8-182">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
