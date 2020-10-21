---
description: Microsoft Edge で仮想デバイスを使用して、モバイルの最初の web サイトを構築します。
title: Microsoft Edge DevTools でモバイルデバイスをエミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、エミュレーション、デバイス、シミュレーション、モバイル
ms.openlocfilehash: 8b636a20fcb1c55630009031ec8bf300624d03d7
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125105"
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

# <span data-ttu-id="207c6-104">Microsoft Edge DevTools でモバイルデバイスをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="207c6-104">Emulate mobile devices in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="207c6-105">モバイルデバイスでページがどのように表示され、どのように応答するかについては、 **デバイスエミュレーション** を使用します。</span><span class="sxs-lookup"><span data-stu-id="207c6-105">Use **Device emulation** to approximate how your page looks and responds on a mobile device.</span></span>  <span data-ttu-id="207c6-106">Microsoft Edge の DevTools には、モバイルデバイスをエミュレートするための機能のコレクションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="207c6-106">The Microsoft Edge DevTools provide a collection of features to help you emulate mobile devices.</span></span>  <span data-ttu-id="207c6-107">このコレクションには、次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="207c6-107">The collection includes the following features.</span></span>  

*   [<span data-ttu-id="207c6-108">モバイルビューポートのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="207c6-108">Simulate a mobile viewport</span></span>](#simulate-a-mobile-viewport)  
*   [<span data-ttu-id="207c6-109">ネットワークを調整する</span><span class="sxs-lookup"><span data-stu-id="207c6-109">Throttle the network</span></span>](#throttle-the-network-only)  
*   [<span data-ttu-id="207c6-110">CPU を調整する</span><span class="sxs-lookup"><span data-stu-id="207c6-110">Throttle the CPU</span></span>](#throttle-the-cpu-only)  
*   [<span data-ttu-id="207c6-111">位置情報のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="207c6-111">Simulate geolocation</span></span>](#override-geolocation)  
*   [<span data-ttu-id="207c6-112">向きを設定する</span><span class="sxs-lookup"><span data-stu-id="207c6-112">Set orientation</span></span>](#set-orientation)  
*   [<span data-ttu-id="207c6-113">ユーザーエージェントの文字列を設定する</span><span class="sxs-lookup"><span data-stu-id="207c6-113">Set the user agent string</span></span>](#set-user-agent-string)  

## <span data-ttu-id="207c6-114">制限事項</span><span class="sxs-lookup"><span data-stu-id="207c6-114">Limitations</span></span>  

<span data-ttu-id="207c6-115">**デバイスエミュレーション** は、モバイルデバイスでのページのルックアンドフィールの最初の部分に [近い][WikiApproximation] ものです。</span><span class="sxs-lookup"><span data-stu-id="207c6-115">**Device emulation** is a [first-order approximation][WikiApproximation] of the look and feel of your page on a mobile device.</span></span>  <span data-ttu-id="207c6-116">**デバイスエミュレーション** では、モバイルデバイスで実際にコードが実行されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="207c6-116">**Device emulation** does not actually run your code on a mobile device.</span></span>  <span data-ttu-id="207c6-117">代わりに、モバイルユーザーエクスペリエンスをノート pc またはデスクトップからシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="207c6-117">Instead you simulate the mobile user experience from your laptop or desktop.</span></span>  

<span data-ttu-id="207c6-118">モバイルデバイスのいくつかの側面は、DevTools ではエミュレートされません。</span><span class="sxs-lookup"><span data-stu-id="207c6-118">Some aspects of mobile devices are never emulated in DevTools.</span></span>  <span data-ttu-id="207c6-119">たとえば、モバイル Cpu のアーキテクチャは、ノート pc またはデスクトップ Cpu のアーキテクチャとは異なります。</span><span class="sxs-lookup"><span data-stu-id="207c6-119">For example, the architecture of mobile CPUs is different than the architecture of laptop or desktop CPUs.</span></span>  <span data-ttu-id="207c6-120">疑わしい場合は、実際にモバイルデバイスでページを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="207c6-120">When in doubt, your best bet is to actually run your page on a mobile device.</span></span>  <span data-ttu-id="207c6-121">[リモートデバッグ] を使って、ページがモバイルデバイスで実際に実行されているときに、コンピューターからページのコードを操作します。</span><span class="sxs-lookup"><span data-stu-id="207c6-121">Use [Remote Debugging][DevToolsRemoteDebugging] to interact with the code of a page from your machine while your page actually runs on a mobile device.</span></span>  <span data-ttu-id="207c6-122">コードを操作しているときに、表示、変更、デバッグ、プロファイル、またはすべて4つの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="207c6-122">You may view, change, debug, profile, or all four while you interact with the code.</span></span>  <span data-ttu-id="207c6-123">使用しているコンピューターがノートブックまたはデスクトップコンピューターである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="207c6-123">Your machine may be a notebook or desktop computer.</span></span>  

## <span data-ttu-id="207c6-124">モバイルビューポートのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="207c6-124">Simulate a mobile viewport</span></span>  

<span data-ttu-id="207c6-125">[ **デバイスエミュレーションの切り替え**  \] ( ![ デバイスツールバー \ の切り替え) を選ぶ ][ImageDeviceToolbarIcon] か、[ **カスタマイズと > 制御** ] を選び `...` ます。 **デバイスエミュレーション** は、モバイルビューポートをシミュレートするための UI を開くために使用します。</span><span class="sxs-lookup"><span data-stu-id="207c6-125">Choose **Toggle device emulation**  \(![Toggle Device Toolbar][ImageDeviceToolbarIcon]\) or choose **Customize and control DevTools** \(`...`\) > **Device emulation** to open the UI that enables you to simulate a mobile viewport.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    <span data-ttu-id="207c6-127">デバイスのツールバー</span><span class="sxs-lookup"><span data-stu-id="207c6-127">The Device Toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="207c6-128">既定では、デバイスのツールバーは、応答性のあるビューポートモードで開きます。</span><span class="sxs-lookup"><span data-stu-id="207c6-128">By default the Device Toolbar opens in Responsive Viewport Mode.</span></span>  

### <span data-ttu-id="207c6-129">応答性ビューポートモード</span><span class="sxs-lookup"><span data-stu-id="207c6-129">Responsive Viewport Mode</span></span>  

<span data-ttu-id="207c6-130">ページの外観を複数の画面サイズにわたってすばやくテストするには、ハンドルをドラッグしてビューポートのサイズを必要なサイズに変更します。</span><span class="sxs-lookup"><span data-stu-id="207c6-130">To quickly test the look and feel of your page across multiple screen sizes, drag the handles to resize the viewport to your required dimensions.</span></span>  <span data-ttu-id="207c6-131">[幅] ボックスと [高さ] ボックスに特定の値を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="207c6-131">You may also enter specific values in the width and height boxes.</span></span>  <span data-ttu-id="207c6-132">次の図では、幅がに設定され、 `626` 高さがに設定されて `516` います。</span><span class="sxs-lookup"><span data-stu-id="207c6-132">In the following figure, the width is set to `626` and the height is set to `516`.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    <span data-ttu-id="207c6-134">応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル</span><span class="sxs-lookup"><span data-stu-id="207c6-134">The handles for changing the dimensions of the viewport when in Responsive Viewport Mode</span></span>  
:::image-end:::  

#### <span data-ttu-id="207c6-135">メディアクエリを表示する</span><span class="sxs-lookup"><span data-stu-id="207c6-135">Show media queries</span></span>  

<span data-ttu-id="207c6-136">ページでメディアクエリを定義している場合は、ビューポートの上にメディアクエリのブレークポイントを表示して、メディアクエリが有効になるビューポートのサイズにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="207c6-136">If you have defined media queries on your page, jump to the viewport dimensions where those media queries take effect by showing media query breakpoints above your viewport.</span></span>  <span data-ttu-id="207c6-137">[**その他のオプション**] で [  >  **メディアクエリ] を**選びます。</span><span class="sxs-lookup"><span data-stu-id="207c6-137">Choose **More options** > **Show media queries**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **<span data-ttu-id="207c6-139">メディアクエリを表示する</span><span class="sxs-lookup"><span data-stu-id="207c6-139">Show media queries</span></span>**  
:::image-end:::  

<span data-ttu-id="207c6-140">メディアクエリがトリガーされるようにビューポートの幅を変更するには、ブレークポイントを選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-140">Choose a breakpoint to change the width of the viewport so that the media query gets triggered.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   <span data-ttu-id="207c6-142">ブレークポイントを選択してビューポートの幅を変更する</span><span class="sxs-lookup"><span data-stu-id="207c6-142">Choose a breakpoint to change the width of the viewport</span></span>  
:::image-end:::  

#### <span data-ttu-id="207c6-143">デバイスの種類を設定する</span><span class="sxs-lookup"><span data-stu-id="207c6-143">Set the device type</span></span>  

<span data-ttu-id="207c6-144">[ **デバイスの種類** ] の一覧を使用して、モバイルデバイスやデスクトップデバイスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="207c6-144">Use the **Device Type** list to simulate a mobile device or desktop device.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   <span data-ttu-id="207c6-146">[ **デバイスの種類** ] の一覧</span><span class="sxs-lookup"><span data-stu-id="207c6-146">The **Device Type** list</span></span>  
:::image-end:::  

<span data-ttu-id="207c6-147">次の表では、使用可能なデバイスの種類のオプションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="207c6-147">The following table describes the differences between the available device type options.</span></span>  <span data-ttu-id="207c6-148">[レンダリング方法] 列は、Microsoft Edge が、モバイルまたはデスクトップのビューポートとしてページをレンダリングするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="207c6-148">The Rendering method column refers to whether Microsoft Edge renders the page as a mobile or desktop viewport.</span></span>  <span data-ttu-id="207c6-149">カーソルのアイコン列は、ページ上にカーソルを置いたときに表示されるカーソルの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="207c6-149">The Cursor icon column refers to what type of cursor you see when you hover on the page.</span></span>  <span data-ttu-id="207c6-150">[トリガーされたイベント] 列は、 `touch` `click` ページを操作するときにページがトリガーまたはイベントを発生させるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="207c6-150">The Events triggered column refers to whether the page triggers `touch` or `click` events when you interact with the page.</span></span>  

| <span data-ttu-id="207c6-151">オプション</span><span class="sxs-lookup"><span data-stu-id="207c6-151">Option</span></span> | <span data-ttu-id="207c6-152">レンダリング方法</span><span class="sxs-lookup"><span data-stu-id="207c6-152">Rendering method</span></span> | <span data-ttu-id="207c6-153">カーソルアイコン</span><span class="sxs-lookup"><span data-stu-id="207c6-153">Cursor icon</span></span> | <span data-ttu-id="207c6-154">トリガーされたイベント</span><span class="sxs-lookup"><span data-stu-id="207c6-154">Events triggered</span></span> |  
|:--- |:--- |:--- |:--- |  
| <span data-ttu-id="207c6-155">モバイル</span><span class="sxs-lookup"><span data-stu-id="207c6-155">Mobile</span></span> | <span data-ttu-id="207c6-156">モバイル</span><span class="sxs-lookup"><span data-stu-id="207c6-156">Mobile</span></span> | <span data-ttu-id="207c6-157">円形</span><span class="sxs-lookup"><span data-stu-id="207c6-157">Circle</span></span> | <span data-ttu-id="207c6-158">タッチ</span><span class="sxs-lookup"><span data-stu-id="207c6-158">touch</span></span> |  
| <span data-ttu-id="207c6-159">モバイル \ (タッチなし)</span><span class="sxs-lookup"><span data-stu-id="207c6-159">Mobile \(no touch\)</span></span> | <span data-ttu-id="207c6-160">モバイル</span><span class="sxs-lookup"><span data-stu-id="207c6-160">Mobile</span></span> | <span data-ttu-id="207c6-161">通常</span><span class="sxs-lookup"><span data-stu-id="207c6-161">Normal</span></span> | <span data-ttu-id="207c6-162"> で、</span><span class="sxs-lookup"><span data-stu-id="207c6-162">click</span></span> |  
| <span data-ttu-id="207c6-163">Desktop</span><span class="sxs-lookup"><span data-stu-id="207c6-163">Desktop</span></span> | <span data-ttu-id="207c6-164">Desktop</span><span class="sxs-lookup"><span data-stu-id="207c6-164">Desktop</span></span> | <span data-ttu-id="207c6-165">通常</span><span class="sxs-lookup"><span data-stu-id="207c6-165">Normal</span></span> | <span data-ttu-id="207c6-166"> で、</span><span class="sxs-lookup"><span data-stu-id="207c6-166">click</span></span> |  
| <span data-ttu-id="207c6-167">デスクトップ \ (タッチ \)</span><span class="sxs-lookup"><span data-stu-id="207c6-167">Desktop \(touch\)</span></span> | <span data-ttu-id="207c6-168">Desktop</span><span class="sxs-lookup"><span data-stu-id="207c6-168">Desktop</span></span> | <span data-ttu-id="207c6-169">円形</span><span class="sxs-lookup"><span data-stu-id="207c6-169">Circle</span></span> | <span data-ttu-id="207c6-170">タッチ</span><span class="sxs-lookup"><span data-stu-id="207c6-170">touch</span></span> |  

> [!NOTE]
> <span data-ttu-id="207c6-171">[**デバイスの種類**] の一覧が表示されない場合は、[**その他**のデバイスの種類の追加] を選択し  >  **Add device type**ます。</span><span class="sxs-lookup"><span data-stu-id="207c6-171">If the **Device Type** list is not displayed, choose **More options** > **Add device type**.</span></span>  

### <span data-ttu-id="207c6-172">モバイルデバイスのビューポートモード</span><span class="sxs-lookup"><span data-stu-id="207c6-172">Mobile Device Viewport Mode</span></span>  

<span data-ttu-id="207c6-173">特定のモバイルデバイスのサイズをシミュレートするには、 **デバイス** の一覧からデバイスを選びます。</span><span class="sxs-lookup"><span data-stu-id="207c6-173">To simulate the dimensions of a specific mobile device, select the device from the **Device** list.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   <span data-ttu-id="207c6-175">**デバイス**の一覧</span><span class="sxs-lookup"><span data-stu-id="207c6-175">The **Device** list</span></span>  
:::image-end:::  

#### <span data-ttu-id="207c6-176">ビューポートを横方向に回転する</span><span class="sxs-lookup"><span data-stu-id="207c6-176">Rotate the viewport to landscape orientation</span></span>  

<span data-ttu-id="207c6-177">Web ページを横方向にテストします。</span><span class="sxs-lookup"><span data-stu-id="207c6-177">Test your webpage in landscape orientation.</span></span>  

*   <span data-ttu-id="207c6-178">ビューポートを横方向に回転するには、[ **回転** \ (回転 \)] を選び ![ ][ImageRotateIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="207c6-178">To rotate the viewport to landscape orientation, choose **Rotate** \(![Rotate][ImageRotateIcon]\).</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       <span data-ttu-id="207c6-180">横方向に表示されたページ</span><span class="sxs-lookup"><span data-stu-id="207c6-180">Page displayed in landscape orientation</span></span>  
    :::image-end:::  
    
> [!NOTE]
> <span data-ttu-id="207c6-181">**デバイスのツールバー**が狭い場合、[**回転**] ボタンは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="207c6-181">The **Rotate** button disappears if your **Device Toolbar** is narrow.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="207c6-183">**デバイスのツールバー**</span><span class="sxs-lookup"><span data-stu-id="207c6-183">The **Device Toolbar**</span></span>  
:::image-end:::  

<span data-ttu-id="207c6-184">詳細については、「 [印刷の向きを設定](#set-orientation)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="207c6-184">For more information, go to [Set orientation](#set-orientation).</span></span>  

#### <span data-ttu-id="207c6-185">デバイスフレームの表示</span><span class="sxs-lookup"><span data-stu-id="207c6-185">Show device frame</span></span>  

<span data-ttu-id="207c6-186">IPhone 6 などの特定のモバイルデバイスのサイズをシミュレートするときに、ビューポートの周りに物理デバイスフレームを表示します。</span><span class="sxs-lookup"><span data-stu-id="207c6-186">Display the physical device frame around the viewport when you simulate the dimensions of a specific mobile device such as an iPhone 6.</span></span>  

1.  <span data-ttu-id="207c6-187">**その他のオプション**を開きます。</span><span class="sxs-lookup"><span data-stu-id="207c6-187">Open **More options**.</span></span>  
1.  <span data-ttu-id="207c6-188">[ **デバイスフレームの表示]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="207c6-188">Choose **Show device frame**.</span></span>  

> [!NOTE]
> <span data-ttu-id="207c6-189">特定のデバイスのデバイスフレームが表示されない場合は、DevTools にそのオプション用の art がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="207c6-189">If you do not see a device frame for a particular device, it means that DevTools does not have art for that option.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         <span data-ttu-id="207c6-191">デバイスフレームの表示</span><span class="sxs-lookup"><span data-stu-id="207c6-191">Show device frame</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         <span data-ttu-id="207c6-193">IPhone 6 のデバイスフレーム</span><span class="sxs-lookup"><span data-stu-id="207c6-193">The device frame for the iPhone 6</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="207c6-194">カスタムモバイルデバイスを追加する</span><span class="sxs-lookup"><span data-stu-id="207c6-194">Add a custom mobile device</span></span>  

<span data-ttu-id="207c6-195">必要なモバイルデバイスオプションが既定のリストに含まれていない場合は、カスタムデバイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="207c6-195">If the mobile device option that you need is not included on the default list, you may add a custom device.</span></span>  <span data-ttu-id="207c6-196">カスタムデバイスを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="207c6-196">To add a custom device, complete the following steps.</span></span>  

1.  <span data-ttu-id="207c6-197">[ **Edit**] >**デバイス**の一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-197">Choose the **Device** list > **Edit**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       <span data-ttu-id="207c6-199">[**編集**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="207c6-199">Choose **Edit**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="207c6-200">[ **カスタムデバイスの追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="207c6-200">Choose **Add custom device**.</span></span>  
1.  <span data-ttu-id="207c6-201">エミュレートされた **デバイス**では、デバイス名、画面の幅、およびカスタムデバイスの画面の高さを入力します。</span><span class="sxs-lookup"><span data-stu-id="207c6-201">On **Emulated Devices**, enter a device name, screen width, and screen height for the custom device.</span></span>  <span data-ttu-id="207c6-202">[デバイスのピクセル比率][MDNWindowDevicePixelRatio]、[ユーザーエージェントの文字列][MDNUserAgent]、[デバイスの種類](#set-the-device-type)の各フィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="207c6-202">The [device pixel ratio][MDNWindowDevicePixelRatio], [user agent string][MDNUserAgent], and [device type](#set-the-device-type) fields are optional.</span></span>  <span data-ttu-id="207c6-203">[デバイスの種類] フィールドは既定で [ **モバイル**] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="207c6-203">The device type field defaults to **Mobile**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       <span data-ttu-id="207c6-205">カスタムデバイスを作成する</span><span class="sxs-lookup"><span data-stu-id="207c6-205">Create a custom device</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="207c6-206">ルーラーを表示する</span><span class="sxs-lookup"><span data-stu-id="207c6-206">Show rulers</span></span>  

<span data-ttu-id="207c6-207">画面のサイズを測定する必要がある場合は、ルーラーを使用して画面サイズをピクセル単位で測定することができます。</span><span class="sxs-lookup"><span data-stu-id="207c6-207">If you need to measure screen dimensions, you may use rulers to measure the screen size in pixels.</span></span>  <span data-ttu-id="207c6-208">[**その他のオプション**] を選択  >  **Show rulers**すると、ビューポートの左上にルーラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="207c6-208">Choose **More options** > **Show rulers** to display rulers above and to the left of your viewport.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         <span data-ttu-id="207c6-210">ルーラーを表示するためのメニュー項目</span><span class="sxs-lookup"><span data-stu-id="207c6-210">Menu item to display rulers</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         <span data-ttu-id="207c6-212">ビューポートの左上にあるルーラー</span><span class="sxs-lookup"><span data-stu-id="207c6-212">Rulers above and to the left of the viewport</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="207c6-213">ビューポートをズームする</span><span class="sxs-lookup"><span data-stu-id="207c6-213">Zoom the viewport</span></span>  

<span data-ttu-id="207c6-214">ページの外観を複数のズームレベルでテストするには、[ **ズーム** ] リストを使用して拡大または縮小します。</span><span class="sxs-lookup"><span data-stu-id="207c6-214">To test the look and feel of your page at multiple zoom levels, use the **Zoom** list to zoom in or out.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **<span data-ttu-id="207c6-216">ズーム</span><span class="sxs-lookup"><span data-stu-id="207c6-216">Zoom</span></span>**  
:::image-end:::  

## <span data-ttu-id="207c6-217">ネットワークと CPU を調整する</span><span class="sxs-lookup"><span data-stu-id="207c6-217">Throttle the network and CPU</span></span>  

<span data-ttu-id="207c6-218">多くの場合、モバイルデバイスではネットワークと CPU の制約があります。</span><span class="sxs-lookup"><span data-stu-id="207c6-218">Mobile devices often have network and CPU constraints.</span></span>  <span data-ttu-id="207c6-219">ページの読み込みの速度と、さまざまなインターネットおよび CPU の速度での応答方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="207c6-219">Ensure you test how quickly your page loads and how it responds at different internet and CPU speeds.</span></span>  

<span data-ttu-id="207c6-220">ネットワークと CPU を調整します。</span><span class="sxs-lookup"><span data-stu-id="207c6-220">Throttle the network and CPU.</span></span>  

1.  <span data-ttu-id="207c6-221">[ **スロットル** リスト] を選択して、事前設定を [ **中間層モバイル** ] または [ **ローエンド] モバイル**に変更します。</span><span class="sxs-lookup"><span data-stu-id="207c6-221">Choose **Throttle** list and change the preset to **Mid-tier mobile** or **Low-end mobile**.</span></span>  
    *   <span data-ttu-id="207c6-222">**ミッドティアのモバイル** では `fast 3G` 、CPU のシミュレーションと調整を行います。</span><span class="sxs-lookup"><span data-stu-id="207c6-222">**Mid-tier mobile** simulates `fast 3G` and throttles your CPU.</span></span>  <span data-ttu-id="207c6-223">通常よりも4倍遅くなります。</span><span class="sxs-lookup"><span data-stu-id="207c6-223">It is four times slower than normal.</span></span>  
    *   <span data-ttu-id="207c6-224">**ローエンドの携帯電話** では、 `slow 3G` CPU のシミュレーションと調整を行います。</span><span class="sxs-lookup"><span data-stu-id="207c6-224">**Low-end mobile** simulates `slow 3G` and throttles your CPU.</span></span>  <span data-ttu-id="207c6-225">通常よりも6倍遅くなります。</span><span class="sxs-lookup"><span data-stu-id="207c6-225">It is six times slower than normal.</span></span>  
    
<span data-ttu-id="207c6-226">すべての調整は、ノート pc またはデスクトップの通常の機能に基づいています。</span><span class="sxs-lookup"><span data-stu-id="207c6-226">All of the throttling is based upon the normal capability of your laptop or desktop.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   <span data-ttu-id="207c6-228">デバイスツールバーの **スロットル** リスト</span><span class="sxs-lookup"><span data-stu-id="207c6-228">The **Throttle** list in the Device Toolbar</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="207c6-229">**スロットルリスト**が非表示になっている場合、**デバイスのツールバー**は狭すぎます。</span><span class="sxs-lookup"><span data-stu-id="207c6-229">If the **Throttle list** is hidden, your **Device Toolbar** is too narrow.</span></span>  <span data-ttu-id="207c6-230">**スロットルの一覧**にアクセスするには、デバイスの**ツールバー**の幅を広げます。</span><span class="sxs-lookup"><span data-stu-id="207c6-230">To access the **Throttle list**, increase the width of the **Device Toolbar**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="207c6-232">**デバイスのツールバー**</span><span class="sxs-lookup"><span data-stu-id="207c6-232">The **Device Toolbar**</span></span>  
:::image-end:::  

### <span data-ttu-id="207c6-233">CPU のみを調整する</span><span class="sxs-lookup"><span data-stu-id="207c6-233">Throttle the CPU only</span></span>  

<span data-ttu-id="207c6-234">ネットワークではなく CPU のみを調整するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="207c6-234">To throttle the CPU only and not the network, complete the following steps.</span></span>

1.  <span data-ttu-id="207c6-235">[ **パフォーマンス** ] パネルを選択し、[ **キャプチャ設定** ] ( ![ キャプチャ設定) を選択し ][ImageCaptureIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="207c6-235">Choose the **Performance** panel, and choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span></span>
1.  <span data-ttu-id="207c6-236">**CPU**  >  の**4 倍の速度**または6x の**減速**を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-236">Choose **CPU** > **4x slowdown** or **6x slowdown**.</span></span>
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       <span data-ttu-id="207c6-238">**パフォーマンス**パネルの**CPU**リスト</span><span class="sxs-lookup"><span data-stu-id="207c6-238">The **CPU** list in the **Performance** panel</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="207c6-239">ネットワークのみを調整する</span><span class="sxs-lookup"><span data-stu-id="207c6-239">Throttle the network only</span></span>  

<span data-ttu-id="207c6-240">ネットワークを調整するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="207c6-240">To throttle the network only, complete the following steps.</span></span>

1.  <span data-ttu-id="207c6-241">[ **ネットワーク** ] パネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-241">Choose the **Network** panel.</span></span>
1.  <span data-ttu-id="207c6-242">「**オンライン**  >  **高速 3g** 」または「**低速 3g**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-242">Choose **Online** > **Fast 3G** or **Slow 3G**.</span></span>
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-network-throttle.msft.png":::
       <span data-ttu-id="207c6-244">[ネットワーク] パネルの **スロットル** リスト</span><span class="sxs-lookup"><span data-stu-id="207c6-244">The **Throttle** list in the Network panel</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="207c6-245">または、 `Control` + `Shift` + `P` \ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択して**コマンドメニュー**を開き、「 `3G` 高速な**3g 調整を有効**にする」または「**低速な3g 調整を有効**にする」を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-245">Or select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**, type `3G`, and choose **Enable fast 3G throttling** or **Enable slow 3G throttling**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       <span data-ttu-id="207c6-247">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="207c6-247">The **Command Menu**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="207c6-248">また、[ **パフォーマンス** ] パネルからネットワークの調整を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="207c6-248">You may also set network throttling from the **Performance** panel.</span></span>  

1.  <span data-ttu-id="207c6-249">[ **キャプチャの設定** ] (キャプチャ設定) を選択し、[ ![ ][ImageCaptureIcon] **ネットワーク** ] リストを選択して、[設定] を [ **高速 3g** ] または [ **低速 3g**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="207c6-249">Choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\) and choose the **Network** list and change the preset to **Fast 3G** or **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       <span data-ttu-id="207c6-251">**パフォーマンス**パネルからネットワーク調整を設定する</span><span class="sxs-lookup"><span data-stu-id="207c6-251">Set network throttling from the **Performance** panel</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="207c6-252">位置情報を上書きする</span><span class="sxs-lookup"><span data-stu-id="207c6-252">Override geolocation</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="207c6-253">適切に表示するために、モバイルデバイスからの位置情報に依存しているページの場合は、位置情報オーバーライド UI を使って、さまざまな geolocations 場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="207c6-253">If your page depends on geolocation information from a mobile device to render properly, provide different geolocations using the geolocation overriding UI.</span></span>  

      1.  <span data-ttu-id="207c6-254">[**カスタマイズと制御] を選択して、** ( `...` \)**その他のツール**  >  **センサー**> します。</span><span class="sxs-lookup"><span data-stu-id="207c6-254">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         <span data-ttu-id="207c6-256">位置情報の**センサー**</span><span class="sxs-lookup"><span data-stu-id="207c6-256">**Sensors** for geolocation</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="207c6-257">コマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="207c6-257">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="207c6-258">`Control` + `Shift` + `P` \ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-258">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="207c6-259">「」 `Sensors` と入力して、「 **センサーを表示**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-259">Type `Sensors`, and choose **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         <span data-ttu-id="207c6-261">位置情報の**センサーを表示する**</span><span class="sxs-lookup"><span data-stu-id="207c6-261">**Show Sensors** for geolocation</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="207c6-262">[ **センサー** ] パネルで、[ **場所** ] ドロップダウンメニューを使用して、devtools に含まれている既定の場所のいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="207c6-262">On the **Sensors** panel, you may select one of the preset locations included in DevTools using the **Location** drop-down menu.</span></span>  <span data-ttu-id="207c6-263">カスタムの場所を入力するには、[**その他...** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-263">To enter a custom location, choose **Other…**</span></span> <span data-ttu-id="207c6-264">目的の場所の座標を入力します。</span><span class="sxs-lookup"><span data-stu-id="207c6-264">and enter the coordinates of your custom location.</span></span>  <span data-ttu-id="207c6-265">位置情報を利用できないときにエラー状態のページをテストするには、[ **場所を使用できませ**ん] を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-265">To test your page in an error state when location information is unavailable, choose **Location unavailable**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    <span data-ttu-id="207c6-267">既定の場所が選択されている**センサー**パネル。</span><span class="sxs-lookup"><span data-stu-id="207c6-267">**Sensors** panel with a preset location selected.</span></span>  
:::image-end:::

## <span data-ttu-id="207c6-268">向きを設定する</span><span class="sxs-lookup"><span data-stu-id="207c6-268">Set orientation</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="207c6-269">適切に表示するために、モバイルデバイスからの向き情報に依存するページの場合は、方向 UI を開きます。</span><span class="sxs-lookup"><span data-stu-id="207c6-269">If your page depends on orientation information from a mobile device to render properly, open the orientation UI.</span></span>  

      1.  <span data-ttu-id="207c6-270">[**カスタマイズと制御] を選択して、** ( `...` \)**その他のツール**  >  **センサー**> します。</span><span class="sxs-lookup"><span data-stu-id="207c6-270">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         <span data-ttu-id="207c6-272">向きの**センサー**</span><span class="sxs-lookup"><span data-stu-id="207c6-272">**Sensors** for orientation</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="207c6-273">コマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="207c6-273">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="207c6-274">`Control` + `Shift` + `P` \ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-274">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="207c6-275">「」 `Sensors` と入力して、「 **センサーを表示**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-275">Type `Sensors`, and choose **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         <span data-ttu-id="207c6-277">向きの**センサーを表示する**</span><span class="sxs-lookup"><span data-stu-id="207c6-277">**Show Sensors** for orientation</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="207c6-278">[ **センサー** ] パネルで、[ **印刷の向き** ] ドロップダウンメニューから既定の向きを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="207c6-278">On the **Sensors** panel, you may select a preset orientation from the **Orientation** drop-down menu.</span></span>  <span data-ttu-id="207c6-279">独自の向きを入力するには、[ **ユーザー設定の向き**] を選択し、独自の [アルファ][MDNDeviceOrientaitonAlpha]、 [ベータ][MDNDeviceOrientaitonBeta]、および [ガンマ][MDNDeviceOrientaitonGamma] 値を入力します。</span><span class="sxs-lookup"><span data-stu-id="207c6-279">To enter your own orientation, choose **Custom orientation**, and enter your own [alpha][MDNDeviceOrientaitonAlpha], [beta][MDNDeviceOrientaitonBeta], and [gamma][MDNDeviceOrientaitonGamma] values.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    <span data-ttu-id="207c6-281">**センサー**パネルの [**向き**] オプション</span><span class="sxs-lookup"><span data-stu-id="207c6-281">**Orientation** options on the **Sensors** panel</span></span>  
:::image-end:::  

## <span data-ttu-id="207c6-282">ユーザーエージェント文字列を設定する</span><span class="sxs-lookup"><span data-stu-id="207c6-282">Set user agent string</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="207c6-283">ページがモバイルデバイスからのユーザーエージェント文字列に依存して適切に表示される場合は、[ **ネットワークの条件** ] パネルを使用して、さまざまなユーザーエージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="207c6-283">If your page depends on the user agent string from a mobile device to render properly, use the **Network conditions** panel to provide different user agent strings.</span></span>  
      
      1.  <span data-ttu-id="207c6-284">[**カスタマイズと制御 devtools** \ (\)] を選択して、 `...` **その他**  >  のツールの**ネットワーク条件**> します。</span><span class="sxs-lookup"><span data-stu-id="207c6-284">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Network conditions**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         <span data-ttu-id="207c6-286">[**その他のツール**] メニューの [**ネットワークの状態**] エントリ</span><span class="sxs-lookup"><span data-stu-id="207c6-286">**Network conditions** entry in the **More tools** menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="207c6-287">コマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="207c6-287">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="207c6-288">`Control` + `Shift` + `P` \ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-288">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="207c6-289">「 `Network conditions` **ネットワーク条件を表示**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-289">Type `Network conditions`, and choose **Show Network conditions**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **<span data-ttu-id="207c6-291">ネットワークの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="207c6-291">Show Network conditions</span></span>**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="207c6-292">[ **ユーザーエージェント**] の横にある **[自動的に選択** する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="207c6-292">Next to **User agent**, clear the **Select automatically** checkbox.</span></span>  <span data-ttu-id="207c6-293">次に、[ **カスタム** ] を選択して、定義済みのユーザーエージェント文字列の一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="207c6-293">Then, choose **Custom...** to select from a list of predefined user agent strings.</span></span>  <span data-ttu-id="207c6-294">独自のユーザーエージェント文字列を入力するには、[ **カスタムユーザーエージェントの入力**] に文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="207c6-294">To enter your own user agent string, enter the string in **Enter a custom user agent**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    <span data-ttu-id="207c6-296">MacOS でユーザーエージェント文字列を Microsoft Edge に設定します。</span><span class="sxs-lookup"><span data-stu-id="207c6-296">Set the user agent string to Microsoft Edge on macOS</span></span>  
:::image-end:::  

## <span data-ttu-id="207c6-297">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="207c6-297">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureIcon]: ../media/capture-settings-icon.msft.png  
[ImageDeviceToolbarIcon]: ../media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[Devて Remoteデバッギング]:...「リモートデバッグ Android デバイスの使用を開始する」をご覧ください。Microsoft ドキュメント "
[DevToolsRemoteDebugging]: ../remote-debugging/index.md "Get started with remote debugging Android devices | Microsoft Docs"  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window. Deviceピクセルの比率 |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "ユーザーエージェント |MDN"  
[MDNDeviceOrientaitonAlpha]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/alpha "DeviceOrientationEvent |MDN"  
[MDNDeviceOrientaitonBeta]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/beta "DeviceOrientationEvent |MDN"  
[MDNDeviceOrientaitonGamma]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/gamma "DeviceOrientationEvent |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "最初の順序での Wikipedia の順序"  

> [!NOTE]
> <span data-ttu-id="207c6-305">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="207c6-305">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="207c6-306">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="207c6-306">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="207c6-308">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="207c6-308">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
