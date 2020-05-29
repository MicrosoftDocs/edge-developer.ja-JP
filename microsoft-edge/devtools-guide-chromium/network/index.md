---
title: Microsoft Edge DevTools でネットワークアクティビティを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 267b0113e07085dd565a3ff3437a3fcac2dff9d7
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611813"
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





# <span data-ttu-id="45d2e-103">Microsoft Edge DevTools でネットワークアクティビティを検査する</span><span class="sxs-lookup"><span data-stu-id="45d2e-103">Inspect Network Activity In Microsoft Edge DevTools</span></span>   



<span data-ttu-id="45d2e-104">これは、ページのネットワークアクティビティの検査に関連する、よく使われる DevTools 機能のいくつかの実践的なチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="45d2e-104">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span></span>  

<span data-ttu-id="45d2e-105">代わりに機能を参照する場合は、[ネットワークの参照][DevtoolsNetworkReference]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d2e-105">See [Network Reference][DevtoolsNetworkReference] if you want to browse features instead.</span></span>  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <span data-ttu-id="45d2e-106">[ネットワーク] パネルを使用する場合</span><span class="sxs-lookup"><span data-stu-id="45d2e-106">When to use the Network panel</span></span>   

<span data-ttu-id="45d2e-107">通常、[ネットワーク] パネルは、リソースが予期したとおりにダウンロードまたはアップロードされるようにする必要がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-107">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span></span>  <span data-ttu-id="45d2e-108">[ネットワーク] パネルの最も一般的なユースケースは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="45d2e-108">The most common use cases for the Network panel are:</span></span>  

*   <span data-ttu-id="45d2e-109">リソースが実際にはまったくアップロードまたはダウンロードされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-109">Making sure that resources are actually being uploaded or downloaded at all.</span></span>  
*   <span data-ttu-id="45d2e-110">HTTP ヘッダー、コンテンツ、サイズなど、個々のリソースのプロパティを検査します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-110">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span></span>  

