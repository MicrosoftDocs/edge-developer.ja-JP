---
description: Microsoft Edge DevTools の最も一般的なネットワーク関連機能のチュートリアルです。
title: Microsoft Edge DevTools でネットワーク アクティビティを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a4a552fa9a45267a6ffa4a4e83e7ebc4e1817162
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439697"
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

# <a name="inspect-network-activity-in-microsoft-edge-devtools"></a><span data-ttu-id="9d1e5-104">Microsoft Edge DevTools でネットワーク アクティビティを検査する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-104">Inspect network activity in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="9d1e5-105">これは、最も一般的な DevTools 機能のいくつかの実践的なチュートリアルで、ページのネットワーク アクティビティの検査に関連しています。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-105">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span></span>  

<span data-ttu-id="9d1e5-106">機能を参照する場合は、[ネットワーク参照] [に移動します][DevtoolsNetworkReference]。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-106">If you want to browse features, navigate to [Network Reference][DevtoolsNetworkReference].</span></span>  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <a name="when-to-use-the-network-panel"></a><span data-ttu-id="9d1e5-107">ネットワーク パネルを使用する場合</span><span class="sxs-lookup"><span data-stu-id="9d1e5-107">When to use the Network panel</span></span>  

<span data-ttu-id="9d1e5-108">通常、リソースが予期したとおりにダウンロードまたはアップロードされるようにする必要がある場合にネットワーク パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-108">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span></span>  <span data-ttu-id="9d1e5-109">ネットワーク パネルの最も一般的なユースケースは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-109">The most common use cases for the Network panel are:</span></span>  

*   <span data-ttu-id="9d1e5-110">リソースが実際にすべてアップロードまたはダウンロードされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-110">Making sure that resources are actually being uploaded or downloaded at all.</span></span>  
*   <span data-ttu-id="9d1e5-111">HTTP ヘッダー、コンテンツ、サイズなど、個々のリソースのプロパティを検査する。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-111">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span></span>  
    
