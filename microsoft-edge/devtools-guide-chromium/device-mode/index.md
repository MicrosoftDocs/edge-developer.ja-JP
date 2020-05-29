---
title: Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 10c1ee12777965778ebec2d257399dc231e2a01a
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607427"
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





# <span data-ttu-id="6f2b1-103">Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="6f2b1-103">Simulate Mobile Devices with Device Mode in Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="6f2b1-104">モバイルデバイスでのページの外観と実行方法については、デバイスモードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-104">Use Device Mode to approximate how your page looks and performs on a mobile device.</span></span>  

<span data-ttu-id="6f2b1-105">デバイスモードは、モバイルデバイスをシミュレートするために役立つ Microsoft Edge DevTools の機能のルースコレクションの名前です。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-105">Device Mode is the name for the loose collection of features in Microsoft Edge DevTools that help you simulate mobile devices.</span></span>  <span data-ttu-id="6f2b1-106">次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-106">These features include:</span></span>  

*   [<span data-ttu-id="6f2b1-107">モバイルビューポートのシミュレート</span><span class="sxs-lookup"><span data-stu-id="6f2b1-107">Simulating a mobile viewport</span></span>](#simulate-a-mobile-viewport)  
*   [<span data-ttu-id="6f2b1-108">ネットワークの調整</span><span class="sxs-lookup"><span data-stu-id="6f2b1-108">Throttling the network</span></span>](#throttle-the-network-only)  
*   [<span data-ttu-id="6f2b1-109">CPU の調整</span><span class="sxs-lookup"><span data-stu-id="6f2b1-109">Throttling the CPU</span></span>](#throttle-the-cpu-only)  
*   [<span data-ttu-id="6f2b1-110">位置情報のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="6f2b1-110">Simulating geolocation</span></span>](#override-geolocation)  
*   [<span data-ttu-id="6f2b1-111">向きの設定</span><span class="sxs-lookup"><span data-stu-id="6f2b1-111">Setting orientation</span></span>](#set-orientation)  

## <span data-ttu-id="6f2b1-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="6f2b1-112">Limitations</span></span>   

<span data-ttu-id="6f2b1-113">デバイスモードは、モバイルデバイスでページがどのように表示されるか、どのように感じられるかについての[最初の概算][WikiApproximation]と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-113">Think of Device Mode as a [first-order approximation][WikiApproximation] of how your page looks and feels on a mobile device.</span></span>  <span data-ttu-id="6f2b1-114">デバイスモードでは、モバイルデバイスで実際にコードを実行することはありません。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-114">With Device Mode you do not actually run your code on a mobile device.</span></span>  <span data-ttu-id="6f2b1-115">ノート pc またはデスクトップでモバイルユーザーエクスペリエンスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-115">You simulate the mobile user experience from your laptop or desktop.</span></span>  

<span data-ttu-id="6f2b1-116">DevTools はシミュレートできないモバイルデバイスにはいくつかの側面があります。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-116">There are some aspects of mobile devices that DevTools will never be able to simulate.</span></span>  <span data-ttu-id="6f2b1-117">たとえば、モバイル Cpu のアーキテクチャは、ノート pc またはデスクトップ Cpu のアーキテクチャとは大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-117">For example, the architecture of mobile CPUs is very different than the architecture of laptop or desktop CPUs.</span></span>  <span data-ttu-id="6f2b1-118">疑わしい場合は、実際にモバイルデバイスでページを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-118">When in doubt, your best bet is to actually run your page on a mobile device.</span></span>  <span data-ttu-id="6f2b1-119">[リモートデバッグ] を使用して、モバイルデバイスで実際に実行しているときに、ノート pc またはデスクトップからページのコードを表示、変更、デバッグ、プロファイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-119">Use [Remote Debugging][DevToolsRemoteDebugging] to view, change, debug, and profile the code of a page from your laptop or desktop while it actually runs on a mobile device.</span></span>  

## <span data-ttu-id="6f2b1-120">モバイルビューポートのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="6f2b1-120">Simulate a mobile viewport</span></span>   

<span data-ttu-id="6f2b1-121">[**デバイスツールバー**の切り替え] をクリックして ![ ][ImageDeviceToolbarIcon] 、モバイルビューポートをシミュレートできる UI を開きます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-121">Click **Toggle Device Toolbar** ![Toggle Device Toolbar][ImageDeviceToolbarIcon] to open the UI that enables you to simulate a mobile viewport.</span></span>  

> ##### <span data-ttu-id="6f2b1-122">図 1</span><span class="sxs-lookup"><span data-stu-id="6f2b1-122">Figure 1</span></span>  
> <span data-ttu-id="6f2b1-123">デバイスのツールバー</span><span class="sxs-lookup"><span data-stu-id="6f2b1-123">The Device Toolbar</span></span>  
> ![デバイスのツールバー][ImageDeviceToolbar]  

<span data-ttu-id="6f2b1-125">既定では、デバイスのツールバーは、応答性のあるビューポートモードで開きます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-125">By default the Device Toolbar opens in Responsive Viewport Mode.</span></span>  

### <span data-ttu-id="6f2b1-126">応答性ビューポートモード</span><span class="sxs-lookup"><span data-stu-id="6f2b1-126">Responsive Viewport Mode</span></span>   

<span data-ttu-id="6f2b1-127">ハンドルをドラッグして、ビューポートのサイズを必要なサイズに変更します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-127">Drag the handles to resize the viewport to whatever dimensions you need.</span></span>  <span data-ttu-id="6f2b1-128">または、[幅] ボックスと [高さ] ボックスに特定の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-128">Or, enter specific values in the width and height boxes.</span></span>  <span data-ttu-id="6f2b1-129">[図 2](#figure-2)では、幅がに設定され、 `626` 高さがに設定されて `516` います。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-129">In [Figure 2](#figure-2), the width is set to `626` and the height is set to `516`.</span></span>  

> ##### <span data-ttu-id="6f2b1-130">図 2</span><span class="sxs-lookup"><span data-stu-id="6f2b1-130">Figure 2</span></span>  
> <span data-ttu-id="6f2b1-131">応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル</span><span class="sxs-lookup"><span data-stu-id="6f2b1-131">The handles for changing the dimensions of the viewport when in Responsive Viewport Mode</span></span>  
> ![応答可能なビューポートモードのときにビューポートの寸法を変更するハンドル][ImageResponsiveHandles]  

#### <span data-ttu-id="6f2b1-133">メディアクエリを表示する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-133">Show media queries</span></span>   

<span data-ttu-id="6f2b1-134">ビューポートの上にメディアクエリのブレークポイントを表示するには、[**その他のオプション**] をクリックし、[**メディアクエリの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-134">To show media query breakpoints above your viewport, click **More options** and then select **Show media queries**.</span></span>  

> ##### <span data-ttu-id="6f2b1-135">図 3</span><span class="sxs-lookup"><span data-stu-id="6f2b1-135">Figure 3</span></span>  
> <span data-ttu-id="6f2b1-136">メディアクエリを表示する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-136">Show media queries</span></span>  
> ![メディアクエリを表示する][ImageShowMediaQueries]  

<span data-ttu-id="6f2b1-138">ブレークポイントをクリックして、ブレークポイントがトリガーされるようにビューポートの幅を変更します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-138">Click a breakpoint to change the width of the viewport so that the breakpoint gets triggered.</span></span>  

> ##### <span data-ttu-id="6f2b1-139">図 4</span><span class="sxs-lookup"><span data-stu-id="6f2b1-139">Figure 4</span></span>  
> <span data-ttu-id="6f2b1-140">ブレークポイントをクリックしてビューポートの幅を変更する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-140">Click a breakpoint to change the width of the viewport</span></span>  
> ![ブレークポイントをクリックしてビューポートの幅を変更する][ImageBreakpoint]  

#### <span data-ttu-id="6f2b1-142">デバイスの種類を設定する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-142">Set the device type</span></span>   

<span data-ttu-id="6f2b1-143">[**デバイスの種類**] の一覧を使用して、モバイルデバイスやデスクトップデバイスをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-143">Use the **Device Type** list to simulate a mobile device or desktop device.</span></span>  

> ##### <span data-ttu-id="6f2b1-144">図 5</span><span class="sxs-lookup"><span data-stu-id="6f2b1-144">Figure 5</span></span>  
> <span data-ttu-id="6f2b1-145">[**デバイスの種類**] の一覧</span><span class="sxs-lookup"><span data-stu-id="6f2b1-145">The **Device Type** list</span></span>  
> ![[デバイスの種類] の一覧][ImageDeviceType]  

<span data-ttu-id="6f2b1-147">次の表では、オプションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-147">The table below describes the differences between the options.</span></span>  <span data-ttu-id="6f2b1-148">**レンダリングメソッド**は、Microsoft Edge がモバイルビューポートまたはデスクトップビューポートとしてページをレンダリングするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-148">**Rendering method** refers to whether Microsoft Edge renders the page as a mobile or desktop viewport.</span></span>  <span data-ttu-id="6f2b1-149">**カーソルアイコン**は、ページ上にマウスポインターを置いたときに表示されるカーソルの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-149">**Cursor icon** refers to what type of cursor you see when you hover over the page.</span></span>  <span data-ttu-id="6f2b1-150">**イベント**は、 `touch` `click` ページを操作するときにそのページが起動するか、イベントを発生させるかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-150">**Events fired** refers to whether the page fires `touch` or `click` events when you interact with the page.</span></span>  

| <span data-ttu-id="6f2b1-151">オプション</span><span class="sxs-lookup"><span data-stu-id="6f2b1-151">Option</span></span> | <span data-ttu-id="6f2b1-152">レンダリング方法</span><span class="sxs-lookup"><span data-stu-id="6f2b1-152">Rendering method</span></span> | <span data-ttu-id="6f2b1-153">カーソルアイコン</span><span class="sxs-lookup"><span data-stu-id="6f2b1-153">Cursor icon</span></span> | <span data-ttu-id="6f2b1-154">イベントを発生させる</span><span class="sxs-lookup"><span data-stu-id="6f2b1-154">Events fired</span></span> |  
|:--- |:--- |:--- |:--- |  
| <span data-ttu-id="6f2b1-155">モバイル</span><span class="sxs-lookup"><span data-stu-id="6f2b1-155">Mobile</span></span> | <span data-ttu-id="6f2b1-156">モバイル</span><span class="sxs-lookup"><span data-stu-id="6f2b1-156">Mobile</span></span> | <span data-ttu-id="6f2b1-157">円形</span><span class="sxs-lookup"><span data-stu-id="6f2b1-157">Circle</span></span> | <span data-ttu-id="6f2b1-158">タッチ</span><span class="sxs-lookup"><span data-stu-id="6f2b1-158">touch</span></span> |  
| <span data-ttu-id="6f2b1-159">モバイル \ (タッチなし)</span><span class="sxs-lookup"><span data-stu-id="6f2b1-159">Mobile \(no touch\)</span></span> | <span data-ttu-id="6f2b1-160">モバイル</span><span class="sxs-lookup"><span data-stu-id="6f2b1-160">Mobile</span></span> | <span data-ttu-id="6f2b1-161">通常</span><span class="sxs-lookup"><span data-stu-id="6f2b1-161">Normal</span></span> | <span data-ttu-id="6f2b1-162"> で、</span><span class="sxs-lookup"><span data-stu-id="6f2b1-162">click</span></span> |  
| <span data-ttu-id="6f2b1-163">Desktop</span><span class="sxs-lookup"><span data-stu-id="6f2b1-163">Desktop</span></span> | <span data-ttu-id="6f2b1-164">Desktop</span><span class="sxs-lookup"><span data-stu-id="6f2b1-164">Desktop</span></span> | <span data-ttu-id="6f2b1-165">通常</span><span class="sxs-lookup"><span data-stu-id="6f2b1-165">Normal</span></span> | <span data-ttu-id="6f2b1-166"> で、</span><span class="sxs-lookup"><span data-stu-id="6f2b1-166">click</span></span> |  
| <span data-ttu-id="6f2b1-167">デスクトップ \ (タッチ \)</span><span class="sxs-lookup"><span data-stu-id="6f2b1-167">Desktop \(touch\)</span></span> | <span data-ttu-id="6f2b1-168">Desktop</span><span class="sxs-lookup"><span data-stu-id="6f2b1-168">Desktop</span></span> | <span data-ttu-id="6f2b1-169">円形</span><span class="sxs-lookup"><span data-stu-id="6f2b1-169">Circle</span></span> | <span data-ttu-id="6f2b1-170">タッチ</span><span class="sxs-lookup"><span data-stu-id="6f2b1-170">touch</span></span> |  

> [!NOTE]
> <span data-ttu-id="6f2b1-171">[**デバイスの種類**] の一覧が表示されない場合は、[**その他のオプション**] をクリックし、[デバイスの種類の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-171">If you do not see the **Device Type** list, click **More options** and select **Add device type**.</span></span>  

### <span data-ttu-id="6f2b1-172">モバイルデバイスのビューポートモード</span><span class="sxs-lookup"><span data-stu-id="6f2b1-172">Mobile Device Viewport Mode</span></span>   

<span data-ttu-id="6f2b1-173">特定のモバイルデバイスのサイズをシミュレートするには、**デバイス**の一覧からデバイスを選びます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-173">To simulate the dimensions of a specific mobile device, select the device from the **Device** list.</span></span>  

> ##### <span data-ttu-id="6f2b1-174">図 6</span><span class="sxs-lookup"><span data-stu-id="6f2b1-174">Figure 6</span></span>  
> <span data-ttu-id="6f2b1-175">デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="6f2b1-175">The Device list</span></span>  
> ![デバイスの一覧][ImageDeviceList]  

#### <span data-ttu-id="6f2b1-177">ビューポートを横方向に回転する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-177">Rotate the viewport to landscape orientation</span></span>   

<span data-ttu-id="6f2b1-178">[回転回転] を**クリックし** ![ ][ImageRotateIcon] て、ビューポートを横方向に回転させます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-178">Click **Rotate** ![Rotate][ImageRotateIcon] to rotate the viewport to landscape orientation.</span></span>  

> ##### <span data-ttu-id="6f2b1-179">図 7</span><span class="sxs-lookup"><span data-stu-id="6f2b1-179">Figure 7</span></span>  
> <span data-ttu-id="6f2b1-180">横方向</span><span class="sxs-lookup"><span data-stu-id="6f2b1-180">Landscape orientation</span></span>  
> ![横方向][ImageLandscape]  

> [!NOTE]
> <span data-ttu-id="6f2b1-182">**デバイスのツールバー**が狭い場合、[**回転**] ボタンは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-182">The **Rotate** button disappears if your **Device Toolbar** is narrow.</span></span>  

> ##### <span data-ttu-id="6f2b1-183">図 8</span><span class="sxs-lookup"><span data-stu-id="6f2b1-183">Figure 8</span></span>  
> <span data-ttu-id="6f2b1-184">デバイスのツールバー</span><span class="sxs-lookup"><span data-stu-id="6f2b1-184">The Device Toolbar</span></span>  
> ![デバイスのツールバー][ImageDeviceToolbar2]  

<span data-ttu-id="6f2b1-186">「[方向を設定](#set-orientation)する」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-186">See also [Set orientation](#set-orientation).</span></span>  

#### <span data-ttu-id="6f2b1-187">デバイスフレームの表示</span><span class="sxs-lookup"><span data-stu-id="6f2b1-187">Show device frame</span></span>   

<span data-ttu-id="6f2b1-188">IPhone 6 など特定のモバイルデバイスのサイズをシミュレートする場合は、[**その他のオプション**] を開き、[**デバイスフレームの表示**] を選択して、ビューポートの周りに物理デバイスフレームを表示します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-188">When simulating the dimensions of a specific mobile device like an iPhone 6, open **More options** and then select **Show device frame** to show the physical device frame around the viewport.</span></span>  

> [!NOTE]
> <span data-ttu-id="6f2b1-189">特定のデバイスのデバイスフレームが表示されない場合は、DevTools にその特定のオプション用の art がないことが考えられます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-189">If you do not see a device frame for a particular device, it probably means that DevTools just does not have art for that specific option.</span></span>  

> ##### <span data-ttu-id="6f2b1-190">図 9</span><span class="sxs-lookup"><span data-stu-id="6f2b1-190">Figure 9</span></span>  
> <span data-ttu-id="6f2b1-191">デバイスフレームの表示</span><span class="sxs-lookup"><span data-stu-id="6f2b1-191">Show device frame</span></span>  
> ![デバイスフレームの表示][ImageShowDeviceFrame]  

> ##### <span data-ttu-id="6f2b1-193">図 10</span><span class="sxs-lookup"><span data-stu-id="6f2b1-193">Figure 10</span></span>  
> <span data-ttu-id="6f2b1-194">IPhone 6 のデバイスフレーム</span><span class="sxs-lookup"><span data-stu-id="6f2b1-194">The device frame for the iPhone 6</span></span>  
> ![IPhone 6 のデバイスフレーム][ImageIphoneFrame]  

#### <span data-ttu-id="6f2b1-196">カスタムモバイルデバイスを追加する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-196">Add a custom mobile device</span></span>   

<span data-ttu-id="6f2b1-197">カスタムデバイスを追加するには:</span><span class="sxs-lookup"><span data-stu-id="6f2b1-197">To add a custom device:</span></span>  

1.  <span data-ttu-id="6f2b1-198">**デバイス**の一覧をクリックし、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-198">Click the **Device** list and then select **Edit**.</span></span>  

> ##### <span data-ttu-id="6f2b1-199">図 11</span><span class="sxs-lookup"><span data-stu-id="6f2b1-199">Figure 11</span></span>  
> <span data-ttu-id="6f2b1-200">[**編集]** の [編集] を選ぶ 
> ![][ImageEdit]</span><span class="sxs-lookup"><span data-stu-id="6f2b1-200">Selecting **Edit**
![Selecting Edit][ImageEdit]</span></span>  

1.  <span data-ttu-id="6f2b1-201">[**カスタムデバイスの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-201">Click **Add custom device**.</span></span>  

1.  <span data-ttu-id="6f2b1-202">デバイスの名前、幅、高さを入力します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-202">Enter a name, width, and height for the device.</span></span>  <span data-ttu-id="6f2b1-203">[デバイスのピクセル比率][MDNWindowDevicePixelRatio]、[ユーザーエージェントの文字列][MDNUserAgent]、[デバイスの種類](#set-the-device-type)の各フィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-203">The [device pixel ratio][MDNWindowDevicePixelRatio], [user agent string][MDNUserAgent], and [device type](#set-the-device-type) fields are optional.</span></span>  <span data-ttu-id="6f2b1-204">[デバイスの種類] フィールドは、既定で [**モバイル**] に設定されているリストです。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-204">The device type field is the list that is set to **Mobile** by default.</span></span>  

> ##### <span data-ttu-id="6f2b1-205">図 12</span><span class="sxs-lookup"><span data-stu-id="6f2b1-205">Figure 12</span></span>  
> <span data-ttu-id="6f2b1-206">カスタムデバイスの作成</span><span class="sxs-lookup"><span data-stu-id="6f2b1-206">Creating a custom device</span></span>  
> ![カスタムデバイスの作成][ImageAddCustomDevice]  

### <span data-ttu-id="6f2b1-208">ルーラーを表示する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-208">Show rulers</span></span>   

<span data-ttu-id="6f2b1-209">[**その他のオプション**] をクリックし、[**ルーラーの表示**] を選択して、ビューポートの左上にあるルーラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-209">Click **More options** and then select **Show rulers** to see rulers above and to the left of your viewport.</span></span>  <span data-ttu-id="6f2b1-210">ルーラーのサイズ調整単位はピクセルです。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-210">The sizing unit of the rulers is pixels.</span></span>  

> ##### <span data-ttu-id="6f2b1-211">図 13</span><span class="sxs-lookup"><span data-stu-id="6f2b1-211">Figure 13</span></span>  
> <span data-ttu-id="6f2b1-212">ルーラーを表示する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-212">Show rulers</span></span>  
> ![ルーラーを表示する][ImageShowRulers]  

> ##### <span data-ttu-id="6f2b1-214">図 14</span><span class="sxs-lookup"><span data-stu-id="6f2b1-214">Figure 14</span></span>  
> <span data-ttu-id="6f2b1-215">ビューポートの左上にあるルーラー</span><span class="sxs-lookup"><span data-stu-id="6f2b1-215">Rulers above and to the left of the viewport</span></span>  
> ![ビューポートの左上にあるルーラー][ImageRulers]  

### <span data-ttu-id="6f2b1-217">ビューポートをズームする</span><span class="sxs-lookup"><span data-stu-id="6f2b1-217">Zoom the viewport</span></span>   

<span data-ttu-id="6f2b1-218">拡大または縮小するには、[**ズーム**] リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-218">Use the **Zoom** list to zoom in or out.</span></span>  

> ##### <span data-ttu-id="6f2b1-219">図 15</span><span class="sxs-lookup"><span data-stu-id="6f2b1-219">Figure 15</span></span>  
> <span data-ttu-id="6f2b1-220">ズーム</span><span class="sxs-lookup"><span data-stu-id="6f2b1-220">Zoom</span></span>  
> ![ズーム][ImageZoomViewport]  

## <span data-ttu-id="6f2b1-222">ネットワークと CPU を調整する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-222">Throttle the network and CPU</span></span>   

<span data-ttu-id="6f2b1-223">ネットワークと CPU を調整するには、[**調整**] の一覧から [**ミッドティアモバイル**] または [**ローエンド**] のモバイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-223">To throttle the network and CPU, select **Mid-tier mobile** or **Low-end mobile** from the **Throttle** list.</span></span>  

> ##### <span data-ttu-id="6f2b1-224">図 16</span><span class="sxs-lookup"><span data-stu-id="6f2b1-224">Figure 16</span></span>  
> <span data-ttu-id="6f2b1-225">スロットルリスト</span><span class="sxs-lookup"><span data-stu-id="6f2b1-225">The Throttle list</span></span>  
> ![スロットルリスト][ImageThrottling]  

<span data-ttu-id="6f2b1-227">**ミッドティアモバイル**では、高速3g をシミュレートし、CPU を調整して、通常よりも4倍遅くなるようにします。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-227">**Mid-tier mobile** simulates fast 3G and throttles your CPU so that it is 4 times slower than normal.</span></span>  <span data-ttu-id="6f2b1-228">**ローエンドの携帯電話**では、低速の3g がシミュレートされ、CPU の6倍が通常よりも遅くなります。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-228">**Low-end mobile** simulates slow 3G and throttles your CPU 6 times slower than normal.</span></span>  <span data-ttu-id="6f2b1-229">調整は、ノート pc またはデスクトップの通常の機能に関連していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-229">Keep in mind that the throttling is relative to the normal capability of your laptop or desktop.</span></span>  

> [!NOTE]
> <span data-ttu-id="6f2b1-230">**デバイスのツールバー**が狭い場合は、**スロットル**リストが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-230">The **Throttle** list will be hidden if your **Device Toolbar** is narrow.</span></span>  

> ##### <span data-ttu-id="6f2b1-231">図 17</span><span class="sxs-lookup"><span data-stu-id="6f2b1-231">Figure 17</span></span>  
> <span data-ttu-id="6f2b1-232">デバイスのツールバー</span><span class="sxs-lookup"><span data-stu-id="6f2b1-232">The Device Toolbar</span></span>  
> ![デバイスのツールバー][ImageDeviceToolbar3]  

### <span data-ttu-id="6f2b1-234">CPU のみを調整する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-234">Throttle the CPU only</span></span>   

<span data-ttu-id="6f2b1-235">ネットワークではなく CPU のみを調整するには、[**パフォーマンス**] パネルに移動し、[**キャプチャ設定**キャプチャの設定] をクリックして、[ ![ ][ImageCaptureIcon] **CPU** ] 一覧から [ **4 倍速**] または [ **6x の速度**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-235">To throttle the CPU only and not the network, go to the **Performance** panel, click **Capture Settings** ![Capture Settings][ImageCaptureIcon], and then select **4x slowdown** or **6x slowdown** from the **CPU** list.</span></span>  

> ##### <span data-ttu-id="6f2b1-236">図18</span><span class="sxs-lookup"><span data-stu-id="6f2b1-236">Figure 18</span></span>  
> <span data-ttu-id="6f2b1-237">CPU リスト</span><span class="sxs-lookup"><span data-stu-id="6f2b1-237">The CPU list</span></span>  
> ![CPU リスト][ImageCPU]  

### <span data-ttu-id="6f2b1-239">ネットワークのみを調整する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-239">Throttle the network only</span></span>   

<span data-ttu-id="6f2b1-240">ネットワークのみを対象とし、CPU は調整しない場合は、**ネットワーク**パネルを開いて、[**スロットル**] の一覧から [ **Fast 3G** ] または [**低速の 3g** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-240">To throttle the network only and not the CPU, go the **Network** panel and select **Fast 3G** or **Slow 3G** from the **Throttle** list.</span></span>  

> ##### <span data-ttu-id="6f2b1-241">図19</span><span class="sxs-lookup"><span data-stu-id="6f2b1-241">Figure 19</span></span>  
> <span data-ttu-id="6f2b1-242">スロットルリスト</span><span class="sxs-lookup"><span data-stu-id="6f2b1-242">The Throttle list</span></span>  
> ![スロットルリスト][ImageNetwork]  

<span data-ttu-id="6f2b1-244">または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押すと、コマンドメニューが開き、「 `3G` **高速な3g 調整を有効**にする」または「低速な**3g 調整**を有効にする」を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-244">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `3G`, and select **Enable fast 3G throttling** or **Enable slow 3G throttling**.</span></span>  

> ##### <span data-ttu-id="6f2b1-245">図20</span><span class="sxs-lookup"><span data-stu-id="6f2b1-245">Figure 20</span></span>  
> <span data-ttu-id="6f2b1-246">コマンドメニュー</span><span class="sxs-lookup"><span data-stu-id="6f2b1-246">The Command Menu</span></span>  
> ![コマンドメニュー][ImageCommandMenu]  

<span data-ttu-id="6f2b1-248">[**パフォーマンス**] パネルからネットワークの調整を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-248">You can also set network throttling from the **Performance** panel.</span></span>  <span data-ttu-id="6f2b1-249">「**キャプチャ設定** ![ キャプチャ設定」をクリックし ][ImageCaptureIcon] て、「 **Fast 3G** 」または「**低速な 3g** 」を**ネットワーク**リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-249">Click **Capture Settings** ![Capture Settings][ImageCaptureIcon] and then select **Fast 3G** or **Slow 3G** from the **Network** list.</span></span>  

> ##### <span data-ttu-id="6f2b1-250">図21</span><span class="sxs-lookup"><span data-stu-id="6f2b1-250">Figure 21</span></span>  
> <span data-ttu-id="6f2b1-251">パフォーマンスパネルからネットワーク調整を設定する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-251">Setting network throttling from the Performance panel</span></span>  
> ![パフォーマンスパネルからネットワーク調整を設定する][ImageNetwork2]  

## <span data-ttu-id="6f2b1-253">位置情報を無効にする</span><span class="sxs-lookup"><span data-stu-id="6f2b1-253">Override geolocation</span></span>   

<span data-ttu-id="6f2b1-254">位置情報を上書きする UI を開くには、[ **devtools のカスタマイズと制御**] をクリックし、[ `...` **その他のツール**センサー] を選択し  >  **Sensors**ます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-254">To open the geolocation overriding UI click **Customize and control DevTools** `...` and then select **More tools** > **Sensors**.</span></span>  

> ##### <span data-ttu-id="6f2b1-255">図22</span><span class="sxs-lookup"><span data-stu-id="6f2b1-255">Figure 22</span></span>  
> <span data-ttu-id="6f2b1-256">センサー</span><span class="sxs-lookup"><span data-stu-id="6f2b1-256">Sensors</span></span>  
> ![センサー][ImageSensors]  

<span data-ttu-id="6f2b1-258">または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押してコマンドメニューを開き、「 `Sensors` 」と入力して、[**センサーの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-258">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `Sensors`, and then select **Show Sensors**.</span></span>  

> ##### <span data-ttu-id="6f2b1-259">図23</span><span class="sxs-lookup"><span data-stu-id="6f2b1-259">Figure 23</span></span>  
> <span data-ttu-id="6f2b1-260">センサーの表示</span><span class="sxs-lookup"><span data-stu-id="6f2b1-260">Show Sensors</span></span>  
> ![センサーの表示][ImageShowSensors]  

<span data-ttu-id="6f2b1-262">[**位置情報] の一覧から**いずれかのプリセットを選ぶか、[**場所**の指定] を選んで独自の座標を入力するか、[場所を選択**できません**] を選択して、位置情報がエラー状態にあるときのページの動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-262">Select one of the presets from the **Geolocation** list, or select **Custom location** to enter your own coordinates, or select **Location unavailable** to test out how your page behaves when geolocation is in an error state.</span></span>  

> ##### <span data-ttu-id="6f2b1-263">図24</span><span class="sxs-lookup"><span data-stu-id="6f2b1-263">Figure 24</span></span>  
> <span data-ttu-id="6f2b1-264">位置情報</span><span class="sxs-lookup"><span data-stu-id="6f2b1-264">Geolocation</span></span>  
> ![位置情報][ImageGeolocation]  

## <span data-ttu-id="6f2b1-266">向きを設定する</span><span class="sxs-lookup"><span data-stu-id="6f2b1-266">Set orientation</span></span>   

<span data-ttu-id="6f2b1-267">向きの UI を開くには、[カスタマイズ] をクリックし、[ **devtools** ] をクリックして、[ `...` **その他のツール**センサー] を選択し  >  **Sensors**ます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-267">To open the orientation UI click **Customize and control DevTools** `...` and then select **More tools** > **Sensors**.</span></span>  

> ##### <span data-ttu-id="6f2b1-268">図25</span><span class="sxs-lookup"><span data-stu-id="6f2b1-268">Figure 25</span></span>  
> <span data-ttu-id="6f2b1-269">センサー</span><span class="sxs-lookup"><span data-stu-id="6f2b1-269">Sensors</span></span>  
> ![センサー][ImageSensors2]  

<span data-ttu-id="6f2b1-271">または、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押してコマンドメニューを開き、「 `Sensors` 」と入力して、[**センサーの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-271">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `Sensors`, and then select **Show Sensors**.</span></span>  

> ##### <span data-ttu-id="6f2b1-272">図26</span><span class="sxs-lookup"><span data-stu-id="6f2b1-272">Figure 26</span></span>  
> <span data-ttu-id="6f2b1-273">センサーの表示</span><span class="sxs-lookup"><span data-stu-id="6f2b1-273">Show Sensors</span></span>  
> ![センサーの表示][ImageShowSensors2]  

<span data-ttu-id="6f2b1-275">[**印刷の向き**] の一覧からいずれかのプリセットを選択するか、[**ユーザー設定の向き**] を選択して、独自のアルファ、ベータ、およびガンマ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-275">Select one of the presets from the **Orientation** list or select **Custom orientation** to set your own alpha, beta, and gamma values.</span></span>  

> ##### <span data-ttu-id="6f2b1-276">図27</span><span class="sxs-lookup"><span data-stu-id="6f2b1-276">Figure 27</span></span>  
> <span data-ttu-id="6f2b1-277">Orientation</span><span class="sxs-lookup"><span data-stu-id="6f2b1-277">Orientation</span></span>  
> ![Orientation][ImageOrientation]  

 



<!--See [Join the DevTools community][DevToolsCommunity] for other ways to leave feedback.  -->  

<!-- image links -->  

[ImageCaptureIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageCustomizeIcon]: /microsoft-edge/devtools-guide-chromium/media/customize-and-control-devtools-icon.msft.png  
[ImageDeviceToolbarIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: /microsoft-edge/devtools-guide-chromium/media/rotate-dark-icon.msft.png  

[ImageDeviceToolbar]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "図 1: デバイスのツールバー"  
[ImageResponsiveHandles]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png "図 2: 応答可能なビューポートモードのときにビューポートの寸法を変更するためのハンドル"  
[ImageShowMediaQueries]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png "図 3: メディアクエリを表示する"  
[ImageBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png "図 4: ブレークポイントをクリックしてビューポートの幅を変更する"  
[ImageDeviceType]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-type-list.msft.png "図 5: [デバイスの種類] の一覧"  
[ImageDeviceList]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-list.msft.png "図 6: デバイスの一覧"  
[ImageLandscape]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-landscape.msft.png "図 7: 横方向"  
[ImageDeviceToolbar2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "図 8: デバイスのツールバー"  
[ImageShowDeviceFrame]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png "図 9: デバイスフレームの表示"  
[ImageIphoneFrame]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png "図 10: iPhone 6 のデバイスフレーム"  
[ImageEdit]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-list-edit.msft.png "図 11: [編集] を選ぶ"  
[ImageAddCustomDevice]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png "図 12: カスタムデバイスの作成"  
[ImageShowRulers]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png "図 13: ルーラーを表示する"  
[ImageRulers]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-rulers.msft.png "図 14: ビューポートの左上にあるルーラー"  
[ImageZoomViewport]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-zoom.msft.png "図 15: ズーム"  
[ImageThrottling]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-throttle.msft.png "図 16: スロットルリスト"  
[ImageDeviceToolbar3]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "図 17: デバイスのツールバー"  
[ImageCPU]: /microsoft-edge/devtools-guide-chromium/media/device-mode-performance-cpu-throttle.msft.png "図 18: CPU の一覧"  
[ImageNetwork]: /microsoft-edge/devtools-guide-chromium/media/device-mode-network-throttle.msft.png "図 19: スロットルの一覧"  
[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/device-mode-command-menu-throttle.msft.png "図 20: コマンドメニュー"  
[ImageNetwork2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-performance-network-throttle.msft.png "図 21: パフォーマンスパネルからネットワーク調整を設定する"  
[ImageSensors]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png "図 22: センサー"  
[ImageShowSensors]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png "図 23: センサーを表示する"  
[ImageGeolocation]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png "図 24: 位置情報"  
[ImageSensors2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png "図 25: センサー"  
[ImageShowSensors2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png "図 26: センサーを表示する"  
[ImageOrientation]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png "図 27: 向き"  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community"  -->
[Devて Remoteデバッギング]:/microsoft-edge/devtools-guide-chromium/remote-debugging/index "Android デバイスのリモートデバッグの開始"
[DevToolsRemoteDebugging]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Get Started with Remote Debugging Android Devices"  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window. Deviceピクセルの比率 |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "ユーザーエージェント |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "最初の順序での Wikipedia の順序"  

> [!NOTE]
> <span data-ttu-id="6f2b1-310">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-310">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6f2b1-311">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-311">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6f2b1-313">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6f2b1-313">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
