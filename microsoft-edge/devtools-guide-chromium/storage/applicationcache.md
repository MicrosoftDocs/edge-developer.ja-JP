---
title: Microsoft Edge DevTools を使ってアプリケーションキャッシュデータを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6ce3087e9c719efbcf4d9ebceb860edd0ed0c3b6
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612096"
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





# <span data-ttu-id="07d6a-103">Microsoft Edge DevTools を使ってアプリケーションキャッシュデータを表示する</span><span class="sxs-lookup"><span data-stu-id="07d6a-103">View Application Cache Data With Microsoft Edge DevTools</span></span>   



> [!WARNING]
> <span data-ttu-id="07d6a-104">アプリケーションキャッシュ API が[web プラットフォームから削除されて][HTMLStandardOfflineWebApplications]います。</span><span class="sxs-lookup"><span data-stu-id="07d6a-104">The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].</span></span>  

<span data-ttu-id="07d6a-105">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って[アプリケーションキャッシュ][MDNWebAPIsWindowApplicationCache]のリソースを検査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07d6a-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <span data-ttu-id="07d6a-106">アプリケーションキャッシュデータの表示</span><span class="sxs-lookup"><span data-stu-id="07d6a-106">View Application Cache Data</span></span>   

1.  <span data-ttu-id="07d6a-107">[**ソース**] タブを選択して、[**ソース**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="07d6a-107">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="07d6a-108">通常、**マニフェスト**ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="07d6a-108">The **Manifest** pane usually opens by default.</span></span>  
    
    > ##### <span data-ttu-id="07d6a-109">図 1</span><span class="sxs-lookup"><span data-stu-id="07d6a-109">Figure 1</span></span>  
    > <span data-ttu-id="07d6a-110">マニフェストウィンドウ</span><span class="sxs-lookup"><span data-stu-id="07d6a-110">The Manifest pane</span></span>  
    > ![マニフェストウィンドウ][ImageManifestPane]  

1.  <span data-ttu-id="07d6a-112">[**アプリケーションキャッシュ**] セクションを展開して、リソースを表示するキャッシュをクリックします。</span><span class="sxs-lookup"><span data-stu-id="07d6a-112">Expand the **Application Cache** section and click a cache to view the resources.</span></span>  
    
    > ##### <span data-ttu-id="07d6a-113">図 2</span><span class="sxs-lookup"><span data-stu-id="07d6a-113">Figure 2</span></span>  
    > <span data-ttu-id="07d6a-114">[アプリケーションキャッシュ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="07d6a-114">The Application Cache pane</span></span>  
    > ![[アプリケーションキャッシュ] ウィンドウ][ImageApplicationCachePane]  

<span data-ttu-id="07d6a-116">表の各行は、キャッシュされたリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="07d6a-116">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="07d6a-117">[**種類**] 列は[リソースのカテゴリ][MDNHTMLResourcesInAnApplicationCache]を表します。</span><span class="sxs-lookup"><span data-stu-id="07d6a-117">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="07d6a-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="07d6a-118">Category</span></span> | <span data-ttu-id="07d6a-119">詳細</span><span class="sxs-lookup"><span data-stu-id="07d6a-119">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="07d6a-120">このリソースはマニフェストに明示的に含まれていました。</span><span class="sxs-lookup"><span data-stu-id="07d6a-120">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="07d6a-121">URL は、別のリソースのフォールバックです。</span><span class="sxs-lookup"><span data-stu-id="07d6a-121">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="07d6a-122">その他のリソースの URL は、DevTools には記載されていません。</span><span class="sxs-lookup"><span data-stu-id="07d6a-122">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="07d6a-123">リソースの属性によっ `manifest` て、このキャッシュがリソースの親であることが示されました。</span><span class="sxs-lookup"><span data-stu-id="07d6a-123">The `manifest` attribute on the resource indicated that this cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="07d6a-124">このリソースがネットワークから取得する必要があることを指定するマニフェスト。</span><span class="sxs-lookup"><span data-stu-id="07d6a-124">The manifest specified that this resource must come from the network.</span></span> |  

<span data-ttu-id="07d6a-125">表の下部には、ネットワーク接続とアプリケーションキャッシュの状態を示す状態アイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="07d6a-125">At the bottom of the table there are status icons indicating your network connection and the status of the Application Cache.</span></span>  <span data-ttu-id="07d6a-126">アプリケーションキャッシュには、次のような状態があります。</span><span class="sxs-lookup"><span data-stu-id="07d6a-126">The Application Cache may have the following states.</span></span>  

| <span data-ttu-id="07d6a-127">状態</span><span class="sxs-lookup"><span data-stu-id="07d6a-127">State</span></span> | <span data-ttu-id="07d6a-128">詳細</span><span class="sxs-lookup"><span data-stu-id="07d6a-128">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="07d6a-129">マニフェストが取得され、更新プログラムがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="07d6a-129">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="07d6a-130">キャッシュにリソースが追加されています。</span><span class="sxs-lookup"><span data-stu-id="07d6a-130">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="07d6a-131">キャッシュには新しい変更はありません。</span><span class="sxs-lookup"><span data-stu-id="07d6a-131">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="07d6a-132">キャッシュを削除しています。</span><span class="sxs-lookup"><span data-stu-id="07d6a-132">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="07d6a-133">キャッシュの新しいバージョンが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="07d6a-133">A new version of the cache is available.</span></span> |  

<!--   -->  



<!-- image links -->  

[ImageManifestPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageApplicationCachePane]: /microsoft-edge/devtools-guide-chromium/media/storage-cache-pane-cache-storage-resources.msft.png "図 2: アプリケーションキャッシュのウィンドウ"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "オフライン Web アプリケーション-HTML 標準"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーションキャッシュのリソース |MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window. applicationCache-Web Api |MDN"  

> [!NOTE]
> <span data-ttu-id="07d6a-140">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="07d6a-140">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="07d6a-141">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="07d6a-141">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="07d6a-143">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="07d6a-143">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
