---
description: Microsoft Edge DevTools のネットワークパネル機能の包括的な参照。
title: ネットワーク分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 758623482ab2179987c6467f8e30c72d8893d710
ms.sourcegitcommit: addfd27bb765c92880a59f259dc702f6e4e1bf28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "11092315"
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

# <span data-ttu-id="495fa-104">ネットワーク分析のリファレンス</span><span class="sxs-lookup"><span data-stu-id="495fa-104">Network Analysis reference</span></span>  

<span data-ttu-id="495fa-105">Microsoft Edge DevTools のネットワーク分析機能の包括的な参照でページがどのように読み込まれるかを分析するための新しい方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="495fa-105">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

<!--
> [!NOTE]
> This reference is based on Microsoft Edge 58.  If you use another version of Microsoft Edge, the UI, and features of DevTools may be different.  To verify which version of Microsoft Edge you are running, navigate to `edge://help`.  
-->

## <span data-ttu-id="495fa-106">ネットワーク要求を記録する</span><span class="sxs-lookup"><span data-stu-id="495fa-106">Record network requests</span></span>  

<span data-ttu-id="495fa-107">既定では、devtools が開いている限り、すべてのネットワーク要求がネットワークパネルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-107">By default, DevTools record all network requests in the Network panel, so long as DevTools is open.</span></span>  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-panel.msft.png":::
   <span data-ttu-id="495fa-109">[ **ネットワーク** ] パネル</span><span class="sxs-lookup"><span data-stu-id="495fa-109">The **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-110">ネットワーク要求の記録を停止する</span><span class="sxs-lookup"><span data-stu-id="495fa-110">Stop recording network requests</span></span>  

<span data-ttu-id="495fa-111">要求の記録を停止するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="495fa-111">To stop recording requests, complete the following steps.</span></span>  

1.  <span data-ttu-id="495fa-112">[ネットワーク] パネルの [**ネットワークログの記録を停止**する] を選択します (ネットワーク ![ ログの記録を停止し ][ImageRecordOnIcon] ます)。 **Network**</span><span class="sxs-lookup"><span data-stu-id="495fa-112">Select **Stop recording network log** \(![Stop recording network log][ImageRecordOnIcon]\) on the **Network** panel.</span></span>  <span data-ttu-id="495fa-113">灰色に変わり、DevTools が要求を記録しなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
1.  <span data-ttu-id="495fa-114">`Control` + `E` `Command` + `E` **ネットワーク**パネルがフォーカスされているときに、\ (Windows \) または \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="495fa-114">Press `Control`+`E` \(Windows\) or `Command`+`E` \(macOS\) while the **Network** panel is in focus.</span></span>  

### <span data-ttu-id="495fa-115">要求をクリアする</span><span class="sxs-lookup"><span data-stu-id="495fa-115">Clear requests</span></span>  

