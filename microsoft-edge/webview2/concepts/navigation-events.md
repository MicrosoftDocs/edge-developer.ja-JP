---
description: ナビゲーション
title: ナビゲーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 0df8e12acb11824006515ac711250d776d276e36
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895579"
---
# <span data-ttu-id="65878-104">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="65878-104">Navigation events</span></span>  

<span data-ttu-id="65878-105">通常のナビゲーションイベントのシーケンスは、、、、、ということです `NavigationStarting` `SourceChanged` `ContentLoading` `HistoryChanged` `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="65878-105">The normal sequence of navigation events is `NavigationStarting`, `SourceChanged`, `ContentLoading`, `HistoryChanged`, and then `NavigationCompleted`.</span></span>  <span data-ttu-id="65878-106">次のイベントは、各ナビゲーションでの WebView2 の状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="65878-106">The following events describe the state of WebView2 during each navigation.</span></span>  

| <span data-ttu-id="65878-107">動作</span><span class="sxs-lookup"><span data-stu-id="65878-107">Sequence</span></span> | <span data-ttu-id="65878-108">[Event Name]</span><span class="sxs-lookup"><span data-stu-id="65878-108">Event name</span></span> | <span data-ttu-id="65878-109">詳細</span><span class="sxs-lookup"><span data-stu-id="65878-109">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="65878-110">件</span><span class="sxs-lookup"><span data-stu-id="65878-110">1</span></span> | `NavigationStarting`  |  <span data-ttu-id="65878-111">WebView2 が移動を開始し、ナビゲーションの結果がネットワーク要求になります。</span><span class="sxs-lookup"><span data-stu-id="65878-111">WebView2 starts to navigate and the navigation results in a network request.</span></span>  <span data-ttu-id="65878-112">ホストは、イベント中に要求を許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="65878-112">The host is able to disallow the request during the event.</span></span>  |  
| <span data-ttu-id="65878-113">両面</span><span class="sxs-lookup"><span data-stu-id="65878-113">2</span></span> | `SourceChanged`  |  <span data-ttu-id="65878-114">WebView2 のソースが新しい URL に変更されます。</span><span class="sxs-lookup"><span data-stu-id="65878-114">The source of WebView2 changes to a new URL.</span></span>  <span data-ttu-id="65878-115">このイベントは、フラグメントナビゲーションなどのネットワーク要求が発生しないナビゲーションによって発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65878-115">The event may result from a navigation that does not cause a network request such as a fragment navigation.</span></span>  |  
| <span data-ttu-id="65878-116">-</span><span class="sxs-lookup"><span data-stu-id="65878-116">3</span></span> | `HistoryChanged`  |  <span data-ttu-id="65878-117">ナビゲーションの結果としての WebView2 の更新履歴。</span><span class="sxs-lookup"><span data-stu-id="65878-117">The history of WebView2 updates as a result of the navigation.</span></span>  |  
| <span data-ttu-id="65878-118">4d</span><span class="sxs-lookup"><span data-stu-id="65878-118">4</span></span> | `ContentLoading`  |  <span data-ttu-id="65878-119">WebView で、新しいページのコンテンツの読み込みが開始されます。</span><span class="sxs-lookup"><span data-stu-id="65878-119">WebView starts loading content for the new page.</span></span>  |  
| <span data-ttu-id="65878-120">個</span><span class="sxs-lookup"><span data-stu-id="65878-120">5</span></span> | `NavigationCompleted`  |  <span data-ttu-id="65878-121">WebView2 は、新しいページのコンテンツの読み込みを完了します。</span><span class="sxs-lookup"><span data-stu-id="65878-121">WebView2 completes loading content on the new page.</span></span>  |  

<span data-ttu-id="65878-122">`navigations`ナビゲーション ID \ (\) を使用して、新しいドキュメントごとに追跡 `NavigationId` します。</span><span class="sxs-lookup"><span data-stu-id="65878-122">Track `navigations` to each new document using the navigation ID \(`NavigationId`\).</span></span>  <span data-ttu-id="65878-123">`NavigationId`新しい文書へのナビゲーションが正常に完了するたびに、WebView の内容が変更されます。</span><span class="sxs-lookup"><span data-stu-id="65878-123">The `NavigationId` of WebView changes every time there is a successful navigation to a new document.</span></span>

:::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 ナビゲーションイベント" lightbox="../media/navigation-graph.png":::
   <span data-ttu-id="65878-125">Microsoft Edge WebView2 ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="65878-125">The Microsoft Edge WebView2 Navigation Events</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="65878-126">上の図は、それぞれのイベント arg で同じプロパティを持つナビゲーションイベントを示して `NavigationId` います。</span><span class="sxs-lookup"><span data-stu-id="65878-126">The previous figure represents navigation events with the same `NavigationId` property on the respective event arg.</span></span>  

 `Navigations` <span data-ttu-id="65878-127">イベントのインスタンスが異なるイベント `NavigationId` は、重複する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65878-127">events with different instances of `NavigationId` event may overlap.</span></span>  <span data-ttu-id="65878-128">たとえば、ナビゲーションを開始する場合は、関連するイベントを待つ必要があり `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="65878-128">For instance when you start a navigation, you have to wait for the related `NavigationStarting` event.</span></span>  <span data-ttu-id="65878-129">別のナビゲーションを開始した場合は、最初のナビゲートのイベントと2番目の移動のイベントが表示され、最初のナビゲーションにイベントが `NavigationStarting` `NavigationStarting` 続き、2番目のナビゲーションで該当する `NavigationCompleted` ナビゲーションイベントの残りすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65878-129">If you then start another navigation, you should see the `NavigationStarting` event for the first navigate followed by the `NavigationStarting` event for the second navigate, followed by the `NavigationCompleted` event for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span>  
 
 <span data-ttu-id="65878-130">エラーが発生した場合は、 `ContentLoading` ナビゲーションがエラーページに続いているかどうかによって、イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65878-130">In error cases there may or may not be a `ContentLoading` event depending on whether the navigation is continued to an error page.</span></span>  
 
 <span data-ttu-id="65878-131">HTTP リダイレクトの場合、1つの行に複数のイベントがあります。その場合は、次のイベント引数にプロパティが設定されていますが、値は `NavigationStarting` `IsRedirect` `NavigationId` 変わりません。</span><span class="sxs-lookup"><span data-stu-id="65878-131">In the case of an HTTP redirect, there are multiple `NavigationStarting` events in a row, where subsequent event args have the `IsRedirect` property set, however the `NavigationId` remains the same.</span></span>  
 
 <span data-ttu-id="65878-132">同じドキュメント (フラグメントへの移動など) では、 `navigations` イベントは発生せず、 `NavigationStarting` をインクリメントしません `NavigationId` 。</span><span class="sxs-lookup"><span data-stu-id="65878-132">Same document `navigations`, such as navigating to a fragment, do not result in the `NavigationStarting` event and do not increment the `NavigationId`.</span></span>  

<span data-ttu-id="65878-133">WebView でサブフレームの内部を監視またはキャンセルするには、と等価の、フレームに対応して `navigations` `FrameNavigationStarting` いないイベントと同じように動作するイベントを使用し `FrameNavigationCompleted` ます。</span><span class="sxs-lookup"><span data-stu-id="65878-133">To monitor or cancel `navigations` inside subframes in the WebView, use the `FrameNavigationStarting` and the `FrameNavigationCompleted` events which act just like the equivalent non-frame counterpart events.</span></span>  

<!-- links -->  
