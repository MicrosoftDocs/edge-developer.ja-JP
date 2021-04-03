---
description: プロセス モデル
title: プロセス モデル |WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: 149234fe99485460f9d0c677b176a42d3b1e5050
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11470852"
---
# <a name="process-model"></a><span data-ttu-id="b8b17-104">プロセス モデル</span><span class="sxs-lookup"><span data-stu-id="b8b17-104">Process model</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="b8b17-105">サポートされているプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="b8b17-105">Supported platforms:</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b8b17-106">Win32, Windows Forms, WinUi, WPF</span><span class="sxs-lookup"><span data-stu-id="b8b17-106">Win32, Windows Forms, WinUi, WPF</span></span>
   :::column-end:::
:::row-end:::  

<span data-ttu-id="b8b17-107">WebView2 は、Microsoft Edge ブラウザーと同じプロセス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8b17-107">WebView2 uses the same process model as the Microsoft Edge browser.</span></span>  <span data-ttu-id="b8b17-108">ブラウザー プロセス モデルの詳細については、「Browser Architecture - モダン Web ブラウザーの内部 [を見る」に移動します][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]。</span><span class="sxs-lookup"><span data-stu-id="b8b17-108">For more information about the browser process model, navigate to [Browser Architecture - Inside look at modern web browser][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture].</span></span>  

<span data-ttu-id="b8b17-109">1 つのブラウザー プロセスは、その記事で説明されているレンダラー プロセスと他のユーティリティ プロセスに関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="b8b17-109">One browser process is associated with the renderer processes and other utility processes as described in that article.</span></span>  <span data-ttu-id="b8b17-110">さらに、WebView2 が指定されている場合、ホスト アプリ要求プロセスは WebView2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8b17-110">Additionally, if WebView2 is specified, the host app requesting processes use WebView2.</span></span>  

:::image type="complex" source="../media/process-model-1.png" alt-text="プロセス 1" lightbox="../media/process-model-1.png":::
   <span data-ttu-id="b8b17-112">プロセス 1</span><span class="sxs-lookup"><span data-stu-id="b8b17-112">Process 1</span></span>  
:::image-end:::  

<span data-ttu-id="b8b17-113">ブラウザー プロセスは、1 つのユーザー データ フォルダーにのみ関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="b8b17-113">A browser process is associated with only one user data folder.</span></span>  <span data-ttu-id="b8b17-114">要求プロセスでは、複数のユーザー データ フォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b8b17-114">A request process may specify more than one user data folder.</span></span>  <span data-ttu-id="b8b17-115">複数のユーザー データ フォルダーを指定する要求プロセスは、同じ数のブラウザー プロセスに関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="b8b17-115">A request process that specifies more than one user data folder is associated with the same number of browser processes.</span></span>  
<span data-ttu-id="b8b17-116">たとえば、2 つのユーザー データ フォルダーへのアクセスを要求する要求プロセスでは、2 つのブラウザー プロセスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8b17-116">For example, a request process that requests access to two user data folders uses two browser processes.</span></span>  

:::image type="complex" source="../media/process-model-2.png" alt-text="プロセス 2" lightbox="../media/process-model-2.png":::
   <span data-ttu-id="b8b17-118">プロセス 2</span><span class="sxs-lookup"><span data-stu-id="b8b17-118">Process 2</span></span>  
:::image-end:::  

<span data-ttu-id="b8b17-119">ブラウザー プロセスは、いくつかのレンダラー プロセスに関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="b8b17-119">A browser process is associated with several renderer processes.</span></span>  <span data-ttu-id="b8b17-120">WebView 2 インスタンスは、サービス フレームへのブラウザー プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8b17-120">A WebView 2 instance creates a browser process to service frames.</span></span>  <span data-ttu-id="b8b17-121">ブラウザー プロセスは、複数のフレームに関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8b17-121">A browser process may be associated with multiple frames.</span></span>  <span data-ttu-id="b8b17-122">ブラウザー プロセスは、WebView2 の異なるインスタンスに関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8b17-122">A browser process may be associated with different instances of WebView2.</span></span>  <span data-ttu-id="b8b17-123">レンダリング プロセスの数は、次の条件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b8b17-123">The number of render processes varies based on the following conditions.</span></span>  

