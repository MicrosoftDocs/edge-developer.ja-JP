---
description: フレーム、ドメイン、種類、またはその他の条件によってリソースを整理します。
title: Microsoft Edge DevTools でページリソースを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a243a400dd85b587a8f299a6b8bc3d3d463796b0
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125399"
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

# <span data-ttu-id="32f9f-104">Microsoft Edge DevTools でページリソースを表示する</span><span class="sxs-lookup"><span data-stu-id="32f9f-104">View page resources with Microsoft Edge DevTools</span></span>  

  

<span data-ttu-id="32f9f-105">このガイドでは、Microsoft Edge DevTools を使って web ページのリソースを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-105">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="32f9f-106">リソースは、適切に表示するためにページに必要なファイルです。</span><span class="sxs-lookup"><span data-stu-id="32f9f-106">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="32f9f-107">リソースの例として、CSS、JavaScript、HTML ファイル、画像などがあります。</span><span class="sxs-lookup"><span data-stu-id="32f9f-107">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="32f9f-108">このガイドは、 [web 開発][MDNLearnWebDevelopment] と [Microsoft Edge devtools][MicrosoftEdgeDevTools]の基本について理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="32f9f-108">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="32f9f-109">リソースを開く</span><span class="sxs-lookup"><span data-stu-id="32f9f-109">Open resources</span></span>  

