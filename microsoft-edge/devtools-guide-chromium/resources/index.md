---
description: フレーム、ドメイン、種類、その他の条件でリソースを整理します。
title: Microsoft Edge DevTools を使用してページ リソースを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 353c36a9d98dac287c3fdaaa3feed2fe3b17cd07
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230776"
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

# <span data-ttu-id="50290-104">Microsoft Edge DevTools を使用してページ リソースを表示する</span><span class="sxs-lookup"><span data-stu-id="50290-104">View page resources with Microsoft Edge DevTools</span></span>  

  

<span data-ttu-id="50290-105">このガイドでは、Microsoft Edge DevTools を使用して Web ページのリソースを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50290-105">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="50290-106">リソースは、ページを正しく表示するために必要なファイルです。</span><span class="sxs-lookup"><span data-stu-id="50290-106">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="50290-107">リソースの例としては、CSS、JavaScript、HTML ファイル、画像があります。</span><span class="sxs-lookup"><span data-stu-id="50290-107">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="50290-108">このガイドでは、Web 開発と Microsoft Edge [][MDNLearnWebDevelopment] [DevTools][MicrosoftEdgeDevTools]の基礎を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="50290-108">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="50290-109">リソースを開く</span><span class="sxs-lookup"><span data-stu-id="50290-109">Open resources</span></span>  

