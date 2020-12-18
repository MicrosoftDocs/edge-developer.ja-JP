---
description: Microsoft Edge DevTools の [アプリケーション] パネルからキャッシュ データを表示する方法について説明します。
title: Microsoft Edge DevTools を使用してキャッシュ データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 770001beb9b7eebd4dae76355a1f3e41a8021ecb
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230804"
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

# <span data-ttu-id="a96f3-104">Microsoft Edge DevTools を使用してキャッシュ データを表示する</span><span class="sxs-lookup"><span data-stu-id="a96f3-104">View cache data with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="a96f3-105">このガイドでは [、Microsoft Edge DevTools を使用して][MicrosoftEdgeDevTools] キャッシュ データを検査する方法 [について説明][MDNCache] します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Cache][MDNCache] data.</span></span>  

<span data-ttu-id="a96f3-106">HTTP キャッシュ データを検査 [しようとしている][MDNHTTPCaching] 場合、これは必要なガイドではありません。</span><span class="sxs-lookup"><span data-stu-id="a96f3-106">If you are trying to inspect [HTTP cache][MDNHTTPCaching] data, this is not the guide you want.</span></span>  <span data-ttu-id="a96f3-107">ネットワーク ログの [ **サイズ** ] 列の情報を **探します**。</span><span class="sxs-lookup"><span data-stu-id="a96f3-107">Look for the information in the **Size** column of the **Network Log**.</span></span>  <span data-ttu-id="a96f3-108">[ネットワーク アクティビティ [のログ] に移動します][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="a96f3-108">Navigate to [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

## <span data-ttu-id="a96f3-109">キャッシュ データを表示する</span><span class="sxs-lookup"><span data-stu-id="a96f3-109">View cache data</span></span>  

1.  <span data-ttu-id="a96f3-110">[アプリケーション **] タブを** 選択して、[アプリケーション] パネル **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="a96f3-110">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="a96f3-111">通常 **、マニフェスト** ウィンドウは既定で開きます。</span><span class="sxs-lookup"><span data-stu-id="a96f3-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="a96f3-113">マニフェスト**ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="a96f3-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a96f3-114">[キャッシュ ストレージ **] セクションを展開** して、使用可能なキャッシュを表示します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-114">Expand the **Cache Storage** section to view available caches.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="使用可能なキャッシュ" lightbox="../media/storage-application-cache-storage.msft.png":::
       <span data-ttu-id="a96f3-116">使用可能なキャッシュ</span><span class="sxs-lookup"><span data-stu-id="a96f3-116">Available caches</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a96f3-117">キャッシュを選択してコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-117">Select a cache to view the contents.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-root-headers.msft.png" alt-text="キャッシュの内容を表示する" lightbox="../media/storage-application-cache-storage-domain-root-headers.msft.png":::
       <span data-ttu-id="a96f3-119">キャッシュの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="a96f3-119">View the contents of a cache</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a96f3-120">表の下のセクションで HTTP ヘッダーを表示するリソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-120">Select a resource to view the HTTP headers in the section below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-index-headers.msft.png" alt-text="リソースの HTTP ヘッダーを表示する" lightbox="../media/storage-application-cache-storage-index-headers.msft.png":::
       <span data-ttu-id="a96f3-122">リソースの HTTP ヘッダーを表示する</span><span class="sxs-lookup"><span data-stu-id="a96f3-122">View the HTTP headers of a resource</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a96f3-123">[ **プレビュー] を** 選択して、リソースのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-123">Choose **Preview** to view the content of a resource.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-js-preview.msft.png" alt-text="リソースのコンテンツを表示する" lightbox="../media/storage-application-cache-storage-domain-js-preview.msft.png":::
       <span data-ttu-id="a96f3-125">リソースのコンテンツを表示する</span><span class="sxs-lookup"><span data-stu-id="a96f3-125">View the content of a resource</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a96f3-126">リソースを更新する</span><span class="sxs-lookup"><span data-stu-id="a96f3-126">Refresh a resource</span></span>  

1.  <span data-ttu-id="a96f3-127">[キャッシュのデータを表示します](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="a96f3-127">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="a96f3-128">更新するリソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-128">Select the resource that you want to refresh.</span></span>  <span data-ttu-id="a96f3-129">DevTools によって強調表示され、選択された状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="a96f3-129">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="更新するリソースを選択する" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       <span data-ttu-id="a96f3-131">更新するリソースを選択する</span><span class="sxs-lookup"><span data-stu-id="a96f3-131">Select a resource to refresh</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a96f3-132">Choose **Refresh** \( ![ Refresh ][ImageRefreshIcon] \).</span><span class="sxs-lookup"><span data-stu-id="a96f3-132">Choose **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <span data-ttu-id="a96f3-133">リソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a96f3-133">Filter resources</span></span>  

1.  <span data-ttu-id="a96f3-134">[キャッシュのデータを表示します](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="a96f3-134">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="a96f3-135">[パス **でフィルター]** テキスト ボックスを使用して、指定したパスと一致しないリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-135">Use the **Filter by Path** text box to filter out any resources that do not match the path that you provide.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="指定したパスと一致しないリソースをフィルター処理する" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       <span data-ttu-id="a96f3-137">指定したパスと一致しないリソースをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a96f3-137">Filter out resources that do not match the specified path</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a96f3-138">リソースの削除</span><span class="sxs-lookup"><span data-stu-id="a96f3-138">Delete a resource</span></span>  

1.  <span data-ttu-id="a96f3-139">[キャッシュのデータを表示します](#view-cache-data)。</span><span class="sxs-lookup"><span data-stu-id="a96f3-139">[View the data for a cache](#view-cache-data).</span></span>  
1.  <span data-ttu-id="a96f3-140">削除するリソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-140">Select the resource that you want to delete.</span></span>  <span data-ttu-id="a96f3-141">DevTools によって強調表示され、選択された状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="a96f3-141">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="削除するリソースを選択する" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       <span data-ttu-id="a96f3-143">削除するリソースを選択する</span><span class="sxs-lookup"><span data-stu-id="a96f3-143">Select a resource to delete</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a96f3-144">Choose **Delete Selected** \( ![ Delete Selected ][ImageDeleteIcon] \).</span><span class="sxs-lookup"><span data-stu-id="a96f3-144">Choose **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="a96f3-145">すべてのキャッシュ データを削除する</span><span class="sxs-lookup"><span data-stu-id="a96f3-145">Delete all cache data</span></span>  

1.  <span data-ttu-id="a96f3-146">アプリケーションクリア**ストレージ**  >  **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="a96f3-146">Open **Application** > **Clear Storage**.</span></span>  
1.  <span data-ttu-id="a96f3-147">[キャッシュ ストレージ] **チェック ボックスが有効** になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a96f3-147">Make sure that the **Cache Storage** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text="[キャッシュ ストレージ] チェック ボックス" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       <span data-ttu-id="a96f3-149">[ **キャッシュ ストレージ]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="a96f3-149">The **Cache Storage** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a96f3-150">[サイト **データのクリア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a96f3-150">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text="[サイト データのクリア] ボタン" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       <span data-ttu-id="a96f3-152">[ **サイト データのクリア]** ボタン</span><span class="sxs-lookup"><span data-stu-id="a96f3-152">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a96f3-153">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a96f3-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "ネットワーク アクティビティをログに記録する |Microsoft Docs"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "Cache |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュ | MDN"  

> [!NOTE]
> <span data-ttu-id="a96f3-158">このページの一部は、 [Google によって][GoogleSitePolicies] 作成および共有され、 [クリエイティブ コモンズ 4.0 インターナショナル ライセンス][CCA4IL]で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a96f3-158">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a96f3-159">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="a96f3-159">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/cache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a96f3-161">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a96f3-161">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
