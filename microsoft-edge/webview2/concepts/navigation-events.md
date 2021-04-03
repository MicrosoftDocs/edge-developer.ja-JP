---
description: ナビゲーション
title: ナビゲーション |WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: e87994d6205f81e01385a131e17091d0c8b001d5
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11470845"
---
# <a name="navigation-events"></a><span data-ttu-id="cf1c8-104">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="cf1c8-104">Navigation events</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="cf1c8-105">サポートされているプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="cf1c8-105">Supported platforms:</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cf1c8-106">Win32, Windows Forms, WinUi, WPF</span><span class="sxs-lookup"><span data-stu-id="cf1c8-106">Win32, Windows Forms, WinUi, WPF</span></span>
   :::column-end:::
:::row-end:::  

<span data-ttu-id="cf1c8-107">ナビゲーション イベントは、WebView2 インスタンスに表示されるコンテンツに対して特定の非同期アクションが発生すると実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-107">Navigation events run when specific asynchronous actions occur to the content displayed in a WebView2 instance.</span></span>  <span data-ttu-id="cf1c8-108">たとえば、WebView2 ユーザーが新しい Web サイトに移動すると、ネイティブ コンテンツはイベントを使用して変更をリッスン `NavigationStarting` します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-108">For example, when a WebView2 user navigates to a new website, the native content listens for the change using `NavigationStarting` event.</span></span>  <span data-ttu-id="cf1c8-109">ナビゲーション アクションが完了すると、実行 `NavigationCompleted` されます。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-109">When the navigation action completes, `NavigationCompleted` runs.</span></span>  <span data-ttu-id="cf1c8-110">ナビゲーション イベントの良い例については [、「WebView2 の開始ガイド」に移動します][Webview2IndexGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-110">For a good example of navigation events, navigate to [WebView2 getting started guide][Webview2IndexGettingStarted].</span></span>  

<!--todo:  Move the relevant information out of the getting started guide to better focus the content and leave the most concise elements in the getting started guide.  -->   

