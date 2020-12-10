---
description: Microsoft Edge DevTools の最も一般的なネットワーク関連機能のチュートリアルです。
title: Microsoft Edge DevTools でネットワーク アクティビティを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a55ff05e29817c483cbf13b8713ef37cf96424d5
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: HT
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

# <span data-ttu-id="9247a-104">Microsoft Edge DevTools でネットワーク アクティビティを検査する</span><span class="sxs-lookup"><span data-stu-id="9247a-104">Inspect network activity in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="9247a-105">これは、最も一般的な DevTools 機能のいくつかの実践的なチュートリアルで、ページのネットワーク アクティビティの検査に関連しています。</span><span class="sxs-lookup"><span data-stu-id="9247a-105">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span></span>  

<span data-ttu-id="9247a-106">代わりに機能を参照する場合は、 [ネットワークの参照][DevtoolsNetworkReference] を確認します。</span><span class="sxs-lookup"><span data-stu-id="9247a-106">See [Network Reference][DevtoolsNetworkReference] if you want to browse features instead.</span></span>  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <span data-ttu-id="9247a-107">ネットワーク パネルを使用する場合</span><span class="sxs-lookup"><span data-stu-id="9247a-107">When to use the Network panel</span></span>  

<span data-ttu-id="9247a-108">通常、リソースが予期したとおりにダウンロードまたはアップロードされるようにする必要がある場合にネットワーク パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9247a-108">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span></span>  <span data-ttu-id="9247a-109">ネットワーク パネルの最も一般的なユースケースは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9247a-109">The most common use cases for the Network panel are:</span></span>  

*   <span data-ttu-id="9247a-110">リソースが実際にすべてアップロードまたはダウンロードされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="9247a-110">Making sure that resources are actually being uploaded or downloaded at all.</span></span>  
*   <span data-ttu-id="9247a-111">HTTP ヘッダー、コンテンツ、サイズなど、個々のリソースのプロパティを検査する。</span><span class="sxs-lookup"><span data-stu-id="9247a-111">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span></span>  
    
<span data-ttu-id="9247a-112">ページの読み込みのパフォーマンスを向上させる方法をお探しの場合は、ネットワーク パネルから開始 **しないでください**。</span><span class="sxs-lookup"><span data-stu-id="9247a-112">If you are looking for ways to improve page load performance, **do not** start with the Network panel.</span></span>  <span data-ttu-id="9247a-113">ネットワーク アクティビティに関連しない読み込みパフォーマンスの問題には、さまざまな種類があります。</span><span class="sxs-lookup"><span data-stu-id="9247a-113">There are many types of load performance issues that are not related to network activity.</span></span>  <span data-ttu-id="9247a-114">ページを改善する方法についての対象候補が表示されるので、監査パネルから開始します。</span><span class="sxs-lookup"><span data-stu-id="9247a-114">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span></span>  <span data-ttu-id="9247a-115">[Web サイトの速度を最適化する][DevtoolsSpeedGetStarted]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9247a-115">See [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

## <span data-ttu-id="9247a-116">ネットワーク パネルを開く</span><span class="sxs-lookup"><span data-stu-id="9247a-116">Open the Network panel</span></span>  

<span data-ttu-id="9247a-117">このチュートリアルを最大限に活用するには、デモを開いてデモのページで機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="9247a-117">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span></span>  

