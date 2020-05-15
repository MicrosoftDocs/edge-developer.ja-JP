---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 25ea8367aa9d64d0a1066cf8c1564f4d9c9f05ed
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654168"
---
# <span data-ttu-id="77ef8-104">WebView2 クラス WinForms クラスの WebView2</span><span class="sxs-lookup"><span data-stu-id="77ef8-104">Microsoft.Web.WebView2.WinForms.WebView2 class</span></span> 

<span data-ttu-id="77ef8-105">名前空間: WebView2 WinForms </span><span class="sxs-lookup"><span data-stu-id="77ef8-105">Namespace: Microsoft.Web.WebView2.WinForms</span></span>\
<span data-ttu-id="77ef8-106">Assembly: WinForms (WebView2 の場合)</span><span class="sxs-lookup"><span data-stu-id="77ef8-106">Assembly: Microsoft.Web.WebView2.WinForms.dll</span></span>

```
class Microsoft.Web.WebView2.WinForms.WebView2
  : public Control
```

<span data-ttu-id="77ef8-107">WebView2 を WinForms に埋め込むためのコントロールです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-107">Control to embed WebView2 in WinForms.</span></span>

## <span data-ttu-id="77ef8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="77ef8-108">Summary</span></span>

 <span data-ttu-id="77ef8-109">Members</span><span class="sxs-lookup"><span data-stu-id="77ef8-109">Members</span></span>                        | <span data-ttu-id="77ef8-110">説明</span><span class="sxs-lookup"><span data-stu-id="77ef8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="77ef8-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="77ef8-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="77ef8-112">ナビゲーションが新しい URI で開始され、その URI のコンテンツがレンダリングを開始した後のコンテンツ読み込みディスパッチ。</span><span class="sxs-lookup"><span data-stu-id="77ef8-112">ContentLoading dispatches after a navigation begins to a new URI and the content of that URI begins to render.</span></span>
