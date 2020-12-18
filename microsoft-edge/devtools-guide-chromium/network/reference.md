---
description: Microsoft Edge DevTools ネットワーク パネル機能の包括的なリファレンス。
title: ネットワーク分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c600197ffa0e415fe42aecc704a523d1b23f8260
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230755"
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

# <span data-ttu-id="a3f31-104">ネットワーク分析のリファレンス</span><span class="sxs-lookup"><span data-stu-id="a3f31-104">Network Analysis reference</span></span>  

<span data-ttu-id="a3f31-105">Microsoft Edge DevTools ネットワーク分析機能の包括的なリファレンスで、ページの読み込み方法を分析する新しい方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-105">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

## <span data-ttu-id="a3f31-106">ネットワーク要求を記録する</span><span class="sxs-lookup"><span data-stu-id="a3f31-106">Record network requests</span></span>  

<span data-ttu-id="a3f31-107">既定では、DevTools が開いている限り、DevTools はネットワーク パネルにすべてのネットワーク要求を記録します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3f31-107">By default, DevTools record all network requests in the **Network** panel, so long as DevTools is open.</span></span>  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-panel.msft.png":::
   <span data-ttu-id="a3f31-109">[ **ネットワーク]** パネル</span><span class="sxs-lookup"><span data-stu-id="a3f31-109">The **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-110">ネットワーク要求の記録を停止する</span><span class="sxs-lookup"><span data-stu-id="a3f31-110">Stop recording network requests</span></span>  

