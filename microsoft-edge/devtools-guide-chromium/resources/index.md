---
title: Microsoft Edge DevTools でページリソースを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0977d0a9132c19742c3337f9dc0c3e1240508a3d
ms.sourcegitcommit: 4c24edbd1c591914cb4109511534851570a614cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611918"
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





# <span data-ttu-id="09d08-103">Microsoft Edge DevTools でページリソースを表示する</span><span class="sxs-lookup"><span data-stu-id="09d08-103">View Page Resources With Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="09d08-104">このガイドでは、Microsoft Edge DevTools を使って web ページのリソースを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09d08-104">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="09d08-105">リソースは、適切に表示するためにページに必要なファイルです。</span><span class="sxs-lookup"><span data-stu-id="09d08-105">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="09d08-106">リソースの例として、CSS、JavaScript、HTML ファイル、画像などがあります。</span><span class="sxs-lookup"><span data-stu-id="09d08-106">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="09d08-107">このガイドは、 [web 開発][MDNLearnWebDevelopment]と[Microsoft Edge devtools][MicrosoftEdgeDevTools]の基本について理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="09d08-107">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="09d08-108">リソースを開く</span><span class="sxs-lookup"><span data-stu-id="09d08-108">Open resources</span></span>   

<span data-ttu-id="09d08-109">検査するリソースの名前がわかっている場合、[**コマンド] メニュー**でリソースをすばやく開くことができます。</span><span class="sxs-lookup"><span data-stu-id="09d08-109">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="09d08-110">`Control` + `P` \ (Windows \) または `Command` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="09d08-110">Press `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="09d08-111">[**ファイルを開く**] ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="09d08-111">The **Open File** dialog opens.</span></span>  
    
    > ##### <span data-ttu-id="09d08-112">図 1</span><span class="sxs-lookup"><span data-stu-id="09d08-112">Figure 1</span></span>  
    > <span data-ttu-id="09d08-113">[**ファイルを開く**] ダイアログボックス</span><span class="sxs-lookup"><span data-stu-id="09d08-113">The **Open File** dialog</span></span>  
    > ![[ファイルを開く] ダイアログボックス][ImageOpenFile]  
    
1.  <span data-ttu-id="09d08-115">ドロップダウンからファイルを選択するか、ファイル名の入力を開始し、[ `Enter` オートコンプリート] ボックスで正しいファイルが強調表示されたら、1回押します。</span><span class="sxs-lookup"><span data-stu-id="09d08-115">Select the file from the dropdown, or start typing the filename and press `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    > ##### <span data-ttu-id="09d08-116">図 2</span><span class="sxs-lookup"><span data-stu-id="09d08-116">Figure 2</span></span>  
    > <span data-ttu-id="09d08-117">[**ファイルを開く**] ダイアログボックスにファイル名を入力する</span><span class="sxs-lookup"><span data-stu-id="09d08-117">Typing a filename in the **Open File** dialog</span></span>  
    > ![[ファイルを開く] ダイアログボックスにファイル名を入力する][ImageFileSearch]  
    
### <span data-ttu-id="09d08-119">[ネットワーク] パネルでリソースを開く</span><span class="sxs-lookup"><span data-stu-id="09d08-119">Open resources in the Network panel</span></span>   

<span data-ttu-id="09d08-120">「[リソースの詳細を調べる][DevtoolsNetworkInspectDetailsResource]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d08-120">See [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

> ##### <span data-ttu-id="09d08-121">図 3</span><span class="sxs-lookup"><span data-stu-id="09d08-121">Figure 3</span></span>  
> <span data-ttu-id="09d08-122">[ネットワーク] パネルでリソースを検査する</span><span class="sxs-lookup"><span data-stu-id="09d08-122">Inspecting a resource in the Network panel</span></span>  
> ![[ネットワーク] パネルでリソースを検査する][ImageNetworkResponse]  

### <span data-ttu-id="09d08-124">[ネットワーク] パネルのリソースを他のパネルから公開する</span><span class="sxs-lookup"><span data-stu-id="09d08-124">Reveal resources in the Network panel from other panels</span></span>   

