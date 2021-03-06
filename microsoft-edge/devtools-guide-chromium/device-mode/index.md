---
description: Microsoft Edge の仮想デバイスを使用して、モバイル ファースト Web サイトを構築します。
title: Microsoft Edge DevTools でモバイル デバイスをエミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, エミュレーション, デバイス, シミュレーション, モバイル
ms.openlocfilehash: 1a83dece95acba386385bfea035a9e2c91639240
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398785"
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

# <a name="emulate-mobile-devices-in-microsoft-edge-devtools"></a><span data-ttu-id="dba41-104">Microsoft Edge DevTools でモバイル デバイスをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="dba41-104">Emulate mobile devices in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="dba41-105">デバイス **エミュレーションを使用** して、モバイル デバイスでのページの外観と応答を概算します。</span><span class="sxs-lookup"><span data-stu-id="dba41-105">Use **Device emulation** to approximate how your page looks and responds on a mobile device.</span></span>  <span data-ttu-id="dba41-106">Microsoft Edge DevTools には、モバイル デバイスのエミュレートに役立つ機能のコレクションが提供されています。</span><span class="sxs-lookup"><span data-stu-id="dba41-106">The Microsoft Edge DevTools provide a collection of features to help you emulate mobile devices.</span></span>  <span data-ttu-id="dba41-107">コレクションには、次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dba41-107">The collection includes the following features.</span></span>  

