---
description: DevTools ネットワーク パネルMicrosoft Edgeの包括的な参照。
title: ネットワーク分析リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bdb1145e7ee8ed7865b68f9fd632c4b1a30007e9
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564834"
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
# <a name="network-analysis-reference"></a><span data-ttu-id="c9f1c-104">ネットワーク分析リファレンス</span><span class="sxs-lookup"><span data-stu-id="c9f1c-104">Network Analysis reference</span></span>  

<span data-ttu-id="c9f1c-105">DevTools ネットワーク分析機能に関するこの包括的な参照で、ページの読み込みMicrosoft Edge新しい方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-105">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

## <a name="record-network-requests"></a><span data-ttu-id="c9f1c-106">ネットワーク要求を記録する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-106">Record network requests</span></span>  

<span data-ttu-id="c9f1c-107">既定では、DevTools が開いている限り、DevTools はネットワーク ツール内のすべてのネットワーク要求を記録します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c9f1c-107">By default, DevTools record all network requests in the **Network** tool, so long as DevTools is open.</span></span>  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-panel.msft.png":::
   <span data-ttu-id="c9f1c-109">ネットワーク**ツール**</span><span class="sxs-lookup"><span data-stu-id="c9f1c-109">The **Network** tool</span></span>  
:::image-end:::  

### <a name="stop-recording-network-requests"></a><span data-ttu-id="c9f1c-110">ネットワーク要求の記録を停止する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-110">Stop recording network requests</span></span>  

