---
title: Microsoft Edge DevTools を使ってキャッシュデータを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 82356777f209b86f88de1ee53b212947d969ff8a
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612075"
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





# <span data-ttu-id="cb2ab-103">Microsoft Edge DevTools を使ってキャッシュデータを表示する</span><span class="sxs-lookup"><span data-stu-id="cb2ab-103">View Cache Data With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="cb2ab-104">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って[キャッシュ][MDNCache]データを検査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-104">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Cache][MDNCache] data.</span></span>  

<span data-ttu-id="cb2ab-105">[HTTP キャッシュ][MDNHTTPCaching]データを検査しようとしている場合、これは目的のガイドではありません。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-105">If you are trying to inspect [HTTP cache][MDNHTTPCaching] data, this is not the guide you want.</span></span>  
<span data-ttu-id="cb2ab-106">**ネットワークログ**の**Size**列で情報を探します。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-106">Look for the information in the **Size** column of the **Network Log**.</span></span>  <span data-ttu-id="cb2ab-107">「[ネットワークアクティビティのログ記録][DevtoolsNetworkLogActivity]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-107">See [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

## <span data-ttu-id="cb2ab-108">キャッシュデータを表示する</span><span class="sxs-lookup"><span data-stu-id="cb2ab-108">View cache data</span></span>   

1.  <span data-ttu-id="cb2ab-109">[**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-109">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="cb2ab-110">通常、**マニフェスト**ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-110">The **Manifest** pane usually opens by default.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-111">図 1</span><span class="sxs-lookup"><span data-stu-id="cb2ab-111">Figure 1</span></span>  
    > <span data-ttu-id="cb2ab-112">マニフェストウィンドウ</span><span class="sxs-lookup"><span data-stu-id="cb2ab-112">The Manifest pane</span></span>  
    > ![マニフェストウィンドウ][ImageManifestPane]  

1.  <span data-ttu-id="cb2ab-114">[**キャッシュ記憶域**] セクションを展開して、利用可能なキャッシュを表示します。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-114">Expand the **Cache Storage** section to view available caches.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-115">図 2</span><span class="sxs-lookup"><span data-stu-id="cb2ab-115">Figure 2</span></span>  
    > <span data-ttu-id="cb2ab-116">利用可能なキャッシュ</span><span class="sxs-lookup"><span data-stu-id="cb2ab-116">Available caches</span></span>  
    > ![利用可能なキャッシュ][ImageCache]  

1.  <span data-ttu-id="cb2ab-118">コンテンツを表示するキャッシュを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-118">Select a cache to view the contents.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-119">図 3</span><span class="sxs-lookup"><span data-stu-id="cb2ab-119">Figure 3</span></span>  
    > <span data-ttu-id="cb2ab-120">キャッシュの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="cb2ab-120">Viewing the contents of a cache</span></span>  
    > ![キャッシュの内容を表示する][ImageCacheView]  

1.  <span data-ttu-id="cb2ab-122">リソースを選択して、表の下のセクションに HTTP ヘッダーを表示します。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-122">Select a resource to view the HTTP headers in the section below the table.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-123">図 4</span><span class="sxs-lookup"><span data-stu-id="cb2ab-123">Figure 4</span></span>  
    > <span data-ttu-id="cb2ab-124">リソースの HTTP ヘッダーの表示</span><span class="sxs-lookup"><span data-stu-id="cb2ab-124">Viewing the HTTP headers of a resource</span></span>  
    > ![リソースの HTTP ヘッダーの表示][ImageViewCacheResource]  

1.  <span data-ttu-id="cb2ab-126">[**プレビュー** ] を選択して、リソースのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-126">Select **Preview** to view the content of a resource.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-127">図 5</span><span class="sxs-lookup"><span data-stu-id="cb2ab-127">Figure 5</span></span>  
    > <span data-ttu-id="cb2ab-128">リソースの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="cb2ab-128">Viewing the content of a resource</span></span>  
    > ![リソースの内容を表示する][ImageCacheContent]  

## <span data-ttu-id="cb2ab-130">リソースを更新する</span><span class="sxs-lookup"><span data-stu-id="cb2ab-130">Refresh a resource</span></span>   

1.  <span data-ttu-id="cb2ab-131">[キャッシュのデータを表示](#view-cache-data)する。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-131">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="cb2ab-132">更新するリソースを選びます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-132">Select the resource that you want to refresh.</span></span>  <span data-ttu-id="cb2ab-133">DevTools では、選択されていることを示すように強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-133">DevTools highlights it to indicate that it is selected.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-134">図 6</span><span class="sxs-lookup"><span data-stu-id="cb2ab-134">Figure 6</span></span>  
    > <span data-ttu-id="cb2ab-135">リソースの選択</span><span class="sxs-lookup"><span data-stu-id="cb2ab-135">Selecting a resource</span></span>  
    > ![リソースの選択][ImageCacheSelected]  

1.  <span data-ttu-id="cb2ab-137">[**更新の更新]** を選び ![ ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-137">Select **Refresh** ![Refresh][ImageRefreshIcon].</span></span>  

## <span data-ttu-id="cb2ab-138">リソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="cb2ab-138">Filter resources</span></span>   

1.  <span data-ttu-id="cb2ab-139">[キャッシュのデータを表示](#view-cache-data)する。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-139">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="cb2ab-140">[**パスを指定してフィルター** ] テキストボックスを使用して、指定したパスと一致しないリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-140">Use the **Filter by Path** text box to filter out any resources that do not match the path that you provide.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-141">図 7</span><span class="sxs-lookup"><span data-stu-id="cb2ab-141">Figure 7</span></span>  
    > <span data-ttu-id="cb2ab-142">指定したパスと一致しないリソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="cb2ab-142">Filtering out resources that do not match the specified path</span></span>  
    > ![指定したパスと一致しないリソースをフィルター処理する][ImageCacheFilter]  

## <span data-ttu-id="cb2ab-144">リソースの削除</span><span class="sxs-lookup"><span data-stu-id="cb2ab-144">Delete a resource</span></span>   

1.  <span data-ttu-id="cb2ab-145">[キャッシュのデータを表示](#view-cache-data)する。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-145">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="cb2ab-146">削除するリソースを選びます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-146">Select the resource that you want to delete.</span></span>  <span data-ttu-id="cb2ab-147">DevTools では、選択されていることを示すように強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-147">DevTools highlights it to indicate that it is selected.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-148">図 8</span><span class="sxs-lookup"><span data-stu-id="cb2ab-148">Figure 8</span></span>  
    > <span data-ttu-id="cb2ab-149">リソースの選択</span><span class="sxs-lookup"><span data-stu-id="cb2ab-149">Selecting a resource</span></span>  
    > ![リソースの選択][ImageCacheSelected2]  

1.  <span data-ttu-id="cb2ab-151">[選択した削除の**削除**] を選択し ![ ][ImageDeleteIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-151">Select **Delete Selected** ![Delete Selected][ImageDeleteIcon].</span></span>  

## <span data-ttu-id="cb2ab-152">すべてのキャッシュデータを削除する</span><span class="sxs-lookup"><span data-stu-id="cb2ab-152">Delete all cache data</span></span>   

1.  <span data-ttu-id="cb2ab-153">**アプリケーション**  >  の**クリアストレージ**を開きます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-153">Open **Application** > **Clear Storage**.</span></span>  
1.  <span data-ttu-id="cb2ab-154">[**キャッシュストレージ**] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-154">Make sure that the **Cache Storage** checkbox is enabled.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-155">図 9</span><span class="sxs-lookup"><span data-stu-id="cb2ab-155">Figure 9</span></span>  
    > <span data-ttu-id="cb2ab-156">[**キャッシュストレージ**] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="cb2ab-156">The **Cache Storage** checkbox</span></span>  
    > ![[キャッシュストレージ] チェックボックス][ImageCacheCheckbox]  

1.  <span data-ttu-id="cb2ab-158">[**サイトデータのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-158">Select **Clear site data**.</span></span>  
    
    > ##### <span data-ttu-id="cb2ab-159">図 10</span><span class="sxs-lookup"><span data-stu-id="cb2ab-159">Figure 10</span></span>  
    > <span data-ttu-id="cb2ab-160">[**サイトデータのクリア**] ボタン</span><span class="sxs-lookup"><span data-stu-id="cb2ab-160">The **Clear Site Data** button</span></span>  
    > ![[サイトデータのクリア] ボタン][ImageCacheClearSite]  

<!--  -->  



<!-- image links -->  

[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  

[ImageManifestPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageCache]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage.msft.png "図 2: 使用できるキャッシュ"  
[ImageCacheView]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-root-headers.msft.png "図 3: キャッシュの内容を表示する"  
[ImageViewCacheResource]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-index-headers.msft.png "図 4: リソースの HTTP ヘッダーの表示"  
[ImageCacheContent]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-js-preview.msft.png "図 5: リソースの内容を表示する"  
[ImageCacheSelected]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-refresh.msft.png "図 6: リソースの選択"  
[ImageCacheFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-filter.msft.png "図 7: 指定したパスと一致しないリソースのフィルター処理"  
[ImageCacheSelected2]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-delete-selected.msft.png "図 8: リソースの選択"  
[ImageCacheCheckbox]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-cache-storage-checkbox.msft.png "図 9: キャッシュ記憶域のチェックボックス"  
[ImageCacheClearSite]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png "図 10: [サイトデータのクリア] ボタン"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevtoolsNetworkLogActivity]: /microsoft-edge/network/index#log-network-activity  "ネットワークアクティビティをログに記録する"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュMDN"  

> [!NOTE]
> <span data-ttu-id="cb2ab-176">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-176">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cb2ab-177">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cache)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-177">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="cb2ab-179">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="cb2ab-179">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