[<span data-ttu-id="77ef8-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="77ef8-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="77ef8-114">このイベントは、コントロールの[CoreWebView2](#corewebview2)が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-114">This event is triggered when the control's [CoreWebView2](#corewebview2) has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="77ef8-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="77ef8-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="77ef8-116">NavigationCompleted はトップレベルドキュメントの移動によって、レンダリングが正常に完了するかどうかによって、発行が完了します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-116">NavigationCompleted dispatches after a navigate of the top level document completes rendering either successfully or not.</span></span>
[<span data-ttu-id="77ef8-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="77ef8-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="77ef8-118">NavigationStarting のトップレベルのドキュメントについて新しい移動が開始される前にディスパッチを開始します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-118">NavigationStarting dispatches before a new navigate starts for the top level document of the WebView2.</span></span>
[<span data-ttu-id="77ef8-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="77ef8-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="77ef8-120">ソースプロパティが変更された後の SourceChanged ディスパッチ。</span><span class="sxs-lookup"><span data-stu-id="77ef8-120">SourceChanged dispatches after the Source property changes.</span></span>
[<span data-ttu-id="77ef8-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="77ef8-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="77ef8-122">WebMessageReceived は、web コンテンツによってアプリホストにメッセージが送信された後でディスパッチさ `chrome.webview.postMessage` れます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-122">WebMessageReceived dispatches after web content sends a message to the app host via `chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="77ef8-123">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="77ef8-123">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="77ef8-124">基になる CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="77ef8-124">The underlying CoreWebView2.</span></span>
[<span data-ttu-id="77ef8-125">Source</span><span class="sxs-lookup"><span data-stu-id="77ef8-125">Source</span></span>](#source) | <span data-ttu-id="77ef8-126">Source プロパティは、WebView2 のトップレベルのドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="77ef8-126">The Source property is the URI of the top level document of the WebView2.</span></span>
[<span data-ttu-id="77ef8-127">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="77ef8-127">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="77ef8-128">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="77ef8-128">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="77ef8-129">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="77ef8-129">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="77ef8-130">Webview が GoBack メソッドによってナビゲーション履歴内の前のページに移動できる場合は、true を返します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-130">Returns true if the webview can navigate to a previous page in the navigation history via the GoBack method.</span></span>
[<span data-ttu-id="77ef8-131">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="77ef8-131">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="77ef8-132">| Forward メソッドを使用して、ナビゲーション履歴内の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-132">Returns true if the webview can navigate to a next page in the navigation history via the GoForward method.</span></span>
[<span data-ttu-id="77ef8-133">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="77ef8-133">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="77ef8-134">コントロールの[CoreWebView2](#corewebview2)の初期化を明示的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="77ef8-134">Explicitly trigger initialization of the control's [CoreWebView2](#corewebview2).</span></span>
[<span data-ttu-id="77ef8-135">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="77ef8-135">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="77ef8-136">WebView2 のトップレベルのドキュメントで、指定されたスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-136">Executes the provided script in the top level document of the WebView2.</span></span>
[<span data-ttu-id="77ef8-137">GoBack</span><span class="sxs-lookup"><span data-stu-id="77ef8-137">GoBack</span></span>](#goback) | <span data-ttu-id="77ef8-138">ナビゲーション履歴で前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-138">Navigate to the previous page in navigation history.</span></span>
[<span data-ttu-id="77ef8-139">GoForward</span><span class="sxs-lookup"><span data-stu-id="77ef8-139">GoForward</span></span>](#goforward) | <span data-ttu-id="77ef8-140">ナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-140">Navigate to the next page in navigation history.</span></span>
[<span data-ttu-id="77ef8-141">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="77ef8-141">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="77ef8-142">WebView2 のトップレベルのドキュメントとして、指定された HTML をレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="77ef8-142">Render the provided HTML as the top level document of the WebView2.</span></span>
[<span data-ttu-id="77ef8-143">再</span><span class="sxs-lookup"><span data-stu-id="77ef8-143">Reload</span></span>](#reload) | <span data-ttu-id="77ef8-144">WebView2 のトップレベルの文書を再度読み込みます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-144">Reload the top level document of the WebView2.</span></span>
[<span data-ttu-id="77ef8-145">Stop</span><span class="sxs-lookup"><span data-stu-id="77ef8-145">Stop</span></span>](#stop) | <span data-ttu-id="77ef8-146">WebView2 で進行中のナビゲーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-146">Stop any in progress navigation in the WebView2.</span></span>
[<span data-ttu-id="77ef8-147">WebView2</span><span class="sxs-lookup"><span data-stu-id="77ef8-147">WebView2</span></span>](#webview2) | <span data-ttu-id="77ef8-148">新しい WebView2 WinForms コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-148">Create a new WebView2 WinForms control.</span></span>
[<span data-ttu-id="77ef8-149">OnEnter</span><span class="sxs-lookup"><span data-stu-id="77ef8-149">OnEnter</span></span>](#onenter) | <span data-ttu-id="77ef8-150">保護されたフォーカスハンドラー。</span><span class="sxs-lookup"><span data-stu-id="77ef8-150">Protected focus handler.</span></span>
[<span data-ttu-id="77ef8-151">OnSizeChanged</span><span class="sxs-lookup"><span data-stu-id="77ef8-151">OnSizeChanged</span></span>](#onsizechanged) | <span data-ttu-id="77ef8-152">保護された SizeChanged ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="77ef8-152">Protected SizeChanged handler.</span></span>
[<span data-ttu-id="77ef8-153">OnVisibleChanged</span><span class="sxs-lookup"><span data-stu-id="77ef8-153">OnVisibleChanged</span></span>](#onvisiblechanged) | <span data-ttu-id="77ef8-154">Protected VisibilityChanged handler。</span><span class="sxs-lookup"><span data-stu-id="77ef8-154">Protected VisibilityChanged handler.</span></span>

## <span data-ttu-id="77ef8-155">Members</span><span class="sxs-lookup"><span data-stu-id="77ef8-155">Members</span></span>

#### <span data-ttu-id="77ef8-156">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="77ef8-156">ContentLoading</span></span> 

<span data-ttu-id="77ef8-157">ナビゲーションが新しい URI で開始され、その URI のコンテンツがレンダリングを開始した後のコンテンツ読み込みディスパッチ。</span><span class="sxs-lookup"><span data-stu-id="77ef8-157">ContentLoading dispatches after a navigation begins to a new URI and the content of that URI begins to render.</span></span>

> <span data-ttu-id="77ef8-158">パブリックイベント EventHandler< CoreWebView2ContentLoadingEventArgs > [Contentloading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="77ef8-158">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="77ef8-159">これは、CoreWebView2 の ContentLoading イベントと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-159">This is equivalent to the ContentLoading event on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-160">詳細については、「CoreWebView2 の読み込みドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-160">See CoreWebView2.ContentLoading documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-161">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="77ef8-161">CoreWebView2Ready</span></span> 

<span data-ttu-id="77ef8-162">このイベントは、コントロールの[CoreWebView2](#corewebview2)が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-162">This event is triggered when the control's [CoreWebView2](#corewebview2) has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="77ef8-163">パブリックイベント EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="77ef8-163">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="77ef8-164">このイベントを処理する必要があるのは、CoreWebView2 に対して1回限りのセットアップ操作を実行する必要がある場合です (たとえば、イベントハンドラーの追加、設定の構成、ドキュメント作成スクリプトのインストール、ホストオブジェクトの追加など)。</span><span class="sxs-lookup"><span data-stu-id="77ef8-164">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span>

<span data-ttu-id="77ef8-165">このイベントには引数はありません。送信者は、CoreWebView2 プロパティが有効 (つまり null ではない) WebView2 コントロールになります。</span><span class="sxs-lookup"><span data-stu-id="77ef8-165">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="77ef8-166">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="77ef8-166">NavigationCompleted</span></span> 

<span data-ttu-id="77ef8-167">NavigationCompleted はトップレベルドキュメントの移動によって、レンダリングが正常に完了するかどうかによって、発行が完了します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-167">NavigationCompleted dispatches after a navigate of the top level document completes rendering either successfully or not.</span></span>

> <span data-ttu-id="77ef8-168">パブリックイベントイベントハンドラー< CoreWebView2NavigationCompletedEventArgs > [Navigationcompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="77ef8-168">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="77ef8-169">これは、CoreWebView2 の NavigationCompleted イベントと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-169">This is equivalent to the NavigationCompleted event on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-170">詳細については、「CoreWebView2 のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-170">See CoreWebView2.NavigationCompleted documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-171">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="77ef8-171">NavigationStarting</span></span> 

<span data-ttu-id="77ef8-172">NavigationStarting のトップレベルのドキュメントについて新しい移動が開始される前にディスパッチを開始します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-172">NavigationStarting dispatches before a new navigate starts for the top level document of the WebView2.</span></span>

> <span data-ttu-id="77ef8-173">パブリックイベントイベントハンドラー< CoreWebView2NavigationStartingEventArgs > [Navigationstarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="77ef8-173">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="77ef8-174">これは、CoreWebView2 の NavigationStarting イベントと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-174">This is equivalent to the NavigationStarting event on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-175">詳細については、「CoreWebView2」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-175">See CoreWebView2.NavigationStarting documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-176">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="77ef8-176">SourceChanged</span></span> 

<span data-ttu-id="77ef8-177">ソースプロパティが変更された後の SourceChanged ディスパッチ。</span><span class="sxs-lookup"><span data-stu-id="77ef8-177">SourceChanged dispatches after the Source property changes.</span></span>

> <span data-ttu-id="77ef8-178">パブリックイベント EventHandler< CoreWebView2SourceChangedEventArgs > [Sourcechanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="77ef8-178">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="77ef8-179">これは、ナビゲーション中に発生する可能性があります。それ以外の場合は、ページのスクリプトによってドキュメントの URI が変更されます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-179">This may happen during a navigation or if otherwise the script in the page changes the URI of the document.</span></span> <span data-ttu-id="77ef8-180">これは、CoreWebView2 の SourceChanged イベントと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-180">This is equivalent to the SourceChanged event on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-181">詳細については、CoreWebView2 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-181">See CoreWebView2.SourceChanged documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-182">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="77ef8-182">WebMessageReceived</span></span> 

<span data-ttu-id="77ef8-183">WebMessageReceived は、web コンテンツによってアプリホストにメッセージが送信された後でディスパッチさ `chrome.webview.postMessage` れます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-183">WebMessageReceived dispatches after web content sends a message to the app host via `chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="77ef8-184">パブリックイベント EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="77ef8-184">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="77ef8-185">これは、CoreWebView2 の WebMessageReceived イベントと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-185">This is equivalent to the WebMessageReceived event on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-186">詳細については、WebMessageReceived のドキュメント CoreWebView2 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-186">See CoreWebView2.WebMessageReceived documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-187">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="77ef8-187">CoreWebView2</span></span> 

<span data-ttu-id="77ef8-188">基になる CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="77ef8-188">The underlying CoreWebView2.</span></span>

> <span data-ttu-id="77ef8-189">パブリック CoreWebView2 [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="77ef8-189">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="77ef8-190">このプロパティを使って、WebView2 で公開されているよりも多くの操作を WebView2 コンテンツで実行します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-190">Use this property to perform more operations on the WebView2 content than is exposed on the WebView2.</span></span> <span data-ttu-id="77ef8-191">この値は、初期化されるまで null です。</span><span class="sxs-lookup"><span data-stu-id="77ef8-191">This value is null until it is initialized.</span></span> <span data-ttu-id="77ef8-192">Initializeasync 呼び出しメソッドを使用して、基になる CoreWebView2 を強制的に初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-192">You can force the underlying CoreWebView2 to initialize via the InitializeAsync method.</span></span>

#### <span data-ttu-id="77ef8-193">Source</span><span class="sxs-lookup"><span data-stu-id="77ef8-193">Source</span></span> 

<span data-ttu-id="77ef8-194">Source プロパティは、WebView2 のトップレベルのドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="77ef8-194">The Source property is the URI of the top level document of the WebView2.</span></span>

> <span data-ttu-id="77ef8-195">パブリック Uri[ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="77ef8-195">public Uri [Source](#source)</span></span>

<span data-ttu-id="77ef8-196">ソースの設定は、CoreWebView2 の呼び出しと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-196">Setting the Source is equivalent to calling CoreWebView2.Navigate.</span></span> <span data-ttu-id="77ef8-197">基になる CoreWebView2 がまだ初期化されていない場合、このプロパティは "about: blank" となります。</span><span class="sxs-lookup"><span data-stu-id="77ef8-197">If the underlying CoreWebView2 is not yet initialized, this property is "about:blank".</span></span> <span data-ttu-id="77ef8-198">プロパティが絶対 URI 以外の URI または null に設定されている場合、プロパティは変わりません。</span><span class="sxs-lookup"><span data-stu-id="77ef8-198">If the property is set to a non-absolute URI or null, the property remains unchanged.</span></span> <span data-ttu-id="77ef8-199">詳細については、CoreWebView2 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-199">See CoreWebView2.Navigate documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-200">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="77ef8-200">ZoomFactor</span></span> 

<span data-ttu-id="77ef8-201">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="77ef8-201">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="77ef8-202">パブリックダブル[ZoomFactor](#zoomfactor)</span><span class="sxs-lookup"><span data-stu-id="77ef8-202">public double [ZoomFactor](#zoomfactor)</span></span>

#### <span data-ttu-id="77ef8-203">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="77ef8-203">CanGoBack</span></span> 

<span data-ttu-id="77ef8-204">Webview が GoBack メソッドによってナビゲーション履歴内の前のページに移動できる場合は、true を返します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-204">Returns true if the webview can navigate to a previous page in the navigation history via the GoBack method.</span></span>

> <span data-ttu-id="77ef8-205">public bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="77ef8-205">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="77ef8-206">これは、CoreWebView2 の CanGoBack プロパティと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-206">This is equivalent to the CanGoBack property on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-207">基になる CoreWebView2 がまだ初期化されていない場合、このプロパティは false になります。</span><span class="sxs-lookup"><span data-stu-id="77ef8-207">If the underlying CoreWebView2 is not yet initialized, this property is false.</span></span> <span data-ttu-id="77ef8-208">詳細については、CanGoBack のドキュメント CoreWebView2 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-208">See CoreWebView2.CanGoBack documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-209">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="77ef8-209">CanGoForward</span></span> 

<span data-ttu-id="77ef8-210">| Forward メソッドを使用して、ナビゲーション履歴内の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-210">Returns true if the webview can navigate to a next page in the navigation history via the GoForward method.</span></span>

> <span data-ttu-id="77ef8-211">public bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="77ef8-211">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="77ef8-212">これは、CoreWebView2 の CanGoForward プロパティと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-212">This is equivalent to the CanGoForward property on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-213">基になる CoreWebView2 がまだ初期化されていない場合、このプロパティは false になります。</span><span class="sxs-lookup"><span data-stu-id="77ef8-213">If the underlying CoreWebView2 is not yet initialized, this property is false.</span></span> <span data-ttu-id="77ef8-214">詳細については、CanGoForward のドキュメント CoreWebView2 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-214">See CoreWebView2.CanGoForward documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-215">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="77ef8-215">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="77ef8-216">コントロールの[CoreWebView2](#corewebview2)の初期化を明示的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="77ef8-216">Explicitly trigger initialization of the control's [CoreWebView2](#corewebview2).</span></span>

> <span data-ttu-id="77ef8-217">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span><span class="sxs-lookup"><span data-stu-id="77ef8-217">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

##### <span data-ttu-id="77ef8-218">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77ef8-218">Parameters</span></span>
* `environment` <span data-ttu-id="77ef8-219">CoreWebView2 の作成に使用する事前に作成された CoreWebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="77ef8-219">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="77ef8-220">独自の環境を作成することにより、CoreWebView2 の初期化方法に影響するいくつかのオプションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-220">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="77ef8-221">Null (既定値) を渡すと、既定の環境が自動的に作成されて使用されます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-221">If you pass null (the default value) then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="77ef8-222">返し</span><span class="sxs-lookup"><span data-stu-id="77ef8-222">Returns</span></span>
<span data-ttu-id="77ef8-223">バックグラウンドの初期化プロセスを表すタスク。</span><span class="sxs-lookup"><span data-stu-id="77ef8-223">A Task that represents the background initialization process.</span></span> <span data-ttu-id="77ef8-224">タスクが完了したら、CoreWebView2 プロパティを使用できるようになります (つまり、null 以外)。</span><span class="sxs-lookup"><span data-stu-id="77ef8-224">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="77ef8-225">コントロールの[CoreWebView2Ready](#corewebview2ready)イベントは、タスクが完了する前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-225">Note that the control's [CoreWebView2Ready](#corewebview2ready) event will be invoked before the task completes.</span></span> 

<span data-ttu-id="77ef8-226">このメソッドを追加すると、何度も呼び出されることはありません (指定した環境は無視されます)。最初の呼び出しと同じタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-226">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="77ef8-227">初期化後にこのメソッドを呼び出す場合は、 [Source](#source)プロパティを設定しても効果はありません (指定された環境は無視されます)。単に、既に進行中の初期化を示すタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-227">Calling this method after initialization has been implicitly triggered by setting the [Source](#source) property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> 

##### <span data-ttu-id="77ef8-228">例外</span><span class="sxs-lookup"><span data-stu-id="77ef8-228">Exceptions</span></span>
* `System.InvalidOperationException` <span data-ttu-id="77ef8-229">UI 以外のスレッドから呼び出された場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-229">Thrown when invoked from non-UI thread.</span></span>

#### <span data-ttu-id="77ef8-230">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="77ef8-230">ExecuteScriptAsync</span></span> 

<span data-ttu-id="77ef8-231">WebView2 のトップレベルのドキュメントで、指定されたスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-231">Executes the provided script in the top level document of the WebView2.</span></span>

> <span data-ttu-id="77ef8-232">パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列スクリプト)</span><span class="sxs-lookup"><span data-stu-id="77ef8-232">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string script)</span></span>

<span data-ttu-id="77ef8-233">これは、CoreWebView2 の Executesメソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-233">This is equivalent to the ExecuteScriptAsync method on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-234">基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは InvalidOperationException をスローします。</span><span class="sxs-lookup"><span data-stu-id="77ef8-234">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="77ef8-235">詳細については、CoreWebView2 のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-235">See CoreWebView2.ExecuteScriptAsync documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-236">GoBack</span><span class="sxs-lookup"><span data-stu-id="77ef8-236">GoBack</span></span> 

<span data-ttu-id="77ef8-237">ナビゲーション履歴で前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-237">Navigate to the previous page in navigation history.</span></span>

> <span data-ttu-id="77ef8-238">パブリック void [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="77ef8-238">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="77ef8-239">これは、CoreWebView2 の GoBack メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-239">This is equivalent to the GoBack method on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-240">基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="77ef8-240">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="77ef8-241">詳細については、CoreWebView2 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-241">See CoreWebView2.GoBack documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-242">GoForward</span><span class="sxs-lookup"><span data-stu-id="77ef8-242">GoForward</span></span> 

<span data-ttu-id="77ef8-243">ナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-243">Navigate to the next page in navigation history.</span></span>

> <span data-ttu-id="77ef8-244">パブリック void [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="77ef8-244">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="77ef8-245">これは、CoreWebView2 の GoForward メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-245">This is equivalent to the GoForward method on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-246">基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="77ef8-246">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="77ef8-247">詳細については、「CoreWebView2 フォワードドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-247">See CoreWebView2.GoForward documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-248">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="77ef8-248">NavigateToString</span></span> 

<span data-ttu-id="77ef8-249">WebView2 のトップレベルのドキュメントとして、指定された HTML をレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="77ef8-249">Render the provided HTML as the top level document of the WebView2.</span></span>

> <span data-ttu-id="77ef8-250">パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="77ef8-250">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="77ef8-251">これは、CoreWebView2 の NavigateToString メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-251">This is equivalent to the NavigateToString method on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-252">基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは InvalidOperationException をスローします。</span><span class="sxs-lookup"><span data-stu-id="77ef8-252">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="77ef8-253">詳細については、NavigateToString のドキュメント CoreWebView2 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-253">See CoreWebView2.NavigateToString documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-254">再</span><span class="sxs-lookup"><span data-stu-id="77ef8-254">Reload</span></span> 

<span data-ttu-id="77ef8-255">WebView2 のトップレベルの文書を再度読み込みます。</span><span class="sxs-lookup"><span data-stu-id="77ef8-255">Reload the top level document of the WebView2.</span></span>

> <span data-ttu-id="77ef8-256">パブリックの void[再読み込み](#reload)()</span><span class="sxs-lookup"><span data-stu-id="77ef8-256">public void [Reload](#reload)()</span></span>

<span data-ttu-id="77ef8-257">これは、CoreWebView2 の Reload メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-257">This is equivalent to the Reload method on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-258">基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは InvalidOperationException をスローします。</span><span class="sxs-lookup"><span data-stu-id="77ef8-258">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="77ef8-259">詳細については、CoreWebView2 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-259">See CoreWebView2.Reload documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-260">Stop</span><span class="sxs-lookup"><span data-stu-id="77ef8-260">Stop</span></span> 

<span data-ttu-id="77ef8-261">WebView2 で進行中のナビゲーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-261">Stop any in progress navigation in the WebView2.</span></span>

> <span data-ttu-id="77ef8-262">パブリック void [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="77ef8-262">public void [Stop](#stop)()</span></span>

<span data-ttu-id="77ef8-263">これは、CoreWebView2 の Stop メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ef8-263">This is equivalent to the Stop method on the CoreWebView2.</span></span> <span data-ttu-id="77ef8-264">基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="77ef8-264">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="77ef8-265">詳細については、CoreWebView2 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ef8-265">See CoreWebView2.Stop documentation for more information.</span></span>

#### <span data-ttu-id="77ef8-266">WebView2</span><span class="sxs-lookup"><span data-stu-id="77ef8-266">WebView2</span></span> 

<span data-ttu-id="77ef8-267">新しい WebView2 WinForms コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-267">Create a new WebView2 WinForms control.</span></span>

> <span data-ttu-id="77ef8-268">パブリック[WebView2](#webview2)()</span><span class="sxs-lookup"><span data-stu-id="77ef8-268">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="77ef8-269">構築後、CoreWebView2 プロパティは null になります。</span><span class="sxs-lookup"><span data-stu-id="77ef8-269">After construction the CoreWebView2 property is null.</span></span> <span data-ttu-id="77ef8-270">[EnsureCoreWebView2Async](#ensurecorewebview2async)を呼び出して、基になる CoreWebView2 を初期化します。</span><span class="sxs-lookup"><span data-stu-id="77ef8-270">Call [EnsureCoreWebView2Async](#ensurecorewebview2async) to initialize the underlying CoreWebView2.</span></span>

#### <span data-ttu-id="77ef8-271">OnEnter</span><span class="sxs-lookup"><span data-stu-id="77ef8-271">OnEnter</span></span> 

<span data-ttu-id="77ef8-272">保護されたフォーカスハンドラー。</span><span class="sxs-lookup"><span data-stu-id="77ef8-272">Protected focus handler.</span></span>

> <span data-ttu-id="77ef8-273">protected override void [OnEnter](#onenter)(EventArgs e)</span><span class="sxs-lookup"><span data-stu-id="77ef8-273">protected override void [OnEnter](#onenter)(EventArgs e)</span></span>

#### <span data-ttu-id="77ef8-274">OnSizeChanged</span><span class="sxs-lookup"><span data-stu-id="77ef8-274">OnSizeChanged</span></span> 

<span data-ttu-id="77ef8-275">保護された SizeChanged ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="77ef8-275">Protected SizeChanged handler.</span></span>

> <span data-ttu-id="77ef8-276">protected override void [Onsizechanged](#onsizechanged)(EventArgs e)</span><span class="sxs-lookup"><span data-stu-id="77ef8-276">protected override void [OnSizeChanged](#onsizechanged)(EventArgs e)</span></span>

#### <span data-ttu-id="77ef8-277">OnVisibleChanged</span><span class="sxs-lookup"><span data-stu-id="77ef8-277">OnVisibleChanged</span></span> 

<span data-ttu-id="77ef8-278">Protected VisibilityChanged handler。</span><span class="sxs-lookup"><span data-stu-id="77ef8-278">Protected VisibilityChanged handler.</span></span>

> <span data-ttu-id="77ef8-279">protected override void [OnVisibleChanged](#onvisiblechanged)(EventArgs e)</span><span class="sxs-lookup"><span data-stu-id="77ef8-279">protected override void [OnVisibleChanged](#onvisiblechanged)(EventArgs e)</span></span>

