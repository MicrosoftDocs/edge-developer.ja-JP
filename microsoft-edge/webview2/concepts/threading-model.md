---
description: スレッド化
title: スレッド モデル |WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: 9a7ce3d66e53b832d4430afb153e6539d97e5db7
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535609"
---
# <a name="threading-model"></a><span data-ttu-id="3de1a-104">スレッド化</span><span class="sxs-lookup"><span data-stu-id="3de1a-104">Threading model</span></span> 

:::row:::
   :::column span="1":::
      <span data-ttu-id="3de1a-105">サポートされているプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="3de1a-105">Supported platforms:</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3de1a-106">Win32, Windows Forms, WinUi, WPF</span><span class="sxs-lookup"><span data-stu-id="3de1a-106">Win32, Windows Forms, WinUi, WPF</span></span>
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3de1a-107">WebView2 コントロールはコンポーネント オブジェクト モデル [(COM)][WindowsWin32ComTheComponentObjectModel] に基づいており、単一スレッド アパートメント [(STA) スレッドで実行する必要][WindowsWin32ComSingleThreadedApartments] があります。</span><span class="sxs-lookup"><span data-stu-id="3de1a-107">The WebView2 control is based on the [Component Object Model (COM)][WindowsWin32ComTheComponentObjectModel] and must run on a [Single Threaded Apartments (STA)][WindowsWin32ComSingleThreadedApartments] thread.</span></span>  

## <a name="thread-safety"></a><span data-ttu-id="3de1a-108">スレッド セーフティ</span><span class="sxs-lookup"><span data-stu-id="3de1a-108">Thread safety</span></span>  

<span data-ttu-id="3de1a-109">WebView2 は UI スレッド上に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de1a-109">The WebView2 must be created on a UI thread.</span></span>  <span data-ttu-id="3de1a-110">具体的には、メッセージ ポンプを持つスレッドです。</span><span class="sxs-lookup"><span data-stu-id="3de1a-110">Specifically, a thread with a message pump.</span></span>  <span data-ttu-id="3de1a-111">そのスレッドですべてのコールバックが発生し、WebView2 への要求は、そのスレッドで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de1a-111">All callbacks occur on that thread and requests into the WebView2 must be done on that thread.</span></span>  <span data-ttu-id="3de1a-112">別のスレッドから WebView2 を使用しても安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="3de1a-112">It isn't safe to use the WebView2 from another thread.</span></span>  

<span data-ttu-id="3de1a-113">唯一の例外は、 の `Content` プロパティです `CoreWebView2WebResourceRequest` 。</span><span class="sxs-lookup"><span data-stu-id="3de1a-113">The only exception is for the `Content` property of `CoreWebView2WebResourceRequest`.</span></span>  <span data-ttu-id="3de1a-114">プロパティ `Content` ストリームは、バックグラウンド スレッドから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3de1a-114">The `Content` property stream is read from a background thread.</span></span>  <span data-ttu-id="3de1a-115">UI スレッドのパフォーマンス低下を防ぐために、ストリームはアジャイルまたはバックグラウンド STA から作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de1a-115">The stream should be agile or be created from a background STA to prevent performance degradation to the UI thread.</span></span>  

## <a name="re-entrancy"></a><span data-ttu-id="3de1a-116">再エントランシー</span><span class="sxs-lookup"><span data-stu-id="3de1a-116">Re-entrancy</span></span>  

<span data-ttu-id="3de1a-117">イベント ハンドラーや完了ハンドラーを含むコールバックは、シリアルに実行されます。</span><span class="sxs-lookup"><span data-stu-id="3de1a-117">Callbacks including event handlers and completion handlers run serially.</span></span>  
<span data-ttu-id="3de1a-118">イベント ハンドラーを実行してメッセージ ループを開始した後、イベント ハンドラーまたは完了コールバックを再入可能な方法で実行できません。</span><span class="sxs-lookup"><span data-stu-id="3de1a-118">After you run an event handler and begin a message loop, you're unable to run any event handler or completion callback in a re-entrant manner.</span></span>  

## <a name="deferrals"></a><span data-ttu-id="3de1a-119">遅延</span><span class="sxs-lookup"><span data-stu-id="3de1a-119">Deferrals</span></span>  

<span data-ttu-id="3de1a-120">一部の WebView2 イベントは、関連するイベント引数に設定された値を読み取り、イベント ハンドラーの完了後にいくつかのアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3de1a-120">Some WebView2 events read values set on the related event arguments or start some action after the event handler completes.</span></span>  <span data-ttu-id="3de1a-121">このようなイベント ハンドラーを非同期操作で実行する必要がある場合は、関連付けられたイベントのイベント引数でメソッド `GetDeferral` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3de1a-121">If you also need to run an asynchronous operation such an event handler, use the `GetDeferral` method on the event arguments of the associated events.</span></span>  <span data-ttu-id="3de1a-122">返されるオブジェクトは、イベント ハンドラーが要求されるまで、イベント ハンドラーが `Deferral` `Complete` 完全と見なされません `Deferral` 。</span><span class="sxs-lookup"><span data-stu-id="3de1a-122">The returned `Deferral` object ensures the event handler isn't considered complete until the `Complete` method of the `Deferral` is requested.</span></span>  