1.  <span data-ttu-id="9247a-118">[デモを開始する][GlitchNetworkGetStarted]を開きます。</span><span class="sxs-lookup"><span data-stu-id="9247a-118">Open the [Get Started Demo][GlitchNetworkGetStarted].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="デモ" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       <span data-ttu-id="9247a-120">デモ</span><span class="sxs-lookup"><span data-stu-id="9247a-120">The demo</span></span>  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="The demo in one window and this tutorial in a different window" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="9247a-121">[DevTools を開始][DevToolsOpen] するには、 `Control`+`Shift`+`J` \(Windows, Linux\) または `Command`+`Option`+`J` \(macOS\) を押します。</span><span class="sxs-lookup"><span data-stu-id="9247a-121">[Open DevTools][DevToolsOpen] by pressing `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="9247a-122">**コンソール**パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="9247a-122">The **Console** panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="コンソール" lightbox="../media/network-glitch-console.msft.png":::
       <span data-ttu-id="9247a-124">**コンソール**</span><span class="sxs-lookup"><span data-stu-id="9247a-124">The **Console**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9247a-125">[ウィンドウの下部に DevTools をドッキング][DevToolsCustomizePlacement]することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9247a-125">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="ウィンドウの下部にドッキングされた DevTools" lightbox="../media/network-glitch-console-bottom.msft.png":::
       <span data-ttu-id="9247a-127">ウィンドウの下部にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="9247a-127">DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-128">**ネットワーク** タブを選択します。  **ネットワーク** パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="9247a-128">Select the **Network** tab.  The **Network** panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="ウィンドウの下部にドッキングされた DevTools のコンソール ツール" lightbox="../media/network-glitch-network-bottom.msft.png":::
       <span data-ttu-id="9247a-130">ウィンドウの下部にドッキングされた DevTools の**コンソール**ツール</span><span class="sxs-lookup"><span data-stu-id="9247a-130">**Console** tool in the DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9247a-131">ネットワーク パネルは空の状態です。</span><span class="sxs-lookup"><span data-stu-id="9247a-131">Right now the Network panel is empty.</span></span>  <span data-ttu-id="9247a-132">DevTools は、開始された場合のみネットワークアクティビティを記録し、DevTools を開始してからはネットワーク アクティビティは発生しません。</span><span class="sxs-lookup"><span data-stu-id="9247a-132">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span></span>  

## <span data-ttu-id="9247a-133">ネットワーク アクティビティをログする</span><span class="sxs-lookup"><span data-stu-id="9247a-133">Log network activity</span></span>  

<span data-ttu-id="9247a-134">ページによって発生するネットワークアクティビティを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9247a-134">To view the network activity that a page causes:</span></span>  

1.  <span data-ttu-id="9247a-135">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="9247a-135">Reload the page.</span></span>  <span data-ttu-id="9247a-136">ネットワーク パネルでは、**ネットワーク ログ**にすべてのネットワークアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-136">The Network panel logs all network activity in the **Network Log**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="ネットワーク ログ" lightbox="../media/network-glitch-network.msft.png":::
       <span data-ttu-id="9247a-138">**ネットワーク ログ**</span><span class="sxs-lookup"><span data-stu-id="9247a-138">The **Network Log**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9247a-139">**ネットワークログ**の各行は、リソースを表します。</span><span class="sxs-lookup"><span data-stu-id="9247a-139">Each row of the **Network Log** represents a resource.</span></span>  <span data-ttu-id="9247a-140">既定では、リソースは時系列順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-140">By default the resources are listed chronologically.</span></span>  <span data-ttu-id="9247a-141">トップリソースは、通常、メインの HTML 文書です。</span><span class="sxs-lookup"><span data-stu-id="9247a-141">The top resource is usually the main HTML document.</span></span>  <span data-ttu-id="9247a-142">一番下のリソースは、最後にリクエストされたものです。</span><span class="sxs-lookup"><span data-stu-id="9247a-142">The bottom resource is whatever was requested last.</span></span>  
    
    <span data-ttu-id="9247a-143">各列は、リソースに関する情報を表します。</span><span class="sxs-lookup"><span data-stu-id="9247a-143">Each column represents information about a resource.</span></span>  <span data-ttu-id="9247a-144">前の図では、既定の列が表示されています。</span><span class="sxs-lookup"><span data-stu-id="9247a-144">In the previous figure the default columns are displayed.</span></span>  

    *   <span data-ttu-id="9247a-145">**状態**。</span><span class="sxs-lookup"><span data-stu-id="9247a-145">**Status**.</span></span>  <span data-ttu-id="9247a-146">応答用の HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="9247a-146">The HTTP status code for response.</span></span>  
    *   <span data-ttu-id="9247a-147">**種類**。</span><span class="sxs-lookup"><span data-stu-id="9247a-147">**Type**.</span></span>  <span data-ttu-id="9247a-148">リソースの種類。</span><span class="sxs-lookup"><span data-stu-id="9247a-148">The resource type.</span></span>  
    *   <span data-ttu-id="9247a-149">**イニシエーター**。</span><span class="sxs-lookup"><span data-stu-id="9247a-149">**Initiator**.</span></span>  <span data-ttu-id="9247a-150">リソースによるリクエストの原因。</span><span class="sxs-lookup"><span data-stu-id="9247a-150">The cause of the resource request.</span></span>  <span data-ttu-id="9247a-151">イニシエーター列のリンクを選ぶと、リクエストの原因になったソースコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-151">Selecting a link in the Initiator column takes you to the source code that caused the request.</span></span>  
    *   <span data-ttu-id="9247a-152">**時刻**。</span><span class="sxs-lookup"><span data-stu-id="9247a-152">**Time**.</span></span>  <span data-ttu-id="9247a-153">リクエストの期間。</span><span class="sxs-lookup"><span data-stu-id="9247a-153">The duration of the request.</span></span>  
    *   <span data-ttu-id="9247a-154">**ウォーター フォール**。</span><span class="sxs-lookup"><span data-stu-id="9247a-154">**Waterfall**.</span></span>  <span data-ttu-id="9247a-155">リクエストの異なるステージのグラフィカル表現。</span><span class="sxs-lookup"><span data-stu-id="9247a-155">A graphical representation of the different stages of the request.</span></span>  <span data-ttu-id="9247a-156">ウォーターフォールの上にマウスポインターを置いて、ブレークダウンを表示します。</span><span class="sxs-lookup"><span data-stu-id="9247a-156">Hover over a Waterfall to see a breakdown.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9247a-157">ネットワーク ログの上のグラフは概要と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="9247a-157">The graph above the Network Log is called the Overview.</span></span>  <span data-ttu-id="9247a-158">このチュートリアルの概要グラフは使用しないため、非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9247a-158">You will not use the Overview graph in this tutorial, so you may hide it.</span></span>  <span data-ttu-id="9247a-159">[概要ウィンドウを非表示にする][DevtoolsReferenceHideOverview]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9247a-159">See [Hide the Overview pane][DevtoolsReferenceHideOverview].</span></span>
    
1.  <span data-ttu-id="9247a-160">DevTools を開くと、ネットワーク ログにネットワークアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-160">After you open DevTools, it records network activity in the Network Log.</span></span>  
    <span data-ttu-id="9247a-161">これを実践するには、まず **ネットワーク ログ** の下部を確認し、最後のアクティビティを頭で記録します。</span><span class="sxs-lookup"><span data-stu-id="9247a-161">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span></span>  
1.  <span data-ttu-id="9247a-162">次に、デモで **データ取得** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9247a-162">Now, select the **Get Data** button in the demo.</span></span>  
1.  <span data-ttu-id="9247a-163">もう一度 **ネットワーク ログ** の下部を確認します。</span><span class="sxs-lookup"><span data-stu-id="9247a-163">Look at the bottom of the **Network Log** again.</span></span>  <span data-ttu-id="9247a-164">`getstarted.json` と呼ばれる新しいリソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-164">You should see a new resource called `getstarted.json`.</span></span>  <span data-ttu-id="9247a-165">**データ取得** ボタンを選択すると、ページによってこのファイルが要求されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-165">Selecting the **Get Data** button caused the page to request this file.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="ネットワーク ログの新しいリソース" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       <span data-ttu-id="9247a-167">**ネットワーク ログ**の新しいリソース</span><span class="sxs-lookup"><span data-stu-id="9247a-167">A new resource in the **Network Log**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9247a-168">詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="9247a-168">Show more information</span></span>  

<span data-ttu-id="9247a-169">ネットワークログの列は構成可能です。</span><span class="sxs-lookup"><span data-stu-id="9247a-169">The columns of the Network Log are configurable.</span></span>  <span data-ttu-id="9247a-170">使用していない列を非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9247a-170">You may hide columns that you are not using.</span></span>  
<span data-ttu-id="9247a-171">既定では非表示になっていますが、役に立つと思われる列も数多くあります。</span><span class="sxs-lookup"><span data-stu-id="9247a-171">There are also many columns that are hidden by default which you may find useful.</span></span>  

1.  <span data-ttu-id="9247a-172">ネットワーク ログ テーブルのヘッダーを右クリックして、**ドメイン** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9247a-172">Right-click the header of the Network Log table and choose **Domain**.</span></span>  <span data-ttu-id="9247a-173">各リソースのドメインが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9247a-173">The domain of each resource is now shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="ドメインの列を有効にする" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       <span data-ttu-id="9247a-175">ドメインの列を有効にする</span><span class="sxs-lookup"><span data-stu-id="9247a-175">Enable the Domain column</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="9247a-176">**名前** 列のセルの上にマウスポインターを置いて、リソースの完全な URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="9247a-176">See the full URL of a resource by hovering over the cell in the **Name** column.</span></span>  
    
## <span data-ttu-id="9247a-177">低速ネットワーク接続のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="9247a-177">Simulate a slower network connection</span></span>  

<span data-ttu-id="9247a-178">サイトの構築に使用するコンピューターのネットワーク接続は、おそらく、ユーザーのモバイルデ バイスのネットワーク接続よりも高速です。</span><span class="sxs-lookup"><span data-stu-id="9247a-178">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span></span>  <span data-ttu-id="9247a-179">ページを調整して、モバイル デバイスでページが読み込まれるまでの時間を把握することができます。</span><span class="sxs-lookup"><span data-stu-id="9247a-179">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span></span>  

1.  <span data-ttu-id="9247a-180">**調整** ドロップダウンを選択します。これは、既定で **オンライン** に設定されているものです。</span><span class="sxs-lookup"><span data-stu-id="9247a-180">Select the **Throttling** dropdown, which is set to **Online** by default.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="調整を有効にする" lightbox="../media/network-glitch-network-throttling.msft.png":::
       <span data-ttu-id="9247a-182">調整を有効にする</span><span class="sxs-lookup"><span data-stu-id="9247a-182">Enable throttling</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-183">**スロー (低速) 3G** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9247a-183">Choose **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="スロー (低速) 3G を選択" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       <span data-ttu-id="9247a-185">スロー (低速) 3G を選択</span><span class="sxs-lookup"><span data-stu-id="9247a-185">Select Slow 3G</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-186">**再読み込み** \(![再読み込み][ImageRefreshIcon]\) を長押しして **キャッシュを空にして再読み込み** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9247a-186">Long-press **Reload** \(![Reload][ImageRefreshIcon]\) and then choose **Empty Cache And Hard Reload**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="キャッシュを空にして再読み込み" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **<span data-ttu-id="9247a-188">キャッシュを空にして再読み込み</span><span class="sxs-lookup"><span data-stu-id="9247a-188">Empty Cache And Hard Reload</span></span>**  
    :::image-end:::  
    
    <span data-ttu-id="9247a-189">繰り返しアクセスした場合、ブラウザーは通常 [キャッシュ][MDNHTTPCache] の一部のファイルを提供します。これにより、ページの読み込みが高速化します。</span><span class="sxs-lookup"><span data-stu-id="9247a-189">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache], which speeds up the page load.</span></span>  <span data-ttu-id="9247a-190">**キャッシュを空にして再読み込み** で、ブラウザーは強制的にすべてのリソースのネットワークにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9247a-190">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span></span>  <span data-ttu-id="9247a-191">これは、初めてのユーザーがあるページの読み込みを使用する方法を確認する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9247a-191">This is helpful when you want to see how a first-time visitor experiences a page load.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9247a-192">**キャッシュを空にして再読み込み** ワークフローは、DevTools を開いている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9247a-192">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span></span>  
    
## <span data-ttu-id="9247a-193">スクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="9247a-193">Capture screenshots</span></span>  

<span data-ttu-id="9247a-194">スクリーンショットを使用すると、読み込み中にページがどのように表示されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9247a-194">Screenshots let you see how a page looked over time while it was loading.</span></span>  

1.  <span data-ttu-id="9247a-195">\(![ネットワーク設定][ImageSettingsIcon]\) を選択し、**スクリーンショットをキャプチャする** チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9247a-195">Select \(![Network settings][ImageSettingsIcon]\) and select the **Capture screenshots** checkbox.</span></span>
1.  <span data-ttu-id="9247a-196">**キャッシュを空にして再読み込み** ワークフローを使用して、もう一度ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="9247a-196">Reload the page again via the **Empty Cache And Hard Reload** workflow.</span></span>  <span data-ttu-id="9247a-197">この方法についてリマインダーが必要な場合は、[低速接続をシミュレートする](#simulate-a-slower-network-connection) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9247a-197">See [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span></span>  
    <span data-ttu-id="9247a-198">スクリーンショット ウィンドウには、読み込み処理中のさまざまなポイントでのページ表示方法についてサムネイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-198">The Screenshots pane provides thumbnails of how the page looked at various points during the loading process.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="ページの読み込みのスクリーンショット" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       <span data-ttu-id="9247a-200">ページの読み込みのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="9247a-200">Screenshots of the page load</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-201">最初のサムネイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9247a-201">Select the first thumbnail.</span></span>  <span data-ttu-id="9247a-202">DevTools では、その地点で発生しているネットワーク アクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-202">DevTools shows you what network activity was occurring at that moment in time.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="最初のスクリーンショット中に発生したネットワーク アクティビティ" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       <span data-ttu-id="9247a-204">最初のスクリーンショット中に発生したネットワーク アクティビティ</span><span class="sxs-lookup"><span data-stu-id="9247a-204">The network activity that was happening during the first screenshot</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-205">\(![ネットワーク設定][ImageSettingsIcon]\) をもう一度選択し、**スクリーンショットをキャプチャする** チェックボックスをオフにして、スクリーンショット ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9247a-205">Select \(![Network settings][ImageSettingsIcon]\) again and deselect the **Capture screenshots** checkbox to close the Screenshots pane.</span></span>
1.  <span data-ttu-id="9247a-206">ページをもう一度読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9247a-206">Reload the page again.</span></span>  
    
## <span data-ttu-id="9247a-207">リソースの詳細を検査する</span><span class="sxs-lookup"><span data-stu-id="9247a-207">Inspect the details of the resource</span></span>  

<span data-ttu-id="9247a-208">リソースを選択して、詳細情報を参照します。</span><span class="sxs-lookup"><span data-stu-id="9247a-208">Select a resource to learn more information about it.</span></span>  <span data-ttu-id="9247a-209">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="9247a-209">Try it now:</span></span>  

1.  <span data-ttu-id="9247a-210">`getstarted.html` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9247a-210">Select `getstarted.html`.</span></span>  <span data-ttu-id="9247a-211">**ヘッダー** タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-211">The **Headers** tab is shown.</span></span>  <span data-ttu-id="9247a-212">このタブを使用して、HTTP ヘッダーを検査します。</span><span class="sxs-lookup"><span data-stu-id="9247a-212">Use this tab to inspect HTTP headers.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text="[ヘッダー] タブ" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       <span data-ttu-id="9247a-214">**ヘッダー** タブ</span><span class="sxs-lookup"><span data-stu-id="9247a-214">The **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-215">**プレビュー** タブを選択します。  HTML の基本的なレンダリングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-215">Select the **Preview** tab.  A basic rendering of the HTML is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text="[プレビュー] タブ" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       <span data-ttu-id="9247a-217">**プレビュー** タブ</span><span class="sxs-lookup"><span data-stu-id="9247a-217">The **Preview** tab</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9247a-218">このタブは、API が HTML でエラーコードを返す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9247a-218">This tab is helpful when an API returns an error code in HTML.</span></span>  <span data-ttu-id="9247a-219">HTML ソースコードよりも、または画像を検査する場合よりも、レンダリングされた HTML の方が読みやすいと思われるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="9247a-219">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span></span>  

1.  <span data-ttu-id="9247a-220">**応答** タブを選択します。  HTML ソースコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-220">Select the **Response** tab.  The HTML source code is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="[応答] タブ" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       <span data-ttu-id="9247a-222">**応答** タブ</span><span class="sxs-lookup"><span data-stu-id="9247a-222">The **Response** tab</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="9247a-223">ファイルが縮小されたときに、**応答** タブの下部にある**フォーマット** \(![フォーマット][ImageFormatIcon]\) ボタンを選択すると、ファイルの内容が読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="9247a-223">When a file is minified, selecting the **Format** \(![Format][ImageFormatIcon]\) button at the bottom of the **Response** tab re-formats the contents of the file for readability.</span></span>  
    
1.  <span data-ttu-id="9247a-224">**タイミング** タブを選択します。 このリソースのネットワークアクティビティの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-224">Select the **Timing** tab.  A breakdown of the network activity for this resource is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text="[タイミング] タブ" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       <span data-ttu-id="9247a-226">**タイミング** タブ</span><span class="sxs-lookup"><span data-stu-id="9247a-226">The **Timing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-227">**閉じる** \(![閉じる][ImageCloseIcon]\) を選択して、もう一度ネットワーク ログを表示します。</span><span class="sxs-lookup"><span data-stu-id="9247a-227">Choose **Close** \(![Close][ImageCloseIcon]\) to view the Network Log again.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="[閉じる] ボタン" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       <span data-ttu-id="9247a-229">**閉じる** ボタン</span><span class="sxs-lookup"><span data-stu-id="9247a-229">The **Close** button</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9247a-230">ネットワークのヘッダーと返信を検索する</span><span class="sxs-lookup"><span data-stu-id="9247a-230">Search network headers and responses</span></span>  

<span data-ttu-id="9247a-231">特定の文字列または正規表現に関するすべてのリソースの HTTP ヘッダーと応答を検索する必要がある場合は、**検索** ウィンドウを使用します。</span><span class="sxs-lookup"><span data-stu-id="9247a-231">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span></span>  

<span data-ttu-id="9247a-232">たとえば、リソースが適切な **キャッシュポリシー** を使用していることを確認する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="9247a-232">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span></span>  

<!--TODO: add cache policies section when available  -->

1.  <span data-ttu-id="9247a-233">**検索** \(![検索][ImageSearchIcon]\) を選びます。</span><span class="sxs-lookup"><span data-stu-id="9247a-233">Choose **Search** \(![Search][ImageSearchIcon]\).</span></span>  <span data-ttu-id="9247a-234">[検索] ウィンドウがネットワーク ログの左側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-234">The Search pane opens to the left of the Network log.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="[検索] ウィンドウ" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       <span data-ttu-id="9247a-236">**検索** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9247a-236">The **Search** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-237">`Cache-Control` を入力して、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9247a-237">Type `Cache-Control` and select `Enter`.</span></span>  <span data-ttu-id="9247a-238">[検索] ウィンドウには、リソース ヘッダーまたはコンテンツ内で見つかった `Cache-Control` のすべてのインスタンスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-238">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="キャッシュ コントロールの検索結果" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       <span data-ttu-id="9247a-240">検索結果</span><span class="sxs-lookup"><span data-stu-id="9247a-240">Search results for</span></span> `Cache-Control`  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-241">結果を選択すると、結果が見つかったリソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-241">Select a result to view the resource in which the result was found.</span></span>  <span data-ttu-id="9247a-242">リソースの詳細を参照している場合は、結果を選択して直接移動します。</span><span class="sxs-lookup"><span data-stu-id="9247a-242">If you are looking at the details of the resource, select a result to go directly to it.</span></span>  <span data-ttu-id="9247a-243">たとえば、ヘッダーでクエリが見つかった場合、[ヘッダー] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="9247a-243">For example, if the query was found in a header, the Headers tab opens.</span></span>   <span data-ttu-id="9247a-244">コンテンツ内にクエリが見つかった場合は、**応答** タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="9247a-244">If the query was found in content, the **Response** tab opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text="[ヘッダー] タブで強調表示された検索結果" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       <span data-ttu-id="9247a-246">**ヘッダー** タブで強調表示された検索結果</span><span class="sxs-lookup"><span data-stu-id="9247a-246">A search result highlighted in the **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-247">[検索] ウィンドウと [ヘッダー] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9247a-247">Close the Search pane and the Headers tab.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="[閉じる] ボタン" lightbox="../media/network-glitch-network-search-close.msft.png":::
       <span data-ttu-id="9247a-249">**閉じる** ボタン</span><span class="sxs-lookup"><span data-stu-id="9247a-249">The **Close** buttons</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="9247a-250">リソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="9247a-250">Filter resources</span></span>  

<span data-ttu-id="9247a-251">DevTools には、タスクに直接関連していないリソースをフィルター処理する多数のワークフローが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9247a-251">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span></span>  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="[フィルター] ツールバー" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   <span data-ttu-id="9247a-253">**フィルター** ツールバー</span><span class="sxs-lookup"><span data-stu-id="9247a-253">The **Filters** toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="9247a-254">**フィルター** ツールバーは、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9247a-254">The **Filters** toolbar should be enabled by default.</span></span>  <span data-ttu-id="9247a-255">そうでなければ：</span><span class="sxs-lookup"><span data-stu-id="9247a-255">If not:</span></span>  

1.  <span data-ttu-id="9247a-256">**フィルター** \(![フィルター][ImageFilterIcon]\) を選んで表示します。</span><span class="sxs-lookup"><span data-stu-id="9247a-256">Choose **Filter** \(![Filter][ImageFilterIcon]\) to show it.</span></span>  
    
### <span data-ttu-id="9247a-257">文字列、正規表現、またはプロパティによってフィルターする</span><span class="sxs-lookup"><span data-stu-id="9247a-257">Filter by string, regular expression, or property</span></span>  

<span data-ttu-id="9247a-258">**フィルター** テキスト ボックスでは、さまざまな種類のフィルターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9247a-258">The **Filter** text box supports many different types of filtering.</span></span>  

1.  <span data-ttu-id="9247a-259">`png` を **フィルター** テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9247a-259">Type `png` into the **Filter** text box.</span></span>  <span data-ttu-id="9247a-260">テキスト `png` が含まれているファイルだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-260">Only the files that contain the text `png` are shown.</span></span>  <span data-ttu-id="9247a-261">この場合、フィルターに一致するファイルは PNG 画像のみです。</span><span class="sxs-lookup"><span data-stu-id="9247a-261">In this case the only files that match the filter are the PNG images.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="文字列フィルター" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       <span data-ttu-id="9247a-263">文字列フィルター</span><span class="sxs-lookup"><span data-stu-id="9247a-263">A string filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-264">「`/.*\.[cj]s+$/`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9247a-264">Type `/.*\.[cj]s+$/`.</span></span>  <span data-ttu-id="9247a-265">DevTools では、末尾が `j` または `c` で終わらず、1つ以上の`s`文字が続いているファイル名で任意のリソースをフィルター処理 します。</span><span class="sxs-lookup"><span data-stu-id="9247a-265">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="正規表現フィルター" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       <span data-ttu-id="9247a-267">正規表現フィルター</span><span class="sxs-lookup"><span data-stu-id="9247a-267">A regular expression filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-268">「`-main.css`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9247a-268">Type `-main.css`.</span></span>  <span data-ttu-id="9247a-269">DevTools で `main.css` をフィルターします。</span><span class="sxs-lookup"><span data-stu-id="9247a-269">DevTools filters out `main.css`.</span></span>  <span data-ttu-id="9247a-270">他のファイルがそのパターンに一致した場合は、それらもフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-270">If any other file matched the pattern they would also be filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="ネガティブ フィルター" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       <span data-ttu-id="9247a-272">ネガティブ フィルター</span><span class="sxs-lookup"><span data-stu-id="9247a-272">A negative filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-273">`domain:cdn.glitch.com` を **フィルター処理** テキスト ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9247a-273">Type `domain:cdn.glitch.com` into the **Filter** text box.</span></span>  <span data-ttu-id="9247a-274">DevTools では、このドメインと一致しない URL のリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9247a-274">DevTools filters out any resource with a URL that does not match this domain.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="プロパティ フィルター" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       <span data-ttu-id="9247a-276">プロパティ フィルター</span><span class="sxs-lookup"><span data-stu-id="9247a-276">A property filter</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9247a-277">フィルター処理できるプロパティの完全なリストについては、[プロパティ別にリクエストをフィルター処理する][DevtoolsReferenceProperty] を参照します。</span><span class="sxs-lookup"><span data-stu-id="9247a-277">See [Filter requests by properties][DevtoolsReferenceProperty] for the full list of filterable properties.</span></span>  
    
1.  <span data-ttu-id="9247a-278">任意のテキストのテキスト ボックスを **フィルター処理** をクリアします。</span><span class="sxs-lookup"><span data-stu-id="9247a-278">Clear the **Filter** text box of any text.</span></span>  
    
### <span data-ttu-id="9247a-279">リソースの種類でフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="9247a-279">Filter by resource type</span></span>  

<span data-ttu-id="9247a-280">スタイルシートなど、特定の種類のファイルに重点を置く場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9247a-280">To focus in on a certain type of file, such as stylesheets:</span></span>  

1.  <span data-ttu-id="9247a-281">**CSS** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9247a-281">Choose **CSS**.</span></span>  <span data-ttu-id="9247a-282">その他のすべての種類のファイルはフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-282">All other file types are filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="CSS ファイルのみを表示する" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       <span data-ttu-id="9247a-284">CSS ファイルのみを表示する</span><span class="sxs-lookup"><span data-stu-id="9247a-284">Show CSS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-285">スクリプトも表示するに `Control` \(Windows, Linux\) または `Command` \(macOS\)を保持してから、**JS** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9247a-285">To also see scripts, hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose **JS**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="CSS と JS ファイルのみを表示する" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       <span data-ttu-id="9247a-287">CSS と JS ファイルのみを表示する</span><span class="sxs-lookup"><span data-stu-id="9247a-287">Show CSS and JS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-288">**すべて** を選択してフィルターを削除し、すべてのリソースをもう一度表示します。</span><span class="sxs-lookup"><span data-stu-id="9247a-288">Choose **All** to remove the filters and see all resources again.</span></span>  
    
<span data-ttu-id="9247a-289">他のフィルター処理ワークフローについては、[フィルターのリクエスト][DevtoolsNetworkReferenceFilter] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9247a-289">See [Filter requests][DevtoolsNetworkReferenceFilter] for other filtering workflows.</span></span>  

## <span data-ttu-id="9247a-290">リクエストをブロック</span><span class="sxs-lookup"><span data-stu-id="9247a-290">Block requests</span></span>  

<span data-ttu-id="9247a-291">ページリソースの一部が利用できない場合、ページはどのように表示され、どのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="9247a-291">How does a page look and behave when some of the page resources are not available?</span></span>  <span data-ttu-id="9247a-292">完全に失敗しましたか? それとも、まだ機能していますか?</span><span class="sxs-lookup"><span data-stu-id="9247a-292">Does it fail completely, or is it still somewhat functional?</span></span>  <span data-ttu-id="9247a-293">リクエストをブロックして、以下の内容を見つけます:</span><span class="sxs-lookup"><span data-stu-id="9247a-293">Block requests to find out:</span></span>  

1.  <span data-ttu-id="9247a-294">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="9247a-294">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="コマンド メニュー" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       <span data-ttu-id="9247a-296">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="9247a-296">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-297">`block` と入力して、**リクエストのブロックを表示** を選択してから、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9247a-297">Type `block`, choose **Show Request Blocking**, and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="リクエストのブロックを表示" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **<span data-ttu-id="9247a-299">リクエストのブロックを表示</span><span class="sxs-lookup"><span data-stu-id="9247a-299">Show Request Blocking</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-300">**パターンを追加** \(![パターンを追加][ImageAddIcon]\) を選びます。</span><span class="sxs-lookup"><span data-stu-id="9247a-300">Choose **Add Pattern** \(![Add Pattern][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="9247a-301">「`main.css`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9247a-301">Type `main.css`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="メインの.css をブロックする" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       <span data-ttu-id="9247a-303">ブロッキング</span><span class="sxs-lookup"><span data-stu-id="9247a-303">Blocking</span></span> `main.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-304">**追加** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9247a-304">Choose **Add**.</span></span>  
1.  <span data-ttu-id="9247a-305">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="9247a-305">Reload the page.</span></span>  <span data-ttu-id="9247a-306">予想どおり、メインのスタイルシートがブロックされているため、ページのスタイルがあまりよくありません。</span><span class="sxs-lookup"><span data-stu-id="9247a-306">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9247a-307">ネットワーク ログの `main.css` 行。</span><span class="sxs-lookup"><span data-stu-id="9247a-307">The `main.css` row in the Network Log.</span></span>  <span data-ttu-id="9247a-308">赤いテキストは、リソースがブロックされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9247a-308">The red text means that the resource was blocked.</span></span>
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="メインの.css がブロックされています" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` <span data-ttu-id="9247a-310">ブロックされています</span><span class="sxs-lookup"><span data-stu-id="9247a-310">has been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9247a-311">**リクエストのブロックを有効にする** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9247a-311">Deselect the **Enable request blocking** checkbox.</span></span>  

## <span data-ttu-id="9247a-312">まとめ</span><span class="sxs-lookup"><span data-stu-id="9247a-312">Conclusion</span></span>  

<span data-ttu-id="9247a-313">おめでとうございます。これでチュートリアルは完了です。</span><span class="sxs-lookup"><span data-stu-id="9247a-313">Congratulations, you have completed the tutorial.</span></span>  <span data-ttu-id="9247a-314">Microsoft Edge DevTools での **ネットワーク** パネルの使い方を理解できました。</span><span class="sxs-lookup"><span data-stu-id="9247a-314">You now know how to use the **Network** panel in the Microsoft Edge DevTools!</span></span>

<span data-ttu-id="9247a-315">[ネットワーク リファレンス][DevtoolsNetworkReference] に移動して、ネットワーク アクティビティの調査に関連するその他の DevTools 機能を見つけます。</span><span class="sxs-lookup"><span data-stu-id="9247a-315">Navigate to the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span></span>  

## <span data-ttu-id="9247a-316">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="9247a-316">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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

[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更 | Microsoft Docs"  
[DevtoolsNetworkReference]: ./reference.md "ネットワーク分析のリファレンス | Microsoft Docs"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "フィルターのリクエスト - ネットワーク分析リファレンス | Microsoft Docs"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "概要ウィンドウを非表示 - ネットワーク分析リファレンス | Microsoft Docs"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "プロパティによるリクエストをフィルター処理 - ネットワーク分析のリファレンス | Microsoft Docs"
[DevToolsOpen]: ../open.md "Microsoft Edge DevTools を開く | Microsoft Docs"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Microsoft Edge DevTools を使用して web サイトの速度を最適化 | Microsoft Docs"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "ネットワーク アクティビティのデモを検査 | グリッチ"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュ | MDN"  

> [!NOTE]
> <span data-ttu-id="9247a-326">このページの一部は、 [Google によって][GoogleSitePolicies] 作成および共有され、 [クリエイティブ コモンズ 4.0 インターナショナル ライセンス][CCA4IL]で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9247a-326">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9247a-327">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/index) にあり、[Kayce Basques][KayceBasques] で作成されています (Technical Writer, Chrome DevTools \& Lighthouse\)。</span><span class="sxs-lookup"><span data-stu-id="9247a-327">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブ コモンズ ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9247a-329">この著作物は、[クリエイティブ コモンズ 4.0 インターナショナル ライセンス][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9247a-329">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
