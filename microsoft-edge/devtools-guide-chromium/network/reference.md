---
title: ネットワーク分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 460ad05983e7615e8739953ce3cb7d559492bc90
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611841"
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







# <span data-ttu-id="0bb0b-103">ネットワーク分析のリファレンス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-103">Network Analysis Reference</span></span>   



<span data-ttu-id="0bb0b-104">Microsoft Edge DevTools のネットワーク分析機能の包括的な参照でページがどのように読み込まれるかを分析するための新しい方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-104">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

<!--
> [!NOTE]
> This reference is based on Microsoft Edge 58.  If you use another version of Microsoft Edge, the UI, and features of DevTools may be different.  Check `edge://help` to see what version of Microsoft Edge you are running.  
-->

## <span data-ttu-id="0bb0b-105">ネットワーク要求を記録する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-105">Record network requests</span></span>   

<span data-ttu-id="0bb0b-106">既定では、devtools はネットワークパネルのすべてのネットワーク要求を記録します。これは、DevTools が開いている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-106">By default, DevTools records all network requests in the Network panel, so long as DevTools is open.</span></span>  

> ##### <span data-ttu-id="0bb0b-107">図 1</span><span class="sxs-lookup"><span data-stu-id="0bb0b-107">Figure 1</span></span>  
> <span data-ttu-id="0bb0b-108">[ネットワーク] パネル</span><span class="sxs-lookup"><span data-stu-id="0bb0b-108">The Network panel</span></span>  
> ![[ネットワーク] パネル][ImageNetworkPanel]  

### <span data-ttu-id="0bb0b-110">ネットワーク要求の記録を停止する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-110">Stop recording network requests</span></span>   

<span data-ttu-id="0bb0b-111">要求の記録を停止するには:</span><span class="sxs-lookup"><span data-stu-id="0bb0b-111">To stop recording requests:</span></span>  

*   <span data-ttu-id="0bb0b-112">[ **Stop recording network log** ![ ][ImageRecordOnIcon] **ネットワーク**] パネルで [ネットワークログの記録停止] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-112">Select **Stop recording network log** ![Stop recording network log][ImageRecordOnIcon] on the **Network** panel.</span></span>  <span data-ttu-id="0bb0b-113">灰色に変わり、DevTools が要求を記録しなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
*   <span data-ttu-id="0bb0b-114">`Control` + `E` `Command` + `E` **ネットワーク**パネルがフォーカスされているときに、\ (Windows \) または \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-114">Press `Control`+`E` \(Windows\) or `Command`+`E` \(macOS\) while the **Network** panel is in focus.</span></span>  

### <span data-ttu-id="0bb0b-115">要求をクリアする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-115">Clear requests</span></span>   

<span data-ttu-id="0bb0b-116">[ネットワーク] パネルの [**クリア] を**選ん ![ ][ImageClearIcon] で、要求テーブルからのすべての要求をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-116">Select **Clear** ![Clear][ImageClearIcon] on the Network panel to clear all requests from the Requests table.</span></span>  

> ##### <span data-ttu-id="0bb0b-117">図 2</span><span class="sxs-lookup"><span data-stu-id="0bb0b-117">Figure 2</span></span>  
> <span data-ttu-id="0bb0b-118">[クリア] ボタン</span><span class="sxs-lookup"><span data-stu-id="0bb0b-118">The Clear button</span></span>  
> ![[クリア] ボタン][ImageClearButton]  

### <span data-ttu-id="0bb0b-120">ページのロード間で要求を保存する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-120">Save requests across page loads</span></span>   

