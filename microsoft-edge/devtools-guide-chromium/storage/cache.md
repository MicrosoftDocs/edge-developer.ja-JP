---
description: Microsoft Edge DevTools のアプリケーションパネルからキャッシュデータを表示する方法について説明します。
title: Microsoft Edge DevTools を使ってキャッシュデータを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c920a171ec89925cc79ab741eed01e11d749bf1b
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993297"
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





# <span data-ttu-id="f3f9d-104">Microsoft Edge DevTools を使ってキャッシュデータを表示する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-104">View cache data with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="f3f9d-105">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って [キャッシュ][MDNCache] データを検査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Cache][MDNCache] data.</span></span>  

<span data-ttu-id="f3f9d-106">[HTTP キャッシュ][MDNHTTPCaching]データを検査しようとしている場合、これは目的のガイドではありません。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-106">If you are trying to inspect [HTTP cache][MDNHTTPCaching] data, this is not the guide you want.</span></span>  <span data-ttu-id="f3f9d-107">**ネットワークログ**の**Size**列で情報を探します。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-107">Look for the information in the **Size** column of the **Network Log**.</span></span>  <span data-ttu-id="f3f9d-108">「 [ネットワークアクティビティのログ記録][DevtoolsNetworkLogActivity]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-108">See [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

## <span data-ttu-id="f3f9d-109">キャッシュデータを表示する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-109">View cache data</span></span>   

1.  <span data-ttu-id="f3f9d-110">[ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-110">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="f3f9d-111">通常、 **マニフェスト** ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="f3f9d-113">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f3f9d-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f3f9d-114">[ **キャッシュ記憶域** ] セクションを展開して、利用可能なキャッシュを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-114">Expand the **Cache Storage** section to view available caches.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="利用可能なキャッシュ" lightbox="../media/storage-application-cache-storage.msft.png":::
       <span data-ttu-id="f3f9d-116">利用可能なキャッシュ</span><span class="sxs-lookup"><span data-stu-id="f3f9d-116">Available caches</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f3f9d-117">コンテンツを表示するキャッシュを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-117">Select a cache to view the contents.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-root-headers.msft.png" alt-text="キャッシュの内容を表示する" lightbox="../media/storage-application-cache-storage-domain-root-headers.msft.png":::
       <span data-ttu-id="f3f9d-119">キャッシュの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-119">View the contents of a cache</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f3f9d-120">リソースを選択して、表の下のセクションに HTTP ヘッダーを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-120">Select a resource to view the HTTP headers in the section below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-index-headers.msft.png" alt-text="リソースの HTTP ヘッダーを表示する" lightbox="../media/storage-application-cache-storage-index-headers.msft.png":::
       <span data-ttu-id="f3f9d-122">リソースの HTTP ヘッダーを表示する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-122">View the HTTP headers of a resource</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f3f9d-123">[ **プレビュー** ] を選択して、リソースのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-123">Select **Preview** to view the content of a resource.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-js-preview.msft.png" alt-text="リソースのコンテンツを表示する" lightbox="../media/storage-application-cache-storage-domain-js-preview.msft.png":::
       <span data-ttu-id="f3f9d-125">リソースのコンテンツを表示する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-125">View the content of a resource</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f3f9d-126">リソースを更新する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-126">Refresh a resource</span></span>   

1.  <span data-ttu-id="f3f9d-127">[キャッシュのデータを表示](#view-cache-data)する。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-127">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="f3f9d-128">更新するリソースを選びます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-128">Select the resource that you want to refresh.</span></span>  <span data-ttu-id="f3f9d-129">DevTools では、選択されていることを示すように強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-129">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="リソースを選択する" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       <span data-ttu-id="f3f9d-131">リソースを選択する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-131">Select a resource</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f3f9d-132">[ **Refresh** (更新)] を選び ![ ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-132">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <span data-ttu-id="f3f9d-133">リソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-133">Filter resources</span></span>   

1.  <span data-ttu-id="f3f9d-134">[キャッシュのデータを表示](#view-cache-data)する。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-134">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="f3f9d-135">[ **パスを指定してフィルター** ] テキストボックスを使用して、指定したパスと一致しないリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-135">Use the **Filter by Path** text box to filter out any resources that do not match the path that you provide.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="指定したパスと一致しないリソースをフィルターで除外する" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       <span data-ttu-id="f3f9d-137">指定したパスと一致しないリソースをフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-137">Filter out resources that do not match the specified path</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f3f9d-138">リソースの削除</span><span class="sxs-lookup"><span data-stu-id="f3f9d-138">Delete a resource</span></span>   

1.  <span data-ttu-id="f3f9d-139">[キャッシュのデータを表示](#view-cache-data)する。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-139">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="f3f9d-140">削除するリソースを選びます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-140">Select the resource that you want to delete.</span></span>  <span data-ttu-id="f3f9d-141">DevTools では、選択されていることを示すように強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-141">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="リソースを選択する" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       <span data-ttu-id="f3f9d-143">リソースを選択する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-143">Select a resource</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f3f9d-144">[ **選択した** \ を削除] ( ![ 選択した \ を削除) を選択し ][ImageDeleteIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-144">Select **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="f3f9d-145">すべてのキャッシュデータを削除する</span><span class="sxs-lookup"><span data-stu-id="f3f9d-145">Delete all cache data</span></span>   

1.  <span data-ttu-id="f3f9d-146">**アプリケーション**  >  の**クリアストレージ**を開きます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-146">Open **Application** > **Clear Storage**.</span></span>  
1.  <span data-ttu-id="f3f9d-147">[ **キャッシュストレージ** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-147">Make sure that the **Cache Storage** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text="[キャッシュストレージ] チェックボックス" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       <span data-ttu-id="f3f9d-149">[ **キャッシュストレージ** ] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="f3f9d-149">The **Cache Storage** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f3f9d-150">[ **サイトデータのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-150">Select **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text="[サイトデータのクリア] ボタン" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       <span data-ttu-id="f3f9d-152">[ **サイトデータのクリア** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="f3f9d-152">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
<!--  
  


-->  

<!-- image links -->  

[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "ネットワークアクティビティのログ |Microsoft ドキュメント"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュMDN"  

> [!NOTE]
> <span data-ttu-id="f3f9d-157">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-157">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f3f9d-158">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cache) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-158">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f3f9d-160">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f3f9d-160">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
