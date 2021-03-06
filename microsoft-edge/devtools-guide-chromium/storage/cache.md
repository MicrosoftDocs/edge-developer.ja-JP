---
description: Microsoft Edge DevTools の [アプリケーション] パネルからキャッシュ データを表示する方法。
title: Microsoft Edge DevTools を使用してキャッシュ データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7e0523e3293bbdafa9c3575344714da708fffe62
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397539"
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

# <a name="view-cache-data-with-microsoft-edge-devtools"></a><span data-ttu-id="f0c75-104">Microsoft Edge DevTools を使用してキャッシュ データを表示する</span><span class="sxs-lookup"><span data-stu-id="f0c75-104">View cache data with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="f0c75-105">このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用してキャッシュ データを検査する方法 [について説明][MDNCache] します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Cache][MDNCache] data.</span></span>  

<span data-ttu-id="f0c75-106">[HTTP][MDNHTTPCaching]キャッシュ データを検査しようとしている場合、これは必要なガイドではありません。</span><span class="sxs-lookup"><span data-stu-id="f0c75-106">If you are trying to inspect [HTTP cache][MDNHTTPCaching] data, this is not the guide you want.</span></span>  <span data-ttu-id="f0c75-107">ネットワーク ログの [ **サイズ** ] 列の情報を **探します**。</span><span class="sxs-lookup"><span data-stu-id="f0c75-107">Look for the information in the **Size** column of the **Network Log**.</span></span>  <span data-ttu-id="f0c75-108">[ネットワーク アクティビティ [のログ記録] に移動します][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="f0c75-108">Navigate to [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

## <a name="view-cache-data"></a><span data-ttu-id="f0c75-109">キャッシュ データの表示</span><span class="sxs-lookup"><span data-stu-id="f0c75-109">View cache data</span></span>  

1.  <span data-ttu-id="f0c75-110">[アプリケーション] **タブを** 選択して、[アプリケーション] パネル **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="f0c75-110">Choose the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="f0c75-111">通常 **、マニフェスト ウィンドウ** は既定で開きます。</span><span class="sxs-lookup"><span data-stu-id="f0c75-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="f0c75-113">[ **マニフェスト]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f0c75-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f0c75-114">[キャッシュ ストレージ **] セクションを展開** して、使用可能なキャッシュを表示します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-114">Expand the **Cache Storage** section to view available caches.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="使用可能なキャッシュ" lightbox="../media/storage-application-cache-storage.msft.png":::
       <span data-ttu-id="f0c75-116">使用可能なキャッシュ</span><span class="sxs-lookup"><span data-stu-id="f0c75-116">Available caches</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f0c75-117">コンテンツを表示するキャッシュを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-117">Choose a cache to view the contents.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-root-headers.msft.png" alt-text="キャッシュの内容を表示する" lightbox="../media/storage-application-cache-storage-domain-root-headers.msft.png":::
       <span data-ttu-id="f0c75-119">キャッシュの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="f0c75-119">View the contents of a cache</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f0c75-120">表の下のセクションで HTTP ヘッダーを表示するリソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-120">Choose a resource to view the HTTP headers in the section below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-index-headers.msft.png" alt-text="リソースの HTTP ヘッダーを表示する" lightbox="../media/storage-application-cache-storage-index-headers.msft.png":::
       <span data-ttu-id="f0c75-122">リソースの HTTP ヘッダーを表示する</span><span class="sxs-lookup"><span data-stu-id="f0c75-122">View the HTTP headers of a resource</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f0c75-123">[ **プレビュー] を** 選択して、リソースのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-123">Choose **Preview** to view the content of a resource.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-js-preview.msft.png" alt-text="リソースのコンテンツを表示する" lightbox="../media/storage-application-cache-storage-domain-js-preview.msft.png":::
       <span data-ttu-id="f0c75-125">リソースのコンテンツを表示する</span><span class="sxs-lookup"><span data-stu-id="f0c75-125">View the content of a resource</span></span>  
    :::image-end:::  
    
## <a name="refresh-a-resource"></a><span data-ttu-id="f0c75-126">リソースの更新</span><span class="sxs-lookup"><span data-stu-id="f0c75-126">Refresh a resource</span></span>  

1.  <span data-ttu-id="f0c75-127">[キャッシュのデータを表示します](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="f0c75-127">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="f0c75-128">更新するリソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-128">Choose the resource that you want to refresh.</span></span>  <span data-ttu-id="f0c75-129">DevTools では強調表示され、選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-129">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="更新するリソースを選択する" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       <span data-ttu-id="f0c75-131">更新するリソースを選択する</span><span class="sxs-lookup"><span data-stu-id="f0c75-131">Choose a resource to refresh</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f0c75-132">[ **更新** \( ![ Refresh ][ImageRefreshIcon] \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="f0c75-132">Choose **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <a name="filter-resources"></a><span data-ttu-id="f0c75-133">リソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="f0c75-133">Filter resources</span></span>  

1.  <span data-ttu-id="f0c75-134">[キャッシュのデータを表示します](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="f0c75-134">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="f0c75-135">[パス **でフィルター] テキスト** ボックスを使用して、指定したパスに一致しないリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-135">Use the **Filter by Path** text box to filter out any resources that do not match the path that you provide.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="指定したパスに一致しないリソースをフィルター処理する" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       <span data-ttu-id="f0c75-137">指定したパスに一致しないリソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="f0c75-137">Filter out resources that do not match the specified path</span></span>  
    :::image-end:::  
    
## <a name="delete-a-resource"></a><span data-ttu-id="f0c75-138">リソースの削除</span><span class="sxs-lookup"><span data-stu-id="f0c75-138">Delete a resource</span></span>  

1.  <span data-ttu-id="f0c75-139">[キャッシュのデータを表示します](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="f0c75-139">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="f0c75-140">削除するリソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-140">Choose the resource that you want to delete.</span></span>  <span data-ttu-id="f0c75-141">DevTools では強調表示され、選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-141">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="削除するリソースを選択する" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       <span data-ttu-id="f0c75-143">削除するリソースを選択する</span><span class="sxs-lookup"><span data-stu-id="f0c75-143">Choose a resource to delete</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f0c75-144">[ **選択済み \(** Delete ![ Selected ][ImageDeleteIcon] \) を削除する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-144">Choose **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <a name="delete-all-cache-data"></a><span data-ttu-id="f0c75-145">すべてのキャッシュ データを削除する</span><span class="sxs-lookup"><span data-stu-id="f0c75-145">Delete all cache data</span></span>  

1.  <span data-ttu-id="f0c75-146">[アプリケーション**クリア**  >  **ストレージ] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="f0c75-146">Open **Application** > **Clear Storage**.</span></span>  
1.  <span data-ttu-id="f0c75-147">[キャッシュ ストレージ] **チェック ボックスが有効** になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0c75-147">Make sure that the **Cache Storage** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text="[キャッシュ ストレージ] チェック ボックス" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       <span data-ttu-id="f0c75-149">[ **キャッシュ ストレージ]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="f0c75-149">The **Cache Storage** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f0c75-150">[サイト **データのクリア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f0c75-150">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text="[サイト データのクリア] ボタン" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       <span data-ttu-id="f0c75-152">[ **サイト データのクリア]** ボタン</span><span class="sxs-lookup"><span data-stu-id="f0c75-152">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f0c75-153">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="f0c75-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "ネットワーク アクティビティのログ |Microsoft Docs"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュ | MDN"  

> [!NOTE]
> <span data-ttu-id="f0c75-158">このページの一部は、 [Google によって][GoogleSitePolicies] 作成および共有され、 [クリエイティブ コモンズ 4.0 インターナショナル ライセンス][CCA4IL]で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0c75-158">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f0c75-159">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="f0c75-159">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f0c75-161">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f0c75-161">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
