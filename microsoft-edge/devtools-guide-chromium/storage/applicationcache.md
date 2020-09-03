---
description: Microsoft Edge DevTools のアプリケーションパネルからアプリケーションキャッシュデータを表示する方法について説明します。
title: Microsoft Edge DevTools を使ってアプリケーションキャッシュデータを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ed742f24900786c3c5b31ec2a026ddbf9d16ccb6
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993325"
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

# <span data-ttu-id="6cf6c-104">Microsoft Edge DevTools を使ってアプリケーションキャッシュデータを表示する</span><span class="sxs-lookup"><span data-stu-id="6cf6c-104">View Application Cache data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="6cf6c-105">アプリケーションキャッシュ API が [web プラットフォームから削除されて][HTMLStandardOfflineWebApplications]います。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-105">The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].</span></span>  

<span data-ttu-id="6cf6c-106">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って [アプリケーションキャッシュ][MDNWebAPIsWindowApplicationCache] のリソースを検査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <span data-ttu-id="6cf6c-107">アプリケーションキャッシュデータの表示</span><span class="sxs-lookup"><span data-stu-id="6cf6c-107">View Application Cache data</span></span>  

1.  <span data-ttu-id="6cf6c-108">[ **ソース** ] タブを選択して、[ **ソース** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-108">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="6cf6c-109">通常、 **マニフェスト** ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-109">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="6cf6c-111">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="6cf6c-111">The **Manifest** pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="6cf6c-112">[ **アプリケーションキャッシュ** ] セクションを展開し、リソースを表示するキャッシュを選択します。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-112">Expand the **Application Cache** section and choose a cache to view the resources.</span></span>  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text="[アプリケーションキャッシュ] ウィンドウ" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       <span data-ttu-id="6cf6c-114">[ **アプリケーションキャッシュ** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="6cf6c-114">The **Application Cache** pane</span></span>  
    :::image-end:::  

<span data-ttu-id="6cf6c-115">表の各行は、キャッシュされたリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-115">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="6cf6c-116">[ **種類** ] 列は [リソースのカテゴリ][MDNHTMLResourcesInAnApplicationCache]を表します。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-116">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="6cf6c-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="6cf6c-117">Category</span></span> | <span data-ttu-id="6cf6c-118">詳細</span><span class="sxs-lookup"><span data-stu-id="6cf6c-118">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="6cf6c-119">このリソースはマニフェストに明示的に含まれていました。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-119">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="6cf6c-120">URL は、別のリソースのフォールバックです。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-120">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="6cf6c-121">その他のリソースの URL は、DevTools には記載されていません。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-121">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="6cf6c-122">`manifest`リソースの属性は、キャッシュがリソースの親であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-122">The `manifest` attribute on the resource indicates that the cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="6cf6c-123">リソースがネットワークから取得される必要があることを示すマニフェスト。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-123">The manifest specified that the resource must come from the network.</span></span> |  

<!--todo:  replace "Master" phrasing if possible.  -->  

<span data-ttu-id="6cf6c-124">表の下部には、ネットワーク接続と **アプリケーションキャッシュ**の状態を示す状態アイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-124">At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.</span></span>  <span data-ttu-id="6cf6c-125">**アプリケーションキャッシュ**には、次のような状態があります。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-125">The **Application Cache** may have the following states.</span></span>  

| <span data-ttu-id="6cf6c-126">状態</span><span class="sxs-lookup"><span data-stu-id="6cf6c-126">State</span></span> | <span data-ttu-id="6cf6c-127">詳細</span><span class="sxs-lookup"><span data-stu-id="6cf6c-127">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="6cf6c-128">マニフェストが取得され、更新プログラムがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-128">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="6cf6c-129">キャッシュにリソースが追加されています。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-129">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="6cf6c-130">キャッシュには新しい変更はありません。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-130">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="6cf6c-131">キャッシュを削除しています。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-131">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="6cf6c-132">キャッシュの新しいバージョンが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-132">A new version of the cache is available.</span></span> |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "オフライン Web アプリケーション-HTML 標準"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーションキャッシュのリソース |MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window. applicationCache-Web Api |MDN"  

> [!NOTE]
> <span data-ttu-id="6cf6c-137">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-137">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6cf6c-138">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-138">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6cf6c-140">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6cf6c-140">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
