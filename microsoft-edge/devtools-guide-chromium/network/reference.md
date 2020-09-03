---
description: Microsoft Edge DevTools のネットワークパネル機能の包括的な参照。
title: ネットワーク分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 38570e6d196314aa6315a34f0b8b1b0b0d740c91
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993619"
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

# <span data-ttu-id="0f952-104">ネットワーク分析のリファレンス</span><span class="sxs-lookup"><span data-stu-id="0f952-104">Network Analysis Reference</span></span>  

<span data-ttu-id="0f952-105">Microsoft Edge DevTools のネットワーク分析機能の包括的な参照でページがどのように読み込まれるかを分析するための新しい方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f952-105">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

<!--
> [!NOTE]
> This reference is based on Microsoft Edge 58.  If you use another version of Microsoft Edge, the UI, and features of DevTools may be different.  Check `edge://help` to see what version of Microsoft Edge you are running.  
-->

## <span data-ttu-id="0f952-106">ネットワーク要求を記録する</span><span class="sxs-lookup"><span data-stu-id="0f952-106">Record network requests</span></span>  

<span data-ttu-id="0f952-107">既定では、devtools はネットワークパネルのすべてのネットワーク要求を記録します。これは、DevTools が開いている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="0f952-107">By default, DevTools records all network requests in the Network panel, so long as DevTools is open.</span></span>  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-panel.msft.png":::
   <span data-ttu-id="0f952-109">図 1: [ **ネットワーク** ] パネル</span><span class="sxs-lookup"><span data-stu-id="0f952-109">Figure 1:  The **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-110">ネットワーク要求の記録を停止する</span><span class="sxs-lookup"><span data-stu-id="0f952-110">Stop recording network requests</span></span>  

<span data-ttu-id="0f952-111">要求の記録を停止するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f952-111">To stop recording requests, complete the following steps.</span></span>  

1.  <span data-ttu-id="0f952-112">[ **Stop recording network log** ![ ][ImageRecordOnIcon] **ネットワーク**] パネルで [ネットワークログの記録停止] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-112">Select **Stop recording network log** ![Stop recording network log][ImageRecordOnIcon] on the **Network** panel.</span></span>  <span data-ttu-id="0f952-113">灰色に変わり、DevTools が要求を記録しなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
1.  <span data-ttu-id="0f952-114">`Control` + `E` `Command` + `E` **ネットワーク**パネルがフォーカスされているときに、\ (Windows \) または \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="0f952-114">Press `Control`+`E` \(Windows\) or `Command`+`E` \(macOS\) while the **Network** panel is in focus.</span></span>  

### <span data-ttu-id="0f952-115">要求をクリアする</span><span class="sxs-lookup"><span data-stu-id="0f952-115">Clear requests</span></span>  