<span data-ttu-id="c9f1c-111">要求の記録を停止するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-111">To stop recording requests, complete the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-112">ネットワーク ツール **で、[** ネットワーク ログの記録 **を停止する** ] \( [ネットワーク ログの記録 ![ を停止する ](../media/record-on-icon.msft.png) ] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-112">On the **Network** tool, choose **Stop recording network log** \(![Stop recording network log](../media/record-on-icon.msft.png)\).</span></span>  <span data-ttu-id="c9f1c-113">DevTools が要求を記録しなくなった場合は灰色になります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
1.  <span data-ttu-id="c9f1c-114">`Control` + `E` ネットワーク ツールのフォーカスWindows\(Windows、Linux\) または `Command` + `E` \*\*\*\* \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-114">Select `Control`+`E` \(Windows, Linux\) or `Command`+`E` \(macOS\) while the **Network** tool is in focus.</span></span>  

### <a name="clear-requests"></a><span data-ttu-id="c9f1c-115">要求をクリアする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-115">Clear requests</span></span>  

<span data-ttu-id="c9f1c-116">[**要求]** テーブルからすべての要求をクリアするには、[ネットワーク] ツールで [\( Clear ![ ](../media/clear-requests-icon.msft.png) \) をクリアする] を選択します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c9f1c-116">Choose **Clear** \(![Clear](../media/clear-requests-icon.msft.png)\) on the **Network** tool to clear all requests from the Requests table.</span></span>  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="[クリア] ボタン" lightbox="../media/network-network-clear-button.msft.png":::
   <span data-ttu-id="c9f1c-118">[ **クリア]** ボタン</span><span class="sxs-lookup"><span data-stu-id="c9f1c-118">The **Clear** button</span></span>  
:::image-end:::  

### <a name="save-requests-across-page-loads"></a><span data-ttu-id="c9f1c-119">ページの読み込み中に要求を保存する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-119">Save requests across page loads</span></span>  

<span data-ttu-id="c9f1c-120">ページ読み込み時に要求を保存\*\*\*\* するには、[ネットワーク] ツールで 、[ログの保持] チェック**ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-120">To save requests across page loads, on the **Network** tool, turn on the **Preserve log** checkbox.</span></span>  <span data-ttu-id="c9f1c-121">DevTools は、ログの保持を無効にするまで、すべての要求 **を保存します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-121">DevTools saves all requests until you disable **Preserve log**.</span></span>  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="[ログの保持] チェック ボックス" lightbox="../media/network-network-preserve-log.msft.png":::
   <span data-ttu-id="c9f1c-123">[ **ログの保持]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="c9f1c-123">The **Preserve Log** checkbox</span></span>  
:::image-end:::  

### <a name="capture-screenshots-during-page-load"></a><span data-ttu-id="c9f1c-124">ページの読み込み中にスクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-124">Capture screenshots during page load</span></span>  

<span data-ttu-id="c9f1c-125">スクリーンショットをキャプチャして、ページの読み込み待ち中にユーザーの表示を分析します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-125">Capture screenshots to analyze what displays for users while waiting for your page to load.</span></span>  

<span data-ttu-id="c9f1c-126">スクリーンショットを有効にするには、[ネットワーク設定]**を**選択し\*\*\*\*、[ネットワーク] ツールで 、[スクリーンショットのキャプチャ]**チェック ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-126">To enable screenshots, choose **Network settings**, and on the **Network** tool, turn on the **Capture screenshots** checkbox.</span></span>  

<span data-ttu-id="c9f1c-127">ネットワーク ツールがフォーカス **されている間に** ページを更新して、スクリーンショットをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-127">Refresh the page while the **Network** tool is in focus to capture screenshots.</span></span>  

<span data-ttu-id="c9f1c-128">スクリーンショットをキャプチャした後、次の方法で操作します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-128">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="c9f1c-129">スクリーンショットにカーソルを合わせると、そのスクリーンショットがキャプチャされたポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-129">Hover on a screenshot to display the point at which that screenshot was captured.</span></span>  <span data-ttu-id="c9f1c-130">[概要] ウィンドウに黄色の線 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-130">A yellow line is displayed on the **Overview** pane.</span></span>  
*   <span data-ttu-id="c9f1c-131">スクリーンのサムネイルを選択して、スクリーンショットのキャプチャ後に発生した要求をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-131">Choose the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="c9f1c-132">サムネイルをダブルクリックして拡大表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-132">Double-click a thumbnail to zoom into it.</span></span>  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="スクリーンショットにカーソルを合わせる" lightbox="../media/network-network-screenshot-hover.msft.png":::
   <span data-ttu-id="c9f1c-134">スクリーンショットにカーソルを合わせる</span><span class="sxs-lookup"><span data-stu-id="c9f1c-134">Hover on a screenshot</span></span>  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and choose **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Choose Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Choose Replay XHR  
:::image-end:::  
-->  

## <a name="change-loading-behavior"></a><span data-ttu-id="c9f1c-135">読み込み動作の変更</span><span class="sxs-lookup"><span data-stu-id="c9f1c-135">Change loading behavior</span></span>  

### <a name="emulate-a-first-time-visitor-by-disabling-the-browser-cache"></a><span data-ttu-id="c9f1c-136">ブラウザー キャッシュを無効にして初めての訪問者をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-136">Emulate a first-time visitor by disabling the browser cache</span></span>  

<span data-ttu-id="c9f1c-137">初めてのユーザーがサイトを体験する方法をエミュレートするには、[キャッシュを無効にする] **チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-137">To emulate how a first-time user experiences your site, turn on the **Disable cache** checkbox.</span></span>  <span data-ttu-id="c9f1c-138">DevTools はブラウザー キャッシュを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-138">DevTools disables the browser cache.</span></span>  <span data-ttu-id="c9f1c-139">この機能は、繰り返し訪問時にブラウザー キャッシュから要求が提供されるので、初めてのユーザー エクスペリエンスをより正確にエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-139">This feature more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="[キャッシュを無効にする] チェック ボックス" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   <span data-ttu-id="c9f1c-141">[ **キャッシュを無効にする]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="c9f1c-141">The **Disable Cache** checkbox</span></span>  
:::image-end:::  

#### <a name="disable-the-browser-cache-from-the-network-conditions-drawer"></a><span data-ttu-id="c9f1c-142">ネットワーク条件ドロワーからブラウザー キャッシュを無効にする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-142">Disable the browser cache from the Network Conditions drawer</span></span>  

<span data-ttu-id="c9f1c-143">他の DevTools パネルで作業している間にキャッシュを無効にする場合は、ネットワーク条件ドロワーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-143">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="c9f1c-144">[ネットワーク条件 **] ドロワーを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-144">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="c9f1c-145">[キャッシュを無効にする] チェック ボックスをオン **にします** 。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-145">Turn on \(or off\) the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <a name="manually-clear-the-browser-cache"></a><span data-ttu-id="c9f1c-146">ブラウザー キャッシュを手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-146">Manually clear the browser cache</span></span>  

<span data-ttu-id="c9f1c-147">ブラウザー キャッシュをいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキスト メニュー \(右クリック\) を開き、[ブラウザー キャッシュのクリア] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-147">To manually clear the browser cache at any time, open the contextual menu \(right-click\) anywhere in the Requests table and choose **Clear Browser Cache**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="[ブラウザー キャッシュのクリア] を選択する" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   <span data-ttu-id="c9f1c-149">[ブラウザー **キャッシュのクリア] を選択する**</span><span class="sxs-lookup"><span data-stu-id="c9f1c-149">Choose **Clear Browser Cache**</span></span>  
:::image-end:::  

### <a name="emulate-offline"></a><span data-ttu-id="c9f1c-150">オフラインでのエミュレート</span><span class="sxs-lookup"><span data-stu-id="c9f1c-150">Emulate offline</span></span>  

<span data-ttu-id="c9f1c-151">プログレッシブ Web アプリという名前の新しいクラスの Web アプリ [は][DevtoolsProgressiveWebApps]、サービス ワーカーの助けを借りてオフライン **で機能します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-151">A new class of web apps, named [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="c9f1c-152">この種類のアプリを構築するときに、データ接続がないデバイスをすばやくシミュレートすると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-152">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="c9f1c-153">[オンライン **] ドロップダウン メニュー** を選択し、[プリセット] で検索 **し**、[オフライン] を選択 **して** オフライン ネットワーク エクスペリエンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-153">Choose the **Online** dropdown menu, search under **Presets**, and choose **Offline** to simulate an offline network experience.</span></span>  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="[オフライン] ドロップダウン メニュー" lightbox="../media/network-network-offline-dropdown.msft.png":::
   <span data-ttu-id="c9f1c-155">[ **オフライン]** ドロップダウン メニュー</span><span class="sxs-lookup"><span data-stu-id="c9f1c-155">The **Offline** dropdown menu</span></span>  
:::image-end:::  

### <a name="emulate-slow-network-connections"></a><span data-ttu-id="c9f1c-156">低速ネットワーク接続のエミュレート</span><span class="sxs-lookup"><span data-stu-id="c9f1c-156">Emulate slow network connections</span></span>  

<span data-ttu-id="c9f1c-157">[オンライン] ドロップダウン メニューから低速 3G、Fast 3G、その他の接続速度 **を** エミュレートします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-157">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="[調整] ドロップダウン メニュー" lightbox="../media/network-network-throttling-menu.msft.png":::
   <span data-ttu-id="c9f1c-159">[ **調整]** ドロップダウン メニュー</span><span class="sxs-lookup"><span data-stu-id="c9f1c-159">The **Throttling** dropdown menu</span></span>  
:::image-end:::  

<span data-ttu-id="c9f1c-160">スロー 3G や Fast 3G など、さまざまなプリセットから選択できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-160">You may choose from different presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="c9f1c-161">独自のカスタム プリセットを追加するには、[調整] メニューを開き、[カスタム追加]**を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-161">To add your own custom presets, open the Throttling menu, and choose **Custom** > **Add**.</span></span>  

<span data-ttu-id="c9f1c-162">DevTools はネットワーク ツールの横\*\*\*\* に警告アイコンを表示し、調整が有効になっていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-162">DevTools displays a warning icon next to the **Network** tool to remind you that throttling is enabled.</span></span>  

#### <a name="emulate-slow-network-connections-from-the-network-conditions-drawer"></a><span data-ttu-id="c9f1c-163">ネットワーク条件ドロワーからの低速ネットワーク接続のエミュレート</span><span class="sxs-lookup"><span data-stu-id="c9f1c-163">Emulate slow network connections from the Network Conditions drawer</span></span>  

<span data-ttu-id="c9f1c-164">他の DevTools パネルで作業している間にネットワーク接続を調整する場合は、[ネットワーク条件] ドロワーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-164">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="c9f1c-165">[ネットワーク条件 **] ドロワーを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-165">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="c9f1c-166">[調整] メニューから接続速度 **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-166">Choose your connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <a name="manually-clear-browser-cookies"></a><span data-ttu-id="c9f1c-167">ブラウザーの Cookie を手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-167">Manually clear browser cookies</span></span>  

<span data-ttu-id="c9f1c-168">ブラウザーの Cookie をいつでも手動でクリアするには、[要求] テーブルの任意の場所にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[ブラウザー Cookie のクリア] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-168">To manually clear browser cookies at any time, hover anywhere in the Requests table, open the contextual menu \(right-click\), and choose **Clear Browser Cookies**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="[ブラウザーの Cookie のクリア] を選択する" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   <span data-ttu-id="c9f1c-170">[ブラウザー **の Cookie のクリア] を選択する**</span><span class="sxs-lookup"><span data-stu-id="c9f1c-170">Choose **Clear Browser Cookies**</span></span>  
:::image-end:::  

### <a name="override-the-user-agent"></a><span data-ttu-id="c9f1c-171">ユーザー エージェントを上書きする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-171">Override the user agent</span></span>  

<span data-ttu-id="c9f1c-172">ユーザー エージェントを手動で上書きするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-172">To manually override the user agent, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-173">[ネットワーク条件 **] ドロワーを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-173">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="c9f1c-174">[自動的に選択 **する] チェック ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-174">Turn off the **Select automatically** checkbox.</span></span>  
1.  <span data-ttu-id="c9f1c-175">メニューからユーザー エージェント オプションを選択するか、テキスト ボックスにカスタム エージェントを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-175">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <a name="filter-requests"></a><span data-ttu-id="c9f1c-176">要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-176">Filter requests</span></span>  

### <a name="filter-requests-by-properties"></a><span data-ttu-id="c9f1c-177">プロパティで要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-177">Filter requests by properties</span></span>  

<span data-ttu-id="c9f1c-178">[フィルター **] テキスト** ボックスを使用して、要求のドメインやサイズなどのプロパティで要求をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-178">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="c9f1c-179">テキスト ボックスが表示されない場合、[フィルター] **ウィンドウ** は非表示の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-179">If the text box is not displayed, the **Filters** pane is probably hidden.</span></span>  
<span data-ttu-id="c9f1c-180">詳細については、「フィルター ウィンドウを非表示 [にする」に移動します](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-180">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="[フィルター] テキスト ボックス" lightbox="../media/network-network-filters-textbox.msft.png":::
   <span data-ttu-id="c9f1c-182">[ **フィルター]** テキスト ボックス</span><span class="sxs-lookup"><span data-stu-id="c9f1c-182">The **Filter** text box</span></span>  
:::image-end:::  

<span data-ttu-id="c9f1c-183">各プロパティをスペースで区切って、複数のプロパティを同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-183">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="c9f1c-184">たとえば `mime-type:image/png larger-than:1K` 、1 KB を超えるすべての PNG を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-184">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than 1 kilobyte.</span></span>  <span data-ttu-id="c9f1c-185">マルチプロパティ フィルターは、操作と同 `AND` じです。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-185">The multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="c9f1c-186">操作は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-186">operations are currently not supported.</span></span>  

<span data-ttu-id="c9f1c-187">サポートされているプロパティの完全な一覧。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-187">The complete list of supported properties.</span></span>  

| <span data-ttu-id="c9f1c-188">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c9f1c-188">Property</span></span> | <span data-ttu-id="c9f1c-189">詳細</span><span class="sxs-lookup"><span data-stu-id="c9f1c-189">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="c9f1c-190">指定したドメインのリソースのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-190">Only display resources from the specified domain.</span></span>  <span data-ttu-id="c9f1c-191">複数のドメインを含めるには、ワイルドカード文字 \( `*` \) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-191">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="c9f1c-192">たとえば、で `*.com` 終わるすべてのドメイン名のリソースを表示します `.com` 。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-192">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="c9f1c-193">DevTools は、オートコンプリートドロップダウン メニューに、見つかったすべてのドメインを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-193">DevTools populate the autocomplete dropdown menu with all of the domains that are found.</span></span> |  
| `has-response-header` | <span data-ttu-id="c9f1c-194">指定した HTTP 応答ヘッダーを含むリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-194">Displays the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="c9f1c-195">DevTools は、オートコンプリート ドロップダウンに、見つかったすべての応答ヘッダーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-195">DevTools populate the autocomplete dropdown with all of the response headers that are found.</span></span> |  
| `is` | <span data-ttu-id="c9f1c-196">リソース `is:running` の検索に `WebSocket` 使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-196">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="c9f1c-197">指定したサイズより大きいリソースをバイト単位で表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-197">Displays resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="c9f1c-198">値の設定は `1000` 、 の値を設定するのと同じです `1k` 。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-198">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="c9f1c-199">指定した HTTP メソッドの種類で取得されたリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-199">Displays resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="c9f1c-200">DevTools はドロップダウンに、見つかったすべての HTTP メソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-200">DevTools populate the dropdown with all of the HTTP methods  that are found.</span></span> |  
| `mime-type` | <span data-ttu-id="c9f1c-201">指定した MIME の種類のリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-201">Displays resources of a specified MIME type.</span></span>  <span data-ttu-id="c9f1c-202">DevTools はドロップダウンに、見つかったすべての MIME の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-202">DevTools populate the dropdown with all MIME types  that are found.</span></span> |  
| `mixed-content` | <span data-ttu-id="c9f1c-203">すべての混在コンテンツ リソース \( \) または現在表示されている `mixed-content:all` コンテンツの \( `mixed-content:displayed` \) を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-203">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="c9f1c-204">保護されていない HTTP \( \) または保護された HTTPS \( \) を使用して取得された `scheme:http` リソースを `scheme:https` 表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-204">Displays resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="c9f1c-205">指定した値に一致 `Set-Cookie` する属性を持 `Domain` つヘッダーを持つリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-205">Displays resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="c9f1c-206">DevTools はオートコンプリートに、見つかったすべての Cookie ドメインを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-206">DevTools populate the autocomplete with all of the cookie domains that are found.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="c9f1c-207">指定した値に一致 `Set-Cookie` する名前のヘッダーを持つリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-207">Displays resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="c9f1c-208">DevTools はオートコンプリートに、見つかったすべての Cookie 名を設定します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-208">DevTools populate the autocomplete with all of the cookie names that are found.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="c9f1c-209">指定した値に一致 `Set-Cookie` する値を持つヘッダーを持つリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-209">Displays resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="c9f1c-210">DevTools はオートコンプリートに、見つかったすべての Cookie 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-210">DevTools populate the autocomplete with all of the cookie values that are found.</span></span> |  
| `status-code` | <span data-ttu-id="c9f1c-211">特定の HTTP 状態コードに一致するリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-211">Displays resources that match the specific HTTP status code.</span></span>  <span data-ttu-id="c9f1c-212">DevTools は、オートコンプリートドロップダウン メニューに、見つかったすべての状態コードを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-212">DevTools populates the autocomplete dropdown menu with all of the status codes that are found.</span></span> |  

### <a name="filter-requests-by-type"></a><span data-ttu-id="c9f1c-213">種類別に要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-213">Filter requests by type</span></span>  

<span data-ttu-id="c9f1c-214">要求の種類別に要求をフィルター処理するには、ネットワーク ツールで次のいずれかのボタンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-214">To filter requests by request type, choose the one of the following buttons on the **Network** tool.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-215">XHR</span><span class="sxs-lookup"><span data-stu-id="c9f1c-215">XHR</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-216">JS</span><span class="sxs-lookup"><span data-stu-id="c9f1c-216">JS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-217">CSS</span><span class="sxs-lookup"><span data-stu-id="c9f1c-217">CSS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-218">Img</span><span class="sxs-lookup"><span data-stu-id="c9f1c-218">Img</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-219">メディア</span><span class="sxs-lookup"><span data-stu-id="c9f1c-219">Media</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-220">フォント</span><span class="sxs-lookup"><span data-stu-id="c9f1c-220">Font</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-221">Doc</span><span class="sxs-lookup"><span data-stu-id="c9f1c-221">Doc</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-222">WS</span><span class="sxs-lookup"><span data-stu-id="c9f1c-222">WS</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-223">WebSocket。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-223">WebSocket.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-224">マニフェスト</span><span class="sxs-lookup"><span data-stu-id="c9f1c-224">Manifest</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-225">Other</span><span class="sxs-lookup"><span data-stu-id="c9f1c-225">Other</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-226">リストされていないその他の型。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-226">Any other type not listed.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="c9f1c-227">ボタンが表示されない場合は、[フィルター] **ウィンドウ** が非表示になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-227">If the buttons do not display, the **Filters** pane may be hidden.</span></span>  
<span data-ttu-id="c9f1c-228">詳細については、「フィルター ウィンドウを非表示 [にする」に移動します](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-228">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="c9f1c-229">複数の種類のフィルターを同時に有効 `Control` にするには、\(Windows、Linux\) または `Command` \(macOS\) を押したまま選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-229">To enable multiple type filters simultaneously, hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose.</span></span>  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="Type フィルターを使用して JS、CSS、および Document リソースを表示する" lightbox="../media/network-network-type-filters.msft.png":::
   <span data-ttu-id="c9f1c-231">Type フィルターを使用して JS、CSS、および Document リソースを表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-231">Use the Type filters to display JS, CSS, and Document resources</span></span>  
:::image-end:::  

### <a name="filter-requests-by-time"></a><span data-ttu-id="c9f1c-232">時間別に要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-232">Filter requests by time</span></span>  

<span data-ttu-id="c9f1c-233">[概要] ウィンドウで左または **右にドラッグ** して、その期間にアクティブだった要求のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-233">Choose and drag left or right on the **Overview** pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="c9f1c-234">フィルターは含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-234">The filter is inclusive.</span></span>  <span data-ttu-id="c9f1c-235">強調表示された時間にアクティブだったすべての要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-235">Any request that was active during the highlighted time is shown.</span></span>  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="約 300 ミリ秒で非アクティブだった要求をフィルター処理する" lightbox="../media/network-network-overview-filter.msft.png":::
   <span data-ttu-id="c9f1c-237">約 300 ミリ秒で非アクティブだった要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-237">Filter out any requests that were inactive around 300 ms</span></span>  
:::image-end:::  

### <a name="hide-data-urls"></a><span data-ttu-id="c9f1c-238">データ URL を非表示にする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-238">Hide data URLs</span></span>  

<span data-ttu-id="c9f1c-239">[データ URL は、][MDNHTTPDataURIs] 他のドキュメントに埋め込まれた小さなファイルです。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-239">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="c9f1c-240">で始まる Requests テーブルに表示される要求は `data:` 、データ URL です。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-240">Any request that displays in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="c9f1c-241">要求を非表示にするには、[データ URL を非表示 **にする] チェック ボックスをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-241">To hide the requests, turn off the **Hide data URLs** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="[データ URL を非表示にする] チェック ボックス" lightbox="../media/network-network-hide-data-urls.msft.png":::
   <span data-ttu-id="c9f1c-243">[ **データ URL を非表示にする] チェック** ボックス</span><span class="sxs-lookup"><span data-stu-id="c9f1c-243">The **Hide Data URLs** checkbox</span></span>  
:::image-end:::  

## <a name="sort-requests"></a><span data-ttu-id="c9f1c-244">要求の並べ替え</span><span class="sxs-lookup"><span data-stu-id="c9f1c-244">Sort requests</span></span>  

<span data-ttu-id="c9f1c-245">既定では、[要求] テーブル内の要求は開始時刻によって並べ替えされますが、他の条件を使用してテーブルを並べ替える場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-245">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <a name="sort-by-column"></a><span data-ttu-id="c9f1c-246">列による並べ替え</span><span class="sxs-lookup"><span data-stu-id="c9f1c-246">Sort by column</span></span>  

<span data-ttu-id="c9f1c-247">[要求] で任意の列のヘッダーを選択し、その列で要求を並べ替える。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-247">Choose the header of any column in the Requests to sort requests by that column.</span></span>  

### <a name="sort-by-activity-phase"></a><span data-ttu-id="c9f1c-248">アクティビティフェーズ別の並べ替え</span><span class="sxs-lookup"><span data-stu-id="c9f1c-248">Sort by activity phase</span></span>  

<span data-ttu-id="c9f1c-249">ウォーターフォールが要求を並べ替える方法を変更するには、Requests テーブルのヘッダーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、 **ウォーター**フォール にカーソルを合わせると、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-249">To change how the Waterfall sorts requests, hover on the header of the Requests table, open the contextual menu \(right-click\), hover on **Waterfall**, and choose one of the following options.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-250">開始時刻</span><span class="sxs-lookup"><span data-stu-id="c9f1c-250">Start Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-251">開始された最初の要求は、上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-251">The first request that was initiated is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-252">応答時間</span><span class="sxs-lookup"><span data-stu-id="c9f1c-252">Response Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-253">ダウンロードを開始した最初の要求が一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-253">The first request that started downloading is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-254">終了時刻</span><span class="sxs-lookup"><span data-stu-id="c9f1c-254">End Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-255">完了した最初の要求は、上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-255">The first request that finished is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-256">合計期間</span><span class="sxs-lookup"><span data-stu-id="c9f1c-256">Total Duration</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-257">最短の接続設定と要求または応答を持つ要求が一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-257">The request with the shortest connection settings and request or response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-258">遅延</span><span class="sxs-lookup"><span data-stu-id="c9f1c-258">Latency</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-259">応答の最も短い時間を待った要求は、一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-259">The request that waited the shortest time for a response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="c9f1c-260">これらの説明では、それぞれのオプションが最短から最長にランク付けされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-260">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="c9f1c-261">[ウォーターフォール] 列のヘッダー **を選択** して、順序を逆にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-261">Choose the header of the **Waterfall** column to reverse the order.</span></span>  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="合計期間でウォーターフォールを並べ替える" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   <span data-ttu-id="c9f1c-263">合計時間 \(各バーの明るい部分は待機時間、暗い部分はバイトのダウンロードに費やされた時間\) でウォーターフォールを並べ替える</span><span class="sxs-lookup"><span data-stu-id="c9f1c-263">Sort the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
:::image-end:::  

## <a name="analyze-requests"></a><span data-ttu-id="c9f1c-264">要求の分析</span><span class="sxs-lookup"><span data-stu-id="c9f1c-264">Analyze requests</span></span>  

<span data-ttu-id="c9f1c-265">DevTools が開いている限り、すべての要求がネットワーク ツールに **記録** されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-265">So long as DevTools are open, it logs all requests in the **Network** tool.</span></span>  
<span data-ttu-id="c9f1c-266">[ネットワーク] パネルを使用して要求を分析します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-266">Use the Network panel to analyze requests.</span></span>  

### <a name="display-a-log-of-requests"></a><span data-ttu-id="c9f1c-267">要求のログを表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-267">Display a log of requests</span></span>  

<span data-ttu-id="c9f1c-268">DevTools が開いている間に行われたすべての要求のログを表示するには、[要求] テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-268">Use the Requests table to display a log of all requests made while DevTools have been open.</span></span>  <span data-ttu-id="c9f1c-269">各アイテムの詳細を表示するには、要求を選択またはホバーします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-269">To reveals more information about each item, choose or hover on requests.</span></span>  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="Requests テーブル" lightbox="../media/network-network-requests-table.msft.png":::
   <span data-ttu-id="c9f1c-271">Requests テーブル</span><span class="sxs-lookup"><span data-stu-id="c9f1c-271">The Requests table</span></span>  
:::image-end:::  

<span data-ttu-id="c9f1c-272">[要求] テーブルには、既定で次の列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-272">The Requests table displays the following columns by default.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-273">名前</span><span class="sxs-lookup"><span data-stu-id="c9f1c-273">Name</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-274">リソースのファイル名または識別子。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-274">The filename of, or an identifier for, the resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-275">状態</span><span class="sxs-lookup"><span data-stu-id="c9f1c-275">Status</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-276">HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-276">The HTTP status code.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-277">型</span><span class="sxs-lookup"><span data-stu-id="c9f1c-277">Type</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-278">要求されたリソースの MIME の種類。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-278">The MIME type of the requested resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-279">イニシエーター</span><span class="sxs-lookup"><span data-stu-id="c9f1c-279">Initiator</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-280">次のオブジェクトまたはプロセスが要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-280">The following objects or processes initiate requests.</span></span>  
      
      *   <span data-ttu-id="c9f1c-281">**パーサー** ユーザーの HTML パーサー Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-281">**Parser**  The HTML parser for Microsoft Edge.</span></span>  
      *   <span data-ttu-id="c9f1c-282">**リダイレクト**  HTTP リダイレクト。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-282">**Redirect**  An HTTP redirect.</span></span>  
      *   <span data-ttu-id="c9f1c-283">**スクリプト**  JavaScript 関数。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-283">**Script**  A JavaScript function.</span></span>  
      *   <span data-ttu-id="c9f1c-284">**その他**  リンクを使用してページに移動したり、アドレス バーに URL を入力したりなど、他のプロセスやアクションもあります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-284">**Other**  Some other process or action, such as navigating to a page using a link or entering a URL in the address bar.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-285">Size</span><span class="sxs-lookup"><span data-stu-id="c9f1c-285">Size</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-286">サーバーによって配信される応答ヘッダーと応答本文の合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-286">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-287">Time</span><span class="sxs-lookup"><span data-stu-id="c9f1c-287">Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-288">要求の開始から応答の最終バイトの受信まで、合計期間。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-288">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c9f1c-289">ウォーターフォール</span><span class="sxs-lookup"><span data-stu-id="c9f1c-289">Waterfall</span></span>](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-290">各要求のアクティビティの視覚的な内訳。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-290">A visual breakdown of the activity for each request.</span></span>  
   :::column-end:::
:::row-end:::  

#### <a name="add-or-remove-columns"></a><span data-ttu-id="c9f1c-291">列の追加または削除</span><span class="sxs-lookup"><span data-stu-id="c9f1c-291">Add or remove columns</span></span>  

<span data-ttu-id="c9f1c-292">Requests テーブルのヘッダーにポインターを置き、コンテキスト メニュー \(右クリック\) を開き、非表示または表示するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-292">Hover on the header of the Requests table, open the contextual menu \(right-click\), and choose an option to hide or show it.</span></span>  <span data-ttu-id="c9f1c-293">現在表示されているオプションには、各アイテムの横にチェックマークが付きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-293">Currently displayed options have checkmarks next to each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="[要求] テーブルに列を追加する" lightbox="../media/network-network-requests-add-column.msft.png":::
   <span data-ttu-id="c9f1c-295">[要求] テーブルに列を追加する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-295">Add a column to the Requests table</span></span>  
:::image-end:::  

#### <a name="add-custom-columns"></a><span data-ttu-id="c9f1c-296">カスタム列の追加</span><span class="sxs-lookup"><span data-stu-id="c9f1c-296">Add custom columns</span></span>  

<span data-ttu-id="c9f1c-297">カスタム列を Requests テーブルに追加するには、Requests テーブルのヘッダーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\*\*\*\* \) を開き、[応答ヘッダーヘッダーのヘッダー列の管理] を選択  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-297">To add a custom column to the Requests table, hover on the header of the Requests table, open the contextual menu \(right-click\), and choose **Response Headers** > **Manage Header Columns**.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="要求テーブルにカスタム列を追加する" lightbox="../media/network-network-requests-add-custom.msft.png":::
   <span data-ttu-id="c9f1c-299">要求テーブルにカスタム列を追加する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-299">Add a custom column to the Requests table</span></span>  
:::image-end:::  

### <a name="display-the-timing-relationship-of-requests"></a><span data-ttu-id="c9f1c-300">要求のタイミング関係を表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-300">Display the timing relationship of requests</span></span>  

<span data-ttu-id="c9f1c-301">要求のタイミング関係を表示するには、ウォーターフォールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-301">Use the Waterfall to display the timing relationships of requests.</span></span>  
<span data-ttu-id="c9f1c-302">ウォーターフォールの既定の組織では、要求の開始時刻が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-302">The default organization of the Waterfall uses the start time of the requests.</span></span>  
<span data-ttu-id="c9f1c-303">そのため、左側より遠い要求は、右に遠い要求よりも早く開始されました。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-303">So, requests that are farther to the left started earlier than the requests that are farther to the right.</span></span>  

<span data-ttu-id="c9f1c-304">ウォーターフォールを並べ替えるさまざまな方法を確認するには、[アクティビティで並べ替え] [フェーズに移動します](#sort-by-activity-phase)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-304">To review the different ways that you may sort the Waterfall, navigate to [Sort by activity phase](#sort-by-activity-phase).</span></span>  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="[要求] ウィンドウの [ウォーターフォール] 列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   <span data-ttu-id="c9f1c-306">[要求] ウィンドウの **[ウォーターフォール]** 列</span><span class="sxs-lookup"><span data-stu-id="c9f1c-306">The Waterfall column of the **Requests** pane</span></span>  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To review the frames of a WebSocket connection, use the following steps.  

1.  Choose the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Choose the **Frames** panel.  The table shows the last 100 frames.  

To refresh the table, re-choose the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames panel" lightbox="../media/network-frames.msft.png":::
   The **Frames** panel  
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

### <a name="display-a-preview-of-a-response-body"></a><span data-ttu-id="c9f1c-307">応答本文のプレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-307">Display a preview of a response body</span></span>  

<span data-ttu-id="c9f1c-308">応答本文のプレビューを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-308">To display a preview of a response body, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-309">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-309">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="c9f1c-310">[プレビュー] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-310">Choose the **Preview** panel.</span></span>  

<span data-ttu-id="c9f1c-311">[プレビュー] タブは、主に画像を表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-311">The Preview tab is mostly useful to display images.</span></span>  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="[プレビュー] パネル" lightbox="../media/network-network-resources-preview.msft.png":::
   <span data-ttu-id="c9f1c-313">[ **プレビュー]** パネル</span><span class="sxs-lookup"><span data-stu-id="c9f1c-313">The **Preview** panel</span></span>  
:::image-end:::  

### <a name="display-a-response-body"></a><span data-ttu-id="c9f1c-314">応答本文の表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-314">Display a response body</span></span>  

<span data-ttu-id="c9f1c-315">要求に対する応答本文を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-315">To display the response body to a request, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-316">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-316">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="c9f1c-317">[応答] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-317">Choose the **Response** panel.</span></span>  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="[応答] パネル" lightbox="../media/network-network-resources-response.msft.png":::
   <span data-ttu-id="c9f1c-319">[ **応答]** パネル</span><span class="sxs-lookup"><span data-stu-id="c9f1c-319">The **Response** panel</span></span>  
:::image-end:::  

### <a name="display-http-headers"></a><span data-ttu-id="c9f1c-320">HTTP ヘッダーの表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-320">Display HTTP headers</span></span>  

<span data-ttu-id="c9f1c-321">要求に関する HTTP ヘッダー データを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-321">To display HTTP header data about a request, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-322">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-322">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="c9f1c-323">[ヘッダー **]** psanel を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-323">Choose the **Headers** psanel.</span></span>  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="[ヘッダー] パネル" lightbox="../media/network-resources-headers.msft.png":::
   <span data-ttu-id="c9f1c-325">[ **ヘッダー]** パネル</span><span class="sxs-lookup"><span data-stu-id="c9f1c-325">The **Headers** panel</span></span>  
:::image-end:::  

#### <a name="display-http-header-source"></a><span data-ttu-id="c9f1c-326">HTTP ヘッダー ソースの表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-326">Display HTTP header source</span></span>  

<span data-ttu-id="c9f1c-327">既定では、[ヘッダー] **パネルには** ヘッダー名がアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-327">By default, the **Headers** panel shows header names alphabetically.</span></span>  <span data-ttu-id="c9f1c-328">HTTP ヘッダー名を受け取った順序で表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-328">To dsiplay the HTTP header names in the order received, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-329">興味のある **要求** の [ヘッダー] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-329">Open the **Headers** panel for the request that interests you.</span></span>  <span data-ttu-id="c9f1c-330">詳細については、[HTTP ヘッダーの表示 [] に移動します](#display-http-headers)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-330">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="c9f1c-331">[ **要求ヘッダー] または**[応答ヘッダー] セクションの横にある **[** ソース **の表示] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-331">Choose **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <a name="display-query-string-parameters"></a><span data-ttu-id="c9f1c-332">クエリ文字列パラメーターの表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-332">Display query string parameters</span></span>  

<span data-ttu-id="c9f1c-333">URL のクエリ文字列パラメーターを人間が読み取り可能な形式で表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-333">To display the query string parameters of a URL in a human-readable format, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-334">興味のある **要求** の [ヘッダー] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-334">Open the **Headers** panel for the request that interests you.</span></span>  <span data-ttu-id="c9f1c-335">詳細については、[HTTP ヘッダーの表示 [] に移動します](#display-http-headers)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-335">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="c9f1c-336">[クエリ文字列パラメーター **] セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-336">Navigate to the **Query String Parameters** section.</span></span>  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="[クエリ文字列のパラメーター] セクション" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   <span data-ttu-id="c9f1c-338">[ **クエリ文字列のパラメーター]** セクション</span><span class="sxs-lookup"><span data-stu-id="c9f1c-338">The **Query String Parameters** section</span></span>  
:::image-end:::  

#### <a name="display-query-string-parameters-source"></a><span data-ttu-id="c9f1c-339">クエリ文字列パラメーターソースの表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-339">Display query string parameters source</span></span>  

<span data-ttu-id="c9f1c-340">要求のクエリ文字列パラメーター ソースを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-340">To display the query string parameter source of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-341">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-341">Navigate to the Query String Parameters section.</span></span>  <span data-ttu-id="c9f1c-342">詳細については、「クエリ文字列パラメーターの [表示」に移動します](#display-query-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-342">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="c9f1c-343">[ソース **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-343">Choose **view source**.</span></span>  

#### <a name="display-url-encoded-query-string-parameters"></a><span data-ttu-id="c9f1c-344">URL エンコードされたクエリ文字列パラメーターの表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-344">Display URL-encoded query string parameters</span></span>  

<span data-ttu-id="c9f1c-345">クエリ文字列パラメーターを人間が読み取り可能な形式で表示し、エンコードを保持するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-345">To display query string parameters in a human-readable format, but with encodings preserved, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-346">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-346">Navigate to the Query String Parameters section.</span></span>  <span data-ttu-id="c9f1c-347">詳細については、「クエリ文字列パラメーターの [表示」に移動します](#display-query-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-347">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="c9f1c-348">[エンコード **された URL の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-348">Choose **view URL encoded**.</span></span>  

### <a name="display-cookies"></a><span data-ttu-id="c9f1c-349">Cookie の表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-349">Display cookies</span></span>  

<span data-ttu-id="c9f1c-350">要求の HTTP ヘッダーで送信された Cookie を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-350">To display the cookies sent in the HTTP header of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-351">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-351">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="c9f1c-352">[Cookie] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-352">Choose the **Cookies** panel.</span></span>  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="[Cookie] パネル" lightbox="../media/network-network-resources-cookies.msft.png":::
   <span data-ttu-id="c9f1c-354">[Cookie] パネル</span><span class="sxs-lookup"><span data-stu-id="c9f1c-354">The Cookies panel</span></span>  
:::image-end:::  

### <a name="display-the-timing-breakdown-of-a-request"></a><span data-ttu-id="c9f1c-355">要求のタイミングの内訳を表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-355">Display the timing breakdown of a request</span></span>  

<span data-ttu-id="c9f1c-356">要求のタイミングの内訳を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-356">To display the timing breakdown of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-357">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-357">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="c9f1c-358">[タイミング] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-358">Choose the **Timing** panel.</span></span>  

<span data-ttu-id="c9f1c-359">データにアクセスする方法を速くするには、[タイミングの内訳を [プレビューする] に移動します](#preview-a-timing-breakdown)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-359">For a faster way to access the data, navigate to [Preview a timing breakdown](#preview-a-timing-breakdown).</span></span>  

<span data-ttu-id="c9f1c-360">[タイミング] パネルに表示される各フェーズの詳細については、「タイミング\*\*\*\* の内訳フェーズ」[を参照してください](#timing-breakdown-phases-explained)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-360">For more information about each of the phases that may be displayed in the **Timing** panel, navigate to [Timing breakdown phases explained](#timing-breakdown-phases-explained).</span></span>  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="[タイミング] パネル" lightbox="../media/network-network-resources-timing.msft.png":::
   <span data-ttu-id="c9f1c-362">[ **タイミング]** パネル</span><span class="sxs-lookup"><span data-stu-id="c9f1c-362">The **Timing** panel</span></span>  
:::image-end:::  

<span data-ttu-id="c9f1c-363">各フェーズの詳細。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-363">More information about each of the phases.</span></span>  

<span data-ttu-id="c9f1c-364">表示にアクセスする方法の詳細については、「タイミングの内訳を表示 [する」に移動します](#display-the-timing-breakdown-of-a-request)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-364">For more information about accessing the display, navigate to [Display timing breakdown](#display-the-timing-breakdown-of-a-request).</span></span>  

#### <a name="preview-a-timing-breakdown"></a><span data-ttu-id="c9f1c-365">タイミングの内訳をプレビューする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-365">Preview a timing breakdown</span></span>  

<span data-ttu-id="c9f1c-366">要求のタイミングの内訳のプレビューを表示するには、[要求] テーブルの **[ウォーター** フォール] 列で、要求のエントリにマウス ポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-366">To display a preview of the timing breakdown of a request, in the **Waterfall** column of the Requests table, hover on the entry for the request.</span></span>  

<span data-ttu-id="c9f1c-367">ホバーせずにデータにアクセスする方法の詳細については、「要求のタイミングの内訳を表示する」 [に移動します](#display-the-timing-breakdown-of-a-request)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-367">For more information about how to access the data without hovering, navigate to [Display the timing breakdown of a request](#display-the-timing-breakdown-of-a-request).</span></span>  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text=">要求のタイミングの内訳をプレビューする" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   <span data-ttu-id="c9f1c-369">要求のタイミングの内訳をプレビューする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-369">Preview the timing breakdown of a request</span></span>  
:::image-end:::  

#### <a name="timing-breakdown-phases-explained"></a><span data-ttu-id="c9f1c-370">タイミングの内訳フェーズの説明</span><span class="sxs-lookup"><span data-stu-id="c9f1c-370">Timing breakdown phases explained</span></span>  

<span data-ttu-id="c9f1c-371">タイミング パネルに表示される各フェーズの詳細。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c9f1c-371">More information about each of the phases that may display in the **Timing** panel.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-372">キューに入る</span><span class="sxs-lookup"><span data-stu-id="c9f1c-372">Queueing</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-373">ブラウザーは、次の値に当てはまる場合に要求をキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-373">The browser queues requests when any of the following are true.</span></span>  
      
      *   <span data-ttu-id="c9f1c-374">優先度の高い要求が存在します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-374">Higher priority requests exist.</span></span>  
      *   <span data-ttu-id="c9f1c-375">同じオリジンに対して 6 つの TCP 接続が開いている。これは制限です。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-375">Six TCP connections are open for the same origin, which is the limit.</span></span>  <span data-ttu-id="c9f1c-376">HTTP/1.0 および HTTP/1.1 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-376">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
      *   <span data-ttu-id="c9f1c-377">ブラウザーがディスク キャッシュ内の領域を簡単に割り当て中です。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-377">The browser is briefly allocating space in the disk cache.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-378">ストール</span><span class="sxs-lookup"><span data-stu-id="c9f1c-378">Stalled</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-379">「キューに入る」で説明されている理由で、要求が **停止します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-379">The request is stalled for any of the reasons described in **Queueing**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-380">DNS ルックアップ</span><span class="sxs-lookup"><span data-stu-id="c9f1c-380">DNS Lookup</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-381">ブラウザーは要求の IP アドレスを解決しています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-381">The browser is resolving the IP address for the request.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-382">初期接続</span><span class="sxs-lookup"><span data-stu-id="c9f1c-382">Initial connection</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-383">ブラウザーは、TCP ハンドシェイク、TCP 再試行、および Secure Socket Layer のネゴシエートを含む接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-383">The browser establishes a connection including TCP handshakes, TCP retries, and negotiates a Secure Socket Layer.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-384">プロキシ ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="c9f1c-384">Proxy negotiation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-385">ブラウザーが要求をプロキシ サーバーとネゴ [シエートしています][WikiProxyServer]。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-385">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-386">送信された要求</span><span class="sxs-lookup"><span data-stu-id="c9f1c-386">Request sent</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-387">要求が送信されています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-387">The request is being sent.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-388">ServiceWorker の準備</span><span class="sxs-lookup"><span data-stu-id="c9f1c-388">ServiceWorker Preparation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-389">ブラウザーがサービス ワーカーを開始しています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-389">The browser is starting the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-390">ServiceWorker への要求</span><span class="sxs-lookup"><span data-stu-id="c9f1c-390">Request to ServiceWorker</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-391">要求がサービス ワーカーに送信されています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-391">The request is being sent to the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-392">待機中 \(TTFB\)</span><span class="sxs-lookup"><span data-stu-id="c9f1c-392">Waiting \(TTFB\)</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-393">ブラウザーは応答の最初のバイトを待機しています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-393">The browser is waiting for the first byte of a response.</span></span>  <span data-ttu-id="c9f1c-394">TTFB は、最初のバイトに時間を表します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-394">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="c9f1c-395">このタイミングには、1 回の待機時間と、サーバーが応答の準備にかかった時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-395">This timing includes one round trip of latency and the time the server took to prepare the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-396">コンテンツのダウンロード</span><span class="sxs-lookup"><span data-stu-id="c9f1c-396">Content Download</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-397">ブラウザーが応答を受信しています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-397">The browser is receiving the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-398">プッシュの受信</span><span class="sxs-lookup"><span data-stu-id="c9f1c-398">Receiving Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-399">ブラウザーは HTTP/2 Server Push を介してこの応答のデータを受信しています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-399">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c9f1c-400">プッシュの読み取り</span><span class="sxs-lookup"><span data-stu-id="c9f1c-400">Reading Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c9f1c-401">ブラウザーは、以前に受信したローカル データを読み取り中です。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-401">The browser is reading the local data previously received.</span></span>  
   :::column-end:::
:::row-end:::  

### <a name="display-initiators-and-dependencies"></a><span data-ttu-id="c9f1c-402">イニシエーターと依存関係の表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-402">Display initiators and dependencies</span></span>  

<span data-ttu-id="c9f1c-403">要求の開始者と依存関係を表示するには、[要求] テーブルで要求を保持してホ `Shift` バーします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-403">To display the initiators and dependencies of a request, hold `Shift`and hover on the request in the Requests table.</span></span>  <span data-ttu-id="c9f1c-404">DevTools の色: イニシエーターは緑で表示され、依存関係は赤で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-404">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="要求の開始者と依存関係を表示する" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   <span data-ttu-id="c9f1c-406">要求の開始者と依存関係を表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-406">Display the initiators and dependencies of a request</span></span>  
:::image-end:::  

<span data-ttu-id="c9f1c-407">Requests テーブルが時系列的に並べらされている場合、行にカーソルを置くと、その前の行に緑色の要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-407">When the Requests table is ordered chronologically, if you hover on a line, the line preceding it displays a green request.</span></span>  <span data-ttu-id="c9f1c-408">緑色の要求は、依存関係の開始者です。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-408">The green request is the initiator of the dependency.</span></span>  <span data-ttu-id="c9f1c-409">それより前の行に別の緑色の要求が表示される場合、その高い要求は開始者の開始者です。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-409">If another green request is displayed on the line before that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="c9f1c-410">などなど。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-410">And so on.</span></span>  

### <a name="display-load-events"></a><span data-ttu-id="c9f1c-411">読み込みイベントの表示</span><span class="sxs-lookup"><span data-stu-id="c9f1c-411">Display load events</span></span>  

<span data-ttu-id="c9f1c-412">DevTools は、ネットワーク ツール上の複数 `DOMContentLoaded` の場所 `load` でイベントのタイミングを **表示** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-412">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the **Network** tool.</span></span>  <span data-ttu-id="c9f1c-413">イベント `DOMContentLoaded` は青で、イベント `load` は赤です。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-413">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="ネットワーク パネルの DOMContentLoaded イベントと読み込みイベントの場所" lightbox="../media/network-network-requests-load-events.msft.png":::
   <span data-ttu-id="c9f1c-415">ネットワーク ツール上の `DOMContentLoaded` イベント `load` の場所\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c9f1c-415">The locations of the `DOMContentLoaded` and `load` events on the **Network** tool</span></span>  
:::image-end:::  

### <a name="display-the-total-number-of-requests"></a><span data-ttu-id="c9f1c-416">要求の総数を表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-416">Display the total number of requests</span></span>  

<span data-ttu-id="c9f1c-417">要求の総数は、[ネットワーク] ツールの下部\*\*\*\* にある [概要] ウィンドウに**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-417">The total number of requests is listed in the **Summary** pane, at the bottom of the **Network** tool.</span></span>  

> [!CAUTION]
> <span data-ttu-id="c9f1c-418">この番号は、DevTools が開いた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-418">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="c9f1c-419">DevTools が開く前に他の要求が発生した場合、それらの要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-419">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="DevTools が開いた後の要求の総数" lightbox="../media/network-network-total-requests.msft.png":::
   <span data-ttu-id="c9f1c-421">DevTools が開いた後の要求の総数</span><span class="sxs-lookup"><span data-stu-id="c9f1c-421">The total number of requests since DevTools were opened</span></span>  
:::image-end:::  

### <a name="display-the-total-download-size"></a><span data-ttu-id="c9f1c-422">ダウンロード サイズの合計を表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-422">Display the total download size</span></span>  

<span data-ttu-id="c9f1c-423">要求の合計ダウンロード サイズは、[ネットワーク] ツール\*\*\*\* の下部にある [概要] ウィンドウに**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-423">The total download size of requests is listed in the **Summary** pane, at the bottom of the **Network** tool.</span></span>  

> [!CAUTION]
> <span data-ttu-id="c9f1c-424">この番号は、DevTools が開いた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-424">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="c9f1c-425">DevTools が開く前に他の要求が発生した場合、前の要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-425">If other requests occurred before DevTools was opened, the previous requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="要求のダウンロード サイズの合計" lightbox="../media/network-network-total-download-size.msft.png":::
   <span data-ttu-id="c9f1c-427">要求のダウンロード サイズの合計</span><span class="sxs-lookup"><span data-stu-id="c9f1c-427">The total download size of requests</span></span>  
:::image-end:::  

<span data-ttu-id="c9f1c-428">ブラウザーが各アイテムの圧縮を解除した後のリソースの大きさを確認するには、リソースの圧縮されていないサイズ [を表示します](#display-the-uncompressed-size-of-a-resource)。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-428">To verify how large resources are after the browser uncompresses each item, navigate to [display the uncompressed size of a resource](#display-the-uncompressed-size-of-a-resource).</span></span>  

### <a name="display-the-stack-trace-that-caused-a-request"></a><span data-ttu-id="c9f1c-429">要求を引き起こしたスタック トレースを表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-429">Display the stack trace that caused a request</span></span>  

<span data-ttu-id="c9f1c-430">JavaScript ステートメントがリソースを要求した後、 **イニシエータ** ー列にカーソルを合わせると、要求に至るスタック トレースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-430">After a JavaScript statement requests a resource, hover on the **Initiator** column to display the stack trace leading up to the request.</span></span>  

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

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="リソース要求に至るスタック トレース" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   <span data-ttu-id="c9f1c-432">リソース要求に至るスタック トレース</span><span class="sxs-lookup"><span data-stu-id="c9f1c-432">The stack trace leading up to a resource request</span></span>  
:::image-end:::  

### <a name="display-the-uncompressed-size-of-a-resource"></a><span data-ttu-id="c9f1c-433">リソースの圧縮されていないサイズを表示する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-433">Display the uncompressed size of a resource</span></span>  

<span data-ttu-id="c9f1c-434">[大きな要求 **行を使用する** ] チェック ボックスをオンにして、[サイズ] 列の下部の値 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-434">Turn on the **Use large request rows** checkbox and then review the bottom value of the **Size** column.</span></span>  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="非圧縮リソースの例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   <span data-ttu-id="c9f1c-436">非圧縮リソースの例 \(ネットワーク上で送信されたファイルの圧縮サイズは `jquery-3.3.1.min.js` `29.9 KB` `84.9 KB` \)</span><span class="sxs-lookup"><span data-stu-id="c9f1c-436">An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
:::image-end:::  

## <a name="export-requests-data"></a><span data-ttu-id="c9f1c-437">要求データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="c9f1c-437">Export requests data</span></span>  

### <a name="save-all-network-requests-to-a-har-file"></a><span data-ttu-id="c9f1c-438">すべてのネットワーク要求を HAR ファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-438">Save all network requests to a HAR file</span></span>  

<span data-ttu-id="c9f1c-439">すべてのネットワーク要求を HAR ファイルに保存するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-439">To save all network requests to a HAR file, complete the following steps.</span></span>  

1.  <span data-ttu-id="c9f1c-440">[要求] テーブルの任意の要求にカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-440">Hover on any request in the Requests table and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="c9f1c-441">[コンテンツ **を使用して HAR として保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-441">Choose **Save as HAR with Content**.</span></span>  <span data-ttu-id="c9f1c-442">DevTools は、DevTools を HAR ファイルに開いた後に発生したすべての要求を保存します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-442">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="c9f1c-443">要求をフィルター処理できない。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-443">You are not able to filter requests.</span></span>  <span data-ttu-id="c9f1c-444">また、1 つの要求を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-444">You are also not able to save a single request.</span></span>  

<span data-ttu-id="c9f1c-445">HAR ファイルを保存したら、分析のために DevTools にインポートし戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-445">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="c9f1c-446">HAR ファイルを Requests テーブルにドラッグ アンド ドロップするだけ。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-446">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="[コンテンツを含む HAR として保存] を選択する" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   <span data-ttu-id="c9f1c-448">[コンテンツ **を含む HAR として保存] を選択する**</span><span class="sxs-lookup"><span data-stu-id="c9f1c-448">Choose **Save as HAR with Content**</span></span>  
:::image-end:::  

### <a name="copy-one-or-more-requests-to-the-clipboard"></a><span data-ttu-id="c9f1c-449">1 つ以上の要求をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-449">Copy one or more requests to the clipboard</span></span>  

<span data-ttu-id="c9f1c-450">[要求 **] テーブルの [** 名前] 列で、要求にカーソルを移動し、コンテキスト メニュー \(右クリック\) を開き、[ **コピー**] をポイントし、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-450">Under the **Name** column of the Requests table, hover on a request, open the contextual menu \(right-click\), hover on **Copy**, and choose one of the following options.</span></span>  

| <span data-ttu-id="c9f1c-451">名前</span><span class="sxs-lookup"><span data-stu-id="c9f1c-451">Name</span></span> | <span data-ttu-id="c9f1c-452">詳細</span><span class="sxs-lookup"><span data-stu-id="c9f1c-452">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="c9f1c-453">リンク アドレスのコピー</span><span class="sxs-lookup"><span data-stu-id="c9f1c-453">Copy Link Address</span></span>** | <span data-ttu-id="c9f1c-454">要求の URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-454">Copy the URL of the request to the clipboard.</span></span> |  
| **<span data-ttu-id="c9f1c-455">応答のコピー</span><span class="sxs-lookup"><span data-stu-id="c9f1c-455">Copy Response</span></span>** | <span data-ttu-id="c9f1c-456">応答本文をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-456">Copy the response body to the clipboard.</span></span> |  
| **<span data-ttu-id="c9f1c-457">フェッチとしてコピーする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-457">Copy as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="c9f1c-458">cURL としてコピーする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-458">Copy as cURL</span></span>** | <span data-ttu-id="c9f1c-459">要求を cURL コマンドとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-459">Copy the request as a cURL command.</span></span> |  
| **<span data-ttu-id="c9f1c-460">[すべてフェッチとしてコピー]</span><span class="sxs-lookup"><span data-stu-id="c9f1c-460">Copy All as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="c9f1c-461">すべて cURL としてコピーする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-461">Copy All as cURL</span></span>** | <span data-ttu-id="c9f1c-462">すべての要求を cURL コマンドのチェーンとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-462">Copy all requests as a chain of cURL commands.</span></span> |  
| **<span data-ttu-id="c9f1c-463">[すべて HAR としてコピー]</span><span class="sxs-lookup"><span data-stu-id="c9f1c-463">Copy All as HAR</span></span>** | <span data-ttu-id="c9f1c-464">すべての要求を HAR データとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-464">Copy all requests as HAR data.</span></span> |  

<!--
:::row:::
   :::column span="1":::
      **Copy Link Address**  
   :::column-end:::
   :::column span="2":::
      Copy the URL of the request to the clipboard.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy Response**  
   :::column-end:::
   :::column span="2":::
      Copy the response body to the clipboard.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy as Fetch**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy as cURL**  
   :::column-end:::
   :::column span="2":::
      Copy the request as a cURL command.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as Fetch**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as cURL**  
   :::column-end:::
   :::column span="2":::
      Copy all requests as a chain of cURL commands.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as HAR**  
   :::column-end:::
   :::column span="2":::
      Copy all requests as HAR data.  
   :::column-end:::
:::row-end:::  
-->  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="[応答のコピー] を選択する" lightbox="../media/network-network-requests-copy-response.msft.png":::
   <span data-ttu-id="c9f1c-466">[応答 **のコピー] を選択する**</span><span class="sxs-lookup"><span data-stu-id="c9f1c-466">Choose **Copy Response**</span></span>  
:::image-end:::  

### <a name="copy-formatted-response-json-to-the-clipboard"></a><span data-ttu-id="c9f1c-467">書式設定された応答 JSON をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-467">Copy formatted response JSON to the clipboard</span></span>  

<span data-ttu-id="c9f1c-468">ネットワーク要求を選択し、[ヘッダー] ウィンドウ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-468">Choose a network request and navigate to the **Headers** pane.</span></span>  <span data-ttu-id="c9f1c-469">応答の JSON 値をコピーするには、[要求\*\*\*\* ペイロード] に移動し、JSON 応答コンテンツにカーソルを置き、コンテキスト メニュー \(右クリック\) を開き、[値のコピー] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-469">To copy the JSON value of a response, navigate to **Request payload**, hover on the JSON response content, open the contextual menu \(right-click\), and choose **Copy Value**.</span></span>  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="コンテキスト メニューの [値のコピー]" lightbox="../media/network-header-copy-property-value.msft.png":::
          <span data-ttu-id="c9f1c-471">**コンテキスト メニューの [値** のコピー]</span><span class="sxs-lookup"><span data-stu-id="c9f1c-471">**Copy Value** in contextual menu</span></span>  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="Microsoft Visual Studio書式設定された応答 JSON を持つコード" lightbox="../media/network-header-paste-property-value.msft.png":::
          <span data-ttu-id="c9f1c-473">コードで書式設定された応答 JSON をMicrosoft Visual Studioする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-473">Pasting formatted response JSON in Microsoft Visual Studio Code</span></span>  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="copy-property-values-from-network-requests-to-your-clipboard"></a><span data-ttu-id="c9f1c-474">ネットワーク要求からクリップボードにプロパティ値をコピーする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-474">Copy property values from network requests to your clipboard</span></span>  

<span data-ttu-id="c9f1c-475">ネットワーク要求からクリップボードにプロパティ値をコピーするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-475">To copy property values from network requests to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="c9f1c-476">[ヘッダー] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-476">Open the **Headers** pane.</span></span>  
1.  <span data-ttu-id="c9f1c-477">次のいずれかのヘッダー セクションを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-477">Open one of the following header sections.</span></span>  
    *   <span data-ttu-id="c9f1c-478">要求ペイロード \(JSON\)</span><span class="sxs-lookup"><span data-stu-id="c9f1c-478">Request payload \(JSON\)</span></span>  
    *   <span data-ttu-id="c9f1c-479">フォーム データ</span><span class="sxs-lookup"><span data-stu-id="c9f1c-479">Form Data</span></span>  
    *   <span data-ttu-id="c9f1c-480">クエリ文字列パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9f1c-480">Query String Parameters</span></span>  
    *   <span data-ttu-id="c9f1c-481">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="c9f1c-481">Request Headers</span></span>  
    *   <span data-ttu-id="c9f1c-482">応答ヘッダー</span><span class="sxs-lookup"><span data-stu-id="c9f1c-482">Response Headers</span></span>  
1.  <span data-ttu-id="c9f1c-483">コンテキスト メニュー \(右クリック\) を開き、[値をコピー> **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-483">Open the contextual menu \(right-click\) > **Copy value**.</span></span>  <span data-ttu-id="c9f1c-484">値を任意のエディターに貼り付け、確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-484">You may now paste the value into any editor to review it.</span></span>  
    
## <a name="change-the-layout-of-the-network-panel"></a><span data-ttu-id="c9f1c-485">[ネットワーク] パネルのレイアウトを変更する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-485">Change the layout of the Network panel</span></span>  

<span data-ttu-id="c9f1c-486">重要な情報を集中するには、ネットワーク\*\*\*\* ツール UI のセクションを展開または折りたたみできます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-486">You may expand or collapse sections of the **Network** tool UI to focus important information.</span></span>  

### <a name="hide-the-filters-pane"></a><span data-ttu-id="c9f1c-487">[フィルター] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-487">Hide the Filters pane</span></span>  

<span data-ttu-id="c9f1c-488">既定では、DevTools には [フィルター] ウィンドウ **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-488">By default, DevTools show the **Filters** pane.</span></span>  
<span data-ttu-id="c9f1c-489">[ **フィルター** \( ![ Filter ](../media/filter-icon.msft.png) \) ] を選択して非表示にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-489">Choose **Filter** \(![Filter](../media/filter-icon.msft.png)\) to hide it.</span></span>  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="[フィルターの非表示] ボタン" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   <span data-ttu-id="c9f1c-491">[フィルターの非表示] ボタン</span><span class="sxs-lookup"><span data-stu-id="c9f1c-491">The Hide Filters button</span></span>  
:::image-end:::  

### <a name="use-large-request-rows"></a><span data-ttu-id="c9f1c-492">大きな要求行を使用する</span><span class="sxs-lookup"><span data-stu-id="c9f1c-492">Use large request rows</span></span>  

<span data-ttu-id="c9f1c-493">ネットワーク要求テーブルに空白を追加する場合は、大きな行を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-493">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="c9f1c-494">一部の列では、大きい行を使用する場合にもう少し情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-494">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="c9f1c-495">たとえば、[サイズ] 列の下部の **値は、** 要求の圧縮されていないサイズです。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-495">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="[要求] ウィンドウの大きな要求行の例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   <span data-ttu-id="c9f1c-497">[要求] ウィンドウの大きな要求行**の例**</span><span class="sxs-lookup"><span data-stu-id="c9f1c-497">An example of large request rows in the **Requests** pane</span></span>  
:::image-end:::  

<span data-ttu-id="c9f1c-498">大きな行を有効にするには、[大きな要求行を使用 **する] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-498">To enable large rows, turn on the **Use large request rows** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="[大きな要求行を使用する] チェック ボックス" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   <span data-ttu-id="c9f1c-500">[ **大きな要求行を使用する]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="c9f1c-500">The **Use large request rows** checkbox</span></span>  
:::image-end:::  

### <a name="hide-the-overview-pane"></a><span data-ttu-id="c9f1c-501">[概要] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="c9f1c-501">Hide the Overview pane</span></span>  

<span data-ttu-id="c9f1c-502">既定では、DevTools は [概要] ウィンドウ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-502">By default, DevTools displays the **Overview** pane.</span></span>  <span data-ttu-id="c9f1c-503">非表示にするには、[概要の表示] **チェック ボックスをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-503">To hide it, turn off the **Show Overview** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="[概要の表示] チェック ボックス" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   <span data-ttu-id="c9f1c-505">[ **概要の表示]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="c9f1c-505">The **Show Overview** checkbox</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c9f1c-506">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c9f1c-506">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "プログレッシブ Web アプリのデバッグ |Microsoft Docs"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "データ URL |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "プロキシ サーバー - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="c9f1c-510">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-510">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c9f1c-511">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-511">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c9f1c-513">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c9f1c-513">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