<span data-ttu-id="32f9f-110">検査するリソースの名前がわかっている場合、[ **コマンド] メニュー** でリソースをすばやく開くことができます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-110">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="32f9f-111">`Control` + `P` \ (Windows, Linux \) または `Command` + `P` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-111">Select `Control`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="32f9f-112">[ **ファイルを開く** ] ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-112">The **Open File** dialog opens.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-command-menu-empty.msft.png":::
       <span data-ttu-id="32f9f-114">[ **ファイルを開く** ] ダイアログボックス</span><span class="sxs-lookup"><span data-stu-id="32f9f-114">The **Open File** dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32f9f-115">ドロップダウンからファイルを選択するか、ファイル名の入力を開始し、[ `Enter` オートコンプリート] ボックスで適切なファイルが強調表示されたら選択します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-115">Select the file from the dropdown, or start typing the filename and select `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-command-menu-file-search.msft.png":::
       <span data-ttu-id="32f9f-117">[ **ファイルを開く** ] ダイアログボックスにファイル名を入力する</span><span class="sxs-lookup"><span data-stu-id="32f9f-117">Type a filename in the **Open File** dialog</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="32f9f-118">[ネットワーク] パネルでリソースを開く</span><span class="sxs-lookup"><span data-stu-id="32f9f-118">Open resources in the Network panel</span></span>  

<span data-ttu-id="32f9f-119">[リソースの詳細を調べる][DevtoolsNetworkInspectDetailsResource]には、を移動します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-119">Navigate to [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-network-response.msft.png":::
   <span data-ttu-id="32f9f-121">[ **ネットワーク** ] パネルでリソースを検査する</span><span class="sxs-lookup"><span data-stu-id="32f9f-121">Inspect a resource in the **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="32f9f-122">[ネットワーク] パネルのリソースを他のパネルから公開する</span><span class="sxs-lookup"><span data-stu-id="32f9f-122">Reveal resources in the Network panel from other panels</span></span>  

<span data-ttu-id="32f9f-123">以下の「 [リソースの参照](#browse-resources) 」セクションでは、DEVTOOLS UI のさまざまな部分からリソースを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-123">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="32f9f-124">**ネットワーク**パネルでリソースを検査する場合は、リソースを右クリックして、[**ネットワークパネルで**表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-124">If you ever want to inspect a resource in the **Network** panel, right-click the resource and choose **Reveal in Network panel**.</span></span>  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **<span data-ttu-id="32f9f-126">[ネットワーク] パネルでの表示</span><span class="sxs-lookup"><span data-stu-id="32f9f-126">Reveal in Network panel</span></span>**  
:::image-end:::  

## <span data-ttu-id="32f9f-127">リソースを参照する</span><span class="sxs-lookup"><span data-stu-id="32f9f-127">Browse resources</span></span>  

### <span data-ttu-id="32f9f-128">[ネットワーク] パネルでリソースを参照する</span><span class="sxs-lookup"><span data-stu-id="32f9f-128">Browse resources in the Network panel</span></span>  

<span data-ttu-id="32f9f-129">ログに [記録するネットワークアクティビティ][DevtoolsNetworkLogActivity]に移動します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-129">Navigate to [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-network-resources.msft.png":::
   <span data-ttu-id="32f9f-131">**ネットワーク**ログのページリソース</span><span class="sxs-lookup"><span data-stu-id="32f9f-131">Page resources in the **Network** Log</span></span>  
:::image-end:::  

### <span data-ttu-id="32f9f-132">ディレクトリで参照</span><span class="sxs-lookup"><span data-stu-id="32f9f-132">Browse by directory</span></span>  

<span data-ttu-id="32f9f-133">ディレクトリごとに整理されたページのリソースを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="32f9f-133">To view the resources of a page organized by directory:</span></span>  

1.  <span data-ttu-id="32f9f-134">[ **ソース** ] タブをクリックして、[ **ソース** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-134">Click the **Sources** tab to open the **Sources** panel.</span></span>  
1.  <span data-ttu-id="32f9f-135">[ **ページ** ] タブをクリックして、ページのリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-135">Click the **Page** tab to show the resources of the page.</span></span>  <span data-ttu-id="32f9f-136">[ **ページ** ] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-136">The **Page** pane opens.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-sources-page-empty.msft.png":::
       <span data-ttu-id="32f9f-138">**ページ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="32f9f-138">The **Page** pane</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="32f9f-139">前の図の明白でない項目の詳細を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-139">Here is a breakdown of the non-obvious items in the previous figure.</span></span>  
    
    | <span data-ttu-id="32f9f-140">ページアイテム</span><span class="sxs-lookup"><span data-stu-id="32f9f-140">Page item</span></span> | <span data-ttu-id="32f9f-141">説明</span><span class="sxs-lookup"><span data-stu-id="32f9f-141">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="32f9f-142">メイン文書の [閲覧コンテキスト][MDNInlineFrame]。</span><span class="sxs-lookup"><span data-stu-id="32f9f-142">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="32f9f-143">ドメイン。</span><span class="sxs-lookup"><span data-stu-id="32f9f-143">The domain.</span></span>  <span data-ttu-id="32f9f-144">下位にあるすべてのリソースがそのドメインから取得されます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-144">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="32f9f-145">たとえば、ファイルの完全な URL はおそらくのように `comlink.global.j` `https://airhorner.com/scripts/comlink.global.js` なります。</span><span class="sxs-lookup"><span data-stu-id="32f9f-145">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="32f9f-146">ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="32f9f-146">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="32f9f-147">メインの HTML 文書。</span><span class="sxs-lookup"><span data-stu-id="32f9f-147">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="32f9f-148">サービスワーカーランタイムコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="32f9f-148">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="32f9f-149">リソースをクリックして **エディター**で表示します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-149">Click a resource to view it in the **Editor**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-sources-page-resource.msft.png":::
       <span data-ttu-id="32f9f-151">**エディター**でファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="32f9f-151">View a file in the **Editor**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="32f9f-152">ファイル名で参照</span><span class="sxs-lookup"><span data-stu-id="32f9f-152">Browse by filename</span></span>  

<span data-ttu-id="32f9f-153">既定では、 **ページ** ウィンドウはディレクトリ別にリソースをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-153">By default the **Page** pane groups resources by directory.</span></span>  <span data-ttu-id="32f9f-154">このグループ化を無効にして、各ドメインのリソースをフラットなリストとして表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="32f9f-154">To disable this grouping and view the resources for each domain as a flat list:</span></span>  