<span data-ttu-id="0f952-116">[ネットワーク] パネルの [ **クリア] を**選ん ![ ][ImageClearIcon] で、要求テーブルからのすべての要求をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0f952-116">Select **Clear** ![Clear][ImageClearIcon] on the Network panel to clear all requests from the Requests table.</span></span>  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="[クリア] ボタン" lightbox="../media/network-network-clear-button.msft.png":::
   <span data-ttu-id="0f952-118">図 2: [ **クリア** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="0f952-118">Figure 2:  The **Clear** button</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-119">ページのロード間で要求を保存する</span><span class="sxs-lookup"><span data-stu-id="0f952-119">Save requests across page loads</span></span>  

<span data-ttu-id="0f952-120">ページの読み込み時に要求を保存するには、[ネットワーク] パネルの [ **ログを保持** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0f952-120">To save requests across page loads, check the **Preserve log** checkbox on the Network panel.</span></span>  <span data-ttu-id="0f952-121">DevTools では、 **Preserve log**を無効にするまで、すべての要求が保存されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-121">DevTools saves all requests until you disable **Preserve log**.</span></span>  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="[ログの保存] チェックボックス" lightbox="../media/network-network-preserve-log.msft.png":::
   <span data-ttu-id="0f952-123">図 3: [ **ログの保存** ] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0f952-123">Figure 3:  The **Preserve Log** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-124">ページの読み込み中にスクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="0f952-124">Capture screenshots during page load</span></span>  

<span data-ttu-id="0f952-125">スクリーンショットをキャプチャして、ページの読み込みを待機しているユーザーに表示される内容を分析します。</span><span class="sxs-lookup"><span data-stu-id="0f952-125">Capture screenshots to analyze what users see as they wait for your page to load.</span></span>  

<span data-ttu-id="0f952-126">スクリーンショットを有効にするには、[**ネットワーク設定**] を選択し、[**ネットワーク**] パネルの [**スクリーンショットのキャプチャ**] チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-126">To enable screenshots, select **Network settings** and select **Capture screenshots** checkbox on the **Network** panel.</span></span>  

<span data-ttu-id="0f952-127">**ネットワーク**パネルがフォーカスされているときにページを更新して、スクリーンショットをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="0f952-127">Refresh the page while the **Network** panel is in focus to capture screenshots.</span></span>  

<span data-ttu-id="0f952-128">スクリーンショットをキャプチャした後、次のように操作します。</span><span class="sxs-lookup"><span data-stu-id="0f952-128">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="0f952-129">スクリーンショットにマウスポインターを置くと、そのスクリーンショットがキャプチャされた点が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-129">Hover over a screenshot to view the point at which that screenshot was captured.</span></span>  <span data-ttu-id="0f952-130">[ **概要** ] ウィンドウに黄色の線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-130">A yellow line appears on the **Overview** pane.</span></span>  
*   <span data-ttu-id="0f952-131">スクリーンショットがキャプチャされた後に発生した要求をすべて除外するには、画面のサムネイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-131">Select the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="0f952-132">サムネイルをダブルクリックして拡大します。</span><span class="sxs-lookup"><span data-stu-id="0f952-132">Double-click a thumbnail to zoom into it.</span></span>  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="スクリーンショット上のマウスポインター" lightbox="../media/network-network-screenshot-hover.msft.png":::
   <span data-ttu-id="0f952-134">図 4: スクリーンショット上のマウスポインター</span><span class="sxs-lookup"><span data-stu-id="0f952-134">Figure 4:  Hovering over a screenshot</span></span>  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and select **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Selecting Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Old Figure 5:  Selecting Replay XHR  
:::image-end:::  
-->  

## <span data-ttu-id="0f952-135">読み込み動作を変更する</span><span class="sxs-lookup"><span data-stu-id="0f952-135">Change loading behavior</span></span>  

### <span data-ttu-id="0f952-136">ブラウザーのキャッシュを無効にして、初めてのユーザーをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="0f952-136">Emulate a first-time visitor by disabling the browser cache</span></span>  

<span data-ttu-id="0f952-137">初めてのユーザーがサイトを体験した方法をエミュレートするには、[ **キャッシュを無効** にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0f952-137">To emulate how a first-time user experiences your site, check the **Disable cache** checkbox.</span></span>  <span data-ttu-id="0f952-138">DevTools は、ブラウザーのキャッシュを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0f952-138">DevTools disables the browser cache.</span></span>  <span data-ttu-id="0f952-139">これにより、初回のユーザーエクスペリエンスが正確にエミュレートされます。要求は、繰り返しアクセスの際にブラウザーのキャッシュから提供されるためです。</span><span class="sxs-lookup"><span data-stu-id="0f952-139">This more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="[キャッシュを無効にする] チェックボックス" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   <span data-ttu-id="0f952-141">図 5: **キャッシュを無効にする** チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0f952-141">Figure 5:  The **Disable Cache** checkbox</span></span>  
:::image-end:::  

#### <span data-ttu-id="0f952-142">[ネットワーク条件] ドロアーからブラウザーキャッシュを無効にする</span><span class="sxs-lookup"><span data-stu-id="0f952-142">Disable the browser cache from the Network Conditions drawer</span></span>  

<span data-ttu-id="0f952-143">他の DevTools パネルを操作しているときに、キャッシュを無効にするには、[ネットワーク条件] ドローワを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f952-143">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="0f952-144">[ **ネットワーク条件** ] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f952-144">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="0f952-145">[ **キャッシュを無効にする** ] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="0f952-145">Check or uncheck the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="0f952-146">ブラウザキャッシュを手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="0f952-146">Manually clear the browser cache</span></span>  

<span data-ttu-id="0f952-147">ブラウザーのキャッシュをいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキストメニュー \ (右クリック \) を開き、[ **ブラウザキャッシュのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-147">To manually clear the browser cache at any time, open the contextual menu \(right-click\) anywhere in the Requests table and select **Clear Browser Cache**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="[ブラウザーキャッシュのクリア] を選ぶ" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   <span data-ttu-id="0f952-149">図 6: [**ブラウザキャッシュのクリア**] の選択</span><span class="sxs-lookup"><span data-stu-id="0f952-149">Figure 6:  Selecting **Clear Browser Cache**</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-150">オフラインでエミュレートする</span><span class="sxs-lookup"><span data-stu-id="0f952-150">Emulate offline</span></span>  

<span data-ttu-id="0f952-151">[プログレッシブ Web アプリ][DevtoolsProgressiveWebApps]という名前の新しいクラスの web アプリでは、サービスの担当**者**のためにオフラインで機能します。</span><span class="sxs-lookup"><span data-stu-id="0f952-151">A new class of web apps, named [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="0f952-152">この種類のアプリを構築しているときに、データ接続がないデバイスをすばやくシミュレートすると便利です。</span><span class="sxs-lookup"><span data-stu-id="0f952-152">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="0f952-153">[ **オンライン** ] ドロップダウンメニューを選択し、[ **プリセット**] で検索し、[ **オフライン** ] を選択して、完全にオフラインのネットワークエクスペリエンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="0f952-153">Select the **Online** dropdown menu, search under **Presets**, and select **Offline** to simulate a completely offline network experience.</span></span>  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="[オフライン] ドロップダウンメニュー" lightbox="../media/network-network-offline-dropdown.msft.png":::
   <span data-ttu-id="0f952-155">図 7: [ **オフライン** ] ドロップダウンメニュー</span><span class="sxs-lookup"><span data-stu-id="0f952-155">Figure 7:  The **Offline** dropdown menu</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-156">低速ネットワーク接続のエミュレート</span><span class="sxs-lookup"><span data-stu-id="0f952-156">Emulate slow network connections</span></span>  

<span data-ttu-id="0f952-157">「 **オンライン** 」ドロップダウンメニューから、低速の3G、Fast 3g、その他の接続速度をエミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="0f952-157">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="[調整] ドロップダウンメニュー" lightbox="../media/network-network-throttling-menu.msft.png":::
   <span data-ttu-id="0f952-159">図 8: [ **調整** ] ドロップダウンメニュー</span><span class="sxs-lookup"><span data-stu-id="0f952-159">Figure 8:  The **Throttling** dropdown menu</span></span>  
:::image-end:::  

<span data-ttu-id="0f952-160">低速の3G や Fast 3G など、さまざまなプリセットから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="0f952-160">You may select from a variety of presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="0f952-161">また、[調整] メニューを開き、[**カスタム**追加] を選択して、独自のカスタムプリセットを追加することもでき  >  **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="0f952-161">You may also add your own custom presets by opening the Throttling menu and selecting **Custom** > **Add**.</span></span>  

<span data-ttu-id="0f952-162">DevTools は、調整が有効になっていることを通知するために、[ **ネットワーク** ] タブの横に警告アイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-162">DevTools displays a warning icon next to the **Network** tab to remind you that throttling is enabled.</span></span>  

#### <span data-ttu-id="0f952-163">ネットワークの状態のドロアーからの低速ネットワーク接続のエミュレート</span><span class="sxs-lookup"><span data-stu-id="0f952-163">Emulate slow network connections from the Network Conditions drawer</span></span>  

<span data-ttu-id="0f952-164">他の DevTools パネルでの作業中にネットワーク接続を調整したい場合は、ネットワーク条件の引き出しを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f952-164">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="0f952-165">[ **ネットワーク条件** ] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f952-165">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="0f952-166">**調整**メニューから希望の接続速度を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-166">Select your desired connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="0f952-167">ブラウザーの cookie を手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="0f952-167">Manually clear browser cookies</span></span>  

<span data-ttu-id="0f952-168">ブラウザーの cookie をいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキストメニュー \ (右クリック \) を開き、[ **ブラウザ cookie のクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-168">To manually clear browser cookies at any time, open the contextual menu \(right-click\) anywhere in the Requests table and select **Clear Browser Cookies**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="[ブラウザーのクリア Cookie の選択]" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   <span data-ttu-id="0f952-170">図 9:**クリアブラウザーの cookie**の選択</span><span class="sxs-lookup"><span data-stu-id="0f952-170">Figure 9:  Selecting **Clear Browser Cookies**</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-171">ユーザーエージェントを上書きする</span><span class="sxs-lookup"><span data-stu-id="0f952-171">Override the user agent</span></span>  

<span data-ttu-id="0f952-172">ユーザーエージェントを手動で上書きするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-172">To manually override the user agent:</span></span>  

1.  <span data-ttu-id="0f952-173">[ **ネットワーク条件** ] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f952-173">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="0f952-174">**[自動] をオフに**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-174">Uncheck **Select automatically**.</span></span>  
1.  <span data-ttu-id="0f952-175">メニューからユーザーエージェントオプションを選択するか、テキストボックスにユーザー設定のオプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="0f952-175">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <span data-ttu-id="0f952-176">フィルター要求</span><span class="sxs-lookup"><span data-stu-id="0f952-176">Filter requests</span></span>  

### <span data-ttu-id="0f952-177">プロパティによって要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0f952-177">Filter requests by properties</span></span>  

<span data-ttu-id="0f952-178">[ **フィルター** ] テキストボックスを使用して、要求のドメインやサイズなどのプロパティによって要求をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0f952-178">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="0f952-179">テキストボックスが表示されない場合は、[フィルター] ウィンドウが非表示になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f952-179">If you do not see the text box, the Filters pane is probably hidden.</span></span>  
<span data-ttu-id="0f952-180">「 [フィルターウィンドウを非表示にする」を](#hide-the-filters-pane)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f952-180">See [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="[フィルター] テキストボックス" lightbox="../media/network-network-filters-textbox.msft.png":::
   <span data-ttu-id="0f952-182">図 10: [ **フィルター** ] テキストボックス</span><span class="sxs-lookup"><span data-stu-id="0f952-182">Figure 10:  The **Filter** text box</span></span>  
:::image-end:::  

<span data-ttu-id="0f952-183">各プロパティをスペースで区切ることで、複数のプロパティを同時に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="0f952-183">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="0f952-184">たとえば、 `mime-type:image/png larger-than:1K` 1 kb より大きいすべての PNGs を表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-184">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than one kilobyte.</span></span>  <span data-ttu-id="0f952-185">これらのマルチプロパティフィルターは、操作に相当 `AND` します。</span><span class="sxs-lookup"><span data-stu-id="0f952-185">These multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="0f952-186">操作は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0f952-186">operations are currently not supported.</span></span>  

<span data-ttu-id="0f952-187">サポートされているプロパティの完全な一覧です。</span><span class="sxs-lookup"><span data-stu-id="0f952-187">The complete list of supported properties.</span></span>  

| <span data-ttu-id="0f952-188">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0f952-188">Property</span></span> | <span data-ttu-id="0f952-189">詳細</span><span class="sxs-lookup"><span data-stu-id="0f952-189">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="0f952-190">指定したドメインのリソースのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-190">Only display resources from the specified domain.</span></span>  <span data-ttu-id="0f952-191">複数のドメインを含めるには、ワイルドカード文字 \ (\) を使用することができ `*` ます。</span><span class="sxs-lookup"><span data-stu-id="0f952-191">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="0f952-192">たとえば、 `*.com` で終わるすべてのドメイン名のリソースが表示され `.com` ます。</span><span class="sxs-lookup"><span data-stu-id="0f952-192">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="0f952-193">DevTools は、オートコンプリートのドロップダウンメニューに、検出されたすべてのドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="0f952-193">DevTools populates the autocomplete dropdown menu with all of the domains it has encountered.</span></span> |  
| `has-response-header` | <span data-ttu-id="0f952-194">指定した HTTP 応答ヘッダーを含むリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-194">Show the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="0f952-195">DevTools は、オートコンプリートのドロップダウンリストに、検出されたすべての応答ヘッダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="0f952-195">DevTools populates the autocomplete dropdown with all of the response headers that it has encountered.</span></span> |  
| `is` | <span data-ttu-id="0f952-196">`is:running`リソースを検索するために使用 `WebSocket` します。</span><span class="sxs-lookup"><span data-stu-id="0f952-196">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="0f952-197">指定したサイズよりも大きいリソースをバイト単位で表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-197">Show resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="0f952-198">値の設定 `1000` は、の値の設定に相当 `1k` します。</span><span class="sxs-lookup"><span data-stu-id="0f952-198">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="0f952-199">指定した HTTP メソッドの種類によって取得されたリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-199">Show resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="0f952-200">DevTools は、検出されたすべての HTTP メソッドをドロップダウンに入力します。</span><span class="sxs-lookup"><span data-stu-id="0f952-200">DevTools populates the dropdown with all of the HTTP methods it has encountered.</span></span> |  
| `mime-type` | <span data-ttu-id="0f952-201">指定した MIME の種類のリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-201">Show resources of a specified MIME type.</span></span>  <span data-ttu-id="0f952-202">DevTools は、検出されたすべての MIME の種類をドロップダウンに入力します。</span><span class="sxs-lookup"><span data-stu-id="0f952-202">DevTools populates the dropdown with all MIME types it has encountered.</span></span> |  
| `mixed-content` | <span data-ttu-id="0f952-203">すべての混合コンテンツリソース \ ( `mixed-content:all` \) を表示するか、現在 \ (\) を表示しているものだけを表示し `mixed-content:displayed` ます。</span><span class="sxs-lookup"><span data-stu-id="0f952-203">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="0f952-204">保護されていない HTTP \ ( `scheme:http` \) または保護された HTTPS \ (\) 経由で取得したリソースを表示 `scheme:https` します。</span><span class="sxs-lookup"><span data-stu-id="0f952-204">Show resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="0f952-205">指定した `Set-Cookie` 値と一致する属性を持つヘッダーが含まれているリソースを表示し `Domain` ます。</span><span class="sxs-lookup"><span data-stu-id="0f952-205">Show the resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="0f952-206">DevTools は、検出されたすべての cookie ドメインにオートコンプリートを設定します。</span><span class="sxs-lookup"><span data-stu-id="0f952-206">DevTools populates the autocomplete with all of the cookie domains that it has encountered.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="0f952-207">指定した値と一致する名前のヘッダーが含まれているリソースを表示し `Set-Cookie` ます。</span><span class="sxs-lookup"><span data-stu-id="0f952-207">Show the resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="0f952-208">DevTools は、検出されたすべての cookie 名でオートコンプリートを入力します。</span><span class="sxs-lookup"><span data-stu-id="0f952-208">DevTools populates the autocomplete with all of the cookie names that it has encountered.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="0f952-209">指定した `Set-Cookie` 値と一致する値を含むヘッダーが含まれているリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-209">Show the resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="0f952-210">DevTools は、検出されたすべての cookie 値でオートコンプリートを設定します。</span><span class="sxs-lookup"><span data-stu-id="0f952-210">DevTools populates the autocomplete with all of the cookie values that it has encountered.</span></span> |  
| `status-code` | <span data-ttu-id="0f952-211">HTTP ステータスコードが指定されたコードと一致するリソースのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-211">Show only the resources for which the HTTP status code matches the specified code.</span></span>  <span data-ttu-id="0f952-212">DevTools は、オートコンプリートのドロップダウンメニューに、検出されたすべての状態コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="0f952-212">DevTools populates the autocomplete dropdown menu with all of the status codes it has encountered.</span></span> |  

### <span data-ttu-id="0f952-213">種類別に要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0f952-213">Filter requests by type</span></span>  

<span data-ttu-id="0f952-214">要求の種類によって要求をフィルター処理するには、[ネットワーク] パネルの **Xhr**、 **JS**、 **CSS**、 **Img**、 **Media**、 **Font**、 **Doc**、 **WS** \ (WebSocket \)、 **マニフェスト**、 **その他** \ (ここに一覧表示されていないその他の種類) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-214">To filter requests by request type, select the **XHR**, **JS**, **CSS**, **Img**, **Media**, **Font**, **Doc**, **WS** \(WebSocket\), **Manifest**, or **Other** \(any other type not listed here\) buttons on the Network panel.</span></span>  

<span data-ttu-id="0f952-215">これらのボタンが表示されない場合は、[フィルター] ウィンドウが非表示になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f952-215">If you do not see these buttons, the Filters pane is probably hidden.</span></span>  
<span data-ttu-id="0f952-216">「 [フィルターウィンドウを非表示にする」を](#hide-the-filters-pane)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f952-216">See [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="0f952-217">複数の種類のフィルターを同時に有効にするに `Control` は、\ (Windows \) または `Command` \ (macOS \) を保持し、を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-217">To enable multiple type filters simultaneously, hold `Control` \(Windows\) or `Command` \(macOS\) and then select.</span></span>  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="型フィルターを使用した JS、CSS、およびドキュメントのリソースの表示" lightbox="../media/network-network-type-filters.msft.png":::
   <span data-ttu-id="0f952-219">図 11: 型フィルターを使用して JS、CSS、およびドキュメントのリソースを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-219">Figure 11:  Using the Type filters to display JS, CSS, and Document resources</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-220">時間に基づいて要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0f952-220">Filter requests by time</span></span>  

<span data-ttu-id="0f952-221">[概要] ウィンドウで左または右にドラッグすると、その期間中にアクティブだった要求のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-221">Select and drag left or right on the Overview pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="0f952-222">フィルターは包含されています。</span><span class="sxs-lookup"><span data-stu-id="0f952-222">The filter is inclusive.</span></span>  <span data-ttu-id="0f952-223">強調表示された時間にアクティブだった要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-223">Any request that was active during the highlighted time is shown.</span></span>  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="300ms の非アクティブな要求をすべてフィルターで除外する" lightbox="../media/network-network-overview-filter.msft.png":::
   <span data-ttu-id="0f952-225">図 12: 300ms を介して非アクティブになっていた要求をすべてフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="0f952-225">Figure 12:  Filtering out any requests that were inactive around 300ms</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-226">データ Url を非表示にする</span><span class="sxs-lookup"><span data-stu-id="0f952-226">Hide data URLs</span></span>  

<span data-ttu-id="0f952-227">[データ url][MDNHTTPDataURIs] は、他のドキュメントに埋め込まれた小さなファイルです。</span><span class="sxs-lookup"><span data-stu-id="0f952-227">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="0f952-228">が開始する要求テーブルに `data:` は、データの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-228">Any request that you see in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="0f952-229">[ **データ url を非表示** にする] チェックボックスをオンにして要求を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="0f952-229">Check the **Hide data URLs** checkbox to hide the requests.</span></span>  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="[データ Url を非表示にする] チェックボックス" lightbox="../media/network-network-hide-data-urls.msft.png":::
   <span data-ttu-id="0f952-231">図 13: [ **データ Url を非表示** にする] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0f952-231">Figure 13:  The **Hide Data URLs** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="0f952-232">並べ替え要求</span><span class="sxs-lookup"><span data-stu-id="0f952-232">Sort requests</span></span>  

<span data-ttu-id="0f952-233">既定では、要求テーブルの要求は開始時刻によって並べ替えられますが、他の条件を使用してテーブルを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="0f952-233">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <span data-ttu-id="0f952-234">列で並べ替え</span><span class="sxs-lookup"><span data-stu-id="0f952-234">Sort by column</span></span>  

<span data-ttu-id="0f952-235">要求内の任意の列のヘッダーを選び、その列によって要求を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="0f952-235">Select the header of any column in the Requests to sort requests by that column.</span></span>  

### <span data-ttu-id="0f952-236">アクティビティ別の並べ替えフェーズ</span><span class="sxs-lookup"><span data-stu-id="0f952-236">Sort by activity phase</span></span>  

<span data-ttu-id="0f952-237">ウォーターフォールでのリクエストの並べ替え方法を変更するには、要求テーブルのヘッダーにカーソルを合わせて、コンテキストメニュー \ (右クリック \) を開き、 **ウォーターフォール**をポイントして、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-237">To change how the Waterfall sorts requests, hover on the header of the Requests table, open the contextual menu \(right-click\), hover over **Waterfall**, and select one of the following options.</span></span>  

*   <span data-ttu-id="0f952-238">**開始時刻**。</span><span class="sxs-lookup"><span data-stu-id="0f952-238">**Start Time**.</span></span>  <span data-ttu-id="0f952-239">最初に開始された要求は一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="0f952-239">The first request that was initiated is at the top.</span></span>  
*   <span data-ttu-id="0f952-240">**応答時間**。</span><span class="sxs-lookup"><span data-stu-id="0f952-240">**Response Time**.</span></span>  <span data-ttu-id="0f952-241">ダウンロードを開始した最初の要求は上部にあります。</span><span class="sxs-lookup"><span data-stu-id="0f952-241">The first request that started downloading is at the top.</span></span>  
*   <span data-ttu-id="0f952-242">**終了時刻**。</span><span class="sxs-lookup"><span data-stu-id="0f952-242">**End Time**.</span></span>  <span data-ttu-id="0f952-243">最初の要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="0f952-243">The first request that finished is at the top.</span></span>  
*   <span data-ttu-id="0f952-244">**合計期間**。</span><span class="sxs-lookup"><span data-stu-id="0f952-244">**Total Duration**.</span></span>  <span data-ttu-id="0f952-245">最短接続の設定と要求/応答を含む要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="0f952-245">The request with the shortest connection setup and request / response is at the top.</span></span>  
*   <span data-ttu-id="0f952-246">**待機時間**。</span><span class="sxs-lookup"><span data-stu-id="0f952-246">**Latency**.</span></span>  <span data-ttu-id="0f952-247">応答の最短時間を待っている要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="0f952-247">The request that waited the shortest time for a response is at the top.</span></span>  

<span data-ttu-id="0f952-248">これらの説明は、それぞれのオプションが最短から最長の順にランク付けされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0f952-248">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="0f952-249">[ **ウォーターフォール** ] 列のヘッダーを選択すると、順序が逆になります。</span><span class="sxs-lookup"><span data-stu-id="0f952-249">Selecting the header of the **Waterfall** column reverses the order.</span></span>  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="ウォーターフォールを合計期間で並べ替える" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   <span data-ttu-id="0f952-251">図 14: ウォーターフォールを合計期間で並べ替える (各バーの明るい部分は待機時間で、暗い部分はバイトのダウンロードにかかる時間です)。</span><span class="sxs-lookup"><span data-stu-id="0f952-251">Figure 14:  Sorting the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
:::image-end:::  

## <span data-ttu-id="0f952-252">分析要求</span><span class="sxs-lookup"><span data-stu-id="0f952-252">Analyze requests</span></span>  

<span data-ttu-id="0f952-253">DevTools が開いている限り、すべての要求がネットワークパネルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-253">So long as DevTools is open, it logs all requests in the Network panel.</span></span>  
<span data-ttu-id="0f952-254">[ネットワーク] パネルを使用して要求を分析します。</span><span class="sxs-lookup"><span data-stu-id="0f952-254">Use the Network panel to analyze requests.</span></span>  

### <span data-ttu-id="0f952-255">要求のログを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-255">View a log of requests</span></span>  

<span data-ttu-id="0f952-256">[要求] テーブルを使って、DevTools が開いている間に行われたすべての要求のログを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-256">Use the Requests table to view a log of all requests made while DevTools has been open.</span></span>  <span data-ttu-id="0f952-257">要求を選択またはマウスでポイントすると、各項目の詳細情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-257">Selecting or hovering over requests reveals more information about each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="要求テーブル" lightbox="../media/network-network-requests-table.msft.png":::
   <span data-ttu-id="0f952-259">図 15: 要求テーブル</span><span class="sxs-lookup"><span data-stu-id="0f952-259">Figure 15:  The Requests table</span></span>  
:::image-end:::  

<span data-ttu-id="0f952-260">要求テーブルには、既定で次の列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-260">The Requests table displays the following columns by default.</span></span>  

*   <span data-ttu-id="0f952-261">**[名前]**。</span><span class="sxs-lookup"><span data-stu-id="0f952-261">**Name**.</span></span>  <span data-ttu-id="0f952-262">リソースのファイル名または識別子。</span><span class="sxs-lookup"><span data-stu-id="0f952-262">The filename of, or an identifier for, the resource.</span></span>  
*   <span data-ttu-id="0f952-263">**状態**。</span><span class="sxs-lookup"><span data-stu-id="0f952-263">**Status**.</span></span>  <span data-ttu-id="0f952-264">HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="0f952-264">The HTTP status code.</span></span>  
*   <span data-ttu-id="0f952-265">**[種類]**。</span><span class="sxs-lookup"><span data-stu-id="0f952-265">**Type**.</span></span>  <span data-ttu-id="0f952-266">要求されたリソースの MIME の種類。</span><span class="sxs-lookup"><span data-stu-id="0f952-266">The MIME type of the requested resource.</span></span>  
*   <span data-ttu-id="0f952-267">**イニシエーター**。</span><span class="sxs-lookup"><span data-stu-id="0f952-267">**Initiator**.</span></span>  <span data-ttu-id="0f952-268">次のオブジェクトまたはプロセスで要求が開始されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-268">The following objects or processes initiate requests:</span></span>  
    *   <span data-ttu-id="0f952-269">**パーサー**。</span><span class="sxs-lookup"><span data-stu-id="0f952-269">**Parser**.</span></span>  <span data-ttu-id="0f952-270">Microsoft Edge の HTML パーサー。</span><span class="sxs-lookup"><span data-stu-id="0f952-270">The HTML parser for Microsoft Edge.</span></span>  
    *   <span data-ttu-id="0f952-271">**リダイレクト**。</span><span class="sxs-lookup"><span data-stu-id="0f952-271">**Redirect**.</span></span>  <span data-ttu-id="0f952-272">HTTP リダイレクト。</span><span class="sxs-lookup"><span data-stu-id="0f952-272">An HTTP redirect.</span></span>  
    *   <span data-ttu-id="0f952-273">**スクリプト**。</span><span class="sxs-lookup"><span data-stu-id="0f952-273">**Script**.</span></span>  <span data-ttu-id="0f952-274">JavaScript 関数。</span><span class="sxs-lookup"><span data-stu-id="0f952-274">A JavaScript function.</span></span>  
    *   <span data-ttu-id="0f952-275">**その他**。</span><span class="sxs-lookup"><span data-stu-id="0f952-275">**Other**.</span></span>  <span data-ttu-id="0f952-276">リンクを介してページに移動したり、アドレスバーに URL を入力したりするなど、他のプロセスまたはアクション。</span><span class="sxs-lookup"><span data-stu-id="0f952-276">Some other process or action, such as navigating to a page via a link or entering a URL in the address bar.</span></span>  
*   <span data-ttu-id="0f952-277">**サイズ**。</span><span class="sxs-lookup"><span data-stu-id="0f952-277">**Size**.</span></span>  <span data-ttu-id="0f952-278">サーバーによって配信された、返信ヘッダーと応答本文の合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="0f952-278">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
*   <span data-ttu-id="0f952-279">**時刻**。</span><span class="sxs-lookup"><span data-stu-id="0f952-279">**Time**.</span></span>  <span data-ttu-id="0f952-280">要求の開始から、応答の最後のバイトの受領までの合計時間。</span><span class="sxs-lookup"><span data-stu-id="0f952-280">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
*   <span data-ttu-id="0f952-281">[**ウォーターフォール**](#view-the-timing-of-requests-in-relation-to-one-another)</span><span class="sxs-lookup"><span data-stu-id="0f952-281">[**Waterfall**](#view-the-timing-of-requests-in-relation-to-one-another).</span></span>  <span data-ttu-id="0f952-282">各要求のアクティビティの視覚的な分類。</span><span class="sxs-lookup"><span data-stu-id="0f952-282">A visual breakdown of the activity for each request.</span></span>  

#### <span data-ttu-id="0f952-283">列を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0f952-283">Add or remove columns</span></span>  

<span data-ttu-id="0f952-284">要求テーブルのヘッダーにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、表示または非表示にするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-284">Hover on the header of the Requests table, open the contextual menu \(right-click\), and select an option to hide or show it.</span></span>  <span data-ttu-id="0f952-285">現在表示されているオプションは各項目の横にチェックマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="0f952-285">Currently displayed options have checkmarks next to each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="要求テーブルへの列の追加" lightbox="../media/network-network-requests-add-column.msft.png":::
   <span data-ttu-id="0f952-287">図 16: 要求テーブルに列を追加する</span><span class="sxs-lookup"><span data-stu-id="0f952-287">Figure 16:  Adding a column to the Requests table</span></span>  
:::image-end:::  

#### <span data-ttu-id="0f952-288">カスタム列を追加する</span><span class="sxs-lookup"><span data-stu-id="0f952-288">Add custom columns</span></span>  

<span data-ttu-id="0f952-289">要求テーブルにカスタム列を追加するには、要求テーブルのヘッダーにマウスポインターを合わせて、コンテキストメニューを開き (\ を右クリック \)、[**応答ヘッダー**で  >  **ヘッダー列を管理**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-289">To add a custom column to the Requests table, hover on the header of the Requests table, open the contextual menu \(right-click\), and select **Response Headers** > **Manage Header Columns**.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="要求テーブルへのカスタム列の追加" lightbox="../media/network-network-requests-add-custom.msft.png":::
   <span data-ttu-id="0f952-291">図 17: 要求テーブルにカスタム列を追加する</span><span class="sxs-lookup"><span data-stu-id="0f952-291">Figure 17:  Adding a custom column to the Requests table</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-292">相互に関連した要求のタイミングを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-292">View the timing of requests in relation to one another</span></span>  

<span data-ttu-id="0f952-293">ウォーターフォールを使用すると、要求のタイミングを相互に関連して表示できます。</span><span class="sxs-lookup"><span data-stu-id="0f952-293">Use the Waterfall to view the timing of requests in relation to one another.</span></span>  
<span data-ttu-id="0f952-294">既定では、ウォーターフォールは要求の開始時刻によって構成されています。</span><span class="sxs-lookup"><span data-stu-id="0f952-294">By default, the Waterfall is organized by the start time of the requests.</span></span>  
<span data-ttu-id="0f952-295">そのため、左から右に向けて開始された要求よりも早く開始されています。</span><span class="sxs-lookup"><span data-stu-id="0f952-295">So, requests that are farther to the left started earlier than those that are farther to the right.</span></span>  

<span data-ttu-id="0f952-296">ウォーターフォールのさまざまな並べ替え方法を確認するには、「 [アクティビティ別に並べ替える](#sort-by-activity-phase) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f952-296">See [Sort by activity phase](#sort-by-activity-phase) to see the different ways that you may sort the Waterfall.</span></span>  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="[要求] ウィンドウの [ウォーターフォール] 列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   <span data-ttu-id="0f952-298">図 18: [ **要求** ] ウィンドウの [ウォーターフォール] 列</span><span class="sxs-lookup"><span data-stu-id="0f952-298">Figure 18:  The Waterfall column of the **Requests** pane</span></span>  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To view the frames of a WebSocket connection:  

1.  Select the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Select the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-select the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames tab" lightbox="../media/network-frames.msft.png":::
   Old Figure 20:  The **Frames** tab  
:::image-end:::  
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

### <span data-ttu-id="0f952-299">応答本文のプレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-299">View a preview of a response body</span></span>  

<span data-ttu-id="0f952-300">応答本文のプレビューを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-300">To view a preview of a response body:</span></span>  

1.  <span data-ttu-id="0f952-301">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-301">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0f952-302">[ **プレビュー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-302">Select the **Preview** tab.</span></span>  

<span data-ttu-id="0f952-303">このタブはほとんどの場合、画像を表示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f952-303">This tab is mostly useful for viewing images.</span></span>  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="[プレビュー] タブ" lightbox="../media/network-network-resources-preview.msft.png":::
   <span data-ttu-id="0f952-305">図 19: [ **プレビュー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="0f952-305">Figure 19:  The **Preview** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-306">応答本文を表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-306">View a response body</span></span>  

<span data-ttu-id="0f952-307">要求に対する応答の本文を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-307">To view the response body to a request:</span></span>  

1.  <span data-ttu-id="0f952-308">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-308">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0f952-309">[ **応答** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-309">Select the **Response** tab.</span></span>  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="[応答] タブ" lightbox="../media/network-network-resources-response.msft.png":::
   <span data-ttu-id="0f952-311">図 20: [ **応答** ] タブ</span><span class="sxs-lookup"><span data-stu-id="0f952-311">Figure 20:  The **Response** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-312">HTTP ヘッダーの表示</span><span class="sxs-lookup"><span data-stu-id="0f952-312">View HTTP headers</span></span>  

<span data-ttu-id="0f952-313">要求に関する HTTP ヘッダーデータを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-313">To view HTTP header data about a request:</span></span>  

1.  <span data-ttu-id="0f952-314">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-314">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0f952-315">[ **ヘッダー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-315">Select the **Headers** tab.</span></span>  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="[ヘッダー] タブ" lightbox="../media/network-resources-headers.msft.png":::
   <span data-ttu-id="0f952-317">図 21: [ **ヘッダー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="0f952-317">Figure 21:  The **Headers** tab</span></span>  
:::image-end:::  

#### <span data-ttu-id="0f952-318">HTTP ヘッダーソースの表示</span><span class="sxs-lookup"><span data-stu-id="0f952-318">View HTTP header source</span></span>  

<span data-ttu-id="0f952-319">既定では、[ヘッダー] タブにはヘッダーの名前がアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-319">By default, the Headers tab shows header names alphabetically.</span></span>  <span data-ttu-id="0f952-320">HTTP ヘッダーの名前を受け取った順序で表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-320">To view the HTTP header names in the order they were received:</span></span>  

1.  <span data-ttu-id="0f952-321">興味のある要求の [ **ヘッダー** ] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f952-321">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="0f952-322">「 [HTTP ヘッダーの表示](#view-http-headers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f952-322">See [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="0f952-323">[**要求ヘッダー** ] または [**応答ヘッダー** ] セクションの横にある [**ソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-323">Select **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <span data-ttu-id="0f952-324">クエリ文字列パラメーターの表示</span><span class="sxs-lookup"><span data-stu-id="0f952-324">View query string parameters</span></span>  

<span data-ttu-id="0f952-325">わかりやすい形式で URL のクエリ文字列パラメーターを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-325">To view the query string parameters of a URL in a human-readable format:</span></span>  

1.  <span data-ttu-id="0f952-326">興味のある要求の [ **ヘッダー** ] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f952-326">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="0f952-327">「 [HTTP ヘッダーの表示](#view-http-headers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f952-327">See [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="0f952-328">[ **クエリ文字列パラメーター** ] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f952-328">Go to the **Query String Parameters** section.</span></span>  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="[クエリ文字列パラメーター] セクション" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   <span data-ttu-id="0f952-330">図 22: [ **クエリ文字列パラメーター** ] セクション</span><span class="sxs-lookup"><span data-stu-id="0f952-330">Figure 22:  The **Query String Parameters** section</span></span>  
:::image-end:::  

#### <span data-ttu-id="0f952-331">クエリ文字列パラメーターソースの表示</span><span class="sxs-lookup"><span data-stu-id="0f952-331">View query string parameters source</span></span>  

<span data-ttu-id="0f952-332">要求のクエリ文字列のパラメーターソースを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-332">To view the query string parameter source of a request:</span></span>  

1.  <span data-ttu-id="0f952-333">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f952-333">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="0f952-334">「 [クエリ文字列パラメーターの表示](#view-query-string-parameters)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f952-334">See [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="0f952-335">[ **ソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-335">Select **view source**.</span></span>  

#### <span data-ttu-id="0f952-336">URL 形式でエンコードされたクエリ文字列パラメーターの表示</span><span class="sxs-lookup"><span data-stu-id="0f952-336">View URL-encoded query string parameters</span></span>  

<span data-ttu-id="0f952-337">わかりやすい形式でクエリ文字列パラメーターを表示するには、次のようにエンコードを保持します。</span><span class="sxs-lookup"><span data-stu-id="0f952-337">To view query string parameters in a human-readable format, but with encodings preserved:</span></span>  

1.  <span data-ttu-id="0f952-338">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f952-338">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="0f952-339">「 [クエリ文字列パラメーターの表示](#view-query-string-parameters)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f952-339">See [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="0f952-340">[ **表示 URL をエンコード**した] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-340">Select **view URL encoded**.</span></span>  

### <span data-ttu-id="0f952-341">Cookie の表示</span><span class="sxs-lookup"><span data-stu-id="0f952-341">View cookies</span></span>  

<span data-ttu-id="0f952-342">要求の HTTP ヘッダーで送信された cookie を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-342">To view the cookies sent in the HTTP header of a request:</span></span>  

1.  <span data-ttu-id="0f952-343">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-343">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0f952-344">[ **Cookies** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-344">Select the **Cookies** tab.</span></span>  

<!--See [Fields][ManageDataCookiesFields] for a description of each of the columns.  -->

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->
<!--TODO: add link when section is available -->

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="[Cookie] タブ" lightbox="../media/network-network-resources-cookies.msft.png":::
   <span data-ttu-id="0f952-346">図 23: [Cookie] タブ</span><span class="sxs-lookup"><span data-stu-id="0f952-346">Figure 23:  The Cookies tab</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-347">要求のタイミングのブレークダウンを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-347">View the timing breakdown of a request</span></span>  

<span data-ttu-id="0f952-348">要求のタイミングの詳細を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f952-348">To view the timing breakdown of a request:</span></span>  

1.  <span data-ttu-id="0f952-349">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-349">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="0f952-350">[ **タイミング** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f952-350">Select the **Timing** tab.</span></span>  

<span data-ttu-id="0f952-351">このデータにすばやくアクセスする方法については、「 [タイミングのブレークダウンをプレビュー](#preview-a-timing-breakdown) する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f952-351">See [Preview a timing breakdown](#preview-a-timing-breakdown) for a faster way to access this data.</span></span>  

<span data-ttu-id="0f952-352">「タイミング」タブに表示される各フェーズについて詳しくは、「 [タイミングのブレークダウン](#timing-breakdown-phases-explained) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f952-352">See [Timing breakdown phases explained](#timing-breakdown-phases-explained) for more information about each of the phases that you may see in the Timing tab.</span></span>  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="[タイミング] タブ" lightbox="../media/network-network-resources-timing.msft.png":::
   <span data-ttu-id="0f952-354">図 24: [ **タイミング** ] タブ</span><span class="sxs-lookup"><span data-stu-id="0f952-354">Figure 24:  The **Timing** tab</span></span>  
:::image-end:::  

<span data-ttu-id="0f952-355">各フェーズに関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="0f952-355">More information about each of the phases.</span></span>  

<span data-ttu-id="0f952-356">このビューにアクセスする別の方法については、「 [タイミングの内訳を表示](#view-the-timing-breakdown-of-a-request) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f952-356">See [View timing breakdown](#view-the-timing-breakdown-of-a-request) for another way to access this view.</span></span>  

#### <span data-ttu-id="0f952-357">タイミングの内訳をプレビューする</span><span class="sxs-lookup"><span data-stu-id="0f952-357">Preview a timing breakdown</span></span>  

<span data-ttu-id="0f952-358">要求のタイミングの内訳のプレビューを表示するには、要求テーブルの [ **ウォーターフォール** ] 列で要求のエントリにマウスポインターを合わせます。</span><span class="sxs-lookup"><span data-stu-id="0f952-358">To view a preview of the timing breakdown of a request, hover over the entry for the request in the **Waterfall** column of the Requests table.</span></span>  

<span data-ttu-id="0f952-359">詳しくは [、「ホバーを必要](#view-the-timing-breakdown-of-a-request) としないデータにアクセスする方法」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f952-359">See [View the timing breakdown of a request](#view-the-timing-breakdown-of-a-request) for a way to access this data that does not require hovering.</span></span>  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="要求のタイミングのブレークダウンのプレビューを >" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   <span data-ttu-id="0f952-361">図 25: 要求のタイミングのブレークダウンのプレビュー</span><span class="sxs-lookup"><span data-stu-id="0f952-361">Figure 25:  Previewing the timing breakdown of a request</span></span>  
:::image-end:::  

#### <span data-ttu-id="0f952-362">タイミングのブレークフェーズについて</span><span class="sxs-lookup"><span data-stu-id="0f952-362">Timing breakdown phases explained</span></span>  

<span data-ttu-id="0f952-363">[ **タイミング** ] タブに表示される各フェーズについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0f952-363">More information about each of the phases you may see in the **Timing** tab.</span></span>  

*   <span data-ttu-id="0f952-364">**キューイング**。</span><span class="sxs-lookup"><span data-stu-id="0f952-364">**Queueing**.</span></span>  <span data-ttu-id="0f952-365">ブラウザーは、次の場合に要求をキューに表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-365">The browser queues requests when:</span></span>  
    *   <span data-ttu-id="0f952-366">優先度の高い要求もあります。</span><span class="sxs-lookup"><span data-stu-id="0f952-366">There are higher priority requests.</span></span>  
    *   <span data-ttu-id="0f952-367">この起点で既に6つの TCP 接続が開かれています。これは制限です。</span><span class="sxs-lookup"><span data-stu-id="0f952-367">There are already six TCP connections open for this origin, which is the limit.</span></span>  <span data-ttu-id="0f952-368">HTTP/1.0 および HTTP/1.1 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-368">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
    *   <span data-ttu-id="0f952-369">ブラウザーは、ディスクキャッシュの領域を一時的に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0f952-369">The browser is briefly allocating space in the disk cache.</span></span>  
*   <span data-ttu-id="0f952-370">**失速**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-370">**Stalled**.</span></span>  <span data-ttu-id="0f952-371">**キュー**に記載されている理由のいずれかで、要求が停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f952-371">The request could be stalled for any of the reasons described in **Queueing**.</span></span>  
*   <span data-ttu-id="0f952-372">**DNS 検索**。</span><span class="sxs-lookup"><span data-stu-id="0f952-372">**DNS Lookup**.</span></span>  <span data-ttu-id="0f952-373">ブラウザーが要求の IP アドレスを解決しています。</span><span class="sxs-lookup"><span data-stu-id="0f952-373">The browser is resolving the IP address for the request.</span></span>  
*   <span data-ttu-id="0f952-374">**初期接続**。</span><span class="sxs-lookup"><span data-stu-id="0f952-374">**Initial connection**.</span></span>  <span data-ttu-id="0f952-375">ブラウザーでは、TCP ハンドシェイク、TCP リトライ、SSL のネゴシエーションなどの接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-375">The browser is establishing a connection including TCP handshakes, TCP retries, and negotiating an SSL.</span></span>
*   <span data-ttu-id="0f952-376">**プロキシネゴシエーション**。</span><span class="sxs-lookup"><span data-stu-id="0f952-376">**Proxy negotiation**.</span></span>  <span data-ttu-id="0f952-377">ブラウザーは、要求を [プロキシサーバー][WikiProxyServer]とネゴシエートしています。</span><span class="sxs-lookup"><span data-stu-id="0f952-377">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
*   <span data-ttu-id="0f952-378">**リクエストを送信**しました。</span><span class="sxs-lookup"><span data-stu-id="0f952-378">**Request sent**.</span></span>  <span data-ttu-id="0f952-379">要求が送信されています。</span><span class="sxs-lookup"><span data-stu-id="0f952-379">The request is being sent.</span></span>  
*   <span data-ttu-id="0f952-380">**Serviceworker の準備**。</span><span class="sxs-lookup"><span data-stu-id="0f952-380">**ServiceWorker Preparation**.</span></span>  <span data-ttu-id="0f952-381">ブラウザーがサービスワーカーを開始しています。</span><span class="sxs-lookup"><span data-stu-id="0f952-381">The browser is starting up the service worker.</span></span>  
*   <span data-ttu-id="0f952-382">**ServiceWorker へのリクエスト**。</span><span class="sxs-lookup"><span data-stu-id="0f952-382">**Request to ServiceWorker**.</span></span>  <span data-ttu-id="0f952-383">要求がサービスワーカーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-383">The request is being sent to the service worker.</span></span>  
*   <span data-ttu-id="0f952-384">**\ (TTFB \) を待機**しています。</span><span class="sxs-lookup"><span data-stu-id="0f952-384">**Waiting \(TTFB\)**.</span></span>  <span data-ttu-id="0f952-385">ブラウザーは、応答の最初のバイトを待機しています。</span><span class="sxs-lookup"><span data-stu-id="0f952-385">The browser is waiting for the first byte of a response.</span></span>  <span data-ttu-id="0f952-386">TTFB は、最初のバイトまでの時間を表します。</span><span class="sxs-lookup"><span data-stu-id="0f952-386">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="0f952-387">このタイミングには、待機時間が1往復、サーバーが応答の準備にかかった時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f952-387">This timing includes 1 round trip of latency and the time the server took to prepare the response.</span></span>  
*   <span data-ttu-id="0f952-388">**コンテンツのダウンロード**。</span><span class="sxs-lookup"><span data-stu-id="0f952-388">**Content Download**.</span></span>  <span data-ttu-id="0f952-389">ブラウザーが応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="0f952-389">The browser is receiving the response.</span></span>  
*   <span data-ttu-id="0f952-390">**プッシュ配信**。</span><span class="sxs-lookup"><span data-stu-id="0f952-390">**Receiving Push**.</span></span>  <span data-ttu-id="0f952-391">ブラウザーが、HTTP/2 Server プッシュ経由でこの応答のデータを受信しています。</span><span class="sxs-lookup"><span data-stu-id="0f952-391">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
*   <span data-ttu-id="0f952-392">**プッシュ中**。</span><span class="sxs-lookup"><span data-stu-id="0f952-392">**Reading Push**.</span></span>  <span data-ttu-id="0f952-393">ブラウザーは、前に受信したローカルデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="0f952-393">The browser is reading the local data previously received.</span></span>  

### <span data-ttu-id="0f952-394">イニシエーターと依存関係を表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-394">View initiators and dependencies</span></span>  

<span data-ttu-id="0f952-395">要求のイニシエーターと依存関係を表示するには、[ `Shift` 要求] テーブルの要求をポイントしたままにします。</span><span class="sxs-lookup"><span data-stu-id="0f952-395">To view the initiators and dependencies of a request, hold `Shift`and hover over the request in the Requests table.</span></span>  <span data-ttu-id="0f952-396">DevTools の色: イニシエーターは緑で表示され、依存関係は赤で示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-396">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="要求のイニシエーターと依存関係の表示" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   <span data-ttu-id="0f952-398">図 26: 要求のイニシエーターと依存関係を表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-398">Figure 26:  Viewing the initiators and dependencies of a request</span></span>  
:::image-end:::  

<span data-ttu-id="0f952-399">要求テーブルが時系列順に並べ替えられている場合、ポイントしている1つ上の緑の要求が依存関係のイニシエーターになります。</span><span class="sxs-lookup"><span data-stu-id="0f952-399">When the Requests table is ordered chronologically, the first green request above the one you are hovering is the initiator of the dependency.</span></span>  <span data-ttu-id="0f952-400">別の緑の要求がその上に表示されている場合は、その上位の要求がイニシエーターのイニシエーターになります。</span><span class="sxs-lookup"><span data-stu-id="0f952-400">If another green request appears above that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="0f952-401">などなど。</span><span class="sxs-lookup"><span data-stu-id="0f952-401">And so on.</span></span>  

### <span data-ttu-id="0f952-402">読み込みイベントを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-402">View load events</span></span>  

<span data-ttu-id="0f952-403">DevTools は、 `DOMContentLoaded` [ `load` ネットワーク] パネル上の複数の場所にある [イベントのタイミング] を表示します。</span><span class="sxs-lookup"><span data-stu-id="0f952-403">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the Network panel.</span></span>  <span data-ttu-id="0f952-404">`DOMContentLoaded`イベントは青色で色分けされ、 `load` イベントは赤になります。</span><span class="sxs-lookup"><span data-stu-id="0f952-404">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="[ネットワーク] パネルでの DOMContentLoaded と load イベントの場所" lightbox="../media/network-network-requests-load-events.msft.png":::
   <span data-ttu-id="0f952-406">図 27: `DOMContentLoaded` `load` ネットワークパネル上のイベントとイベントの場所</span><span class="sxs-lookup"><span data-stu-id="0f952-406">Figure 27:  The locations of the `DOMContentLoaded` and `load` events on the Network panel</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-407">要求の合計数を表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-407">View the total number of requests</span></span>  

<span data-ttu-id="0f952-408">[ネットワーク] パネルの下部にある [概要] ウィンドウに、要求の合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-408">The total number of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="0f952-409">この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="0f952-409">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="0f952-410">DevTools が開かれる前に他の要求が発生した場合、これらの要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="0f952-410">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="DevTools が開かれてからの要求の合計数です。" lightbox="../media/network-network-total-requests.msft.png":::
   <span data-ttu-id="0f952-412">図 28: DevTools が開かれた後の要求の合計数</span><span class="sxs-lookup"><span data-stu-id="0f952-412">Figure 28:  The total number of requests since DevTools was opened</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-413">ダウンロードの合計サイズを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-413">View the total download size</span></span>  

<span data-ttu-id="0f952-414">要求の合計ダウンロードサイズが、[ネットワーク] パネルの下部にある [概要] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-414">The total download size of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="0f952-415">この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="0f952-415">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="0f952-416">DevTools が開かれる前に、他の要求が発生した場合、以前の要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="0f952-416">If other requests occurred before DevTools was opened, the previous requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="リクエストのダウンロード合計サイズ" lightbox="../media/network-network-total-download-size.msft.png":::
   <span data-ttu-id="0f952-418">図 29: 要求のダウンロード合計サイズ</span><span class="sxs-lookup"><span data-stu-id="0f952-418">Figure 29:  The total download size of requests</span></span>  
:::image-end:::  

<span data-ttu-id="0f952-419">各項目を圧縮した後の大きなリソースについては [、「リソースの未圧縮サイズを表示](#view-the-uncompressed-size-of-a-resource) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f952-419">See [View the uncompressed size of a resource](#view-the-uncompressed-size-of-a-resource) to see how large resources are after the browser uncompresses each item.</span></span>  

### <span data-ttu-id="0f952-420">要求の原因となったスタックトレースを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-420">View the stack trace that caused a request</span></span>  

<span data-ttu-id="0f952-421">JavaScript ステートメントでリソースを要求した後、[ **イニシエーター** ] 列をマウスでポイントすると、要求までのスタックトレースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-421">After a JavaScript statement requests a resource, hover over the **Initiator** column to view the stack trace leading up to the request.</span></span>  

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

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="リソース要求までのスタックトレース" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   <span data-ttu-id="0f952-423">図 30: リソース要求までのスタックトレース</span><span class="sxs-lookup"><span data-stu-id="0f952-423">Figure 30:  The stack trace leading up to a resource request</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-424">リソースの未圧縮サイズを表示する</span><span class="sxs-lookup"><span data-stu-id="0f952-424">View the uncompressed size of a resource</span></span>  

<span data-ttu-id="0f952-425">[ **大きな要求行を使用する** ] チェックボックスをオンにして、[ **サイズ** ] 列の下の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f952-425">Select the **Use large request rows** checkbox and then look at the bottom value of the **Size** column.</span></span>  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="圧縮されていないリソースの例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   <span data-ttu-id="0f952-427">図 31: 圧縮されていないリソースの例 \ (ネットワーク経由で送信されたファイルの圧縮サイズ、圧縮されてい `jquery-3.3.1.min.js` ない `29.9 KB` サイズなど `84.9 KB` )</span><span class="sxs-lookup"><span data-stu-id="0f952-427">Figure 31:  An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
:::image-end:::  

## <span data-ttu-id="0f952-428">要求データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0f952-428">Export requests data</span></span>  

### <span data-ttu-id="0f952-429">すべてのネットワーク要求を HAR ファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="0f952-429">Save all network requests to a HAR file</span></span>  

<span data-ttu-id="0f952-430">すべてのネットワーク要求を HAR ファイルに保存するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f952-430">To save all network requests to a HAR file, complete the following steps.</span></span>  

1.  <span data-ttu-id="0f952-431">要求テーブル内の任意の要求にマウスポインターを合わせ、コンテキストメニューを開きます (\ を右クリックします)。</span><span class="sxs-lookup"><span data-stu-id="0f952-431">Hover on any request in the Requests table and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="0f952-432">[ **コンテンツを含む HAR として保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-432">Select **Save as HAR with Content**.</span></span>  <span data-ttu-id="0f952-433">DevTools は、HAR ファイルに対して DevTools を開いた後に発生した要求をすべて保存します。</span><span class="sxs-lookup"><span data-stu-id="0f952-433">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="0f952-434">要求をフィルター処理したり、1つの要求のみを保存したりする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="0f952-434">There is no way to filter requests, or to save just a single request.</span></span>  

<span data-ttu-id="0f952-435">HAR ファイルを保存すると、そのファイルを分析用の DevTools にインポートして戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="0f952-435">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="0f952-436">HAR ファイルを [要求] テーブルにドラッグアンドドロップするだけです。</span><span class="sxs-lookup"><span data-stu-id="0f952-436">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--See also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="[コンテンツを含む HAR として保存] を選ぶ" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   <span data-ttu-id="0f952-438">図 32: [**コンテンツを含む HAR として保存] を**選ぶ</span><span class="sxs-lookup"><span data-stu-id="0f952-438">Figure 32:  Selecting **Save as HAR with Content**</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-439">1つ以上の要求をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="0f952-439">Copy one or more requests to the clipboard</span></span>  

<span data-ttu-id="0f952-440">要求テーブルの [ **名前** ] 列で、要求をポイントし、コンテキストメニューを開きます。 \ (右クリック \)、[ **コピー**] をポイントして、次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="0f952-440">Under the **Name** column of the Requests table, hover on a request, open the contextual menu \(right-click\), hover over **Copy**, and select one of the following options.</span></span>  

*   <span data-ttu-id="0f952-441">**リンクアドレスをコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-441">**Copy Link Address**.</span></span>  <span data-ttu-id="0f952-442">要求の URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f952-442">Copy the URL of the request to the clipboard.</span></span>  
*   <span data-ttu-id="0f952-443">**回答をコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-443">**Copy Response**.</span></span>  <span data-ttu-id="0f952-444">応答本文をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f952-444">Copy the response body to the clipboard.</span></span>  
*   <span data-ttu-id="0f952-445">**取り出しとしてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-445">**Copy as Fetch**.</span></span>  
*   <span data-ttu-id="0f952-446">**CURL としてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-446">**Copy as cURL**.</span></span>  <span data-ttu-id="0f952-447">CURL コマンドとして要求をコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f952-447">Copy the request as a cURL command.</span></span>  
*   <span data-ttu-id="0f952-448">**すべてを Fetch としてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-448">**Copy All as Fetch**.</span></span>  
*   <span data-ttu-id="0f952-449">**CURL としてすべてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-449">**Copy All as cURL**.</span></span>  <span data-ttu-id="0f952-450">すべての要求を cURL コマンドのチェーンとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f952-450">Copy all requests as a chain of cURL commands.</span></span>  
*   <span data-ttu-id="0f952-451">**すべてを HAR としてコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0f952-451">**Copy All as HAR**.</span></span>  <span data-ttu-id="0f952-452">すべての要求を HAR データとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f952-452">Copy all requests as HAR data.</span></span>  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="[返信のコピー] の選択" lightbox="../media/network-network-requests-copy-response.msft.png":::
   <span data-ttu-id="0f952-454">図 33: [**返信のコピー** ] の選択</span><span class="sxs-lookup"><span data-stu-id="0f952-454">Figure 33:  Selecting **Copy Response**</span></span>  
:::image-end:::  

## <span data-ttu-id="0f952-455">[ネットワーク] パネルのレイアウトを変更する</span><span class="sxs-lookup"><span data-stu-id="0f952-455">Change the layout of the Network panel</span></span>  

<span data-ttu-id="0f952-456">ネットワークパネル UI のセクションを展開したり折りたたんだりして、重要な情報を強調することができます。</span><span class="sxs-lookup"><span data-stu-id="0f952-456">You may expand or collapse sections of the Network panel UI to focus important information.</span></span>  

### <span data-ttu-id="0f952-457">[フィルター] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="0f952-457">Hide the Filters pane</span></span>  

<span data-ttu-id="0f952-458">既定では、DevTools によって [ **フィルター] ウィンドウ**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-458">By default, DevTools shows the **Filters pane**.</span></span>  
<span data-ttu-id="0f952-459">[フィルターフィルター] を **選択し** ![ ][ImageFilterIcon] て非表示にします。</span><span class="sxs-lookup"><span data-stu-id="0f952-459">Select **Filter** ![Filter][ImageFilterIcon] to hide it.</span></span>  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="[フィルターの非表示] ボタン" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   <span data-ttu-id="0f952-461">図 34: [フィルターの非表示] ボタン</span><span class="sxs-lookup"><span data-stu-id="0f952-461">Figure 34:  The Hide Filters button</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-462">大きな要求行を使用する</span><span class="sxs-lookup"><span data-stu-id="0f952-462">Use large request rows</span></span>  

<span data-ttu-id="0f952-463">ネットワーク要求テーブルにより多くの空白が必要な場合は、大きな行を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f952-463">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="0f952-464">列によっては、大きな行を使用するときに、さらに多くの情報が表示される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0f952-464">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="0f952-465">たとえば、 **Size** 列の下の値は、要求の非圧縮サイズです。</span><span class="sxs-lookup"><span data-stu-id="0f952-465">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="要求ウィンドウの大きな要求行の例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   <span data-ttu-id="0f952-467">図 35: [ **要求** ] ウィンドウの大きな要求行の例</span><span class="sxs-lookup"><span data-stu-id="0f952-467">Figure 35:  An example of large request rows in the **Requests** pane</span></span>  
:::image-end:::  

<span data-ttu-id="0f952-468">大きな行を有効にするには、[ **大きな要求行を使用** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0f952-468">Select the **Use large request rows** checkbox to enable large rows.</span></span>  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="[大きな要求行の使用] チェックボックス" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   <span data-ttu-id="0f952-470">図 36: [ **大きな要求行の使用** ] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0f952-470">Figure 36:  The **Use large request rows** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="0f952-471">[概要] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="0f952-471">Hide the Overview pane</span></span>  

<span data-ttu-id="0f952-472">既定では、DevTools によって [ **概要] ウィンドウ**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-472">By default, DevTools shows the **Overview pane**.</span></span>  <span data-ttu-id="0f952-473">[ **概要の表示** ] チェックボックスをオフにして非表示にします。</span><span class="sxs-lookup"><span data-stu-id="0f952-473">Deselect the **Show Overview** checkbox to hide it.</span></span>  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="[概要の表示] チェックボックス" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   <span data-ttu-id="0f952-475">図 37: [ **概要の表示** ] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0f952-475">Figure 37:  The **Show Overview** checkbox</span></span>  
:::image-end:::  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: /microsoft-edge/devtools-guide-chromium/network/progressive-web-apps "プログレッシブ Web アプリをデバッグする"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "データ Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "プロキシサーバー-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="0f952-479">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f952-479">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0f952-480">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="0f952-480">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0f952-482">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0f952-482">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