<span data-ttu-id="495fa-116">[ネットワーク] パネルの [ **クリア** ] (オフ) を選択して ![ ][ImageClearIcon] 、要求テーブルからのすべての要求をクリアします。</span><span class="sxs-lookup"><span data-stu-id="495fa-116">Select **Clear** \(![Clear][ImageClearIcon]\) on the Network panel to clear all requests from the Requests table.</span></span>  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-clear-button.msft.png":::
   <span data-ttu-id="495fa-118">[ **クリア** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="495fa-118">The **Clear** button</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-119">ページのロード間で要求を保存する</span><span class="sxs-lookup"><span data-stu-id="495fa-119">Save requests across page loads</span></span>  

<span data-ttu-id="495fa-120">ページの読み込み時に要求を保存するには、[ネットワーク] パネルの [ **ログを保持** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="495fa-120">To save requests across page loads, check the **Preserve log** checkbox on the Network panel.</span></span>  <span data-ttu-id="495fa-121">DevTools では、 **Preserve log**を無効にするまで、すべての要求が保存されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-121">DevTools saves all requests until you disable **Preserve log**.</span></span>  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-preserve-log.msft.png":::
   <span data-ttu-id="495fa-123">[ **ログの保存** ] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="495fa-123">The **Preserve Log** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-124">ページの読み込み中にスクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="495fa-124">Capture screenshots during page load</span></span>  

<span data-ttu-id="495fa-125">ページが読み込まれるのを待っている間にユーザーに表示される内容を分析するためのスクリーンショットをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="495fa-125">Capture screenshots to analyze what displays for users while waiting for your page to load.</span></span>  

<span data-ttu-id="495fa-126">スクリーンショットを有効にするには、[**ネットワーク設定**] を選択し、[**ネットワーク**] パネルの [**スクリーンショットのキャプチャ**] チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-126">To enable screenshots, select **Network settings** and select **Capture screenshots** checkbox on the **Network** panel.</span></span>  

<span data-ttu-id="495fa-127">**ネットワーク**パネルがフォーカスされているときにページを更新して、スクリーンショットをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="495fa-127">Refresh the page while the **Network** panel is in focus to capture screenshots.</span></span>  

<span data-ttu-id="495fa-128">スクリーンショットをキャプチャした後、次のように操作します。</span><span class="sxs-lookup"><span data-stu-id="495fa-128">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="495fa-129">スクリーンショットにマウスポインターを置くと、そのスクリーンショットがキャプチャされた点が表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-129">Hover over a screenshot to view the point at which that screenshot was captured.</span></span>  <span data-ttu-id="495fa-130">[ **概要** ] ウィンドウに黄色の線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-130">A yellow line is displayed on the **Overview** pane.</span></span>  
*   <span data-ttu-id="495fa-131">スクリーンショットがキャプチャされた後に発生した要求をすべて除外するには、画面のサムネイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-131">Select the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="495fa-132">サムネイルをダブルクリックして拡大します。</span><span class="sxs-lookup"><span data-stu-id="495fa-132">Double-click a thumbnail to zoom into it.</span></span>  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-screenshot-hover.msft.png":::
   <span data-ttu-id="495fa-134">スクリーンショット上のマウスポインター</span><span class="sxs-lookup"><span data-stu-id="495fa-134">Hovering over a screenshot</span></span>  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and select **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-replay-xhr.msft.png":::
   Selecting Replay XHR  
:::image-end:::  
-->  

## <span data-ttu-id="495fa-135">読み込み動作を変更する</span><span class="sxs-lookup"><span data-stu-id="495fa-135">Change loading behavior</span></span>  

### <span data-ttu-id="495fa-136">ブラウザーのキャッシュを無効にして、初めてのユーザーをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="495fa-136">Emulate a first-time visitor by disabling the browser cache</span></span>  

<span data-ttu-id="495fa-137">初めてのユーザーがサイトを体験した方法をエミュレートするには、[ **キャッシュを無効** にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="495fa-137">To emulate how a first-time user experiences your site, check the **Disable cache** checkbox.</span></span>  <span data-ttu-id="495fa-138">DevTools は、ブラウザーのキャッシュを無効にします。</span><span class="sxs-lookup"><span data-stu-id="495fa-138">DevTools disables the browser cache.</span></span>  <span data-ttu-id="495fa-139">この機能は、初回のユーザーエクスペリエンスをより正確にエミュレートします。要求は、繰り返しアクセスの際にブラウザーのキャッシュから提供されるためです。</span><span class="sxs-lookup"><span data-stu-id="495fa-139">This feature more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   <span data-ttu-id="495fa-141">[ **キャッシュを無効にする** ] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="495fa-141">The **Disable Cache** checkbox</span></span>  
:::image-end:::  

#### <span data-ttu-id="495fa-142">[ネットワーク条件] ドロアーからブラウザーキャッシュを無効にする</span><span class="sxs-lookup"><span data-stu-id="495fa-142">Disable the browser cache from the Network Conditions drawer</span></span>  

<span data-ttu-id="495fa-143">他の DevTools パネルを操作しているときに、キャッシュを無効にするには、[ネットワーク条件] ドローワを使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-143">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="495fa-144">[ **ネットワーク条件** ] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="495fa-144">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="495fa-145">[ **キャッシュを無効にする** ] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="495fa-145">Check or uncheck the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="495fa-146">ブラウザキャッシュを手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="495fa-146">Manually clear the browser cache</span></span>  

<span data-ttu-id="495fa-147">ブラウザーのキャッシュをいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキストメニュー \ (右クリック \) を開き、[ **ブラウザキャッシュのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-147">To manually clear the browser cache at any time, open the contextual menu \(right-click\) anywhere in the Requests table and select **Clear Browser Cache**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   <span data-ttu-id="495fa-149">[**ブラウザーキャッシュのクリア**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="495fa-149">Selecting **Clear Browser Cache**</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-150">オフラインでエミュレートする</span><span class="sxs-lookup"><span data-stu-id="495fa-150">Emulate offline</span></span>  

<span data-ttu-id="495fa-151">[プログレッシブ Web アプリ][DevtoolsProgressiveWebApps]という名前の新しいクラスの web アプリでは、サービスの担当**者**のためにオフラインで機能します。</span><span class="sxs-lookup"><span data-stu-id="495fa-151">A new class of web apps, named [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="495fa-152">この種類のアプリを構築しているときに、データ接続がないデバイスをすばやくシミュレートすると便利です。</span><span class="sxs-lookup"><span data-stu-id="495fa-152">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="495fa-153">[ **オンライン** ] ドロップダウンメニューを選択し、[ **プリセット**] で検索し、[ **オフライン** ] を選択して、オフラインネットワークエクスペリエンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="495fa-153">Select the **Online** dropdown menu, search under **Presets**, and select **Offline** to simulate an offline network experience.</span></span>  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-offline-dropdown.msft.png":::
   <span data-ttu-id="495fa-155">[ **オフライン** ] ドロップダウンメニュー</span><span class="sxs-lookup"><span data-stu-id="495fa-155">The **Offline** dropdown menu</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-156">低速ネットワーク接続のエミュレート</span><span class="sxs-lookup"><span data-stu-id="495fa-156">Emulate slow network connections</span></span>  

<span data-ttu-id="495fa-157">「 **オンライン** 」ドロップダウンメニューから、低速の3G、Fast 3g、その他の接続速度をエミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="495fa-157">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-throttling-menu.msft.png":::
   <span data-ttu-id="495fa-159">[ **調整** ] ドロップダウンメニュー</span><span class="sxs-lookup"><span data-stu-id="495fa-159">The **Throttling** dropdown menu</span></span>  
:::image-end:::  

<span data-ttu-id="495fa-160">低速の3G や Fast 3G など、さまざまなプリセットから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="495fa-160">You may select from different presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="495fa-161">また、[調整] メニューを開き、[**カスタム**追加] を選択して、独自のカスタムプリセットを追加することもでき  >  **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="495fa-161">You may also add your own custom presets by opening the Throttling menu and selecting **Custom** > **Add**.</span></span>  

<span data-ttu-id="495fa-162">DevTools は、調整が有効になっていることを通知するために、[ **ネットワーク** ] タブの横に警告アイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-162">DevTools displays a warning icon next to the **Network** tab to remind you that throttling is enabled.</span></span>  

#### <span data-ttu-id="495fa-163">ネットワークの状態のドロアーからの低速ネットワーク接続のエミュレート</span><span class="sxs-lookup"><span data-stu-id="495fa-163">Emulate slow network connections from the Network Conditions drawer</span></span>  

<span data-ttu-id="495fa-164">他の DevTools パネルでの作業中にネットワーク接続を調整したい場合は、ネットワーク条件の引き出しを使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-164">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="495fa-165">[ **ネットワーク条件** ] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="495fa-165">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="495fa-166">[ **調整** ] メニューから接続速度を選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-166">Select your connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="495fa-167">ブラウザーの cookie を手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="495fa-167">Manually clear browser cookies</span></span>  

<span data-ttu-id="495fa-168">ブラウザーの cookie をいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキストメニュー \ (右クリック \) を開き、[ **ブラウザ cookie のクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-168">To manually clear browser cookies at any time, open the contextual menu \(right-click\) anywhere in the Requests table and select **Clear Browser Cookies**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   <span data-ttu-id="495fa-170">[**ブラウザーのクリア cookie**の選択]</span><span class="sxs-lookup"><span data-stu-id="495fa-170">Selecting **Clear Browser Cookies**</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-171">ユーザーエージェントを上書きする</span><span class="sxs-lookup"><span data-stu-id="495fa-171">Override the user agent</span></span>  

<span data-ttu-id="495fa-172">ユーザーエージェントを手動で上書きするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-172">To manually override the user agent, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-173">[ **ネットワーク条件** ] ドローワを開きます。</span><span class="sxs-lookup"><span data-stu-id="495fa-173">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="495fa-174">**[自動] をオフに**します。</span><span class="sxs-lookup"><span data-stu-id="495fa-174">Uncheck **Select automatically**.</span></span>  
1.  <span data-ttu-id="495fa-175">メニューからユーザーエージェントオプションを選択するか、テキストボックスにユーザー設定のオプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="495fa-175">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <span data-ttu-id="495fa-176">フィルター要求</span><span class="sxs-lookup"><span data-stu-id="495fa-176">Filter requests</span></span>  

### <span data-ttu-id="495fa-177">プロパティによって要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="495fa-177">Filter requests by properties</span></span>  

<span data-ttu-id="495fa-178">[ **フィルター** ] テキストボックスを使用して、要求のドメインやサイズなどのプロパティによって要求をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="495fa-178">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="495fa-179">テキストボックスが表示されない場合は、[ **フィルター** ] ウィンドウが非表示になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="495fa-179">If the text box is not displayed, the **Filters** pane is probably hidden.</span></span>  
<span data-ttu-id="495fa-180">詳細については、「 [[フィルター] ウィンドウを非表示](#hide-the-filters-pane)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-180">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-filters-textbox.msft.png":::
   <span data-ttu-id="495fa-182">[ **フィルター** ] テキストボックス</span><span class="sxs-lookup"><span data-stu-id="495fa-182">The **Filter** text box</span></span>  
:::image-end:::  

<span data-ttu-id="495fa-183">各プロパティをスペースで区切ることで、複数のプロパティを同時に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="495fa-183">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="495fa-184">たとえば、 `mime-type:image/png larger-than:1K` 1 kb より大きいすべての PNGs を表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-184">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than 1 kilobyte.</span></span>  <span data-ttu-id="495fa-185">複数プロパティフィルターは、操作と同じです `AND` 。</span><span class="sxs-lookup"><span data-stu-id="495fa-185">The multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="495fa-186">操作は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="495fa-186">operations are currently not supported.</span></span>  

<span data-ttu-id="495fa-187">サポートされているプロパティの完全な一覧です。</span><span class="sxs-lookup"><span data-stu-id="495fa-187">The complete list of supported properties.</span></span>  

| <span data-ttu-id="495fa-188">プロパティ</span><span class="sxs-lookup"><span data-stu-id="495fa-188">Property</span></span> | <span data-ttu-id="495fa-189">詳細</span><span class="sxs-lookup"><span data-stu-id="495fa-189">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="495fa-190">指定したドメインのリソースのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-190">Only display resources from the specified domain.</span></span>  <span data-ttu-id="495fa-191">複数のドメインを含めるには、ワイルドカード文字 \ (\) を使用することができ `*` ます。</span><span class="sxs-lookup"><span data-stu-id="495fa-191">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="495fa-192">たとえば、 `*.com` で終わるすべてのドメイン名のリソースが表示され `.com` ます。</span><span class="sxs-lookup"><span data-stu-id="495fa-192">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="495fa-193">DevTools は、見つかったすべてのドメインのオートコンプリートのドロップダウンメニューに入力します。</span><span class="sxs-lookup"><span data-stu-id="495fa-193">DevTools populate the autocomplete dropdown menu with all of the domains that are found.</span></span> |  
| `has-response-header` | <span data-ttu-id="495fa-194">指定した HTTP 応答ヘッダーを含むリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-194">Displays the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="495fa-195">DevTools は、見つかったすべての応答ヘッダーのオートコンプリートのドロップダウンリストにデータを設定します。</span><span class="sxs-lookup"><span data-stu-id="495fa-195">DevTools populate the autocomplete dropdown with all of the response headers that are found.</span></span> |  
| `is` | <span data-ttu-id="495fa-196">`is:running`リソースを検索するために使用 `WebSocket` します。</span><span class="sxs-lookup"><span data-stu-id="495fa-196">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="495fa-197">指定したサイズよりも大きいリソースを、バイト単位で表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-197">Displays resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="495fa-198">値の設定 `1000` は、の値の設定に相当 `1k` します。</span><span class="sxs-lookup"><span data-stu-id="495fa-198">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="495fa-199">指定した HTTP メソッド型を経由して取得されたリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-199">Displays resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="495fa-200">DevTools は、検出されたすべての HTTP メソッドを使用して、ドロップダウンにデータを設定します。</span><span class="sxs-lookup"><span data-stu-id="495fa-200">DevTools populate the dropdown with all of the HTTP methods  that are found.</span></span> |  
| `mime-type` | <span data-ttu-id="495fa-201">指定した MIME の種類のリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-201">Displays resources of a specified MIME type.</span></span>  <span data-ttu-id="495fa-202">DevTools では、検出されたすべての MIME の種類がドロップダウンに設定されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-202">DevTools populate the dropdown with all MIME types  that are found.</span></span> |  
| `mixed-content` | <span data-ttu-id="495fa-203">すべての混合コンテンツリソース \ ( `mixed-content:all` \) を表示するか、現在 \ (\) を表示しているものだけを表示し `mixed-content:displayed` ます。</span><span class="sxs-lookup"><span data-stu-id="495fa-203">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="495fa-204">保護されていない HTTP \ ( `scheme:http` \) または保護された HTTPS \ (\) 経由で取得したリソース `scheme:https` を表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-204">Displays resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="495fa-205">指定した値と一致する属性を持つヘッダーが含まれているリソースを表示 `Set-Cookie` `Domain` します。</span><span class="sxs-lookup"><span data-stu-id="495fa-205">Displays resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="495fa-206">DevTools は、検出されたすべての cookie ドメインにオートコンプリートを設定します。</span><span class="sxs-lookup"><span data-stu-id="495fa-206">DevTools populate the autocomplete with all of the cookie domains that are found.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="495fa-207">指定した値と一致する名前のヘッダーが含まれているリソースを表示 `Set-Cookie` します。</span><span class="sxs-lookup"><span data-stu-id="495fa-207">Displays resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="495fa-208">DevTools は、検出されたすべての cookie 名でオートコンプリートを設定します。</span><span class="sxs-lookup"><span data-stu-id="495fa-208">DevTools populate the autocomplete with all of the cookie names that are found.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="495fa-209">指定された値と一致する値のヘッダーが含まれているリソースを表示 `Set-Cookie` します。</span><span class="sxs-lookup"><span data-stu-id="495fa-209">Displays resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="495fa-210">DevTools は、検出されたすべての cookie 値でオートコンプリートを設定します。</span><span class="sxs-lookup"><span data-stu-id="495fa-210">DevTools populate the autocomplete with all of the cookie values that are found.</span></span> |  
| `status-code` | <span data-ttu-id="495fa-211">特定の HTTP 状態コードに一致するリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-211">Displays resources that match the specific HTTP status code.</span></span>  <span data-ttu-id="495fa-212">DevTools は、検出されたすべての状態コードと共にオートコンプリートのドロップダウンメニューに入力します。</span><span class="sxs-lookup"><span data-stu-id="495fa-212">DevTools populates the autocomplete dropdown menu with all of the status codes that are found.</span></span> |  

### <span data-ttu-id="495fa-213">種類別に要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="495fa-213">Filter requests by type</span></span>  

<span data-ttu-id="495fa-214">要求の種類別に要求をフィルター処理するには、[ **ネットワーク** ] パネルで次のいずれかのボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-214">To filter requests by request type, select the one of the following buttons on the **Network** panel.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-215">XHR</span><span class="sxs-lookup"><span data-stu-id="495fa-215">XHR</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-216">.JS</span><span class="sxs-lookup"><span data-stu-id="495fa-216">JS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-217">CSS</span><span class="sxs-lookup"><span data-stu-id="495fa-217">CSS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-218">Img</span><span class="sxs-lookup"><span data-stu-id="495fa-218">Img</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-219">メディア</span><span class="sxs-lookup"><span data-stu-id="495fa-219">Media</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-220">フォント</span><span class="sxs-lookup"><span data-stu-id="495fa-220">Font</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-221">アドバイザー</span><span class="sxs-lookup"><span data-stu-id="495fa-221">Doc</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-222">WS-METADATA</span><span class="sxs-lookup"><span data-stu-id="495fa-222">WS</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-223">WebSocket.</span><span class="sxs-lookup"><span data-stu-id="495fa-223">WebSocket.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-224">ノート</span><span class="sxs-lookup"><span data-stu-id="495fa-224">Manifest</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-225">Other</span><span class="sxs-lookup"><span data-stu-id="495fa-225">Other</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-226">リストされていないその他の型。</span><span class="sxs-lookup"><span data-stu-id="495fa-226">Any other type not listed.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="495fa-227">ボタンが表示されない場合は、[ **フィルター** ] ウィンドウが非表示になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="495fa-227">If the buttons do not display, the **Filters** pane may be hidden.</span></span>  
<span data-ttu-id="495fa-228">詳細については、「 [[フィルター] ウィンドウを非表示](#hide-the-filters-pane)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-228">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="495fa-229">複数の種類のフィルターを同時に有効にするに `Control` は、\ (Windows \) または `Command` \ (macOS \) を保持し、を選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-229">To enable multiple type filters simultaneously, hold `Control` \(Windows\) or `Command` \(macOS\) and then select.</span></span>  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-type-filters.msft.png":::
   <span data-ttu-id="495fa-231">型フィルターを使用した JS、CSS、およびドキュメントのリソースの表示</span><span class="sxs-lookup"><span data-stu-id="495fa-231">Using the Type filters to display JS, CSS, and Document resources</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-232">時間に基づいて要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="495fa-232">Filter requests by time</span></span>  

<span data-ttu-id="495fa-233">[概要] ウィンドウで左または右にドラッグすると、その期間中にアクティブだった要求のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-233">Select and drag left or right on the Overview pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="495fa-234">フィルターは包含されています。</span><span class="sxs-lookup"><span data-stu-id="495fa-234">The filter is inclusive.</span></span>  <span data-ttu-id="495fa-235">強調表示された時間にアクティブだった要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-235">Any request that was active during the highlighted time is shown.</span></span>  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-overview-filter.msft.png":::
   <span data-ttu-id="495fa-237">300 ms で非アクティブになっていた要求をすべてフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="495fa-237">Filtering out any requests that were inactive around 300 ms</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-238">データ Url を非表示にする</span><span class="sxs-lookup"><span data-stu-id="495fa-238">Hide data URLs</span></span>  

<span data-ttu-id="495fa-239">[データ url][MDNHTTPDataURIs] は、他のドキュメントに埋め込まれた小さなファイルです。</span><span class="sxs-lookup"><span data-stu-id="495fa-239">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="495fa-240">で始まる要求テーブルに表示されるすべての要求 `data:` は、データの URL です。</span><span class="sxs-lookup"><span data-stu-id="495fa-240">Any request that displays in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="495fa-241">[ **データ url を非表示** にする] チェックボックスをオンにして要求を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="495fa-241">Check the **Hide data URLs** checkbox to hide the requests.</span></span>  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-hide-data-urls.msft.png":::
   <span data-ttu-id="495fa-243">[ **データ url を非表示** にする] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="495fa-243">The **Hide Data URLs** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="495fa-244">並べ替え要求</span><span class="sxs-lookup"><span data-stu-id="495fa-244">Sort requests</span></span>  

<span data-ttu-id="495fa-245">既定では、要求テーブルの要求は開始時刻によって並べ替えられますが、他の条件を使用してテーブルを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="495fa-245">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <span data-ttu-id="495fa-246">列で並べ替え</span><span class="sxs-lookup"><span data-stu-id="495fa-246">Sort by column</span></span>  

<span data-ttu-id="495fa-247">要求内の任意の列のヘッダーを選び、その列によって要求を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="495fa-247">Select the header of any column in the Requests to sort requests by that column.</span></span>  

### <span data-ttu-id="495fa-248">アクティビティ別の並べ替えフェーズ</span><span class="sxs-lookup"><span data-stu-id="495fa-248">Sort by activity phase</span></span>  

<span data-ttu-id="495fa-249">ウォーターフォールでのリクエストの並べ替え方法を変更するには、要求テーブルのヘッダーにカーソルを合わせて、コンテキストメニュー \ (右クリック \) を開き、 **ウォーターフォール**をポイントして、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-249">To change how the Waterfall sorts requests, hover on the header of the Requests table, open the contextual menu \(right-click\), hover over **Waterfall**, and select one of the following options.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-250">開始時刻</span><span class="sxs-lookup"><span data-stu-id="495fa-250">Start Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-251">最初に開始された要求は一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="495fa-251">The first request that was initiated is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-252">応答時間</span><span class="sxs-lookup"><span data-stu-id="495fa-252">Response Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-253">ダウンロードを開始した最初の要求は上部にあります。</span><span class="sxs-lookup"><span data-stu-id="495fa-253">The first request that started downloading is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-254">終了時刻</span><span class="sxs-lookup"><span data-stu-id="495fa-254">End Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-255">最初の要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="495fa-255">The first request that finished is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-256">合計期間</span><span class="sxs-lookup"><span data-stu-id="495fa-256">Total Duration</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-257">最短の接続設定と要求または応答を含む要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="495fa-257">The request with the shortest connection settings and request or response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-258">遅延</span><span class="sxs-lookup"><span data-stu-id="495fa-258">Latency</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-259">応答の最短時間を待っている要求が一番上にあります。</span><span class="sxs-lookup"><span data-stu-id="495fa-259">The request that waited the shortest time for a response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="495fa-260">これらの説明は、それぞれのオプションが最短から最長の順にランク付けされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="495fa-260">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="495fa-261">[ **ウォーターフォール** ] 列のヘッダーを選択すると、順序が逆になります。</span><span class="sxs-lookup"><span data-stu-id="495fa-261">Selecting the header of the **Waterfall** column reverses the order.</span></span>  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   <span data-ttu-id="495fa-263">ウォーターフォールを合計期間で並べ替える (各バーの明るい部分は待機時間で、暗い部分はバイトのダウンロードにかかる時間です)。</span><span class="sxs-lookup"><span data-stu-id="495fa-263">Sorting the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
:::image-end:::  

## <span data-ttu-id="495fa-264">分析要求</span><span class="sxs-lookup"><span data-stu-id="495fa-264">Analyze requests</span></span>  

<span data-ttu-id="495fa-265">DevTools が開いている限り、すべての要求がネットワークパネルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-265">So long as DevTools are open, it logs all requests in the Network panel.</span></span>  
<span data-ttu-id="495fa-266">[ネットワーク] パネルを使用して要求を分析します。</span><span class="sxs-lookup"><span data-stu-id="495fa-266">Use the Network panel to analyze requests.</span></span>  

### <span data-ttu-id="495fa-267">要求のログを表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-267">View a log of requests</span></span>  

<span data-ttu-id="495fa-268">[要求] テーブルを使って、DevTools が開いている間に行われたすべての要求のログを表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-268">Use the Requests table to view a log of all requests made while DevTools have been open.</span></span>  <span data-ttu-id="495fa-269">要求を選択またはマウスでポイントすると、各項目の詳細情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-269">Selecting or hovering over requests reveals more information about each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-table.msft.png":::
   <span data-ttu-id="495fa-271">要求テーブル</span><span class="sxs-lookup"><span data-stu-id="495fa-271">The Requests table</span></span>  
:::image-end:::  

<span data-ttu-id="495fa-272">要求テーブルには、既定で次の列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-272">The Requests table displays the following columns by default.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-273">名前</span><span class="sxs-lookup"><span data-stu-id="495fa-273">Name</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-274">リソースのファイル名または識別子。</span><span class="sxs-lookup"><span data-stu-id="495fa-274">The filename of, or an identifier for, the resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-275">ステータス</span><span class="sxs-lookup"><span data-stu-id="495fa-275">Status</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-276">HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="495fa-276">The HTTP status code.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-277">型</span><span class="sxs-lookup"><span data-stu-id="495fa-277">Type</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-278">要求されたリソースの MIME の種類。</span><span class="sxs-lookup"><span data-stu-id="495fa-278">The MIME type of the requested resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-279">・</span><span class="sxs-lookup"><span data-stu-id="495fa-279">Initiator</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-280">次のオブジェクトまたはプロセスが要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="495fa-280">The following objects or processes initiate requests.</span></span>  
      
      *   <span data-ttu-id="495fa-281">**パーサー**  Microsoft Edge の HTML パーサー。</span><span class="sxs-lookup"><span data-stu-id="495fa-281">**Parser**  The HTML parser for Microsoft Edge.</span></span>  
      *   <span data-ttu-id="495fa-282">**Redirect**  HTTP リダイレクト。</span><span class="sxs-lookup"><span data-stu-id="495fa-282">**Redirect**  An HTTP redirect.</span></span>  
      *   <span data-ttu-id="495fa-283">**スクリプト**  JavaScript 関数。</span><span class="sxs-lookup"><span data-stu-id="495fa-283">**Script**  A JavaScript function.</span></span>  
      *   <span data-ttu-id="495fa-284">**その他**  リンクを使用してページに移動したり、アドレスバーに URL を入力したりするなど、他のプロセスまたはアクション。</span><span class="sxs-lookup"><span data-stu-id="495fa-284">**Other**  Some other process or action, such as navigating to a page using a link or entering a URL in the address bar.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-285">Size</span><span class="sxs-lookup"><span data-stu-id="495fa-285">Size</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-286">サーバーによって配信された、返信ヘッダーと応答本文の合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="495fa-286">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-287">時間</span><span class="sxs-lookup"><span data-stu-id="495fa-287">Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-288">要求の開始から、応答の最後のバイトの受領までの合計時間。</span><span class="sxs-lookup"><span data-stu-id="495fa-288">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="495fa-289">ウォーターフォール図</span><span class="sxs-lookup"><span data-stu-id="495fa-289">Waterfall</span></span>](#view-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-290">各要求のアクティビティの視覚的な分類。</span><span class="sxs-lookup"><span data-stu-id="495fa-290">A visual breakdown of the activity for each request.</span></span>  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="495fa-291">列を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="495fa-291">Add or remove columns</span></span>  

<span data-ttu-id="495fa-292">要求テーブルのヘッダーにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、表示または非表示にするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-292">Hover on the header of the Requests table, open the contextual menu \(right-click\), and select an option to hide or show it.</span></span>  <span data-ttu-id="495fa-293">現在表示されているオプションは各項目の横にチェックマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="495fa-293">Currently displayed options have checkmarks next to each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-add-column.msft.png":::
   <span data-ttu-id="495fa-295">要求テーブルへの列の追加</span><span class="sxs-lookup"><span data-stu-id="495fa-295">Adding a column to the Requests table</span></span>  
:::image-end:::  

#### <span data-ttu-id="495fa-296">カスタム列を追加する</span><span class="sxs-lookup"><span data-stu-id="495fa-296">Add custom columns</span></span>  

<span data-ttu-id="495fa-297">要求テーブルにカスタム列を追加するには、要求テーブルのヘッダーにマウスポインターを合わせて、コンテキストメニューを開き (\ を右クリック \)、[**応答ヘッダー**で  >  **ヘッダー列を管理**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-297">To add a custom column to the Requests table, hover on the header of the Requests table, open the contextual menu \(right-click\), and select **Response Headers** > **Manage Header Columns**.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-add-custom.msft.png":::
   <span data-ttu-id="495fa-299">要求テーブルへのカスタム列の追加</span><span class="sxs-lookup"><span data-stu-id="495fa-299">Adding a custom column to the Requests table</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-300">要求のタイミングの関係を表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-300">View the timing relationship of requests</span></span>  

<span data-ttu-id="495fa-301">ウォーターフォールを使用して、要求のタイミングの関係を表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-301">Use the Waterfall to view the timing relationships of requests.</span></span>  
<span data-ttu-id="495fa-302">ウォーターフォールの既定の組織では、要求の開始時刻が使用されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-302">The default organization of the Waterfall uses the start time of the requests.</span></span>  
<span data-ttu-id="495fa-303">そのため、左から右への要求よりも早く開始されていた要求は、その前から始まります。</span><span class="sxs-lookup"><span data-stu-id="495fa-303">So, requests that are farther to the left started earlier than the requests that are farther to the right.</span></span>  

<span data-ttu-id="495fa-304">ウォーターフォールのさまざまな並べ替え方法を確認するには、[ [アクティビティ別に並べ替え] フェーズ](#sort-by-activity-phase)に移動します。</span><span class="sxs-lookup"><span data-stu-id="495fa-304">To review the different ways that you may sort the Waterfall, navigate to [Sort by activity phase](#sort-by-activity-phase).</span></span>  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-waterfall.msft.png":::
   <span data-ttu-id="495fa-306">[ **要求** ] ウィンドウの [ウォーターフォール] 列</span><span class="sxs-lookup"><span data-stu-id="495fa-306">The Waterfall column of the **Requests** pane</span></span>  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To view the frames of a WebSocket connection, use the following steps.  

1.  Select the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Select the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-select the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-frames.msft.png":::
   The **Frames** tab  
:::image-end:::  
-->

<!--The table contains the following three columns.  

*   **Data**.  The message payload.  If the message is plain text, it is displayed here.  For binary opcodes, this column displays the name and code of the opcode.  The following opcodes are supported: Continuation Frame, Binary Frame, Connection Close Frame, Ping Frame, and Pong Frame.  
*   **Length**.  The length of the message payload, in bytes.  
*   **Time**.  The time when the message was received or sent.  -->

<!--Messages are color-coded according to each type.  

*   Outgoing text messages are light-green.  
*   Incoming text messages are white.  
*   WebSocket opcodes are light-yellow.  
*   Errors are light-red.  -->

### <span data-ttu-id="495fa-307">応答本文のプレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-307">View a preview of a response body</span></span>  

<span data-ttu-id="495fa-308">応答本文のプレビューを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-308">To view a preview of a response body, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-309">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-309">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="495fa-310">[ **プレビュー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-310">Select the **Preview** tab.</span></span>  

<span data-ttu-id="495fa-311">このタブはほとんどの場合、画像を表示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="495fa-311">This tab is mostly useful for viewing images.</span></span>  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-resources-preview.msft.png":::
   <span data-ttu-id="495fa-313">[ **プレビュー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="495fa-313">The **Preview** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-314">応答本文を表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-314">View a response body</span></span>  

<span data-ttu-id="495fa-315">要求に対する応答の本文を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-315">To view the response body to a request, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-316">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-316">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="495fa-317">[ **応答** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-317">Select the **Response** tab.</span></span>  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-resources-response.msft.png":::
   <span data-ttu-id="495fa-319">[ **応答** ] タブ</span><span class="sxs-lookup"><span data-stu-id="495fa-319">The **Response** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-320">HTTP ヘッダーの表示</span><span class="sxs-lookup"><span data-stu-id="495fa-320">View HTTP headers</span></span>  

<span data-ttu-id="495fa-321">要求に関する HTTP ヘッダーデータを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-321">To view HTTP header data about a request, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-322">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-322">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="495fa-323">[ **ヘッダー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-323">Select the **Headers** tab.</span></span>  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-resources-headers.msft.png":::
   <span data-ttu-id="495fa-325">[ **ヘッダー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="495fa-325">The **Headers** tab</span></span>  
:::image-end:::  

#### <span data-ttu-id="495fa-326">HTTP ヘッダーソースの表示</span><span class="sxs-lookup"><span data-stu-id="495fa-326">View HTTP header source</span></span>  

<span data-ttu-id="495fa-327">既定では、[ヘッダー] タブにはヘッダーの名前がアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-327">By default, the Headers tab shows header names alphabetically.</span></span>  <span data-ttu-id="495fa-328">受け取った順序で HTTP ヘッダーの名前を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-328">To view the HTTP header names in the order received, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-329">興味のある要求の [ **ヘッダー** ] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="495fa-329">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="495fa-330">詳細については、「 [HTTP ヘッダーを表示](#view-http-headers)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-330">For more information, navigate to [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="495fa-331">[**要求ヘッダー** ] または [**応答ヘッダー** ] セクションの横にある [**ソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-331">Select **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <span data-ttu-id="495fa-332">クエリ文字列パラメーターの表示</span><span class="sxs-lookup"><span data-stu-id="495fa-332">View query string parameters</span></span>  

<span data-ttu-id="495fa-333">人間が読める形式で URL のクエリ文字列パラメーターを表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="495fa-333">To view the query string parameters of a URL in a human-readable format, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-334">興味のある要求の [ **ヘッダー** ] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="495fa-334">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="495fa-335">詳細については、「 [HTTP ヘッダーを表示](#view-http-headers)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-335">For more information, navigate to [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="495fa-336">[ **クエリ文字列パラメーター** ] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="495fa-336">Go to the **Query String Parameters** section.</span></span>  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   <span data-ttu-id="495fa-338">[ **クエリ文字列パラメーター** ] セクション</span><span class="sxs-lookup"><span data-stu-id="495fa-338">The **Query String Parameters** section</span></span>  
:::image-end:::  

#### <span data-ttu-id="495fa-339">クエリ文字列パラメーターソースの表示</span><span class="sxs-lookup"><span data-stu-id="495fa-339">View query string parameters source</span></span>  

<span data-ttu-id="495fa-340">要求のクエリ文字列のパラメーターソースを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-340">To view the query string parameter source of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-341">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="495fa-341">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="495fa-342">詳細については、「 [クエリ文字列パラメーターを表示](#view-query-string-parameters)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-342">For more information, navigate to [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="495fa-343">[ **ソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-343">Select **view source**.</span></span>  

#### <span data-ttu-id="495fa-344">URL 形式でエンコードされたクエリ文字列パラメーターの表示</span><span class="sxs-lookup"><span data-stu-id="495fa-344">View URL-encoded query string parameters</span></span>  

<span data-ttu-id="495fa-345">人間が読める形式でクエリ文字列パラメーターを表示するには、エンコードが保持されている場合は、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-345">To view query string parameters in a human-readable format, but with encodings preserved, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-346">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="495fa-346">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="495fa-347">詳細については、「 [クエリ文字列パラメーターを表示](#view-query-string-parameters)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-347">For more information, navigate to [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="495fa-348">[ **表示 URL をエンコード**した] を選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-348">Select **view URL encoded**.</span></span>  

### <span data-ttu-id="495fa-349">Cookie の表示</span><span class="sxs-lookup"><span data-stu-id="495fa-349">View cookies</span></span>  

<span data-ttu-id="495fa-350">要求の HTTP ヘッダーで送信された cookie を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="495fa-350">To view the cookies sent in the HTTP header of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-351">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-351">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="495fa-352">[ **Cookies** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-352">Select the **Cookies** tab.</span></span>  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-resources-cookies.msft.png":::
   <span data-ttu-id="495fa-354">[Cookie] タブ</span><span class="sxs-lookup"><span data-stu-id="495fa-354">The Cookies tab</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-355">要求のタイミングのブレークダウンを表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-355">View the timing breakdown of a request</span></span>  

<span data-ttu-id="495fa-356">要求のタイミングの詳細を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-356">To view the timing breakdown of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="495fa-357">要求の URL を要求テーブルの [ **名前** ] 列で選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-357">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="495fa-358">[ **タイミング** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-358">Select the **Timing** tab.</span></span>  

<span data-ttu-id="495fa-359">データにすばやくアクセスする方法については、「 [タイミングのブレークダウンのプレビュー](#preview-a-timing-breakdown)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-359">For a faster way to access the data, navigate to [Preview a timing breakdown](#preview-a-timing-breakdown).</span></span>  

<span data-ttu-id="495fa-360">[ **タイミング** ] タブに表示される可能性がある各フェーズについて詳しくは、「 [タイミングのブレークダウンフェーズ](#timing-breakdown-phases-explained)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-360">For more information about each of the phases that may be displayed in the **Timing** tab, navigate to [Timing breakdown phases explained](#timing-breakdown-phases-explained).</span></span>  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-resources-timing.msft.png":::
   <span data-ttu-id="495fa-362">[ **タイミング** ] タブ</span><span class="sxs-lookup"><span data-stu-id="495fa-362">The **Timing** tab</span></span>  
:::image-end:::  

<span data-ttu-id="495fa-363">各フェーズに関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="495fa-363">More information about each of the phases.</span></span>  

<span data-ttu-id="495fa-364">ビューへのアクセスの詳細については、「 [タイミングのブレークを表示](#view-the-timing-breakdown-of-a-request)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-364">For more information about accessing the view, navigate to [View timing breakdown](#view-the-timing-breakdown-of-a-request).</span></span>  

#### <span data-ttu-id="495fa-365">タイミングの内訳をプレビューする</span><span class="sxs-lookup"><span data-stu-id="495fa-365">Preview a timing breakdown</span></span>  

<span data-ttu-id="495fa-366">要求のタイミングの内訳のプレビューを表示するには、要求テーブルの [ **ウォーターフォール** ] 列で、要求のエントリをポイントします。</span><span class="sxs-lookup"><span data-stu-id="495fa-366">To view a preview of the timing breakdown of a request, in the **Waterfall** column of the Requests table, hover on the entry for the request.</span></span>  

<span data-ttu-id="495fa-367">ホバーしないでデータにアクセスする方法の詳細については、「 [要求のタイミングの内訳を表示](#view-the-timing-breakdown-of-a-request)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-367">For more information about how to access the data without hovering, navigate to [View the timing breakdown of a request](#view-the-timing-breakdown-of-a-request).</span></span>  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   <span data-ttu-id="495fa-369">要求のタイミングのブレークダウンのプレビュー</span><span class="sxs-lookup"><span data-stu-id="495fa-369">Previewing the timing breakdown of a request</span></span>  
:::image-end:::  

#### <span data-ttu-id="495fa-370">タイミングのブレークフェーズについて</span><span class="sxs-lookup"><span data-stu-id="495fa-370">Timing breakdown phases explained</span></span>  

<span data-ttu-id="495fa-371">[ **タイミング** ] タブに表示される可能性のある各フェーズについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="495fa-371">More information about each of the phases that may display in the **Timing** tab.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-372">キュー</span><span class="sxs-lookup"><span data-stu-id="495fa-372">Queueing</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-373">ブラウザーは、次のいずれかの条件が満たされた場合に要求を待ちます。</span><span class="sxs-lookup"><span data-stu-id="495fa-373">The browser queues requests when any of the following are true.</span></span>  
      *   <span data-ttu-id="495fa-374">優先度の高い要求が存在します。</span><span class="sxs-lookup"><span data-stu-id="495fa-374">Higher priority requests exist.</span></span>  
      *   <span data-ttu-id="495fa-375">同じ起点 (上限) に対して6つの TCP 接続が開かれます。</span><span class="sxs-lookup"><span data-stu-id="495fa-375">Six TCP connections are open for the same origin, which is the limit.</span></span>  <span data-ttu-id="495fa-376">HTTP/1.0 および HTTP/1.1 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-376">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
      *   <span data-ttu-id="495fa-377">ブラウザーは、ディスクキャッシュの領域を一時的に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="495fa-377">The browser is briefly allocating space in the disk cache.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-378">停止</span><span class="sxs-lookup"><span data-stu-id="495fa-378">Stalled</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-379">**キュー**に記載されている理由により、要求は停止します。</span><span class="sxs-lookup"><span data-stu-id="495fa-379">The request is stalled for any of the reasons described in **Queueing**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-380">DNS 参照</span><span class="sxs-lookup"><span data-stu-id="495fa-380">DNS Lookup</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-381">ブラウザーが要求の IP アドレスを解決しています。</span><span class="sxs-lookup"><span data-stu-id="495fa-381">The browser is resolving the IP address for the request.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-382">初期接続</span><span class="sxs-lookup"><span data-stu-id="495fa-382">Initial connection</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-383">ブラウザーは、TCP ハンドシェイク、TCP 再試行、セキュリティで保護されたソケットレイヤーのネゴシエーションを含む接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="495fa-383">The browser establishes a connection including TCP handshakes, TCP retries, and negotiates a Secure Socket Layer.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-384">プロキシネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="495fa-384">Proxy negotiation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-385">ブラウザーは、要求を [プロキシサーバー][WikiProxyServer]とネゴシエートしています。</span><span class="sxs-lookup"><span data-stu-id="495fa-385">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-386">送信要求</span><span class="sxs-lookup"><span data-stu-id="495fa-386">Request sent</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-387">要求が送信されています。</span><span class="sxs-lookup"><span data-stu-id="495fa-387">The request is being sent.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-388">ServiceWorker の準備</span><span class="sxs-lookup"><span data-stu-id="495fa-388">ServiceWorker Preparation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-389">ブラウザーがサービスワーカーを開始しています。</span><span class="sxs-lookup"><span data-stu-id="495fa-389">The browser is starting the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-390">ServiceWorker へのリクエスト</span><span class="sxs-lookup"><span data-stu-id="495fa-390">Request to ServiceWorker</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-391">要求がサービスワーカーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-391">The request is being sent to the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-392">待機中 \ (TTFB \)</span><span class="sxs-lookup"><span data-stu-id="495fa-392">Waiting \(TTFB\)</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-393">ブラウザーは、応答の最初のバイトを待機しています。</span><span class="sxs-lookup"><span data-stu-id="495fa-393">The browser is waiting for the first byte of a response.</span></span>  <span data-ttu-id="495fa-394">TTFB は、最初のバイトまでの時間を表します。</span><span class="sxs-lookup"><span data-stu-id="495fa-394">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="495fa-395">このタイミングには、待機時間のラウンドトリップの1つと、サーバーが応答の準備に費やした時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="495fa-395">This timing includes one round trip of latency and the time the server took to prepare the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-396">コンテンツのダウンロード</span><span class="sxs-lookup"><span data-stu-id="495fa-396">Content Download</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-397">ブラウザーが応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="495fa-397">The browser is receiving the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-398">プッシュ受信</span><span class="sxs-lookup"><span data-stu-id="495fa-398">Receiving Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-399">ブラウザーが、HTTP/2 Server プッシュ経由でこの応答のデータを受信しています。</span><span class="sxs-lookup"><span data-stu-id="495fa-399">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-400">プッシュの読み取り</span><span class="sxs-lookup"><span data-stu-id="495fa-400">Reading Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-401">ブラウザーは、前に受信したローカルデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="495fa-401">The browser is reading the local data previously received.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="495fa-402">イニシエーターと依存関係を表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-402">View initiators and dependencies</span></span>  

<span data-ttu-id="495fa-403">要求のイニシエーターと依存関係を表示するには、[ `Shift` 要求] テーブルの要求をポイントしたままにします。</span><span class="sxs-lookup"><span data-stu-id="495fa-403">To view the initiators and dependencies of a request, hold `Shift`and hover over the request in the Requests table.</span></span>  <span data-ttu-id="495fa-404">DevTools の色: イニシエーターは緑で表示され、依存関係は赤で示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-404">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   <span data-ttu-id="495fa-406">要求のイニシエーターと依存関係の表示</span><span class="sxs-lookup"><span data-stu-id="495fa-406">Viewing the initiators and dependencies of a request</span></span>  
:::image-end:::  

<span data-ttu-id="495fa-407">要求テーブルが時系列で並べ替えられている場合、その行の上にカーソルを置くと、その行の前の行に緑色の要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-407">When the Requests table is ordered chronologically, if you hover on a line, the line preceding it displays a green request.</span></span>  <span data-ttu-id="495fa-408">緑の要求は、依存関係のイニシエーターです。</span><span class="sxs-lookup"><span data-stu-id="495fa-408">The green request is the initiator of the dependency.</span></span>  <span data-ttu-id="495fa-409">この行の前に別の緑の要求が表示されている場合は、その上位の要求がイニシエーターのイニシエーターになります。</span><span class="sxs-lookup"><span data-stu-id="495fa-409">If another green request is displayed on the line before that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="495fa-410">などなど。</span><span class="sxs-lookup"><span data-stu-id="495fa-410">And so on.</span></span>  

### <span data-ttu-id="495fa-411">読み込みイベントを表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-411">View load events</span></span>  

<span data-ttu-id="495fa-412">DevTools は、 `DOMContentLoaded` [ `load` ネットワーク] パネル上の複数の場所にある [イベントのタイミング] を表示します。</span><span class="sxs-lookup"><span data-stu-id="495fa-412">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the Network panel.</span></span>  <span data-ttu-id="495fa-413">`DOMContentLoaded`イベントは青色で色分けされ、 `load` イベントは赤になります。</span><span class="sxs-lookup"><span data-stu-id="495fa-413">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-load-events.msft.png":::
   <span data-ttu-id="495fa-415">[ `DOMContentLoaded` `load` ネットワーク] パネルでのイベントとイベントの場所</span><span class="sxs-lookup"><span data-stu-id="495fa-415">The locations of the `DOMContentLoaded` and `load` events on the Network panel</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-416">要求の合計数を表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-416">View the total number of requests</span></span>  

<span data-ttu-id="495fa-417">[ネットワーク] パネルの下部にある [概要] ウィンドウに、要求の合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-417">The total number of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="495fa-418">この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="495fa-418">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="495fa-419">DevTools が開かれる前に他の要求が発生した場合、これらの要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="495fa-419">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-total-requests.msft.png":::
   <span data-ttu-id="495fa-421">DevTools が開かれてからの要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="495fa-421">The total number of requests since DevTools were opened</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-422">ダウンロードの合計サイズを表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-422">View the total download size</span></span>  

<span data-ttu-id="495fa-423">要求の合計ダウンロードサイズが、[ネットワーク] パネルの下部にある [概要] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-423">The total download size of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="495fa-424">この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="495fa-424">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="495fa-425">DevTools が開かれる前に、他の要求が発生した場合、以前の要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="495fa-425">If other requests occurred before DevTools was opened, the previous requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-total-download-size.msft.png":::
   <span data-ttu-id="495fa-427">リクエストのダウンロード合計サイズ</span><span class="sxs-lookup"><span data-stu-id="495fa-427">The total download size of requests</span></span>  
:::image-end:::  

<span data-ttu-id="495fa-428">サイズの大きいリソースがどのように圧縮されているかを確認するには、[ [リソースの未圧縮サイズ](#view-the-uncompressed-size-of-a-resource)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495fa-428">To verify how large resources are after the browser uncompresses each item, navigate to [View the uncompressed size of a resource](#view-the-uncompressed-size-of-a-resource).</span></span>  

### <span data-ttu-id="495fa-429">要求の原因となったスタックトレースを表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-429">View the stack trace that caused a request</span></span>  

<span data-ttu-id="495fa-430">JavaScript ステートメントでリソースを要求した後、[ **イニシエーター** ] 列をマウスでポイントすると、要求までのスタックトレースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-430">After a JavaScript statement requests a resource, hover over the **Initiator** column to view the stack trace leading up to the request.</span></span>  

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

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   <span data-ttu-id="495fa-432">リソース要求までのスタックトレース</span><span class="sxs-lookup"><span data-stu-id="495fa-432">The stack trace leading up to a resource request</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-433">リソースの未圧縮サイズを表示する</span><span class="sxs-lookup"><span data-stu-id="495fa-433">View the uncompressed size of a resource</span></span>  

<span data-ttu-id="495fa-434">[ **大きな要求行を使用する** ] チェックボックスをオンにして、[ **サイズ** ] 列の下の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="495fa-434">Select the **Use large request rows** checkbox and then look at the bottom value of the **Size** column.</span></span>  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   <span data-ttu-id="495fa-436">圧縮されていないリソースの例 \ (ネットワーク経由で送信されたファイルの圧縮サイズ、圧縮されてい `jquery-3.3.1.min.js` ない `29.9 KB` サイズなど `84.9 KB` )</span><span class="sxs-lookup"><span data-stu-id="495fa-436">An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
:::image-end:::  

## <span data-ttu-id="495fa-437">要求データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="495fa-437">Export requests data</span></span>  

### <span data-ttu-id="495fa-438">すべてのネットワーク要求を HAR ファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="495fa-438">Save all network requests to a HAR file</span></span>  

<span data-ttu-id="495fa-439">すべてのネットワーク要求を HAR ファイルに保存するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="495fa-439">To save all network requests to a HAR file, complete the following steps.</span></span>  

1.  <span data-ttu-id="495fa-440">要求テーブル内の任意の要求にマウスポインターを合わせ、コンテキストメニューを開きます (\ を右クリックします)。</span><span class="sxs-lookup"><span data-stu-id="495fa-440">Hover on any request in the Requests table and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="495fa-441">[ **コンテンツを含む HAR として保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-441">Select **Save as HAR with Content**.</span></span>  <span data-ttu-id="495fa-442">DevTools は、HAR ファイルに対して DevTools を開いた後に発生した要求をすべて保存します。</span><span class="sxs-lookup"><span data-stu-id="495fa-442">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="495fa-443">要求をフィルター処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="495fa-443">You are not able to filter requests.</span></span>  <span data-ttu-id="495fa-444">1つのリクエストを保存することもできません。</span><span class="sxs-lookup"><span data-stu-id="495fa-444">You are also not able to save a single request.</span></span>  

<span data-ttu-id="495fa-445">HAR ファイルを保存すると、そのファイルを分析用の DevTools にインポートして戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="495fa-445">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="495fa-446">HAR ファイルを [要求] テーブルにドラッグアンドドロップするだけです。</span><span class="sxs-lookup"><span data-stu-id="495fa-446">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   <span data-ttu-id="495fa-448">[**コンテンツを含む HAR として保存] を**選ぶ</span><span class="sxs-lookup"><span data-stu-id="495fa-448">Selecting **Save as HAR with Content**</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-449">1つ以上の要求をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="495fa-449">Copy one or more requests to the clipboard</span></span>  

<span data-ttu-id="495fa-450">要求テーブルの [ **名前** ] 列で、要求をポイントし、コンテキストメニューを開きます。 \ (右クリック \)、[ **コピー**] をポイントして、次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="495fa-450">Under the **Name** column of the Requests table, hover on a request, open the contextual menu \(right-click\), hover over **Copy**, and select one of the following options.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-451">リンクアドレスをコピーする</span><span class="sxs-lookup"><span data-stu-id="495fa-451">Copy Link Address</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-452">要求の URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="495fa-452">Copy the URL of the request to the clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-453">返信のコピー</span><span class="sxs-lookup"><span data-stu-id="495fa-453">Copy Response</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-454">応答本文をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="495fa-454">Copy the response body to the clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-455">フェッチとしてコピー</span><span class="sxs-lookup"><span data-stu-id="495fa-455">Copy as Fetch</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-456">CURL としてコピー</span><span class="sxs-lookup"><span data-stu-id="495fa-456">Copy as cURL</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-457">CURL コマンドとして要求をコピーします。</span><span class="sxs-lookup"><span data-stu-id="495fa-457">Copy the request as a cURL command.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-458">すべてをフェッチとしてコピーする</span><span class="sxs-lookup"><span data-stu-id="495fa-458">Copy All as Fetch</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-459">CURL としてすべてコピー</span><span class="sxs-lookup"><span data-stu-id="495fa-459">Copy All as cURL</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-460">すべての要求を cURL コマンドのチェーンとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="495fa-460">Copy all requests as a chain of cURL commands.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="495fa-461">すべてを HAR としてコピーする</span><span class="sxs-lookup"><span data-stu-id="495fa-461">Copy All as HAR</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="495fa-462">すべての要求を HAR データとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="495fa-462">Copy all requests as HAR data.</span></span>  
   :::column-end:::
:::row-end:::  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-copy-response.msft.png":::
   <span data-ttu-id="495fa-464">[**返信のコピー** ] の選択</span><span class="sxs-lookup"><span data-stu-id="495fa-464">Selecting **Copy Response**</span></span>  
:::image-end:::  

## <span data-ttu-id="495fa-465">[ネットワーク] パネルのレイアウトを変更する</span><span class="sxs-lookup"><span data-stu-id="495fa-465">Change the layout of the Network panel</span></span>  

<span data-ttu-id="495fa-466">ネットワークパネル UI のセクションを展開したり折りたたんだりして、重要な情報を強調することができます。</span><span class="sxs-lookup"><span data-stu-id="495fa-466">You may expand or collapse sections of the Network panel UI to focus important information.</span></span>  

### <span data-ttu-id="495fa-467">[フィルター] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="495fa-467">Hide the Filters pane</span></span>  

<span data-ttu-id="495fa-468">既定では、DevTools によって [ **フィルター] ウィンドウ**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-468">By default, DevTools show the **Filters pane**.</span></span>  
<span data-ttu-id="495fa-469">**Filter** ![ ][ImageFilterIcon] 非表示にするには、[フィルター \] (フィルター \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="495fa-469">Select **Filter** \(![Filter][ImageFilterIcon]\) to hide it.</span></span>  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   <span data-ttu-id="495fa-471">[フィルターの非表示] ボタン</span><span class="sxs-lookup"><span data-stu-id="495fa-471">The Hide Filters button</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-472">大きな要求行を使用する</span><span class="sxs-lookup"><span data-stu-id="495fa-472">Use large request rows</span></span>  

<span data-ttu-id="495fa-473">ネットワーク要求テーブルにより多くの空白が必要な場合は、大きな行を使用します。</span><span class="sxs-lookup"><span data-stu-id="495fa-473">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="495fa-474">列によっては、大きな行を使用するときに、さらに多くの情報が表示される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="495fa-474">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="495fa-475">たとえば、 **Size** 列の下の値は、要求の非圧縮サイズです。</span><span class="sxs-lookup"><span data-stu-id="495fa-475">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   <span data-ttu-id="495fa-477">**要求ウィンドウの**大きな要求行の例</span><span class="sxs-lookup"><span data-stu-id="495fa-477">An example of large request rows in the **Requests** pane</span></span>  
:::image-end:::  

<span data-ttu-id="495fa-478">大きな行を有効にするには、[ **大きな要求行を使用** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="495fa-478">Select the **Use large request rows** checkbox to enable large rows.</span></span>  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   <span data-ttu-id="495fa-480">[ **大きな要求行の使用** ] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="495fa-480">The **Use large request rows** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="495fa-481">[概要] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="495fa-481">Hide the Overview pane</span></span>  

<span data-ttu-id="495fa-482">既定では、DevTools によって [ **概要] ウィンドウ**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-482">By default, DevTools show the **Overview pane**.</span></span>  <span data-ttu-id="495fa-483">[ **概要の表示** ] チェックボックスをオフにして非表示にします。</span><span class="sxs-lookup"><span data-stu-id="495fa-483">Deselect the **Show Overview** checkbox to hide it.</span></span>  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   <span data-ttu-id="495fa-485">[ **概要の表示** ] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="495fa-485">The **Show Overview** checkbox</span></span>  
:::image-end:::  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps.md "プログレッシブ Web アプリのデバッグ |Microsoft ドキュメント"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "データ Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "プロキシサーバー-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="495fa-489">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="495fa-489">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="495fa-490">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="495fa-490">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="495fa-492">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="495fa-492">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