*   <span data-ttu-id="b8b17-124">ブラウザーでの Web サイト分離機能の使用。</span><span class="sxs-lookup"><span data-stu-id="b8b17-124">Use of the website isolation feature in your browser.</span></span>  
*   <span data-ttu-id="b8b17-125">関連付けられた WebView2 インスタンスでレンダリングされる、切断された個別の原点の数。</span><span class="sxs-lookup"><span data-stu-id="b8b17-125">The number of distinct disconnected origins rendered in associated instances of WebView2.</span></span>  

<span data-ttu-id="b8b17-126">Web サイトの分離ブラウザー機能については、前のコンテンツで説明しています。</span><span class="sxs-lookup"><span data-stu-id="b8b17-126">The website isolation browser feature is described in the previous content.</span></span> 
<!--todo:  which previous content?  -->  
 

<span data-ttu-id="b8b17-127">ユーザー `CoreWebView2Environment` データ フォルダーとブラウザー プロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="b8b17-127">The `CoreWebView2Environment` represents a user data folder and browser process.</span></span>  <span data-ttu-id="b8b17-128">前述した Web サイトの分離に応じて WebView2 でさまざまなレンダラー プロセスが使用されるので、このプロセスは 1 つのプロセスセットに直接 `CoreWebView2` 対応しません。</span><span class="sxs-lookup"><span data-stu-id="b8b17-128">The `CoreWebView2` does not directly correspond to any one set of processes since various renderer processes are used by a WebView2 depending on website isolation as previously described.</span></span>  

<span data-ttu-id="b8b17-129">ブラウザーおよびレンダラー プロセスでのクラッシュやハングに対応するには、 `ProcessFailed` のイベントを使用します `CoreWebView2` 。</span><span class="sxs-lookup"><span data-stu-id="b8b17-129">To react to crashes and hangs in the browser and renderer processes, use the `ProcessFailed` event of `CoreWebView2`.</span></span>  

<span data-ttu-id="b8b17-130">関連付けられたブラウザーおよびレンダラー プロセスを安全にシャットダウンするには、 `Close` のメソッドを使用します `CoreWebView2Controller` 。</span><span class="sxs-lookup"><span data-stu-id="b8b17-130">To safely shut down associated browser and renderer processes, use the `Close` method of `CoreWebView2Controller`.</span></span>  

<span data-ttu-id="b8b17-131">WebView2 インスタンスの **DevTools** ウィンドウから [ブラウザー タスク マネージャー] ウィンドウを開く場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8b17-131">To open the Browser Task Manager window from the **DevTools** window of a WebView2 instance, complete on of the following actions.</span></span>  

*   <span data-ttu-id="b8b17-132">を選択します `Shift` + `Escape` 。</span><span class="sxs-lookup"><span data-stu-id="b8b17-132">Select `Shift`+`Escape`.</span></span>  
*   <span data-ttu-id="b8b17-133">DevTools ウィンドウのタイトル バーにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、 を選択します `Browser task manager` 。</span><span class="sxs-lookup"><span data-stu-id="b8b17-133">Hover on the DevTools window title bar, open the contextual menu \(right-click\), and choose `Browser task manager`.</span></span>  

<span data-ttu-id="b8b17-134">WebView2 のブラウザー プロセスに関連付けられているすべてのプロセスが、関連する目的を含めて表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8b17-134">All processes associated with the browser process of your WebView2 are displayed including associated purposes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b8b17-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8b17-135">See also</span></span>  

*   <span data-ttu-id="b8b17-136">WebView2 の使用を開始するには [、[WebView2 の開始][Webview2IndexGettingStarted] ガイド] ガイドに移動します。</span><span class="sxs-lookup"><span data-stu-id="b8b17-136">To Get Started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2IndexGettingStarted] guides.</span></span>  
*   <span data-ttu-id="b8b17-137">WebView2 機能の包括的な例については、GitHub の [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samples] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b8b17-137">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples repo][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>  
*   <span data-ttu-id="b8b17-138">WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WpfWebview2]。</span><span class="sxs-lookup"><span data-stu-id="b8b17-138">For more detailed information about WebView2 APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2WpfWebview2].</span></span>  
*   <span data-ttu-id="b8b17-139">WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="b8b17-139">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="b8b17-140">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="b8b17-140">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGettingStarted]: ../index.md#getting-started "はじめに - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]: https://developers.google.com/web/updates/2018/09/inside-browser-part1#browser-architecture "ブラウザーのアーキテクチャ - 最新の Web ブラウザーを見る (パート 1)"  
