---
description: フレーム、ドメイン、種類、その他の条件でリソースを整理します。
title: Microsoft Edge DevTools を使用してページ リソースを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 75063b23f23c25ff4fe2e7f6e044a2de9a7b1ccd
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398225"
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

# <a name="view-page-resources-with-microsoft-edge-devtools"></a><span data-ttu-id="690e1-104">Microsoft Edge DevTools を使用してページ リソースを表示する</span><span class="sxs-lookup"><span data-stu-id="690e1-104">View page resources with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="690e1-105">このガイドでは、Microsoft Edge DevTools を使用して Web ページのリソースを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="690e1-105">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="690e1-106">リソースは、ページが正しく表示するために必要なファイルです。</span><span class="sxs-lookup"><span data-stu-id="690e1-106">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="690e1-107">リソースの例としては、CSS、JavaScript、HTML ファイル、および画像が含まれます。</span><span class="sxs-lookup"><span data-stu-id="690e1-107">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="690e1-108">このガイドでは、Web 開発の基本と Microsoft [][MDNLearnWebDevelopment] [Edge DevTools][MicrosoftEdgeDevTools]に精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="690e1-108">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="open-resources"></a><span data-ttu-id="690e1-109">リソースを開く</span><span class="sxs-lookup"><span data-stu-id="690e1-109">Open resources</span></span>  