<span data-ttu-id="50290-110">検査するリソースの名前が分かっている場合、コマンド メニューを\*\*\*\* 使用すると、リソースを高速に開く方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="50290-110">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="50290-111">`Control` + `P` \(Windows,Linux\) または `Command` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="50290-111">Select `Control`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="50290-112">[ **ファイルを開く]** ダイアログボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="50290-112">The **Open File** dialog opens.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text="[ファイルを開く] ダイアログ" lightbox="../media/resources-command-menu-empty.msft.png":::
       <span data-ttu-id="50290-114">[ **ファイルを開く]** ダイアログ</span><span class="sxs-lookup"><span data-stu-id="50290-114">The **Open File** dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="50290-115">ドロップダウンからファイルを選択するか、ファイル名の入力を開始し、オートコンプリート ボックスで正しいファイルが強調表示された後 `Enter` で選択します。</span><span class="sxs-lookup"><span data-stu-id="50290-115">Select the file from the dropdown, or start typing the filename and select `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="[ファイルを開く] ダイアログボックスにファイル名を入力する" lightbox="../media/resources-command-menu-file-search.msft.png":::
       <span data-ttu-id="50290-117">[ファイルを開く] ダイアログ **ボックスにファイル名を入力** する</span><span class="sxs-lookup"><span data-stu-id="50290-117">Type a filename in the **Open File** dialog</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="50290-118">[ネットワーク] パネルでリソースを開く</span><span class="sxs-lookup"><span data-stu-id="50290-118">Open resources in the Network panel</span></span>  

<span data-ttu-id="50290-119">[リソースの [詳細を検査する] に移動します][DevtoolsNetworkInspectDetailsResource]。</span><span class="sxs-lookup"><span data-stu-id="50290-119">Navigate to [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="[ネットワーク] パネルでリソースを検査する" lightbox="../media/resources-network-response.msft.png":::
   <span data-ttu-id="50290-121">[ネットワーク] パネルでリソースを **検査** する</span><span class="sxs-lookup"><span data-stu-id="50290-121">Inspect a resource in the **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="50290-122">他のパネルからネットワーク パネルの表示リソースを表示する</span><span class="sxs-lookup"><span data-stu-id="50290-122">Reveal resources in the Network panel from other panels</span></span>  

<span data-ttu-id="50290-123">以下 [の「](#browse-resources) リソースの参照」セクションでは、DevTools UI のさまざまな部分からリソースを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="50290-123">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="50290-124">[ネットワーク] パネルでリソースを検査する\*\*\*\* 場合は、リソースを右クリックし、[ネットワーク] パネルで [表示 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="50290-124">If you ever want to inspect a resource in the **Network** panel, right-click the resource and choose **Reveal in Network panel**.</span></span>  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="ネットワーク パネルでの表示" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **<span data-ttu-id="50290-126">ネットワーク パネルでの表示</span><span class="sxs-lookup"><span data-stu-id="50290-126">Reveal in Network panel</span></span>**  
:::image-end:::  

## <span data-ttu-id="50290-127">リソースを参照する</span><span class="sxs-lookup"><span data-stu-id="50290-127">Browse resources</span></span>  

### <span data-ttu-id="50290-128">[ネットワーク] パネルでリソースを参照する</span><span class="sxs-lookup"><span data-stu-id="50290-128">Browse resources in the Network panel</span></span>  

<span data-ttu-id="50290-129">[ネットワーク アクティビティ [のログ] に移動します][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="50290-129">Navigate to [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="ネットワーク ログのページ リソース" lightbox="../media/resources-network-resources.msft.png":::
   <span data-ttu-id="50290-131">ネットワーク ログの **ページ** リソース</span><span class="sxs-lookup"><span data-stu-id="50290-131">Page resources in the **Network** Log</span></span>  
:::image-end:::  

### <span data-ttu-id="50290-132">ディレクトリで参照</span><span class="sxs-lookup"><span data-stu-id="50290-132">Browse by directory</span></span>  

<span data-ttu-id="50290-133">ディレクトリごとに整理されたページのリソースを表示するには:</span><span class="sxs-lookup"><span data-stu-id="50290-133">To view the resources of a page organized by directory:</span></span>  

1.  <span data-ttu-id="50290-134">[ソース **] タブを** クリックして、[ソース] パネル **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="50290-134">Click the **Sources** tab to open the **Sources** panel.</span></span>  
1.  <span data-ttu-id="50290-135">ページの **リソースを** 表示するには、[ページ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50290-135">Click the **Page** tab to show the resources of the page.</span></span>  <span data-ttu-id="50290-136">[ **ページ] ウィンドウ** が開きます。</span><span class="sxs-lookup"><span data-stu-id="50290-136">The **Page** pane opens.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="ページウィンドウ" lightbox="../media/resources-sources-page-empty.msft.png":::
       <span data-ttu-id="50290-138">**ページ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="50290-138">The **Page** pane</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="50290-139">前の図の明白でない項目の詳細を次に示します。</span><span class="sxs-lookup"><span data-stu-id="50290-139">Here is a breakdown of the non-obvious items in the previous figure.</span></span>  
    
    | <span data-ttu-id="50290-140">ページ アイテム</span><span class="sxs-lookup"><span data-stu-id="50290-140">Page item</span></span> | <span data-ttu-id="50290-141">説明</span><span class="sxs-lookup"><span data-stu-id="50290-141">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="50290-142">メイン ドキュメントの [参照コンテキスト][MDNInlineFrame]。</span><span class="sxs-lookup"><span data-stu-id="50290-142">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="50290-143">ドメイン。</span><span class="sxs-lookup"><span data-stu-id="50290-143">The domain.</span></span>  <span data-ttu-id="50290-144">その下に入れ子になっているすべてのリソースは、そのドメインから提供されます。</span><span class="sxs-lookup"><span data-stu-id="50290-144">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="50290-145">たとえば、ファイルの完全な URL `comlink.global.j` は、おそらく `https://airhorner.com/scripts/comlink.global.js` .</span><span class="sxs-lookup"><span data-stu-id="50290-145">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="50290-146">ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="50290-146">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="50290-147">メイン HTML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="50290-147">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="50290-148">サービス ワーカー ランタイム コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="50290-148">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="50290-149">リソースをクリックしてエディターに表示 **します**。</span><span class="sxs-lookup"><span data-stu-id="50290-149">Click a resource to view it in the **Editor**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="エディターでファイルを表示する" lightbox="../media/resources-sources-page-resource.msft.png":::
       <span data-ttu-id="50290-151">エディターでファイルを表示 **する**</span><span class="sxs-lookup"><span data-stu-id="50290-151">View a file in the **Editor**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="50290-152">ファイル名で参照</span><span class="sxs-lookup"><span data-stu-id="50290-152">Browse by filename</span></span>  

<span data-ttu-id="50290-153">既定では、ページ **ウィンドウは** リソースをディレクトリ別にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="50290-153">By default the **Page** pane groups resources by directory.</span></span>  <span data-ttu-id="50290-154">このグループ化を無効にして、各ドメインのリソースをフラット リストとして表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="50290-154">To disable this grouping and view the resources for each domain as a flat list:</span></span>  

