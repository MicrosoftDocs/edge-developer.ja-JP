---
description: ナビゲーション
title: ナビゲーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/05/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: ac15b9f32a29c64bbdc2a7886fa654a2d71a5453
ms.sourcegitcommit: 4cea8cf99b5f12db9d2daba99bbf48f3ccc537fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314798"
---
# <span data-ttu-id="92b05-104">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="92b05-104">Navigation events</span></span>  

<span data-ttu-id="92b05-105">ナビゲーション イベントの通常のシーケンスは `NavigationStarting` 、 , , , , , and then `SourceChanged` `ContentLoading` `HistoryChanged` です `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="92b05-105">The normal sequence of navigation events is `NavigationStarting`, `SourceChanged`, `ContentLoading`, `HistoryChanged`, and then `NavigationCompleted`.</span></span>  <span data-ttu-id="92b05-106">次のイベントは、各ナビゲーション中の WebView2 の状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="92b05-106">The following events describe the state of WebView2 during each navigation.</span></span>  

| <span data-ttu-id="92b05-107">Sequence</span><span class="sxs-lookup"><span data-stu-id="92b05-107">Sequence</span></span> | <span data-ttu-id="92b05-108">[Event Name]</span><span class="sxs-lookup"><span data-stu-id="92b05-108">Event name</span></span> | <span data-ttu-id="92b05-109">詳細</span><span class="sxs-lookup"><span data-stu-id="92b05-109">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="92b05-110">1</span><span class="sxs-lookup"><span data-stu-id="92b05-110">1</span></span> | `NavigationStarting`  |  <span data-ttu-id="92b05-111">WebView2 は移動を開始し、ナビゲーションの結果はネットワーク要求になります。</span><span class="sxs-lookup"><span data-stu-id="92b05-111">WebView2 starts to navigate and the navigation results in a network request.</span></span>  <span data-ttu-id="92b05-112">ホストは、イベント中に要求を禁止できます。</span><span class="sxs-lookup"><span data-stu-id="92b05-112">The host is able to disallow the request during the event.</span></span>  |  
| <span data-ttu-id="92b05-113">2</span><span class="sxs-lookup"><span data-stu-id="92b05-113">2</span></span> | `SourceChanged`  |  <span data-ttu-id="92b05-114">WebView2 のソースが新しい URL に変更されます。</span><span class="sxs-lookup"><span data-stu-id="92b05-114">The source of WebView2 changes to a new URL.</span></span>  <span data-ttu-id="92b05-115">このイベントは、フラグメント ナビゲーションなどのネットワーク要求を引き起こしていないナビゲーションによって発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92b05-115">The event may result from a navigation that does not cause a network request such as a fragment navigation.</span></span>  |  
| <span data-ttu-id="92b05-116">3</span><span class="sxs-lookup"><span data-stu-id="92b05-116">3</span></span> | `HistoryChanged`  |  <span data-ttu-id="92b05-117">ナビゲーションの結果として WebView2 の履歴が更新されます。</span><span class="sxs-lookup"><span data-stu-id="92b05-117">The history of WebView2 updates as a result of the navigation.</span></span>  |  
| <span data-ttu-id="92b05-118">4</span><span class="sxs-lookup"><span data-stu-id="92b05-118">4</span></span> | `ContentLoading`  |  <span data-ttu-id="92b05-119">WebView2 は、新しいページのコンテンツの読み込みを開始します。</span><span class="sxs-lookup"><span data-stu-id="92b05-119">WebView2 starts loading content for the new page.</span></span>  |  
| <span data-ttu-id="92b05-120">5</span><span class="sxs-lookup"><span data-stu-id="92b05-120">5</span></span> | `NavigationCompleted`  |  <span data-ttu-id="92b05-121">WebView2 は、新しいページでのコンテンツの読み込みを完了します。</span><span class="sxs-lookup"><span data-stu-id="92b05-121">WebView2 completes loading content on the new page.</span></span>  |  

<span data-ttu-id="92b05-122">ナビゲーション ID \( \) を使用して、新しい `navigations` 各ドキュメントに `NavigationId` 追跡します。</span><span class="sxs-lookup"><span data-stu-id="92b05-122">Track `navigations` to each new document using the navigation ID \(`NavigationId`\).</span></span>  <span data-ttu-id="92b05-123">新 `NavigationId` しいドキュメントへのナビゲーションが正常に行うたび、WebView の変更点が変わります。</span><span class="sxs-lookup"><span data-stu-id="92b05-123">The `NavigationId` of WebView changes every time there is a successful navigation to a new document.</span></span>

:::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 ナビゲーション イベント" lightbox="../media/navigation-graph.png":::
   <span data-ttu-id="92b05-125">Microsoft Edge WebView2 ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="92b05-125">The Microsoft Edge WebView2 Navigation Events</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="92b05-126">前の図は、それぞれのイベント引数で同じ `NavigationId` プロパティを持つナビゲーション イベントを表しています。</span><span class="sxs-lookup"><span data-stu-id="92b05-126">The previous figure represents navigation events with the same `NavigationId` property on the respective event arg.</span></span>  

 `Navigations` <span data-ttu-id="92b05-127">イベントのインスタンスが異なると、 `NavigationId` イベントが重複する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92b05-127">events with different instances of `NavigationId` event may overlap.</span></span>  <span data-ttu-id="92b05-128">たとえば、ナビゲーションを開始するときに、関連するイベントを待つ必要 `NavigationStarting` があります。</span><span class="sxs-lookup"><span data-stu-id="92b05-128">For instance when you start a navigation, you have to wait for the related `NavigationStarting` event.</span></span>  <span data-ttu-id="92b05-129">その後、別のナビゲーションを開始すると、最初のナビゲーションのイベントが表示され、次に 2 番目のナビゲーションのイベントが表示され、次に最初のナビゲーションのイベントが表示され、次に 2 番目のナビゲーションに適したナビゲーション イベントの残りのすべてが表示されます。 `NavigationStarting` `NavigationStarting` `NavigationCompleted`</span><span class="sxs-lookup"><span data-stu-id="92b05-129">If you then start another navigation, you should see the `NavigationStarting` event for the first navigate followed by the `NavigationStarting` event for the second navigate, followed by the `NavigationCompleted` event for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span>  
 
 <span data-ttu-id="92b05-130">エラーの場合、ナビゲーションがエラー ページに続くかどうかによって、イベントが発生する場合とない `ContentLoading` 場合があります。</span><span class="sxs-lookup"><span data-stu-id="92b05-130">In error cases there may or may not be a `ContentLoading` event depending on whether the navigation is continued to an error page.</span></span>  
 
 <span data-ttu-id="92b05-131">HTTP リダイレクトの場合、1 行に複数のイベントがあります。後続のイベント引数にはプロパティが設定されます。ただし、イベントは `NavigationStarting` `IsRedirect` `NavigationId` 同じままです。</span><span class="sxs-lookup"><span data-stu-id="92b05-131">In the case of an HTTP redirect, there are multiple `NavigationStarting` events in a row, where subsequent event args have the `IsRedirect` property set, however the `NavigationId` remains the same.</span></span>  
 
 <span data-ttu-id="92b05-132">フラグメントへの移動など、同じドキュメントではイベントが発生し、インクリメント `navigations` `NavigationStarting` は行わりません `NavigationId` 。</span><span class="sxs-lookup"><span data-stu-id="92b05-132">Same document `navigations`, such as navigating to a fragment, do not result in the `NavigationStarting` event and do not increment the `NavigationId`.</span></span>  

<span data-ttu-id="92b05-133">WebView のサブフレーム内で監視またはキャンセルするには、対応する同等の非フレーム イベントと同様に機能するイベント `navigations` `FrameNavigationStarting` `FrameNavigationCompleted` とイベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="92b05-133">To monitor or cancel `navigations` inside subframes in the WebView, use the `FrameNavigationStarting` and the `FrameNavigationCompleted` events which act just like the equivalent non-frame counterpart events.</span></span>  

<!-- links -->  