<span data-ttu-id="690e1-110">検査するリソースの名前がわかっている場合は、コマンド メニューを 使用してリソースを高速に開きます。</span><span class="sxs-lookup"><span data-stu-id="690e1-110">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="690e1-111">`Control` + `P` \(Windows, Linux\) または `Command` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="690e1-111">Select `Control`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="690e1-112">[ **ファイルを開く]** ダイアログボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="690e1-112">The **Open File** dialog opens.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text="[ファイルを開く] ダイアログ" lightbox="../media/resources-command-menu-empty.msft.png":::
       <span data-ttu-id="690e1-114">[ **ファイルを開く]** ダイアログ</span><span class="sxs-lookup"><span data-stu-id="690e1-114">The **Open File** dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="690e1-115">ドロップダウンからファイルを選択するか、ファイル名の入力を開始し、オートコンプリート ボックスで正しいファイルが強調表示された後 `Enter` で選択します。</span><span class="sxs-lookup"><span data-stu-id="690e1-115">Choose the file from the dropdown, or start typing the filename and select `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="[ファイルを開く] ダイアログボックスにファイル名を入力する" lightbox="../media/resources-command-menu-file-search.msft.png":::
       <span data-ttu-id="690e1-117">[ファイルを開く] ダイアログボックス **にファイル名を入力** する</span><span class="sxs-lookup"><span data-stu-id="690e1-117">Type a filename in the **Open File** dialog</span></span>  
    :::image-end:::  
    
### <a name="open-resources-in-the-network-tool"></a><span data-ttu-id="690e1-118">ネットワーク ツールでリソースを開く</span><span class="sxs-lookup"><span data-stu-id="690e1-118">Open resources in the Network tool</span></span>  

<span data-ttu-id="690e1-119">[リソースの [詳細を検査する] に移動します][DevtoolsNetworkInspectDetailsResource]。</span><span class="sxs-lookup"><span data-stu-id="690e1-119">Navigate to [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="ネットワーク ツールでリソースを検査する" lightbox="../media/resources-network-response.msft.png":::
   <span data-ttu-id="690e1-121">ネットワーク ツールでリソース **を検査** する</span><span class="sxs-lookup"><span data-stu-id="690e1-121">Inspect a resource in the **Network** tool</span></span>  
:::image-end:::  

### <a name="reveal-resources-in-the-network-tool-from-other-panels"></a><span data-ttu-id="690e1-122">他のパネルからネットワーク ツールのリソースを表示する</span><span class="sxs-lookup"><span data-stu-id="690e1-122">Reveal resources in the Network tool from other panels</span></span>  

<span data-ttu-id="690e1-123">下 [の [リソースの](#browse-resources) 参照] セクションでは、DevTools UI のさまざまな部分からリソースを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="690e1-123">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="690e1-124">ネットワーク ツールでリソースを検査する場合は、リソースにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[ネットワーク] パネルで [表示] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="690e1-124">If you ever want to inspect a resource in the **Network** tool,  hover on the resource, open the contextual menu \(right-click\), and choose **Reveal in Network panel**.</span></span>  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="[ネットワーク] パネルで表示する" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **<span data-ttu-id="690e1-126">[ネットワーク] パネルで表示する</span><span class="sxs-lookup"><span data-stu-id="690e1-126">Reveal in Network panel</span></span>**  
:::image-end:::  

## <a name="browse-resources"></a><span data-ttu-id="690e1-127">リソースの参照</span><span class="sxs-lookup"><span data-stu-id="690e1-127">Browse resources</span></span>  

### <a name="browse-resources-in-the-network-panel"></a><span data-ttu-id="690e1-128">[ネットワーク] パネルでリソースを参照する</span><span class="sxs-lookup"><span data-stu-id="690e1-128">Browse resources in the Network panel</span></span>  

<span data-ttu-id="690e1-129">[ネットワーク アクティビティ [のログ記録] に移動します][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="690e1-129">Navigate to [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="ネットワーク ログのページ リソース" lightbox="../media/resources-network-resources.msft.png":::
   <span data-ttu-id="690e1-131">ネットワーク ログの**ページ リソース**</span><span class="sxs-lookup"><span data-stu-id="690e1-131">Page resources in the **Network** Log</span></span>  
:::image-end:::  

### <a name="browse-by-directory"></a><span data-ttu-id="690e1-132">ディレクトリで参照する</span><span class="sxs-lookup"><span data-stu-id="690e1-132">Browse by directory</span></span>  

<span data-ttu-id="690e1-133">ディレクトリ別に整理されたページのリソースを表示するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="690e1-133">To view the resources of a page organized by directory:</span></span>  

1.  <span data-ttu-id="690e1-134">[ソース] **ツールを選択** して 、[ソース] **パネルを開** きます。</span><span class="sxs-lookup"><span data-stu-id="690e1-134">Choose the **Sources** tool to open the **Sources** panel.</span></span>  
1.  <span data-ttu-id="690e1-135">[ページ **] パネルを** 選択して、ページのリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="690e1-135">Choose the **Page** panel to show the resources of the page.</span></span>  <span data-ttu-id="690e1-136">[ **ページ] ウィンドウが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="690e1-136">The **Page** pane opens.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="ページウィンドウ" lightbox="../media/resources-sources-page-empty.msft.png":::
       <span data-ttu-id="690e1-138">[ **ページ]** パネル</span><span class="sxs-lookup"><span data-stu-id="690e1-138">The **Page** panel</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="690e1-139">前の図の非明白な項目の内訳を次に示します。</span><span class="sxs-lookup"><span data-stu-id="690e1-139">Here is a breakdown of the non-obvious items in the previous figure.</span></span>  
    
    | <span data-ttu-id="690e1-140">ページ アイテム</span><span class="sxs-lookup"><span data-stu-id="690e1-140">Page item</span></span> | <span data-ttu-id="690e1-141">説明</span><span class="sxs-lookup"><span data-stu-id="690e1-141">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="690e1-142">メイン ドキュメントの [参照コンテキスト][MDNInlineFrame]です。</span><span class="sxs-lookup"><span data-stu-id="690e1-142">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="690e1-143">ドメイン。</span><span class="sxs-lookup"><span data-stu-id="690e1-143">The domain.</span></span>  <span data-ttu-id="690e1-144">その下に入れ子になったすべてのリソースは、そのドメインから来ます。</span><span class="sxs-lookup"><span data-stu-id="690e1-144">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="690e1-145">たとえば、ファイルの完全な URL `comlink.global.j` はおそらく `https://airhorner.com/scripts/comlink.global.js` です。</span><span class="sxs-lookup"><span data-stu-id="690e1-145">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="690e1-146">ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="690e1-146">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="690e1-147">メインの HTML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="690e1-147">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="690e1-148">サービス ワーカーのランタイム コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="690e1-148">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="690e1-149">エディターで表示するリソースを選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="690e1-149">Choose a resource to view it in the **Editor**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="エディターでファイルを表示する" lightbox="../media/resources-sources-page-resource.msft.png":::
       <span data-ttu-id="690e1-151">エディターでファイルを表示 **する**</span><span class="sxs-lookup"><span data-stu-id="690e1-151">View a file in the **Editor**</span></span>  
    :::image-end:::  
    
### <a name="browse-by-filename"></a><span data-ttu-id="690e1-152">ファイル名で参照する</span><span class="sxs-lookup"><span data-stu-id="690e1-152">Browse by filename</span></span>  

<span data-ttu-id="690e1-153">既定では **、Page パネルはリソース** をディレクトリ別にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="690e1-153">By default the **Page** panel groups resources by directory.</span></span>  <span data-ttu-id="690e1-154">このグループ化を無効にして、各ドメインのリソースをフラット リストとして表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="690e1-154">To disable this grouping and view the resources for each domain as a flat list:</span></span>  

