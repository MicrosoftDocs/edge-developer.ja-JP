---
description: Microsoft Edge DevTools の最も一般的なネットワーク関連機能のチュートリアルです。
title: Microsoft Edge DevTools でネットワークアクティビティを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a55ff05e29817c483cbf13b8713ef37cf96424d5
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125427"
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

# <span data-ttu-id="9cc58-104">Microsoft Edge DevTools でネットワークアクティビティを検査する</span><span class="sxs-lookup"><span data-stu-id="9cc58-104">Inspect network activity in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="9cc58-105">これは、ページのネットワークアクティビティの検査に関連する、よく使われる DevTools 機能のいくつかの実践的なチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="9cc58-105">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span></span>  

<span data-ttu-id="9cc58-106">代わりに機能を参照する場合は、 [ネットワークの参照][DevtoolsNetworkReference] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc58-106">See [Network Reference][DevtoolsNetworkReference] if you want to browse features instead.</span></span>  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <span data-ttu-id="9cc58-107">[ネットワーク] パネルを使用する場合</span><span class="sxs-lookup"><span data-stu-id="9cc58-107">When to use the Network panel</span></span>  

<span data-ttu-id="9cc58-108">通常、[ネットワーク] パネルは、リソースが予期したとおりにダウンロードまたはアップロードされるようにする必要がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-108">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span></span>  <span data-ttu-id="9cc58-109">[ネットワーク] パネルの最も一般的なユースケースは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9cc58-109">The most common use cases for the Network panel are:</span></span>  

*   <span data-ttu-id="9cc58-110">リソースが実際にはまったくアップロードまたはダウンロードされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-110">Making sure that resources are actually being uploaded or downloaded at all.</span></span>  
*   <span data-ttu-id="9cc58-111">HTTP ヘッダー、コンテンツ、サイズなど、個々のリソースのプロパティを検査します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-111">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span></span>  
    
