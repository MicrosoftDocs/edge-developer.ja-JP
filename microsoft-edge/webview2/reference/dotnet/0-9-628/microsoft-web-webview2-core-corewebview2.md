---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2。
ms.openlocfilehash: 3a728ad32647a3d74eda7b36b947e335bf4a1e80
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012302"
---
# <span data-ttu-id="d89ba-104">WebView2 クラス (CoreWebView2 クラス)</span><span class="sxs-lookup"><span data-stu-id="d89ba-104">Microsoft.Web.WebView2.Core.CoreWebView2 class</span></span> 

<span data-ttu-id="d89ba-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="d89ba-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d89ba-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="d89ba-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d89ba-107">WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-107">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="d89ba-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d89ba-108">Summary</span></span>

 <span data-ttu-id="d89ba-109">Members</span><span class="sxs-lookup"><span data-stu-id="d89ba-109">Members</span></span>                        | <span data-ttu-id="d89ba-110">説明</span><span class="sxs-lookup"><span data-stu-id="d89ba-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d89ba-111">BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="d89ba-111">BrowserProcessId</span></span>](#browserprocessid) | <span data-ttu-id="d89ba-112">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="d89ba-112">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="d89ba-113">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="d89ba-113">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="d89ba-114">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-114">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="d89ba-115">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="d89ba-115">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="d89ba-116">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-116">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="d89ba-117">ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="d89ba-117">ContainsFullScreenElement</span></span>](#containsfullscreenelement) | <span data-ttu-id="d89ba-118">WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-118">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="d89ba-119">ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="d89ba-119">ContainsFullScreenElementChanged</span></span>](#containsfullscreenelementchanged) | <span data-ttu-id="d89ba-120">持つ Fullfullscreenelement プロパティが変更されたときに発生する、Fullfullscreenelementchanged。</span><span class="sxs-lookup"><span data-stu-id="d89ba-120">ContainsFullScreenElementChanged fires when the ContainsFullScreenElement property changes.</span></span>
[<span data-ttu-id="d89ba-121">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="d89ba-121">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="d89ba-122">ContentLoading は、コンテンツが読み込まれる前に、AddScriptToExecuteOnDocumentCreated によって追加されたスクリプトを含みます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-122">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated.</span></span>
[<span data-ttu-id="d89ba-123">DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="d89ba-123">DocumentTitle</span></span>](#documenttitle) | <span data-ttu-id="d89ba-124">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="d89ba-124">The title for the current top level document.</span></span>
[<span data-ttu-id="d89ba-125">ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="d89ba-125">DocumentTitleChanged</span></span>](#documenttitlechanged) | <span data-ttu-id="d89ba-126">Document肩書は、WebView の DocumentTitle プロパティが変更され、NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-126">DocumentTitleChanged fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>
[<span data-ttu-id="d89ba-127">FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="d89ba-127">FrameNavigationCompleted</span></span>](#framenavigationcompleted) | <span data-ttu-id="d89ba-128">FrameNavigationCompleted は、子フレームが完全に読み込まれた (読み込みが開始された) か、エラーが発生して読み込みを停止したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-128">FrameNavigationCompleted fires when a child frame has completely loaded (body.onload has fired) or loading stopped with error.</span></span>
[<span data-ttu-id="d89ba-129">FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d89ba-129">FrameNavigationStarting</span></span>](#framenavigationstarting) | <span data-ttu-id="d89ba-130">FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-130">FrameNavigationStarting fires when a child frame in the WebView requests permission to navigate to a different URI.</span></span>
[<span data-ttu-id="d89ba-131">変更履歴</span><span class="sxs-lookup"><span data-stu-id="d89ba-131">HistoryChanged</span></span>](#historychanged) | <span data-ttu-id="d89ba-132">履歴は、トップレベルのドキュメントのナビゲーション履歴の変更をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="d89ba-132">HistoryChange listen to the change of navigation history for the top level document.</span></span>
[<span data-ttu-id="d89ba-133">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="d89ba-133">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="d89ba-134">NavigationCompleted は、WebView が完全に読み込まれるとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-134">NavigationCompleted fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>
[<span data-ttu-id="d89ba-135">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d89ba-135">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="d89ba-136">NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-136">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span>
[<span data-ttu-id="d89ba-137">NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="d89ba-137">NewWindowRequested</span></span>](#newwindowrequested) | <span data-ttu-id="d89ba-138">NewWindowRequested は、WebView 内のコンテンツが、window からの移動などの新しいウィンドウを開くように要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-138">NewWindowRequested fires when content inside the WebView requests to open a new window, such as through window.open.</span></span>
[<span data-ttu-id="d89ba-139">PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="d89ba-139">PermissionRequested</span></span>](#permissionrequested) | <span data-ttu-id="d89ba-140">PermissionRequested は、WebView のコンテンツが権限を持つ一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-140">PermissionRequested fires when content in a WebView requests permission to access some privileged resources.</span></span>
[<span data-ttu-id="d89ba-141">ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="d89ba-141">ProcessFailed</span></span>](#processfailed) | <span data-ttu-id="d89ba-142">ProcessFailed は、WebView プロセスが予期せず終了したか、応答しなくなったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-142">ProcessFailed fires when a WebView process is terminated unexpectedly or becomes unresponsive.</span></span>
[<span data-ttu-id="d89ba-143">Scriptて開く</span><span class="sxs-lookup"><span data-stu-id="d89ba-143">ScriptDialogOpening</span></span>](#scriptdialogopening) | <span data-ttu-id="d89ba-144">このイベントは、WebView の JavaScript ダイアログ (アラート、確認、プロンプト、または "beforeunload") が表示されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-144">The event fires when a JavaScript dialog (alert, confirm, prompt, or beforeunload) will show for the WebView.</span></span>
[<span data-ttu-id="d89ba-145">設定</span><span class="sxs-lookup"><span data-stu-id="d89ba-145">Settings</span></span>](#settings) | <span data-ttu-id="d89ba-146">CoreWebView2Settings オブジェクトには、実行に関するさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d89ba-146">The CoreWebView2Settings object contains various modifiable settings for the running</span></span>
[<span data-ttu-id="d89ba-147">Source</span><span class="sxs-lookup"><span data-stu-id="d89ba-147">Source</span></span>](#source) | <span data-ttu-id="d89ba-148">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="d89ba-148">The URI of the current top level document.</span></span>
[<span data-ttu-id="d89ba-149">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="d89ba-149">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="d89ba-150">SourceChanged Source プロパティが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-150">SourceChanged fires when the Source property changes.</span></span>
[<span data-ttu-id="d89ba-151">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="d89ba-151">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="d89ba-152">WebMessageReceived は、CoreWebView2Settings 設定が設定され、WebView 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-152">WebMessageReceived fires when the CoreWebView2Settings.IsWebMessageEnabled setting is set and the top level document of the WebView calls `window.chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="d89ba-153">WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="d89ba-153">WebResourceRequested</span></span>](#webresourcerequested) | <span data-ttu-id="d89ba-154">WebResourceRequested は、AddWebResourceRequestedFilter で指定された Web リソース一致のリソースコンテキストフィルターと URL に対して、WebView で URL 要求 (network、file など) を実行したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-154">WebResourceRequested fires when a URL request (through network, file etc.) is made in the WebView for a Web resource matching resource context filter and URL specified in AddWebResourceRequestedFilter.</span></span>
[<span data-ttu-id="d89ba-155">WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="d89ba-155">WebResourceResponseReceived</span></span>](#webresourceresponsereceived) | <span data-ttu-id="d89ba-156">WebResourceResponseReceived イベントは、WebView が WebResource 要求に対する応答を受信して処理した後に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-156">WebResourceResponseReceived event fires after the WebView has received and processed the response for a WebResource request.</span></span>
[<span data-ttu-id="d89ba-157">WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="d89ba-157">WindowCloseRequested</span></span>](#windowcloserequested) | <span data-ttu-id="d89ba-158">WindowCloseRequested が呼び出された後など、WebView 内のコンテンツがウィンドウを閉じる必要がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-158">WindowCloseRequested fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span>
[<span data-ttu-id="d89ba-159">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="d89ba-159">AddHostObjectToScript</span></span>](#addhostobjecttoscript) | <span data-ttu-id="d89ba-160">指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-160">Add the provided host object to script running in the WebView with the specified name.</span></span>
[<span data-ttu-id="d89ba-161">AddScriptToExecuteOnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="d89ba-161">AddScriptToExecuteOnDocumentCreatedAsync</span></span>](#addscripttoexecuteondocumentcreatedasync) | <span data-ttu-id="d89ba-162">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-162">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="d89ba-163">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="d89ba-163">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="d89ba-164">URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-164">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="d89ba-165">Calldev| Protocolmethodasync</span><span class="sxs-lookup"><span data-stu-id="d89ba-165">CallDevToolsProtocolMethodAsync</span></span>](#calldevtoolsprotocolmethodasync) | <span data-ttu-id="d89ba-166">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-166">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="d89ba-167">CapturePreviewAsync</span><span class="sxs-lookup"><span data-stu-id="d89ba-167">CapturePreviewAsync</span></span>](#capturepreviewasync) | <span data-ttu-id="d89ba-168">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d89ba-168">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="d89ba-169">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d89ba-169">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="d89ba-170">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-170">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="d89ba-171">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="d89ba-171">GetDevToolsProtocolEventReceiver</span></span>](#getdevtoolsprotocoleventreceiver) | <span data-ttu-id="d89ba-172">DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-172">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>
[<span data-ttu-id="d89ba-173">GoBack</span><span class="sxs-lookup"><span data-stu-id="d89ba-173">GoBack</span></span>](#goback) | <span data-ttu-id="d89ba-174">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-174">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="d89ba-175">GoForward</span><span class="sxs-lookup"><span data-stu-id="d89ba-175">GoForward</span></span>](#goforward) | <span data-ttu-id="d89ba-176">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-176">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="d89ba-177">検索</span><span class="sxs-lookup"><span data-stu-id="d89ba-177">Navigate</span></span>](#navigate) | <span data-ttu-id="d89ba-178">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-178">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="d89ba-179">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="d89ba-179">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="d89ba-180">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-180">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="d89ba-181">Opendevツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="d89ba-181">OpenDevToolsWindow</span></span>](#opendevtoolswindow) | <span data-ttu-id="d89ba-182">WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-182">Opens the DevTools window for the current document in the WebView.</span></span>
[<span data-ttu-id="d89ba-183">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="d89ba-183">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="d89ba-184">指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-184">Post the specified webMessage to the top level document in this WebView.</span></span>
[<span data-ttu-id="d89ba-185">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="d89ba-185">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="d89ba-186">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="d89ba-186">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="d89ba-187">再</span><span class="sxs-lookup"><span data-stu-id="d89ba-187">Reload</span></span>](#reload) | <span data-ttu-id="d89ba-188">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="d89ba-188">Reload the current page.</span></span>
[<span data-ttu-id="d89ba-189">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="d89ba-189">RemoveHostObjectFromScript</span></span>](#removehostobjectfromscript) | <span data-ttu-id="d89ba-190">名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="d89ba-190">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>
[<span data-ttu-id="d89ba-191">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="d89ba-191">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="d89ba-192">指定したスクリプト id を使用して、AddScriptToExecuteOnDocumentCreated で追加された対応する JavaScript を削除します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-192">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated with the specified script id.</span></span>
[<span data-ttu-id="d89ba-193">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="d89ba-193">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="d89ba-194">以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-194">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>
[<span data-ttu-id="d89ba-195">Stop</span><span class="sxs-lookup"><span data-stu-id="d89ba-195">Stop</span></span>](#stop) | <span data-ttu-id="d89ba-196">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-196">Stop all navigations and pending resource fetches.</span></span>

## <span data-ttu-id="d89ba-197">Members</span><span class="sxs-lookup"><span data-stu-id="d89ba-197">Members</span></span>

#### <span data-ttu-id="d89ba-198">BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="d89ba-198">BrowserProcessId</span></span> 

<span data-ttu-id="d89ba-199">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="d89ba-199">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="d89ba-200">パブリック uint [ブラウザー processid](#browserprocessid)</span><span class="sxs-lookup"><span data-stu-id="d89ba-200">public uint [BrowserProcessId](#browserprocessid)</span></span>

#### <span data-ttu-id="d89ba-201">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="d89ba-201">CanGoBack</span></span> 

<span data-ttu-id="d89ba-202">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-202">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="d89ba-203">public bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="d89ba-203">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="d89ba-204">CanGoBack の値が変更されると、履歴変更イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-204">The HistoryChanged event will fire if CanGoBack changes value.</span></span>

#### <span data-ttu-id="d89ba-205">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="d89ba-205">CanGoForward</span></span> 

<span data-ttu-id="d89ba-206">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-206">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="d89ba-207">public bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="d89ba-207">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="d89ba-208">CanGoForward の値が変更されると、履歴変更イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-208">The HistoryChanged event will fire if CanGoForward changes value.</span></span>

#### <span data-ttu-id="d89ba-209">ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="d89ba-209">ContainsFullScreenElement</span></span> 

<span data-ttu-id="d89ba-210">WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-210">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="d89ba-211">パブリックブール型 [Fullscreenelement](#containsfullscreenelement)</span><span class="sxs-lookup"><span data-stu-id="d89ba-211">public bool [ContainsFullScreenElement](#containsfullscreenelement)</span></span>

#### <span data-ttu-id="d89ba-212">ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="d89ba-212">ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="d89ba-213">持つ Fullfullscreenelement プロパティが変更されたときに発生する、Fullfullscreenelementchanged。</span><span class="sxs-lookup"><span data-stu-id="d89ba-213">ContainsFullScreenElementChanged fires when the ContainsFullScreenElement property changes.</span></span>

> <span data-ttu-id="d89ba-214">パブリックイベント EventHandler< オブジェクト > [Fullfullscreenelementchanged](#containsfullscreenelementchanged)</span><span class="sxs-lookup"><span data-stu-id="d89ba-214">public event EventHandler< object > [ContainsFullScreenElementChanged](#containsfullscreenelementchanged)</span></span>

<span data-ttu-id="d89ba-215">これは、WebView 内の HTML 要素が、WebView のサイズまたはフルスクリーンのままであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-215">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="d89ba-216">このイベントは、たとえば、ビデオ要素が全画面表示になっている要求の場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d89ba-216">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="d89ba-217">次に、Fullfullscreenelementelementのリスナーが、応答で WebView のサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-217">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

#### <span data-ttu-id="d89ba-218">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="d89ba-218">ContentLoading</span></span> 

<span data-ttu-id="d89ba-219">ContentLoading は、コンテンツが読み込まれる前に、AddScriptToExecuteOnDocumentCreated によって追加されたスクリプトを含みます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-219">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated.</span></span>

> <span data-ttu-id="d89ba-220">パブリックイベントハンドラー< [CoreWebView2ContentLoadingEventArgs](microsoft-web-webview2-core-corewebview2contentloadingeventargs.md)  >  [contentloading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="d89ba-220">public event EventHandler< [CoreWebView2ContentLoadingEventArgs](microsoft-web-webview2-core-corewebview2contentloadingeventargs.md) > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="d89ba-221">同じページナビゲーションが発生した場合、ContentLoading は発生しません (フラグメントナビゲーションや履歴の状態ナビゲートなど)。</span><span class="sxs-lookup"><span data-stu-id="d89ba-221">ContentLoading will not fire if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span>

<span data-ttu-id="d89ba-222">これは、NavigationStarting イベントと SourceChanged イベントの後で、履歴の変更イベントと Navigationstarting イベントの前に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-222">This follows the NavigationStarting and SourceChanged events and precedes the HistoryChanged and NavigationCompleted events.</span></span>

#### <span data-ttu-id="d89ba-223">DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="d89ba-223">DocumentTitle</span></span> 

<span data-ttu-id="d89ba-224">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="d89ba-224">The title for the current top level document.</span></span>

> <span data-ttu-id="d89ba-225">パブリック文字列 [ドキュメントタイトル](#documenttitle)</span><span class="sxs-lookup"><span data-stu-id="d89ba-225">public string [DocumentTitle](#documenttitle)</span></span>

<span data-ttu-id="d89ba-226">ドキュメントに明示的なタイトルが含まれていない場合、または空の場合は、ドキュメントの URI と一致しないかもしれない既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-226">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

#### <span data-ttu-id="d89ba-227">ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="d89ba-227">DocumentTitleChanged</span></span> 

<span data-ttu-id="d89ba-228">Document肩書は、WebView の DocumentTitle プロパティが変更され、NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-228">DocumentTitleChanged fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

> <span data-ttu-id="d89ba-229">パブリックイベントイベントハンドラー< オブジェクト >[ドキュメント](#documenttitlechanged)の概要</span><span class="sxs-lookup"><span data-stu-id="d89ba-229">public event EventHandler< object > [DocumentTitleChanged](#documenttitlechanged)</span></span>

#### <span data-ttu-id="d89ba-230">FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="d89ba-230">FrameNavigationCompleted</span></span> 

<span data-ttu-id="d89ba-231">FrameNavigationCompleted は、子フレームが完全に読み込まれた (読み込みが開始された) か、エラーが発生して読み込みを停止したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-231">FrameNavigationCompleted fires when a child frame has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

> <span data-ttu-id="d89ba-232">パブリックイベント EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [FrameNavigationCompleted](#framenavigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="d89ba-232">public event EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md) > [FrameNavigationCompleted](#framenavigationcompleted)</span></span>

#### <span data-ttu-id="d89ba-233">FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d89ba-233">FrameNavigationStarting</span></span> 

<span data-ttu-id="d89ba-234">FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-234">FrameNavigationStarting fires when a child frame in the WebView requests permission to navigate to a different URI.</span></span>

> <span data-ttu-id="d89ba-235">パブリックイベント EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [FrameNavigationStarting](#framenavigationstarting)</span><span class="sxs-lookup"><span data-stu-id="d89ba-235">public event EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md) > [FrameNavigationStarting](#framenavigationstarting)</span></span>

<span data-ttu-id="d89ba-236">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-236">This will fire for redirects as well.</span></span> <span data-ttu-id="d89ba-237">対応するナビゲーションは、イベントハンドラーから制御が返されるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-237">Corresponding navigations can be blocked until the event handler returns.</span></span>

#### <span data-ttu-id="d89ba-238">変更履歴</span><span class="sxs-lookup"><span data-stu-id="d89ba-238">HistoryChanged</span></span> 

<span data-ttu-id="d89ba-239">履歴は、トップレベルのドキュメントのナビゲーション履歴の変更をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="d89ba-239">HistoryChange listen to the change of navigation history for the top level document.</span></span>

> <span data-ttu-id="d89ba-240">パブリックイベント EventHandler< オブジェクト > [履歴の変更](#historychanged)</span><span class="sxs-lookup"><span data-stu-id="d89ba-240">public event EventHandler< object > [HistoryChanged](#historychanged)</span></span>

<span data-ttu-id="d89ba-241">履歴の変更を使って、CanGoBack/CanGoForward の値が変更されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-241">Use HistoryChange to check if CanGoBack/CanGoForward value has changed.</span></span> <span data-ttu-id="d89ba-242">GoBack/GoForward を使用する場合にも変更履歴が発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-242">HistoryChanged also fires for using GoBack/GoForward.</span></span> <span data-ttu-id="d89ba-243">変更履歴は、SourceChanged と ContentLoading の後に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-243">HistoryChanged fires after SourceChanged and ContentLoading.</span></span>

#### <span data-ttu-id="d89ba-244">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="d89ba-244">NavigationCompleted</span></span> 

<span data-ttu-id="d89ba-245">NavigationCompleted は、WebView が完全に読み込まれるとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-245">NavigationCompleted fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

> <span data-ttu-id="d89ba-246">パブリックイベント EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [navigationcompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="d89ba-246">public event EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md) > [NavigationCompleted](#navigationcompleted)</span></span>

#### <span data-ttu-id="d89ba-247">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d89ba-247">NavigationStarting</span></span> 

<span data-ttu-id="d89ba-248">NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-248">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span>

> <span data-ttu-id="d89ba-249">パブリックイベント EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [navigationstarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="d89ba-249">public event EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md) > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="d89ba-250">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-250">This will fire for redirects as well.</span></span> <span data-ttu-id="d89ba-251">対応するナビゲーションは、イベントハンドラーから制御が返されるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-251">Corresponding navigations can be blocked until the event handler returns.</span></span>

#### <span data-ttu-id="d89ba-252">NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="d89ba-252">NewWindowRequested</span></span> 

<span data-ttu-id="d89ba-253">NewWindowRequested は、WebView 内のコンテンツが、window からの移動などの新しいウィンドウを開くように要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-253">NewWindowRequested fires when content inside the WebView requests to open a new window, such as through window.open.</span></span>

> <span data-ttu-id="d89ba-254">パブリックイベント EventHandler< [CoreWebView2NewWindowRequestedEventArgs](microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md)  >  [newwindowrequested](#newwindowrequested)</span><span class="sxs-lookup"><span data-stu-id="d89ba-254">public event EventHandler< [CoreWebView2NewWindowRequestedEventArgs](microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md) > [NewWindowRequested](#newwindowrequested)</span></span>

<span data-ttu-id="d89ba-255">アプリは、開かれたウィンドウと見なされるターゲット WebView を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-255">The app can pass a target WebView that will be considered the opened window.</span></span> <span data-ttu-id="d89ba-256">新しいウィンドウが要求されたスクリプトは、イベント引数で遅延が発生しなかった場合に、イベントハンドラーから制御が返されるまでブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-256">Scripts resulted in the new window requested can be blocked until the event handler returns if a deferral is not taken on the event args.</span></span> <span data-ttu-id="d89ba-257">延期が行われると、遅延が完了するまで、スクリプトはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-257">If a deferral is taken, then scripts are blocked until the deferral is completed.</span></span>

#### <span data-ttu-id="d89ba-258">PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="d89ba-258">PermissionRequested</span></span> 

<span data-ttu-id="d89ba-259">PermissionRequested は、WebView のコンテンツが権限を持つ一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-259">PermissionRequested fires when content in a WebView requests permission to access some privileged resources.</span></span>

> <span data-ttu-id="d89ba-260">パブリックイベント EventHandler< [CoreWebView2PermissionRequestedEventArgs](microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md)  >  [permissionrequested](#permissionrequested)</span><span class="sxs-lookup"><span data-stu-id="d89ba-260">public event EventHandler< [CoreWebView2PermissionRequestedEventArgs](microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md) > [PermissionRequested](#permissionrequested)</span></span>

<span data-ttu-id="d89ba-261">イベント引数に対して遅延が発生しない場合は、イベントハンドラーから制御が返されるまで、後続のスクリプトをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-261">If a deferral is not taken on the event args, the subsequent scripts can be blocked until the event handler returns.</span></span> <span data-ttu-id="d89ba-262">延期が行われると、遅延が完了するまで、スクリプトはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-262">If a deferral is taken, then the scripts are blocked until the deferral is completed.</span></span>

#### <span data-ttu-id="d89ba-263">ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="d89ba-263">ProcessFailed</span></span> 

<span data-ttu-id="d89ba-264">ProcessFailed は、WebView プロセスが予期せず終了したか、応答しなくなったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-264">ProcessFailed fires when a WebView process is terminated unexpectedly or becomes unresponsive.</span></span>

> <span data-ttu-id="d89ba-265">パブリックイベント EventHandler< [CoreWebView2ProcessFailedEventArgs](microsoft-web-webview2-core-corewebview2processfailedeventargs.md)  >  [processfailed](#processfailed)</span><span class="sxs-lookup"><span data-stu-id="d89ba-265">public event EventHandler< [CoreWebView2ProcessFailedEventArgs](microsoft-web-webview2-core-corewebview2processfailedeventargs.md) > [ProcessFailed](#processfailed)</span></span>

#### <span data-ttu-id="d89ba-266">Scriptて開く</span><span class="sxs-lookup"><span data-stu-id="d89ba-266">ScriptDialogOpening</span></span> 

<span data-ttu-id="d89ba-267">このイベントは、WebView の JavaScript ダイアログ (アラート、確認、プロンプト、または "beforeunload") が表示されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-267">The event fires when a JavaScript dialog (alert, confirm, prompt, or beforeunload) will show for the WebView.</span></span>

> <span data-ttu-id="d89ba-268">パブリックイベント EventHandler< [CoreWebView2ScriptDialogOpeningEventArgs](microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md)  >  [script を開く](#scriptdialogopening)</span><span class="sxs-lookup"><span data-stu-id="d89ba-268">public event EventHandler< [CoreWebView2ScriptDialogOpeningEventArgs](microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md) > [ScriptDialogOpening](#scriptdialogopening)</span></span>

<span data-ttu-id="d89ba-269">このイベントは、CoreWebView2Settings Defaultscript Senabled プロパティが false に設定されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-269">This event only fires if the CoreWebView2Settings.AreDefaultScriptDialogsEnabled property is set to false.</span></span> <span data-ttu-id="d89ba-270">Scriptdialogs 左中イベントを使うと、ダイアログを非表示にしたり、既定のダイアログをカスタムダイアログに置き換えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-270">The ScriptDialogOpening event can be used to suppress dialogs or replace default dialogs with custom dialogs.</span></span> <span data-ttu-id="d89ba-271">イベント引数に対して遅延が発生しない場合は、イベントハンドラーから制御が返されるまで、後続のスクリプトをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-271">If a deferral is not taken on the event args, the subsequent scripts can be blocked until the event handler returns.</span></span> <span data-ttu-id="d89ba-272">延期が行われると、遅延が完了するまで、スクリプトはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-272">If a deferral is taken, then the scripts are blocked until the deferral is completed.</span></span>

#### <span data-ttu-id="d89ba-273">設定</span><span class="sxs-lookup"><span data-stu-id="d89ba-273">Settings</span></span> 

<span data-ttu-id="d89ba-274">CoreWebView2Settings オブジェクトには、実行に関するさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d89ba-274">The CoreWebView2Settings object contains various modifiable settings for the running</span></span>

> <span data-ttu-id="d89ba-275">パブリック [CoreWebView2Settings](microsoft-web-webview2-core-corewebview2settings.md)の [設定](#settings)</span><span class="sxs-lookup"><span data-stu-id="d89ba-275">public [CoreWebView2Settings](microsoft-web-webview2-core-corewebview2settings.md) [Settings](#settings)</span></span>

#### <span data-ttu-id="d89ba-276">Source</span><span class="sxs-lookup"><span data-stu-id="d89ba-276">Source</span></span> 

<span data-ttu-id="d89ba-277">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="d89ba-277">The URI of the current top level document.</span></span>

> <span data-ttu-id="d89ba-278">パブリック文字列 [ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="d89ba-278">public string [Source](#source)</span></span>

<span data-ttu-id="d89ba-279">この値は、別のサイトやフラグメントナビゲーションへの移動などの場合に、SourceChanged イベント発生の一部として変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-279">This value potentially changes as a part of the SourceChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="d89ba-280">ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションにも同じように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-280">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

#### <span data-ttu-id="d89ba-281">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="d89ba-281">SourceChanged</span></span> 

<span data-ttu-id="d89ba-282">SourceChanged Source プロパティが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-282">SourceChanged fires when the Source property changes.</span></span>

> <span data-ttu-id="d89ba-283">パブリックイベント EventHandler< [CoreWebView2SourceChangedEventArgs](microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md)  >  [sourcechanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="d89ba-283">public event EventHandler< [CoreWebView2SourceChangedEventArgs](microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md) > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="d89ba-284">SourceChanged のサイトまたはフラグメントナビゲーションに移動する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-284">SourceChanged fires for navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="d89ba-285">ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションについては、このような操作は発生しません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-285">It will not fire for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span> <span data-ttu-id="d89ba-286">SourceChanged ドキュメントへのナビゲーションのためにコンテンツを読み込む前に、SourceChanged が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-286">SourceChanged fires before ContentLoading for navigation to a new document.</span></span>

#### <span data-ttu-id="d89ba-287">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="d89ba-287">WebMessageReceived</span></span> 

<span data-ttu-id="d89ba-288">WebMessageReceived は、CoreWebView2Settings 設定が設定され、WebView 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-288">WebMessageReceived fires when the CoreWebView2Settings.IsWebMessageEnabled setting is set and the top level document of the WebView calls `window.chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="d89ba-289">パブリックイベント EventHandler< [CoreWebView2WebMessageReceivedEventArgs](microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md)  >  [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="d89ba-289">public event EventHandler< [CoreWebView2WebMessageReceivedEventArgs](microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md) > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="d89ba-290">PostMessage 関数は、 `void postMessage(object)` JSON 変換でサポートされているオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d89ba-290">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span> <span data-ttu-id="d89ba-291">PostMessage が呼び出されると、ハンドラーの Invoke メソッドが、JSON 文字列に変換された postMessage のオブジェクトパラメーターと共に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-291">When postMessage is called, the handler's Invoke method will be called with the postMessage's object parameter converted to a JSON string.</span></span>

#### <span data-ttu-id="d89ba-292">WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="d89ba-292">WebResourceRequested</span></span> 

<span data-ttu-id="d89ba-293">WebResourceRequested は、AddWebResourceRequestedFilter で指定された Web リソース一致のリソースコンテキストフィルターと URL に対して、WebView で URL 要求 (network、file など) を実行したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-293">WebResourceRequested fires when a URL request (through network, file etc.) is made in the WebView for a Web resource matching resource context filter and URL specified in AddWebResourceRequestedFilter.</span></span>

> <span data-ttu-id="d89ba-294">パブリックイベント EventHandler< [CoreWebView2WebResourceRequestedEventArgs](microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md)  >  [WebResourceRequested](#webresourcerequested)</span><span class="sxs-lookup"><span data-stu-id="d89ba-294">public event EventHandler< [CoreWebView2WebResourceRequestedEventArgs](microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md) > [WebResourceRequested](#webresourcerequested)</span></span>

<span data-ttu-id="d89ba-295">このホストでは、要求を表示して変更したり、HTTP と同様のパターンで応答を提供したりすることができます。この場合、要求はすぐに完了します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-295">The host can view and modify the request or provide a response in a similar pattern to HTTP, in which case the request immediately completed.</span></span> <span data-ttu-id="d89ba-296">これには、承認ヘッダーなど、ネットワークスタックによって追加された要求ヘッダーが含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-296">This may not contain any request headers that are added by the network stack, such as Authorization headers.</span></span> <span data-ttu-id="d89ba-297">要求された web リソースは、イベント引数で遅延が発生しなかった場合に、イベントハンドラーから制御が返されるまでブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-297">The web resource requested can be blocked until the event handler returns if a deferral is not taken on the event args.</span></span> <span data-ttu-id="d89ba-298">延期が行われた場合、保留が完了するまで、要求された web リソースはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-298">If a deferral is taken, then the web resource requested is blocked until the deferral is completed.</span></span>

#### <span data-ttu-id="d89ba-299">WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="d89ba-299">WebResourceResponseReceived</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="d89ba-300">WebResourceResponseReceived イベントは、WebView が WebResource 要求に対する応答を受信して処理した後に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-300">WebResourceResponseReceived event fires after the WebView has received and processed the response for a WebResource request.</span></span>

> <span data-ttu-id="d89ba-301">パブリックイベント EventHandler< [CoreWebView2WebResourceResponseReceivedEventArgs](microsoft-web-webview2-core-corewebview2webresourceresponsereceivedeventargs.md)  >  [WebResourceResponseReceived](#webresourceresponsereceived)</span><span class="sxs-lookup"><span data-stu-id="d89ba-301">public event EventHandler< [CoreWebView2WebResourceResponseReceivedEventArgs](microsoft-web-webview2-core-corewebview2webresourceresponsereceivedeventargs.md) > [WebResourceResponseReceived](#webresourceresponsereceived)</span></span>

<span data-ttu-id="d89ba-302">イベント引数には、WebResourceResponse によって送信された WebResourceRequest が含まれています。これには、認証ヘッダーなど、関連付けられた WebResourceRequested イベントの一部として含まれていないネットワークスタックによって追加されたヘッダーも含まれています。</span><span class="sxs-lookup"><span data-stu-id="d89ba-302">The event args include the WebResourceRequest as sent by the wire and WebResourceResponse received, including any additional headers added by the network stack that were not be included as part of the associated WebResourceRequested event, such as Authentication headers.</span></span>

#### <span data-ttu-id="d89ba-303">WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="d89ba-303">WindowCloseRequested</span></span> 

<span data-ttu-id="d89ba-304">WindowCloseRequested が呼び出された後など、WebView 内のコンテンツがウィンドウを閉じる必要がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-304">WindowCloseRequested fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span>

> <span data-ttu-id="d89ba-305">public イベント EventHandler< object > [WindowCloseRequested](#windowcloserequested)</span><span class="sxs-lookup"><span data-stu-id="d89ba-305">public event EventHandler< object > [WindowCloseRequested](#windowcloserequested)</span></span>

<span data-ttu-id="d89ba-306">アプリが適切である場合は、アプリで WebView と関連するアプリのウィンドウを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-306">The app should close the WebView and related app window if that makes sense to the app.</span></span>

#### <span data-ttu-id="d89ba-307">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="d89ba-307">AddHostObjectToScript</span></span> 

<span data-ttu-id="d89ba-308">指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-308">Add the provided host object to script running in the WebView with the specified name.</span></span>

> <span data-ttu-id="d89ba-309">public void [Addhostobjecttoscript](#addhostobjecttoscript)(文字列名、オブジェクト rawobject)</span><span class="sxs-lookup"><span data-stu-id="d89ba-309">public void [AddHostObjectToScript](#addhostobjecttoscript)(string name, object rawObject)</span></span>

<span data-ttu-id="d89ba-310">ホストオブジェクトは、でホストオブジェクトプロキシとして公開され `window.chrome.webview.hostObjects.{name}` ます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-310">Host objects are exposed as host object proxies via `window.chrome.webview.hostObjects.{name}`.</span></span> <span data-ttu-id="d89ba-311">ホストオブジェクトプロキシは保証され、ホストオブジェクトを表すオブジェクトに解決されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-311">Host object proxies are promises and will resolve to an object representing the host object.</span></span> <span data-ttu-id="d89ba-312">WebView の JavaScript コードは、appObject に次の方法でアクセスして、appObject の属性とメソッドにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-312">JavaScript code in the WebView will be able to access appObject as following and then access attributes and methods of appObject.</span></span>

<span data-ttu-id="d89ba-313">IDispatch を使って IDispatch を実装するクラスを作成するには、公開するクラスごとに次の属性を使います。</span><span class="sxs-lookup"><span data-stu-id="d89ba-313">To create a IDispatch implementing class in C# use the following attributes on each class you intend to expose.</span></span> 
```
// Bridge and BridgeAnotherClass are C# classes that implement IDispatch and works with AddRemoteObject.
[ClassInterface(ClassInterfaceType.AutoDual)]
[ComVisible(true)]
public class BridgeAnotherClass
{
    // Sample property.
    public string Prop { get; set; } = "Example";
}

[ClassInterface(ClassInterfaceType.AutoDual)]
[ComVisible(true)]
public class Bridge
{
    public string Func(string param)
    {
        return "Example: " + param;
    }

    public BridgeAnotherClass AnotherObject { get; set; } = new BridgeAnotherClass();

    // Sample indexed property.
    [System.Runtime.CompilerServices.IndexerName("Items")]
    public string this[int index]
    {
        get { return m_dictionary[index]; }
        set { m_dictionary[index] = value; }
    }
    private Dictionary<int, string> m_dictionary = new Dictionary<int, string>();
}
```
 <span data-ttu-id="d89ba-314">次に、これらのクラスのインスタンスを次の方法で追加し `AddHostObjectToScript` ます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-314">Then add instances of those classes via `AddHostObjectToScript`:</span></span> 
```
webView.CoreWebView2.AddHostObjectToScript("bridge", new Bridge());
```
 <span data-ttu-id="d89ba-315">次に、スクリプトでメソッドを呼び出して、AddHostObjectToScript で追加されたオブジェクトのこれらのプロパティにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-315">And then in script you can call the methods, and access those properties of the objects added via AddHostObjectToScript:</span></span> 
```
// Find added objects on the hostObjects property
const bridge = chrome.webview.hostObjects.bridge;

// Call a method and pass in a parameter.
// The result is another proxy promise so you must await to get the result.
console.log(await bridge.Func("testing..."));

// A property may be another object as long as its class also implements
// IDispatch.
// Getting a property also gets a proxy promise you must await.
const propValue = await bridge.AnotherObject.Prop;
console.log(propValue);

// Indexed properties
let index = 123;
bridge[index] = "test";
let result = await bridge[index];
console.log(result);
```

<span data-ttu-id="d89ba-316">単純型、IDispatch、配列はサポートされていますが、ジェネリック IUnknown、VT_DECIMAL、または VT_RECORD variant はサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d89ba-316">Note that while simple types, IDispatch and array are supported, generic IUnknown, VT_DECIMAL, or VT_RECORD variant is not supported.</span></span> <span data-ttu-id="d89ba-317">コールバック関数などのリモート JavaScript オブジェクトは、IDispatch を実装するオブジェクトと共に VT_DISPATCH VARIANT として表されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-317">Remote JavaScript objects like callback functions are represented as an VT_DISPATCH VARIANT with the object implementing IDispatch.</span></span> <span data-ttu-id="d89ba-318">JavaScript のコールバックメソッドは、DISPID の DISPID_VALUE を使って呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-318">The JavaScript callback method may be invoked using DISPID_VALUE for the DISPID.</span></span> <span data-ttu-id="d89ba-319">入れ子になった配列は、最大3レベルまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-319">Nested arrays are supported up to a depth of 3.</span></span> <span data-ttu-id="d89ba-320">参照型での配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-320">Arrays of by reference types are not supported.</span></span> <span data-ttu-id="d89ba-321">VT_EMPTY と VT_NULL は JavaScript に NULL としてマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-321">VT_EMPTY and VT_NULL are mapped into JavaScript as null.</span></span> <span data-ttu-id="d89ba-322">JavaScript は null で、undefined は VT_EMPTY にマップされます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-322">In JavaScript null and undefined are mapped to VT_EMPTY.</span></span>

<span data-ttu-id="d89ba-323">さらに、すべてのホストオブジェクトがとして公開され `window.chrome.webview.hostObjects.sync.{name}` ます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-323">Additionally, all host objects are exposed as `window.chrome.webview.hostObjects.sync.{name}`.</span></span> <span data-ttu-id="d89ba-324">ここでは、ホストオブジェクトが同期ホストオブジェクトプロキシとして公開されています。</span><span class="sxs-lookup"><span data-stu-id="d89ba-324">Here the host objects are exposed as synchronous host object proxies.</span></span> <span data-ttu-id="d89ba-325">これらは、ホストコードが実行されるためのクロスプロセスとの通信を待機している、実行中のスクリプトの実行を待機していて、機能やプロパティへのアクセスを同期することはできません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-325">These are not promises and calls to functions or property access synchronously block running script waiting to communicate cross process for the host code to run.</span></span> <span data-ttu-id="d89ba-326">これにより、信頼性の問題が発生する可能性があり、上記で説明した promise ベースの非同期 API を使うことをお勧めし `window.chrome.webview.hostObjects.{name}` ます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-326">Accordingly this can result in reliability issues and it is recommended that you use the promise based asynchronous `window.chrome.webview.hostObjects.{name}` API described above.</span></span>

<span data-ttu-id="d89ba-327">同期ホストオブジェクトプロキシと非同期ホストオブジェクトプロキシは、どちらも同じホストオブジェクトをプロキシすることができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-327">Synchronous host object proxies and asynchronous host object proxies can both proxy the same host object.</span></span> <span data-ttu-id="d89ba-328">1つのプロキシによって加えられたリモートの変更は、他のプロキシと同期か非同期かにかかわらず、同じホストオブジェクトの他のプロキシにも反映されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-328">Remote changes made by one proxy will be reflected in any other proxy of that same host object whether the other proxies and synchronous or asynchronous.</span></span>

<span data-ttu-id="d89ba-329">JavaScript はネイティブコードへの同期呼び出しでブロックされますが、ネイティブコードは JavaScript にコールバックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-329">While JavaScript is blocked on a synchronous call to native code, that native code is unable to call back to JavaScript.</span></span> <span data-ttu-id="d89ba-330">これを実行しようとすると、HRESULT_FROM_WIN32 (ERROR_POSSIBLE_DEADLOCK) で失敗します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-330">Attempts to do so will fail with HRESULT_FROM_WIN32(ERROR_POSSIBLE_DEADLOCK).</span></span>

<span data-ttu-id="d89ba-331">ホストオブジェクトプロキシは、すべてのプロパティ get、プロパティセット、メソッド呼び出しを受け取る JavaScript プロキシオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d89ba-331">Host object proxies are JavaScript Proxy objects that intercept all property get, property set, and method invocations.</span></span> <span data-ttu-id="d89ba-332">関数またはオブジェクトプロトタイプの一部であるプロパティまたはメソッドはローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-332">Properties or methods that are a part of the Function or Object prototype are run locally.</span></span> <span data-ttu-id="d89ba-333">さらに、配列内のすべてのプロパティまたはメソッド `chrome.webview.hostObjects.options.forceLocalProperties` もローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-333">Additionally any property or method in the array `chrome.webview.hostObjects.options.forceLocalProperties` will also be run locally.</span></span> <span data-ttu-id="d89ba-334">これは既定で、JavaScript のような、というようなオプションのメソッドが含まれてい `toJSON` `Symbol.toPrimitive` ます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-334">This defaults to including optional methods that have meaning in JavaScript like `toJSON` and `Symbol.toPrimitive`.</span></span> <span data-ttu-id="d89ba-335">必要に応じて、この配列に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-335">You can add more to this array as required.</span></span>

<span data-ttu-id="d89ba-336">最善の手段と `chrome.webview.hostObjects.cleanupSome` して、ガベージコレクションのホストオブジェクトプロキシを収集する方法があります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-336">There's a method `chrome.webview.hostObjects.cleanupSome` that will best effort garbage collect host object proxies.</span></span>

<span data-ttu-id="d89ba-337">ホストオブジェクトプロキシには、ローカルで実行される次のメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-337">Host object proxies additionally have the following methods which run locally:</span></span>

* <span data-ttu-id="d89ba-338">applyHostFunction、getHostProperty、setHostProperty: ホストオブジェクトでメソッドの呼び出し、プロパティの取得、プロパティの設定を実行します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-338">applyHostFunction, getHostProperty, setHostProperty: Perform a method invocation, property get, or property set on the host object.</span></span> <span data-ttu-id="d89ba-339">これらのメソッドを使うと、競合するローカルメソッドまたはプロパティがある場合に、メソッドまたはプロパティを明示的に強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-339">You can use these to explicitly force a method or property to run remotely if there is a conflicting local method or property.</span></span> <span data-ttu-id="d89ba-340">たとえば、 `proxy.toString()` はプロキシオブジェクトに対してローカル toString メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-340">For instance, `proxy.toString()` will run the local toString method on the proxy object.</span></span> <span data-ttu-id="d89ba-341">ただし `proxy.applyHostFunction('toString')` `toString` 、代わりに host プロキシオブジェクトで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-341">But `proxy.applyHostFunction('toString')` runs `toString` on the host proxied object instead.</span></span>

* <span data-ttu-id="d89ba-342">getLocalProperty、setLocalProperty: プロパティ get、またはローカルにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-342">getLocalProperty, setLocalProperty: Perform property get, or property set locally.</span></span> <span data-ttu-id="d89ba-343">これらのメソッドを使うと、ホストオブジェクトプロキシ自体でプロパティを取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-343">You can use these methods to force getting or setting a property on the host object proxy itself rather than on the host object it represents.</span></span> <span data-ttu-id="d89ba-344">たとえば、 `proxy.unknownProperty` は、host プロキシオブジェクトから名前が付けられたプロパティを取得し `unknownProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-344">For instance, `proxy.unknownProperty` will get the property named `unknownProperty` from the host proxied object.</span></span> <span data-ttu-id="d89ba-345">ただし、この `proxy.getLocalProperty('unknownProperty')` プロパティの値は `unknownProperty` プロキシオブジェクト自体で取得されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-345">But `proxy.getLocalProperty('unknownProperty')` will get the value of the property `unknownProperty` on the proxy object itself.</span></span>

* <span data-ttu-id="d89ba-346">同期: 非同期ホストオブジェクトプロキシは、同じホストオブジェクトの同期ホストオブジェクトプロキシの promise を返す同期メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-346">sync: Asynchronous host object proxies expose a sync method which returns a promise for a synchronous host object proxy for the same host object.</span></span> <span data-ttu-id="d89ba-347">たとえば、 `chrome.webview.hostObjects.sample.methodCall()` 非同期ホストオブジェクトプロキシを返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-347">For example, `chrome.webview.hostObjects.sample.methodCall()` returns an asynchronous host object proxy.</span></span> <span data-ttu-id="d89ba-348">代わりに、メソッドを使用して `sync` 同期ホストオブジェクトプロキシを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-348">You can use the `sync` method to obtain a synchronous host object proxy instead:</span></span> `const syncProxy = await chrome.webview.hostObjects.sample.methodCall().sync()`

* <span data-ttu-id="d89ba-349">非同期: 同期ホストオブジェクトプロキシは、同じホストオブジェクトの非同期ホストオブジェクトプロキシをブロックして返す async メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-349">async: Synchronous host object proxies expose an async method which blocks and returns an asynchronous host object proxy for the same host object.</span></span> <span data-ttu-id="d89ba-350">たとえば、 `chrome.webview.hostObjects.sync.sample.methodCall()` 同期ホストオブジェクトプロキシを返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-350">For example, `chrome.webview.hostObjects.sync.sample.methodCall()` returns a synchronous host object proxy.</span></span> <span data-ttu-id="d89ba-351">このブロックに対してメソッドを呼び出す `async` と、同じホストオブジェクトの非同期ホストオブジェクトプロキシが返されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-351">Calling the `async` method on this blocks and then returns an asynchronous host object proxy for the same host object:</span></span> `const asyncProxy = chrome.webview.hostObjects.sync.sample.methodCall().async()`

* <span data-ttu-id="d89ba-352">次に、非同期ホストオブジェクトプロキシには then メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-352">then: Asynchronous host object proxies have a then method.</span></span> <span data-ttu-id="d89ba-353">これにより、awaitable を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-353">This allows them to be awaitable.</span></span> `then` <span data-ttu-id="d89ba-354">は、host オブジェクトの表現によって解決される promise を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-354">will return a promise that resolves with a representation of the host object.</span></span> <span data-ttu-id="d89ba-355">プロキシが JavaScript リテラルを表す場合は、そのリテラルのコピーがローカルに返されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-355">If the proxy represents a JavaScript literal then a copy of that is returned locally.</span></span> <span data-ttu-id="d89ba-356">プロキシが関数を表す場合は、awaitable 以外のプロキシが返されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-356">If the proxy represents a function then a non-awaitable proxy is returned.</span></span> <span data-ttu-id="d89ba-357">プロキシがリテラルプロパティと関数プロパティが混在した JavaScript オブジェクトを表している場合、オブジェクトのコピーが、一部のプロパティをホストオブジェクトプロキシとして返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-357">If the proxy represents a JavaScript object with a mix of literal properties and function properties, then the a copy of the object is returned with some properties as host object proxies.</span></span>

<span data-ttu-id="d89ba-358">その他のすべてのプロパティとメソッドの呼び出し (上記のリモートオブジェクトプロキシメソッド、forceLocalProperties リスト、関数およびオブジェクトプロトタイプのプロパティ以外) は、リモートで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-358">All other property and method invocations (other than the above Remote object proxy methods, forceLocalProperties list, and properties on Function and Object prototypes) are run remotely.</span></span> <span data-ttu-id="d89ba-359">非同期ホストオブジェクトプロキシは、メソッドのリモート呼び出しまたはプロパティの取得の非同期完了を表す promise を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-359">Asynchronous host object proxies return a promise representing asynchronous completion of remotely invoking the method, or getting the property.</span></span> <span data-ttu-id="d89ba-360">この保証は、リモート操作が完了した後に解決され、その約束が、演算の結果値に解決されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-360">The promise resolves after the remote operations complete and the promises resolve to the resulting value of the operation.</span></span> <span data-ttu-id="d89ba-361">同期ホストオブジェクトプロキシは、同じように動作しますが、JavaScript の実行をブロックし、リモート操作が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-361">Synchronous host object proxies work similarly but block JavaScript execution and wait for the remote operation to complete.</span></span>

<span data-ttu-id="d89ba-362">非同期ホストオブジェクトプロキシのプロパティの設定は、若干異なります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-362">Setting a property on an asynchronous host object proxy works slightly differently.</span></span> <span data-ttu-id="d89ba-363">Set はすぐに戻り値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-363">The set returns immediately and the return value is the value that will be set.</span></span> <span data-ttu-id="d89ba-364">これは JavaScript プロキシオブジェクトの要件です。</span><span class="sxs-lookup"><span data-stu-id="d89ba-364">This is a requirement of the JavaScript Proxy object.</span></span> <span data-ttu-id="d89ba-365">プロパティセットが完了するのを非同期的に待つ必要がある場合は、上記のように、setHostProperty メソッドを使って、promise を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-365">If you need to asynchronously wait for the property set to complete, use the setHostProperty method which returns a promise as described above.</span></span> <span data-ttu-id="d89ba-366">同期オブジェクトプロパティセットプロパティは、プロパティが設定されるまで同期的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-366">Synchronous object property set property synchronously blocks until the property is set.</span></span>

#### <span data-ttu-id="d89ba-367">AddScriptToExecuteOnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="d89ba-367">AddScriptToExecuteOnDocumentCreatedAsync</span></span> 

<span data-ttu-id="d89ba-368">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-368">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="d89ba-369">パブリック async タスク< 文字列 > [AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync)(文字列 javaScript)</span><span class="sxs-lookup"><span data-stu-id="d89ba-369">public async Task< string > [AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync)(string javaScript)</span></span>

##### <span data-ttu-id="d89ba-370">返し</span><span class="sxs-lookup"><span data-stu-id="d89ba-370">Returns</span></span>
<span data-ttu-id="d89ba-371">[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)を呼び出したときに渡すことができるスクリプト id を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-371">Returns a script id that may be passed when calling [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated).</span></span> 

<span data-ttu-id="d89ba-372">挿入されたスクリプトは、RemoveScriptToExecuteOnDocumentCreated で削除されるまで、将来のすべての上位レベルのドキュメントと子フレームのナビゲーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-372">The injected script will apply to all future top level document and child frame navigations until removed with RemoveScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="d89ba-373">これは非同期的に適用されるため、今後のナビゲーションでスクリプトを実行する準備ができていることを確認する前に、完了ハンドラーが実行されるまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-373">This is applied asynchronously and you must wait for the completion handler to run before you can be sure that the script is ready to execute on future navigations.</span></span>

<span data-ttu-id="d89ba-374">[サンドボックス](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)のプロパティまたは[コンテンツセキュリティポリシーの HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)によって、HTML ドキュメントに何らかのサンドボックスが含まれている場合は、このスクリプトの実行に影響します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-374">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="d89ba-375">たとえば、' allow als ' キーワードが設定されていない場合、関数への呼び出し `alert` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-375">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

#### <span data-ttu-id="d89ba-376">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="d89ba-376">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="d89ba-377">URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-377">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="d89ba-378">パブリック void [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(文字列 Uri、CoreWebView2WebResourceContext resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="d89ba-378">public void [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(string uri, CoreWebView2WebResourceContext ResourceContext)</span></span>

<span data-ttu-id="d89ba-379">URI パラメーターには、ワイルドカード文字列 (' \* '、0以上、'? ': まったく1つ) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-379">The URI parameter can be a wildcard string ('\*': zero or more, '?': exactly one).</span></span> <span data-ttu-id="d89ba-380">nullptr は、L "" と同じです。</span><span class="sxs-lookup"><span data-stu-id="d89ba-380">nullptr is equivalent to L"".</span></span> <span data-ttu-id="d89ba-381">リソースコンテキストフィルターの説明については、「CoreWebView2WebResourceContext enum」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d89ba-381">See CoreWebView2WebResourceContext enum for description of resource context filters.</span></span>

#### <span data-ttu-id="d89ba-382">Calldev| Protocolmethodasync</span><span class="sxs-lookup"><span data-stu-id="d89ba-382">CallDevToolsProtocolMethodAsync</span></span> 

<span data-ttu-id="d89ba-383">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-383">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="d89ba-384">パブリック async タスク< 文字列 > [CalldevparametersAsJson Protocolmethodasync](#calldevtoolsprotocolmethodasync)(文字列 methodName, string)</span><span class="sxs-lookup"><span data-stu-id="d89ba-384">public async Task< string > [CallDevToolsProtocolMethodAsync](#calldevtoolsprotocolmethodasync)(string methodName, string parametersAsJson)</span></span>

##### <span data-ttu-id="d89ba-385">返し</span><span class="sxs-lookup"><span data-stu-id="d89ba-385">Returns</span></span>
<span data-ttu-id="d89ba-386">メソッドの戻りオブジェクトを表す JSON 文字列。</span><span class="sxs-lookup"><span data-stu-id="d89ba-386">A JSON string that represents the method's return object.</span></span> 

<span data-ttu-id="d89ba-387">使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d89ba-387">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="d89ba-388">MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="d89ba-388">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="d89ba-389">ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。</span><span class="sxs-lookup"><span data-stu-id="d89ba-389">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="d89ba-390">メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-390">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="d89ba-391">Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-391">Invoke will be called with the method's return object as a JSON string.</span></span>

#### <span data-ttu-id="d89ba-392">CapturePreviewAsync</span><span class="sxs-lookup"><span data-stu-id="d89ba-392">CapturePreviewAsync</span></span> 

<span data-ttu-id="d89ba-393">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d89ba-393">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="d89ba-394">パブリック async タスク [CapturePreviewAsync](#capturepreviewasync)(CoreWebView2CapturePreviewImageFormat imageformat、ストリーム画像 estream)</span><span class="sxs-lookup"><span data-stu-id="d89ba-394">public async Task [CapturePreviewAsync](#capturepreviewasync)(CoreWebView2CapturePreviewImageFormat imageFormat, Stream imageStream)</span></span>

<span data-ttu-id="d89ba-395">ImageFormat パラメーターを使用して、画像の形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-395">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="d89ba-396">結果のイメージバイナリデータは、指定された imageStream パラメーターに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-396">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="d89ba-397">CapturePreview がストリームへの書き込みを終了すると、指定された handler パラメーターの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-397">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

#### <span data-ttu-id="d89ba-398">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d89ba-398">ExecuteScriptAsync</span></span> 

<span data-ttu-id="d89ba-399">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-399">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="d89ba-400">パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列 javaScript)</span><span class="sxs-lookup"><span data-stu-id="d89ba-400">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

##### <span data-ttu-id="d89ba-401">返し</span><span class="sxs-lookup"><span data-stu-id="d89ba-401">Returns</span></span>
<span data-ttu-id="d89ba-402">指定された JavaScript を実行した結果を表す JSON エンコードされた文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-402">Returns a JSON encoded string that represents the result of running the provided JavaScript.</span></span> 

<span data-ttu-id="d89ba-403">このメソッドは、指定された JavaScript を非同期的に実行し、指定された JavaScript の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-403">This method runs the provided JavaScript asynchronously and will return the result of the provided JavaScript.</span></span> <span data-ttu-id="d89ba-404">提供された JavaScript の結果が `undefined` 、参照循環を含んでいる場合、または JSON にエンコードできない場合は、文字列 ' null ' が返されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-404">If the result of the provided JavaScript is `undefined`, contains a reference cycle, or otherwise cannot be encoded into JSON, the string 'null' is returned.</span></span> <span data-ttu-id="d89ba-405">指定した JavaScript で呼び出される関数に明示的な戻り値がない場合 `undefined` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-405">If a called function in the provided JavaScript has no explicit return value, `undefined` is returned.</span></span> <span data-ttu-id="d89ba-406">指定した JavaScript が処理されない例外をスローすると、' null ' が返されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-406">If the provided JavaScript throws an unhandled exception, 'null' is returned.</span></span> <span data-ttu-id="d89ba-407">NavigationStarting イベントの後にこのメソッドが呼び出されると、指定された JavaScript は、読み込み時に新しいドキュメントで実行されます。これは、ContentLoading がトリガーされたときと同じです。</span><span class="sxs-lookup"><span data-stu-id="d89ba-407">If this method is called after a NavigationStarting event, the provided JavaScript is run on the new document when it loads, around the same time that ContentLoading is triggered.</span></span> <span data-ttu-id="d89ba-408">ExecutesCoreWebView2Settings がに設定されている場合でも動作 `FALSE` します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-408">ExecuteScriptAsync will work even if CoreWebView2Settings.IsScriptEnabled is set to `FALSE`.</span></span>

#### <span data-ttu-id="d89ba-409">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="d89ba-409">GetDevToolsProtocolEventReceiver</span></span> 

<span data-ttu-id="d89ba-410">DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-410">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>

> <span data-ttu-id="d89ba-411">パブリック CoreWebView2DevToolsProtocolEventReceiver [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(文字列 eventName)</span><span class="sxs-lookup"><span data-stu-id="d89ba-411">public CoreWebView2DevToolsProtocolEventReceiver [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(string eventName)</span></span>

<span data-ttu-id="d89ba-412">使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d89ba-412">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="d89ba-413">MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="d89ba-413">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="d89ba-414">ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。</span><span class="sxs-lookup"><span data-stu-id="d89ba-414">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="d89ba-415">メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-415">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="d89ba-416">Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-416">Invoke will be called with the method's return object as a JSON string.</span></span>

#### <span data-ttu-id="d89ba-417">GoBack</span><span class="sxs-lookup"><span data-stu-id="d89ba-417">GoBack</span></span> 

<span data-ttu-id="d89ba-418">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-418">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="d89ba-419">パブリック void [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="d89ba-419">public void [GoBack](#goback)()</span></span>

#### <span data-ttu-id="d89ba-420">GoForward</span><span class="sxs-lookup"><span data-stu-id="d89ba-420">GoForward</span></span> 

<span data-ttu-id="d89ba-421">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-421">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="d89ba-422">パブリック void [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="d89ba-422">public void [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="d89ba-423">検索</span><span class="sxs-lookup"><span data-stu-id="d89ba-423">Navigate</span></span> 

<span data-ttu-id="d89ba-424">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-424">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="d89ba-425">パブリック void の [移動](#navigate)(文字列 uri)</span><span class="sxs-lookup"><span data-stu-id="d89ba-425">public void [Navigate](#navigate)(string uri)</span></span>

<span data-ttu-id="d89ba-426">詳細については、ナビゲーションイベントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d89ba-426">See the navigation events for more information.</span></span> <span data-ttu-id="d89ba-427">これによってナビゲーションが開始されることに注意してください。この操作が完了すると、対応する NavigationStarting イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-427">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

#### <span data-ttu-id="d89ba-428">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="d89ba-428">NavigateToString</span></span> 

<span data-ttu-id="d89ba-429">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-429">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="d89ba-430">パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="d89ba-430">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="d89ba-431">HtmlContent パラメーターの合計サイズは、2 MB を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-431">The htmlContent parameter may not be larger than 2 MB in total size.</span></span> <span data-ttu-id="d89ba-432">新しいページの起点は "空白" になります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-432">The origin of the new page will be about:blank.</span></span>

#### <span data-ttu-id="d89ba-433">Opendevツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="d89ba-433">OpenDevToolsWindow</span></span> 

<span data-ttu-id="d89ba-434">WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-434">Opens the DevTools window for the current document in the WebView.</span></span>

> <span data-ttu-id="d89ba-435">パブリック void [Opendevツールウィンドウ](#opendevtoolswindow)()</span><span class="sxs-lookup"><span data-stu-id="d89ba-435">public void [OpenDevToolsWindow](#opendevtoolswindow)()</span></span>

<span data-ttu-id="d89ba-436">DevTools ウィンドウが既に開いているときに、何も呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-436">Does nothing if called when the DevTools window is already open.</span></span>

#### <span data-ttu-id="d89ba-437">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="d89ba-437">PostWebMessageAsJson</span></span> 

<span data-ttu-id="d89ba-438">指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-438">Post the specified webMessage to the top level document in this WebView.</span></span>

> <span data-ttu-id="d89ba-439">パブリック void [Postwebmessageasjson](#postwebmessageasjson)(String webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="d89ba-439">public void [PostWebMessageAsJson](#postwebmessageasjson)(string webMessageAsJson)</span></span>

<span data-ttu-id="d89ba-440">最上位のドキュメントのウィンドウには、"." というメッセージイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-440">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="d89ba-441">このドキュメントの JavaScript は、次のようにしてイベントをサブスクライブし、サブスクライブを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-441">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span>

```
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

<span data-ttu-id="d89ba-442">イベント引数は、のインスタンス `MessageEvent` です。</span><span class="sxs-lookup"><span data-stu-id="d89ba-442">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="d89ba-443">CoreWebView2Settings の設定は true である必要があります。また、このメソッドは E_INVALIDARG で失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-443">The CoreWebView2Settings.IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="d89ba-444">イベント arg の data プロパティは、JSON 文字列として JavaScript オブジェクトに解析された webMessage 文字列のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="d89ba-444">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="d89ba-445">イベント arg の source プロパティは、オブジェクトへの参照です `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="d89ba-445">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="d89ba-446">WebView の HTML ドキュメントからホストにメッセージを送信する方法については、「WebMessageReceived イベント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d89ba-446">See WebMessageReceived event for information on sending messages from the HTML document in the WebView to the host.</span></span> <span data-ttu-id="d89ba-447">このメッセージは非同期的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-447">This message is sent asynchronously.</span></span> <span data-ttu-id="d89ba-448">メッセージがページに投稿される前にナビゲーションが発生した場合、メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-448">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

#### <span data-ttu-id="d89ba-449">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="d89ba-449">PostWebMessageAsString</span></span> 

<span data-ttu-id="d89ba-450">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="d89ba-450">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="d89ba-451">パブリック void [Postwebmessageasstring](#postwebmessageasstring)(String webmessageasstring)</span><span class="sxs-lookup"><span data-stu-id="d89ba-451">public void [PostWebMessageAsString](#postwebmessageasstring)(string webMessageAsString)</span></span>

<span data-ttu-id="d89ba-452">これは、PostWebMessageAsJson とまったく同じように動作し `window.chrome.webview` ますが、message イベント arg の data プロパティは、webMessageAsString と同じ値を持つ文字列になります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-452">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="d89ba-453">JSON オブジェクトではなく単純な文字列を使って通信する場合は、PostWebMessageAsJson の代わりに、これを使います。</span><span class="sxs-lookup"><span data-stu-id="d89ba-453">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="d89ba-454">再</span><span class="sxs-lookup"><span data-stu-id="d89ba-454">Reload</span></span> 

<span data-ttu-id="d89ba-455">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="d89ba-455">Reload the current page.</span></span>

> <span data-ttu-id="d89ba-456">パブリックの void [再読み込み](#reload)()</span><span class="sxs-lookup"><span data-stu-id="d89ba-456">public void [Reload](#reload)()</span></span>

<span data-ttu-id="d89ba-457">これは、すべてのナビゲーションイベント (HTTP キャッシュ内のエントリを含む) を含む、現在のトップレベルドキュメントの URI に移動する操作と似ています。</span><span class="sxs-lookup"><span data-stu-id="d89ba-457">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="d89ba-458">ただし、戻る/forward 履歴は変更されません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-458">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="d89ba-459">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="d89ba-459">RemoveHostObjectFromScript</span></span> 

<span data-ttu-id="d89ba-460">名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="d89ba-460">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>

> <span data-ttu-id="d89ba-461">パブリック void [Removehostobjectfromscript](#removehostobjectfromscript)(文字列名)</span><span class="sxs-lookup"><span data-stu-id="d89ba-461">public void [RemoveHostObjectFromScript](#removehostobjectfromscript)(string name)</span></span>

<span data-ttu-id="d89ba-462">新しいアクセスの試行は拒否されますが、そのオブジェクトが WebView の JavaScript コードによって既に取得されている場合は、JavaScript コードはそのオブジェクトに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d89ba-462">While new access attempts will be denied, if the object is already obtained by JavaScript code in the WebView, the JavaScript code will continue to have access to that object.</span></span> <span data-ttu-id="d89ba-463">既に削除されているか追加されていない名前に対してこのメソッドを呼び出すと、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-463">Calling this method for a name that is already removed or never added will fail.</span></span>

#### <span data-ttu-id="d89ba-464">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="d89ba-464">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="d89ba-465">指定したスクリプト id を使用して、AddScriptToExecuteOnDocumentCreated で追加された対応する JavaScript を削除します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-465">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated with the specified script id.</span></span>

> <span data-ttu-id="d89ba-466">パブリック void [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(文字列 id)</span><span class="sxs-lookup"><span data-stu-id="d89ba-466">public void [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(string id)</span></span>

#### <span data-ttu-id="d89ba-467">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="d89ba-467">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="d89ba-468">以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-468">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="d89ba-469">パブリック void [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(文字列 Uri、 [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="d89ba-469">public void [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(string uri, [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) ResourceContext)</span></span>

<span data-ttu-id="d89ba-470">同じフィルターが複数回追加された場合は、削除が有効になるまで何度も削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d89ba-470">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="d89ba-471">追加されていないフィルターの E_INVALIDARG を返します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-471">Returns E_INVALIDARG for a filter that was never added.</span></span>

#### <span data-ttu-id="d89ba-472">Stop</span><span class="sxs-lookup"><span data-stu-id="d89ba-472">Stop</span></span> 

<span data-ttu-id="d89ba-473">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="d89ba-473">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="d89ba-474">パブリック void [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="d89ba-474">public void [Stop](#stop)()</span></span>

<span data-ttu-id="d89ba-475">スクリプトは停止されません。</span><span class="sxs-lookup"><span data-stu-id="d89ba-475">Does not stop scripts.</span></span>