<span data-ttu-id="9d1e5-112">ページ読み込みパフォーマンスを向上させる方法を探している場合は、ネットワーク**ツールを使用して開始**してください。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-112">If you are looking for ways to improve page load performance, **do not** start with the **Network** tool.</span></span>  <span data-ttu-id="9d1e5-113">ネットワーク アクティビティに関連しない読み込みパフォーマンスの問題には、さまざまな種類があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-113">There are many types of load performance issues that are not related to network activity.</span></span>  <span data-ttu-id="9d1e5-114">ページを改善する方法についての対象候補が表示されるので、監査パネルから開始します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-114">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span></span>  <span data-ttu-id="9d1e5-115">[Web サイト [の速度の最適化] に移動します][DevtoolsSpeedGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-115">Navigate to [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

## <a name="open-the-network-panel"></a><span data-ttu-id="9d1e5-116">ネットワーク パネルを開く</span><span class="sxs-lookup"><span data-stu-id="9d1e5-116">Open the Network panel</span></span>  

<span data-ttu-id="9d1e5-117">このチュートリアルを最大限に活用するには、デモを開いてデモのページで機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-117">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span></span>  

1.  <span data-ttu-id="9d1e5-118">[デモを開始する][GlitchNetworkGetStarted]を開きます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-118">Open the [Get Started Demo][GlitchNetworkGetStarted].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="デモ" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       <span data-ttu-id="9d1e5-120">デモ</span><span class="sxs-lookup"><span data-stu-id="9d1e5-120">The demo</span></span>  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="The demo in one window and this tutorial in a different window" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="9d1e5-121">[DevTools を開く][DevToolsOpen]には `Control` + `Shift` + `J` 、[\(Windows, Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-121">To [Open DevTools][DevToolsOpen], select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="9d1e5-122">コンソール **ツールが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-122">The **Console** tool opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="コンソール" lightbox="../media/network-glitch-console.msft.png":::
       <span data-ttu-id="9d1e5-124">**コンソール**</span><span class="sxs-lookup"><span data-stu-id="9d1e5-124">The **Console**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9d1e5-125">[ウィンドウの下部に DevTools をドッキング][DevToolsCustomizePlacement]することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-125">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="ウィンドウの下部にドッキングされた DevTools" lightbox="../media/network-glitch-console-bottom.msft.png":::
       <span data-ttu-id="9d1e5-127">ウィンドウの下部にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="9d1e5-127">DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-128">ネットワーク ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-128">Open the **Network** tool.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="ウィンドウの下部にドッキングされた DevTools のコンソール ツール" lightbox="../media/network-glitch-network-bottom.msft.png":::
       <span data-ttu-id="9d1e5-130">ウィンドウの下部にドッキングされた DevTools の**コンソール**ツール</span><span class="sxs-lookup"><span data-stu-id="9d1e5-130">**Console** tool in the DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9d1e5-131">現在、ネットワーク **ツール** は空です。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-131">Right now the **Network** tool is empty.</span></span>  <span data-ttu-id="9d1e5-132">DevTools は、開始された場合のみネットワークアクティビティを記録し、DevTools を開始してからはネットワーク アクティビティは発生しません。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-132">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span></span>  

## <a name="log-network-activity"></a><span data-ttu-id="9d1e5-133">ネットワーク アクティビティをログする</span><span class="sxs-lookup"><span data-stu-id="9d1e5-133">Log network activity</span></span>  

<span data-ttu-id="9d1e5-134">ページによって発生するネットワークアクティビティを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-134">To view the network activity that a page causes:</span></span>  

1.  <span data-ttu-id="9d1e5-135">Web ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-135">Refresh the webpage.</span></span>  <span data-ttu-id="9d1e5-136">ネットワーク パネルでは、**ネットワーク ログ**にすべてのネットワークアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-136">The Network panel logs all network activity in the **Network Log**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="ネットワーク ログ" lightbox="../media/network-glitch-network.msft.png":::
       <span data-ttu-id="9d1e5-138">**ネットワーク ログ**</span><span class="sxs-lookup"><span data-stu-id="9d1e5-138">The **Network Log**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9d1e5-139">**ネットワークログ**の各行は、リソースを表します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-139">Each row of the **Network Log** represents a resource.</span></span>  <span data-ttu-id="9d1e5-140">既定では、リソースは時系列順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-140">By default the resources are listed chronologically.</span></span>  <span data-ttu-id="9d1e5-141">トップリソースは、通常、メインの HTML 文書です。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-141">The top resource is usually the main HTML document.</span></span>  <span data-ttu-id="9d1e5-142">一番下のリソースは、最後にリクエストされたものです。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-142">The bottom resource is whatever was requested last.</span></span>  
    
    <span data-ttu-id="9d1e5-143">各列は、リソースに関する情報を表します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-143">Each column represents information about a resource.</span></span>  <span data-ttu-id="9d1e5-144">前の図では、既定の列が表示されています。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-144">In the previous figure the default columns are displayed.</span></span>  

    *   <span data-ttu-id="9d1e5-145">**状態**。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-145">**Status**.</span></span>  <span data-ttu-id="9d1e5-146">応答用の HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-146">The HTTP status code for response.</span></span>  
    *   <span data-ttu-id="9d1e5-147">**種類**。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-147">**Type**.</span></span>  <span data-ttu-id="9d1e5-148">リソースの種類。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-148">The resource type.</span></span>  
    *   <span data-ttu-id="9d1e5-149">**イニシエーター**。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-149">**Initiator**.</span></span>  <span data-ttu-id="9d1e5-150">リソースによるリクエストの原因。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-150">The cause of the resource request.</span></span>  <span data-ttu-id="9d1e5-151">[イニシエーター] 列のリンクを CHoosing すると、要求の原因となるソース コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-151">CHoosing a link in the Initiator column takes you to the source code that caused the request.</span></span>  
    *   <span data-ttu-id="9d1e5-152">**時刻**。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-152">**Time**.</span></span>  <span data-ttu-id="9d1e5-153">リクエストの期間。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-153">The duration of the request.</span></span>  
    *   <span data-ttu-id="9d1e5-154">**ウォーター フォール**。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-154">**Waterfall**.</span></span>  <span data-ttu-id="9d1e5-155">リクエストの異なるステージのグラフィカル表現。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-155">A graphical representation of the different stages of the request.</span></span>  <span data-ttu-id="9d1e5-156">内訳を表示するには、ウォーターフォールにカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-156">To display a breakdown, hover on a Waterfall.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9d1e5-157">ネットワーク ログの上のグラフは概要と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-157">The graph above the Network Log is called the Overview.</span></span>  <span data-ttu-id="9d1e5-158">このチュートリアルの概要グラフは使用しないため、非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-158">You will not use the Overview graph in this tutorial, so you may hide it.</span></span>  <span data-ttu-id="9d1e5-159">[概要] [ウィンドウを非表示にするに移動します][DevtoolsReferenceHideOverview]。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-159">Navigate to [Hide the Overview pane][DevtoolsReferenceHideOverview].</span></span>
    
1.  <span data-ttu-id="9d1e5-160">DevTools を開くと、ネットワーク ログにネットワークアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-160">After you open DevTools, it records network activity in the Network Log.</span></span>  
    <span data-ttu-id="9d1e5-161">これを実践するには、まず **ネットワーク ログ** の下部を確認し、最後のアクティビティを頭で記録します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-161">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span></span>  
1.  <span data-ttu-id="9d1e5-162">次に、デモで **データ取得** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-162">Now, select the **Get Data** button in the demo.</span></span>  
1.  <span data-ttu-id="9d1e5-163">もう一度 **ネットワーク ログ** の下部を確認します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-163">Look at the bottom of the **Network Log** again.</span></span>  <span data-ttu-id="9d1e5-164">という名前の新しいリソース `getstarted.json` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-164">A new resource named `getstarted.json` is displayed.</span></span>  <span data-ttu-id="9d1e5-165">Web ページでファイルを要求するには、[データの取得] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-165">To cause the webpage to request the file, choose the **Get Data** button.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="ネットワーク ログの新しいリソース" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       <span data-ttu-id="9d1e5-167">**ネットワーク ログ**の新しいリソース</span><span class="sxs-lookup"><span data-stu-id="9d1e5-167">A new resource in the **Network Log**</span></span>  
    :::image-end:::  
    
## <a name="show-more-information"></a><span data-ttu-id="9d1e5-168">詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-168">Show more information</span></span>  

<span data-ttu-id="9d1e5-169">ネットワークログの列は構成可能です。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-169">The columns of the Network Log are configurable.</span></span>  <span data-ttu-id="9d1e5-170">使用していない列を非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-170">You may hide columns that you are not using.</span></span>  
<span data-ttu-id="9d1e5-171">既定では非表示になっていますが、役に立つと思われる列も数多くあります。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-171">There are also many columns that are hidden by default which you may find useful.</span></span>  

1.  <span data-ttu-id="9d1e5-172">ネットワーク ログ テーブルのヘッダーにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[ドメイン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-172">Hover on the header of the Network Log table, open the contextual menu \(right-click\), and choose **Domain**.</span></span>  <span data-ttu-id="9d1e5-173">各リソースのドメインが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-173">The domain of each resource is now shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="ドメインの列を有効にする" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       <span data-ttu-id="9d1e5-175">ドメインの列を有効にする</span><span class="sxs-lookup"><span data-stu-id="9d1e5-175">Enable the Domain column</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="9d1e5-176">リソースの完全な URL を確認するには、[名前] 列のセルにマウス ポインター **を置** きます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-176">To review the full URL of a resource, hover on the cell in the **Name** column.</span></span>  
    
## <a name="simulate-a-slower-network-connection"></a><span data-ttu-id="9d1e5-177">低速ネットワーク接続のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="9d1e5-177">Simulate a slower network connection</span></span>  

<span data-ttu-id="9d1e5-178">サイトの構築に使用するコンピューターのネットワーク接続は、おそらく、ユーザーのモバイルデ バイスのネットワーク接続よりも高速です。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-178">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span></span>  <span data-ttu-id="9d1e5-179">ページを調整して、モバイル デバイスでページが読み込まれるまでの時間を把握することができます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-179">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span></span>  

1.  <span data-ttu-id="9d1e5-180">[調整 **] ドロップダウンを選択** します。これは既定で **[オンライン] に** 設定されています。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-180">Choose the **Throttling** dropdown, which is set to **Online** by default.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="調整を有効にする" lightbox="../media/network-glitch-network-throttling.msft.png":::
       <span data-ttu-id="9d1e5-182">調整を有効にする</span><span class="sxs-lookup"><span data-stu-id="9d1e5-182">Enable throttling</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-183">**スロー (低速) 3G** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-183">Choose **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="[低速 3G] を選択する" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       <span data-ttu-id="9d1e5-185">[低速 3G] を選択する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-185">Choose Slow 3G</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-186">**再読み込み** \(![再読み込み](../media/refresh-icon.msft.png)\) を長押しして **キャッシュを空にして再読み込み** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-186">Long-press **Reload** \(![Reload](../media/refresh-icon.msft.png)\) and then choose **Empty Cache And Hard Reload**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="キャッシュを空にして再読み込み" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **<span data-ttu-id="9d1e5-188">キャッシュを空にして再読み込み</span><span class="sxs-lookup"><span data-stu-id="9d1e5-188">Empty Cache And Hard Reload</span></span>**  
    :::image-end:::  
    
    <span data-ttu-id="9d1e5-189">繰り返しアクセスした場合、ブラウザーは通常 [キャッシュ][MDNHTTPCache] の一部のファイルを提供します。これにより、ページの読み込みが高速化します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-189">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache], which speeds up the page load.</span></span>  <span data-ttu-id="9d1e5-190">**キャッシュを空にして再読み込み** で、ブラウザーは強制的にすべてのリソースのネットワークにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-190">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span></span>  <span data-ttu-id="9d1e5-191">初めての訪問者がページの読み込み方法を表示するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-191">Use it to display how a first-time visitor experiences a page load.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9d1e5-192">**キャッシュを空にして再読み込み** ワークフローは、DevTools を開いている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-192">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span></span>  
    
## <a name="capture-screenshots"></a><span data-ttu-id="9d1e5-193">スクリーンショットをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="9d1e5-193">Capture screenshots</span></span>  

<span data-ttu-id="9d1e5-194">スクリーンショットは、Web ページの読み込み中の時間の表示方法を表示します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-194">Screenshots display how a webpage looks over time while it loads.</span></span>  

1.  <span data-ttu-id="9d1e5-195">[\( ![ Network settings ](../media/settings-icon.msft.png) \) を選択し、[スクリーンショットのキャプチャ] **チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-195">Choose \(![Network settings](../media/settings-icon.msft.png)\) and turn on the **Capture screenshots** checkbox.</span></span>
1.  <span data-ttu-id="9d1e5-196">[空のキャッシュとハードリロード] **ワークフローを使用してページを再び更新** します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-196">Refresh the page again using the **Empty Cache And Hard Reload** workflow.</span></span>  <span data-ttu-id="9d1e5-197">これを行 [う方法に関するリマインダー](#simulate-a-slower-network-connection) が必要な場合は、[低速の接続をシミュレートする] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-197">Navigate to [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span></span>  
    <span data-ttu-id="9d1e5-198">[スクリーンショット] パネルには、読み込みプロセス中にページがさまざまなポイントを見た方法のサムネイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-198">The Screenshots panel provides thumbnails of how the page looked at various points during the loading process.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="ページの読み込みのスクリーンショット" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       <span data-ttu-id="9d1e5-200">ページの読み込みのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="9d1e5-200">Screenshots of the page load</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-201">最初のサムネイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-201">Choose the first thumbnail.</span></span>  <span data-ttu-id="9d1e5-202">DevTools では、その地点で発生しているネットワーク アクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-202">DevTools shows you what network activity was occurring at that moment in time.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="最初のスクリーンショット中に発生したネットワーク アクティビティ" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       <span data-ttu-id="9d1e5-204">最初のスクリーンショット中に発生したネットワーク アクティビティ</span><span class="sxs-lookup"><span data-stu-id="9d1e5-204">The network activity that was happening during the first screenshot</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-205">[\( Network settings \) を再度選択し、[スクリーンショットのキャプチャ] チェック ボックスをオフにして [スクリーンショット ![ ](../media/settings-icon.msft.png) ] ウィンドウを閉じます。 </span><span class="sxs-lookup"><span data-stu-id="9d1e5-205">Choose \(![Network settings](../media/settings-icon.msft.png)\) again and turn off the **Capture screenshots** checkbox to close the Screenshots pane.</span></span>
1.  <span data-ttu-id="9d1e5-206">ページを再び更新します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-206">Refresh the page again.</span></span>  
    
## <a name="inspect-the-details-of-the-resource"></a><span data-ttu-id="9d1e5-207">リソースの詳細を検査する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-207">Inspect the details of the resource</span></span>  

<span data-ttu-id="9d1e5-208">リソースを選択して、そのリソースの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-208">Choose a resource to learn more information about it.</span></span>  <span data-ttu-id="9d1e5-209">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="9d1e5-209">Try it now:</span></span>  

1.  <span data-ttu-id="9d1e5-210">を選択します `getstarted.html` 。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-210">Choose `getstarted.html`.</span></span>  <span data-ttu-id="9d1e5-211">[ **ヘッダー]** パネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-211">The **Headers** panel is shown.</span></span>  <span data-ttu-id="9d1e5-212">このパネルを使用して HTTP ヘッダーを検査します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-212">Use this panel to inspect HTTP headers.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text="[ヘッダー] パネル" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       <span data-ttu-id="9d1e5-214">[ **ヘッダー]** パネル</span><span class="sxs-lookup"><span data-stu-id="9d1e5-214">The **Headers** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-215">[プレビュー] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-215">Choose the **Preview** panel.</span></span>  <span data-ttu-id="9d1e5-216">HTML の基本的なレンダリングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-216">A basic rendering of the HTML is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text="[プレビュー] パネル" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       <span data-ttu-id="9d1e5-218">[ **プレビュー]** パネル</span><span class="sxs-lookup"><span data-stu-id="9d1e5-218">The **Preview** panel</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9d1e5-219">パネルは、API が HTML でエラー コードを返す場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-219">The panel is helpful when an API returns an error code in HTML.</span></span>  <span data-ttu-id="9d1e5-220">HTML ソースコードよりも、または画像を検査する場合よりも、レンダリングされた HTML の方が読みやすいと思われるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-220">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span></span>  

1.  <span data-ttu-id="9d1e5-221">[応答] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-221">Choose the **Response** panel.</span></span>  <span data-ttu-id="9d1e5-222">HTML ソース コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-222">The HTML source code is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="[応答] パネル" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       <span data-ttu-id="9d1e5-224">[ **応答]** パネル</span><span class="sxs-lookup"><span data-stu-id="9d1e5-224">The **Response** panel</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="9d1e5-225">ファイルが minified の場合は、[応答] パネルの下部にある [Format **\(** Format \)] ボタンを選択して、ファイルの内容を読みやすさのために再 ![ ](../media/format-icon.msft.png) フォーマットします。 </span><span class="sxs-lookup"><span data-stu-id="9d1e5-225">When a file is minified, choose the **Format** \(![Format](../media/format-icon.msft.png)\) button at the bottom of the **Response** panel to re-format the contents of the file for readability.</span></span>  
    
1.  <span data-ttu-id="9d1e5-226">[タイミング] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-226">Choose the **Timing** panel.</span></span>  <span data-ttu-id="9d1e5-227">リソースのネットワーク アクティビティの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-227">A breakdown of the network activity for the resource is displayed.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text="[タイミング] パネル" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       <span data-ttu-id="9d1e5-229">[ **タイミング]** パネル</span><span class="sxs-lookup"><span data-stu-id="9d1e5-229">The **Timing** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-230">**閉じる** \(![閉じる](../media/close-icon.msft.png)\) を選択して、もう一度ネットワーク ログを表示します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-230">Choose **Close** \(![Close](../media/close-icon.msft.png)\) to view the Network Log again.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="[閉じる] ボタン" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       <span data-ttu-id="9d1e5-232">**閉じる** ボタン</span><span class="sxs-lookup"><span data-stu-id="9d1e5-232">The **Close** button</span></span>  
    :::image-end:::  
    
## <a name="search-network-headers-and-responses"></a><span data-ttu-id="9d1e5-233">ネットワークのヘッダーと返信を検索する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-233">Search network headers and responses</span></span>  

<span data-ttu-id="9d1e5-234">特定の文字列または正規表現に関するすべてのリソースの HTTP ヘッダーと応答を検索する必要がある場合は、**検索** ウィンドウを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-234">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span></span>  

<span data-ttu-id="9d1e5-235">たとえば、リソースが適切な **キャッシュポリシー** を使用していることを確認する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-235">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span></span>  

<!--TODO: add cache policies section when available  -->

1.  <span data-ttu-id="9d1e5-236">**検索** \(![検索](../media/search-icon.msft.png)\) を選びます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-236">Choose **Search** \(![Search](../media/search-icon.msft.png)\).</span></span>  <span data-ttu-id="9d1e5-237">[検索] ウィンドウがネットワーク ログの左側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-237">The Search pane opens to the left of the Network log.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="[検索] ウィンドウ" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       <span data-ttu-id="9d1e5-239">**検索** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="9d1e5-239">The **Search** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-240">`Cache-Control` を入力して、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-240">Type `Cache-Control` and select `Enter`.</span></span>  <span data-ttu-id="9d1e5-241">[検索] ウィンドウには、リソース ヘッダーまたはコンテンツ内で見つかった `Cache-Control` のすべてのインスタンスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-241">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="キャッシュ コントロールの検索結果" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       <span data-ttu-id="9d1e5-243">検索結果</span><span class="sxs-lookup"><span data-stu-id="9d1e5-243">Search results for</span></span> `Cache-Control`  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-244">結果を選択して、結果が見つかったリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-244">Choose a result to view the resource in which the result was found.</span></span>  <span data-ttu-id="9d1e5-245">リソースの詳細を参照している場合は、結果を選択して直接移動します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-245">If you are looking at the details of the resource, select a result to go directly to it.</span></span>  <span data-ttu-id="9d1e5-246">たとえば、クエリがヘッダーで見つかった場合は、[ヘッダー] **パネルが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-246">For example, if the query was found in a header, the **Headers** panel opens.</span></span>   <span data-ttu-id="9d1e5-247">クエリがコンテンツで見つかった場合は、[応答 **] パネルが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-247">If the query was found in content, the **Response** panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text="[ヘッダー] パネルで強調表示された検索結果" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       <span data-ttu-id="9d1e5-249">[ヘッダー] パネルで強調表示された**検索結果**</span><span class="sxs-lookup"><span data-stu-id="9d1e5-249">A search result highlighted in the **Headers** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-250">[検索] ウィンドウと [ヘッダー] パネル **を閉** じます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-250">Close the Search pane and the **Headers** panel.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="[閉じる] ボタン" lightbox="../media/network-glitch-network-search-close.msft.png":::
       <span data-ttu-id="9d1e5-252">**閉じる** ボタン</span><span class="sxs-lookup"><span data-stu-id="9d1e5-252">The **Close** buttons</span></span>  
    :::image-end:::  
    
## <a name="filter-resources"></a><span data-ttu-id="9d1e5-253">リソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-253">Filter resources</span></span>  

<span data-ttu-id="9d1e5-254">DevTools には、タスクに直接関連していないリソースをフィルター処理する多数のワークフローが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-254">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span></span>  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="[フィルター] ツールバー" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   <span data-ttu-id="9d1e5-256">**フィルター** ツールバー</span><span class="sxs-lookup"><span data-stu-id="9d1e5-256">The **Filters** toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="9d1e5-257">既定 **では、[フィルター** ] ツールバーをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-257">The **Filters** toolbar should be turned on by default.</span></span>  <span data-ttu-id="9d1e5-258">そうでなければ：</span><span class="sxs-lookup"><span data-stu-id="9d1e5-258">If not:</span></span>  

1.  <span data-ttu-id="9d1e5-259">**フィルター** \(![フィルター](../media/filter-icon.msft.png)\) を選んで表示します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-259">Choose **Filter** \(![Filter](../media/filter-icon.msft.png)\) to show it.</span></span>  
    
### <a name="filter-by-string-regular-expression-or-property"></a><span data-ttu-id="9d1e5-260">文字列、正規表現、またはプロパティによってフィルターする</span><span class="sxs-lookup"><span data-stu-id="9d1e5-260">Filter by string, regular expression, or property</span></span>  

<span data-ttu-id="9d1e5-261">**フィルター** テキスト ボックスでは、さまざまな種類のフィルターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-261">The **Filter** text box supports many different types of filtering.</span></span>  

1.  <span data-ttu-id="9d1e5-262">`png` を **フィルター** テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-262">Type `png` into the **Filter** text box.</span></span>  <span data-ttu-id="9d1e5-263">テキスト `png` が含まれているファイルだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-263">Only the files that contain the text `png` are shown.</span></span>  <span data-ttu-id="9d1e5-264">この場合、フィルターに一致するファイルは PNG 画像のみです。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-264">In this case the only files that match the filter are the PNG images.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="文字列フィルター" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       <span data-ttu-id="9d1e5-266">文字列フィルター</span><span class="sxs-lookup"><span data-stu-id="9d1e5-266">A string filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-267">「`/.*\.[cj]s+$/`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-267">Type `/.*\.[cj]s+$/`.</span></span>  <span data-ttu-id="9d1e5-268">DevTools では、末尾が `j` または `c` で終わらず、1つ以上の`s`文字が続いているファイル名で任意のリソースをフィルター処理 します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-268">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="正規表現フィルター" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       <span data-ttu-id="9d1e5-270">正規表現フィルター</span><span class="sxs-lookup"><span data-stu-id="9d1e5-270">A regular expression filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-271">「`-main.css`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-271">Type `-main.css`.</span></span>  <span data-ttu-id="9d1e5-272">DevTools で `main.css` をフィルターします。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-272">DevTools filters out `main.css`.</span></span>  <span data-ttu-id="9d1e5-273">パターンに一致するファイルがある場合は、tit もフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-273">If any file matches the pattern, tit is also filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="ネガティブ フィルター" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       <span data-ttu-id="9d1e5-275">ネガティブ フィルター</span><span class="sxs-lookup"><span data-stu-id="9d1e5-275">A negative filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-276">`domain:cdn.glitch.com` を **フィルター処理** テキスト ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-276">Type `domain:cdn.glitch.com` into the **Filter** text box.</span></span>  <span data-ttu-id="9d1e5-277">DevTools では、このドメインと一致しない URL のリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-277">DevTools filters out any resource with a URL that does not match this domain.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="プロパティ フィルター" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       <span data-ttu-id="9d1e5-279">プロパティ フィルター</span><span class="sxs-lookup"><span data-stu-id="9d1e5-279">A property filter</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9d1e5-280">フィルター可能なプロパティの完全な一覧については、[プロパティで要求 [をフィルター処理する] に移動します][DevtoolsReferenceProperty]。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-280">For the full list of filterable properties, navigate to [Filter requests by properties][DevtoolsReferenceProperty].</span></span>  
    
1.  <span data-ttu-id="9d1e5-281">任意のテキストのテキスト ボックスを **フィルター処理** をクリアします。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-281">Clear the **Filter** text box of any text.</span></span>  
    
### <a name="filter-by-resource-type"></a><span data-ttu-id="9d1e5-282">リソースの種類でフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-282">Filter by resource type</span></span>  

<span data-ttu-id="9d1e5-283">スタイルシートなど、特定の種類のファイルに重点を置く場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-283">To focus in on a certain type of file, such as stylesheets:</span></span>  

1.  <span data-ttu-id="9d1e5-284">**CSS** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-284">Choose **CSS**.</span></span>  <span data-ttu-id="9d1e5-285">その他のすべての種類のファイルはフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-285">All other file types are filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="CSS ファイルのみを表示する" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       <span data-ttu-id="9d1e5-287">CSS ファイルのみを表示する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-287">Show CSS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-288">スクリプトも表示するには `Control` 、\(Windows、Linux\) または `Command` \(macOS\) を選択して保持し **、[JS] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-288">To also display scripts, select and hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose **JS**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="CSS と JS ファイルのみを表示する" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       <span data-ttu-id="9d1e5-290">CSS と JS ファイルのみを表示する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-290">Show CSS and JS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-291">フィルターを削除してすべてのリソースを再度表示するには、[すべて] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-291">To remove the filters and display all resources again, choose **All**.</span></span>  
    
<span data-ttu-id="9d1e5-292">その他のフィルター ワークフローについては、[要求のフィルター [] に移動します][DevtoolsNetworkReferenceFilter]。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-292">For other filtering workflows, navigate to [Filter requests][DevtoolsNetworkReferenceFilter].</span></span>  

## <a name="block-requests"></a><span data-ttu-id="9d1e5-293">リクエストをブロック</span><span class="sxs-lookup"><span data-stu-id="9d1e5-293">Block requests</span></span>  

<span data-ttu-id="9d1e5-294">ページリソースの一部が利用できない場合、ページはどのように表示され、どのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="9d1e5-294">How does a page look and behave when some of the page resources are not available?</span></span>  <span data-ttu-id="9d1e5-295">完全に失敗しましたか? それとも、まだ機能していますか?</span><span class="sxs-lookup"><span data-stu-id="9d1e5-295">Does it fail completely, or is it still somewhat functional?</span></span>  <span data-ttu-id="9d1e5-296">リクエストをブロックして、以下の内容を見つけます:</span><span class="sxs-lookup"><span data-stu-id="9d1e5-296">Block requests to find out:</span></span>  

1.  <span data-ttu-id="9d1e5-297">`Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-297">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="コマンド メニュー" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       <span data-ttu-id="9d1e5-299">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="9d1e5-299">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-300">`block` と入力して、**リクエストのブロックを表示** を選択してから、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-300">Type `block`, choose **Show Request Blocking**, and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="リクエストのブロックを表示" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **<span data-ttu-id="9d1e5-302">リクエストのブロックを表示</span><span class="sxs-lookup"><span data-stu-id="9d1e5-302">Show Request Blocking</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-303">**パターンを追加** \(![パターンを追加](../media/add-icon.msft.png)\) を選びます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-303">Choose **Add Pattern** \(![Add Pattern](../media/add-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="9d1e5-304">「`main.css`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-304">Type `main.css`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="メインの.css をブロックする" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       <span data-ttu-id="9d1e5-306">ブロッキング</span><span class="sxs-lookup"><span data-stu-id="9d1e5-306">Blocking</span></span> `main.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-307">**追加** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-307">Choose **Add**.</span></span>  
1.  <span data-ttu-id="9d1e5-308">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-308">Refresh the page.</span></span>  <span data-ttu-id="9d1e5-309">予想どおり、メインのスタイルシートがブロックされているため、ページのスタイルがあまりよくありません。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-309">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9d1e5-310">ネットワーク ログの `main.css` 行。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-310">The `main.css` row in the Network Log.</span></span>  <span data-ttu-id="9d1e5-311">赤いテキストは、リソースがブロックされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-311">The red text means that the resource was blocked.</span></span>
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="メインの.css がブロックされています" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` <span data-ttu-id="9d1e5-313">ブロックされています</span><span class="sxs-lookup"><span data-stu-id="9d1e5-313">has been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9d1e5-314">**リクエストのブロックを有効にする** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-314">Deselect the **Enable request blocking** checkbox.</span></span>  

## <a name="conclusion"></a><span data-ttu-id="9d1e5-315">まとめ</span><span class="sxs-lookup"><span data-stu-id="9d1e5-315">Conclusion</span></span>  

<span data-ttu-id="9d1e5-316">おめでとうございます。これでチュートリアルは完了です。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-316">Congratulations, you have completed the tutorial.</span></span>  <span data-ttu-id="9d1e5-317">これで、Microsoft Edge DevTools でネットワーク ツールを使用する方法がわかっています。 </span><span class="sxs-lookup"><span data-stu-id="9d1e5-317">You now know how to use the **Network** tool in the Microsoft Edge DevTools!</span></span>

<span data-ttu-id="9d1e5-318">[ネットワーク リファレンス][DevtoolsNetworkReference] に移動して、ネットワーク アクティビティの調査に関連するその他の DevTools 機能を見つけます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-318">Navigate to the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9d1e5-319">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="9d1e5-319">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更 | Microsoft Docs"  
[DevtoolsNetworkReference]: ./reference.md "ネットワーク分析のリファレンス | Microsoft Docs"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "フィルターのリクエスト - ネットワーク分析リファレンス | Microsoft Docs"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "概要ウィンドウを非表示 - ネットワーク分析リファレンス | Microsoft Docs"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "プロパティによるリクエストをフィルター処理 - ネットワーク分析のリファレンス | Microsoft Docs"
[DevToolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Microsoft Edge DevTools を使用して web サイトの速度を最適化 | Microsoft Docs"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "ネットワーク アクティビティのデモを検査 | グリッチ"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュ | MDN"  

> [!NOTE]
> <span data-ttu-id="9d1e5-329">このページの一部は、 [Google によって][GoogleSitePolicies] 作成および共有され、 [クリエイティブ コモンズ 4.0 インターナショナル ライセンス][CCA4IL]で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-329">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9d1e5-330">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-330">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9d1e5-332">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9d1e5-332">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