1.  <span data-ttu-id="690e1-155">[ページ] **パネルを開** きます。</span><span class="sxs-lookup"><span data-stu-id="690e1-155">Open the **Page** panel.</span></span>  <span data-ttu-id="690e1-156">[ディレクトリで [参照] に移動します](#browse-by-directory)。</span><span class="sxs-lookup"><span data-stu-id="690e1-156">Navigate to [Browse by directory](#browse-by-directory).</span></span>  
1.  <span data-ttu-id="690e1-157">[その **他のオプション]** `...` を選択し、[ **フォルダー別グループ化] を無効にします**。</span><span class="sxs-lookup"><span data-stu-id="690e1-157">Choose **More Options** `...` and disable **Group By Folder**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text="[フォルダー別にグループ化] オプション" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       <span data-ttu-id="690e1-159">[ **フォルダー別にグループ化]** オプション</span><span class="sxs-lookup"><span data-stu-id="690e1-159">The **Group By Folder** option</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="690e1-160">リソースはファイルの種類別に整理されます。</span><span class="sxs-lookup"><span data-stu-id="690e1-160">Resources are organized by file type.</span></span>  <span data-ttu-id="690e1-161">各ファイルの種類では、リソースはアルファベット順に整理されます。</span><span class="sxs-lookup"><span data-stu-id="690e1-161">Within each file type the resources are organized alphabetically.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="Group By Folder を無効にした後のページ パネル" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       <span data-ttu-id="690e1-163">Group **By** Folder を無効にした **後のページ パネル**</span><span class="sxs-lookup"><span data-stu-id="690e1-163">The **Page** panel after disabling **Group By Folder**</span></span>  
    :::image-end:::  
    
### <a name="browse-by-file-type"></a><span data-ttu-id="690e1-164">ファイルの種類別に参照する</span><span class="sxs-lookup"><span data-stu-id="690e1-164">Browse by file type</span></span>  

<span data-ttu-id="690e1-165">ファイルの種類に基づいてリソースをグループ化するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="690e1-165">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="690e1-166">[アプリケーション] **タブを選択** します。 [ **アプリケーション] ツール** が開きます。</span><span class="sxs-lookup"><span data-stu-id="690e1-166">Choose the **Application** tab.  The **Application** tool opens.</span></span>  <span data-ttu-id="690e1-167">既定では、通常 **、マニフェスト ウィンドウ** が最初に開きます。</span><span class="sxs-lookup"><span data-stu-id="690e1-167">By default the **Manifest** pane usually opens first.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="アプリケーション ツール" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       <span data-ttu-id="690e1-169">アプリケーション**ツール**</span><span class="sxs-lookup"><span data-stu-id="690e1-169">The **Application** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="690e1-170">[フレーム] ウィンドウまで **下にスクロール** します。</span><span class="sxs-lookup"><span data-stu-id="690e1-170">Scroll down to the **Frames** pane.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="[フレーム] ウィンドウ" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       <span data-ttu-id="690e1-172">[ **フレーム]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="690e1-172">The **Frames** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="690e1-173">興味のあるセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="690e1-173">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="690e1-174">リソースを選択して表示します。</span><span class="sxs-lookup"><span data-stu-id="690e1-174">Choose a resource to view it.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="[アプリケーション] パネルでリソースを表示する" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       <span data-ttu-id="690e1-176">[アプリケーション] パネルでリソース **を表示** する</span><span class="sxs-lookup"><span data-stu-id="690e1-176">View a resource in the **Application** panel</span></span>  
    :::image-end:::  
    
#### <a name="browse-files-by-type-in-the-network-panel"></a><span data-ttu-id="690e1-177">[ネットワーク] パネルの種類別にファイルを参照する</span><span class="sxs-lookup"><span data-stu-id="690e1-177">Browse files by type in the Network panel</span></span>  

<span data-ttu-id="690e1-178">[リソースの [種類でフィルター] に移動します][DevtoolsNetworkFilterByResourceType]。</span><span class="sxs-lookup"><span data-stu-id="690e1-178">Navigate to [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="ネットワーク ログの CSS のフィルター" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   <span data-ttu-id="690e1-180">ネットワーク ログの CSS **の** フィルター</span><span class="sxs-lookup"><span data-stu-id="690e1-180">Filter for CSS in the **Network** Log</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="690e1-181">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="690e1-181">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "リソースの種類によるフィルター - Microsoft Edge DevTools のネットワーク アクティビティを調|Microsoft Docs"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "リソースの詳細を調す - Microsoft Edge DevTools サーバーでネットワーク アクティビティを|Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "ネットワーク アクティビティのログ - Microsoft Edge DevTools サーバーでネットワーク アクティビティを|Microsoft Docs"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: Inline Frame 要素|MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Web 開発の詳細|MDN"  

> [!NOTE]
> <span data-ttu-id="690e1-188">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="690e1-188">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="690e1-189">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/resources/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="690e1-189">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="690e1-191">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="690e1-191">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
