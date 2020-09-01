---
title: Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6973f28a0cb530e8928976adb1354fa7471ee343
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10985312"
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





# <span data-ttu-id="03039-103">Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="03039-103">Simulate mobile devices with Device Mode in Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="03039-104">モバイルデバイスでのページの外観と実行方法については、デバイスモードを使用します。</span><span class="sxs-lookup"><span data-stu-id="03039-104">Use Device Mode to approximate how your page looks and performs on a mobile device.</span></span>  

<span data-ttu-id="03039-105">デバイスモードは、モバイルデバイスをシミュレートするために役立つ Microsoft Edge DevTools の機能のルースコレクションの名前です。</span><span class="sxs-lookup"><span data-stu-id="03039-105">Device Mode is the name for the loose collection of features in Microsoft Edge DevTools that help you simulate mobile devices.</span></span>  <span data-ttu-id="03039-106">次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="03039-106">These features include:</span></span>  

*   [<span data-ttu-id="03039-107">モバイルビューポートのシミュレート</span><span class="sxs-lookup"><span data-stu-id="03039-107">Simulating a mobile viewport</span></span>](#simulate-a-mobile-viewport)  
*   [<span data-ttu-id="03039-108">ネットワークの調整</span><span class="sxs-lookup"><span data-stu-id="03039-108">Throttling the network</span></span>](#throttle-the-network-only)  
*   [<span data-ttu-id="03039-109">CPU の調整</span><span class="sxs-lookup"><span data-stu-id="03039-109">Throttling the CPU</span></span>](#throttle-the-cpu-only)  
*   [<span data-ttu-id="03039-110">位置情報のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="03039-110">Simulating geolocation</span></span>](#override-geolocation)  
*   [<span data-ttu-id="03039-111">向きの設定</span><span class="sxs-lookup"><span data-stu-id="03039-111">Setting orientation</span></span>](#set-orientation)  

## <span data-ttu-id="03039-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="03039-112">Limitations</span></span>   

<span data-ttu-id="03039-113">デバイスモードは、モバイルデバイスでページがどのように表示されるか、どのように感じられるかについての [最初の概算][WikiApproximation] と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="03039-113">Think of Device Mode as a [first-order approximation][WikiApproximation] of how your page looks and feels on a mobile device.</span></span>  <span data-ttu-id="03039-114">デバイスモードでは、モバイルデバイスで実際にコードを実行することはありません。</span><span class="sxs-lookup"><span data-stu-id="03039-114">With Device Mode you do not actually run your code on a mobile device.</span></span>  <span data-ttu-id="03039-115">ノート pc またはデスクトップでモバイルユーザーエクスペリエンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="03039-115">You simulate the mobile user experience from your laptop or desktop.</span></span>  

<span data-ttu-id="03039-116">DevTools はシミュレートできないモバイルデバイスにはいくつかの側面があります。</span><span class="sxs-lookup"><span data-stu-id="03039-116">There are some aspects of mobile devices that DevTools will never be able to simulate.</span></span>  <span data-ttu-id="03039-117">たとえば、モバイル Cpu のアーキテクチャは、ノート pc またはデスクトップ Cpu のアーキテクチャとは大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="03039-117">For example, the architecture of mobile CPUs is very different than the architecture of laptop or desktop CPUs.</span></span>  <span data-ttu-id="03039-118">疑わしい場合は、実際にモバイルデバイスでページを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="03039-118">When in doubt, your best bet is to actually run your page on a mobile device.</span></span>  <span data-ttu-id="03039-119">[リモートデバッグ] を使用して、モバイルデバイスで実際に実行しているときに、ノート pc またはデスクトップからページのコードを表示、変更、デバッグ、プロファイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="03039-119">Use [Remote Debugging][DevToolsRemoteDebugging] to view, change, debug, and profile the code of a page from your laptop or desktop while it actually runs on a mobile device.</span></span>  

## <span data-ttu-id="03039-120">モバイルビューポートのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="03039-120">Simulate a mobile viewport</span></span>   

<span data-ttu-id="03039-121">[ **デバイスツールバーの切り替え** ] ( ![ デバイスツールバー ][ImageDeviceToolbarIcon] \ の切り替え) をクリックして、モバイルビューポートをシミュレートできる UI を開きます。</span><span class="sxs-lookup"><span data-stu-id="03039-121">Click **Toggle Device Toolbar** \(![Toggle Device Toolbar][ImageDeviceToolbarIcon]\) to open the UI that enables you to simulate a mobile viewport.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="03039-123">デバイスのツールバー</span><span class="sxs-lookup"><span data-stu-id="03039-123">The Device Toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="03039-124">既定では、デバイスのツールバーは、応答性のあるビューポートモードで開きます。</span><span class="sxs-lookup"><span data-stu-id="03039-124">By default the Device Toolbar opens in Responsive Viewport Mode.</span></span>  

### <span data-ttu-id="03039-125">応答性ビューポートモード</span><span class="sxs-lookup"><span data-stu-id="03039-125">Responsive Viewport Mode</span></span>   

<span data-ttu-id="03039-126">ハンドルをドラッグして、ビューポートのサイズを必要なサイズに変更します。</span><span class="sxs-lookup"><span data-stu-id="03039-126">Drag the handles to resize the viewport to whatever dimensions you need.</span></span>  <span data-ttu-id="03039-127">または、[幅] ボックスと [高さ] ボックスに特定の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="03039-127">Or, enter specific values in the width and height boxes.</span></span>  <span data-ttu-id="03039-128">次の図では、幅がに設定され、 `626` 高さがに設定されて `516` います。</span><span class="sxs-lookup"><span data-stu-id="03039-128">In the following figure, the width is set to `626` and the height is set to `516`.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
   <span data-ttu-id="03039-130">応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル</span><span class="sxs-lookup"><span data-stu-id="03039-130">The handles for changing the dimensions of the viewport when in Responsive Viewport Mode</span></span>  
:::image-end:::  

#### <span data-ttu-id="03039-131">メディアクエリを表示する</span><span class="sxs-lookup"><span data-stu-id="03039-131">Show media queries</span></span>   

<span data-ttu-id="03039-132">ビューポートの上にメディアクエリのブレークポイントを表示するには、[ **その他のオプション** ] をクリックし、[ **メディアクエリの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03039-132">To show media query breakpoints above your viewport, click **More options** and then select **Show media queries**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="メディアクエリを表示する" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **<span data-ttu-id="03039-134">メディアクエリを表示する</span><span class="sxs-lookup"><span data-stu-id="03039-134">Show media queries</span></span>**  
:::image-end:::  

<span data-ttu-id="03039-135">ブレークポイントをクリックして、ブレークポイントがトリガーされるようにビューポートの幅を変更します。</span><span class="sxs-lookup"><span data-stu-id="03039-135">Click a breakpoint to change the width of the viewport so that the breakpoint gets triggered.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="ブレークポイントをクリックしてビューポートの幅を変更する" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   <span data-ttu-id="03039-137">ブレークポイントをクリックしてビューポートの幅を変更する</span><span class="sxs-lookup"><span data-stu-id="03039-137">Click a breakpoint to change the width of the viewport</span></span>  
:::image-end:::  

#### <span data-ttu-id="03039-138">デバイスの種類を設定する</span><span class="sxs-lookup"><span data-stu-id="03039-138">Set the device type</span></span>   

<span data-ttu-id="03039-139">[ **デバイスの種類** ] の一覧を使用して、モバイルデバイスやデスクトップデバイスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="03039-139">Use the **Device Type** list to simulate a mobile device or desktop device.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="[デバイスの種類] の一覧" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   <span data-ttu-id="03039-141">[ **デバイスの種類** ] の一覧</span><span class="sxs-lookup"><span data-stu-id="03039-141">The **Device Type** list</span></span>  
:::image-end:::  

<span data-ttu-id="03039-142">次の表では、オプションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="03039-142">The table below describes the differences between the options.</span></span>  <span data-ttu-id="03039-143">**レンダリングメソッド** は、Microsoft Edge がモバイルビューポートまたはデスクトップビューポートとしてページをレンダリングするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="03039-143">**Rendering method** refers to whether Microsoft Edge renders the page as a mobile or desktop viewport.</span></span>  <span data-ttu-id="03039-144">**カーソルアイコン** は、ページ上にマウスポインターを置いたときに表示されるカーソルの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="03039-144">**Cursor icon** refers to what type of cursor you see when you hover over the page.</span></span>  <span data-ttu-id="03039-145">**イベント** は、 `touch` `click` ページを操作するときにそのページが起動するか、イベントを発生させるかを示します。</span><span class="sxs-lookup"><span data-stu-id="03039-145">**Events fired** refers to whether the page fires `touch` or `click` events when you interact with the page.</span></span>  

| <span data-ttu-id="03039-146">オプション</span><span class="sxs-lookup"><span data-stu-id="03039-146">Option</span></span> | <span data-ttu-id="03039-147">レンダリング方法</span><span class="sxs-lookup"><span data-stu-id="03039-147">Rendering method</span></span> | <span data-ttu-id="03039-148">カーソルアイコン</span><span class="sxs-lookup"><span data-stu-id="03039-148">Cursor icon</span></span> | <span data-ttu-id="03039-149">イベントを発生させる</span><span class="sxs-lookup"><span data-stu-id="03039-149">Events fired</span></span> |  
|:--- |:--- |:--- |:--- |  
| <span data-ttu-id="03039-150">モバイル</span><span class="sxs-lookup"><span data-stu-id="03039-150">Mobile</span></span> | <span data-ttu-id="03039-151">モバイル</span><span class="sxs-lookup"><span data-stu-id="03039-151">Mobile</span></span> | <span data-ttu-id="03039-152">円形</span><span class="sxs-lookup"><span data-stu-id="03039-152">Circle</span></span> | <span data-ttu-id="03039-153">タッチ</span><span class="sxs-lookup"><span data-stu-id="03039-153">touch</span></span> |  
| <span data-ttu-id="03039-154">モバイル \ (タッチなし)</span><span class="sxs-lookup"><span data-stu-id="03039-154">Mobile \(no touch\)</span></span> | <span data-ttu-id="03039-155">モバイル</span><span class="sxs-lookup"><span data-stu-id="03039-155">Mobile</span></span> | <span data-ttu-id="03039-156">通常</span><span class="sxs-lookup"><span data-stu-id="03039-156">Normal</span></span> | <span data-ttu-id="03039-157"> で、</span><span class="sxs-lookup"><span data-stu-id="03039-157">click</span></span> |  
| <span data-ttu-id="03039-158">Desktop</span><span class="sxs-lookup"><span data-stu-id="03039-158">Desktop</span></span> | <span data-ttu-id="03039-159">Desktop</span><span class="sxs-lookup"><span data-stu-id="03039-159">Desktop</span></span> | <span data-ttu-id="03039-160">通常</span><span class="sxs-lookup"><span data-stu-id="03039-160">Normal</span></span> | <span data-ttu-id="03039-161"> で、</span><span class="sxs-lookup"><span data-stu-id="03039-161">click</span></span> |  
| <span data-ttu-id="03039-162">デスクトップ \ (タッチ \)</span><span class="sxs-lookup"><span data-stu-id="03039-162">Desktop \(touch\)</span></span> | <span data-ttu-id="03039-163">Desktop</span><span class="sxs-lookup"><span data-stu-id="03039-163">Desktop</span></span> | <span data-ttu-id="03039-164">円形</span><span class="sxs-lookup"><span data-stu-id="03039-164">Circle</span></span> | <span data-ttu-id="03039-165">タッチ</span><span class="sxs-lookup"><span data-stu-id="03039-165">touch</span></span> |  

> [!NOTE]
> <span data-ttu-id="03039-166">[ **デバイスの種類** ] の一覧が表示されない場合は、[ **その他のオプション** ] をクリックし、[デバイスの種類の **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03039-166">If you do not see the **Device Type** list, click **More options** and select **Add device type**.</span></span>  

### <span data-ttu-id="03039-167">モバイルデバイスのビューポートモード</span><span class="sxs-lookup"><span data-stu-id="03039-167">Mobile Device Viewport Mode</span></span>   

<span data-ttu-id="03039-168">特定のモバイルデバイスのサイズをシミュレートするには、 **デバイス** の一覧からデバイスを選びます。</span><span class="sxs-lookup"><span data-stu-id="03039-168">To simulate the dimensions of a specific mobile device, select the device from the **Device** list.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="デバイスの一覧" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   <span data-ttu-id="03039-170">**デバイス**の一覧</span><span class="sxs-lookup"><span data-stu-id="03039-170">The **Device** list</span></span>  
:::image-end:::  

#### <span data-ttu-id="03039-171">ビューポートを横方向に回転する</span><span class="sxs-lookup"><span data-stu-id="03039-171">Rotate the viewport to landscape orientation</span></span>   

<span data-ttu-id="03039-172">**Rotate** ![ ][ImageRotateIcon] ビューポートを横方向に回転するには、[回転 (回転 \)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03039-172">Click **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横方向" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
   <span data-ttu-id="03039-174">横方向</span><span class="sxs-lookup"><span data-stu-id="03039-174">Landscape orientation</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="03039-175">**デバイスのツールバー**が狭い場合、[**回転**] ボタンは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="03039-175">The **Rotate** button disappears if your **Device Toolbar** is narrow.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="03039-177">**デバイスのツールバー**</span><span class="sxs-lookup"><span data-stu-id="03039-177">The **Device Toolbar**</span></span>  
:::image-end:::  

<span data-ttu-id="03039-178">「 [方向を設定](#set-orientation)する」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="03039-178">See also [Set orientation](#set-orientation).</span></span>  

#### <span data-ttu-id="03039-179">デバイスフレームの表示</span><span class="sxs-lookup"><span data-stu-id="03039-179">Show device frame</span></span>   

<span data-ttu-id="03039-180">IPhone 6 など特定のモバイルデバイスのサイズをシミュレートする場合は、[ **その他のオプション** ] を開き、[ **デバイスフレームの表示** ] を選択して、ビューポートの周りに物理デバイスフレームを表示します。</span><span class="sxs-lookup"><span data-stu-id="03039-180">When simulating the dimensions of a specific mobile device like an iPhone 6, open **More options** and then select **Show device frame** to show the physical device frame around the viewport.</span></span>  

> [!NOTE]
> <span data-ttu-id="03039-181">特定のデバイスのデバイスフレームが表示されない場合は、DevTools にその特定のオプション用の art がないことが考えられます。</span><span class="sxs-lookup"><span data-stu-id="03039-181">If you do not see a device frame for a particular device, it probably means that DevTools just does not have art for that specific option.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="デバイスフレームの表示" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         <span data-ttu-id="03039-183">デバイスフレームの表示</span><span class="sxs-lookup"><span data-stu-id="03039-183">Show device frame</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="IPhone 6 のデバイスフレーム" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         <span data-ttu-id="03039-185">IPhone 6 のデバイスフレーム</span><span class="sxs-lookup"><span data-stu-id="03039-185">The device frame for the iPhone 6</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="03039-186">カスタムモバイルデバイスを追加する</span><span class="sxs-lookup"><span data-stu-id="03039-186">Add a custom mobile device</span></span>   

<span data-ttu-id="03039-187">カスタムデバイスを追加するには:</span><span class="sxs-lookup"><span data-stu-id="03039-187">To add a custom device:</span></span>  

1.  <span data-ttu-id="03039-188">**デバイス**の一覧をクリックし、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03039-188">Click the **Device** list and then select **Edit**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="[編集] を選ぶ" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       <span data-ttu-id="03039-190">[**編集**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="03039-190">Select **Edit**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="03039-191">[ **カスタムデバイスの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03039-191">Click **Add custom device**.</span></span>  
1.  <span data-ttu-id="03039-192">デバイスの名前、幅、高さを入力します。</span><span class="sxs-lookup"><span data-stu-id="03039-192">Enter a name, width, and height for the device.</span></span>  <span data-ttu-id="03039-193">[デバイスのピクセル比率][MDNWindowDevicePixelRatio]、[ユーザーエージェントの文字列][MDNUserAgent]、[デバイスの種類](#set-the-device-type)の各フィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="03039-193">The [device pixel ratio][MDNWindowDevicePixelRatio], [user agent string][MDNUserAgent], and [device type](#set-the-device-type) fields are optional.</span></span>  <span data-ttu-id="03039-194">[デバイスの種類] フィールドは、既定で [ **モバイル** ] に設定されているリストです。</span><span class="sxs-lookup"><span data-stu-id="03039-194">The device type field is the list that is set to **Mobile** by default.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="カスタムデバイスを作成する" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       <span data-ttu-id="03039-196">カスタムデバイスの作成</span><span class="sxs-lookup"><span data-stu-id="03039-196">Createa custom device</span></span>  
    :::image-end:::  

### <span data-ttu-id="03039-197">ルーラーを表示する</span><span class="sxs-lookup"><span data-stu-id="03039-197">Show rulers</span></span>   

<span data-ttu-id="03039-198">[ **その他のオプション** ] をクリックし、[ **ルーラーの表示** ] を選択して、ビューポートの左上にあるルーラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="03039-198">Click **More options** and then select **Show rulers** to see rulers above and to the left of your viewport.</span></span>  <span data-ttu-id="03039-199">ルーラーのサイズ調整単位はピクセルです。</span><span class="sxs-lookup"><span data-stu-id="03039-199">The sizing unit of the rulers is pixels.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="ルーラーを表示する" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         **<span data-ttu-id="03039-201">ルーラーを表示する</span><span class="sxs-lookup"><span data-stu-id="03039-201">Show rulers</span></span>**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="ビューポートの左上にあるルーラー" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         <span data-ttu-id="03039-203">ビューポートの左上にあるルーラー</span><span class="sxs-lookup"><span data-stu-id="03039-203">Rulers above and to the left of the viewport</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="03039-204">ビューポートをズームする</span><span class="sxs-lookup"><span data-stu-id="03039-204">Zoom the viewport</span></span>   

<span data-ttu-id="03039-205">拡大または縮小するには、[ **ズーム** ] リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="03039-205">Use the **Zoom** list to zoom in or out.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="ズーム" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **<span data-ttu-id="03039-207">ズーム</span><span class="sxs-lookup"><span data-stu-id="03039-207">Zoom</span></span>**  
:::image-end:::  

## <span data-ttu-id="03039-208">ネットワークと CPU を調整する</span><span class="sxs-lookup"><span data-stu-id="03039-208">Throttle the network and CPU</span></span>   

<span data-ttu-id="03039-209">ネットワークと CPU を調整するには、[**調整**] の一覧から [**ミッドティアモバイル**] または [**ローエンド**] のモバイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="03039-209">To throttle the network and CPU, select **Mid-tier mobile** or **Low-end mobile** from the **Throttle** list.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="スロットルリスト" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   <span data-ttu-id="03039-211">**スロットル**リスト</span><span class="sxs-lookup"><span data-stu-id="03039-211">The **Throttle** list</span></span>  
:::image-end:::  

<span data-ttu-id="03039-212">**ミッドティアモバイル** では、高速3g をシミュレートし、CPU を調整して、通常よりも4倍遅くなるようにします。</span><span class="sxs-lookup"><span data-stu-id="03039-212">**Mid-tier mobile** simulates fast 3G and throttles your CPU so that it is 4 times slower than normal.</span></span>  <span data-ttu-id="03039-213">**ローエンドの携帯電話** では、低速の3g がシミュレートされ、CPU の6倍が通常よりも遅くなります。</span><span class="sxs-lookup"><span data-stu-id="03039-213">**Low-end mobile** simulates slow 3G and throttles your CPU 6 times slower than normal.</span></span>  <span data-ttu-id="03039-214">調整は、ノート pc またはデスクトップの通常の機能に関連していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="03039-214">Keep in mind that the throttling is relative to the normal capability of your laptop or desktop.</span></span>  

> [!NOTE]
> <span data-ttu-id="03039-215">**デバイスのツールバー**が狭い場合、**スロットル**リストは表示されません。</span><span class="sxs-lookup"><span data-stu-id="03039-215">The **Throttle** list is hidden if your **Device Toolbar** is narrow.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="デバイスのツールバー" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="03039-217">**デバイスのツールバー**</span><span class="sxs-lookup"><span data-stu-id="03039-217">The **Device Toolbar**</span></span>  
:::image-end:::  

### <span data-ttu-id="03039-218">CPU のみを調整する</span><span class="sxs-lookup"><span data-stu-id="03039-218">Throttle the CPU only</span></span>   

<span data-ttu-id="03039-219">ネットワークではなく CPU のみを調整するには、[**パフォーマンス**] パネルに移動し、[**キャプチャの設定**] (キャプチャ設定) をクリックして、[ ![ ][ImageCaptureIcon] **CPU** ] の一覧から [ **4 倍速**(減速)] または [ **6x** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03039-219">To throttle the CPU only and not the network, go to the **Performance** panel, click **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\), and then select **4x slowdown** or **6x slowdown** from the **CPU** list.</span></span>  

:::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="CPU リスト" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
   <span data-ttu-id="03039-221">**CPU**リスト</span><span class="sxs-lookup"><span data-stu-id="03039-221">The **CPU** list</span></span>  
:::image-end:::  

### <span data-ttu-id="03039-222">ネットワークのみを調整する</span><span class="sxs-lookup"><span data-stu-id="03039-222">Throttle the network only</span></span>   

<span data-ttu-id="03039-223">ネットワークのみを対象とし、CPU は調整しない場合は、**ネットワーク**パネルを開いて、[**スロットル**] の一覧から [ **Fast 3G** ] または [**低速の 3g** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03039-223">To throttle the network only and not the CPU, go the **Network** panel and select **Fast 3G** or **Slow 3G** from the **Throttle** list.</span></span>  

:::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="スロットルリスト" lightbox="../media/device-mode-network-throttle.msft.png":::
   <span data-ttu-id="03039-225">**スロットル**リスト</span><span class="sxs-lookup"><span data-stu-id="03039-225">The **Throttle** list</span></span>  
:::image-end:::  

<span data-ttu-id="03039-226">または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押すと、**コマンドメニュー**が開き、「 `3G` 高速な**3g 調整を有効**にする」または「**低速な3g 調整**を有効にする」を選択します。</span><span class="sxs-lookup"><span data-stu-id="03039-226">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**, type `3G`, and select **Enable fast 3G throttling** or **Enable slow 3G throttling**.</span></span>  

:::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="コマンドメニュー" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
   <span data-ttu-id="03039-228">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="03039-228">The **Command Menu**</span></span>  
:::image-end:::  

<span data-ttu-id="03039-229">[ **パフォーマンス** ] パネルからネットワークの調整を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="03039-229">You can also set network throttling from the **Performance** panel.</span></span>  <span data-ttu-id="03039-230">「 **キャプチャ設定** 」 ( ![ キャプチャ設定 ][ImageCaptureIcon] ) をクリックして、「 **Fast 3G** 」または「 **低速な 3g** 」を **ネットワーク** リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="03039-230">Click **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\) and then select **Fast 3G** or **Slow 3G** from the **Network** list.</span></span>  

:::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="パフォーマンスパネルからネットワーク調整を設定する" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
   <span data-ttu-id="03039-232">**パフォーマンス**パネルからネットワーク調整を設定する</span><span class="sxs-lookup"><span data-stu-id="03039-232">Set network throttling from the **Performance** panel</span></span>  
:::image-end:::  

## <span data-ttu-id="03039-233">位置情報を無効にする</span><span class="sxs-lookup"><span data-stu-id="03039-233">Override geolocation</span></span>   

<span data-ttu-id="03039-234">位置情報を上書きする UI を開くには、[**ユーザー設定と制御**] をクリックして ( `...` \)、[**その他のツール**センサー] を選択し  >  **Sensors**ます。</span><span class="sxs-lookup"><span data-stu-id="03039-234">To open the geolocation overriding UI click **Customize and control DevTools** \(`...`\) and then select **More tools** > **Sensors**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="センサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
   **<span data-ttu-id="03039-236">センサー</span><span class="sxs-lookup"><span data-stu-id="03039-236">Sensors</span></span>**  
:::image-end:::  

<span data-ttu-id="03039-237">または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押してコマンドメニューを開き、「 `Sensors` 」と入力して、[**センサーの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03039-237">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `Sensors`, and then select **Show Sensors**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="センサーの表示" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
   **<span data-ttu-id="03039-239">センサーの表示</span><span class="sxs-lookup"><span data-stu-id="03039-239">Show Sensors</span></span>**  
:::image-end:::  

<span data-ttu-id="03039-240">[ **位置情報] の一覧から** いずれかのプリセットを選ぶか、[ **場所** の指定] を選んで独自の座標を入力するか、[場所を選択 **できません** ] を選択して、位置情報がエラー状態にあるときのページの動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="03039-240">Select one of the presets from the **Geolocation** list, or select **Custom location** to enter your own coordinates, or select **Location unavailable** to test out how your page behaves when geolocation is in an error state.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="位置情報" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
   **<span data-ttu-id="03039-242">位置情報</span><span class="sxs-lookup"><span data-stu-id="03039-242">Geolocation</span></span>**  
:::image-end:::  

## <span data-ttu-id="03039-243">向きを設定する</span><span class="sxs-lookup"><span data-stu-id="03039-243">Set orientation</span></span>   

:::row:::
   :::column span="":::
      <span data-ttu-id="03039-244">向きの UI を開くには、[カスタマイズ] をクリックし、[ **devtools** ] をクリックして、[ `...` **その他のツール**センサー] を選択し  >  **Sensors**ます。</span><span class="sxs-lookup"><span data-stu-id="03039-244">To open the orientation UI click **Customize and control DevTools** `...` and then select **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="センサー" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         **<span data-ttu-id="03039-246">センサー</span><span class="sxs-lookup"><span data-stu-id="03039-246">Sensors</span></span>**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="03039-247">または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押してコマンドメニューを開き、「 `Sensors` 」と入力して、[**センサーの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03039-247">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `Sensors`, and then select **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="センサーの表示" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **<span data-ttu-id="03039-249">センサーの表示</span><span class="sxs-lookup"><span data-stu-id="03039-249">Show Sensors</span></span>**  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="03039-250">[ **印刷の向き** ] の一覧からいずれかのプリセットを選択するか、[ **ユーザー設定の向き** ] を選択して、独自のアルファ、ベータ、およびガンマ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="03039-250">Select one of the presets from the **Orientation** list or select **Custom orientation** to set your own alpha, beta, and gamma values.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="Orientation" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
   **<span data-ttu-id="03039-252">Orientation</span><span class="sxs-lookup"><span data-stu-id="03039-252">Orientation</span></span>**  
:::image-end:::  

<!--  
 


-->  

<!--See [Join the DevTools community][DevToolsCommunity] for other ways to leave feedback.  -->  

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

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "最初の順序での Wikipedia の順序"  

> [!NOTE]
> <span data-ttu-id="03039-257">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="03039-257">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="03039-258">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="03039-258">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="03039-260">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="03039-260">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