<span data-ttu-id="3de1a-123">たとえば、イベント ハンドラーが完了すると、子ウィンドウとして接続するイベント `NewWindowRequested` `CoreWebView2` を提供できます。</span><span class="sxs-lookup"><span data-stu-id="3de1a-123">For instance, you may use the `NewWindowRequested` event to provide a `CoreWebView2` to connect as a child window when the event handler completes.</span></span>  <span data-ttu-id="3de1a-124">ただし、非同期的に作成する必要がある場合 `CoreWebView2` は、 で `GetDeferral` メソッドを要求します `NewWindowRequestedEventArgs` 。</span><span class="sxs-lookup"><span data-stu-id="3de1a-124">But if you need to asynchronously create the `CoreWebView2`, request the `GetDeferral` method on the `NewWindowRequestedEventArgs`.</span></span>  <span data-ttu-id="3de1a-125">非同期的に作成し、オブジェクトのプロパティを設定した後、メソッドを使用してオブジェクトの要求 `CoreWebView2` `NewWindow` `NewWindowRequestedEventArgs` `Complete` `Deferral` を返 `GetDeferral` します。</span><span class="sxs-lookup"><span data-stu-id="3de1a-125">After you've asynchronously created the `CoreWebView2` and set the `NewWindow` property on the `NewWindowRequestedEventArgs`, request `Complete` on the `Deferral` object be returned using the `GetDeferral` method.</span></span>  

## <a name="block-the-ui-thread"></a><span data-ttu-id="3de1a-126">UI スレッドをブロックする</span><span class="sxs-lookup"><span data-stu-id="3de1a-126">Block the UI thread</span></span>  

<span data-ttu-id="3de1a-127">WebView2 は、UI スレッドのメッセージ ポンプに依存して、イベント ハンドラー コールバックと非同期メソッド完了コールバックを実行します。</span><span class="sxs-lookup"><span data-stu-id="3de1a-127">The WebView2 relies on the message pump of the UI thread to run event handler callbacks and async method completion callbacks.</span></span>  <span data-ttu-id="3de1a-128">メッセージ ポンプをブロックするメソッドを使用する場合は、WebView2 イベント ハンドラーと非同期メソッド完了ハンドラーは `Task.Result` `WaitForSingleObject` 実行されません。</span><span class="sxs-lookup"><span data-stu-id="3de1a-128">If you use methods that block the message pump such as `Task.Result` or `WaitForSingleObject`, then your WebView2 event handlers and async method completion handlers don't run.</span></span>  <span data-ttu-id="3de1a-129">たとえば、次のコードは完了しないので、完了するまでメッセージ ポンプを `Task.Result` `ExecuteScriptAsync` 停止します。</span><span class="sxs-lookup"><span data-stu-id="3de1a-129">For example, the following code doesn't complete, because `Task.Result` stops the message pump while it waits for `ExecuteScriptAsync` to complete.</span></span>  <span data-ttu-id="3de1a-130">メッセージ ポンプがブロックされたので、 `ExecuteScriptAsync` 完了できない。</span><span class="sxs-lookup"><span data-stu-id="3de1a-130">Since the message pump is blocked, the `ExecuteScriptAsync` isn't able to complete.</span></span>   

```csharp
private void Button_Click(object sender, EventArgs e)
{
    string result = webView2Control.CoreWebView2.ExecuteScriptAsync("'test'").Result;
    MessageBox.Show(this, result, "Script Result");
}
```  

<span data-ttu-id="3de1a-131">メッセージ ポンプや UI スレッドをブロックしない `await` `async` and などの非同期 `await` メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="3de1a-131">Use an asynchronous `await` mechanism such as `async` and `await`, which doesn't block the message pump or the UI thread.</span></span>  

```csharp
private async void Button_Click(object sender, EventArgs e)
{
    string result = await webView2Control.CoreWebView2.ExecuteScriptAsync("'test'");
    MessageBox.Show(this, result, "Script Result");
}
```  

## <a name="see-also"></a><span data-ttu-id="3de1a-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="3de1a-132">See also</span></span>  

*   <span data-ttu-id="3de1a-133">WebView2 の使用を開始するには [、「WebView2 Get Started Guides guides」に][Webview2IndexGetStarted] 移動します。</span><span class="sxs-lookup"><span data-stu-id="3de1a-133">To get started using WebView2, navigate to [WebView2 Get Started Guides][Webview2IndexGetStarted] guides.</span></span>  
*   <span data-ttu-id="3de1a-134">WebView2 機能の包括的な例については、GitHub の [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samples] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3de1a-134">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples repo][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>  
*   <span data-ttu-id="3de1a-135">WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WpfWebview2]。</span><span class="sxs-lookup"><span data-stu-id="3de1a-135">For more detailed information about WebView2 APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2WpfWebview2].</span></span>  
*   <span data-ttu-id="3de1a-136">WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="3de1a-136">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="3de1a-137">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="3de1a-137">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGetStarted]: ../index.md#get-started "はじめに - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  

[WindowsWin32ComSingleThreadedApartments]: /windows/win32/com/single-threaded-apartments "シングル スレッド アパートメント |Microsoft Docs"  
[WindowsWin32ComTheComponentObjectModel]: /windows/win32/com/the-component-object-model "Component オブジェクト モデル |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