<span data-ttu-id="0bb0b-121">ページの読み込み時に要求を保存するには、[ネットワーク] パネルの [**ログを保持**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-121">To save requests across page loads, check the **Preserve log** checkbox on the Network panel.</span></span>  <span data-ttu-id="0bb0b-122">DevTools では、 **Preserve log**を無効にするまで、すべての要求が保存されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-122">DevTools saves all requests until you disable **Preserve log**.</span></span>  

> ##### <span data-ttu-id="0bb0b-123">図 3</span><span class="sxs-lookup"><span data-stu-id="0bb0b-123">Figure 3</span></span>  
> <span data-ttu-id="0bb0b-124">[ログの保存] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-124">The Preserve Log checkbox</span></span>  
> ![[ログの保存] チェックボックス][ImagePreserveLogCheckBox]  

### <span data-ttu-id="0bb0b-126">ページの読み込み中にスクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-126">Capture screenshots during page load</span></span>   

<span data-ttu-id="0bb0b-127">スクリーンショットをキャプチャして、ページの読み込みを待機しているユーザーに表示される内容を分析します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-127">Capture screenshots to analyze what users see as they wait for your page to load.</span></span>  

<span data-ttu-id="0bb0b-128">スクリーンショットを有効にするには、[**ネットワーク設定**] を選択し、[**ネットワーク**] パネルの [**スクリーンショットのキャプチャ**] チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-128">To enable screenshots, select **Network settings** and select **Capture screenshots** checkbox on the **Network** panel.</span></span>  

<span data-ttu-id="0bb0b-129">**ネットワーク**パネルがフォーカスされているときにページを再読み込みして、スクリーンショットをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-129">Reload the page while the **Network** panel is in focus to capture screenshots.</span></span>  

<span data-ttu-id="0bb0b-130">スクリーンショットをキャプチャした後、次のように操作します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-130">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="0bb0b-131">スクリーンショットにマウスポインターを置くと、そのスクリーンショットがキャプチャされた点が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-131">Hover over a screenshot to view the point at which that screenshot was captured.</span></span>  <span data-ttu-id="0bb0b-132">[**概要**] ウィンドウに黄色の線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-132">A yellow line appears on the **Overview** pane.</span></span>  
*   <span data-ttu-id="0bb0b-133">スクリーンショットがキャプチャされた後に発生した要求をすべて除外するには、画面のサムネイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-133">Select the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="0bb0b-134">サムネイルをダブルクリックして、拡大表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-134">Double-click a thumbnail to zoom in on it.</span></span>  

> ##### <span data-ttu-id="0bb0b-135">図 4</span><span class="sxs-lookup"><span data-stu-id="0bb0b-135">Figure 4</span></span>  
> <span data-ttu-id="0bb0b-136">スクリーンショット上のマウスポインター</span><span class="sxs-lookup"><span data-stu-id="0bb0b-136">Hovering over a screenshot</span></span>  
> ![スクリーンショット上のマウスポインター][ImageScreenshotHover]  

<!--  ### Replay XHR request   -->

<!--  To replay an XHR request, right-click the request in the Requests table and select **Replay XHR**.  -->

<!--  
> ##### Old Figure 5  
> Selecting Replay XHR  
> ![Selecting Replay XHR][ImageReplayXHR]  
-->  

## <span data-ttu-id="0bb0b-138">読み込み動作を変更する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-138">Change loading behavior</span></span>  

### <span data-ttu-id="0bb0b-139">ブラウザーのキャッシュを無効にして、初めてのユーザーをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-139">Emulate a first-time visitor by disabling the browser cache</span></span>   

<span data-ttu-id="0bb0b-140">初めてのユーザーがサイトを体験した方法をエミュレートするには、[**キャッシュを無効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-140">To emulate how a first-time user experiences your site, check the **Disable cache** checkbox.</span></span>  <span data-ttu-id="0bb0b-141">DevTools は、ブラウザーのキャッシュを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-141">DevTools disables the browser cache.</span></span>  <span data-ttu-id="0bb0b-142">これにより、初回のユーザーエクスペリエンスが正確にエミュレートされます。要求は、繰り返しアクセスの際にブラウザーのキャッシュから提供されるためです。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-142">This more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

> ##### <span data-ttu-id="0bb0b-143">図 5</span><span class="sxs-lookup"><span data-stu-id="0bb0b-143">Figure 5</span></span>  
> <span data-ttu-id="0bb0b-144">[キャッシュを無効にする] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-144">The Disable Cache checkbox</span></span>  
> <span data-ttu-id="0bb0b-145">![キャッシュを無効にする] チェックボックス[ImageDisableCacheCheckBox]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-145">![The Disable Cache checkbox][ImageDisableCacheCheckBox]</span></span>  

#### <span data-ttu-id="0bb0b-146">[ネットワーク条件] ドロアーからブラウザーキャッシュを無効にする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-146">Disable the browser cache from the Network Conditions drawer</span></span>   

<span data-ttu-id="0bb0b-147">他の DevTools パネルを操作しているときに、キャッシュを無効にするには、[ネットワーク条件] ドローワを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-147">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="0bb0b-148">[**ネットワーク条件**] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-148">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="0bb0b-149">[**キャッシュを無効にする**] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-149">Check or uncheck the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="0bb0b-150">ブラウザキャッシュを手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-150">Manually clear the browser cache</span></span>   

<span data-ttu-id="0bb0b-151">いつでもブラウザキャッシュを手動でクリアするには、要求テーブルの任意の場所を右クリックして、[**ブラウザキャッシュのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-151">To manually clear the browser cache at any time, right-click anywhere in the Requests table and select **Clear Browser Cache**.</span></span>  

> ##### <span data-ttu-id="0bb0b-152">図 6</span><span class="sxs-lookup"><span data-stu-id="0bb0b-152">Figure 6</span></span>  
> <span data-ttu-id="0bb0b-153">[ブラウザーキャッシュのクリア] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-153">Selecting Clear Browser Cache</span></span>  
> <span data-ttu-id="0bb0b-154">![ブラウザキャッシュのクリア] を選択します。[ImageClearBrowserCache]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-154">![Selecting Clear Browser Cache][ImageClearBrowserCache]</span></span>  

### <span data-ttu-id="0bb0b-155">オフラインでエミュレートする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-155">Emulate offline</span></span>   

<span data-ttu-id="0bb0b-156">[プログレッシブ Web アプリ][DevtoolsProgressiveWebApps]と呼ばれる新しいクラスの web アプリでは、サービスの担当**者**のためにオフラインで機能します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-156">A new class of web apps, called [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="0bb0b-157">この種類のアプリを構築しているときに、データ接続がないデバイスをすばやくシミュレートすると便利です。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-157">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="0bb0b-158">[**オンライン**] ドロップダウンメニューを選択し、[**プリセット**] で検索し、[**オフライン**] を選択して、完全にオフラインのネットワークエクスペリエンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-158">Select the **Online** dropdown menu, search under **Presets**, and select **Offline** to simulate a completely offline network experience.</span></span>  

> ##### <span data-ttu-id="0bb0b-159">図 7</span><span class="sxs-lookup"><span data-stu-id="0bb0b-159">Figure 7</span></span>  
> <span data-ttu-id="0bb0b-160">[オフライン] ドロップダウンメニュー</span><span class="sxs-lookup"><span data-stu-id="0bb0b-160">The Offline dropdown menu</span></span>  
> <span data-ttu-id="0bb0b-161">![オフライン] ドロップダウンメニュー[ImageOfflineDropdown]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-161">![The Offline dropdown menu][ImageOfflineDropdown]</span></span>  

### <span data-ttu-id="0bb0b-162">低速ネットワーク接続のエミュレート</span><span class="sxs-lookup"><span data-stu-id="0bb0b-162">Emulate slow network connections</span></span>   

<span data-ttu-id="0bb0b-163">「**オンライン**」ドロップダウンメニューから、低速の3G、Fast 3g、その他の接続速度をエミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-163">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

> ##### <span data-ttu-id="0bb0b-164">図 8</span><span class="sxs-lookup"><span data-stu-id="0bb0b-164">Figure 8</span></span>  
> <span data-ttu-id="0bb0b-165">[調整] ドロップダウンメニュー</span><span class="sxs-lookup"><span data-stu-id="0bb0b-165">The Throttling dropdown menu</span></span>  
> <span data-ttu-id="0bb0b-166">![調整] ドロップダウンメニュー[ImageNetworkThrottlingMenu]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-166">![The Throttling dropdown menu][ImageNetworkThrottlingMenu]</span></span>  

<span data-ttu-id="0bb0b-167">低速の3G や Fast 3G など、さまざまなプリセットから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-167">You may select from a variety of presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="0bb0b-168">また、[調整] メニューを開き、[**カスタム**追加] を選択して、独自のカスタムプリセットを追加することもでき  >  **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-168">You may also add your own custom presets by opening the Throttling menu and selecting **Custom** > **Add**.</span></span>  

<span data-ttu-id="0bb0b-169">DevTools は、調整が有効になっていることを通知するために、[**ネットワーク**] タブの横に警告アイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-169">DevTools displays a warning icon next to the **Network** tab to remind you that throttling is enabled.</span></span>  

#### <span data-ttu-id="0bb0b-170">ネットワークの状態のドロアーからの低速ネットワーク接続のエミュレート</span><span class="sxs-lookup"><span data-stu-id="0bb0b-170">Emulate slow network connections from the Network Conditions drawer</span></span>   

<span data-ttu-id="0bb0b-171">他の DevTools パネルでの作業中にネットワーク接続を調整したい場合は、ネットワーク条件の引き出しを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-171">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="0bb0b-172">[**ネットワーク条件**] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-172">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="0bb0b-173">**調整**メニューから希望の接続速度を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-173">Select your desired connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="0bb0b-174">ブラウザーの cookie を手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-174">Manually clear browser cookies</span></span>   

<span data-ttu-id="0bb0b-175">ブラウザの cookie をいつでも手動でクリアするには、要求テーブルの任意の場所を右クリックして、[**ブラウザクッキーのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-175">To manually clear browser cookies at any time, right-click anywhere in the Requests table and select **Clear Browser Cookies**.</span></span>  

> ##### <span data-ttu-id="0bb0b-176">図 9</span><span class="sxs-lookup"><span data-stu-id="0bb0b-176">Figure 9</span></span>  
> <span data-ttu-id="0bb0b-177">[ブラウザーのクリア Cookie の選択]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-177">Selecting Clear Browser Cookies</span></span>  
> <span data-ttu-id="0bb0b-178">![ブラウザーのクリア Cookie の選択][ImageClearBrowserCookies]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-178">![Selecting Clear Browser Cookies][ImageClearBrowserCookies]</span></span>  

### <span data-ttu-id="0bb0b-179">ユーザーエージェントを上書きする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-179">Override the user agent</span></span>   

<span data-ttu-id="0bb0b-180">ユーザーエージェントを手動で上書きするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-180">To manually override the user agent:</span></span>  

1.  <span data-ttu-id="0bb0b-181">[**ネットワーク条件**] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-181">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="0bb0b-182">**[自動] をオフに**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-182">Uncheck **Select automatically**.</span></span>  
1.  <span data-ttu-id="0bb0b-183">メニューからユーザーエージェントオプションを選択するか、テキストボックスにユーザー設定のオプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-183">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <span data-ttu-id="0bb0b-184">フィルター要求</span><span class="sxs-lookup"><span data-stu-id="0bb0b-184">Filter requests</span></span>   

### <span data-ttu-id="0bb0b-185">プロパティによって要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-185">Filter requests by properties</span></span>   

<span data-ttu-id="0bb0b-186">[**フィルター** ] テキストボックスを使用して、要求のドメインやサイズなどのプロパティによって要求をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-186">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="0bb0b-187">テキストボックスが表示されない場合は、[フィルター] ウィンドウが非表示になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-187">If you do not see the text box, the Filters pane is probably hidden.</span></span>  
<span data-ttu-id="0bb0b-188">「[フィルターウィンドウを非表示にする」を](#hide-the-filters-pane)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-188">See [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

> ##### <span data-ttu-id="0bb0b-189">図 10</span><span class="sxs-lookup"><span data-stu-id="0bb0b-189">Figure 10</span></span>  
> <span data-ttu-id="0bb0b-190">[フィルター] テキストボックス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-190">The Filters text box</span></span>  
> <span data-ttu-id="0bb0b-191">![フィルター] テキストボックス[ImageFilterTextBox]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-191">![The Filters text box][ImageFilterTextBox]</span></span>  

<span data-ttu-id="0bb0b-192">各プロパティをスペースで区切ることで、複数のプロパティを同時に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-192">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="0bb0b-193">たとえば、 `mime-type:image/png larger-than:1K` 1 kb より大きいすべての PNGs を表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-193">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than one kilobyte.</span></span>  <span data-ttu-id="0bb0b-194">これらのマルチプロパティフィルターは、操作に相当 `AND` します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-194">These multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="0bb0b-195">操作は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-195">operations are currently not supported.</span></span>  

<span data-ttu-id="0bb0b-196">サポートされているプロパティの完全な一覧です。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-196">The complete list of supported properties.</span></span>  

| <span data-ttu-id="0bb0b-197">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-197">Property</span></span> | <span data-ttu-id="0bb0b-198">詳細</span><span class="sxs-lookup"><span data-stu-id="0bb0b-198">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="0bb0b-199">指定したドメインのリソースのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-199">Only display resources from the specified domain.</span></span>  <span data-ttu-id="0bb0b-200">複数のドメインを含めるには、ワイルドカード文字 \ (\) を使用することができ `*` ます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-200">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="0bb0b-201">たとえば、 `*.com` で終わるすべてのドメイン名のリソースが表示され `.com` ます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-201">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="0bb0b-202">DevTools は、オートコンプリートのドロップダウンメニューに、検出されたすべてのドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-202">DevTools populates the autocomplete dropdown menu with all of the domains it has encountered.</span></span> |  
| `has-response-header` | <span data-ttu-id="0bb0b-203">指定した HTTP 応答ヘッダーを含むリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-203">Show the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="0bb0b-204">DevTools は、オートコンプリートのドロップダウンリストに、検出されたすべての応答ヘッダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-204">DevTools populates the autocomplete dropdown with all of the response headers that it has encountered.</span></span> |  
| `is` | <span data-ttu-id="0bb0b-205">`is:running`リソースを検索するために使用 `WebSocket` します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-205">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="0bb0b-206">指定したサイズよりも大きいリソースをバイト単位で表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-206">Show resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="0bb0b-207">値の設定 `1000` は、の値の設定に相当 `1k` します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-207">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="0bb0b-208">指定した HTTP メソッドの種類によって取得されたリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-208">Show resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="0bb0b-209">DevTools は、検出されたすべての HTTP メソッドをドロップダウンに入力します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-209">DevTools populates the dropdown with all of the HTTP methods it has encountered.</span></span> |  
| `mime-type` | <span data-ttu-id="0bb0b-210">指定した MIME の種類のリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-210">Show resources of a specified MIME type.</span></span>  <span data-ttu-id="0bb0b-211">DevTools は、検出されたすべての MIME の種類をドロップダウンに入力します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-211">DevTools populates the dropdown with all MIME types it has encountered.</span></span> |  
| `mixed-content` | <span data-ttu-id="0bb0b-212">すべての混合コンテンツリソース \ ( `mixed-content:all` \) を表示するか、現在 \ (\) を表示しているものだけを表示し `mixed-content:displayed` ます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-212">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="0bb0b-213">保護されていない HTTP \ ( `scheme:http` \) または保護された HTTPS \ (\) 経由で取得したリソースを表示 `scheme:https` します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-213">Show resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="0bb0b-214">指定した `Set-Cookie` 値と一致する属性を持つヘッダーが含まれているリソースを表示し `Domain` ます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-214">Show the resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="0bb0b-215">DevTools は、検出されたすべての cookie ドメインにオートコンプリートを設定します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-215">DevTools populates the autocomplete with all of the cookie domains that it has encountered.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="0bb0b-216">指定した値と一致する名前のヘッダーが含まれているリソースを表示し `Set-Cookie` ます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-216">Show the resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="0bb0b-217">DevTools は、検出されたすべての cookie 名でオートコンプリートを入力します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-217">DevTools populates the autocomplete with all of the cookie names that it has encountered.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="0bb0b-218">指定した `Set-Cookie` 値と一致する値を含むヘッダーが含まれているリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-218">Show the resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="0bb0b-219">DevTools は、検出されたすべての cookie 値でオートコンプリートを設定します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-219">DevTools populates the autocomplete with all of the cookie values that it has encountered.</span></span> |  
| `status-code` | <span data-ttu-id="0bb0b-220">HTTP ステータスコードが指定されたコードと一致するリソースのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-220">Show only the resources for which the HTTP status code matches the specified code.</span></span>  <span data-ttu-id="0bb0b-221">DevTools は、オートコンプリートのドロップダウンメニューに、検出されたすべての状態コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-221">DevTools populates the autocomplete dropdown menu with all of the status codes it has encountered.</span></span> |  

### <span data-ttu-id="0bb0b-222">種類別に要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-222">Filter requests by type</span></span>   

<span data-ttu-id="0bb0b-223">要求の種類によって要求をフィルター処理するには、[ネットワーク] パネルの**Xhr**、 **JS**、 **CSS**、 **Img**、 **Media**、 **Font**、 **Doc**、 **WS** \ (WebSocket \)、**マニフェスト**、**その他**\ (ここに一覧表示されていないその他の種類) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-223">To filter requests by request type, select the **XHR**, **JS**, **CSS**, **Img**, **Media**, **Font**, **Doc**, **WS** \(WebSocket\), **Manifest**, or **Other** \(any other type not listed here\) buttons on the Network panel.</span></span>  

<span data-ttu-id="0bb0b-224">これらのボタンが表示されない場合は、[フィルター] ウィンドウが非表示になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-224">If you do not see these buttons, the Filters pane is probably hidden.</span></span>  
<span data-ttu-id="0bb0b-225">「[フィルターウィンドウを非表示にする」を](#hide-the-filters-pane)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-225">See [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="0bb0b-226">複数の種類のフィルターを同時に有効にするに `Control` は、\ (Windows \) または `Command` \ (macOS \) を保持し、を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-226">To enable multiple type filters simultaneously, hold `Control` \(Windows\) or `Command` \(macOS\) and then select.</span></span>  

> ##### <span data-ttu-id="0bb0b-227">図 11</span><span class="sxs-lookup"><span data-stu-id="0bb0b-227">Figure 11</span></span>  
> <span data-ttu-id="0bb0b-228">型フィルターを使用した JS、CSS、およびドキュメントのリソースの表示</span><span class="sxs-lookup"><span data-stu-id="0bb0b-228">Using the Type filters to display JS, CSS, and Document resources</span></span>  
> <span data-ttu-id="0bb0b-229">![型フィルターを使用して JS、CSS、およびドキュメントのリソースを表示する][ImageMultiTypeFilter]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-229">![Using the Type filters to display JS, CSS, and Document resources][ImageMultiTypeFilter]</span></span>  

### <span data-ttu-id="0bb0b-230">時間に基づいて要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-230">Filter requests by time</span></span>   

<span data-ttu-id="0bb0b-231">[概要] ウィンドウで左または右にドラッグすると、その期間中にアクティブだった要求のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-231">Select and drag left or right on the Overview pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="0bb0b-232">フィルターは包含されています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-232">The filter is inclusive.</span></span>  <span data-ttu-id="0bb0b-233">強調表示された時間にアクティブだった要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-233">Any request that was active during the highlighted time is shown.</span></span>  

> ##### <span data-ttu-id="0bb0b-234">図 12</span><span class="sxs-lookup"><span data-stu-id="0bb0b-234">Figure 12</span></span>  
> <span data-ttu-id="0bb0b-235">300ms の非アクティブな要求をすべてフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-235">Filtering out any requests that were inactive around 300ms</span></span>  
> <span data-ttu-id="0bb0b-236">![300 ミリ秒を経由しない非アクティブな要求をフィルター処理しています][Image概要フィルター]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-236">![Filtering out any requests that were inactive around 300ms][ImageOverviewFilter]</span></span>  

### <span data-ttu-id="0bb0b-237">データ Url を非表示にする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-237">Hide data URLs</span></span>  

<span data-ttu-id="0bb0b-238">[データ url][MDNHTTPDataURIs]は、他のドキュメントに埋め込まれた小さなファイルです。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-238">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="0bb0b-239">が開始する要求テーブルに `data:` は、データの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-239">Any request that you see in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="0bb0b-240">[**データ url の非表示**] チェックボックスをオンにして、これらの要求を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-240">Check the **Hide data URLs** checkbox to hide these requests.</span></span>  

> ##### <span data-ttu-id="0bb0b-241">図 13</span><span class="sxs-lookup"><span data-stu-id="0bb0b-241">Figure 13</span></span>  
> <span data-ttu-id="0bb0b-242">[データ Url を非表示にする] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-242">The Hide Data URLs checkbox</span></span>  
> <span data-ttu-id="0bb0b-243">![データ Url を非表示にする] チェックボックス[ImageHideDataURLsCheckBox]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-243">![The Hide Data URLs checkbox][ImageHideDataURLsCheckBox]</span></span>  

## <span data-ttu-id="0bb0b-244">並べ替え要求</span><span class="sxs-lookup"><span data-stu-id="0bb0b-244">Sort requests</span></span>  

<span data-ttu-id="0bb0b-245">既定では、要求テーブルの要求は開始時刻によって並べ替えられますが、他の条件を使用してテーブルを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-245">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <span data-ttu-id="0bb0b-246">列で並べ替え</span><span class="sxs-lookup"><span data-stu-id="0bb0b-246">Sort by column</span></span>   

<span data-ttu-id="0bb0b-247">要求内の任意の列のヘッダーを選び、その列によって要求を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-247">Select the header of any column in the Requests to sort requests by that column.</span></span>  

### <span data-ttu-id="0bb0b-248">アクティビティ別の並べ替えフェーズ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-248">Sort by activity phase</span></span>   

<span data-ttu-id="0bb0b-249">ウォーターフォールでのリクエストの並べ替え方法を変更するには、要求テーブルのヘッダーを右クリックし、**ウォーターフォール**をポイントして、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-249">To change how the Waterfall sorts requests, right-click the header of the Requests table, hover over **Waterfall**, and select one of the following options.</span></span>  

*   <span data-ttu-id="0bb0b-250">**開始時刻**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-250">**Start Time**.</span></span>  <span data-ttu-id="0bb0b-251">最初に開始された要求は一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-251">The first request that was initiated is at the top.</span></span>  
*   <span data-ttu-id="0bb0b-252">**応答時間**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-252">**Response Time**.</span></span>  <span data-ttu-id="0bb0b-253">ダウンロードを開始した最初の要求は上部にあります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-253">The first request that started downloading is at the top.</span></span>  
*   <span data-ttu-id="0bb0b-254">**終了時刻**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-254">**End Time**.</span></span>  <span data-ttu-id="0bb0b-255">最初の要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-255">The first request that finished is at the top.</span></span>  
*   <span data-ttu-id="0bb0b-256">**合計期間**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-256">**Total Duration**.</span></span>  <span data-ttu-id="0bb0b-257">最短接続の設定と要求/応答を含む要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-257">The request with the shortest connection setup and request / response is at the top.</span></span>  
*   <span data-ttu-id="0bb0b-258">**待機時間**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-258">**Latency**.</span></span>  <span data-ttu-id="0bb0b-259">応答の最短時間を待っている要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-259">The request that waited the shortest time for a response is at the top.</span></span>  

<span data-ttu-id="0bb0b-260">これらの説明は、それぞれのオプションが最短から最長の順にランク付けされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-260">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="0bb0b-261">[**ウォーターフォール**] 列のヘッダーを選択すると、順序が逆になります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-261">Selecting the header of the **Waterfall** column reverses the order.</span></span>  

> ##### <span data-ttu-id="0bb0b-262">図 14</span><span class="sxs-lookup"><span data-stu-id="0bb0b-262">Figure 14</span></span>  
> <span data-ttu-id="0bb0b-263">ウォーターフォールを合計期間で並べ替える (各バーの明るい部分は待機時間で、暗い部分はバイトのダウンロードにかかる時間です)。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-263">Sorting the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
> <span data-ttu-id="0bb0b-264">![ウォーターフォールを合計期間で並べ替える][ImageWaterfallTotalDuration]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-264">![Sorting the Waterfall by total duration][ImageWaterfallTotalDuration]</span></span>  

## <span data-ttu-id="0bb0b-265">分析要求</span><span class="sxs-lookup"><span data-stu-id="0bb0b-265">Analyze requests</span></span>   

<span data-ttu-id="0bb0b-266">DevTools が開いている限り、すべての要求がネットワークパネルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-266">So long as DevTools is open, it logs all requests in the Network panel.</span></span>  
<span data-ttu-id="0bb0b-267">[ネットワーク] パネルを使用して要求を分析します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-267">Use the Network panel to analyze requests.</span></span>  

### <span data-ttu-id="0bb0b-268">要求のログを表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-268">View a log of requests</span></span>   

<span data-ttu-id="0bb0b-269">[要求] テーブルを使って、DevTools が開いている間に行われたすべての要求のログを表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-269">Use the Requests table to view a log of all requests made while DevTools has been open.</span></span>  <span data-ttu-id="0bb0b-270">要求を選択またはマウスでポイントすると、各項目の詳細情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-270">Selecting or hovering over requests reveals more information about each item.</span></span>  

> ##### <span data-ttu-id="0bb0b-271">図 15</span><span class="sxs-lookup"><span data-stu-id="0bb0b-271">Figure 15</span></span>  
> <span data-ttu-id="0bb0b-272">要求テーブル</span><span class="sxs-lookup"><span data-stu-id="0bb0b-272">The Requests table</span></span>  
> <span data-ttu-id="0bb0b-273">![リクエスト] テーブル[ImageRequestsTable]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-273">![The Requests table][ImageRequestsTable]</span></span>  

<span data-ttu-id="0bb0b-274">要求テーブルには、既定で次の列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-274">The Requests table displays the following columns by default:</span></span>  

*   <span data-ttu-id="0bb0b-275">**[名前]**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-275">**Name**.</span></span>  <span data-ttu-id="0bb0b-276">リソースのファイル名または識別子。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-276">The filename of, or an identifier for, the resource.</span></span>  
*   <span data-ttu-id="0bb0b-277">**状態**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-277">**Status**.</span></span>  <span data-ttu-id="0bb0b-278">HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-278">The HTTP status code.</span></span>  
*   <span data-ttu-id="0bb0b-279">**[種類]**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-279">**Type**.</span></span>  <span data-ttu-id="0bb0b-280">要求されたリソースの MIME の種類。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-280">The MIME type of the requested resource.</span></span>  
*   <span data-ttu-id="0bb0b-281">**イニシエーター**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-281">**Initiator**.</span></span>  <span data-ttu-id="0bb0b-282">次のオブジェクトまたはプロセスで要求が開始されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-282">The following objects or processes initiate requests:</span></span>  
    *   <span data-ttu-id="0bb0b-283">**パーサー**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-283">**Parser**.</span></span>  <span data-ttu-id="0bb0b-284">Microsoft Edge の HTML パーサー。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-284">The HTML parser for Microsoft Edge.</span></span>  
    *   <span data-ttu-id="0bb0b-285">**リダイレクト**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-285">**Redirect**.</span></span>  <span data-ttu-id="0bb0b-286">HTTP リダイレクト。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-286">An HTTP redirect.</span></span>  
    *   <span data-ttu-id="0bb0b-287">**スクリプト**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-287">**Script**.</span></span>  <span data-ttu-id="0bb0b-288">JavaScript 関数。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-288">A JavaScript function.</span></span>  
    *   <span data-ttu-id="0bb0b-289">**その他**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-289">**Other**.</span></span>  <span data-ttu-id="0bb0b-290">リンクを介してページに移動したり、アドレスバーに URL を入力したりするなど、他のプロセスまたはアクション。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-290">Some other process or action, such as navigating to a page via a link or entering a URL in the address bar.</span></span>  
*   <span data-ttu-id="0bb0b-291">**サイズ**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-291">**Size**.</span></span>  <span data-ttu-id="0bb0b-292">サーバーによって配信された、返信ヘッダーと応答本文の合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-292">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
*   <span data-ttu-id="0bb0b-293">**時刻**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-293">**Time**.</span></span>  <span data-ttu-id="0bb0b-294">要求の開始から、応答の最後のバイトの受領までの合計時間。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-294">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
*   <span data-ttu-id="0bb0b-295">[**ウォーターフォール**](#view-the-timing-of-requests-in-relation-to-one-another)</span><span class="sxs-lookup"><span data-stu-id="0bb0b-295">[**Waterfall**](#view-the-timing-of-requests-in-relation-to-one-another).</span></span>  <span data-ttu-id="0bb0b-296">各要求のアクティビティの視覚的な分類。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-296">A visual breakdown of the activity for each request.</span></span>  

#### <span data-ttu-id="0bb0b-297">列を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-297">Add or remove columns</span></span>   

<span data-ttu-id="0bb0b-298">要求テーブルのヘッダーを右クリックして、表示または非表示にするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-298">Right-click the header of the Requests table and select an option to hide or show it.</span></span>  <span data-ttu-id="0bb0b-299">現在表示されているオプションは各項目の横にチェックマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-299">Currently displayed options have checkmarks next to each item.</span></span>  

> ##### <span data-ttu-id="0bb0b-300">図 16</span><span class="sxs-lookup"><span data-stu-id="0bb0b-300">Figure 16</span></span>  
> <span data-ttu-id="0bb0b-301">要求テーブルへの列の追加</span><span class="sxs-lookup"><span data-stu-id="0bb0b-301">Adding a column to the Requests table</span></span>  
> <span data-ttu-id="0bb0b-302">![要求テーブルに列を追加しています][ImageRequestsTableAddColumn]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-302">![Adding a column to the Requests table][ImageRequestsTableAddColumn]</span></span>  

#### <span data-ttu-id="0bb0b-303">カスタム列を追加する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-303">Add custom columns</span></span>   

<span data-ttu-id="0bb0b-304">要求テーブルにカスタム列を追加するには、要求テーブルのヘッダーを右クリックし、[**応答ヘッダー**] を選択して、  >  **ヘッダー列を管理**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-304">To add a custom column to the Requests table, right-click the header of the Requests table and select **Response Headers** > **Manage Header Columns**.</span></span>  

> ##### <span data-ttu-id="0bb0b-305">図 17</span><span class="sxs-lookup"><span data-stu-id="0bb0b-305">Figure 17</span></span>  
> <span data-ttu-id="0bb0b-306">要求テーブルへのカスタム列の追加</span><span class="sxs-lookup"><span data-stu-id="0bb0b-306">Adding a custom column to the Requests table</span></span>  
> <span data-ttu-id="0bb0b-307">![要求テーブルにカスタム列を追加しています][ImageRequestsTableCustomColumn]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-307">![Adding a custom column to the Requests table][ImageRequestsTableCustomColumn]</span></span>  

### <span data-ttu-id="0bb0b-308">相互に関連した要求のタイミングを表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-308">View the timing of requests in relation to one another</span></span>   

<span data-ttu-id="0bb0b-309">ウォーターフォールを使用すると、要求のタイミングを相互に関連して表示できます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-309">Use the Waterfall to view the timing of requests in relation to one another.</span></span>  
<span data-ttu-id="0bb0b-310">既定では、ウォーターフォールは要求の開始時刻によって構成されています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-310">By default, the Waterfall is organized by the start time of the requests.</span></span>  
<span data-ttu-id="0bb0b-311">そのため、左から右に向けて開始された要求よりも早く開始されています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-311">So, requests that are farther to the left started earlier than those that are farther to the right.</span></span>  

<span data-ttu-id="0bb0b-312">ウォーターフォールのさまざまな並べ替え方法を確認するには、「[アクティビティ別に並べ替える](#sort-by-activity-phase)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-312">See [Sort by activity phase](#sort-by-activity-phase) to see the different ways that you may sort the Waterfall.</span></span>  

> ##### <span data-ttu-id="0bb0b-313">図18</span><span class="sxs-lookup"><span data-stu-id="0bb0b-313">Figure 18</span></span>  
> <span data-ttu-id="0bb0b-314">[要求] ウィンドウの [ウォーターフォール] 列</span><span class="sxs-lookup"><span data-stu-id="0bb0b-314">The Waterfall column of the Requests pane</span></span>  
> <span data-ttu-id="0bb0b-315">![要求] ウィンドウの [ウォーターフォール] 列[ImageRequestsTableWaterfallColumn]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-315">![The Waterfall column of the Requests pane][ImageRequestsTableWaterfallColumn]</span></span>  

<!-- ### Analyze the frames of a WebSocket Connection   -->

<!--To view the frames of a WebSocket connection:  

1.  Select the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Select the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-click the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
> ##### Old Figure 20  
> The Frames tab  
> ![The Frames tab][ImageFrames]  
-->

<!--The table contains three columns:  

*   **Data**.  The message payload.  If the message is plain text, it is displayed here.  For binary opcodes, this column displays the name and code of the opcode.  The following opcodes are supported: Continuation Frame, Binary Frame, Connection Close Frame, Ping Frame, and Pong Frame.  
*   **Length**.  The length of the message payload, in bytes.  
*   **Time**.  The time when the message was received or sent.  -->

<!--Messages are color-coded according to their type:  

*   Outgoing text messages are light-green.  
*   Incoming text messages are white.  
*   WebSocket opcodes are light-yellow.  
*   Errors are light-red.  -->

### <span data-ttu-id="0bb0b-316">応答本文のプレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-316">View a preview of a response body</span></span>   

<span data-ttu-id="0bb0b-317">応答本文のプレビューを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-317">To view a preview of a response body:</span></span>  

1.  <span data-ttu-id="0bb0b-318">要求の URL を要求テーブルの [**名前**] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-318">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0bb0b-319">[**プレビュー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-319">Select the **Preview** tab.</span></span>  

<span data-ttu-id="0bb0b-320">このタブはほとんどの場合、画像を表示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-320">This tab is mostly useful for viewing images.</span></span>  

> ##### <span data-ttu-id="0bb0b-321">図19</span><span class="sxs-lookup"><span data-stu-id="0bb0b-321">Figure 19</span></span>  
> <span data-ttu-id="0bb0b-322">[プレビュー] タブ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-322">The Preview tab</span></span>  
> <span data-ttu-id="0bb0b-323">![プレビュー] タブ[ImagePreview]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-323">![The Preview tab][ImagePreview]</span></span>  

### <span data-ttu-id="0bb0b-324">応答本文を表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-324">View a response body</span></span>   

<span data-ttu-id="0bb0b-325">要求に対する応答の本文を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-325">To view the response body to a request:</span></span>  

1.  <span data-ttu-id="0bb0b-326">要求の URL を要求テーブルの [**名前**] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-326">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0bb0b-327">[**応答**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-327">Select the **Response** tab.</span></span>  

> ##### <span data-ttu-id="0bb0b-328">図20</span><span class="sxs-lookup"><span data-stu-id="0bb0b-328">Figure 20</span></span>  
> <span data-ttu-id="0bb0b-329">[応答] タブ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-329">The Response tab</span></span>  
> <span data-ttu-id="0bb0b-330">![返信] タブ[ImageResponse]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-330">![The Response tab][ImageResponse]</span></span>  

### <span data-ttu-id="0bb0b-331">HTTP ヘッダーの表示</span><span class="sxs-lookup"><span data-stu-id="0bb0b-331">View HTTP headers</span></span>   

<span data-ttu-id="0bb0b-332">要求に関する HTTP ヘッダーデータを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-332">To view HTTP header data about a request:</span></span>  

1.  <span data-ttu-id="0bb0b-333">要求の URL を要求テーブルの [**名前**] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-333">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0bb0b-334">[**ヘッダー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-334">Select the **Headers** tab.</span></span>  

> ##### <span data-ttu-id="0bb0b-335">図21</span><span class="sxs-lookup"><span data-stu-id="0bb0b-335">Figure 21</span></span>  
> <span data-ttu-id="0bb0b-336">[ヘッダー] タブ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-336">The Headers tab</span></span>  
> <span data-ttu-id="0bb0b-337">![ヘッダー] タブ[ImageHeaders]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-337">![The Headers tab][ImageHeaders]</span></span>  

#### <span data-ttu-id="0bb0b-338">HTTP ヘッダーソースの表示</span><span class="sxs-lookup"><span data-stu-id="0bb0b-338">View HTTP header source</span></span>   

<span data-ttu-id="0bb0b-339">既定では、[ヘッダー] タブにはヘッダーの名前がアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-339">By default, the Headers tab shows header names alphabetically.</span></span>  <span data-ttu-id="0bb0b-340">HTTP ヘッダーの名前を受け取った順序で表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-340">To view the HTTP header names in the order they were received:</span></span>  

1.  <span data-ttu-id="0bb0b-341">興味のある要求の [**ヘッダー** ] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-341">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="0bb0b-342">「 [HTTP ヘッダーの表示](#view-http-headers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-342">See [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="0bb0b-343">[**要求ヘッダー** ] または [**応答ヘッダー** ] セクションの横にある [**ソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-343">Select **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <span data-ttu-id="0bb0b-344">クエリ文字列パラメーターの表示</span><span class="sxs-lookup"><span data-stu-id="0bb0b-344">View query string parameters</span></span>   

<span data-ttu-id="0bb0b-345">わかりやすい形式で URL のクエリ文字列パラメーターを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-345">To view the query string parameters of a URL in a human-readable format:</span></span>  

1.  <span data-ttu-id="0bb0b-346">興味のある要求の [**ヘッダー** ] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-346">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="0bb0b-347">「 [HTTP ヘッダーの表示](#view-http-headers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-347">See [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="0bb0b-348">[**クエリ文字列パラメーター** ] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-348">Go to the **Query String Parameters** section.</span></span>  

> ##### <span data-ttu-id="0bb0b-349">図22</span><span class="sxs-lookup"><span data-stu-id="0bb0b-349">Figure 22</span></span>  
> <span data-ttu-id="0bb0b-350">[クエリ文字列パラメーター] セクション</span><span class="sxs-lookup"><span data-stu-id="0bb0b-350">The Query String Parameters section</span></span>  
> <span data-ttu-id="0bb0b-351">![クエリ文字列パラメーター] セクション[ImageQueryStringParameters]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-351">![The Query String Parameters section][ImageQueryStringParameters]</span></span>  

#### <span data-ttu-id="0bb0b-352">クエリ文字列パラメーターソースの表示</span><span class="sxs-lookup"><span data-stu-id="0bb0b-352">View query string parameters source</span></span>   

<span data-ttu-id="0bb0b-353">要求のクエリ文字列のパラメーターソースを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-353">To view the query string parameter source of a request:</span></span>  

1.  <span data-ttu-id="0bb0b-354">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-354">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="0bb0b-355">「[クエリ文字列パラメーターの表示](#view-query-string-parameters)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-355">See [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="0bb0b-356">[**ソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-356">Select **view source**.</span></span>  

#### <span data-ttu-id="0bb0b-357">URL 形式でエンコードされたクエリ文字列パラメーターの表示</span><span class="sxs-lookup"><span data-stu-id="0bb0b-357">View URL-encoded query string parameters</span></span>   

<span data-ttu-id="0bb0b-358">わかりやすい形式でクエリ文字列パラメーターを表示するには、次のようにエンコードを保持します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-358">To view query string parameters in a human-readable format, but with encodings preserved:</span></span>  

1.  <span data-ttu-id="0bb0b-359">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-359">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="0bb0b-360">「[クエリ文字列パラメーターの表示](#view-query-string-parameters)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-360">See [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="0bb0b-361">[**表示 URL をエンコード**した] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-361">Select **view URL encoded**.</span></span>  

### <span data-ttu-id="0bb0b-362">Cookie の表示</span><span class="sxs-lookup"><span data-stu-id="0bb0b-362">View cookies</span></span>   

<span data-ttu-id="0bb0b-363">要求の HTTP ヘッダーで送信された cookie を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-363">To view the cookies sent in the HTTP header of a request:</span></span>  

1.  <span data-ttu-id="0bb0b-364">要求の URL を要求テーブルの [**名前**] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-364">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0bb0b-365">[ **Cookies** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-365">Select the **Cookies** tab.</span></span>  

<!--See [Fields][ManageDataCookiesFields] for a description of each of the columns.  -->

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->
<!--TODO: add link when section is available -->

> ##### <span data-ttu-id="0bb0b-366">図23</span><span class="sxs-lookup"><span data-stu-id="0bb0b-366">Figure 23</span></span>  
> <span data-ttu-id="0bb0b-367">[Cookie] タブ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-367">The Cookies tab</span></span>  
> <span data-ttu-id="0bb0b-368">![Cookies] タブ[ImageCookies]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-368">![The Cookies tab][ImageCookies]</span></span>  

### <span data-ttu-id="0bb0b-369">要求のタイミングのブレークダウンを表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-369">View the timing breakdown of a request</span></span>   

<span data-ttu-id="0bb0b-370">要求のタイミングの詳細を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-370">To view the timing breakdown of a request:</span></span>  

1.  <span data-ttu-id="0bb0b-371">要求の URL を要求テーブルの [**名前**] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-371">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0bb0b-372">[**タイミング**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-372">Select the **Timing** tab.</span></span>  

<span data-ttu-id="0bb0b-373">このデータにすばやくアクセスする方法については、「[タイミングのブレークダウンをプレビュー](#preview-a-timing-breakdown)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-373">See [Preview a timing breakdown](#preview-a-timing-breakdown) for a faster way to access this data.</span></span>  

<span data-ttu-id="0bb0b-374">「タイミング」タブに表示される各フェーズについて詳しくは、「[タイミングのブレークダウン](#timing-breakdown-phases-explained)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-374">See [Timing breakdown phases explained](#timing-breakdown-phases-explained) for more information about each of the phases that you may see in the Timing tab.</span></span>  

> ##### <span data-ttu-id="0bb0b-375">図24</span><span class="sxs-lookup"><span data-stu-id="0bb0b-375">Figure 24</span></span>  
> <span data-ttu-id="0bb0b-376">[タイミング] タブ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-376">The Timing tab</span></span>  
> <span data-ttu-id="0bb0b-377">![タイミング] タブ[ImageTiming]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-377">![The Timing tab][ImageTiming]</span></span>  

<span data-ttu-id="0bb0b-378">各フェーズに関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-378">More information about each of the phases.</span></span>  

<span data-ttu-id="0bb0b-379">このビューにアクセスする別の方法については、「[タイミングの内訳を表示](#view-the-timing-breakdown-of-a-request)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-379">See [View timing breakdown](#view-the-timing-breakdown-of-a-request) for another way to access this view.</span></span>  

#### <span data-ttu-id="0bb0b-380">タイミングの内訳をプレビューする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-380">Preview a timing breakdown</span></span>   

<span data-ttu-id="0bb0b-381">要求のタイミングの内訳のプレビューを表示するには、要求テーブルの [**ウォーターフォール**] 列で要求のエントリにマウスポインターを合わせます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-381">To view a preview of the timing breakdown of a request, hover over the entry for the request in the **Waterfall** column of the Requests table.</span></span>  

<span data-ttu-id="0bb0b-382">詳しくは[、「ホバーを必要](#view-the-timing-breakdown-of-a-request)としないデータにアクセスする方法」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-382">See [View the timing breakdown of a request](#view-the-timing-breakdown-of-a-request) for a way to access this data that does not require hovering.</span></span>  

> ##### <span data-ttu-id="0bb0b-383">図25</span><span class="sxs-lookup"><span data-stu-id="0bb0b-383">Figure 25</span></span>  
> <span data-ttu-id="0bb0b-384">要求のタイミングのブレークダウンのプレビュー</span><span class="sxs-lookup"><span data-stu-id="0bb0b-384">Previewing the timing breakdown of a request</span></span>  
> <span data-ttu-id="0bb0b-385">![要求のタイミングの詳細をプレビューしています][ImageWaterfallHover]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-385">![Previewing the timing breakdown of a request][ImageWaterfallHover]</span></span>  

#### <span data-ttu-id="0bb0b-386">タイミングのブレークフェーズについて</span><span class="sxs-lookup"><span data-stu-id="0bb0b-386">Timing breakdown phases explained</span></span>   

<span data-ttu-id="0bb0b-387">[タイミング] タブに表示される各フェーズについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-387">More information about each of the phases you may see in the Timing tab:</span></span>  

*   <span data-ttu-id="0bb0b-388">**キューイング**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-388">**Queueing**.</span></span>  <span data-ttu-id="0bb0b-389">ブラウザーは、次の場合に要求をキューに表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-389">The browser queues requests when:</span></span>  
    *   <span data-ttu-id="0bb0b-390">優先度の高い要求もあります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-390">There are higher priority requests.</span></span>  
    *   <span data-ttu-id="0bb0b-391">この起点で既に6つの TCP 接続が開かれています。これは制限です。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-391">There are already six TCP connections open for this origin, which is the limit.</span></span>  <span data-ttu-id="0bb0b-392">HTTP/1.0 および HTTP/1.1 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-392">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
    *   <span data-ttu-id="0bb0b-393">ブラウザーは、ディスクキャッシュの領域を一時的に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-393">The browser is briefly allocating space in the disk cache.</span></span>  
*   <span data-ttu-id="0bb0b-394">**失速**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-394">**Stalled**.</span></span>  <span data-ttu-id="0bb0b-395">**キュー**に記載されている理由のいずれかで、要求が停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-395">The request could be stalled for any of the reasons described in **Queueing**.</span></span>  
*   <span data-ttu-id="0bb0b-396">**DNS 検索**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-396">**DNS Lookup**.</span></span>  <span data-ttu-id="0bb0b-397">ブラウザーが要求の IP アドレスを解決しています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-397">The browser is resolving the IP address for the request.</span></span>  
*   <span data-ttu-id="0bb0b-398">**プロキシネゴシエーション**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-398">**Proxy negotiation**.</span></span>  <span data-ttu-id="0bb0b-399">ブラウザーは、要求を[プロキシサーバー][WikiProxyServer]とネゴシエートしています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-399">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
*   <span data-ttu-id="0bb0b-400">**リクエストを送信**しました。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-400">**Request sent**.</span></span>  <span data-ttu-id="0bb0b-401">要求が送信されています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-401">The request is being sent.</span></span>  
*   <span data-ttu-id="0bb0b-402">**Serviceworker の準備**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-402">**ServiceWorker Preparation**.</span></span>  <span data-ttu-id="0bb0b-403">ブラウザーがサービスワーカーを開始しています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-403">The browser is starting up the service worker.</span></span>  
*   <span data-ttu-id="0bb0b-404">**ServiceWorker へのリクエスト**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-404">**Request to ServiceWorker**.</span></span>  <span data-ttu-id="0bb0b-405">要求がサービスワーカーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-405">The request is being sent to the service worker.</span></span>  
*   <span data-ttu-id="0bb0b-406">**\ (TTFB \) を待機**しています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-406">**Waiting \(TTFB\)**.</span></span>  <span data-ttu-id="0bb0b-407">ブラウザーは、応答の最初のバイトを待機しています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-407">The browser is waiting for the first byte of a response.</span></span>  
  <span data-ttu-id="0bb0b-408">TTFB は、最初のバイトまでの時間を表します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-408">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="0bb0b-409">このタイミングには、待機時間が1往復、サーバーが応答の準備にかかった時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-409">This timing includes 1 round trip of latency and the time the server took to prepare the response.</span></span>  
*   <span data-ttu-id="0bb0b-410">**コンテンツのダウンロード**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-410">**Content Download**.</span></span>  <span data-ttu-id="0bb0b-411">ブラウザーが応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-411">The browser is receiving the response.</span></span>  
*   <span data-ttu-id="0bb0b-412">**プッシュ配信**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-412">**Receiving Push**.</span></span>  <span data-ttu-id="0bb0b-413">ブラウザーが、HTTP/2 Server プッシュ経由でこの応答のデータを受信しています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-413">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
*   <span data-ttu-id="0bb0b-414">**プッシュ中**。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-414">**Reading Push**.</span></span>  <span data-ttu-id="0bb0b-415">ブラウザーは、前に受信したローカルデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-415">The browser is reading the local data previously received.</span></span>  

### <span data-ttu-id="0bb0b-416">イニシエーターと依存関係を表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-416">View initiators and dependencies</span></span>   

<span data-ttu-id="0bb0b-417">要求のイニシエーターと依存関係を表示するには、[ `Shift` 要求] テーブルの要求をポイントしたままにします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-417">To view the initiators and dependencies of a request, hold `Shift`and hover over the request in the Requests table.</span></span>  <span data-ttu-id="0bb0b-418">DevTools の色: イニシエーターは緑で表示され、依存関係は赤で示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-418">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

> ##### <span data-ttu-id="0bb0b-419">図26</span><span class="sxs-lookup"><span data-stu-id="0bb0b-419">Figure 26</span></span>  
> <span data-ttu-id="0bb0b-420">要求のイニシエーターと依存関係の表示</span><span class="sxs-lookup"><span data-stu-id="0bb0b-420">Viewing the initiators and dependencies of a request</span></span>  
> <span data-ttu-id="0bb0b-421">![要求のイニシエーターと依存関係の表示][ImageRequestInitiatorsDependencies]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-421">![Viewing the initiators and dependencies of a request][ImageRequestInitiatorsDependencies]</span></span>  

<span data-ttu-id="0bb0b-422">要求テーブルが時系列順に並べ替えられている場合、ポイントしている1つ上の緑の要求が依存関係のイニシエーターになります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-422">When the Requests table is ordered chronologically, the first green request above the one you are hovering is the initiator of the dependency.</span></span>  <span data-ttu-id="0bb0b-423">別の緑の要求がその上に表示されている場合は、その上位の要求がイニシエーターのイニシエーターになります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-423">If another green request appears above that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="0bb0b-424">などなど。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-424">And so on.</span></span>  

### <span data-ttu-id="0bb0b-425">読み込みイベントを表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-425">View load events</span></span>   

<span data-ttu-id="0bb0b-426">DevTools は、 `DOMContentLoaded` [ `load` ネットワーク] パネル上の複数の場所にある [イベントのタイミング] を表示します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-426">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the Network panel.</span></span>  <span data-ttu-id="0bb0b-427">`DOMContentLoaded`イベントは青色で色分けされ、 `load` イベントは赤になります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-427">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

> ##### <span data-ttu-id="0bb0b-428">図27</span><span class="sxs-lookup"><span data-stu-id="0bb0b-428">Figure 27</span></span>  
> <span data-ttu-id="0bb0b-429">[ `DOMContentLoaded` `load` ネットワーク] パネルでのイベントとイベントの場所</span><span class="sxs-lookup"><span data-stu-id="0bb0b-429">The locations of the `DOMContentLoaded` and `load` events on the Network panel</span></span>  
> <span data-ttu-id="0bb0b-430">![ネットワークパネルでの DOMContentLoaded および load イベントの場所][ImageNetworkPanelDOMContentLoadedLoadEvents]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-430">![The locations of the DOMContentLoaded and load events on the Network panel][ImageNetworkPanelDOMContentLoadedLoadEvents]</span></span>  

### <span data-ttu-id="0bb0b-431">要求の合計数を表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-431">View the total number of requests</span></span>   

<span data-ttu-id="0bb0b-432">[ネットワーク] パネルの下部にある [概要] ウィンドウに、要求の合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-432">The total number of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="0bb0b-433">この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-433">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="0bb0b-434">DevTools が開かれる前に他の要求が発生した場合、これらの要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-434">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

> ##### <span data-ttu-id="0bb0b-435">図28</span><span class="sxs-lookup"><span data-stu-id="0bb0b-435">Figure 28</span></span>  
> <span data-ttu-id="0bb0b-436">DevTools が開かれてからの要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-436">The total number of requests since DevTools was opened</span></span>  
> <span data-ttu-id="0bb0b-437">![DevTools が開かれたための要求の合計数][ImageTotalRequests]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-437">![The total number of requests since DevTools was opened][ImageTotalRequests]</span></span>  

### <span data-ttu-id="0bb0b-438">ダウンロードの合計サイズを表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-438">View the total download size</span></span>   

<span data-ttu-id="0bb0b-439">要求の合計ダウンロードサイズが、[ネットワーク] パネルの下部にある [概要] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-439">The total download size of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="0bb0b-440">この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-440">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="0bb0b-441">DevTools が開かれる前に他の要求が発生した場合、これらの要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-441">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

> ##### <span data-ttu-id="0bb0b-442">図29</span><span class="sxs-lookup"><span data-stu-id="0bb0b-442">Figure 29</span></span>  
> <span data-ttu-id="0bb0b-443">リクエストのダウンロード合計サイズ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-443">The total download size of requests</span></span>  
> <span data-ttu-id="0bb0b-444">![リクエストのダウンロード合計サイズ][ImageTotalSize]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-444">![The total download size of requests][ImageTotalSize]</span></span>  

<span data-ttu-id="0bb0b-445">各項目を圧縮した後の大きなリソースについては[、「リソースの未圧縮サイズを表示](#view-the-uncompressed-size-of-a-resource)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-445">See [View the uncompressed size of a resource](#view-the-uncompressed-size-of-a-resource) to see how large resources are after the browser uncompresses each item.</span></span>  

### <span data-ttu-id="0bb0b-446">要求の原因となったスタックトレースを表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-446">View the stack trace that caused a request</span></span>   

<span data-ttu-id="0bb0b-447">JavaScript ステートメントでリソースを要求した後、[**イニシエーター** ] 列をマウスでポイントすると、要求までのスタックトレースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-447">After a JavaScript statement requests a resource, hover over the **Initiator** column to view the stack trace leading up to the request.</span></span>  

<!-- [codepen.io/contoso/pen/yLBrOWa?editors=0010#0](https://codepen.io/contoso/pen/yLBrOWa?editors=0010#0) -->  

<!--
```javascript
function init() {
  getData();
}

function getData() {
  fetch('https:/httpbin.org/get?message=hi');
}

init();
```  
-->  

> ##### <span data-ttu-id="0bb0b-448">図30</span><span class="sxs-lookup"><span data-stu-id="0bb0b-448">Figure 30</span></span>  
> <span data-ttu-id="0bb0b-449">リソース要求までのスタックトレース</span><span class="sxs-lookup"><span data-stu-id="0bb0b-449">The stack trace leading up to a resource request</span></span>  
> <span data-ttu-id="0bb0b-450">!(リソース要求につながるスタックトレース)[ImageInitiatorStack]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-450">![The stack trace leading up to a resource request][ImageInitiatorStack]</span></span>  

### <span data-ttu-id="0bb0b-451">リソースの未圧縮サイズを表示する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-451">View the uncompressed size of a resource</span></span>   

<span data-ttu-id="0bb0b-452">[**大きな要求行を使用する**] チェックボックスをオンにして、[**サイズ**] 列の下の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-452">Select the **Use large request rows** checkbox and then look at the bottom value of the **Size** column.</span></span>  

> ##### <span data-ttu-id="0bb0b-453">図31</span><span class="sxs-lookup"><span data-stu-id="0bb0b-453">Figure 31</span></span>  
> <span data-ttu-id="0bb0b-454">圧縮されていないリソースの例 \ (ネットワーク経由で送信されたファイルの圧縮サイズ、圧縮されてい `jquery-3.3.1.min.js` ない `29.9 KB` サイズなど `84.9 KB` )</span><span class="sxs-lookup"><span data-stu-id="0bb0b-454">An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
> <span data-ttu-id="0bb0b-455">![圧縮されていないリソースの例][ImageUncompressedResources]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-455">![An example of uncompressed resources][ImageUncompressedResources]</span></span>  

## <span data-ttu-id="0bb0b-456">要求データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-456">Export requests data</span></span>   

### <span data-ttu-id="0bb0b-457">すべてのネットワーク要求を HAR ファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-457">Save all network requests to a HAR file</span></span>   

<span data-ttu-id="0bb0b-458">すべてのネットワーク要求を HAR ファイルに保存するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-458">To save all network requests to a HAR file:</span></span>  

1.  <span data-ttu-id="0bb0b-459">要求テーブルで任意の要求を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-459">Right-click any request in the Requests table.</span></span>  
1.  <span data-ttu-id="0bb0b-460">[**コンテンツを含む HAR として保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-460">Select **Save as HAR with Content**.</span></span>  <span data-ttu-id="0bb0b-461">DevTools は、HAR ファイルに対して DevTools を開いた後に発生した要求をすべて保存します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-461">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="0bb0b-462">要求をフィルター処理したり、1つの要求のみを保存したりする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-462">There is no way to filter requests, or to save just a single request.</span></span>  

<span data-ttu-id="0bb0b-463">HAR ファイルを保存すると、そのファイルを分析用の DevTools にインポートして戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-463">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="0bb0b-464">HAR ファイルを [要求] テーブルにドラッグアンドドロップするだけです。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-464">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--See also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

> ##### <span data-ttu-id="0bb0b-465">図32</span><span class="sxs-lookup"><span data-stu-id="0bb0b-465">Figure 32</span></span>  
> <span data-ttu-id="0bb0b-466">[コンテンツを含む HAR として保存] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="0bb0b-466">Selecting Save as HAR with Content</span></span>  
> <span data-ttu-id="0bb0b-467">![コンテンツを含む HAR として保存] を選びます。[ImageSaveAsHAR]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-467">![Selecting Save as HAR with Content][ImageSaveAsHAR]</span></span>  

### <span data-ttu-id="0bb0b-468">1つ以上の要求をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-468">Copy one or more requests to the clipboard</span></span>   

<span data-ttu-id="0bb0b-469">要求テーブルの [**名前**] 列で、要求を右クリックし、[**コピー**] をポイントして、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-469">Under the **Name** column of the Requests table, right-click a request, hover over **Copy**, and select one of the following options:</span></span>  

*   <span data-ttu-id="0bb0b-470">**リンクアドレスをコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-470">**Copy Link Address**.</span></span>  <span data-ttu-id="0bb0b-471">要求の URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-471">Copy the URL of the request to the clipboard.</span></span>  
*   <span data-ttu-id="0bb0b-472">**回答をコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-472">**Copy Response**.</span></span>  <span data-ttu-id="0bb0b-473">応答本文をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-473">Copy the response body to the clipboard.</span></span>  
*   <span data-ttu-id="0bb0b-474">**取り出しとしてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-474">**Copy as Fetch**.</span></span>  
*   <span data-ttu-id="0bb0b-475">**CURL としてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-475">**Copy as cURL**.</span></span>  <span data-ttu-id="0bb0b-476">CURL コマンドとして要求をコピーします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-476">Copy the request as a cURL command.</span></span>  
*   <span data-ttu-id="0bb0b-477">**すべてを Fetch としてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-477">**Copy All as Fetch**.</span></span>  
*   <span data-ttu-id="0bb0b-478">**CURL としてすべてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-478">**Copy All as cURL**.</span></span>  <span data-ttu-id="0bb0b-479">すべての要求を cURL コマンドのチェーンとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-479">Copy all requests as a chain of cURL commands.</span></span>  
*   <span data-ttu-id="0bb0b-480">**すべてを HAR としてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-480">**Copy All as HAR**.</span></span>  <span data-ttu-id="0bb0b-481">すべての要求を HAR データとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-481">Copy all requests as HAR data.</span></span>  

> ##### <span data-ttu-id="0bb0b-482">図33</span><span class="sxs-lookup"><span data-stu-id="0bb0b-482">Figure 33</span></span>  
> <span data-ttu-id="0bb0b-483">[返信のコピー] の選択</span><span class="sxs-lookup"><span data-stu-id="0bb0b-483">Selecting Copy Response</span></span>  
> <span data-ttu-id="0bb0b-484">![回答のコピーの選択][ImageCopyResponse]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-484">![Selecting Copy Response][ImageCopyResponse]</span></span>  

## <span data-ttu-id="0bb0b-485">[ネットワーク] パネルのレイアウトを変更する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-485">Change the layout of the Network panel</span></span>  

<span data-ttu-id="0bb0b-486">ネットワークパネル UI のセクションを展開したり折りたたんだりして、重要な情報を強調することができます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-486">You may expand or collapse sections of the Network panel UI to focus important information.</span></span>  

### <span data-ttu-id="0bb0b-487">[フィルター] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-487">Hide the Filters pane</span></span>   

<span data-ttu-id="0bb0b-488">既定では、DevTools によって [**フィルター] ウィンドウ**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-488">By default, DevTools shows the **Filters pane**.</span></span>  
<span data-ttu-id="0bb0b-489">[フィルターフィルター] を**選択し** ![ ][ImageFilterIcon] て非表示にします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-489">Select **Filter** ![Filter][ImageFilterIcon]  to hide it.</span></span>  

> ##### <span data-ttu-id="0bb0b-490">図34</span><span class="sxs-lookup"><span data-stu-id="0bb0b-490">Figure 34</span></span>  
> <span data-ttu-id="0bb0b-491">[フィルターの非表示] ボタン</span><span class="sxs-lookup"><span data-stu-id="0bb0b-491">The Hide Filters button</span></span>  
> <span data-ttu-id="0bb0b-492">![フィルターの非表示] ボタン[Imagehideフィルタ] ボタン</span><span class="sxs-lookup"><span data-stu-id="0bb0b-492">![The Hide Filters button][ImageHideFiltersButton]</span></span>  

### <span data-ttu-id="0bb0b-493">大きな要求行を使用する</span><span class="sxs-lookup"><span data-stu-id="0bb0b-493">Use large request rows</span></span>   

<span data-ttu-id="0bb0b-494">ネットワーク要求テーブルにより多くの空白が必要な場合は、大きな行を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-494">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="0bb0b-495">列によっては、大きな行を使用するときに、さらに多くの情報が表示される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-495">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="0bb0b-496">たとえば、 **Size**列の下の値は、要求の非圧縮サイズです。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-496">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

> ##### <span data-ttu-id="0bb0b-497">図35</span><span class="sxs-lookup"><span data-stu-id="0bb0b-497">Figure 35</span></span>  
> <span data-ttu-id="0bb0b-498">要求ウィンドウの大きな要求行の例</span><span class="sxs-lookup"><span data-stu-id="0bb0b-498">An example of large request rows in the Requests pane</span></span>  
> <span data-ttu-id="0bb0b-499">![要求] ウィンドウの大きな要求行の例[ImageLargeRequestRows]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-499">![An example of large request rows in the Requests pane][ImageLargeRequestRows]</span></span>  

<span data-ttu-id="0bb0b-500">大きな行を有効にするには、[**大きな要求行を使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-500">Select the **Use large request rows** checkbox to enable large rows.</span></span>  

> ##### <span data-ttu-id="0bb0b-501">図36</span><span class="sxs-lookup"><span data-stu-id="0bb0b-501">Figure 36</span></span>  
> <span data-ttu-id="0bb0b-502">大きい要求行のチェックボックス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-502">The Large Request Rows checkbox</span></span>  
> <span data-ttu-id="0bb0b-503">![大きな要求行数] チェックボックス[ImageLargeRequestRowsCheckbox]</span><span class="sxs-lookup"><span data-stu-id="0bb0b-503">![The Large Request Rows checkbox][ImageLargeRequestRowsCheckbox]</span></span>  

### <span data-ttu-id="0bb0b-504">[概要] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="0bb0b-504">Hide the Overview pane</span></span>   

<span data-ttu-id="0bb0b-505">既定では、DevTools によって [**概要] ウィンドウ**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-505">By default, DevTools shows the **Overview pane**.</span></span>  
<span data-ttu-id="0bb0b-506">[**概要の表示**] チェックボックスをオフにして非表示にします。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-506">Deselect the **Show Overview** checkbox to hide it.</span></span>  

> ##### <span data-ttu-id="0bb0b-507">図37</span><span class="sxs-lookup"><span data-stu-id="0bb0b-507">Figure 37</span></span>  
> <span data-ttu-id="0bb0b-508">[概要の表示] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-508">The Show Overview checkbox</span></span>  
> <span data-ttu-id="0bb0b-509">![概要の表示] チェックボックス[Imagehide概要] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-509">![The Show Overview checkbox][ImageHideOverviewCheckbox]</span></span>  

<!-->   -->  

  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-requests-icon.msft.png  
[ImageFilterIcon]: /microsoft-edge/devtools-guide-chromium/media/filter-icon.msft.png  
[ImageHideIcon]: /microsoft-edge/devtools-guide-chromium/media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: /microsoft-edge/devtools-guide-chromium/media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: /microsoft-edge/devtools-guide-chromium/media/record-on-icon.msft.png  

[ImageNetworkPanel]: /microsoft-edge/devtools-guide-chromium/media/network-network-panel.msft.png "図 1: [ネットワーク] パネル"  
[ImageClearButton]: /microsoft-edge/devtools-guide-chromium/media/network-network-clear-button.msft.png "図 2: [クリア] ボタン"  
[ImagePreserveLogCheckBox]: /microsoft-edge/devtools-guide-chromium/media/network-network-preserve-log.msft.png "図 3: [ログの保存] チェックボックス"  
[ImageScreenshotHover]: /microsoft-edge/devtools-guide-chromium/media/network-network-screenshot-hover.msft.png "図 4: スクリーンショット上のマウスポインター"  
<!--[ImageReplayXHR]: /microsoft-edge/devtools-guide-chromium/media/network-replay-xhr.msft.png "Old Figure 5: Selecting Replay XHR"  -->  
[ImageDisableCacheCheckBox]:/microsoft-edge/devtools-guide-chromium/media/network-network-disable-cache-checkbox.msft.png "図 5: キャッシュを無効にする] チェックボックス  
[ImageClearBrowserCache]:/microsoft-edge/devtools-guide-chromium/media/network-network-clear-browser-cache.msft.png "図 6: ブラウザーキャッシュのクリア" を選択する  
[ImageOfflineDropdown]:/microsoft-edge/devtools-guide-chromium/media/network-network-offline-dropdown.msft.png "図 7: オフラインドロップダウンメニュー  
[ImageNetworkThrottlingMenu]:/microsoft-edge/devtools-guide-chromium/media/network-network-throttling-menu.msft.png "図 8: ネットワーク調整メニュー"  
[ImageClearBrowserCookies]:/microsoft-edge/devtools-guide-chromium/media/network-network-clear-browser-cookies.msft.png "図 9: [ブラウザー Cookie のクリア] の選択  
[ImageFilterTextBox]:/microsoft-edge/devtools-guide-chromium/media/network-network-filters-textbox.msft.png "図 10: フィルターのテキストボックス"  
[ImageMultiTypeFilter]:/microsoft-edge/devtools-guide-chromium/media/network-network-type-filters.msft.png "図 11: 型フィルターを使用して JS、CSS、およびドキュメントのリソースを表示する  
[Image概要フィルター]:/microsoft-edge/devtools-guide-chromium/media/network-network-overview-filter.msft.png "図 12: 300ms で非アクティブな要求をすべてフィルターで除外する"
[ImageOverviewFilter]: /microsoft-edge/devtools-guide-chromium/media/network-network-overview-filter.msft.png "Figure 12: Filtering out any requests that were inactive around 300ms"  
[ImageHideDataURLsCheckBox]:/microsoft-edge/devtools-guide-chromium/media/network-network-hide-data-urls.msft.png "図 13: [データ Url を非表示にする] チェックボックス  
[ImageWaterfallTotalDuration]:/microsoft-edge/devtools-guide-chromium/media/network-network-waterfall-total-duration.msft.png "図 14: ウォーターフォール (全体の期間) の並べ替え"  
[ImageRequestsTable]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-table.msft.png "図 15: 要求テーブル"  
[ImageRequestsTableAddColumn]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-add-column.msft.png "図 16: 要求テーブルに列を追加する"  
[ImageRequestsTableCustomColumn]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-add-custom.msft.png "図 17: 要求テーブルにカスタム列を追加する"  
[ImageRequestsTableWaterfallColumn]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-waterfall.msft.png "図 18: [要求] ウィンドウの [ウォーターフォール] 列  
[ImagePreview]:/microsoft-edge/devtools-guide-chromium/media/network-network-resources-preview.msft.png "図 19: [プレビュー] タブ」  
<!--[ImageFrames]: /microsoft-edge/devtools-guide-chromium/media/network-frames.msft.png "Old Figure 20: The Frames tab"  -->  
[ImageResponse]:/microsoft-edge/devtools-guide-chromium/media/network-network-resources-response.msft.png "図 20: [応答] タブ  
[ImageHeaders]:/microsoft-edge/devtools-guide-chromium/media/network-resources-headers.msft.png "図 21: [ヘッダー] タブ  
[ImageQueryStringParameters]:/microsoft-edge/devtools-guide-chromium/media/network-network-resources-headers-query-string-parameters.msft.png "図 22: クエリ文字列パラメーターセクション"  
[ImageCookies]:/microsoft-edge/devtools-guide-chromium/media/network-network-resources-cookies.msft.png "図 23: [Cookie] タブ  
[ImageTiming]:/microsoft-edge/devtools-guide-chromium/media/network-network-resources-timing.msft.png "図 24: [タイミング] タブ」  
[ImageWaterfallHover]:/microsoft-edge/devtools-guide-chromium/media/network-network-resources-waterfall-hover.msft.png "図 25: 要求のタイミングの詳細をプレビューしています"  
[ImageRequestInitiatorsDependencies]:/microsoft-edge/devtools-guide-chromium/media/network-network-resources-initiators-dependencies.msft.png "図 26: 要求のイニシエーターと依存関係を表示する"  
[ImageNetworkPanelDOMContentLoadedLoadEvents]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-load-events.msft.png "図 27: ネットワークパネル上の DOMContentLoaded イベントと load イベント  
[ImageTotalRequests]:/microsoft-edge/devtools-guide-chromium/media/network-network-total-requests.msft.png "Figure 28: DevTools が開かれたための要求の合計数"  
[ImageTotalSize]:/microsoft-edge/devtools-guide-chromium/media/network-network-total-download-size.msft.png "Figure 29: 要求の合計ダウンロードサイズ"  
[ImageInitiatorStack]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-initiator-stack.msft.png "図 30: リソース要求までのスタックトレース  
[ImageUncompressedResources]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-uncompressed-compare.msft.png "図 31: 圧縮されていないリソースの例"  
[ImageSaveAsHAR]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-save-har-content.msft.png "図 32: [コンテンツを含む HAR として保存] を選択します。  
[ImageCopyResponse]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-copy-response.msft.png "図 33: 返信のコピーの選択"  
[Imagehidefilter Button]:/microsoft-edge/devtools-guide-chromium/media/network-network-resources-hide-filters-button.msft.png "図 34: [フィルターの非表示] ボタン
[ImageHideFiltersButton]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-hide-filters-button.msft.png "Figure 34: The Hide Filters button"  
[ImageLargeRequestRows]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-large-request-rows.msft.png "図 35: 要求ウィンドウの大きな要求行の例"  
[ImageLargeRequestRowsCheckbox]:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-use-large-request-rows-on.msft.png "図 36: 大きな要求行のチェックボックス  
<span data-ttu-id="0bb0b-546">[Imagehide概要] チェックボックス:/microsoft-edge/devtools-guide-chromium/media/network-network-requests-show-overview-off.msft.png "図 37: [概要を非表示にする] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0bb0b-546">[ImageHideOverviewCheckbox]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-show-overview-off.msft.png "Figure 37: The Hide Overview checkbox"</span></span>  

<!-- links -->  

[DevtoolsProgressiveWebApps]: /microsoft-edge/devtools-guide-chromium/network/progressive-web-apps "プログレッシブ Web アプリをデバッグする"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "データ Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "プロキシサーバー-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="0bb0b-550">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-550">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0bb0b-551">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/network/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-551">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0bb0b-553">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0bb0b-553">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