<span data-ttu-id="a3f31-111">要求の記録を停止するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-111">To stop recording requests, complete the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-112">[ネットワーク] **パネルで** 、[ネットワーク ログの **記録を停止** する] \( [ネットワーク ログの記録 ![ を停止する] ][ImageRecordOnIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-112">On the **Network** panel, choose **Stop recording network log** \(![Stop recording network log][ImageRecordOnIcon]\).</span></span>  <span data-ttu-id="a3f31-113">DevTools が要求を記録しなくなった場合は灰色になります。</span><span class="sxs-lookup"><span data-stu-id="a3f31-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
1.  <span data-ttu-id="a3f31-114">ネットワーク `Control` + `E` パネルにフォーカスがある場合は `Command` + `E` 、\(Windows,Linux\)\*\*\*\* または \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-114">Select `Control`+`E` \(Windows, Linux\) or `Command`+`E` \(macOS\) while the **Network** panel is in focus.</span></span>  

### <span data-ttu-id="a3f31-115">要求をクリアする</span><span class="sxs-lookup"><span data-stu-id="a3f31-115">Clear requests</span></span>  

<span data-ttu-id="a3f31-116">[**要求]** テーブルからすべての要求をクリアするには、[ネットワーク] パネルで [クリア \ (クリア ![ ][ImageClearIcon] \) ] を選択します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3f31-116">Choose **Clear** \(![Clear][ImageClearIcon]\) on the **Network** panel to clear all requests from the Requests table.</span></span>  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="[クリア] ボタン" lightbox="../media/network-network-clear-button.msft.png":::
   <span data-ttu-id="a3f31-118">[ **クリア]** ボタン</span><span class="sxs-lookup"><span data-stu-id="a3f31-118">The **Clear** button</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-119">ページの読み込み時に要求を保存する</span><span class="sxs-lookup"><span data-stu-id="a3f31-119">Save requests across page loads</span></span>  

<span data-ttu-id="a3f31-120">ページの読み込み時に要求を保存するには、[ **ネットワーク** ] パネルで [保持ログ] チェック **ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-120">To save requests across page loads, on the **Network** panel, turn on the **Preserve log** checkbox.</span></span>  <span data-ttu-id="a3f31-121">DevTools は、保持ログを無効にするまで、すべての要求 **を保存します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-121">DevTools saves all requests until you disable **Preserve log**.</span></span>  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="[ログの保持] チェック ボックス" lightbox="../media/network-network-preserve-log.msft.png":::
   <span data-ttu-id="a3f31-123">[ **ログの保持]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="a3f31-123">The **Preserve Log** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-124">ページ読み込み中のスクリーンショットのキャプチャ</span><span class="sxs-lookup"><span data-stu-id="a3f31-124">Capture screenshots during page load</span></span>  

<span data-ttu-id="a3f31-125">スクリーンショットをキャプチャして、ページが読み込むのを待っている間にユーザーに表示される画面を分析します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-125">Capture screenshots to analyze what displays for users while waiting for your page to load.</span></span>  

<span data-ttu-id="a3f31-126">スクリーンショットを有効にするには、[ネットワーク**設定]** を選択し\*\*\*\*、[ネットワーク] パネルで [スクリーンショットのキャプチャ]**チェック ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-126">To enable screenshots, choose **Network settings**, and on the **Network** panel, turn on the **Capture screenshots** checkbox.</span></span>  

<span data-ttu-id="a3f31-127">ネットワーク パネルにフォーカス **がある間に** ページを更新し、スクリーンショットをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-127">Refresh the page while the **Network** panel is in focus to capture screenshots.</span></span>  

<span data-ttu-id="a3f31-128">スクリーンショットをキャプチャした後は、次の方法で操作します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-128">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="a3f31-129">スクリーンショットをポイントすると、そのスクリーンショットがキャプチャされたポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-129">Hover on a screenshot to display the point at which that screenshot was captured.</span></span>  <span data-ttu-id="a3f31-130">[概要] ウィンドウに黄色の線 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-130">A yellow line is displayed on the **Overview** pane.</span></span>  
*   <span data-ttu-id="a3f31-131">スクリーンショットをキャプチャした後に発生した要求をフィルター処理するには、画面のサムネイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-131">Choose the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="a3f31-132">サムネイルをダブルクリックして拡大します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-132">Double-click a thumbnail to zoom into it.</span></span>  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="スクリーンショットにカーソルを合わせる" lightbox="../media/network-network-screenshot-hover.msft.png":::
   <span data-ttu-id="a3f31-134">スクリーンショットにカーソルを合わせる</span><span class="sxs-lookup"><span data-stu-id="a3f31-134">Hover on a screenshot</span></span>  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and choose **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Choose Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Choose Replay XHR  
:::image-end:::  
-->  

## <span data-ttu-id="a3f31-135">読み込み時の動作を変更する</span><span class="sxs-lookup"><span data-stu-id="a3f31-135">Change loading behavior</span></span>  

### <span data-ttu-id="a3f31-136">ブラウザー キャッシュを無効にして初回訪問者をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="a3f31-136">Emulate a first-time visitor by disabling the browser cache</span></span>  

<span data-ttu-id="a3f31-137">初めてのユーザーがサイトを体験する方法をエミュレートするには、[キャッシュを無効にする] チェック **ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-137">To emulate how a first-time user experiences your site, turn on the **Disable cache** checkbox.</span></span>  <span data-ttu-id="a3f31-138">DevTools はブラウザー キャッシュを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-138">DevTools disables the browser cache.</span></span>  <span data-ttu-id="a3f31-139">この機能は、初回のユーザー エクスペリエンスをより正確にエミュレートします。これは、要求は繰り返しアクセス時にブラウザー キャッシュから提供されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-139">This feature more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="[キャッシュを無効にする] チェック ボックス" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   <span data-ttu-id="a3f31-141">[ **キャッシュを無効にする] チェック** ボックス</span><span class="sxs-lookup"><span data-stu-id="a3f31-141">The **Disable Cache** checkbox</span></span>  
:::image-end:::  

#### <span data-ttu-id="a3f31-142">ネットワーク条件ドロワーからブラウザー キャッシュを無効にする</span><span class="sxs-lookup"><span data-stu-id="a3f31-142">Disable the browser cache from the Network Conditions drawer</span></span>  

<span data-ttu-id="a3f31-143">他の DevTools パネルで作業している間にキャッシュを無効にする場合は、ネットワーク条件ドロワーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-143">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="a3f31-144">ネットワーク条件ドロ **ワーを開** きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-144">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="a3f31-145">[キャッシュを無効にする] チェック ボックスをオン **またはオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-145">Turn on \(or off\) the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="a3f31-146">ブラウザー キャッシュを手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="a3f31-146">Manually clear the browser cache</span></span>  

<span data-ttu-id="a3f31-147">ブラウザー キャッシュをいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキスト メニュー \(右クリック\) を開き、[ブラウザー キャッシュのクリア] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-147">To manually clear the browser cache at any time, open the contextual menu \(right-click\) anywhere in the Requests table and choose **Clear Browser Cache**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="ブラウザー キャッシュのクリアを選択する" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   <span data-ttu-id="a3f31-149">ブラウザー **キャッシュのクリアを選択する**</span><span class="sxs-lookup"><span data-stu-id="a3f31-149">Choose **Clear Browser Cache**</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-150">オフラインでエミュレートする</span><span class="sxs-lookup"><span data-stu-id="a3f31-150">Emulate offline</span></span>  

<span data-ttu-id="a3f31-151">新しいクラスの Web アプリ [(Progressive Web Apps)][DevtoolsProgressiveWebApps]は、サービス ワーカーの支援を受け、オフライン **で機能します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-151">A new class of web apps, named [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="a3f31-152">この種類のアプリを構築するときに、データ接続がないデバイスをすばやくシミュレートすると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3f31-152">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="a3f31-153">[オンライン] **ドロップダウン メニュー** を選択し、[ **プリセット**] で検索し、[ **オフライン** ] を選択してオフライン ネットワーク エクスペリエンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-153">Choose the **Online** dropdown menu, search under **Presets**, and choose **Offline** to simulate an offline network experience.</span></span>  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="[オフライン] ドロップダウン メニュー" lightbox="../media/network-network-offline-dropdown.msft.png":::
   <span data-ttu-id="a3f31-155">[ **オフライン]** ドロップダウン メニュー</span><span class="sxs-lookup"><span data-stu-id="a3f31-155">The **Offline** dropdown menu</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-156">低速ネットワーク接続をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="a3f31-156">Emulate slow network connections</span></span>  

<span data-ttu-id="a3f31-157">[オンライン] ドロップダウン メニューからスロー 3G、Fast 3G、その他の接続速度 **を** エミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-157">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="[調整] ドロップダウン メニュー" lightbox="../media/network-network-throttling-menu.msft.png":::
   <span data-ttu-id="a3f31-159">[ **調整]** ドロップダウン メニュー</span><span class="sxs-lookup"><span data-stu-id="a3f31-159">The **Throttling** dropdown menu</span></span>  
:::image-end:::  

<span data-ttu-id="a3f31-160">スロー 3G や Fast 3G など、さまざまなプリセットから選択できます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-160">You may choose from different presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="a3f31-161">独自のカスタム プリセットを追加するには、[調整] メニューを開き、[カスタム追加]**を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-161">To add your own custom presets, open the Throttling menu, and choose **Custom** > **Add**.</span></span>  

<span data-ttu-id="a3f31-162">DevTools では、[ネットワーク] タブの横に警告アイコンが **表示** され、調整が有効になっていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-162">DevTools displays a warning icon next to the **Network** tab to remind you that throttling is enabled.</span></span>  

#### <span data-ttu-id="a3f31-163">ネットワーク条件ドロワーからの低速ネットワーク接続をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="a3f31-163">Emulate slow network connections from the Network Conditions drawer</span></span>  

<span data-ttu-id="a3f31-164">他の DevTools パネルで作業している間にネットワーク接続を調整する場合は、ネットワーク条件ドロワーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-164">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="a3f31-165">ネットワーク条件ドロ **ワーを開** きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-165">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="a3f31-166">[調整] メニューから接続速度 **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-166">Choose your connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="a3f31-167">ブラウザーの Cookie を手動でクリアする</span><span class="sxs-lookup"><span data-stu-id="a3f31-167">Manually clear browser cookies</span></span>  

<span data-ttu-id="a3f31-168">ブラウザーの Cookie をいつでも手動でクリアするには、[要求] テーブルの任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[ブラウザー Cookie のクリア] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-168">To manually clear browser cookies at any time, hover anywhere in the Requests table, open the contextual menu \(right-click\), and choose **Clear Browser Cookies**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="ブラウザーの Cookie のクリアを選択する" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   <span data-ttu-id="a3f31-170">ブラウザー **の Cookie のクリアを選択する**</span><span class="sxs-lookup"><span data-stu-id="a3f31-170">Choose **Clear Browser Cookies**</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-171">ユーザー エージェントを上書きする</span><span class="sxs-lookup"><span data-stu-id="a3f31-171">Override the user agent</span></span>  

<span data-ttu-id="a3f31-172">ユーザー エージェントを手動で上書きするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-172">To manually override the user agent, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-173">ネットワーク条件ドロ **ワーを開** きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-173">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="a3f31-174">[自動的に選択 **] チェック ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-174">Turn off the **Select automatically** checkbox.</span></span>  
1.  <span data-ttu-id="a3f31-175">メニューからユーザー エージェント オプションを選択するか、テキスト ボックスにカスタム エージェント オプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-175">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <span data-ttu-id="a3f31-176">要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a3f31-176">Filter requests</span></span>  

### <span data-ttu-id="a3f31-177">プロパティで要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a3f31-177">Filter requests by properties</span></span>  

<span data-ttu-id="a3f31-178">[フィルター **] テキスト** ボックスを使用して、要求のドメインやサイズなどのプロパティで要求をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-178">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="a3f31-179">テキスト ボックスが表示されていない場合は、[フィルター **]** ウィンドウは非表示である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a3f31-179">If the text box is not displayed, the **Filters** pane is probably hidden.</span></span>  
<span data-ttu-id="a3f31-180">詳細については、[フィルター] ウィンドウ [を非表示にするに移動します](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-180">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="[フィルター] テキスト ボックス" lightbox="../media/network-network-filters-textbox.msft.png":::
   <span data-ttu-id="a3f31-182">[ **フィルター]** テキスト ボックス</span><span class="sxs-lookup"><span data-stu-id="a3f31-182">The **Filter** text box</span></span>  
:::image-end:::  

<span data-ttu-id="a3f31-183">各プロパティをスペースで区切って、複数のプロパティを同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-183">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="a3f31-184">たとえば、1 キロバイトを超えるすべての `mime-type:image/png larger-than:1K` PNG を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-184">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than 1 kilobyte.</span></span>  <span data-ttu-id="a3f31-185">マルチプロパティ フィルターは操作と同 `AND` じです。</span><span class="sxs-lookup"><span data-stu-id="a3f31-185">The multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="a3f31-186">操作は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a3f31-186">operations are currently not supported.</span></span>  

<span data-ttu-id="a3f31-187">サポートされているプロパティの完全な一覧。</span><span class="sxs-lookup"><span data-stu-id="a3f31-187">The complete list of supported properties.</span></span>  

| <span data-ttu-id="a3f31-188">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a3f31-188">Property</span></span> | <span data-ttu-id="a3f31-189">詳細</span><span class="sxs-lookup"><span data-stu-id="a3f31-189">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="a3f31-190">指定されたドメインのリソースのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-190">Only display resources from the specified domain.</span></span>  <span data-ttu-id="a3f31-191">複数のドメインを含めるには、ワイルドカード文字 `*` \( \) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-191">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="a3f31-192">たとえば、終 `*.com` わるすべてのドメイン名のリソースを表示します `.com` 。</span><span class="sxs-lookup"><span data-stu-id="a3f31-192">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="a3f31-193">DevTools は、オートコンプリートドロップダウン メニューに、見つかったすべてのドメインを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-193">DevTools populate the autocomplete dropdown menu with all of the domains that are found.</span></span> |  
| `has-response-header` | <span data-ttu-id="a3f31-194">指定された HTTP 応答ヘッダーを含むリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-194">Displays the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="a3f31-195">DevTools は、見つかったすべての応答ヘッダーをオートコンプリート ドロップダウンに設定します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-195">DevTools populate the autocomplete dropdown with all of the response headers that are found.</span></span> |  
| `is` | <span data-ttu-id="a3f31-196">リソース `is:running` を検索するために `WebSocket` 使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-196">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="a3f31-197">指定したサイズより大きいリソースをバイト単位で表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-197">Displays resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="a3f31-198">値の設定は `1000` 、値を設定するのと同じです `1k` 。</span><span class="sxs-lookup"><span data-stu-id="a3f31-198">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="a3f31-199">指定された HTTP メソッド型で取得されたリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-199">Displays resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="a3f31-200">DevTools は、見つかったすべての HTTP メソッドをドロップダウンに設定します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-200">DevTools populate the dropdown with all of the HTTP methods  that are found.</span></span> |  
| `mime-type` | <span data-ttu-id="a3f31-201">指定された MIME タイプのリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-201">Displays resources of a specified MIME type.</span></span>  <span data-ttu-id="a3f31-202">DevTools は、見つかったすべての MIME タイプをドロップダウンに設定します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-202">DevTools populate the dropdown with all MIME types  that are found.</span></span> |  
| `mixed-content` | <span data-ttu-id="a3f31-203">すべての混在コンテンツ リソース \( \) または現在表示されているリソース `mixed-content:all` \( \) を表示 `mixed-content:displayed` します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-203">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="a3f31-204">保護されていない HTTP \( \) または保護された `scheme:http` HTTPS \( \) で取得したリソースを表示 `scheme:https` します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-204">Displays resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="a3f31-205">指定された値と一致 `Set-Cookie` する属性を持つ `Domain` ヘッダーを持つリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-205">Displays resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="a3f31-206">DevTools は、見つかったすべての Cookie ドメインをオートコンプリートに追加します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-206">DevTools populate the autocomplete with all of the cookie domains that are found.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="a3f31-207">指定された値と一致 `Set-Cookie` する名前のヘッダーを持つリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-207">Displays resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="a3f31-208">DevTools は、見つかったすべての Cookie 名をオートコンプリートに追加します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-208">DevTools populate the autocomplete with all of the cookie names that are found.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="a3f31-209">指定された値と一 `Set-Cookie` 致する値を持つヘッダーを持つリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-209">Displays resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="a3f31-210">DevTools は、見つかったすべての Cookie 値をオートコンプリートに設定します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-210">DevTools populate the autocomplete with all of the cookie values that are found.</span></span> |  
| `status-code` | <span data-ttu-id="a3f31-211">特定の HTTP 状態コードに一致するリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-211">Displays resources that match the specific HTTP status code.</span></span>  <span data-ttu-id="a3f31-212">DevTools は、オートコンプリートドロップダウン メニューに、見つかったすべての状態コードを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-212">DevTools populates the autocomplete dropdown menu with all of the status codes that are found.</span></span> |  

### <span data-ttu-id="a3f31-213">種類別に要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a3f31-213">Filter requests by type</span></span>  

<span data-ttu-id="a3f31-214">要求の種類によって要求をフィルター処理するには、[ネットワーク] パネルで次のいずれかのボタンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-214">To filter requests by request type, choose the one of the following buttons on the **Network** panel.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-215">XHR</span><span class="sxs-lookup"><span data-stu-id="a3f31-215">XHR</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-216">JS</span><span class="sxs-lookup"><span data-stu-id="a3f31-216">JS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-217">CSS</span><span class="sxs-lookup"><span data-stu-id="a3f31-217">CSS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-218">Img</span><span class="sxs-lookup"><span data-stu-id="a3f31-218">Img</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-219">Media</span><span class="sxs-lookup"><span data-stu-id="a3f31-219">Media</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-220">フォント</span><span class="sxs-lookup"><span data-stu-id="a3f31-220">Font</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-221">Doc</span><span class="sxs-lookup"><span data-stu-id="a3f31-221">Doc</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-222">WS</span><span class="sxs-lookup"><span data-stu-id="a3f31-222">WS</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-223">WebSocket。</span><span class="sxs-lookup"><span data-stu-id="a3f31-223">WebSocket.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-224">マニフェスト</span><span class="sxs-lookup"><span data-stu-id="a3f31-224">Manifest</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-225">Other</span><span class="sxs-lookup"><span data-stu-id="a3f31-225">Other</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-226">一覧に表示されないその他の型。</span><span class="sxs-lookup"><span data-stu-id="a3f31-226">Any other type not listed.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="a3f31-227">ボタンが表示されない場合は、[フィルター] **ウィンドウ** が非表示になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3f31-227">If the buttons do not display, the **Filters** pane may be hidden.</span></span>  
<span data-ttu-id="a3f31-228">詳細については、[フィルター] ウィンドウ [を非表示にするに移動します](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-228">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="a3f31-229">複数の種類のフィルターを同時に有効にするには `Control` 、\(Windows,Linux\) または `Command` \(macOS\) を保持してから選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-229">To enable multiple type filters simultaneously, hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose.</span></span>  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="Type フィルターを使用して JS、CSS、および Document リソースを表示する" lightbox="../media/network-network-type-filters.msft.png":::
   <span data-ttu-id="a3f31-231">Type フィルターを使用して JS、CSS、および Document リソースを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-231">Use the Type filters to display JS, CSS, and Document resources</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-232">時間で要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a3f31-232">Filter requests by time</span></span>  

<span data-ttu-id="a3f31-233">[概要] ウィンドウで左または\*\*\*\* 右に選択してドラッグすると、その期間にアクティブだった要求だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-233">Choose and drag left or right on the **Overview** pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="a3f31-234">フィルターは包括的です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-234">The filter is inclusive.</span></span>  <span data-ttu-id="a3f31-235">強調表示された時間中にアクティブだったすべての要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-235">Any request that was active during the highlighted time is shown.</span></span>  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="約 300 ミリ秒で非アクティブだったすべての要求をフィルター処理する" lightbox="../media/network-network-overview-filter.msft.png":::
   <span data-ttu-id="a3f31-237">約 300 ミリ秒で非アクティブだったすべての要求をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a3f31-237">Filter out any requests that were inactive around 300 ms</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-238">データ URL を非表示にする</span><span class="sxs-lookup"><span data-stu-id="a3f31-238">Hide data URLs</span></span>  

<span data-ttu-id="a3f31-239">[データ URL は、][MDNHTTPDataURIs] 他のドキュメントに埋め込まれた小さなファイルです。</span><span class="sxs-lookup"><span data-stu-id="a3f31-239">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="a3f31-240">[要求] テーブルに表示される要求は、データ `data:` URL です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-240">Any request that displays in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="a3f31-241">要求を非表示にする場合は、[データ URL を非表示 **にする] チェック ボックスをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-241">To hide the requests, turn off the **Hide data URLs** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="[データ URL を非表示にする] チェック ボックス" lightbox="../media/network-network-hide-data-urls.msft.png":::
   <span data-ttu-id="a3f31-243">[ **データ URL を非表示にする] チェック** ボックス</span><span class="sxs-lookup"><span data-stu-id="a3f31-243">The **Hide Data URLs** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="a3f31-244">要求を並べ替える</span><span class="sxs-lookup"><span data-stu-id="a3f31-244">Sort requests</span></span>  

<span data-ttu-id="a3f31-245">既定では、[Requests] テーブルの要求は開始時刻で並べ替されますが、他の条件を使用してテーブルを並べ替える場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3f31-245">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <span data-ttu-id="a3f31-246">列で並べ替える</span><span class="sxs-lookup"><span data-stu-id="a3f31-246">Sort by column</span></span>  

<span data-ttu-id="a3f31-247">[要求] 内の任意の列のヘッダーを選択して、その列で要求を並べ替える。</span><span class="sxs-lookup"><span data-stu-id="a3f31-247">Choose the header of any column in the Requests to sort requests by that column.</span></span>  

### <span data-ttu-id="a3f31-248">アクティビティ フェーズでの並べ替え</span><span class="sxs-lookup"><span data-stu-id="a3f31-248">Sort by activity phase</span></span>  

<span data-ttu-id="a3f31-249">ウォーターフォールで要求を並べ替える方法を変更するには、[要求] テーブルのヘッダーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、 **ウォーター**フォールにカーソルを合わせると、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-249">To change how the Waterfall sorts requests, hover on the header of the Requests table, open the contextual menu \(right-click\), hover on **Waterfall**, and choose one of the following options.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-250">開始時刻</span><span class="sxs-lookup"><span data-stu-id="a3f31-250">Start Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-251">最初に開始された要求が一番上にある。</span><span class="sxs-lookup"><span data-stu-id="a3f31-251">The first request that was initiated is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-252">応答時間</span><span class="sxs-lookup"><span data-stu-id="a3f31-252">Response Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-253">最初にダウンロードを開始した要求が一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-253">The first request that started downloading is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-254">終了時刻</span><span class="sxs-lookup"><span data-stu-id="a3f31-254">End Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-255">完了した最初の要求は一番上です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-255">The first request that finished is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-256">Total Duration</span><span class="sxs-lookup"><span data-stu-id="a3f31-256">Total Duration</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-257">最短の接続設定と要求または応答を持つ要求が一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-257">The request with the shortest connection settings and request or response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-258">遅延</span><span class="sxs-lookup"><span data-stu-id="a3f31-258">Latency</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-259">応答の最も短い時間を待った要求が一番上にある。</span><span class="sxs-lookup"><span data-stu-id="a3f31-259">The request that waited the shortest time for a response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="a3f31-260">これらの説明では、各オプションが最短から最長の間でランク付けされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f31-260">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="a3f31-261">[ウォーターフォール] 列の **ヘッダーを選択** して、順序を逆にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-261">Choose the header of the **Waterfall** column to reverse the order.</span></span>  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="ウォーターフォールを合計時間で並べ替える" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   <span data-ttu-id="a3f31-263">合計時間でウォーターフォールを並べ替える \(各バーの明るい部分は待機時間、暗い部分はバイトのダウンロードに費やされた時間\)</span><span class="sxs-lookup"><span data-stu-id="a3f31-263">Sort the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
:::image-end:::  

## <span data-ttu-id="a3f31-264">要求を分析する</span><span class="sxs-lookup"><span data-stu-id="a3f31-264">Analyze requests</span></span>  

<span data-ttu-id="a3f31-265">DevTools が開いている限り、すべての要求をネットワーク パネルに **記録** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-265">So long as DevTools are open, it logs all requests in the **Network** panel.</span></span>  
<span data-ttu-id="a3f31-266">ネットワーク パネルを使用して要求を分析します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-266">Use the Network panel to analyze requests.</span></span>  

### <span data-ttu-id="a3f31-267">要求のログを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-267">Display a log of requests</span></span>  

<span data-ttu-id="a3f31-268">DevTools が開いている間に行われたすべての要求のログを表示するには、Requests テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-268">Use the Requests table to display a log of all requests made while DevTools have been open.</span></span>  <span data-ttu-id="a3f31-269">各アイテムに関する詳細な情報を表示するには、要求を選択またはホバーします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-269">To reveals more information about each item, choose or hover on requests.</span></span>  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="要求テーブル" lightbox="../media/network-network-requests-table.msft.png":::
   <span data-ttu-id="a3f31-271">要求テーブル</span><span class="sxs-lookup"><span data-stu-id="a3f31-271">The Requests table</span></span>  
:::image-end:::  

<span data-ttu-id="a3f31-272">既定では、[要求] テーブルには次の列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-272">The Requests table displays the following columns by default.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-273">名前</span><span class="sxs-lookup"><span data-stu-id="a3f31-273">Name</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-274">リソースのファイル名または識別子。</span><span class="sxs-lookup"><span data-stu-id="a3f31-274">The filename of, or an identifier for, the resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-275">ステータス</span><span class="sxs-lookup"><span data-stu-id="a3f31-275">Status</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-276">HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="a3f31-276">The HTTP status code.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-277">型</span><span class="sxs-lookup"><span data-stu-id="a3f31-277">Type</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-278">要求されたリソースの MIME タイプ。</span><span class="sxs-lookup"><span data-stu-id="a3f31-278">The MIME type of the requested resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-279">Initiator</span><span class="sxs-lookup"><span data-stu-id="a3f31-279">Initiator</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-280">次のオブジェクトまたはプロセスが要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-280">The following objects or processes initiate requests.</span></span>  
      
      *   <span data-ttu-id="a3f31-281">**パーサー**  Microsoft Edge の HTML パーサー。</span><span class="sxs-lookup"><span data-stu-id="a3f31-281">**Parser**  The HTML parser for Microsoft Edge.</span></span>  
      *   <span data-ttu-id="a3f31-282">**リダイレクト**  HTTP リダイレクト。</span><span class="sxs-lookup"><span data-stu-id="a3f31-282">**Redirect**  An HTTP redirect.</span></span>  
      *   <span data-ttu-id="a3f31-283">**スクリプト**  JavaScript 関数。</span><span class="sxs-lookup"><span data-stu-id="a3f31-283">**Script**  A JavaScript function.</span></span>  
      *   <span data-ttu-id="a3f31-284">**その他**  リンクを使用してページに移動したり、アドレス バーに URL を入力したりなど、その他のプロセスまたはアクション。</span><span class="sxs-lookup"><span data-stu-id="a3f31-284">**Other**  Some other process or action, such as navigating to a page using a link or entering a URL in the address bar.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-285">Size</span><span class="sxs-lookup"><span data-stu-id="a3f31-285">Size</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-286">サーバーによって配信される応答ヘッダーと応答本文の合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="a3f31-286">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-287">時間</span><span class="sxs-lookup"><span data-stu-id="a3f31-287">Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-288">要求の開始から、応答の最後のバイトの受信まで、合計時間。</span><span class="sxs-lookup"><span data-stu-id="a3f31-288">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="a3f31-289">ウォーターフォール</span><span class="sxs-lookup"><span data-stu-id="a3f31-289">Waterfall</span></span>](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-290">各要求のアクティビティの視覚的な内訳。</span><span class="sxs-lookup"><span data-stu-id="a3f31-290">A visual breakdown of the activity for each request.</span></span>  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="a3f31-291">列を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="a3f31-291">Add or remove columns</span></span>  

<span data-ttu-id="a3f31-292">[要求] テーブルのヘッダーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、表示または非表示にするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-292">Hover on the header of the Requests table, open the contextual menu \(right-click\), and choose an option to hide or show it.</span></span>  <span data-ttu-id="a3f31-293">現在表示されているオプションでは、各項目の横にチェックマークが付きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-293">Currently displayed options have checkmarks next to each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="[要求] テーブルに列を追加する" lightbox="../media/network-network-requests-add-column.msft.png":::
   <span data-ttu-id="a3f31-295">[要求] テーブルに列を追加する</span><span class="sxs-lookup"><span data-stu-id="a3f31-295">Add a column to the Requests table</span></span>  
:::image-end:::  

#### <span data-ttu-id="a3f31-296">カスタム列を追加する</span><span class="sxs-lookup"><span data-stu-id="a3f31-296">Add custom columns</span></span>  

<span data-ttu-id="a3f31-297">要求テーブルにカスタム列を追加するには、[要求] テーブルのヘッダーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\)\*\*\*\* を開き、[応答ヘッダーヘッダーのヘッダー列の管理] を選択します  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3f31-297">To add a custom column to the Requests table, hover on the header of the Requests table, open the contextual menu \(right-click\), and choose **Response Headers** > **Manage Header Columns**.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="要求テーブルにカスタム列を追加する" lightbox="../media/network-network-requests-add-custom.msft.png":::
   <span data-ttu-id="a3f31-299">要求テーブルにカスタム列を追加する</span><span class="sxs-lookup"><span data-stu-id="a3f31-299">Add a custom column to the Requests table</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-300">要求のタイミング関係を表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-300">Display the timing relationship of requests</span></span>  

<span data-ttu-id="a3f31-301">ウォーターフォールを使用して、要求のタイミング関係を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-301">Use the Waterfall to display the timing relationships of requests.</span></span>  
<span data-ttu-id="a3f31-302">ウォーターフォールの既定の組織では、要求の開始時刻が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-302">The default organization of the Waterfall uses the start time of the requests.</span></span>  
<span data-ttu-id="a3f31-303">したがって、左側の要求は、右側の要求よりも早く開始されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-303">So, requests that are farther to the left started earlier than the requests that are farther to the right.</span></span>  

<span data-ttu-id="a3f31-304">ウォーターフォールを並べ替えるさまざまな方法を確認するには、[アクティビティ別に並べ替え] [フェーズに移動します](#sort-by-activity-phase)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-304">To review the different ways that you may sort the Waterfall, navigate to [Sort by activity phase](#sort-by-activity-phase).</span></span>  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="[要求] ウィンドウのウォーターフォール列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   <span data-ttu-id="a3f31-306">[要求] ウィンドウの **ウォーターフォール** 列</span><span class="sxs-lookup"><span data-stu-id="a3f31-306">The Waterfall column of the **Requests** pane</span></span>  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To review the frames of a WebSocket connection, use the following steps.  

1.  Choose the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Choose the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-choose the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames tab" lightbox="../media/network-frames.msft.png":::
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

### <span data-ttu-id="a3f31-307">応答本文のプレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-307">Display a preview of a response body</span></span>  

<span data-ttu-id="a3f31-308">応答本文のプレビューを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-308">To display a preview of a response body, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-309">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-309">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="a3f31-310">[プレビュー] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-310">Choose the **Preview** tab.</span></span>  

<span data-ttu-id="a3f31-311">[プレビュー] タブは、画像を表示する場合に最も便利です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-311">The Preview tab is mostly useful to display images.</span></span>  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="[プレビュー] タブ" lightbox="../media/network-network-resources-preview.msft.png":::
   <span data-ttu-id="a3f31-313">**プレビュー** タブ</span><span class="sxs-lookup"><span data-stu-id="a3f31-313">The **Preview** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-314">応答本文を表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-314">Display a response body</span></span>  

<span data-ttu-id="a3f31-315">要求に応答本文を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-315">To display the response body to a request, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-316">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-316">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="a3f31-317">[応答] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-317">Choose the **Response** tab.</span></span>  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="[応答] タブ" lightbox="../media/network-network-resources-response.msft.png":::
   <span data-ttu-id="a3f31-319">**応答** タブ</span><span class="sxs-lookup"><span data-stu-id="a3f31-319">The **Response** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-320">HTTP ヘッダーを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-320">Display HTTP headers</span></span>  

<span data-ttu-id="a3f31-321">要求に関する HTTP ヘッダー データを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-321">To display HTTP header data about a request, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-322">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-322">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="a3f31-323">[ヘッダー **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-323">Choose the **Headers** tab.</span></span>  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="[ヘッダー] タブ" lightbox="../media/network-resources-headers.msft.png":::
   <span data-ttu-id="a3f31-325">**ヘッダー** タブ</span><span class="sxs-lookup"><span data-stu-id="a3f31-325">The **Headers** tab</span></span>  
:::image-end:::  

#### <span data-ttu-id="a3f31-326">HTTP ヘッダー ソースの表示</span><span class="sxs-lookup"><span data-stu-id="a3f31-326">Display HTTP header source</span></span>  

<span data-ttu-id="a3f31-327">既定では、[ヘッダー] タブにはヘッダー名がアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-327">By default, the Headers tab shows header names alphabetically.</span></span>  <span data-ttu-id="a3f31-328">HTTP ヘッダー名を受け取った順序で表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-328">To dsiplay the HTTP header names in the order received, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-329">関心のある **要求** の [ヘッダー] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-329">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="a3f31-330">詳細については、「HTTP ヘッダーを表示 [する」に移動します](#display-http-headers)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-330">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="a3f31-331">[**要求ヘッダー] セクションまたは**[応答ヘッダー] セクションの横にあるビュー**ソースを選択**します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3f31-331">Choose **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <span data-ttu-id="a3f31-332">クエリ文字列パラメーターを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-332">Display query string parameters</span></span>  

<span data-ttu-id="a3f31-333">URL のクエリ文字列パラメーターを人間が判読できる形式で表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-333">To display the query string parameters of a URL in a human-readable format, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-334">関心のある **要求** の [ヘッダー] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-334">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="a3f31-335">詳細については、「HTTP ヘッダーを表示 [する」に移動します](#display-http-headers)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-335">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="a3f31-336">[クエリ文字列パラメーター **] セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-336">Go to the **Query String Parameters** section.</span></span>  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="[クエリ文字列パラメーター] セクション" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   <span data-ttu-id="a3f31-338">[ **クエリ文字列パラメーター]** セクション</span><span class="sxs-lookup"><span data-stu-id="a3f31-338">The **Query String Parameters** section</span></span>  
:::image-end:::  

#### <span data-ttu-id="a3f31-339">クエリ文字列パラメーター ソースを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-339">Display query string parameters source</span></span>  

<span data-ttu-id="a3f31-340">要求のクエリ文字列パラメーター ソースを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-340">To display the query string parameter source of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-341">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-341">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="a3f31-342">詳細については、クエリ文字列パラメーター [を表示するに移動します](#display-query-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-342">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="a3f31-343">ビュー **ソースを選択します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-343">Choose **view source**.</span></span>  

#### <span data-ttu-id="a3f31-344">URL エンコードされたクエリ文字列パラメーターを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-344">Display URL-encoded query string parameters</span></span>  

<span data-ttu-id="a3f31-345">クエリ文字列パラメーターを人間が読み取り可能な形式で表示し、エンコードを保持するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-345">To display query string parameters in a human-readable format, but with encodings preserved, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-346">[クエリ文字列パラメーター] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-346">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="a3f31-347">詳細については、クエリ文字列パラメーター [を表示するに移動します](#display-query-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-347">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="a3f31-348">エンコード **されたビュー URL を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-348">Choose **view URL encoded**.</span></span>  

### <span data-ttu-id="a3f31-349">Cookie の表示</span><span class="sxs-lookup"><span data-stu-id="a3f31-349">Display cookies</span></span>  

<span data-ttu-id="a3f31-350">要求の HTTP ヘッダーで送信された Cookie を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-350">To display the cookies sent in the HTTP header of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-351">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-351">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="a3f31-352">[Cookie] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-352">Choose the **Cookies** tab.</span></span>  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="[Cookie] タブ" lightbox="../media/network-network-resources-cookies.msft.png":::
   <span data-ttu-id="a3f31-354">[Cookie] タブ</span><span class="sxs-lookup"><span data-stu-id="a3f31-354">The Cookies tab</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-355">要求のタイミングの内訳を表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-355">Display the timing breakdown of a request</span></span>  

<span data-ttu-id="a3f31-356">要求のタイミングの内訳を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-356">To display the timing breakdown of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-357">[要求] テーブルの [名前\*\*\*\*] 列で、要求の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-357">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="a3f31-358">[タイミング **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-358">Choose the **Timing** tab.</span></span>  

<span data-ttu-id="a3f31-359">データに高速にアクセスするには、[タイミングの詳細をプレビューする [] に移動します](#preview-a-timing-breakdown)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-359">For a faster way to access the data, navigate to [Preview a timing breakdown](#preview-a-timing-breakdown).</span></span>  

<span data-ttu-id="a3f31-360">[タイミング] タブに表示される各フェーズの詳細については、説明\*\*\*\* されているタイミングブレークダウン フェーズ[に移動します](#timing-breakdown-phases-explained)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-360">For more information about each of the phases that may be displayed in the **Timing** tab, navigate to [Timing breakdown phases explained](#timing-breakdown-phases-explained).</span></span>  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="[タイミング] タブ" lightbox="../media/network-network-resources-timing.msft.png":::
   <span data-ttu-id="a3f31-362">**タイミング** タブ</span><span class="sxs-lookup"><span data-stu-id="a3f31-362">The **Timing** tab</span></span>  
:::image-end:::  

<span data-ttu-id="a3f31-363">各フェーズの詳細。</span><span class="sxs-lookup"><span data-stu-id="a3f31-363">More information about each of the phases.</span></span>  

<span data-ttu-id="a3f31-364">表示にアクセスする方法の詳細については、[表示タイミングの詳細 [] に移動します](#display-the-timing-breakdown-of-a-request)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-364">For more information about accessing the display, navigate to [Display timing breakdown](#display-the-timing-breakdown-of-a-request).</span></span>  

#### <span data-ttu-id="a3f31-365">タイミングの詳細をプレビューする</span><span class="sxs-lookup"><span data-stu-id="a3f31-365">Preview a timing breakdown</span></span>  

<span data-ttu-id="a3f31-366">要求のタイミングの詳細のプレビューを表示するには、[要求] テーブルの **[ウォーター** フォール] 列で、要求のエントリをポイントします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-366">To display a preview of the timing breakdown of a request, in the **Waterfall** column of the Requests table, hover on the entry for the request.</span></span>  

<span data-ttu-id="a3f31-367">ホバーせずにデータにアクセスする方法の詳細については、「要求のタイミングの内訳を表示 [する」に移動します](#display-the-timing-breakdown-of-a-request)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-367">For more information about how to access the data without hovering, navigate to [Display the timing breakdown of a request](#display-the-timing-breakdown-of-a-request).</span></span>  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text=">要求のタイミングの詳細をプレビューする" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   <span data-ttu-id="a3f31-369">要求のタイミングの詳細をプレビューする</span><span class="sxs-lookup"><span data-stu-id="a3f31-369">Preview the timing breakdown of a request</span></span>  
:::image-end:::  

#### <span data-ttu-id="a3f31-370">説明されているタイミングブレークダウン フェーズ</span><span class="sxs-lookup"><span data-stu-id="a3f31-370">Timing breakdown phases explained</span></span>  

<span data-ttu-id="a3f31-371">[タイミング] タブに表示される各フェーズ**の詳細。**</span><span class="sxs-lookup"><span data-stu-id="a3f31-371">More information about each of the phases that may display in the **Timing** tab.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-372">キューに入る</span><span class="sxs-lookup"><span data-stu-id="a3f31-372">Queueing</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-373">ブラウザーは、次の場合に要求をキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-373">The browser queues requests when any of the following are true.</span></span>  
      
      *   <span data-ttu-id="a3f31-374">優先度の高い要求が存在します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-374">Higher priority requests exist.</span></span>  
      *   <span data-ttu-id="a3f31-375">同じオリジンに対して 6 つの TCP 接続が開いている。これは制限です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-375">Six TCP connections are open for the same origin, which is the limit.</span></span>  <span data-ttu-id="a3f31-376">HTTP/1.0 および HTTP/1.1 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-376">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
      *   <span data-ttu-id="a3f31-377">ブラウザーは、ディスク キャッシュ内の領域を一時的に割り当て中です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-377">The browser is briefly allocating space in the disk cache.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-378">ストール</span><span class="sxs-lookup"><span data-stu-id="a3f31-378">Stalled</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-379">要求は、「キュー」で説明されている理由の何らかの理由で **ストールします**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-379">The request is stalled for any of the reasons described in **Queueing**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-380">DNS 参照</span><span class="sxs-lookup"><span data-stu-id="a3f31-380">DNS Lookup</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-381">ブラウザーが要求の IP アドレスを解決しています。</span><span class="sxs-lookup"><span data-stu-id="a3f31-381">The browser is resolving the IP address for the request.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-382">初期接続</span><span class="sxs-lookup"><span data-stu-id="a3f31-382">Initial connection</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-383">ブラウザーは、TCP ハンドシェイク、TCP 再試行、および Secure Socket Layer のネゴシエートを含む接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-383">The browser establishes a connection including TCP handshakes, TCP retries, and negotiates a Secure Socket Layer.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-384">プロキシ ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a3f31-384">Proxy negotiation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-385">ブラウザーがプロキシ サーバーと要求をネゴ [シエートしています][WikiProxyServer]。</span><span class="sxs-lookup"><span data-stu-id="a3f31-385">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-386">送信された要求</span><span class="sxs-lookup"><span data-stu-id="a3f31-386">Request sent</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-387">要求が送信されています。</span><span class="sxs-lookup"><span data-stu-id="a3f31-387">The request is being sent.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-388">ServiceWorker の準備</span><span class="sxs-lookup"><span data-stu-id="a3f31-388">ServiceWorker Preparation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-389">ブラウザーがサービス ワーカーを開始しています。</span><span class="sxs-lookup"><span data-stu-id="a3f31-389">The browser is starting the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-390">ServiceWorker への要求</span><span class="sxs-lookup"><span data-stu-id="a3f31-390">Request to ServiceWorker</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-391">要求はサービス ワーカーに送信されています。</span><span class="sxs-lookup"><span data-stu-id="a3f31-391">The request is being sent to the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-392">Waiting \(TTFB\)</span><span class="sxs-lookup"><span data-stu-id="a3f31-392">Waiting \(TTFB\)</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-393">ブラウザーは応答の最初のバイトを待機しています。</span><span class="sxs-lookup"><span data-stu-id="a3f31-393">The browser is waiting for the first byte of a response.</span></span>  <span data-ttu-id="a3f31-394">TTFB は、Time To First Byte を表します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-394">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="a3f31-395">このタイミングには、1 回の待機時間と、サーバーが応答の準備にかかった時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-395">This timing includes one round trip of latency and the time the server took to prepare the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-396">コンテンツのダウンロード</span><span class="sxs-lookup"><span data-stu-id="a3f31-396">Content Download</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-397">ブラウザーが応答を受信しています。</span><span class="sxs-lookup"><span data-stu-id="a3f31-397">The browser is receiving the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-398">プッシュの受信</span><span class="sxs-lookup"><span data-stu-id="a3f31-398">Receiving Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-399">ブラウザーは HTTP/2 サーバー プッシュを介してこの応答のデータを受信しています。</span><span class="sxs-lookup"><span data-stu-id="a3f31-399">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a3f31-400">プッシュ読み取り</span><span class="sxs-lookup"><span data-stu-id="a3f31-400">Reading Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="a3f31-401">ブラウザーは、以前に受信したローカル データを読み取り中です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-401">The browser is reading the local data previously received.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="a3f31-402">開始者と依存関係を表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-402">Display initiators and dependencies</span></span>  

<span data-ttu-id="a3f31-403">要求の開始者と依存関係を表示するには、[要求] テーブルで要求を保持して `Shift` ポイントします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-403">To display the initiators and dependencies of a request, hold `Shift`and hover on the request in the Requests table.</span></span>  <span data-ttu-id="a3f31-404">DevTools の色: 開始者は緑色で表示され、依存関係は赤で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-404">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="要求の開始者と依存関係を表示する" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   <span data-ttu-id="a3f31-406">要求の開始者と依存関係を表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-406">Display the initiators and dependencies of a request</span></span>  
:::image-end:::  

<span data-ttu-id="a3f31-407">時間順に Requests テーブルが並べらた場合、行にカーソルを合わせると、前の行に緑色の要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-407">When the Requests table is ordered chronologically, if you hover on a line, the line preceding it displays a green request.</span></span>  <span data-ttu-id="a3f31-408">緑色の要求は、依存関係の開始者です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-408">The green request is the initiator of the dependency.</span></span>  <span data-ttu-id="a3f31-409">それより前の行に別の緑色の要求が表示される場合、その上位の要求は開始者の開始者になります。</span><span class="sxs-lookup"><span data-stu-id="a3f31-409">If another green request is displayed on the line before that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="a3f31-410">などなど。</span><span class="sxs-lookup"><span data-stu-id="a3f31-410">And so on.</span></span>  

### <span data-ttu-id="a3f31-411">読み込みイベントを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-411">Display load events</span></span>  

<span data-ttu-id="a3f31-412">DevTools は、ネットワーク パネル上の複数の場所にイベントの `DOMContentLoaded` `load` タイミングを **表示** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-412">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the **Network** panel.</span></span>  <span data-ttu-id="a3f31-413">イベント `DOMContentLoaded` は青色で、イベントは `load` 赤です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-413">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="DOMContentLoaded の場所とネットワーク パネル上のイベントの読み込み" lightbox="../media/network-network-requests-load-events.msft.png":::
   <span data-ttu-id="a3f31-415">ネットワーク パネル上 `DOMContentLoaded` の `load` イベント **の** 場所</span><span class="sxs-lookup"><span data-stu-id="a3f31-415">The locations of the `DOMContentLoaded` and `load` events on the **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-416">要求の総数を表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-416">Display the total number of requests</span></span>  

<span data-ttu-id="a3f31-417">要求の総数は、[ネットワーク] パネルの下部\*\*\*\* にある [概要] ウィンドウに**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-417">The total number of requests is listed in the **Summary** pane, at the bottom of the **Network** panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="a3f31-418">この番号は、DevTools が開いた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-418">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="a3f31-419">DevTools が開く前に他の要求が発生した場合、それらの要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="a3f31-419">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="DevTools が開いた後の要求の総数" lightbox="../media/network-network-total-requests.msft.png":::
   <span data-ttu-id="a3f31-421">DevTools が開いた後の要求の総数</span><span class="sxs-lookup"><span data-stu-id="a3f31-421">The total number of requests since DevTools were opened</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-422">ダウンロード の合計サイズを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-422">Display the total download size</span></span>  

<span data-ttu-id="a3f31-423">要求の合計ダウンロード サイズは、[概要] ウィンドウ\*\*\*\* の [ネットワーク] パネルの下部に**一覧表示**されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-423">The total download size of requests is listed in the **Summary** pane, at the bottom of the **Network** panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="a3f31-424">この番号は、DevTools が開いた後にログに記録された要求のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-424">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="a3f31-425">DevTools が開く前に他の要求が発生した場合、以前の要求はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="a3f31-425">If other requests occurred before DevTools was opened, the previous requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="要求の合計ダウンロード サイズ" lightbox="../media/network-network-total-download-size.msft.png":::
   <span data-ttu-id="a3f31-427">要求の合計ダウンロード サイズ</span><span class="sxs-lookup"><span data-stu-id="a3f31-427">The total download size of requests</span></span>  
:::image-end:::  

<span data-ttu-id="a3f31-428">ブラウザーが各アイテムの圧縮を解除した後のリソースの大きさを確認するには、リソースの圧縮されていないサイズを表示 [します](#display-the-uncompressed-size-of-a-resource)。</span><span class="sxs-lookup"><span data-stu-id="a3f31-428">To verify how large resources are after the browser uncompresses each item, navigate to [display the uncompressed size of a resource](#display-the-uncompressed-size-of-a-resource).</span></span>  

### <span data-ttu-id="a3f31-429">要求を発生したスタック トレースを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-429">Display the stack trace that caused a request</span></span>  

<span data-ttu-id="a3f31-430">JavaScript ステートメントがリソースを要求した後 **、Initiator** 列をポイントして、要求に至るスタック トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-430">After a JavaScript statement requests a resource, hover on the **Initiator** column to display the stack trace leading up to the request.</span></span>  

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
   <span data-ttu-id="a3f31-432">リソース要求に至るスタック トレース</span><span class="sxs-lookup"><span data-stu-id="a3f31-432">The stack trace leading up to a resource request</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-433">リソースの圧縮されていないサイズを表示する</span><span class="sxs-lookup"><span data-stu-id="a3f31-433">Display the uncompressed size of a resource</span></span>  

<span data-ttu-id="a3f31-434">[大きな要求 **行を使用する]** チェック ボックスをオンにし、[サイズ] 列の一番下の値 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-434">Turn on the **Use large request rows** checkbox and then review the bottom value of the **Size** column.</span></span>  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="圧縮されていないリソースの例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   <span data-ttu-id="a3f31-436">圧縮されていないリソース \(ネットワーク上で送信されたファイルの圧縮されたサイズは `jquery-3.3.1.min.js` `29.9 KB` `84.9 KB` \) の例です。</span><span class="sxs-lookup"><span data-stu-id="a3f31-436">An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
:::image-end:::  

## <span data-ttu-id="a3f31-437">要求データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a3f31-437">Export requests data</span></span>  

### <span data-ttu-id="a3f31-438">すべてのネットワーク要求を HAR ファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="a3f31-438">Save all network requests to a HAR file</span></span>  

<span data-ttu-id="a3f31-439">すべてのネットワーク要求を HAR ファイルに保存するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-439">To save all network requests to a HAR file, complete the following steps.</span></span>  

1.  <span data-ttu-id="a3f31-440">[要求] テーブル内の任意の要求をポイントし、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-440">Hover on any request in the Requests table and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="a3f31-441">Choose **Save as HAR with Content**.</span><span class="sxs-lookup"><span data-stu-id="a3f31-441">Choose **Save as HAR with Content**.</span></span>  <span data-ttu-id="a3f31-442">DevTools は、DevTools を開いた後に発生した要求を HAR ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-442">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="a3f31-443">要求をフィルター処理できない。</span><span class="sxs-lookup"><span data-stu-id="a3f31-443">You are not able to filter requests.</span></span>  <span data-ttu-id="a3f31-444">また、1 つの要求を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f31-444">You are also not able to save a single request.</span></span>  

<span data-ttu-id="a3f31-445">HAR ファイルを保存したら、分析のために DevTools にインポートし戻します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-445">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="a3f31-446">HAR ファイルを Requests テーブルにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-446">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="Choose Save as HAR with Content" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   <span data-ttu-id="a3f31-448">Choose **Save as HAR with Content**</span><span class="sxs-lookup"><span data-stu-id="a3f31-448">Choose **Save as HAR with Content**</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-449">1 つ以上の要求をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="a3f31-449">Copy one or more requests to the clipboard</span></span>  

<span data-ttu-id="a3f31-450">[要求\*\*\*\*] テーブルの [名前] 列で、要求をポイントし、コンテキスト メニュー \(右クリック\) を開き、[コピー] をポイントして、次のいずれかのオプションを選択します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3f31-450">Under the **Name** column of the Requests table, hover on a request, open the contextual menu \(right-click\), hover on **Copy**, and choose one of the following options.</span></span>  

| <span data-ttu-id="a3f31-451">名前</span><span class="sxs-lookup"><span data-stu-id="a3f31-451">Name</span></span> | <span data-ttu-id="a3f31-452">詳細</span><span class="sxs-lookup"><span data-stu-id="a3f31-452">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="a3f31-453">リンク アドレスのコピー</span><span class="sxs-lookup"><span data-stu-id="a3f31-453">Copy Link Address</span></span>** | <span data-ttu-id="a3f31-454">要求の URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-454">Copy the URL of the request to the clipboard.</span></span> |  
| **<span data-ttu-id="a3f31-455">応答のコピー</span><span class="sxs-lookup"><span data-stu-id="a3f31-455">Copy Response</span></span>** | <span data-ttu-id="a3f31-456">応答本文をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-456">Copy the response body to the clipboard.</span></span> |  
| **<span data-ttu-id="a3f31-457">フェッチとしてコピー</span><span class="sxs-lookup"><span data-stu-id="a3f31-457">Copy as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="a3f31-458">cURL としてコピー</span><span class="sxs-lookup"><span data-stu-id="a3f31-458">Copy as cURL</span></span>** | <span data-ttu-id="a3f31-459">要求を cURL コマンドとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-459">Copy the request as a cURL command.</span></span> |  
| **<span data-ttu-id="a3f31-460">すべてフェッチとしてコピー</span><span class="sxs-lookup"><span data-stu-id="a3f31-460">Copy All as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="a3f31-461">すべて cURL としてコピー</span><span class="sxs-lookup"><span data-stu-id="a3f31-461">Copy All as cURL</span></span>** | <span data-ttu-id="a3f31-462">すべての要求を cURL コマンドのチェーンとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-462">Copy all requests as a chain of cURL commands.</span></span> |  
| **<span data-ttu-id="a3f31-463">Copy All as HAR</span><span class="sxs-lookup"><span data-stu-id="a3f31-463">Copy All as HAR</span></span>** | <span data-ttu-id="a3f31-464">すべての要求を HAR データとしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-464">Copy all requests as HAR data.</span></span> |  

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

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="Choose Copy Response" lightbox="../media/network-network-requests-copy-response.msft.png":::
   <span data-ttu-id="a3f31-466">Choose **Copy Response**</span><span class="sxs-lookup"><span data-stu-id="a3f31-466">Choose **Copy Response**</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-467">書式設定された応答 JSON をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="a3f31-467">Copy formatted response JSON to the clipboard</span></span>  

<span data-ttu-id="a3f31-468">ネットワーク要求を選択し、[ヘッダー] ウィンドウ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-468">Choose a network request and navigate to the **Headers** pane.</span></span>  <span data-ttu-id="a3f31-469">応答の JSON 値をコピーするには、[要求\*\*\*\* ペイロード] に移動し、JSON 応答コンテンツにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[値のコピー] を選択**します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-469">To copy the JSON value of a response, navigate to **Request payload**, hover on the JSON response content, open the contextual menu \(right-click\), and choose **Copy Value**.</span></span>  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="コンテキスト メニューの [値のコピー]" lightbox="../media/network-header-copy-property-value.msft.png":::
          <span data-ttu-id="a3f31-471">**コンテキスト メニューの [値** のコピー]</span><span class="sxs-lookup"><span data-stu-id="a3f31-471">**Copy Value** in contextual menu</span></span>  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="Visual Studio応答 JSON を含むコード" lightbox="../media/network-header-paste-property-value.msft.png":::
          <span data-ttu-id="a3f31-473">書式設定された応答 JSON を Visual Studio コードに貼り付け</span><span class="sxs-lookup"><span data-stu-id="a3f31-473">Pasting formatted response JSON in Visual Studio Code</span></span>  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="a3f31-474">ネットワーク要求からクリップボードにプロパティ値をコピーする</span><span class="sxs-lookup"><span data-stu-id="a3f31-474">Copy property values from network requests to your clipboard</span></span>  

<span data-ttu-id="a3f31-475">ネットワーク要求からクリップボードにプロパティ値をコピーするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-475">To copy property values from network requests to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="a3f31-476">[ヘッダー **] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-476">Open the **Headers** pane.</span></span>  
1.  <span data-ttu-id="a3f31-477">次のいずれかのヘッダー セクションを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-477">Open one of the following header sections.</span></span>  
    *   <span data-ttu-id="a3f31-478">要求ペイロード \(JSON\)</span><span class="sxs-lookup"><span data-stu-id="a3f31-478">Request payload \(JSON\)</span></span>  
    *   <span data-ttu-id="a3f31-479">フォーム データ</span><span class="sxs-lookup"><span data-stu-id="a3f31-479">Form Data</span></span>  
    *   <span data-ttu-id="a3f31-480">クエリ文字列パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3f31-480">Query String Parameters</span></span>  
    *   <span data-ttu-id="a3f31-481">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a3f31-481">Request Headers</span></span>  
    *   <span data-ttu-id="a3f31-482">応答ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a3f31-482">Response Headers</span></span>  
1.  <span data-ttu-id="a3f31-483">コンテキスト メニュー \(右クリック\) を開き、[値を> **します**。</span><span class="sxs-lookup"><span data-stu-id="a3f31-483">Open the contextual menu \(right-click\) > **Copy value**.</span></span>  <span data-ttu-id="a3f31-484">これで、任意のエディターに値を貼り付け、確認できます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-484">You can now paste the value into any editor to review it.</span></span>  
    
## <span data-ttu-id="a3f31-485">ネットワーク パネルのレイアウトを変更する</span><span class="sxs-lookup"><span data-stu-id="a3f31-485">Change the layout of the Network panel</span></span>  

<span data-ttu-id="a3f31-486">ネットワーク パネル UI のセクションを展開または折りたたみ、 **重要な情報** に集中することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-486">You may expand or collapse sections of the **Network** panel UI to focus important information.</span></span>  

### <span data-ttu-id="a3f31-487">[フィルター] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="a3f31-487">Hide the Filters pane</span></span>  

<span data-ttu-id="a3f31-488">既定では、DevTools には [フィルター] ウィンドウ **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-488">By default, DevTools show the **Filters** pane.</span></span>  
<span data-ttu-id="a3f31-489">Choose **Filter** \( ![ Filter ][ImageFilterIcon] \) to hide it.</span><span class="sxs-lookup"><span data-stu-id="a3f31-489">Choose **Filter** \(![Filter][ImageFilterIcon]\) to hide it.</span></span>  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="[フィルターの非表示] ボタン" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   <span data-ttu-id="a3f31-491">[フィルターの非表示] ボタン</span><span class="sxs-lookup"><span data-stu-id="a3f31-491">The Hide Filters button</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-492">大きな要求行を使用する</span><span class="sxs-lookup"><span data-stu-id="a3f31-492">Use large request rows</span></span>  

<span data-ttu-id="a3f31-493">ネットワーク要求テーブルに空白を追加する場合は、大きな行を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-493">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="a3f31-494">一部の列は、大きな行を使用する場合に、もう少し多くの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a3f31-494">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="a3f31-495">たとえば、[Size] 列の下部\*\*\*\* の値は、要求の圧縮されていないサイズです。</span><span class="sxs-lookup"><span data-stu-id="a3f31-495">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="[要求] ウィンドウの大きな要求行の例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   <span data-ttu-id="a3f31-497">[要求] ウィンドウの大きな要求行 **の** 例</span><span class="sxs-lookup"><span data-stu-id="a3f31-497">An example of large request rows in the **Requests** pane</span></span>  
:::image-end:::  

<span data-ttu-id="a3f31-498">大きい行を有効にするには、[大きい要求行を使用 **する] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-498">To enable large rows, turn on the **Use large request rows** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="[大きな要求行を使用する] チェック ボックス" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   <span data-ttu-id="a3f31-500">[ **大きな要求行を使用する] チェック** ボックス</span><span class="sxs-lookup"><span data-stu-id="a3f31-500">The **Use large request rows** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="a3f31-501">[概要] ウィンドウを非表示にする</span><span class="sxs-lookup"><span data-stu-id="a3f31-501">Hide the Overview pane</span></span>  

<span data-ttu-id="a3f31-502">既定では、DevTools には [概要] ウィンドウ **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-502">By default, DevTools displays the **Overview** pane.</span></span>  <span data-ttu-id="a3f31-503">非表示にする場合は、[概要の表示 **] チェック ボックスをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="a3f31-503">To hide it, turn off the **Show Overview** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="[概要の表示] チェック ボックス" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   <span data-ttu-id="a3f31-505">[ **概要の表示]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="a3f31-505">The **Show Overview** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="a3f31-506">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a3f31-506">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "段階的な Web アプリをデバッグする |Microsoft Docs"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "データ URL |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "プロキシ サーバー - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="a3f31-510">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3f31-510">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a3f31-511">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="a3f31-511">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a3f31-513">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a3f31-513">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