1.  <span data-ttu-id="32f9f-155">**ページ**ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-155">Open the **Page** pane.</span></span>  <span data-ttu-id="32f9f-156">「 [ディレクトリで参照」](#browse-by-directory)に移動します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-156">Navigate to [Browse by directory](#browse-by-directory).</span></span>  
1.  <span data-ttu-id="32f9f-157">[ **その他のオプション**] を選び `...` 、[ **グループごとにグループ化**] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="32f9f-157">Choose **More Options** `...` and disable **Group By Folder**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       <span data-ttu-id="32f9f-159">[ **フォルダーでグループ化** ] オプション</span><span class="sxs-lookup"><span data-stu-id="32f9f-159">The **Group By Folder** option</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="32f9f-160">リソースはファイルの種類別に整理されます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-160">Resources are organized by file type.</span></span>  <span data-ttu-id="32f9f-161">各ファイルの種類では、リソースがアルファベット順に構成されています。</span><span class="sxs-lookup"><span data-stu-id="32f9f-161">Within each file type the resources are organized alphabetically.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       <span data-ttu-id="32f9f-163">[**グループ化] フォルダーを**無効にした後の**ページ**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="32f9f-163">The **Page** pane after disabling **Group By Folder**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="32f9f-164">ファイルの種類で参照する</span><span class="sxs-lookup"><span data-stu-id="32f9f-164">Browse by file type</span></span>  

<span data-ttu-id="32f9f-165">ファイルの種類に基づいてリソースをグループ化するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="32f9f-165">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="32f9f-166">[ **アプリケーション** ] タブをクリックします。 **アプリケーション** パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-166">Click the **Application** tab.  The **Application** panel opens.</span></span>  <span data-ttu-id="32f9f-167">既定では、最初に **マニフェスト** ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-167">By default the **Manifest** pane usually opens first.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       <span data-ttu-id="32f9f-169">**アプリケーション**パネル</span><span class="sxs-lookup"><span data-stu-id="32f9f-169">The **Application** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32f9f-170">[ **フレーム** ] ウィンドウまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="32f9f-170">Scroll down to the **Frames** pane.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       <span data-ttu-id="32f9f-172">[ **フレーム** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="32f9f-172">The **Frames** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32f9f-173">目的のセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-173">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="32f9f-174">リソースをクリックして表示します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-174">Click a resource to view it.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       <span data-ttu-id="32f9f-176">**アプリケーション**パネルでリソースを表示する</span><span class="sxs-lookup"><span data-stu-id="32f9f-176">View a resource in the **Application** panel</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="32f9f-177">[ネットワーク] パネルでファイルの種類を参照する</span><span class="sxs-lookup"><span data-stu-id="32f9f-177">Browse files by type in the Network panel</span></span>  

<span data-ttu-id="32f9f-178">リソースの [種類によるフィルター][DevtoolsNetworkFilterByResourceType]に移動します。</span><span class="sxs-lookup"><span data-stu-id="32f9f-178">Navigate to [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="[ファイルを開く] ダイアログボックス" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   <span data-ttu-id="32f9f-180">**ネットワーク**ログの CSS をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="32f9f-180">Filter for CSS in the **Network** Log</span></span>  
:::image-end:::  

## <span data-ttu-id="32f9f-181">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="32f9f-181">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "リソースの種類によるフィルター-Microsoft Edge DevTools でのネットワークアクティビティの検査 |Microsoft ドキュメント"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "リソースの詳細を調べる-Microsoft Edge DevTools でのネットワークアクティビティの検査 |Microsoft ドキュメント"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "ネットワークアクティビティのログ-Microsoft Edge DevTools でネットワークアクティビティを検査するMicrosoft ドキュメント"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: インラインフレームの要素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Web 開発について学ぶ |MDN"  

> [!NOTE]
> <span data-ttu-id="32f9f-188">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="32f9f-188">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="32f9f-189">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/resources/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="32f9f-189">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="32f9f-191">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="32f9f-191">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
