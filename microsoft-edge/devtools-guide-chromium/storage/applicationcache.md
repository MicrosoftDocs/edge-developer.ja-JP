---
description: Microsoft Edge DevTools の [アプリケーション] パネルからアプリケーション キャッシュ データを表示する方法について説明します。
title: Microsoft Edge DevTools を使用してアプリケーション キャッシュ データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3d73047a8332e4d6cae5f7411f968a7dfe4c3738
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230783"
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

# <span data-ttu-id="0c1a0-104">Microsoft Edge DevTools を使用してアプリケーション キャッシュ データを表示する</span><span class="sxs-lookup"><span data-stu-id="0c1a0-104">View Application Cache data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="0c1a0-105">アプリケーション キャッシュ API は [、Web プラットフォームから削除されています][HTMLStandardOfflineWebApplications]。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-105">The Application Cache API is [being removed from the web platform][HTMLStandardOfflineWebApplications].</span></span>  

<span data-ttu-id="0c1a0-106">このガイドでは [、Microsoft Edge DevTools を使用して][MicrosoftEdgeDevTools] アプリケーション キャッシュ リソースを [検査する方法を示][MDNWebAPIsWindowApplicationCache] します。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect [Application Cache][MDNWebAPIsWindowApplicationCache] resources.</span></span>  

## <span data-ttu-id="0c1a0-107">アプリケーション キャッシュ データの表示</span><span class="sxs-lookup"><span data-stu-id="0c1a0-107">View Application Cache data</span></span>  

1.  <span data-ttu-id="0c1a0-108">[ソース **] タブを** 選択して 、[ソース] パネル **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-108">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="0c1a0-109">通常 **、マニフェスト** ウィンドウは既定で開きます。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-109">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="0c1a0-111">マニフェスト**ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="0c1a0-111">The **Manifest** pane</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="0c1a0-112">[アプリケーション キャッシュ **] セクションを展開** し、リソースを表示するキャッシュを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-112">Expand the **Application Cache** section and choose a cache to view the resources.</span></span>  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text="[アプリケーション キャッシュ] ウィンドウ" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       <span data-ttu-id="0c1a0-114">[ **アプリケーション キャッシュ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0c1a0-114">The **Application Cache** pane</span></span>  
    :::image-end:::  

<span data-ttu-id="0c1a0-115">テーブルの各行は、キャッシュされたリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-115">Each row of the table represents a cached resource.</span></span>  

<span data-ttu-id="0c1a0-116">[ **種類]** 列は、リソース [のカテゴリを表します][MDNHTMLResourcesInAnApplicationCache]。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-116">The **Type** column represents the [category of the resource][MDNHTMLResourcesInAnApplicationCache].</span></span>  

| <span data-ttu-id="0c1a0-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="0c1a0-117">Category</span></span> | <span data-ttu-id="0c1a0-118">詳細</span><span class="sxs-lookup"><span data-stu-id="0c1a0-118">Details</span></span> |  
|:--- |:--- |  
| `Explicit` | <span data-ttu-id="0c1a0-119">このリソースは、マニフェストに明示的に一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-119">This resource was explicitly listed in the manifest.</span></span> |  
| `Fallback` | <span data-ttu-id="0c1a0-120">URL は別のリソースのフォールバックです。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-120">The URL is a fallback for another resource.</span></span>  <span data-ttu-id="0c1a0-121">他のリソースの URL は DevTools には表示されません。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-121">The URL of the other resource is not listed in DevTools.</span></span> |  
| `Master` | <span data-ttu-id="0c1a0-122">リソース `manifest` の属性は、キャッシュがリソースの親を示します。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-122">The `manifest` attribute on the resource indicates that the cache is the parent of the resource.</span></span> |  
| `Network` | <span data-ttu-id="0c1a0-123">リソースがネットワークから取得される必要があるというマニフェスト。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-123">The manifest specified that the resource must come from the network.</span></span> |  

<!--todo:  replace "Master" phrasing if possible.  -->  

<span data-ttu-id="0c1a0-124">表の下部には、ネットワーク接続とアプリケーション キャッシュの状態を示すステータス アイコン **があります**。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-124">At the bottom of the table there are status icons indicating your network connection and the status of the **Application Cache**.</span></span>  <span data-ttu-id="0c1a0-125">アプリケーション **キャッシュの** 状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-125">The **Application Cache** may have the following states.</span></span>  

| <span data-ttu-id="0c1a0-126">状態</span><span class="sxs-lookup"><span data-stu-id="0c1a0-126">State</span></span> | <span data-ttu-id="0c1a0-127">詳細</span><span class="sxs-lookup"><span data-stu-id="0c1a0-127">Details</span></span> |  
|:--- |:--- |  
| `CHECKING` | <span data-ttu-id="0c1a0-128">マニフェストがフェッチされ、更新プログラムが確認されています。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-128">The manifest is being fetched and checked for updates.</span></span> |  
| `DOWNLOADING` | <span data-ttu-id="0c1a0-129">リソースがキャッシュに追加されています。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-129">Resources are being added to the cache.</span></span> |  
| `IDLE` | <span data-ttu-id="0c1a0-130">キャッシュには新しい変更はありません。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-130">The cache has no new changes.</span></span> |  
| `OBSOLETE` | <span data-ttu-id="0c1a0-131">キャッシュが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-131">The cache is being deleted.</span></span> |  
| `UPDATEREADY` |  <span data-ttu-id="0c1a0-132">新しいバージョンのキャッシュを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-132">A new version of the cache is available.</span></span> |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "オフライン Web アプリケーション - HTML 標準"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーション キャッシュ内のリソース |MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web API |MDN"  

> [!NOTE]
> <span data-ttu-id="0c1a0-137">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-137">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0c1a0-138">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-138">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0c1a0-140">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0c1a0-140">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