*   [<span data-ttu-id="dba41-108">モバイル ビューポートをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="dba41-108">Simulate a mobile viewport</span></span>](#simulate-a-mobile-viewport)  
*   [<span data-ttu-id="dba41-109">ネットワークの調整</span><span class="sxs-lookup"><span data-stu-id="dba41-109">Throttle the network</span></span>](#throttle-the-network-only)  
*   [<span data-ttu-id="dba41-110">CPU の調整</span><span class="sxs-lookup"><span data-stu-id="dba41-110">Throttle the CPU</span></span>](#throttle-the-cpu-only)  
*   [<span data-ttu-id="dba41-111">位置情報をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="dba41-111">Simulate geolocation</span></span>](#override-geolocation)  
*   [<span data-ttu-id="dba41-112">方向を設定する</span><span class="sxs-lookup"><span data-stu-id="dba41-112">Set orientation</span></span>](#set-orientation)  
*   [<span data-ttu-id="dba41-113">ユーザー エージェントの文字列を設定する</span><span class="sxs-lookup"><span data-stu-id="dba41-113">Set the user agent string</span></span>](#set-user-agent-string)  

## <a name="limitations"></a><span data-ttu-id="dba41-114">制限事項</span><span class="sxs-lookup"><span data-stu-id="dba41-114">Limitations</span></span>  

<span data-ttu-id="dba41-115">**デバイス エミュレーション** は、 [モバイル デバイス][WikiApproximation] 上のページの外観の 1 次近似です。</span><span class="sxs-lookup"><span data-stu-id="dba41-115">**Device emulation** is a [first-order approximation][WikiApproximation] of the look and feel of your page on a mobile device.</span></span>  <span data-ttu-id="dba41-116">**デバイス エミュレーション** は、実際にはモバイル デバイス上でコードを実行しない。</span><span class="sxs-lookup"><span data-stu-id="dba41-116">**Device emulation** does not actually run your code on a mobile device.</span></span>  <span data-ttu-id="dba41-117">代わりに、ラップトップまたはデスクトップからモバイル ユーザー エクスペリエンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="dba41-117">Instead you simulate the mobile user experience from your laptop or desktop.</span></span>  

<span data-ttu-id="dba41-118">モバイル デバイスの一部の側面は、DevTools ではエミュレートされません。</span><span class="sxs-lookup"><span data-stu-id="dba41-118">Some aspects of mobile devices are never emulated in DevTools.</span></span>  <span data-ttu-id="dba41-119">たとえば、モバイル CPU のアーキテクチャは、ラップトップまたはデスクトップ CPU のアーキテクチャとは異なります。</span><span class="sxs-lookup"><span data-stu-id="dba41-119">For example, the architecture of mobile CPUs is different than the architecture of laptop or desktop CPUs.</span></span>  <span data-ttu-id="dba41-120">疑わしい場合は、モバイル デバイスでページを実際に実行する方法が最善の策です。</span><span class="sxs-lookup"><span data-stu-id="dba41-120">When in doubt, your best bet is to actually run your page on a mobile device.</span></span>  <span data-ttu-id="dba41-121">[リモート デバッグ][DevToolsRemoteDebugging] を使用して、ページがモバイル デバイス上で実際に実行されている間にコンピューターからページのコードを操作します。</span><span class="sxs-lookup"><span data-stu-id="dba41-121">Use [Remote Debugging][DevToolsRemoteDebugging] to interact with the code of a page from your machine while your page actually runs on a mobile device.</span></span>  <span data-ttu-id="dba41-122">コードを操作している間は、表示、変更、デバッグ、プロファイル、または 4 つすべて表示できます。</span><span class="sxs-lookup"><span data-stu-id="dba41-122">You may view, change, debug, profile, or all four while you interact with the code.</span></span>  <span data-ttu-id="dba41-123">コンピューターはノートブックまたはデスクトップ コンピューターである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dba41-123">Your machine may be a notebook or desktop computer.</span></span>  

## <a name="simulate-a-mobile-viewport"></a><span data-ttu-id="dba41-124">モバイル ビューポートをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="dba41-124">Simulate a mobile viewport</span></span>  

<span data-ttu-id="dba41-125">[**デバイス エミュレーションの**切り替え\( Toggle Device Toolbar \) を選択するか ![ ][ImageDeviceToolbarIcon] **、[DevTools** `...` \( \*\*\*\* \) > デバイス エミュレーションのカスタマイズと制御] を選択して、モバイル ビューポートをシミュレートできる UI を開きます。</span><span class="sxs-lookup"><span data-stu-id="dba41-125">Choose **Toggle device emulation**  \(![Toggle Device Toolbar][ImageDeviceToolbarIcon]\) or choose **Customize and control DevTools** \(`...`\) > **Device emulation** to open the UI that enables you to simulate a mobile viewport.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="[デバイス] ツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    <span data-ttu-id="dba41-127">[デバイス] ツールバー</span><span class="sxs-lookup"><span data-stu-id="dba41-127">The Device Toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="dba41-128">既定では、デバイス ツールバーはレスポンシブ ビューポート モードで開きます。</span><span class="sxs-lookup"><span data-stu-id="dba41-128">By default the Device Toolbar opens in Responsive Viewport Mode.</span></span>  

### <a name="responsive-viewport-mode"></a><span data-ttu-id="dba41-129">レスポンシブ ビューポート モード</span><span class="sxs-lookup"><span data-stu-id="dba41-129">Responsive Viewport Mode</span></span>  

<span data-ttu-id="dba41-130">複数の画面サイズでページの外観をすばやくテストするには、ハンドルをドラッグして必要なサイズに合わせてビューポートのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="dba41-130">To quickly test the look and feel of your page across multiple screen sizes, drag the handles to resize the viewport to your required dimensions.</span></span>  <span data-ttu-id="dba41-131">幅と高さのボックスに特定の値を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="dba41-131">You may also enter specific values in the width and height boxes.</span></span>  <span data-ttu-id="dba41-132">次の図では、幅がに設定され `626` 、高さがに設定されています `516` 。</span><span class="sxs-lookup"><span data-stu-id="dba41-132">In the following figure, the width is set to `626` and the height is set to `516`.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="レスポンシブ ビューポート モードでビューポートの寸法を変更するハンドル" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    <span data-ttu-id="dba41-134">レスポンシブ ビューポート モードでビューポートの寸法を変更するハンドル</span><span class="sxs-lookup"><span data-stu-id="dba41-134">The handles for changing the dimensions of the viewport when in Responsive Viewport Mode</span></span>  
:::image-end:::  

#### <a name="show-media-queries"></a><span data-ttu-id="dba41-135">メディア クエリの表示</span><span class="sxs-lookup"><span data-stu-id="dba41-135">Show media queries</span></span>  

<span data-ttu-id="dba41-136">ページでメディア クエリを定義している場合は、ビューポートの上にメディア クエリブレークポイントを表示して、それらのメディア クエリが有効なビューポートディメンションにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="dba41-136">If you have defined media queries on your page, jump to the viewport dimensions where those media queries take effect by showing media query breakpoints above your viewport.</span></span>  <span data-ttu-id="dba41-137">[その**他のオプション**  >  **] [メディア クエリの表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-137">Choose **More options** > **Show media queries**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="メディア クエリの表示" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **<span data-ttu-id="dba41-139">メディア クエリの表示</span><span class="sxs-lookup"><span data-stu-id="dba41-139">Show media queries</span></span>**  
:::image-end:::  

<span data-ttu-id="dba41-140">ブレークポイントを選択して、メディア クエリがトリガーされるビューポートの幅を変更します。</span><span class="sxs-lookup"><span data-stu-id="dba41-140">Choose a breakpoint to change the width of the viewport so that the media query gets triggered.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="ブレークポイントを選択してビューポートの幅を変更する" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   <span data-ttu-id="dba41-142">ブレークポイントを選択してビューポートの幅を変更する</span><span class="sxs-lookup"><span data-stu-id="dba41-142">Choose a breakpoint to change the width of the viewport</span></span>  
:::image-end:::  

#### <a name="set-the-device-type"></a><span data-ttu-id="dba41-143">デバイスの種類を設定する</span><span class="sxs-lookup"><span data-stu-id="dba41-143">Set the device type</span></span>  

<span data-ttu-id="dba41-144">モバイル デバイスまたは **デスクトップ デバイスを** シミュレートするには、[デバイスの種類] リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="dba41-144">Use the **Device Type** list to simulate a mobile device or desktop device.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="[デバイスの種類] リスト" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   <span data-ttu-id="dba41-146">[**デバイスの種類] リスト**</span><span class="sxs-lookup"><span data-stu-id="dba41-146">The **Device Type** list</span></span>  
:::image-end:::  

<span data-ttu-id="dba41-147">次の表に、使用可能なデバイスの種類のオプションの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="dba41-147">The following table describes the differences between the available device type options.</span></span>  <span data-ttu-id="dba41-148">[レンダリング] メソッド列は、Microsoft Edge がページをモバイル ビューポートまたはデスクトップ ビューポートとしてレンダリングするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dba41-148">The Rendering method column refers to whether Microsoft Edge renders the page as a mobile or desktop viewport.</span></span>  <span data-ttu-id="dba41-149">[カーソル] アイコン列は、ページにマウス ポインターを置くと表示されるカーソルの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="dba41-149">The Cursor icon column refers to what type of cursor is displayed when you hover on the page.</span></span>  <span data-ttu-id="dba41-150">[イベントがトリガーされた] 列は、ページを操作するときに、ページがトリガーするか `touch` `click` 、イベントをトリガーするかを示します。</span><span class="sxs-lookup"><span data-stu-id="dba41-150">The Events triggered column refers to whether the page triggers `touch` or `click` events when you interact with the page.</span></span>  

| <span data-ttu-id="dba41-151">オプション</span><span class="sxs-lookup"><span data-stu-id="dba41-151">Option</span></span> | <span data-ttu-id="dba41-152">レンダリング メソッド</span><span class="sxs-lookup"><span data-stu-id="dba41-152">Rendering method</span></span> | <span data-ttu-id="dba41-153">カーソル アイコン</span><span class="sxs-lookup"><span data-stu-id="dba41-153">Cursor icon</span></span> | <span data-ttu-id="dba41-154">トリガーされるイベント</span><span class="sxs-lookup"><span data-stu-id="dba41-154">Events triggered</span></span> |  
|:--- |:--- |:--- |:--- |  
| <span data-ttu-id="dba41-155">モバイル</span><span class="sxs-lookup"><span data-stu-id="dba41-155">Mobile</span></span> | <span data-ttu-id="dba41-156">モバイル</span><span class="sxs-lookup"><span data-stu-id="dba41-156">Mobile</span></span> | <span data-ttu-id="dba41-157">円形</span><span class="sxs-lookup"><span data-stu-id="dba41-157">Circle</span></span> | <span data-ttu-id="dba41-158">タッチ</span><span class="sxs-lookup"><span data-stu-id="dba41-158">touch</span></span> |  
| <span data-ttu-id="dba41-159">Mobile \(no touch\)</span><span class="sxs-lookup"><span data-stu-id="dba41-159">Mobile \(no touch\)</span></span> | <span data-ttu-id="dba41-160">モバイル</span><span class="sxs-lookup"><span data-stu-id="dba41-160">Mobile</span></span> | <span data-ttu-id="dba41-161">通常</span><span class="sxs-lookup"><span data-stu-id="dba41-161">Normal</span></span> | <span data-ttu-id="dba41-162">て </span><span class="sxs-lookup"><span data-stu-id="dba41-162">choose</span></span> |  
| <span data-ttu-id="dba41-163">Desktop</span><span class="sxs-lookup"><span data-stu-id="dba41-163">Desktop</span></span> | <span data-ttu-id="dba41-164">Desktop</span><span class="sxs-lookup"><span data-stu-id="dba41-164">Desktop</span></span> | <span data-ttu-id="dba41-165">通常</span><span class="sxs-lookup"><span data-stu-id="dba41-165">Normal</span></span> | <span data-ttu-id="dba41-166">て </span><span class="sxs-lookup"><span data-stu-id="dba41-166">choose</span></span> |  
| <span data-ttu-id="dba41-167">デスクトップ \(touch\)</span><span class="sxs-lookup"><span data-stu-id="dba41-167">Desktop \(touch\)</span></span> | <span data-ttu-id="dba41-168">Desktop</span><span class="sxs-lookup"><span data-stu-id="dba41-168">Desktop</span></span> | <span data-ttu-id="dba41-169">円形</span><span class="sxs-lookup"><span data-stu-id="dba41-169">Circle</span></span> | <span data-ttu-id="dba41-170">タッチ</span><span class="sxs-lookup"><span data-stu-id="dba41-170">touch</span></span> |  

> [!NOTE]
> <span data-ttu-id="dba41-171">[デバイスの**種類] リストが**表示されない場合は、[その他の**オプション] [デバイスの**  >  **種類の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-171">If the **Device Type** list is not displayed, choose **More options** > **Add device type**.</span></span>  

### <a name="mobile-device-viewport-mode"></a><span data-ttu-id="dba41-172">モバイル デバイス ビューポート モード</span><span class="sxs-lookup"><span data-stu-id="dba41-172">Mobile Device Viewport Mode</span></span>  

<span data-ttu-id="dba41-173">特定のモバイル デバイスの寸法をシミュレートするには、[デバイス] リストからデバイス **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="dba41-173">To simulate the dimensions of a specific mobile device, select the device from the **Device** list.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="[デバイス] リスト" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   <span data-ttu-id="dba41-175">[**デバイス] リスト**</span><span class="sxs-lookup"><span data-stu-id="dba41-175">The **Device** list</span></span>  
:::image-end:::  

#### <a name="rotate-the-viewport-to-landscape-orientation"></a><span data-ttu-id="dba41-176">ビューポートを横向きに回転する</span><span class="sxs-lookup"><span data-stu-id="dba41-176">Rotate the viewport to landscape orientation</span></span>  

<span data-ttu-id="dba41-177">横向きに Web ページをテストします。</span><span class="sxs-lookup"><span data-stu-id="dba41-177">Test your webpage in landscape orientation.</span></span>  

*   <span data-ttu-id="dba41-178">ビューポートを横向きに回転するには、[ **回転]\(** 回転 ![ ][ImageRotateIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="dba41-178">To rotate the viewport to landscape orientation, choose **Rotate** \(![Rotate][ImageRotateIcon]\).</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横向きに表示されるページ" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       <span data-ttu-id="dba41-180">横向きに表示されるページ</span><span class="sxs-lookup"><span data-stu-id="dba41-180">Page displayed in landscape orientation</span></span>  
    :::image-end:::  
    
> [!NOTE]
> <span data-ttu-id="dba41-181">デバイス **ツールバーが** 狭い場合は、[回転] **ボタンが** 表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="dba41-181">The **Rotate** button disappears if your **Device Toolbar** is narrow.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="[デバイス] ツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="dba41-183">[ **デバイス] ツールバー**</span><span class="sxs-lookup"><span data-stu-id="dba41-183">The **Device Toolbar**</span></span>  
:::image-end:::  

<span data-ttu-id="dba41-184">詳細については、[方向の設定] [に移動します](#set-orientation)。</span><span class="sxs-lookup"><span data-stu-id="dba41-184">For more information, navigate to [Set orientation](#set-orientation).</span></span>  

#### <a name="show-device-frame"></a><span data-ttu-id="dba41-185">デバイス フレームの表示</span><span class="sxs-lookup"><span data-stu-id="dba41-185">Show device frame</span></span>  

<span data-ttu-id="dba41-186">iPhone 6 などの特定のモバイル デバイスの寸法をシミュレートするときに、ビューポートの周囲に物理デバイス フレームを表示します。</span><span class="sxs-lookup"><span data-stu-id="dba41-186">Display the physical device frame around the viewport when you simulate the dimensions of a specific mobile device such as an iPhone 6.</span></span>  

1.  <span data-ttu-id="dba41-187">[その **他のオプション] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="dba41-187">Open **More options**.</span></span>  
1.  <span data-ttu-id="dba41-188">[デバイス **フレームの表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-188">Choose **Show device frame**.</span></span>  

> [!NOTE]
> <span data-ttu-id="dba41-189">特定のデバイスのデバイス フレームが表示されない場合は、DevTools にオプションのアートが含められているという意味です。</span><span class="sxs-lookup"><span data-stu-id="dba41-189">If a device frame for a particular device is not displayed, it means that DevTools does not have art for the option.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="デバイス フレームの表示" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         <span data-ttu-id="dba41-191">デバイス フレームの表示</span><span class="sxs-lookup"><span data-stu-id="dba41-191">Show device frame</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="iPhone 6 のデバイス フレーム" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         <span data-ttu-id="dba41-193">iPhone 6 のデバイス フレーム</span><span class="sxs-lookup"><span data-stu-id="dba41-193">The device frame for the iPhone 6</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="add-a-custom-mobile-device"></a><span data-ttu-id="dba41-194">カスタム モバイル デバイスの追加</span><span class="sxs-lookup"><span data-stu-id="dba41-194">Add a custom mobile device</span></span>  

<span data-ttu-id="dba41-195">必要なモバイル デバイス オプションが既定のリストに含まれていない場合は、カスタム デバイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dba41-195">If the mobile device option that you need is not included on the default list, you may add a custom device.</span></span>  <span data-ttu-id="dba41-196">カスタム デバイスを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dba41-196">To add a custom device, complete the following steps.</span></span>  

1.  <span data-ttu-id="dba41-197">[編集] **で [デバイス** ] > **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-197">Choose the **Device** list > **Edit**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="[編集] を選択します。" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       <span data-ttu-id="dba41-199">[編集 **] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="dba41-199">Choose **Edit**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="dba41-200">[カスタム **デバイスの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-200">Choose **Add custom device**.</span></span>  
1.  <span data-ttu-id="dba41-201">[ **エミュレートされたデバイス] で**、カスタム デバイスのデバイス名、画面幅、画面の高さを入力します。</span><span class="sxs-lookup"><span data-stu-id="dba41-201">On **Emulated Devices**, enter a device name, screen width, and screen height for the custom device.</span></span>  <span data-ttu-id="dba41-202">デバイス[のピクセル比、][MDNWindowDevicePixelRatio][ユーザー エージェント文字列、][MDNUserAgent][およびデバイスの種類](#set-the-device-type)フィールドはオプションです。</span><span class="sxs-lookup"><span data-stu-id="dba41-202">The [device pixel ratio][MDNWindowDevicePixelRatio], [user agent string][MDNUserAgent], and [device type](#set-the-device-type) fields are optional.</span></span>  <span data-ttu-id="dba41-203">デバイスの種類フィールドの既定値は Mobile **です**。</span><span class="sxs-lookup"><span data-stu-id="dba41-203">The device type field defaults to **Mobile**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="カスタム デバイスの作成" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       <span data-ttu-id="dba41-205">カスタム デバイスの作成</span><span class="sxs-lookup"><span data-stu-id="dba41-205">Create a custom device</span></span>  
    :::image-end:::  
    
### <a name="show-rulers"></a><span data-ttu-id="dba41-206">ルーラーを表示する</span><span class="sxs-lookup"><span data-stu-id="dba41-206">Show rulers</span></span>  

<span data-ttu-id="dba41-207">画面のサイズを測定する必要がある場合は、ルーラーを使用して画面サイズをピクセル単位で測定できます。</span><span class="sxs-lookup"><span data-stu-id="dba41-207">If you need to measure screen dimensions, you may use rulers to measure the screen size in pixels.</span></span>  <span data-ttu-id="dba41-208">[**その他のオプション**  >  **] ルーラーを表示**して、ビューポートの上と左にルーラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="dba41-208">Choose **More options** > **Show rulers** to display rulers above and to the left of your viewport.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="ルーラーを表示するメニュー項目" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         <span data-ttu-id="dba41-210">ルーラーを表示するメニュー項目</span><span class="sxs-lookup"><span data-stu-id="dba41-210">Menu item to display rulers</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="ビューポートの上と左のルーラー" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         <span data-ttu-id="dba41-212">ビューポートの上と左のルーラー</span><span class="sxs-lookup"><span data-stu-id="dba41-212">Rulers above and to the left of the viewport</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="zoom-the-viewport"></a><span data-ttu-id="dba41-213">ビューポートをズームする</span><span class="sxs-lookup"><span data-stu-id="dba41-213">Zoom the viewport</span></span>  

<span data-ttu-id="dba41-214">複数のズーム レベルでページの外観をテストするには、ズーム リスト\*\*\*\* を使用して拡大または縮小します。</span><span class="sxs-lookup"><span data-stu-id="dba41-214">To test the look and feel of your page at multiple zoom levels, use the **Zoom** list to zoom in or out.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="Zoom" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **<span data-ttu-id="dba41-216">Zoom</span><span class="sxs-lookup"><span data-stu-id="dba41-216">Zoom</span></span>**  
:::image-end:::  

## <a name="throttle-the-network-and-cpu"></a><span data-ttu-id="dba41-217">ネットワークと CPU の調整</span><span class="sxs-lookup"><span data-stu-id="dba41-217">Throttle the network and CPU</span></span>  

<span data-ttu-id="dba41-218">多くの場合、モバイル デバイスにはネットワークと CPU の制約があります。</span><span class="sxs-lookup"><span data-stu-id="dba41-218">Mobile devices often have network and CPU constraints.</span></span>  <span data-ttu-id="dba41-219">ページの読み込み速度と、さまざまなインターネット速度と CPU 速度での応答方法をテストしてください。</span><span class="sxs-lookup"><span data-stu-id="dba41-219">Ensure you test how quickly your page loads and how it responds at different internet and CPU speeds.</span></span>  

<span data-ttu-id="dba41-220">ネットワークと CPU を調整します。</span><span class="sxs-lookup"><span data-stu-id="dba41-220">Throttle the network and CPU.</span></span>  

1.  <span data-ttu-id="dba41-221">[ **スロットル リスト]** を選択し、プリセットを **[中** 層モバイル] または [ローエンド モバイル] **に変更します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-221">Choose **Throttle** list and change the preset to **Mid-tier mobile** or **Low-end mobile**.</span></span>  
    *   <span data-ttu-id="dba41-222">**中層モバイルは、CPU** `fast 3G` をシミュレートして調整します。</span><span class="sxs-lookup"><span data-stu-id="dba41-222">**Mid-tier mobile** simulates `fast 3G` and throttles your CPU.</span></span>  <span data-ttu-id="dba41-223">通常の 4 倍遅くなります。</span><span class="sxs-lookup"><span data-stu-id="dba41-223">It is four times slower than normal.</span></span>  
    *   <span data-ttu-id="dba41-224">**ローエンド モバイルは、CPU** `slow 3G` をシミュレートして調整します。</span><span class="sxs-lookup"><span data-stu-id="dba41-224">**Low-end mobile** simulates `slow 3G` and throttles your CPU.</span></span>  <span data-ttu-id="dba41-225">通常の 6 倍遅くなります。</span><span class="sxs-lookup"><span data-stu-id="dba41-225">It is six times slower than normal.</span></span>  
    
<span data-ttu-id="dba41-226">すべての調整は、ラップトップまたはデスクトップの通常の機能に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="dba41-226">All of the throttling is based upon the normal capability of your laptop or desktop.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="デバイス ツールバーのスロットル リスト" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   <span data-ttu-id="dba41-228">デバイス **ツールバー** のスロットル リスト</span><span class="sxs-lookup"><span data-stu-id="dba41-228">The **Throttle** list in the Device Toolbar</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="dba41-229">スロットル リスト **が非表示の** 場合、デバイス **ツールバーが** 狭すぎます。</span><span class="sxs-lookup"><span data-stu-id="dba41-229">If the **Throttle list** is hidden, your **Device Toolbar** is too narrow.</span></span>  <span data-ttu-id="dba41-230">スロットル リストに **アクセスするには、** デバイス ツールバーの幅を **大きくします**。</span><span class="sxs-lookup"><span data-stu-id="dba41-230">To access the **Throttle list**, increase the width of the **Device Toolbar**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="[デバイス] ツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="dba41-232">[ **デバイス] ツールバー**</span><span class="sxs-lookup"><span data-stu-id="dba41-232">The **Device Toolbar**</span></span>  
:::image-end:::  

### <a name="throttle-the-cpu-only"></a><span data-ttu-id="dba41-233">CPU のみを調整する</span><span class="sxs-lookup"><span data-stu-id="dba41-233">Throttle the CPU only</span></span>  

<span data-ttu-id="dba41-234">ネットワークではなく CPU のみを調整するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dba41-234">To throttle the CPU only and not the network, complete the following steps.</span></span>

1.  <span data-ttu-id="dba41-235">[パフォーマンス] **パネルを選択** し、[キャプチャ設定\( Capture **Settings** ![ ][ImageCaptureIcon] \] ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="dba41-235">Choose the **Performance** panel, and choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span></span>
1.  <span data-ttu-id="dba41-236">**[CPU**  >  **4x スローダウン] または** **[6 倍のスローダウン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-236">Choose **CPU** > **4x slowdown** or **6x slowdown**.</span></span>
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="[パフォーマンス] パネルの CPU リスト" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       <span data-ttu-id="dba41-238">[**パフォーマンス]** パネルの**CPU リスト**</span><span class="sxs-lookup"><span data-stu-id="dba41-238">The **CPU** list in the **Performance** panel</span></span>  
    :::image-end:::  
    
### <a name="throttle-the-network-only"></a><span data-ttu-id="dba41-239">ネットワークの調整のみ</span><span class="sxs-lookup"><span data-stu-id="dba41-239">Throttle the network only</span></span>  

<span data-ttu-id="dba41-240">ネットワークのみを調整するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dba41-240">To throttle the network only, complete the following steps.</span></span>

1.  <span data-ttu-id="dba41-241">[ネットワーク] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="dba41-241">Choose the **Network** tool.</span></span>
1.  <span data-ttu-id="dba41-242">[**オンライン**  >  **高速 3G] または [** 低速**3G] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-242">Choose **Online** > **Fast 3G** or **Slow 3G**.</span></span>
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="[ネットワーク] パネルの [スロットル] リスト" lightbox="../media/device-mode-network-throttle.msft.png":::
       <span data-ttu-id="dba41-244">[ **ネットワーク]** パネルの [スロットル] リスト</span><span class="sxs-lookup"><span data-stu-id="dba41-244">The **Throttle** list in the Network panel</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="dba41-245">または `Control` + `Shift` + `P` 、[\(Windows, `Command` + `Shift` + `P` Linux\) または \(macOS\)\*\*\*\* `3G` \*\*\*\*\*\*\*\* を選択してコマンド メニューを開き、入力し、[高速 3G 調整を有効にする] または [低速 3G 調整を有効にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dba41-245">Or select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**, type `3G`, and choose **Enable fast 3G throttling** or **Enable slow 3G throttling**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="コマンド メニュー" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       <span data-ttu-id="dba41-247">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="dba41-247">The **Command Menu**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="dba41-248">[パフォーマンス] パネルからネットワーク調整を **設定** することもできます。</span><span class="sxs-lookup"><span data-stu-id="dba41-248">You may also set network throttling from the **Performance** panel.</span></span>  

1.  <span data-ttu-id="dba41-249">[**キャプチャ設定**\( Capture Settings \) を選択し、[ネットワーク] リストを選択し、プリセットを ![ ][ImageCaptureIcon] **[Fast 3G]** または **[低速 3G] に変更します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dba41-249">Choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\) and choose the **Network** list and change the preset to **Fast 3G** or **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="[パフォーマンス] パネルからネットワーク調整を設定する" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       <span data-ttu-id="dba41-251">[パフォーマンス] パネルからネットワーク調整 **を設定** する</span><span class="sxs-lookup"><span data-stu-id="dba41-251">Set network throttling from the **Performance** panel</span></span>  
    :::image-end:::  
    
## <a name="override-geolocation"></a><span data-ttu-id="dba41-252">位置情報を上書きする</span><span class="sxs-lookup"><span data-stu-id="dba41-252">Override geolocation</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="dba41-253">ページがモバイル デバイスからの位置情報に依存して適切にレンダリングされる場合は、地理位置情報オーバーライド UI を使用してさまざまな位置情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dba41-253">If your page depends on geolocation information from a mobile device to render properly, provide different geolocations using the geolocation overriding UI.</span></span>  

      1.  <span data-ttu-id="dba41-254">**[DevTools \(** \) のカスタマイズと制御 `...` ] を選択>**その他のツール**  >  **センサー を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-254">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="地理位置情報用センサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         <span data-ttu-id="dba41-256">**地理位置情報** 用センサー</span><span class="sxs-lookup"><span data-stu-id="dba41-256">**Sensors** for geolocation</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="dba41-257">コマンド メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="dba41-257">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="dba41-258">`Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="dba41-258">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="dba41-259">を `Sensors` 入力し、[センサー **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-259">Type `Sensors`, and choose **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="地理位置情報のセンサーを表示する" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         <span data-ttu-id="dba41-261">**地理位置情報のセンサー** を表示する</span><span class="sxs-lookup"><span data-stu-id="dba41-261">**Show Sensors** for geolocation</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="dba41-262">[ **センサー] パネル** で、[場所] ドロップダウン メニューを使用して、DevTools に含まれるプリセットの **場所のいずれかを** 選択できます。</span><span class="sxs-lookup"><span data-stu-id="dba41-262">On the **Sensors** panel, you may select one of the preset locations included in DevTools using the **Location** drop-down menu.</span></span>  <span data-ttu-id="dba41-263">カスタムの場所を入力するには、[その他] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="dba41-263">To enter a custom location, choose **Other…**</span></span> <span data-ttu-id="dba41-264">をクリックし、カスタムの場所の座標を入力します。</span><span class="sxs-lookup"><span data-stu-id="dba41-264">and enter the coordinates of your custom location.</span></span>  <span data-ttu-id="dba41-265">位置情報が使用できない場合にエラー状態でページをテストするには、[場所を **使用できません] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-265">To test your page in an error state when location information is unavailable, choose **Location unavailable**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="事前に設定された場所が選択されたセンサー パネル" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    <span data-ttu-id="dba41-267">**事前に設定** された場所が選択されたセンサー パネル。</span><span class="sxs-lookup"><span data-stu-id="dba41-267">**Sensors** panel with a preset location selected.</span></span>  
:::image-end:::

## <a name="set-orientation"></a><span data-ttu-id="dba41-268">方向を設定する</span><span class="sxs-lookup"><span data-stu-id="dba41-268">Set orientation</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="dba41-269">ページがモバイル デバイスからのオリエンテーション情報に依存して適切にレンダリングされる場合は、向き UI を開きます。</span><span class="sxs-lookup"><span data-stu-id="dba41-269">If your page depends on orientation information from a mobile device to render properly, open the orientation UI.</span></span>  

      1.  <span data-ttu-id="dba41-270">**[DevTools \(** \) のカスタマイズと制御 `...` ] を選択>**その他のツール**  >  **センサー を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-270">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="方向のセンサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         <span data-ttu-id="dba41-272">**方向の** センサー</span><span class="sxs-lookup"><span data-stu-id="dba41-272">**Sensors** for orientation</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="dba41-273">コマンド メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="dba41-273">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="dba41-274">`Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="dba41-274">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="dba41-275">を `Sensors` 入力し、[センサー **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-275">Type `Sensors`, and choose **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="方向のセンサーを表示する" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         <span data-ttu-id="dba41-277">**方向のセンサーを** 表示する</span><span class="sxs-lookup"><span data-stu-id="dba41-277">**Show Sensors** for orientation</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="dba41-278">[センサー **] パネル** で、[方向] ドロップダウン メニューから事前設定 **の向** きを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dba41-278">On the **Sensors** panel, you may select a preset orientation from the **Orientation** drop-down menu.</span></span>  <span data-ttu-id="dba41-279">独自の向きを入力するには **、[カスタム**の向き] を選択し、独自のアルファ値、[ベータ][MDNDeviceOrientaitonAlpha]値、ガンマ値[を入力][MDNDeviceOrientaitonGamma]します。 [][MDNDeviceOrientaitonBeta]</span><span class="sxs-lookup"><span data-stu-id="dba41-279">To enter your own orientation, choose **Custom orientation**, and enter your own [alpha][MDNDeviceOrientaitonAlpha], [beta][MDNDeviceOrientaitonBeta], and [gamma][MDNDeviceOrientaitonGamma] values.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="センサー パネルの方向オプション" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    <span data-ttu-id="dba41-281">**センサー**パネルの**方向オプション**</span><span class="sxs-lookup"><span data-stu-id="dba41-281">**Orientation** options on the **Sensors** panel</span></span>  
:::image-end:::  

## <a name="set-user-agent-string"></a><span data-ttu-id="dba41-282">ユーザー エージェント文字列の設定</span><span class="sxs-lookup"><span data-stu-id="dba41-282">Set user agent string</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="dba41-283">ページがモバイル デバイスのユーザー エージェント文字列に依存して適切にレンダリングされる場合は\*\*\*\*、[ネットワーク条件] パネルを使用して、異なるユーザー エージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="dba41-283">If your page depends on the user agent string from a mobile device to render properly, use the **Network conditions** panel to provide different user agent strings.</span></span>  
      
      1.  <span data-ttu-id="dba41-284">**[DevTools \(** \) をカスタマイズして制御 `...` する] を選択>**その他のツール**  >  **ネットワーク条件を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-284">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Network conditions**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text="[その他のツール] メニューのネットワーク条件エントリ" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         <span data-ttu-id="dba41-286">**[その他のツール**] メニュー**のネットワーク条件エントリ**</span><span class="sxs-lookup"><span data-stu-id="dba41-286">**Network conditions** entry in the **More tools** menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="dba41-287">コマンド メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="dba41-287">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="dba41-288">`Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="dba41-288">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="dba41-289">を `Network conditions` 入力し、[ネットワーク条件 **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-289">Type `Network conditions`, and choose **Show Network conditions**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="ネットワーク条件の表示" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **<span data-ttu-id="dba41-291">ネットワーク条件の表示</span><span class="sxs-lookup"><span data-stu-id="dba41-291">Show Network conditions</span></span>**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="dba41-292">[ユーザー エージェント **] の横にある**[自動的に選択 **する] チェック ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="dba41-292">Next to **User agent**, clear the **Select automatically** checkbox.</span></span>  <span data-ttu-id="dba41-293">次に **、[Custom...] を選択** して、定義済みのユーザー エージェント文字列の一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="dba41-293">Then, choose **Custom...** to select from a list of predefined user agent strings.</span></span>  <span data-ttu-id="dba41-294">独自のユーザー エージェント文字列を入力するには、[カスタム ユーザー エージェントの入力 **] に文字列を入力します**。</span><span class="sxs-lookup"><span data-stu-id="dba41-294">To enter your own user agent string, enter the string in **Enter a custom user agent**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="macOS でユーザー エージェント文字列を Microsoft Edge に設定する" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    <span data-ttu-id="dba41-296">macOS でユーザー エージェント文字列を Microsoft Edge に設定する</span><span class="sxs-lookup"><span data-stu-id="dba41-296">Set the user agent string to Microsoft Edge on macOS</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="dba41-297">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="dba41-297">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureIcon]: ../media/capture-settings-icon.msft.png  
[ImageDeviceToolbarIcon]: ../media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[DevToolsRemoteDebugging]: ../remote-debugging/index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window.devicePixelRatio |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "User Agent |MDN"  
[MDNDeviceOrientaitonAlpha]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/alpha "DeviceOrientationEvent.alpha |MDN"  
[MDNDeviceOrientaitonBeta]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/beta "DeviceOrientationEvent.beta |MDN"  
[MDNDeviceOrientaitonGamma]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/gamma "DeviceOrientationEvent.gamma |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "近似の順序 - 1 次 - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="dba41-305">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="dba41-305">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="dba41-306">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="dba41-306">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="dba41-308">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="dba41-308">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
