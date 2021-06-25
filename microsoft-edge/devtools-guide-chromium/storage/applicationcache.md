---
description: DevTools の [アプリケーション] パネルからアプリケーション キャッシュ データMicrosoft Edgeする方法。
title: DevTools を使用してアプリケーション キャッシュ データMicrosoft Edge表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 71e71555940d74f2071178be2e6daf0ec2f49dfd
ms.sourcegitcommit: d0a6959c5338cf1927093b4a9ed29a0bc0390b43
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "11615422"
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
# <a name="view-application-cache-data-with-microsoft-edge-devtools"></a><span data-ttu-id="cccb9-104">DevTools を使用してアプリケーション キャッシュ データMicrosoft Edge表示する</span><span class="sxs-lookup"><span data-stu-id="cccb9-104">View Application Cache data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="cccb9-105">アプリケーション キャッシュは非推奨であり、使用を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="cccb9-105">The Application Cache is deprecated, and you should avoid using it.</span></span>  <span data-ttu-id="cccb9-106">アプリケーション キャッシュ API が Web プラットフォームから削除されています。</span><span class="sxs-lookup"><span data-stu-id="cccb9-106">The Application Cache API is being removed from the web platform.</span></span>  <span data-ttu-id="cccb9-107">詳細については [、「Preparing for AppCache の削除」に移動します][WebDevAppcacheRemoval]。</span><span class="sxs-lookup"><span data-stu-id="cccb9-107">For more information, navigate to [Preparing for AppCache removal][WebDevAppcacheRemoval].</span></span>

<span data-ttu-id="cccb9-108">このガイドでは、アプリケーション キャッシュ リソースを調[Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使用[する方法を示][MDNWebAPIsWindowApplicationCache]します。</span><span class="sxs-lookup"><span data-stu-id="cccb9-108">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <a name="view-application-cache-data"></a><span data-ttu-id="cccb9-109">アプリケーション キャッシュ データの表示</span><span class="sxs-lookup"><span data-stu-id="cccb9-109">View Application Cache data</span></span>  

1.  <span data-ttu-id="cccb9-110">DevTools の上部で、[アプリケーション] ツール **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="cccb9-110">At the top of DevTools, choose the **Application** tool.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="cccb9-112">[ **マニフェスト]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="cccb9-112">The **Manifest** pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="cccb9-113">[アプリケーション キャッシュ **] セクションを展開** し、キャッシュを選択してリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="cccb9-113">Expand the **Application Cache** section and choose a cache to view the resources.</span></span>  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text="[アプリケーション キャッシュ] ウィンドウ" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       <span data-ttu-id="cccb9-115">[ **アプリケーション キャッシュ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="cccb9-115">The **Application Cache** pane</span></span>  
    :::image-end:::  

<span data-ttu-id="cccb9-116">テーブルの各行は、キャッシュされたリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="cccb9-116">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="cccb9-117">[ **種類]** 列は、リソース [のカテゴリを表します][MDNHTMLResourcesInAnApplicationCache]。</span><span class="sxs-lookup"><span data-stu-id="cccb9-117">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="cccb9-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cccb9-118">Category</span></span> | <span data-ttu-id="cccb9-119">詳細</span><span class="sxs-lookup"><span data-stu-id="cccb9-119">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="cccb9-120">このリソースはマニフェストに明示的に一覧表示されました。</span><span class="sxs-lookup"><span data-stu-id="cccb9-120">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="cccb9-121">URL は別のリソースのフォールバックです。</span><span class="sxs-lookup"><span data-stu-id="cccb9-121">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="cccb9-122">他のリソースの URL は DevTools に表示されません。</span><span class="sxs-lookup"><span data-stu-id="cccb9-122">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="cccb9-123">リソース `manifest` の属性は、キャッシュがリソースの親を示します。</span><span class="sxs-lookup"><span data-stu-id="cccb9-123">The `manifest` attribute on the resource indicates that the cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="cccb9-124">リソースがネットワークから取得する必要があるというマニフェストが指定されています。</span><span class="sxs-lookup"><span data-stu-id="cccb9-124">The manifest specified that the resource must come from the network.</span></span> |  

<!--todo:  replace "Master" phrasing if possible.  -->  

<span data-ttu-id="cccb9-125">表の下部には、ネットワーク接続とアプリケーション キャッシュの状態を示す状態アイコン **があります**。</span><span class="sxs-lookup"><span data-stu-id="cccb9-125">At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.</span></span>  <span data-ttu-id="cccb9-126">アプリケーション **キャッシュの状態** は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cccb9-126">The **Application Cache** may have the following states.</span></span>  

| <span data-ttu-id="cccb9-127">状態</span><span class="sxs-lookup"><span data-stu-id="cccb9-127">State</span></span> | <span data-ttu-id="cccb9-128">詳細</span><span class="sxs-lookup"><span data-stu-id="cccb9-128">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="cccb9-129">マニフェストがフェッチされ、更新プログラムがチェックされています。</span><span class="sxs-lookup"><span data-stu-id="cccb9-129">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="cccb9-130">リソースがキャッシュに追加されています。</span><span class="sxs-lookup"><span data-stu-id="cccb9-130">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="cccb9-131">キャッシュに新しい変更はありません。</span><span class="sxs-lookup"><span data-stu-id="cccb9-131">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="cccb9-132">キャッシュが削除中です。</span><span class="sxs-lookup"><span data-stu-id="cccb9-132">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="cccb9-133">新しいバージョンのキャッシュを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cccb9-133">A new version of the cache is available.</span></span> |  

<!-- links -->  
[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
<!-- external links: -->
[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーション キャッシュ 内のリソース|MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web API |MDN"  

[WebDevAppcacheRemoval]: https://web.dev/appcache-removal "AppCache の削除の準備|web.dev"  

> [!NOTE]
> <span data-ttu-id="cccb9-138">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="cccb9-138">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cccb9-139">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="cccb9-139">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="cccb9-141">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="cccb9-141">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