<span data-ttu-id="9cc58-112">ページの読み込みのパフォーマンスを向上させる方法を探している場合は、[ネットワーク] パネルから開始しないで **ください** 。</span><span class="sxs-lookup"><span data-stu-id="9cc58-112">If you are looking for ways to improve page load performance, **do not** start with the Network panel.</span></span>  <span data-ttu-id="9cc58-113">ネットワークアクティビティに関連していない読み込みパフォーマンスの問題には、さまざまな種類があります。</span><span class="sxs-lookup"><span data-stu-id="9cc58-113">There are many types of load performance issues that are not related to network activity.</span></span>  <span data-ttu-id="9cc58-114">ページを改善する方法についての候補が表示されるため、監査パネルから開始します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-114">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span></span>  <span data-ttu-id="9cc58-115">「 [Web サイトの速度を最適化][DevtoolsSpeedGetStarted]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc58-115">See [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

## <span data-ttu-id="9cc58-116">[ネットワーク] パネルを開く</span><span class="sxs-lookup"><span data-stu-id="9cc58-116">Open the Network panel</span></span>  

<span data-ttu-id="9cc58-117">このチュートリアルを最大限に活用するには、デモを開き、デモページの機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="9cc58-117">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span></span>  

1.  <span data-ttu-id="9cc58-118">[はじめに] の [デモ][GlitchNetworkGetStarted]を開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-118">Open the [Get Started Demo][GlitchNetworkGetStarted].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="デモ" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       <span data-ttu-id="9cc58-120">デモ</span><span class="sxs-lookup"><span data-stu-id="9cc58-120">The demo</span></span>  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="デモ" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="9cc58-121">[Open DevTools][DevToolsOpen] `Control` + `Shift` + `J` \ (Windows、Linux \) または `Command` + `Option` + `J` \ (macOS \) を押して、devtools を開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-121">[Open DevTools][DevToolsOpen] by pressing `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="9cc58-122">**コンソール**パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-122">The **Console** panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="デモ" lightbox="../media/network-glitch-console.msft.png":::
       <span data-ttu-id="9cc58-124">**本体**</span><span class="sxs-lookup"><span data-stu-id="9cc58-124">The **Console**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9cc58-125">[ウィンドウの下部に DevTools をドッキング][DevToolsCustomizePlacement]することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9cc58-125">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="デモ" lightbox="../media/network-glitch-console-bottom.msft.png":::
       <span data-ttu-id="9cc58-127">ウィンドウの下部にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="9cc58-127">DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-128">[ **ネットワーク** ] タブを選択します。 [ **ネットワーク** ] パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-128">Select the **Network** tab.  The **Network** panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-bottom.msft.png":::
       <span data-ttu-id="9cc58-130">ウィンドウの下部にドッキングされた DevTools の**コンソール**ツール</span><span class="sxs-lookup"><span data-stu-id="9cc58-130">**Console** tool in the DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9cc58-131">[ネットワーク] パネルが空になりました。</span><span class="sxs-lookup"><span data-stu-id="9cc58-131">Right now the Network panel is empty.</span></span>  <span data-ttu-id="9cc58-132">DevTools は、開いた後にのみネットワークアクティビティを記録し、DevTools を開いた後のネットワークアクティビティは発生しませんでした。</span><span class="sxs-lookup"><span data-stu-id="9cc58-132">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span></span>  

## <span data-ttu-id="9cc58-133">ネットワークアクティビティをログに記録する</span><span class="sxs-lookup"><span data-stu-id="9cc58-133">Log network activity</span></span>  

<span data-ttu-id="9cc58-134">ページによって発生するネットワークアクティビティを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9cc58-134">To view the network activity that a page causes:</span></span>  

1.  <span data-ttu-id="9cc58-135">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="9cc58-135">Reload the page.</span></span>  <span data-ttu-id="9cc58-136">ネットワークパネルでは、ネットワーク **ログ**にすべてのネットワークアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-136">The Network panel logs all network activity in the **Network Log**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network.msft.png":::
       <span data-ttu-id="9cc58-138">**ネットワークログ**</span><span class="sxs-lookup"><span data-stu-id="9cc58-138">The **Network Log**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9cc58-139">**ネットワークログ**の各行は、リソースを表します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-139">Each row of the **Network Log** represents a resource.</span></span>  <span data-ttu-id="9cc58-140">既定では、リソースは時系列順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-140">By default the resources are listed chronologically.</span></span>  <span data-ttu-id="9cc58-141">トップリソースは、通常、メインの HTML 文書です。</span><span class="sxs-lookup"><span data-stu-id="9cc58-141">The top resource is usually the main HTML document.</span></span>  <span data-ttu-id="9cc58-142">一番下のリソースは、要求されたすべてのものです。</span><span class="sxs-lookup"><span data-stu-id="9cc58-142">The bottom resource is whatever was requested last.</span></span>  
    
    <span data-ttu-id="9cc58-143">各列は、リソースに関する情報を表します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-143">Each column represents information about a resource.</span></span>  <span data-ttu-id="9cc58-144">前の図では、既定の列が表示されています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-144">In the previous figure the default columns are displayed.</span></span>  

    *   <span data-ttu-id="9cc58-145">**状態**。</span><span class="sxs-lookup"><span data-stu-id="9cc58-145">**Status**.</span></span>  <span data-ttu-id="9cc58-146">応答の HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="9cc58-146">The HTTP status code for response.</span></span>  
    *   <span data-ttu-id="9cc58-147">**[種類]**。</span><span class="sxs-lookup"><span data-stu-id="9cc58-147">**Type**.</span></span>  <span data-ttu-id="9cc58-148">リソースの種類。</span><span class="sxs-lookup"><span data-stu-id="9cc58-148">The resource type.</span></span>  
    *   <span data-ttu-id="9cc58-149">**イニシエーター**。</span><span class="sxs-lookup"><span data-stu-id="9cc58-149">**Initiator**.</span></span>  <span data-ttu-id="9cc58-150">リソース要求の原因。</span><span class="sxs-lookup"><span data-stu-id="9cc58-150">The cause of the resource request.</span></span>  <span data-ttu-id="9cc58-151">[イニシエーター] 列のリンクを選ぶと、要求を発生させたソースコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-151">Selecting a link in the Initiator column takes you to the source code that caused the request.</span></span>  
    *   <span data-ttu-id="9cc58-152">**時刻**。</span><span class="sxs-lookup"><span data-stu-id="9cc58-152">**Time**.</span></span>  <span data-ttu-id="9cc58-153">要求の期間。</span><span class="sxs-lookup"><span data-stu-id="9cc58-153">The duration of the request.</span></span>  
    *   <span data-ttu-id="9cc58-154">**ウォーターフォール**</span><span class="sxs-lookup"><span data-stu-id="9cc58-154">**Waterfall**.</span></span>  <span data-ttu-id="9cc58-155">要求の異なるステージのグラフィカル表現。</span><span class="sxs-lookup"><span data-stu-id="9cc58-155">A graphical representation of the different stages of the request.</span></span>  <span data-ttu-id="9cc58-156">ウォーターフォールの上にマウスポインターを置くと、ブレークダウンが表示できます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-156">Hover over a Waterfall to see a breakdown.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9cc58-157">ネットワークログの上のグラフは概要と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-157">The graph above the Network Log is called the Overview.</span></span>  <span data-ttu-id="9cc58-158">このチュートリアルの概要グラフは使用しないため、非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-158">You will not use the Overview graph in this tutorial, so you may hide it.</span></span>  <span data-ttu-id="9cc58-159">「 [概要ウィンドウを非表示にする」を][DevtoolsReferenceHideOverview]参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc58-159">See [Hide the Overview pane][DevtoolsReferenceHideOverview].</span></span>
    
1.  <span data-ttu-id="9cc58-160">DevTools を開くと、ネットワークログにネットワークアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-160">After you open DevTools, it records network activity in the Network Log.</span></span>  
    <span data-ttu-id="9cc58-161">これを示すには、まず **ネットワークログ** の下部を確認し、最後のアクティビティを記録します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-161">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span></span>  
1.  <span data-ttu-id="9cc58-162">次に、デモの [ **データの取得** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-162">Now, select the **Get Data** button in the demo.</span></span>  
1.  <span data-ttu-id="9cc58-163">もう一度 **ネットワークログ** の下部を確認します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-163">Look at the bottom of the **Network Log** again.</span></span>  <span data-ttu-id="9cc58-164">という新しいリソースが表示され `getstarted.json` ます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-164">You should see a new resource called `getstarted.json`.</span></span>  <span data-ttu-id="9cc58-165">[ **データの取得** ] ボタンを選択すると、ページによってこのファイルが要求されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-165">Selecting the **Get Data** button caused the page to request this file.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       <span data-ttu-id="9cc58-167">**ネットワークログ**の新しいリソース</span><span class="sxs-lookup"><span data-stu-id="9cc58-167">A new resource in the **Network Log**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9cc58-168">詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="9cc58-168">Show more information</span></span>  

<span data-ttu-id="9cc58-169">ネットワークログの列は構成可能です。</span><span class="sxs-lookup"><span data-stu-id="9cc58-169">The columns of the Network Log are configurable.</span></span>  <span data-ttu-id="9cc58-170">使用していない列を非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-170">You may hide columns that you are not using.</span></span>  
<span data-ttu-id="9cc58-171">既定で非表示になっている列も数多く用意されています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-171">There are also many columns that are hidden by default which you may find useful.</span></span>  

1.  <span data-ttu-id="9cc58-172">ネットワークログテーブルのヘッダーを右クリックして、[ **ドメイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-172">Right-click the header of the Network Log table and choose **Domain**.</span></span>  <span data-ttu-id="9cc58-173">各リソースのドメインが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9cc58-173">The domain of each resource is now shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       <span data-ttu-id="9cc58-175">[Domain] 列を有効にする</span><span class="sxs-lookup"><span data-stu-id="9cc58-175">Enable the Domain column</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="9cc58-176">[ **名前** 列のセルの上にマウスポインターを置くと、リソースの完全な URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-176">See the full URL of a resource by hovering over the cell in the **Name** column.</span></span>  
    
## <span data-ttu-id="9cc58-177">低速ネットワーク接続のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="9cc58-177">Simulate a slower network connection</span></span>  

<span data-ttu-id="9cc58-178">サイトの構築に使用するコンピューターのネットワーク接続は、おそらく、ユーザーのモバイルデバイスのネットワーク接続よりも高速です。</span><span class="sxs-lookup"><span data-stu-id="9cc58-178">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span></span>  <span data-ttu-id="9cc58-179">ページを調整することによって、モバイルデバイスでページが読み込まれるまでの時間を把握することができます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-179">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span></span>  

1.  <span data-ttu-id="9cc58-180">[ **調整** ] ドロップダウンを選択します。これは、既定で [ **オンライン** ] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-180">Select the **Throttling** dropdown, which is set to **Online** by default.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-throttling.msft.png":::
       <span data-ttu-id="9cc58-182">調整を有効にする</span><span class="sxs-lookup"><span data-stu-id="9cc58-182">Enable throttling</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-183">[ **低速 3g**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-183">Choose **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       <span data-ttu-id="9cc58-185">低速3G を選択</span><span class="sxs-lookup"><span data-stu-id="9cc58-185">Select Slow 3G</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-186">長 **押しし** て ( ![ リロード ][ImageRefreshIcon] \)、[ **キャッシュを空**にする] を選択し、[ハードリロード] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-186">Long-press **Reload** \(![Reload][ImageRefreshIcon]\) and then choose **Empty Cache And Hard Reload**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="デモ" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **<span data-ttu-id="9cc58-188">空のキャッシュとハードリロード</span><span class="sxs-lookup"><span data-stu-id="9cc58-188">Empty Cache And Hard Reload</span></span>**  
    :::image-end:::  
    
    <span data-ttu-id="9cc58-189">繰り返しアクセスした場合、ブラウザーは通常 [キャッシュ][MDNHTTPCache]の一部のファイルを提供します。これにより、ページの読み込みが高速化されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-189">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache], which speeds up the page load.</span></span>  <span data-ttu-id="9cc58-190">**空のキャッシュとハードリロード** は、ブラウザーがすべてのリソースについてネットワークにアクセスすることを強制します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-190">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span></span>  <span data-ttu-id="9cc58-191">これは、初めてのユーザーがページの読み込みを体験する方法を確認する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9cc58-191">This is helpful when you want to see how a first-time visitor experiences a page load.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9cc58-192">**空のキャッシュと "Hard Reload** " ワークフローは、devtools が開いている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-192">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span></span>  
    
## <span data-ttu-id="9cc58-193">スクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="9cc58-193">Capture screenshots</span></span>  

<span data-ttu-id="9cc58-194">スクリーンショットを使用すると、ページの読み込み中にページがどのように表示されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-194">Screenshots let you see how a page looked over time while it was loading.</span></span>  

1.  <span data-ttu-id="9cc58-195">\ ( ![ ネットワーク設定) を選択 ][ImageSettingsIcon] し、[ **スクリーンショットのキャプチャ** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9cc58-195">Select \(![Network settings][ImageSettingsIcon]\) and select the **Capture screenshots** checkbox.</span></span>
1.  <span data-ttu-id="9cc58-196">**空のキャッシュとハードリロード**ワークフローを使用して、もう一度ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="9cc58-196">Reload the page again via the **Empty Cache And Hard Reload** workflow.</span></span>  <span data-ttu-id="9cc58-197">この方法について事前に確認が必要な場合は [、「低速接続をシミュレート](#simulate-a-slower-network-connection) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc58-197">See [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span></span>  
    <span data-ttu-id="9cc58-198">スクリーンショットウィンドウには、読み込み処理中のさまざまなポイントでページがどのように表示されるかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-198">The Screenshots pane provides thumbnails of how the page looked at various points during the loading process.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       <span data-ttu-id="9cc58-200">ページの読み込みのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="9cc58-200">Screenshots of the page load</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-201">最初のサムネイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-201">Select the first thumbnail.</span></span>  <span data-ttu-id="9cc58-202">DevTools は、現時点で発生していたネットワークアクティビティを示しています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-202">DevTools shows you what network activity was occurring at that moment in time.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       <span data-ttu-id="9cc58-204">最初のスクリーンショットで発生したネットワークアクティビティ</span><span class="sxs-lookup"><span data-stu-id="9cc58-204">The network activity that was happening during the first screenshot</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-205">もう一度 [\ (ネットワーク設定)] を選び、[ ![ ][ImageSettingsIcon] **スクリーンショットのキャプチャ** ] チェックボックスをオフにして、スクリーンショットウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-205">Select \(![Network settings][ImageSettingsIcon]\) again and deselect the **Capture screenshots** checkbox to close the Screenshots pane.</span></span>
1.  <span data-ttu-id="9cc58-206">ページをもう一度読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-206">Reload the page again.</span></span>  
    
## <span data-ttu-id="9cc58-207">リソースの詳細を調べる</span><span class="sxs-lookup"><span data-stu-id="9cc58-207">Inspect the details of the resource</span></span>  

<span data-ttu-id="9cc58-208">詳細については、リソースを選択してください。</span><span class="sxs-lookup"><span data-stu-id="9cc58-208">Select a resource to learn more information about it.</span></span>  <span data-ttu-id="9cc58-209">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="9cc58-209">Try it now:</span></span>  

1.  <span data-ttu-id="9cc58-210">を選択し `getstarted.html` ます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-210">Select `getstarted.html`.</span></span>  <span data-ttu-id="9cc58-211">[ **ヘッダー** ] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-211">The **Headers** tab is shown.</span></span>  <span data-ttu-id="9cc58-212">このタブを使用して、HTTP ヘッダーを検査します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-212">Use this tab to inspect HTTP headers.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       <span data-ttu-id="9cc58-214">[ **ヘッダー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="9cc58-214">The **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-215">[ **プレビュー** ] タブを選択します。 HTML の基本的なレンダリングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-215">Select the **Preview** tab.  A basic rendering of the HTML is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       <span data-ttu-id="9cc58-217">[ **プレビュー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="9cc58-217">The **Preview** tab</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9cc58-218">このタブは、API が HTML でエラーコードを返す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9cc58-218">This tab is helpful when an API returns an error code in HTML.</span></span>  <span data-ttu-id="9cc58-219">HTML ソースコードよりもレンダリングされた HTML を読みやすくしたり、画像を検査したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-219">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span></span>  

1.  <span data-ttu-id="9cc58-220">[ **応答** ] タブを選択します。 HTML ソースコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-220">Select the **Response** tab.  The HTML source code is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       <span data-ttu-id="9cc58-222">[ **応答** ] タブ</span><span class="sxs-lookup"><span data-stu-id="9cc58-222">The **Response** tab</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="9cc58-223">ファイルが縮小されたときに、 **Format** [ ![ ][ImageFormatIcon] **返信**] タブの下部にある [書式 \ (書式 \)] ボタンを選択すると、ファイルの内容が読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="9cc58-223">When a file is minified, selecting the **Format** \(![Format][ImageFormatIcon]\) button at the bottom of the **Response** tab re-formats the contents of the file for readability.</span></span>  
    
1.  <span data-ttu-id="9cc58-224">[ **タイミング** ] タブを選択します。 このリソースのネットワークアクティビティの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-224">Select the **Timing** tab.  A breakdown of the network activity for this resource is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       <span data-ttu-id="9cc58-226">[ **タイミング** ] タブ</span><span class="sxs-lookup"><span data-stu-id="9cc58-226">The **Timing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-227">[ **閉じる** ] を選択し ![ ][ImageCloseIcon] て、もう一度ネットワークログを表示します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-227">Choose **Close** \(![Close][ImageCloseIcon]\) to view the Network Log again.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       <span data-ttu-id="9cc58-229">[ **閉じる** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="9cc58-229">The **Close** button</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9cc58-230">ネットワークのヘッダーと返信を検索する</span><span class="sxs-lookup"><span data-stu-id="9cc58-230">Search network headers and responses</span></span>  

<span data-ttu-id="9cc58-231">特定の文字列または正規表現について、すべてのリソースの HTTP ヘッダーと応答を検索する必要がある場合は、[ **検索** ] ウィンドウを使用します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-231">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span></span>  

<span data-ttu-id="9cc58-232">たとえば、リソースが適切な **キャッシュポリシー**を使っていることを確認する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="9cc58-232">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span></span>  

<!--TODO: add cache policies section when available  -->

1.  <span data-ttu-id="9cc58-233">[ **検索** ] ( ![ 検索 ][ImageSearchIcon] \) を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-233">Choose **Search** \(![Search][ImageSearchIcon]\).</span></span>  <span data-ttu-id="9cc58-234">[検索] ウィンドウがネットワークログの左側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-234">The Search pane opens to the left of the Network log.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       <span data-ttu-id="9cc58-236">[ **検索** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9cc58-236">The **Search** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-237">入力 `Cache-Control` して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-237">Type `Cache-Control` and select `Enter`.</span></span>  <span data-ttu-id="9cc58-238">[検索] ウィンドウには、 `Cache-Control` リソースヘッダーまたはコンテンツ内で見つかったすべてのインスタンスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-238">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       <span data-ttu-id="9cc58-240">検索結果</span><span class="sxs-lookup"><span data-stu-id="9cc58-240">Search results for</span></span> `Cache-Control`  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-241">結果を選択すると、結果が見つかったリソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-241">Select a result to view the resource in which the result was found.</span></span>  <span data-ttu-id="9cc58-242">リソースの詳細が表示されている場合は、結果を選択して直接移動します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-242">If you are looking at the details of the resource, select a result to go directly to it.</span></span>  <span data-ttu-id="9cc58-243">たとえば、ヘッダーで検索されたクエリの場合、[ヘッダー] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-243">For example, if the query was found in a header, the Headers tab opens.</span></span>   <span data-ttu-id="9cc58-244">コンテンツ内にクエリが見つかった場合は、[ **応答** ] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-244">If the query was found in content, the **Response** tab opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       <span data-ttu-id="9cc58-246">[ **ヘッダー** ] タブで強調表示された検索結果</span><span class="sxs-lookup"><span data-stu-id="9cc58-246">A search result highlighted in the **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-247">[検索] ウィンドウと [ヘッダー] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-247">Close the Search pane and the Headers tab.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-search-close.msft.png":::
       <span data-ttu-id="9cc58-249">[ **閉じる** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="9cc58-249">The **Close** buttons</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9cc58-250">リソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="9cc58-250">Filter resources</span></span>  

<span data-ttu-id="9cc58-251">DevTools には、タスクに関連していないリソースをフィルター処理するための多数のワークフローが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-251">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span></span>  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   <span data-ttu-id="9cc58-253">[ **フィルター** ] ツールバー</span><span class="sxs-lookup"><span data-stu-id="9cc58-253">The **Filters** toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="9cc58-254">[ **フィルター** ] ツールバーは、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-254">The **Filters** toolbar should be enabled by default.</span></span>  <span data-ttu-id="9cc58-255">そうでなければ：</span><span class="sxs-lookup"><span data-stu-id="9cc58-255">If not:</span></span>  

1.  <span data-ttu-id="9cc58-256">[ **フィルター** \ ![ ] (フィルター \) を選んで ][ImageFilterIcon] 表示します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-256">Choose **Filter** \(![Filter][ImageFilterIcon]\) to show it.</span></span>  
    
### <span data-ttu-id="9cc58-257">文字列、正規表現、またはプロパティによるフィルター処理</span><span class="sxs-lookup"><span data-stu-id="9cc58-257">Filter by string, regular expression, or property</span></span>  

<span data-ttu-id="9cc58-258">**フィルター**テキストボックスでは、さまざまな種類のフィルターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-258">The **Filter** text box supports many different types of filtering.</span></span>  

1.  <span data-ttu-id="9cc58-259">`png`[**フィルター** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-259">Type `png` into the **Filter** text box.</span></span>  <span data-ttu-id="9cc58-260">テキストが含まれているファイルのみ `png` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-260">Only the files that contain the text `png` are shown.</span></span>  <span data-ttu-id="9cc58-261">この場合、フィルターに一致するファイルは PNG 画像のみです。</span><span class="sxs-lookup"><span data-stu-id="9cc58-261">In this case the only files that match the filter are the PNG images.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       <span data-ttu-id="9cc58-263">文字列フィルター</span><span class="sxs-lookup"><span data-stu-id="9cc58-263">A string filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-264">「`/.*\.[cj]s+$/`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-264">Type `/.*\.[cj]s+$/`.</span></span>  <span data-ttu-id="9cc58-265">DevTools では、末尾が a または a の後に1つ以上の文字が続いているファイル名でリソースをフィルター処理 `j` `c` `s` します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-265">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       <span data-ttu-id="9cc58-267">正規表現フィルター</span><span class="sxs-lookup"><span data-stu-id="9cc58-267">A regular expression filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-268">「`-main.css`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-268">Type `-main.css`.</span></span>  <span data-ttu-id="9cc58-269">DevTools でフィルター処理 `main.css` します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-269">DevTools filters out `main.css`.</span></span>  <span data-ttu-id="9cc58-270">他のファイルがそのパターンに一致した場合は、それらもフィルターで除外されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-270">If any other file matched the pattern they would also be filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       <span data-ttu-id="9cc58-272">ネガティブフィルター</span><span class="sxs-lookup"><span data-stu-id="9cc58-272">A negative filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-273">`domain:cdn.glitch.com`[**フィルター** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-273">Type `domain:cdn.glitch.com` into the **Filter** text box.</span></span>  <span data-ttu-id="9cc58-274">DevTools は、このドメインと一致しない URL のリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-274">DevTools filters out any resource with a URL that does not match this domain.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       <span data-ttu-id="9cc58-276">プロパティフィルター</span><span class="sxs-lookup"><span data-stu-id="9cc58-276">A property filter</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9cc58-277">フィルター処理可能なプロパティの完全なリストについては、「 [プロパティ別に要求をフィルター処理][DevtoolsReferenceProperty] する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9cc58-277">See [Filter requests by properties][DevtoolsReferenceProperty] for the full list of filterable properties.</span></span>  
    
1.  <span data-ttu-id="9cc58-278">任意のテキストの **フィルター** テキストボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="9cc58-278">Clear the **Filter** text box of any text.</span></span>  
    
### <span data-ttu-id="9cc58-279">リソースの種類でフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="9cc58-279">Filter by resource type</span></span>  

<span data-ttu-id="9cc58-280">スタイルシートなど、特定の種類のファイルにフォーカスを移動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9cc58-280">To focus in on a certain type of file, such as stylesheets:</span></span>  

1.  <span data-ttu-id="9cc58-281">[ **CSS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-281">Choose **CSS**.</span></span>  <span data-ttu-id="9cc58-282">その他のすべての種類のファイルはフィルターで除外されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-282">All other file types are filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       <span data-ttu-id="9cc58-284">CSS ファイルのみを表示する</span><span class="sxs-lookup"><span data-stu-id="9cc58-284">Show CSS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-285">スクリプトも表示するに `Control` は、\ (Windows、Linux \) または `Command` \ (macOS \) を保持し、[ **JS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-285">To also see scripts, hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose **JS**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       <span data-ttu-id="9cc58-287">CSS と JS ファイルのみを表示する</span><span class="sxs-lookup"><span data-stu-id="9cc58-287">Show CSS and JS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-288">[ **すべて** ] を選択してフィルターを削除し、すべてのリソースをもう一度表示します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-288">Choose **All** to remove the filters and see all resources again.</span></span>  
    
<span data-ttu-id="9cc58-289">「他のフィルター処理ワークフローの [フィルター要求][DevtoolsNetworkReferenceFilter] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc58-289">See [Filter requests][DevtoolsNetworkReferenceFilter] for other filtering workflows.</span></span>  

## <span data-ttu-id="9cc58-290">リクエストをブロック</span><span class="sxs-lookup"><span data-stu-id="9cc58-290">Block requests</span></span>  

<span data-ttu-id="9cc58-291">ページリソースの一部が利用できない場合、ページはどのように表示され、どのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="9cc58-291">How does a page look and behave when some of the page resources are not available?</span></span>  <span data-ttu-id="9cc58-292">完全に失敗したか、まだ機能していますか?</span><span class="sxs-lookup"><span data-stu-id="9cc58-292">Does it fail completely, or is it still somewhat functional?</span></span>  <span data-ttu-id="9cc58-293">確認要求をブロックする:</span><span class="sxs-lookup"><span data-stu-id="9cc58-293">Block requests to find out:</span></span>  

1.  <span data-ttu-id="9cc58-294">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-294">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       <span data-ttu-id="9cc58-296">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="9cc58-296">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-297">「」と入力し `block` 、[ **要求ブロックの表示**] を選択して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-297">Type `block`, choose **Show Request Blocking**, and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **<span data-ttu-id="9cc58-299">リクエストブロックの表示</span><span class="sxs-lookup"><span data-stu-id="9cc58-299">Show Request Blocking</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-300">[ **パターンの追加** ] ( ![ パターン ][ImageAddIcon] の追加) を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-300">Choose **Add Pattern** \(![Add Pattern][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="9cc58-301">「`main.css`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-301">Type `main.css`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       <span data-ttu-id="9cc58-303">ブロッキング</span><span class="sxs-lookup"><span data-stu-id="9cc58-303">Blocking</span></span> `main.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-304">[ **追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-304">Choose **Add**.</span></span>  
1.  <span data-ttu-id="9cc58-305">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="9cc58-305">Reload the page.</span></span>  <span data-ttu-id="9cc58-306">期待どおり、メインのスタイルシートがブロックされているため、ページのスタイルが少し messed ます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-306">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9cc58-307">`main.css`ネットワークログの行。</span><span class="sxs-lookup"><span data-stu-id="9cc58-307">The `main.css` row in the Network Log.</span></span>  <span data-ttu-id="9cc58-308">赤いテキストは、リソースがブロックされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9cc58-308">The red text means that the resource was blocked.</span></span>
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="デモ" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` <span data-ttu-id="9cc58-310">がブロックされています</span><span class="sxs-lookup"><span data-stu-id="9cc58-310">has been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9cc58-311">[ **リクエストのブロックを有効にする** ] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9cc58-311">Deselect the **Enable request blocking** checkbox.</span></span>  

## <span data-ttu-id="9cc58-312">まとめ</span><span class="sxs-lookup"><span data-stu-id="9cc58-312">Conclusion</span></span>  

<span data-ttu-id="9cc58-313">これでチュートリアルを完了しました。</span><span class="sxs-lookup"><span data-stu-id="9cc58-313">Congratulations, you have completed the tutorial.</span></span>  <span data-ttu-id="9cc58-314">Microsoft Edge DevTools での **ネットワーク** パネルの使い方について説明しました。</span><span class="sxs-lookup"><span data-stu-id="9cc58-314">You now know how to use the **Network** panel in the Microsoft Edge DevTools!</span></span>

<span data-ttu-id="9cc58-315">ネットワーク [参照][DevtoolsNetworkReference] に移動して、ネットワークアクティビティの調査に関連するその他の devtools 機能を見つけます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-315">Navigate to the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span></span>  

## <span data-ttu-id="9cc58-316">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="9cc58-316">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-icon.msft.png  
[ImageCloseIcon]: ../media/close-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageScreenshotsIcon]: ../media/screenshots-icon.msft.png  
[ImageSearchIcon]: ../media/search-icon.msft.png  
[ImageSettingsIcon]: ../media/settings-icon.msft.png

<!-- links -->  

<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更する |Microsoft ドキュメント"  
[DevtoolsNetworkReference]: ./reference.md "ネットワーク分析のリファレンス |Microsoft ドキュメント"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "フィルター要求-ネットワーク分析リファレンス |Microsoft ドキュメント"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "概要ウィンドウを非表示にする-ネットワーク分析のリファレンス |Microsoft ドキュメント"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "プロパティによるフィルター要求-ネットワーク分析のリファレンス |Microsoft ドキュメント"
[DevToolsOpen]: ../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Microsoft Edge DevTools を使用して web サイトの速度を最適化する |Microsoft ドキュメント"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "ネットワークアクティビティの調査デモ |故障"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュMDN"  

> [!NOTE]
> <span data-ttu-id="9cc58-326">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9cc58-326">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9cc58-327">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-327">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9cc58-329">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9cc58-329">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
