---
description: DevTools の [アプリケーション] パネルからアプリケーション キャッシュ データMicrosoft Edgeする方法。
title: DevTools を使用してアプリケーション キャッシュ データMicrosoft Edge表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ec0d1a003e621ecc2220c3eb0d03992bcd8fffa1
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565023"
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
# <a name="view-application-cache-data-with-microsoft-edge-devtools"></a><span data-ttu-id="d72df-104">DevTools を使用してアプリケーション キャッシュ データMicrosoft Edge表示する</span><span class="sxs-lookup"><span data-stu-id="d72df-104">View Application Cache data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="d72df-105">アプリケーション キャッシュ API が [Web プラットフォームから削除されています][HTMLStandardOfflineWebApplications]。</span><span class="sxs-lookup"><span data-stu-id="d72df-105">The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].</span></span>  

<!--todo: Replace [HTMLStandardOfflineWebApplications] with [WebDevAppcacheRemoval].  -->  

<span data-ttu-id="d72df-106">このガイドでは、アプリケーション キャッシュ リソースを調[Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使用[する方法を示][MDNWebAPIsWindowApplicationCache]します。</span><span class="sxs-lookup"><span data-stu-id="d72df-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <a name="view-application-cache-data"></a><span data-ttu-id="d72df-107">アプリケーション キャッシュ データの表示</span><span class="sxs-lookup"><span data-stu-id="d72df-107">View Application Cache data</span></span>  

1.  <span data-ttu-id="d72df-108">DevTools の上部で、[アプリケーション] ツール **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="d72df-108">At the top of DevTools, choose the **Application** tool.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="d72df-110">[ **マニフェスト]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="d72df-110">The **Manifest** pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="d72df-111">[アプリケーション キャッシュ **] セクションを展開** し、キャッシュを選択してリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="d72df-111">Expand the **Application Cache** section and choose a cache to view the resources.</span></span>  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text="[アプリケーション キャッシュ] ウィンドウ" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       <span data-ttu-id="d72df-113">[ **アプリケーション キャッシュ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="d72df-113">The **Application Cache** pane</span></span>  
    :::image-end:::  

<span data-ttu-id="d72df-114">テーブルの各行は、キャッシュされたリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="d72df-114">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="d72df-115">[ **種類]** 列は、リソース [のカテゴリを表します][MDNHTMLResourcesInAnApplicationCache]。</span><span class="sxs-lookup"><span data-stu-id="d72df-115">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="d72df-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d72df-116">Category</span></span> | <span data-ttu-id="d72df-117">詳細</span><span class="sxs-lookup"><span data-stu-id="d72df-117">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="d72df-118">このリソースはマニフェストに明示的に一覧表示されました。</span><span class="sxs-lookup"><span data-stu-id="d72df-118">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="d72df-119">URL は別のリソースのフォールバックです。</span><span class="sxs-lookup"><span data-stu-id="d72df-119">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="d72df-120">他のリソースの URL は DevTools に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d72df-120">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="d72df-121">リソース `manifest` の属性は、キャッシュがリソースの親を示します。</span><span class="sxs-lookup"><span data-stu-id="d72df-121">The `manifest` attribute on the resource indicates that the cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="d72df-122">リソースがネットワークから取得する必要があるというマニフェストが指定されています。</span><span class="sxs-lookup"><span data-stu-id="d72df-122">The manifest specified that the resource must come from the network.</span></span> |  

<!--todo:  replace "Master" phrasing if possible.  -->  

<span data-ttu-id="d72df-123">表の下部には、ネットワーク接続とアプリケーション キャッシュの状態を示す状態アイコン **があります**。</span><span class="sxs-lookup"><span data-stu-id="d72df-123">At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.</span></span>  <span data-ttu-id="d72df-124">アプリケーション **キャッシュの状態** は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d72df-124">The **Application Cache** may have the following states.</span></span>  

| <span data-ttu-id="d72df-125">状態</span><span class="sxs-lookup"><span data-stu-id="d72df-125">State</span></span> | <span data-ttu-id="d72df-126">詳細</span><span class="sxs-lookup"><span data-stu-id="d72df-126">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="d72df-127">マニフェストがフェッチされ、更新プログラムがチェックされています。</span><span class="sxs-lookup"><span data-stu-id="d72df-127">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="d72df-128">リソースがキャッシュに追加されています。</span><span class="sxs-lookup"><span data-stu-id="d72df-128">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="d72df-129">キャッシュに新しい変更はありません。</span><span class="sxs-lookup"><span data-stu-id="d72df-129">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="d72df-130">キャッシュが削除中です。</span><span class="sxs-lookup"><span data-stu-id="d72df-130">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="d72df-131">新しいバージョンのキャッシュを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d72df-131">A new version of the cache is available.</span></span> |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "オフライン Web アプリケーション - HTML Standard"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーション キャッシュ 内のリソース|MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web API |MDN"  

[WebDevAppcacheRemoval]: https://web.dev/appcache-removal "AppCache の削除の準備|web.dev"  

> [!NOTE]
> <span data-ttu-id="d72df-137">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="d72df-137">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d72df-138">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="d72df-138">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="d72df-140">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="d72df-140">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