<span data-ttu-id="cf1c8-111">ナビゲーション イベントの通常のシーケンス `NavigationStarting` は `SourceChanged` 、、、、、、 `ContentLoading` `HistoryChanged` です `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-111">The normal sequence of navigation events is `NavigationStarting`, `SourceChanged`, `ContentLoading`, `HistoryChanged`, and then `NavigationCompleted`.</span></span>  <span data-ttu-id="cf1c8-112">次のイベントは、各ナビゲーション中の WebView2 の状態について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-112">The following events describe the state of WebView2 during each navigation.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 ナビゲーション イベント" lightbox="../media/navigation-graph.png":::
         <span data-ttu-id="cf1c8-114">Microsoft Edge WebView2 ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="cf1c8-114">The Microsoft Edge WebView2 Navigation Events</span></span>  
      :::image-end:::  
      
      > [!NOTE]
      > <span data-ttu-id="cf1c8-115">図は、それぞれのイベント引数に同じ `NavigationId` プロパティを持つナビゲーション イベントを表します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-115">The figure represents navigation events with the same `NavigationId` property on the respective event argument.</span></span>  
   :::column-end:::
   :::column span="2":::
      | <span data-ttu-id="cf1c8-116">シーケンス</span><span class="sxs-lookup"><span data-stu-id="cf1c8-116">Sequence</span></span> | <span data-ttu-id="cf1c8-117">[Event Name]</span><span class="sxs-lookup"><span data-stu-id="cf1c8-117">Event name</span></span> | <span data-ttu-id="cf1c8-118">詳細</span><span class="sxs-lookup"><span data-stu-id="cf1c8-118">Details</span></span> |  
      |:--- |:--- |:--- |  
      | <span data-ttu-id="cf1c8-119">1</span><span class="sxs-lookup"><span data-stu-id="cf1c8-119">1</span></span> | `NavigationStarting`  |  <span data-ttu-id="cf1c8-120">WebView2 は移動を開始し、ナビゲーションはネットワーク要求になります。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-120">WebView2 starts to navigate and the navigation results in a network request.</span></span>  <span data-ttu-id="cf1c8-121">ホストは、イベント中に要求を禁止する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-121">The host may disallow the request during the event.</span></span>  |  
      | <span data-ttu-id="cf1c8-122">2</span><span class="sxs-lookup"><span data-stu-id="cf1c8-122">2</span></span> | `SourceChanged`  |  <span data-ttu-id="cf1c8-123">WebView2 のソースが新しい URL に変更されます。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-123">The source of WebView2 changes to a new URL.</span></span>  <span data-ttu-id="cf1c8-124">このイベントは、フラグメント ナビゲーションなどのネットワーク要求を引き起こしていないナビゲーション アクションによって発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-124">The event may result from a navigation action that does not cause a network request such as a fragment navigation.</span></span>  |  
      | <span data-ttu-id="cf1c8-125">3</span><span class="sxs-lookup"><span data-stu-id="cf1c8-125">3</span></span> | `ContentLoading`  |  <span data-ttu-id="cf1c8-126">WebView は、新しいページのコンテンツの読み込みを開始します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-126">WebView starts loading content for the new page.</span></span>  |  
      | <span data-ttu-id="cf1c8-127">4</span><span class="sxs-lookup"><span data-stu-id="cf1c8-127">4</span></span> | `HistoryChanged`  |  <span data-ttu-id="cf1c8-128">ナビゲーションによって、WebView2 の履歴が更新されます。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-128">The navigation causes the history of WebView2 to update.</span></span>  |  
      | <span data-ttu-id="cf1c8-129">5</span><span class="sxs-lookup"><span data-stu-id="cf1c8-129">5</span></span> | `NavigationCompleted`  |  <span data-ttu-id="cf1c8-130">WebView2 は、新しいページでのコンテンツの読み込みを完了します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-130">WebView2 completes loading content on the new page.</span></span>  |  
   :::column-end:::
:::row-end:::

<span data-ttu-id="cf1c8-131">ナビゲーション ID \( event\) を使用して、新しい各ドキュメントへのナビゲーション `NavigationId` イベントを追跡します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-131">Track navigation events to each new document using the navigation ID \(`NavigationId` event\).</span></span>  <span data-ttu-id="cf1c8-132">WebView `NavigationId` のイベントは、新しいドキュメントへの正常なナビゲーションが完了する度に変更されます。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-132">The `NavigationId` event of WebView changes every time a successful navigation to a new document completes.</span></span>  

 <span data-ttu-id="cf1c8-133">イベントのインスタンスが異なるナビゲーション `NavigationId` イベントが重複する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-133">Navigation events with different instances of `NavigationId` event may overlap.</span></span>  <span data-ttu-id="cf1c8-134">たとえば、ナビゲーション イベントを開始する場合は、関連するイベントを待つ必要 `NavigationStarting` があります。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-134">For instance, when you start a navigation event, you must wait for the related `NavigationStarting` event.</span></span>  <span data-ttu-id="cf1c8-135">その後、別のナビゲーションを開始すると、最初のナビゲーションのイベントが表示され、その後に 2 番目のナビゲーションのイベントが表示され、次に最初のナビゲーションのイベントが続き、2 番目のナビゲーションに適したナビゲーション イベントの残りの部分が表示されます。 `NavigationStarting` `NavigationStarting` `NavigationCompleted`</span><span class="sxs-lookup"><span data-stu-id="cf1c8-135">If you then start another navigation, you should see the `NavigationStarting` event for the first navigate followed by the `NavigationStarting` event for the second navigate, followed by the `NavigationCompleted` event for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span>  
 
 <span data-ttu-id="cf1c8-136">エラーの場合、ナビゲーションがエラー ページに続いているかどうかによって、イベントが発生する場合とできない `ContentLoading` 場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-136">In error cases, there may or may not be a `ContentLoading` event depending on whether the navigation is continued to an error page.</span></span>  
 
 <span data-ttu-id="cf1c8-137">HTTP リダイレクトが発生した場合、1 行に複数のイベントが発生し、後でイベントの引数にプロパティが設定されているが、イベント `NavigationStarting` `IsRedirect` は同 `NavigationId` じままです。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-137">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row, where later event arguments have the `IsRedirect` property set, however the `NavigationId` event remains the same.</span></span>  
 
 <span data-ttu-id="cf1c8-138">フラグメントへの移動など、同じドキュメント ナビゲーション イベントはイベントを発生しないし、イベント `NavigationStarting` をインクリメント `NavigationId` しない。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-138">Same document navigation events, such as navigating to a fragment, do not result in the `NavigationStarting` event and do not increment the `NavigationId` event.</span></span>  

<span data-ttu-id="cf1c8-139">WebView2 インスタンス内のサブフレーム内のナビゲーション イベントを監視またはキャンセルするには、同等のフレーム以外の対応するイベントと同様に機能するイベント `FrameNavigationStarting` `FrameNavigationCompleted` を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-139">To monitor or cancel navigation events inside subframes in a WebView2 instance, use the `FrameNavigationStarting` and `FrameNavigationCompleted` events that act just like the equivalent non-frame counterpart events.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cf1c8-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf1c8-140">See also</span></span>  

*   <span data-ttu-id="cf1c8-141">WebView2 の使用を開始するには [、「WebView2 Getting Started Guides guides」に][Webview2IndexGettingStarted] 移動します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-141">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2IndexGettingStarted] guides.</span></span>  
*   <span data-ttu-id="cf1c8-142">WebView2 機能の包括的な例については、GitHub の [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samples] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-142">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples repo][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>  
*   <span data-ttu-id="cf1c8-143">WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WpfWebview2]。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-143">For more detailed information about WebView2 APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2WpfWebview2].</span></span>  
*   <span data-ttu-id="cf1c8-144">WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="cf1c8-144">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="cf1c8-145">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="cf1c8-145">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGettingStarted]: ../index.md#getting-started "はじめに - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