<span data-ttu-id="09d08-125">以下の「[リソースの参照](#browse-resources)」セクションでは、DEVTOOLS UI のさまざまな部分からリソースを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09d08-125">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="09d08-126">**ネットワーク**パネルでリソースを検査する場合は、リソースを右クリックして、[**ネットワークパネルで**表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="09d08-126">If you ever want to inspect a resource in the **Network** panel, right-click the resource and select **Reveal in Network panel**.</span></span>  

> ##### <span data-ttu-id="09d08-127">図 4</span><span class="sxs-lookup"><span data-stu-id="09d08-127">Figure 4</span></span>  
> <span data-ttu-id="09d08-128">[**ネットワークパネルで**表示する] オプション</span><span class="sxs-lookup"><span data-stu-id="09d08-128">The **Reveal in Network panel** option</span></span>  
> ![[ネットワーク] パネルでの表示][ImageRevealNetwork]  

## <span data-ttu-id="09d08-130">リソースを参照する</span><span class="sxs-lookup"><span data-stu-id="09d08-130">Browse resources</span></span>   

### <span data-ttu-id="09d08-131">[ネットワーク] パネルでリソースを参照する</span><span class="sxs-lookup"><span data-stu-id="09d08-131">Browse resources in the Network panel</span></span>   

<span data-ttu-id="09d08-132">「[ネットワークアクティビティのログ記録][DevtoolsNetworkLogActivity]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d08-132">See [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

> ##### <span data-ttu-id="09d08-133">図 5</span><span class="sxs-lookup"><span data-stu-id="09d08-133">Figure 5</span></span>  
> <span data-ttu-id="09d08-134">ネットワークログのページリソース</span><span class="sxs-lookup"><span data-stu-id="09d08-134">Page resources in the Network Log</span></span>  
> ![ネットワークログのページリソース][ImageNetworkLog]  

### <span data-ttu-id="09d08-136">ディレクトリで参照</span><span class="sxs-lookup"><span data-stu-id="09d08-136">Browse by directory</span></span>   

<span data-ttu-id="09d08-137">ディレクトリごとに整理されたページのリソースを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="09d08-137">To view the resources of a page organized by directory:</span></span>  

1.  <span data-ttu-id="09d08-138">[**ソース**] タブをクリックして、[**ソース**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="09d08-138">Click the **Sources** tab to open the **Sources** panel.</span></span>  
1.  <span data-ttu-id="09d08-139">[**ページ**] タブをクリックして、ページのリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="09d08-139">Click the **Page** tab to show the resources of the page.</span></span>  <span data-ttu-id="09d08-140">[**ページ**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="09d08-140">The **Page** pane opens.</span></span>  
    
    > ##### <span data-ttu-id="09d08-141">図 6</span><span class="sxs-lookup"><span data-stu-id="09d08-141">Figure 6</span></span>  
    > <span data-ttu-id="09d08-142">**ページ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="09d08-142">The **Page** pane</span></span>  
    > ![ページウィンドウ][ImagePage]  
    
    <span data-ttu-id="09d08-144">[図 6](#figure-6)の明白でない項目の詳細を次に示します。</span><span class="sxs-lookup"><span data-stu-id="09d08-144">Here is a breakdown of the non-obvious items in [Figure 6](#figure-6):</span></span>  
    
    | <span data-ttu-id="09d08-145">ページアイテム</span><span class="sxs-lookup"><span data-stu-id="09d08-145">Page item</span></span> | <span data-ttu-id="09d08-146">説明</span><span class="sxs-lookup"><span data-stu-id="09d08-146">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="09d08-147">メイン文書の[閲覧コンテキスト][MDNInlineFrame]。</span><span class="sxs-lookup"><span data-stu-id="09d08-147">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="09d08-148">ドメイン。</span><span class="sxs-lookup"><span data-stu-id="09d08-148">The domain.</span></span>  <span data-ttu-id="09d08-149">下位にあるすべてのリソースがそのドメインから取得されます。</span><span class="sxs-lookup"><span data-stu-id="09d08-149">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="09d08-150">たとえば、ファイルの完全な URL はおそらくのように `comlink.global.j` `https://airhorner.com/scripts/comlink.global.js` なります。</span><span class="sxs-lookup"><span data-stu-id="09d08-150">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="09d08-151">ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="09d08-151">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="09d08-152">メインの HTML 文書。</span><span class="sxs-lookup"><span data-stu-id="09d08-152">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="09d08-153">サービスワーカーランタイムコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="09d08-153">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="09d08-154">リソースをクリックして**エディター**で表示します。</span><span class="sxs-lookup"><span data-stu-id="09d08-154">Click a resource to view it in the **Editor**.</span></span>  
    
    > ##### <span data-ttu-id="09d08-155">図 7</span><span class="sxs-lookup"><span data-stu-id="09d08-155">Figure 7</span></span>  
    > <span data-ttu-id="09d08-156">**エディター**でのファイルの表示</span><span class="sxs-lookup"><span data-stu-id="09d08-156">Viewing a file in the **Editor**</span></span>  
    > ![エディターでのファイルの表示][ImageSourcesView]  
    
### <span data-ttu-id="09d08-158">ファイル名で参照</span><span class="sxs-lookup"><span data-stu-id="09d08-158">Browse by filename</span></span>   

<span data-ttu-id="09d08-159">既定では、**ページ**ウィンドウはディレクトリ別にリソースをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="09d08-159">By default the **Page** pane groups resources by directory.</span></span>  <span data-ttu-id="09d08-160">このグループ化を無効にして、各ドメインのリソースをフラットなリストとして表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="09d08-160">To disable this grouping and view the resources for each domain as a flat list:</span></span>  

1.  <span data-ttu-id="09d08-161">**ページ**ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="09d08-161">Open the **Page** pane.</span></span>  <span data-ttu-id="09d08-162">「[ディレクトリで参照」を](#browse-by-directory)参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d08-162">See [Browse by directory](#browse-by-directory).</span></span>  
1.  <span data-ttu-id="09d08-163">[**その他のオプション**] をクリックし `...` て、[**グループ化**] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="09d08-163">Click **More Options** `...` and disable **Group By Folder**.</span></span>  
    
    > ##### <span data-ttu-id="09d08-164">図 8</span><span class="sxs-lookup"><span data-stu-id="09d08-164">Figure 8</span></span>  
    > <span data-ttu-id="09d08-165">[**フォルダーでグループ化**] オプション</span><span class="sxs-lookup"><span data-stu-id="09d08-165">The **Group By Folder** option</span></span>  
    > ![[フォルダーでグループ化] オプション][ImageGroupByFolder]  
    
    <span data-ttu-id="09d08-167">リソースはファイルの種類別に整理されます。</span><span class="sxs-lookup"><span data-stu-id="09d08-167">Resources are organized by file type.</span></span>  <span data-ttu-id="09d08-168">各ファイルの種類では、リソースがアルファベット順に構成されています。</span><span class="sxs-lookup"><span data-stu-id="09d08-168">Within each file type the resources are organized alphabetically.</span></span>  
    
    > ##### <span data-ttu-id="09d08-169">図 9</span><span class="sxs-lookup"><span data-stu-id="09d08-169">Figure 9</span></span>  
    > <span data-ttu-id="09d08-170">[**グループ化] フォルダーを**無効にした後の**ページ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="09d08-170">The **Page** pane after disabling **Group By Folder**</span></span>  
    > ![[グループ化] フォルダーを無効にした後のページウィンドウ][ImageFileNames]  
    
### <span data-ttu-id="09d08-172">ファイルの種類で参照する</span><span class="sxs-lookup"><span data-stu-id="09d08-172">Browse by file type</span></span>   

<span data-ttu-id="09d08-173">ファイルの種類に基づいてリソースをグループ化するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="09d08-173">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="09d08-174">[**アプリケーション**] タブをクリックします。 **アプリケーション**パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="09d08-174">Click the **Application** tab.  The **Application** panel opens.</span></span>  <span data-ttu-id="09d08-175">既定では、最初に**マニフェスト**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="09d08-175">By default the **Manifest** pane usually opens first.</span></span>  
    
    > ##### <span data-ttu-id="09d08-176">図 10</span><span class="sxs-lookup"><span data-stu-id="09d08-176">Figure 10</span></span>  
    > <span data-ttu-id="09d08-177">**アプリケーション**パネル</span><span class="sxs-lookup"><span data-stu-id="09d08-177">The **Application** panel</span></span>  
    > ![アプリケーションパネル][ImageApplication]  
    
1.  <span data-ttu-id="09d08-179">[**フレーム**] ウィンドウまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="09d08-179">Scroll down to the **Frames** pane.</span></span>  
    
    > ##### <span data-ttu-id="09d08-180">図 11</span><span class="sxs-lookup"><span data-stu-id="09d08-180">Figure 11</span></span>  
    > <span data-ttu-id="09d08-181">[**フレーム**] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="09d08-181">The **Frames** pane</span></span>  
    > ![[フレーム] ウィンドウ][ImageFrames]  
    
1.  <span data-ttu-id="09d08-183">目的のセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="09d08-183">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="09d08-184">リソースをクリックして表示します。</span><span class="sxs-lookup"><span data-stu-id="09d08-184">Click a resource to view it.</span></span>  
    
    > ##### <span data-ttu-id="09d08-185">図 12</span><span class="sxs-lookup"><span data-stu-id="09d08-185">Figure 12</span></span>  
    > <span data-ttu-id="09d08-186">**アプリケーション**パネルでのリソースの表示</span><span class="sxs-lookup"><span data-stu-id="09d08-186">Viewing a resource in the **Application** panel</span></span>  
    > ![アプリケーションパネルでのリソースの表示][ImageApplicationView]  

#### <span data-ttu-id="09d08-188">[ネットワーク] パネルでファイルの種類を参照する</span><span class="sxs-lookup"><span data-stu-id="09d08-188">Browse files by type in the Network panel</span></span>   

<span data-ttu-id="09d08-189">「[リソースの種類でフィルター処理][DevtoolsNetworkFilterByResourceType]する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09d08-189">See [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

> ##### <span data-ttu-id="09d08-190">図 13</span><span class="sxs-lookup"><span data-stu-id="09d08-190">Figure 13</span></span>  
> <span data-ttu-id="09d08-191">ネットワークログの CSS をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="09d08-191">Filtering for CSS in the Network Log</span></span>  
> ![ネットワークログの CSS をフィルター処理する][ImageCSS]  

<!--  -->  



<!-- image links -->  

[ImageOpenFile]: /microsoft-edge/devtools-guide-chromium/media/resources-command-menu-empty.msft.png "図 1: [ファイルを開く] ダイアログボックス"  
[ImageFileSearch]: /microsoft-edge/devtools-guide-chromium/media/resources-command-menu-file-search.msft.png "図 2: [ファイルを開く] ダイアログボックスにファイル名を入力する"  
[ImageNetworkResponse]: /microsoft-edge/devtools-guide-chromium/media/resources-network-response.msft.png "図 3: * * Network * * パネルでリソースを検査する"  
[ImageRevealNetwork]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-reveal-in-network-panel.msft.png "図 4: ネットワークパネルでの表示"  
[ImageNetworkLog]: /microsoft-edge/devtools-guide-chromium/media/resources-network-resources.msft.png "図 5: ネットワークログのページリソース"  
[ImagePage]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-empty.msft.png "図 6: [ページ] ウィンドウ"  
[ImageSourcesView]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resource.msft.png "図 7: エディターでファイルを表示する"  
[ImageGroupByFolder]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resource-group-by-folder.msft.png "図 8: [フォルダーでグループ化] オプション"  
[ImageFileNames]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png "図 9: [グループ化] フォルダーを無効にした後のページウィンドウ"  
[ImageApplication]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner.msft.png "図 10: アプリケーションパネル"  
[ImageFrames]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner-frames-expanded.msft.png "図 11: [フレーム] ウィンドウ"  
[ImageApplicationView]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner-expanded-resources.msft.png "図 12: アプリケーションパネルでのリソースの表示"  
[ImageCSS]: /microsoft-edge/devtools-guide-chromium/media/resources-network-resources-filter-css.msft.png "図 13: ネットワークログの CSS をフィルター処理する"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevtoolsNetworkFilterByResourceType]: /microsoft-edge/devtools-guide-chromium/network/index#filter-by-resource-type "リソースの種類によるフィルター-Microsoft Edge DevTools でネットワークアクティビティを検査する"  
[DevtoolsNetworkInspectDetailsResource]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "リソースの詳細を調べる-Microsoft Edge DevTools でのネットワークアクティビティの調査"  
[DevtoolsNetworkLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワークアクティビティのログ-Microsoft Edge DevTools でネットワークアクティビティを検査する"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: インラインフレームの要素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Web 開発について学ぶ |MDN"  

> [!NOTE]
> <span data-ttu-id="09d08-212">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="09d08-212">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="09d08-213">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/resources/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="09d08-213">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="09d08-215">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="09d08-215">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