<span data-ttu-id="45d2e-111">ページの読み込みのパフォーマンスを向上させる方法を探している場合は、[ネットワーク] パネルから開始しないで**ください**。</span><span class="sxs-lookup"><span data-stu-id="45d2e-111">If you are looking for ways to improve page load performance, **do not** start with the Network panel.</span></span>  <span data-ttu-id="45d2e-112">ネットワークアクティビティに関連していない読み込みパフォーマンスの問題には、さまざまな種類があります。</span><span class="sxs-lookup"><span data-stu-id="45d2e-112">There are many types of load performance issues that are not related to network activity.</span></span>  <span data-ttu-id="45d2e-113">ページを改善する方法についての候補が表示されるため、監査パネルから開始します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-113">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span></span>  <span data-ttu-id="45d2e-114">「 [Web サイトの速度を最適化][DevtoolsSpeedGetStarted]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d2e-114">See [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

## <span data-ttu-id="45d2e-115">[ネットワーク] パネルを開く</span><span class="sxs-lookup"><span data-stu-id="45d2e-115">Open the Network panel</span></span>   

<span data-ttu-id="45d2e-116">このチュートリアルを最大限に活用するには、デモを開き、デモページの機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="45d2e-116">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span></span>  

1.  <span data-ttu-id="45d2e-117">[はじめに] の[デモ][GlitchNetworkGetStarted]を開きます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-117">Open the [Get Started Demo][GlitchNetworkGetStarted] .</span></span>  
    
    > ##### <span data-ttu-id="45d2e-118">図 1</span><span class="sxs-lookup"><span data-stu-id="45d2e-118">Figure 1</span></span>  
    > <span data-ttu-id="45d2e-119">デモ</span><span class="sxs-lookup"><span data-stu-id="45d2e-119">The demo</span></span>  
    > ![デモ][ImagesTutorialDemo]  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    > ##### old Figure 2  
    > The demo in one window and this tutorial in a different window  
    > ![The demo in one window and this tutorial in a different window][ImagesTutorialWindows]  -->

1.  <span data-ttu-id="45d2e-121">[Open DevTools][DevToolsOpen] `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押して、devtools を開きます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-121">[Open DevTools][DevToolsOpen] by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="45d2e-122">**コンソール**パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-122">The **Console** panel opens.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-123">図 2</span><span class="sxs-lookup"><span data-stu-id="45d2e-123">Figure 2</span></span>  
    > <span data-ttu-id="45d2e-124">本体</span><span class="sxs-lookup"><span data-stu-id="45d2e-124">The Console</span></span>  
    > <span data-ttu-id="45d2e-125">![コンソール][ImagesTutorialConsole]</span><span class="sxs-lookup"><span data-stu-id="45d2e-125">![The Console][ImagesTutorialConsole]</span></span>  
    
    <span data-ttu-id="45d2e-126">[ウィンドウの下部に DevTools をドッキング][DevToolsCustomizePlacement]することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-126">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span></span>  
    
    > ##### <span data-ttu-id="45d2e-127">図 3</span><span class="sxs-lookup"><span data-stu-id="45d2e-127">Figure 3</span></span>  
    > <span data-ttu-id="45d2e-128">ウィンドウの下部にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="45d2e-128">DevTools docked to the bottom of the window</span></span>  
    > <span data-ttu-id="45d2e-129">![DevTools] ウィンドウの下部にドッキングされています。[ImagesTutorialDocked]</span><span class="sxs-lookup"><span data-stu-id="45d2e-129">![DevTools docked to the bottom of the window][ImagesTutorialDocked]</span></span>  

1.  <span data-ttu-id="45d2e-130">[**ネットワーク**] タブを選択します。 [ネットワーク] パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-130">Select the **Network** tab.  The Network panel opens.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-131">図 4</span><span class="sxs-lookup"><span data-stu-id="45d2e-131">Figure 4</span></span>  
    > <span data-ttu-id="45d2e-132">ウィンドウの下部にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="45d2e-132">DevTools docked to the bottom of the window</span></span>  
    > <span data-ttu-id="45d2e-133">![DevTools] ウィンドウの下部にドッキングされています。[ImagesTutorialNetwork]</span><span class="sxs-lookup"><span data-stu-id="45d2e-133">![DevTools docked to the bottom of the window][ImagesTutorialNetwork]</span></span>  

<span data-ttu-id="45d2e-134">[ネットワーク] パネルが空になりました。</span><span class="sxs-lookup"><span data-stu-id="45d2e-134">Right now the Network panel is empty.</span></span>  <span data-ttu-id="45d2e-135">DevTools は、開いた後にのみネットワークアクティビティを記録し、DevTools を開いた後のネットワークアクティビティは発生しませんでした。</span><span class="sxs-lookup"><span data-stu-id="45d2e-135">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span></span>  

## <span data-ttu-id="45d2e-136">ネットワークアクティビティをログに記録する</span><span class="sxs-lookup"><span data-stu-id="45d2e-136">Log network activity</span></span>   

<span data-ttu-id="45d2e-137">ページによって発生するネットワークアクティビティを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="45d2e-137">To view the network activity that a page causes:</span></span>  

1.  <span data-ttu-id="45d2e-138">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-138">Reload the page.</span></span>  <span data-ttu-id="45d2e-139">ネットワークパネルでは、ネットワーク**ログ**にすべてのネットワークアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-139">The Network panel logs all network activity in the **Network Log**.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-140">図 5</span><span class="sxs-lookup"><span data-stu-id="45d2e-140">Figure 5</span></span>  
    > <span data-ttu-id="45d2e-141">ネットワークログ</span><span class="sxs-lookup"><span data-stu-id="45d2e-141">The Network Log</span></span>  
    > <span data-ttu-id="45d2e-142">![ネットワークログ][ImagesTutorialLog]</span><span class="sxs-lookup"><span data-stu-id="45d2e-142">![The Network Log][ImagesTutorialLog]</span></span>  
    
    <span data-ttu-id="45d2e-143">**ネットワークログ**の各行は、リソースを表します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-143">Each row of the **Network Log** represents a resource.</span></span>  <span data-ttu-id="45d2e-144">既定では、リソースは時系列順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-144">By default the resources are listed chronologically.</span></span>  <span data-ttu-id="45d2e-145">トップリソースは、通常、メインの HTML 文書です。</span><span class="sxs-lookup"><span data-stu-id="45d2e-145">The top resource is usually the main HTML document.</span></span>  <span data-ttu-id="45d2e-146">一番下のリソースは、要求されたすべてのものです。</span><span class="sxs-lookup"><span data-stu-id="45d2e-146">The bottom resource is whatever was requested last.</span></span>  
    
    <span data-ttu-id="45d2e-147">各列は、リソースに関する情報を表します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-147">Each column represents information about a resource.</span></span>  <span data-ttu-id="45d2e-148">[**図 6**](#figure-6)は、既定の列を示しています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-148">[**Figure 6**](#figure-6) shows the default columns:</span></span>  

    *   <span data-ttu-id="45d2e-149">**状態**。</span><span class="sxs-lookup"><span data-stu-id="45d2e-149">**Status**.</span></span>  <span data-ttu-id="45d2e-150">応答の HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="45d2e-150">The HTTP status code for response.</span></span>  
    *   <span data-ttu-id="45d2e-151">**[種類]**。</span><span class="sxs-lookup"><span data-stu-id="45d2e-151">**Type**.</span></span>  <span data-ttu-id="45d2e-152">リソースの種類。</span><span class="sxs-lookup"><span data-stu-id="45d2e-152">The resource type.</span></span>  
    *   <span data-ttu-id="45d2e-153">**イニシエーター**。</span><span class="sxs-lookup"><span data-stu-id="45d2e-153">**Initiator**.</span></span>  <span data-ttu-id="45d2e-154">リソース要求の原因。</span><span class="sxs-lookup"><span data-stu-id="45d2e-154">The cause of the resource request.</span></span>  <span data-ttu-id="45d2e-155">[イニシエーター] 列のリンクを選ぶと、要求を発生させたソースコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-155">Selecting a link in the Initiator column takes you to the source code that caused the request.</span></span>  
    *   <span data-ttu-id="45d2e-156">**時刻**。</span><span class="sxs-lookup"><span data-stu-id="45d2e-156">**Time**.</span></span>  <span data-ttu-id="45d2e-157">要求の期間。</span><span class="sxs-lookup"><span data-stu-id="45d2e-157">The duration of the request.</span></span>  
    *   <span data-ttu-id="45d2e-158">**ウォーターフォール**</span><span class="sxs-lookup"><span data-stu-id="45d2e-158">**Waterfall**.</span></span>  <span data-ttu-id="45d2e-159">要求の異なるステージのグラフィカル表現。</span><span class="sxs-lookup"><span data-stu-id="45d2e-159">A graphical representation of the different stages of the request.</span></span>  
        <span data-ttu-id="45d2e-160">ウォーターフォールの上にマウスポインターを置くと、ブレークダウンが表示できます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-160">Hover over a Waterfall to see a breakdown.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="45d2e-161">ネットワークログの上のグラフは概要と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-161">The graph above the Network Log is called the Overview.</span></span>  <span data-ttu-id="45d2e-162">このチュートリアルの概要グラフは使用しないため、非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-162">You will not use the Overview graph in this tutorial, so you may hide it.</span></span>  <span data-ttu-id="45d2e-163">「[概要ウィンドウを非表示にする」を][DevtoolsReferenceHideOverview]参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d2e-163">See [Hide the Overview pane][DevtoolsReferenceHideOverview].</span></span>
        
1.  <span data-ttu-id="45d2e-164">DevTools を開くと、ネットワークログにネットワークアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-164">After you open DevTools, it records network activity in the Network Log.</span></span>  
    <span data-ttu-id="45d2e-165">これを示すには、まず**ネットワークログ**の下部を確認し、最後のアクティビティを記録します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-165">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span></span>  
1.  <span data-ttu-id="45d2e-166">次に、デモの [**データの取得**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-166">Now, select the **Get Data** button in the demo.</span></span>  
1.  <span data-ttu-id="45d2e-167">もう一度**ネットワークログ**の下部を確認します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-167">Look at the bottom of the **Network Log** again.</span></span>  <span data-ttu-id="45d2e-168">という新しいリソースが表示され `getstarted.json` ます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-168">You should see a new resource called `getstarted.json`.</span></span>  <span data-ttu-id="45d2e-169">[**データの取得**] ボタンを選択すると、ページによってこのファイルが要求されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-169">Selecting the **Get Data** button caused the page to request this file.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-170">図 6</span><span class="sxs-lookup"><span data-stu-id="45d2e-170">Figure 6</span></span>  
    > <span data-ttu-id="45d2e-171">ネットワークログの新しいリソース</span><span class="sxs-lookup"><span data-stu-id="45d2e-171">A new resource in the Network Log</span></span>  
    > <span data-ttu-id="45d2e-172">![ネットワークログの新しいリソース][ImagesTutorialRuntime]</span><span class="sxs-lookup"><span data-stu-id="45d2e-172">![A new resource in the Network Log][ImagesTutorialRuntime]</span></span>  

## <span data-ttu-id="45d2e-173">詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="45d2e-173">Show more information</span></span>   

<span data-ttu-id="45d2e-174">ネットワークログの列は構成可能です。</span><span class="sxs-lookup"><span data-stu-id="45d2e-174">The columns of the Network Log are configurable.</span></span>  <span data-ttu-id="45d2e-175">使用していない列を非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-175">You may hide columns that you are not using.</span></span>  
<span data-ttu-id="45d2e-176">既定で非表示になっている列も数多く用意されています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-176">There are also many columns that are hidden by default which you may find useful.</span></span>  

1.  <span data-ttu-id="45d2e-177">ネットワークログテーブルのヘッダーを右クリックし、[**ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-177">Right-click the header of the Network Log table and select **Domain**.</span></span>  <span data-ttu-id="45d2e-178">各リソースのドメインが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="45d2e-178">The domain of each resource is now shown.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-179">図 7</span><span class="sxs-lookup"><span data-stu-id="45d2e-179">Figure 7</span></span>  
    > <span data-ttu-id="45d2e-180">ドメイン列を有効にする</span><span class="sxs-lookup"><span data-stu-id="45d2e-180">Enabling the Domain column</span></span>  
    > <span data-ttu-id="45d2e-181">![Domain 列を有効にする][ImagesTutorialDomain]</span><span class="sxs-lookup"><span data-stu-id="45d2e-181">![Enabling the Domain column][ImagesTutorialDomain]</span></span>  
    
    > [!TIP]
    > <span data-ttu-id="45d2e-182">[**名前**列のセルの上にマウスポインターを置くと、リソースの完全な URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-182">See the full URL of a resource by hovering over the cell in the **Name** column.</span></span>  

## <span data-ttu-id="45d2e-183">低速ネットワーク接続のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="45d2e-183">Simulate a slower network connection</span></span>   

<span data-ttu-id="45d2e-184">サイトの構築に使用するコンピューターのネットワーク接続は、おそらく、ユーザーのモバイルデバイスのネットワーク接続よりも高速です。</span><span class="sxs-lookup"><span data-stu-id="45d2e-184">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span></span>  <span data-ttu-id="45d2e-185">ページを調整することによって、モバイルデバイスでページが読み込まれるまでの時間を把握することができます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-185">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span></span>  

1.  <span data-ttu-id="45d2e-186">[**調整**] ドロップダウンを選択します。これは、既定で [**オンライン**] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-186">Select the **Throttling** dropdown, which is set to **Online** by default.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-187">図 8</span><span class="sxs-lookup"><span data-stu-id="45d2e-187">Figure 8</span></span>  
    > <span data-ttu-id="45d2e-188">調整を有効にする</span><span class="sxs-lookup"><span data-stu-id="45d2e-188">Enabling throttling</span></span>  
    > <span data-ttu-id="45d2e-189">![調整を有効にする][ImagesTutorialThrottling]</span><span class="sxs-lookup"><span data-stu-id="45d2e-189">![Enabling throttling][ImagesTutorialThrottling]</span></span>  
    
1.  <span data-ttu-id="45d2e-190">[**低速 3g**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-190">Select **Slow 3G**.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-191">図 9</span><span class="sxs-lookup"><span data-stu-id="45d2e-191">Figure 9</span></span>  
    > <span data-ttu-id="45d2e-192">低速3G の選択</span><span class="sxs-lookup"><span data-stu-id="45d2e-192">Selecting Slow 3G</span></span>  
    > <span data-ttu-id="45d2e-193">![低速3G の選択][ImagesTutorialSlow3G]</span><span class="sxs-lookup"><span data-stu-id="45d2e-193">![Selecting Slow 3G][ImagesTutorialSlow3G]</span></span>  
    
1.  <span data-ttu-id="45d2e-194">長押しして、[**リロード** ![ ] をクリックし、 ][ImageRefreshIcon] [**キャッシュを空**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-194">Long-press **Reload** ![Reload][ImageRefreshIcon] and then select **Empty Cache And Hard Reload**.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-195">図 10</span><span class="sxs-lookup"><span data-stu-id="45d2e-195">Figure 10</span></span>  
    > <span data-ttu-id="45d2e-196">空のキャッシュとハードリロード</span><span class="sxs-lookup"><span data-stu-id="45d2e-196">Empty Cache And Hard Reload</span></span>  
    > <span data-ttu-id="45d2e-197">![空のキャッシュとハードリロード][ImagesTutorialHardReload]</span><span class="sxs-lookup"><span data-stu-id="45d2e-197">![Empty Cache And Hard Reload][ImagesTutorialHardReload]</span></span>  
    
    <span data-ttu-id="45d2e-198">繰り返しアクセスした場合、ブラウザーは通常[キャッシュ][MDNHTTPCache]の一部のファイルを提供します。これにより、ページの読み込みが高速化されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-198">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache] , which speeds up the page load.</span></span>  <span data-ttu-id="45d2e-199">**空のキャッシュとハードリロード**は、ブラウザーがすべてのリソースについてネットワークにアクセスすることを強制します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-199">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span></span>  <span data-ttu-id="45d2e-200">これは、初めてのユーザーがページの読み込みを体験する方法を確認する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="45d2e-200">This is helpful when you want to see how a first-time visitor experiences a page load.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="45d2e-201">**空のキャッシュと "Hard Reload** " ワークフローは、devtools が開いている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-201">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span></span>  

## <span data-ttu-id="45d2e-202">スクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="45d2e-202">Capture screenshots</span></span>   

<span data-ttu-id="45d2e-203">スクリーンショットを使用すると、ページの読み込み中にページがどのように表示されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-203">Screenshots let you see how a page looked over time while it was loading.</span></span>  

1.  <span data-ttu-id="45d2e-204">[ ![ ネットワーク設定] を選択 ][ImageSettingsIcon] し、[**スクリーンショットのキャプチャ**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-204">Select ![Network settings][ImageSettingsIcon] and select the **Capture screenshots** checkbox.</span></span>
1.  <span data-ttu-id="45d2e-205">**空のキャッシュとハードリロード**ワークフローを使用して、もう一度ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-205">Reload the page again via the **Empty Cache And Hard Reload** workflow.</span></span>  <span data-ttu-id="45d2e-206">この方法について事前に確認が必要な場合は[、「低速接続をシミュレート](#simulate-a-slower-network-connection)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d2e-206">See [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span></span>  
    <span data-ttu-id="45d2e-207">スクリーンショットウィンドウには、読み込み処理中のさまざまなポイントでページがどのように表示されるかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-207">The Screenshots pane provides thumbnails of how the page looked at various points during the loading process.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-208">図 11</span><span class="sxs-lookup"><span data-stu-id="45d2e-208">Figure 11</span></span>  
    > <span data-ttu-id="45d2e-209">ページの読み込みのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="45d2e-209">Screenshots of the page load</span></span>  
    > <span data-ttu-id="45d2e-210">![ページの読み込みのスクリーンショット][ImagesTutorialAllScreenshots]</span><span class="sxs-lookup"><span data-stu-id="45d2e-210">![Screenshots of the page load][ImagesTutorialAllScreenshots]</span></span>  

1.  <span data-ttu-id="45d2e-211">最初のサムネイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-211">Select the first thumbnail.</span></span>  <span data-ttu-id="45d2e-212">DevTools は、現時点で発生していたネットワークアクティビティを示しています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-212">DevTools shows you what network activity was occurring at that moment in time.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-213">図 12</span><span class="sxs-lookup"><span data-stu-id="45d2e-213">Figure 12</span></span>  
    > <span data-ttu-id="45d2e-214">最初のスクリーンショットで発生したネットワークアクティビティ</span><span class="sxs-lookup"><span data-stu-id="45d2e-214">The network activity that was happening during the first screenshot</span></span>  
    > <span data-ttu-id="45d2e-215">![最初のスクリーンショットで発生したネットワークアクティビティ][ImagesTutorialFirstScreenshot]</span><span class="sxs-lookup"><span data-stu-id="45d2e-215">![The network activity that was happening during the first screenshot][ImagesTutorialFirstScreenshot]</span></span>  

1.  <span data-ttu-id="45d2e-216">[ ![ ネットワーク設定] を ][ImageSettingsIcon] もう一度選択し、[**スクリーンショットのキャプチャ**] チェックボックスをオフにして、スクリーンショットウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-216">Select ![Network settings][ImageSettingsIcon] again and deselect the **Capture screenshots** checkbox to close the Screenshots pane.</span></span>
1.  <span data-ttu-id="45d2e-217">ページをもう一度読み込みます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-217">Reload the page again.</span></span>  

## <span data-ttu-id="45d2e-218">リソースの詳細を調べる</span><span class="sxs-lookup"><span data-stu-id="45d2e-218">Inspect the details of the resource</span></span>   

<span data-ttu-id="45d2e-219">詳細については、リソースを選択してください。</span><span class="sxs-lookup"><span data-stu-id="45d2e-219">Select a resource to learn more information about it.</span></span>  <span data-ttu-id="45d2e-220">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="45d2e-220">Try it now:</span></span>  

1.  <span data-ttu-id="45d2e-221">を選択し `getstarted.html` ます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-221">Select `getstarted.html`.</span></span>  <span data-ttu-id="45d2e-222">[**ヘッダー** ] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-222">The **Headers** tab is shown.</span></span>  <span data-ttu-id="45d2e-223">このタブを使用して、HTTP ヘッダーを検査します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-223">Use this tab to inspect HTTP headers.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-224">図 13</span><span class="sxs-lookup"><span data-stu-id="45d2e-224">Figure 13</span></span>  
    > <span data-ttu-id="45d2e-225">[ヘッダー] タブ</span><span class="sxs-lookup"><span data-stu-id="45d2e-225">The Headers tab</span></span>  
    > <span data-ttu-id="45d2e-226">![ヘッダー] タブ[ImagesTutorialHeaders]</span><span class="sxs-lookup"><span data-stu-id="45d2e-226">![The Headers tab][ImagesTutorialHeaders]</span></span>  
    
1.  <span data-ttu-id="45d2e-227">[**プレビュー** ] タブを選択します。 HTML の基本的なレンダリングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-227">Select the **Preview** tab.  A basic rendering of the HTML is shown.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-228">図 14</span><span class="sxs-lookup"><span data-stu-id="45d2e-228">Figure 14</span></span>  
    > <span data-ttu-id="45d2e-229">[プレビュー] タブ</span><span class="sxs-lookup"><span data-stu-id="45d2e-229">The Preview tab</span></span>  
    > <span data-ttu-id="45d2e-230">![プレビュー] タブ[ImagesTutorialPreview]</span><span class="sxs-lookup"><span data-stu-id="45d2e-230">![The Preview tab][ImagesTutorialPreview]</span></span>  

     <span data-ttu-id="45d2e-231">このタブは、API が HTML でエラーコードを返す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="45d2e-231">This tab is helpful when an API returns an error code in HTML.</span></span>  <span data-ttu-id="45d2e-232">HTML ソースコードよりもレンダリングされた HTML を読みやすくしたり、画像を検査したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-232">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span></span>  

1.  <span data-ttu-id="45d2e-233">[**応答**] タブを選択します。 HTML ソースコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-233">Select the **Response** tab.  The HTML source code is shown.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-234">図 15</span><span class="sxs-lookup"><span data-stu-id="45d2e-234">Figure 15</span></span>  
    > <span data-ttu-id="45d2e-235">[応答] タブ</span><span class="sxs-lookup"><span data-stu-id="45d2e-235">The Response tab</span></span>  
    > <span data-ttu-id="45d2e-236">![返信] タブ[ImagesTutorialResponse]</span><span class="sxs-lookup"><span data-stu-id="45d2e-236">![The Response tab][ImagesTutorialResponse]</span></span>  
    
    > [!TIP]
    > <span data-ttu-id="45d2e-237">ファイルが縮小されたときに、 **Format** [ ![ 返信] タブの下部にある [書式の書式設定] を選ぶと、 ][ImageFormatIcon] ファイルの内容が読みやすくなります。 **Response**</span><span class="sxs-lookup"><span data-stu-id="45d2e-237">When a file is minified, selecting the **Format** ![Format][ImageFormatIcon] button at the bottom of the **Response** tab re-formats the contents of the file for readability.</span></span>  

1.  <span data-ttu-id="45d2e-238">[**タイミング**] タブを選択します。 このリソースのネットワークアクティビティの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-238">Select the **Timing** tab.  A breakdown of the network activity for this resource is shown.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-239">図 16</span><span class="sxs-lookup"><span data-stu-id="45d2e-239">Figure 16</span></span>  
    > <span data-ttu-id="45d2e-240">[タイミング] タブ</span><span class="sxs-lookup"><span data-stu-id="45d2e-240">The Timing tab</span></span>  
    > <span data-ttu-id="45d2e-241">![タイミング] タブ[ImagesTutorialTiming]</span><span class="sxs-lookup"><span data-stu-id="45d2e-241">![The Timing tab][ImagesTutorialTiming]</span></span>  

1.  <span data-ttu-id="45d2e-242">[閉じる] を**選択し** ![ ][ImageCloseIcon] て、もう一度ネットワークログを表示します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-242">Select **Close** ![Close][ImageCloseIcon] to view the Network Log again.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-243">図 17</span><span class="sxs-lookup"><span data-stu-id="45d2e-243">Figure 17</span></span>  
    > <span data-ttu-id="45d2e-244">[閉じる] ボタン</span><span class="sxs-lookup"><span data-stu-id="45d2e-244">The Close button</span></span>  
    > <span data-ttu-id="45d2e-245">![閉じる] ボタン[ImagesTutorialCloseTiming]</span><span class="sxs-lookup"><span data-stu-id="45d2e-245">![The Close button][ImagesTutorialCloseTiming]</span></span>  

## <span data-ttu-id="45d2e-246">ネットワークのヘッダーと返信を検索する</span><span class="sxs-lookup"><span data-stu-id="45d2e-246">Search network headers and responses</span></span>   

<span data-ttu-id="45d2e-247">特定の文字列または正規表現について、すべてのリソースの HTTP ヘッダーと応答を検索する必要がある場合は、[**検索**] ウィンドウを使用します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-247">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span></span>  

<span data-ttu-id="45d2e-248">たとえば、リソースが適切な**キャッシュポリシー**を使っていることを確認する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-248">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span></span>  

<!--TODO: add cache policies section when available  -->

1.  <span data-ttu-id="45d2e-249">[**検索**検索] を選び ![ ][ImageSearchIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-249">Select **Search** ![Search][ImageSearchIcon].</span></span>  <span data-ttu-id="45d2e-250">[検索] ウィンドウがネットワークログの左側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-250">The Search pane opens to the left of the Network log.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-251">図18</span><span class="sxs-lookup"><span data-stu-id="45d2e-251">Figure 18</span></span>  
    > <span data-ttu-id="45d2e-252">[検索] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="45d2e-252">The Search pane</span></span>  
    > <span data-ttu-id="45d2e-253">![検索ウィンドウ][ImagesTutorialSearch]</span><span class="sxs-lookup"><span data-stu-id="45d2e-253">![The Search pane][ImagesTutorialSearch]</span></span>  

1.  <span data-ttu-id="45d2e-254">入力 `Cache-Control` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-254">Type `Cache-Control` and press `Enter`.</span></span>  <span data-ttu-id="45d2e-255">[検索] ウィンドウには、 `Cache-Control` リソースヘッダーまたはコンテンツ内で見つかったすべてのインスタンスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-255">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-256">図19</span><span class="sxs-lookup"><span data-stu-id="45d2e-256">Figure 19</span></span>  
    > <span data-ttu-id="45d2e-257">検索結果</span><span class="sxs-lookup"><span data-stu-id="45d2e-257">Search results for</span></span> `Cache-Control`  
    > <span data-ttu-id="45d2e-258">![キャッシュの検索結果][ImagesTutorialResults]</span><span class="sxs-lookup"><span data-stu-id="45d2e-258">![Search results for Cache-Control][ImagesTutorialResults]</span></span>  

1.  <span data-ttu-id="45d2e-259">結果を選択すると、結果が見つかったリソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-259">Select a result to view the resource in which the result was found.</span></span>  <span data-ttu-id="45d2e-260">リソースの詳細が表示されている場合は、結果を選択して直接移動します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-260">If you are looking at the details of the resource, select a result to go directly to it.</span></span>  <span data-ttu-id="45d2e-261">たとえば、ヘッダーで検索されたクエリの場合、[ヘッダー] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-261">For example, if the query was found in a header, the Headers tab opens.</span></span>   <span data-ttu-id="45d2e-262">コンテンツ内にクエリが見つかった場合は、[**応答**] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-262">If the query was found in content, the **Response** tab opens.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-263">図20</span><span class="sxs-lookup"><span data-stu-id="45d2e-263">Figure 20</span></span>  
    > <span data-ttu-id="45d2e-264">[ヘッダー] タブで強調表示された検索結果</span><span class="sxs-lookup"><span data-stu-id="45d2e-264">A search result highlighted in the Headers tab</span></span>  
    > <span data-ttu-id="45d2e-265">![ヘッダー] タブで強調表示された検索結果[ImagesTutorialCache]</span><span class="sxs-lookup"><span data-stu-id="45d2e-265">![A search result highlighted in the Headers tab][ImagesTutorialCache]</span></span>  
    
1.  <span data-ttu-id="45d2e-266">[検索] ウィンドウと [ヘッダー] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-266">Close the Search pane and the Headers tab.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-267">図21</span><span class="sxs-lookup"><span data-stu-id="45d2e-267">Figure 21</span></span>  
    > <span data-ttu-id="45d2e-268">[閉じる] ボタン</span><span class="sxs-lookup"><span data-stu-id="45d2e-268">The Close buttons</span></span>  
    > <span data-ttu-id="45d2e-269">![閉じる] ボタン[ImagesTutorialCloseButtons]</span><span class="sxs-lookup"><span data-stu-id="45d2e-269">![The Close buttons][ImagesTutorialCloseButtons]</span></span>  
    
## <span data-ttu-id="45d2e-270">リソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="45d2e-270">Filter resources</span></span>   

<span data-ttu-id="45d2e-271">DevTools には、タスクに関連していないリソースをフィルター処理するための多数のワークフローが用意されています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-271">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span></span>  

> ##### <span data-ttu-id="45d2e-272">図22</span><span class="sxs-lookup"><span data-stu-id="45d2e-272">Figure 22</span></span>  
> <span data-ttu-id="45d2e-273">[フィルター] ツールバー</span><span class="sxs-lookup"><span data-stu-id="45d2e-273">The Filters toolbar</span></span>  
> <span data-ttu-id="45d2e-274">![フィルター] ツールバー[ImagesTutorialFilters]</span><span class="sxs-lookup"><span data-stu-id="45d2e-274">![The Filters toolbar][ImagesTutorialFilters]</span></span>  

<span data-ttu-id="45d2e-275">[**フィルター** ] ツールバーは、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-275">The **Filters** toolbar should be enabled by default.</span></span>  <span data-ttu-id="45d2e-276">そうでなければ：</span><span class="sxs-lookup"><span data-stu-id="45d2e-276">If not:</span></span>  

1.  <span data-ttu-id="45d2e-277">[**フィルターフィルター] を選択**し ![ ][ImageFilterIcon] て表示します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-277">Select **Filter** ![Filter][ImageFilterIcon] to show it.</span></span>  

### <span data-ttu-id="45d2e-278">文字列、正規表現、またはプロパティによるフィルター処理</span><span class="sxs-lookup"><span data-stu-id="45d2e-278">Filter by string, regular expression, or property</span></span>   

<span data-ttu-id="45d2e-279">**フィルター**テキストボックスでは、さまざまな種類のフィルターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-279">The **Filter** text box supports many different types of filtering.</span></span>  

1.  <span data-ttu-id="45d2e-280">`png`[**フィルター** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-280">Type `png` into the **Filter** text box.</span></span>  <span data-ttu-id="45d2e-281">テキストが含まれているファイルのみ `png` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-281">Only the files that contain the text `png` are shown.</span></span>  <span data-ttu-id="45d2e-282">この場合、フィルターに一致するファイルは PNG 画像のみです。</span><span class="sxs-lookup"><span data-stu-id="45d2e-282">In this case the only files that match the filter are the PNG images.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-283">図23</span><span class="sxs-lookup"><span data-stu-id="45d2e-283">Figure 23</span></span>  
    > <span data-ttu-id="45d2e-284">文字列フィルター</span><span class="sxs-lookup"><span data-stu-id="45d2e-284">A string filter</span></span>  
    > <span data-ttu-id="45d2e-285">![文字列フィルター][ImagesTutorialPNG]</span><span class="sxs-lookup"><span data-stu-id="45d2e-285">![A string filter][ImagesTutorialPNG]</span></span>  

1.  <span data-ttu-id="45d2e-286">「`/.*\.[cj]s+$/`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-286">Type `/.*\.[cj]s+$/`.</span></span>  <span data-ttu-id="45d2e-287">DevTools では、末尾が a または a の後に1つ以上の文字が続いているファイル名でリソースをフィルター処理 `j` `c` `s` します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-287">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-288">図24</span><span class="sxs-lookup"><span data-stu-id="45d2e-288">Figure 24</span></span>  
    > <span data-ttu-id="45d2e-289">正規表現フィルター</span><span class="sxs-lookup"><span data-stu-id="45d2e-289">A regular expression filter</span></span>  
    > <span data-ttu-id="45d2e-290">![正規表現フィルター][ImagesTutorialRegEx]</span><span class="sxs-lookup"><span data-stu-id="45d2e-290">![A regular expression filter][ImagesTutorialRegEx]</span></span>  
    
1.  <span data-ttu-id="45d2e-291">「`-main.css`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-291">Type `-main.css`.</span></span>  <span data-ttu-id="45d2e-292">DevTools でフィルター処理 `main.css` します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-292">DevTools filters out `main.css`.</span></span>  <span data-ttu-id="45d2e-293">他のファイルがそのパターンに一致した場合は、それらもフィルターで除外されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-293">If any other file matched the pattern they would also be filtered out.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-294">図25</span><span class="sxs-lookup"><span data-stu-id="45d2e-294">Figure 25</span></span>  
    > <span data-ttu-id="45d2e-295">ネガティブフィルター</span><span class="sxs-lookup"><span data-stu-id="45d2e-295">A negative filter</span></span>  
    > <span data-ttu-id="45d2e-296">![ネガティブフィルター][ImagesTutorialNegative]</span><span class="sxs-lookup"><span data-stu-id="45d2e-296">![A negative filter][ImagesTutorialNegative]</span></span>  
    
1.  <span data-ttu-id="45d2e-297">`domain:cdn.glitch.com`[**フィルター** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-297">Type `domain:cdn.glitch.com` into the **Filter** text box.</span></span>  <span data-ttu-id="45d2e-298">DevTools は、このドメインと一致しない URL のリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-298">DevTools filters out any resource with a URL that does not match this domain.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-299">図26</span><span class="sxs-lookup"><span data-stu-id="45d2e-299">Figure 26</span></span>  
    > <span data-ttu-id="45d2e-300">プロパティフィルター</span><span class="sxs-lookup"><span data-stu-id="45d2e-300">A property filter</span></span>  
    > <span data-ttu-id="45d2e-301">![プロパティフィルター][ImagesTutorialProperty]</span><span class="sxs-lookup"><span data-stu-id="45d2e-301">![A property filter][ImagesTutorialProperty]</span></span>  

    <span data-ttu-id="45d2e-302">フィルター処理可能なプロパティの完全なリストについては、「[プロパティ別に要求をフィルター処理][DevtoolsReferenceProperty]する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45d2e-302">See [Filter requests by properties][DevtoolsReferenceProperty] for the full list of filterable properties.</span></span>  
    
    
1.  <span data-ttu-id="45d2e-303">任意のテキストの**フィルター**テキストボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-303">Clear the **Filter** text box of any text.</span></span>  

### <span data-ttu-id="45d2e-304">リソースの種類でフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="45d2e-304">Filter by resource type</span></span>   

<span data-ttu-id="45d2e-305">スタイルシートなど、特定の種類のファイルにフォーカスを移動するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="45d2e-305">To focus in on a certain type of file, such as stylesheets:</span></span>  

1.  <span data-ttu-id="45d2e-306">[ **CSS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-306">Select **CSS**.</span></span>  <span data-ttu-id="45d2e-307">その他のすべての種類のファイルはフィルターで除外されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-307">All other file types are filtered out.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-308">図27</span><span class="sxs-lookup"><span data-stu-id="45d2e-308">Figure 27</span></span>  
    > <span data-ttu-id="45d2e-309">CSS ファイルのみを表示する</span><span class="sxs-lookup"><span data-stu-id="45d2e-309">Showing CSS files only</span></span>  
    > <span data-ttu-id="45d2e-310">![CSS ファイルのみ表示][ImagesTutorialCSS]</span><span class="sxs-lookup"><span data-stu-id="45d2e-310">![Showing CSS files only][ImagesTutorialCSS]</span></span>  
    
1.  <span data-ttu-id="45d2e-311">スクリプトも表示するに `Control` は、\ (Windows \) または `Command` \ (macOS \) を保持し、[ **JS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-311">To also see scripts, hold `Control` \(Windows\) or `Command` \(macOS\) and then select **JS**.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-312">図28</span><span class="sxs-lookup"><span data-stu-id="45d2e-312">Figure 28</span></span>  
    > <span data-ttu-id="45d2e-313">CSS と JS ファイルのみを表示する</span><span class="sxs-lookup"><span data-stu-id="45d2e-313">Showing CSS and JS files only</span></span>  
    > <span data-ttu-id="45d2e-314">![CSS と JS ファイルのみを表示します][ImagesTutorialCSSJS]</span><span class="sxs-lookup"><span data-stu-id="45d2e-314">![Showing CSS and JS files only][ImagesTutorialCSSJS]</span></span>  
    
1.  <span data-ttu-id="45d2e-315">[**すべて**] を選択してフィルターを削除し、すべてのリソースをもう一度表示します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-315">Select **All** to remove the filters and see all resources again.</span></span>  

<span data-ttu-id="45d2e-316">「他のフィルター処理ワークフローの[フィルター要求][DevtoolsNetworkReferenceFilter]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d2e-316">See [Filter requests][DevtoolsNetworkReferenceFilter] for other filtering workflows.</span></span>  

## <span data-ttu-id="45d2e-317">リクエストをブロック</span><span class="sxs-lookup"><span data-stu-id="45d2e-317">Block requests</span></span>   

<span data-ttu-id="45d2e-318">ページリソースの一部が利用できない場合、ページはどのように表示され、どのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="45d2e-318">How does a page look and behave when some of the page resources are not available?</span></span>  <span data-ttu-id="45d2e-319">完全に失敗したか、まだ機能していますか?</span><span class="sxs-lookup"><span data-stu-id="45d2e-319">Does it fail completely, or is it still somewhat functional?</span></span>  <span data-ttu-id="45d2e-320">確認要求をブロックする:</span><span class="sxs-lookup"><span data-stu-id="45d2e-320">Block requests to find out:</span></span>  

1.  <span data-ttu-id="45d2e-321">`Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-321">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-322">図29</span><span class="sxs-lookup"><span data-stu-id="45d2e-322">Figure 29</span></span>  
    > <span data-ttu-id="45d2e-323">コマンドメニュー</span><span class="sxs-lookup"><span data-stu-id="45d2e-323">The Command Menu</span></span>  
    > <span data-ttu-id="45d2e-324">![コマンドメニュー][ImagesTutorialCommandMenu]</span><span class="sxs-lookup"><span data-stu-id="45d2e-324">![The Command Menu][ImagesTutorialCommandMenu]</span></span>  
    
1.  <span data-ttu-id="45d2e-325">「」と入力し `block` 、[**要求ブロックの表示**] を選択して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-325">Type `block`, select **Show Request Blocking**, and press `Enter`.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-326">図30</span><span class="sxs-lookup"><span data-stu-id="45d2e-326">Figure 30</span></span>  
    > <span data-ttu-id="45d2e-327">リクエストブロックの表示</span><span class="sxs-lookup"><span data-stu-id="45d2e-327">Show Request Blocking</span></span>  
    > <span data-ttu-id="45d2e-328">![要求のブロックを表示][ImagesTutorialBlock]</span><span class="sxs-lookup"><span data-stu-id="45d2e-328">![Show Request Blocking][ImagesTutorialBlock]</span></span>  

1.  <span data-ttu-id="45d2e-329">[パターン追加パターンの**追加**] を選択し ![ ][ImageAddIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-329">Select **Add Pattern** ![Add Pattern][ImageAddIcon].</span></span>  
1.  <span data-ttu-id="45d2e-330">「`main.css`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-330">Type `main.css`.</span></span>  
    
    > ##### <span data-ttu-id="45d2e-331">図31</span><span class="sxs-lookup"><span data-stu-id="45d2e-331">Figure 31</span></span>  
    > <span data-ttu-id="45d2e-332">ブロッキング</span><span class="sxs-lookup"><span data-stu-id="45d2e-332">Blocking</span></span> `main.css`  
    > <span data-ttu-id="45d2e-333">![ブロックする][ImagesTutorialAddBlock]</span><span class="sxs-lookup"><span data-stu-id="45d2e-333">![Blocking main.css][ImagesTutorialAddBlock]</span></span>  
    
1.  <span data-ttu-id="45d2e-334">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-334">Select **Add**.</span></span>  
1.  <span data-ttu-id="45d2e-335">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-335">Reload the page.</span></span>  <span data-ttu-id="45d2e-336">期待どおり、メインのスタイルシートがブロックされているため、ページのスタイルが少し messed ます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-336">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="45d2e-337">`main.css`ネットワークログの行。</span><span class="sxs-lookup"><span data-stu-id="45d2e-337">The `main.css` row in the Network Log.</span></span>  <span data-ttu-id="45d2e-338">赤いテキストは、リソースがブロックされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="45d2e-338">The red text means that the resource was blocked.</span></span>
    
    > ##### <span data-ttu-id="45d2e-339">図32</span><span class="sxs-lookup"><span data-stu-id="45d2e-339">Figure 32</span></span>  
    > `main.css` <span data-ttu-id="45d2e-340">がブロックされています</span><span class="sxs-lookup"><span data-stu-id="45d2e-340">has been blocked</span></span>  
    > <span data-ttu-id="45d2e-341">![メイン .css はブロックされています][ImagesTutorialBlockedStyles]</span><span class="sxs-lookup"><span data-stu-id="45d2e-341">![main.css has been blocked][ImagesTutorialBlockedStyles]</span></span>  

1.  <span data-ttu-id="45d2e-342">[**リクエストのブロックを有効にする**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="45d2e-342">Deselect the **Enable request blocking** checkbox.</span></span>  

## <span data-ttu-id="45d2e-343">まとめ</span><span class="sxs-lookup"><span data-stu-id="45d2e-343">Conclusion</span></span>  

<span data-ttu-id="45d2e-344">これでチュートリアルを完了しました。</span><span class="sxs-lookup"><span data-stu-id="45d2e-344">Congratulations, you have completed the tutorial.</span></span>  <span data-ttu-id="45d2e-345">Microsoft Edge DevTools でのネットワークパネルの使い方について説明しました。</span><span class="sxs-lookup"><span data-stu-id="45d2e-345">You now know how to use the Network panel in the Microsoft Edge DevTools!</span></span>






<span data-ttu-id="45d2e-346">ネットワークの[参照][DevtoolsNetworkReference]を確認して、ネットワークアクティビティの調査に関連するその他の devtools 機能を見つけます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-346">Check out the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span></span>  

 



<!-- image links -->  

[ImageAddIcon]: /microsoft-edge/devtools-guide-chromium/media/add-icon.msft.png  
[ImageCloseIcon]: /microsoft-edge/devtools-guide-chromium/media/close-icon.msft.png  
[ImageFilterIcon]: /microsoft-edge/devtools-guide-chromium/media/filter-icon.msft.png  
[ImageFormatIcon]: /microsoft-edge/devtools-guide-chromium/media/format-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  
[ImageScreenshotsIcon]: /microsoft-edge/devtools-guide-chromium/media/screenshots-icon.msft.png  
[ImageSearchIcon]: /microsoft-edge/devtools-guide-chromium/media/search-icon.msft.png  
[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png

[ImagesTutorialDemo]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-inspect-network-activity-demo.msft.png "図 1: デモ"  
<!--[ImagesTutorialWindows]: /microsoft-edge/devtools-guide-chromium/media/network-tutorial/windows.msft.png " old Figure 2: The demo in one window and this tutorial in a different window"  -->  
[ImagesTutorialConsole]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-console.msft.png "図 2: 本体  
[ImagesTutorialDocked]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-console-bottom.msft.png "図 3: ウィンドウの下部にドッキングされている DevTools  
[ImagesTutorialNetwork]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-bottom.msft.png "図 4: ウィンドウの下部にドッキングされている DevTools  
[ImagesTutorialLog]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network.msft.png "図 5: ネットワークログ"  
[ImagesTutorialRuntime]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-new-resource.msft.png "図 6: ネットワークログの新しいリソース  
[ImagesTutorialDomain]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-edit-column.msft.png "図 7: ドメイン列を有効にする"  
[ImagesTutorialThrottling]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-throttling.msft.png "図 8: 調整を有効にする"  
[ImagesTutorialSlow3G]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-throttling-slow-3g.msft.png "図 9: 低速 3G" の選択  
[ImagesTutorialHardReload]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-empty-cache-and-hard-reset.msft.png "図 10: 空のキャッシュとハードリロード"  
[ImagesTutorialAllScreenshots]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-screenshots.msft.png "図 11: ページ読み込みのスクリーンショット"  
[ImagesTutorialFirstScreenshot]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-screenshots-first.msft.png "図 12: 最初のスクリーンショットの間に発生したネットワークアクティビティ  
[ImagesTutorialHeaders]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-headers.msft.png "図 13: [ヘッダー] タブ  
[ImagesTutorialPreview]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-preview.msft.png "図 14: [プレビュー] タブ  
[ImagesTutorialResponse]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-response.msft.png "図 15: [応答] タブ  
[ImagesTutorialTiming]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-timing.msft.png "図 16: [タイミング] タブ  
[ImagesTutorialCloseTiming]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-close-tabs.msft.png "図 17: [閉じる] ボタン  
[ImagesTutorialSearch]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-empty.msft.png "図 18: [検索] ウィンドウ  
[ImagesTutorialResults]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-cache-control.msft.png "図 19: キャッシュコントロールの検索結果  
[ImagesTutorialCache]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-cache-control-headers-response-headers.msft.png "図 20: [ヘッダー] タブで強調表示された検索結果  
[ImagesTutorialCloseButtons]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-close.msft.png "図 21: [閉じる] ボタン  
[ImagesTutorialFilters]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-empty.msft.png "図 22: [フィルター] ツールバー  
[ImagesTutorialPNG]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-png.msft.png "図 23: 文字列フィルター"  
[ImagesTutorialRegEx]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-regex.msft.png "図 24: 正規表現フィルター"  
[ImagesTutorialNegative]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-negative-statement.msft.png "図 25: 負のフィルター"  
[ImagesTutorialProperty]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-property-value.msft.png "図 26: プロパティフィルター"  
[ImagesTutorialCSS]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-file-type-css.msft.png "Figure 27: CSS ファイルのみを表示しています"  
[ImagesTutorialCSSJS]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-file-type-css-js.msft.png "図 28: CSS と JS ファイルのみ表示されます"  
[ImagesTutorialCommandMenu]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-empty.msft.png "図 29: コマンドメニュー  
[ImagesTutorialBlock]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block.msft.png "図 30: ブロック要求の表示"  
[ImagesTutorialAddBlock]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block-add-pattern.msft.png "図 31: メイン .css をブロックする"  
[ImagesTutorialBlockedStyles]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block-main-css.msft.png "図 32: メイン .css はブロックされています"  

<!-- links -->  


<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DevtoolsNetworkReference]: /microsoft-edge/devtools-guide-chromium/network/reference "ネットワーク分析のリファレンス"
[DevtoolsNetworkReferenceFilter]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests "フィルター要求-ネットワーク分析リファレンス"  
[DevtoolsReferenceHideOverview]: /microsoft-edge/devtools-guide-chromium/network/reference#hide-the-overview-pane "概要ウィンドウを非表示にする-ネットワーク分析のリファレンス"
[DevtoolsReferenceProperty]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "プロパティによって要求をフィルター処理する-ネットワーク分析リファレンス"
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  
[DevtoolsSpeedGetStarted]: /microsoft-edge/devtools-guide-chromium/speed/get-started "Microsoft Edge DevTools を使用して Web サイトの速度を最適化する"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "ネットワークアクティビティのデモを検査する"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュMDN"  

> [!NOTE]
> <span data-ttu-id="45d2e-388">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="45d2e-388">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="45d2e-389">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/network/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-389">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="45d2e-391">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="45d2e-391">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