1.  <span data-ttu-id="50290-155">ページ ウィンドウ **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="50290-155">Open the **Page** pane.</span></span>  <span data-ttu-id="50290-156">ディレクトリで [参照に移動します](#browse-by-directory)。</span><span class="sxs-lookup"><span data-stu-id="50290-156">Navigate to [Browse by directory](#browse-by-directory).</span></span>  
1.  <span data-ttu-id="50290-157">[その **他のオプション] を** `...` 選択し、[ **フォルダー別グループ化] を無効にします**。</span><span class="sxs-lookup"><span data-stu-id="50290-157">Choose **More Options** `...` and disable **Group By Folder**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text="[フォルダーでグループ化] オプション" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       <span data-ttu-id="50290-159">[ **フォルダーでグループ化]** オプション</span><span class="sxs-lookup"><span data-stu-id="50290-159">The **Group By Folder** option</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="50290-160">リソースはファイルの種類ごとに整理されています。</span><span class="sxs-lookup"><span data-stu-id="50290-160">Resources are organized by file type.</span></span>  <span data-ttu-id="50290-161">各ファイルの種類内では、リソースはアルファベット順に整理されます。</span><span class="sxs-lookup"><span data-stu-id="50290-161">Within each file type the resources are organized alphabetically.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="フォルダー別グループを無効にした後のページ ウィンドウ" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       <span data-ttu-id="50290-163">フォルダー **別グループ** を無効にした **後のページ ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="50290-163">The **Page** pane after disabling **Group By Folder**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="50290-164">ファイルの種類で参照</span><span class="sxs-lookup"><span data-stu-id="50290-164">Browse by file type</span></span>  

<span data-ttu-id="50290-165">ファイルの種類に基づいてリソースをグループ化するには:</span><span class="sxs-lookup"><span data-stu-id="50290-165">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="50290-166">[アプリケーション] **タブをクリック** します。 [ **アプリケーション]** パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="50290-166">Click the **Application** tab.  The **Application** panel opens.</span></span>  <span data-ttu-id="50290-167">既定では、通常 **、マニフェスト ウィンドウ** が最初に開きます。</span><span class="sxs-lookup"><span data-stu-id="50290-167">By default the **Manifest** pane usually opens first.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="[アプリケーション] パネル" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       <span data-ttu-id="50290-169">[ **アプリケーション]** パネル</span><span class="sxs-lookup"><span data-stu-id="50290-169">The **Application** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="50290-170">フレーム ウィンドウまで **下にスクロール** します。</span><span class="sxs-lookup"><span data-stu-id="50290-170">Scroll down to the **Frames** pane.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="[フレーム] ウィンドウ" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       <span data-ttu-id="50290-172">[ **フレーム]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="50290-172">The **Frames** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="50290-173">必要なセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="50290-173">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="50290-174">リソースをクリックして表示します。</span><span class="sxs-lookup"><span data-stu-id="50290-174">Click a resource to view it.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="[アプリケーション] パネルでリソースを表示する" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       <span data-ttu-id="50290-176">[アプリケーション] パネルでリソース **を表示** する</span><span class="sxs-lookup"><span data-stu-id="50290-176">View a resource in the **Application** panel</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="50290-177">[ネットワーク] パネルで種類別にファイルを参照する</span><span class="sxs-lookup"><span data-stu-id="50290-177">Browse files by type in the Network panel</span></span>  

<span data-ttu-id="50290-178">[リソースの [種類でフィルター] に移動します][DevtoolsNetworkFilterByResourceType]。</span><span class="sxs-lookup"><span data-stu-id="50290-178">Navigate to [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="ネットワーク ログで CSS をフィルター処理する" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   <span data-ttu-id="50290-180">ネットワーク ログで CSS を **フィルター** 処理する</span><span class="sxs-lookup"><span data-stu-id="50290-180">Filter for CSS in the **Network** Log</span></span>  
:::image-end:::  

## <span data-ttu-id="50290-181">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="50290-181">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "リソースの種類によるフィルター - Microsoft Edge DevTools でネットワーク アクティビティを検査する |Microsoft Docs"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "リソースの詳細を検査する - Microsoft Edge DevTools でネットワーク アクティビティを検査する |Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "ネットワーク アクティビティをログに記録する - Microsoft Edge DevTools でネットワーク アクティビティを検査する |Microsoft Docs"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: Inline Frame 要素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Web 開発について |MDN"  

> [!NOTE]
> <span data-ttu-id="50290-188">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="50290-188">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="50290-189">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/resources/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="50290-189">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="50290-191">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="50290-191">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
