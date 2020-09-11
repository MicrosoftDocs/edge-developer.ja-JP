---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2 の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2。
ms.openlocfilehash: ca31ddd3536350d3b3bdd02b445b4c47589f7dba
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011112"
---
# <span data-ttu-id="3e441-104">0.9.579 クラスの WebView2 クラス (CoreWebView2)</span><span class="sxs-lookup"><span data-stu-id="3e441-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2 class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="3e441-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="3e441-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="3e441-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="3e441-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="3e441-107">WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-107">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="3e441-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="3e441-108">Summary</span></span>

 <span data-ttu-id="3e441-109">Members</span><span class="sxs-lookup"><span data-stu-id="3e441-109">Members</span></span>                        | <span data-ttu-id="3e441-110">説明</span><span class="sxs-lookup"><span data-stu-id="3e441-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3e441-111">BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="3e441-111">BrowserProcessId</span></span>](#browserprocessid) | <span data-ttu-id="3e441-112">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="3e441-112">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="3e441-113">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="3e441-113">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="3e441-114">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-114">Returns true if the webview can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="3e441-115">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="3e441-115">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="3e441-116">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-116">Returns true if the webview can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="3e441-117">ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="3e441-117">ContainsFullScreenElement</span></span>](#containsfullscreenelement) | <span data-ttu-id="3e441-118">WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3e441-118">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="3e441-119">ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="3e441-119">ContainsFullScreenElementChanged</span></span>](#containsfullscreenelementchanged) | <span data-ttu-id="3e441-120">"の場合、要素のプロパティが変更されたときに通知します。</span><span class="sxs-lookup"><span data-stu-id="3e441-120">Notifies when the ContainsFullScreenElement property changes.</span></span>
[<span data-ttu-id="3e441-121">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="3e441-121">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="3e441-122">ContentLoading は、コンテンツが読み込まれる前に発生します。 AddScriptToExecuteOnDocumentCreated ContentLoading によって追加されたスクリプトは、同じページナビゲーション (フラグメントナビゲーションや履歴の推移など) が発生した場合には発生しません。</span><span class="sxs-lookup"><span data-stu-id="3e441-122">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated ContentLoading will not fire if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span>
[<span data-ttu-id="3e441-123">DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="3e441-123">DocumentTitle</span></span>](#documenttitle) | <span data-ttu-id="3e441-124">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="3e441-124">The title for the current top level document.</span></span>
[<span data-ttu-id="3e441-125">ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="3e441-125">DocumentTitleChanged</span></span>](#documenttitlechanged) | <span data-ttu-id="3e441-126">イベントは、WebView の DocumentTitle プロパティが変更されたとき、または NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-126">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>
[<span data-ttu-id="3e441-127">FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="3e441-127">FrameNavigationCompleted</span></span>](#framenavigationcompleted) | <span data-ttu-id="3e441-128">FrameNavigationCompleted イベントが発生するのは、子フレームが完全に読み込まれた (読み込みが開始された) か、エラーが発生して読み込みを停止したときです。</span><span class="sxs-lookup"><span data-stu-id="3e441-128">FrameNavigationCompleted event fires when a child frame has completely loaded (body.onload has fired) or loading stopped with error.</span></span>
[<span data-ttu-id="3e441-129">FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="3e441-129">FrameNavigationStarting</span></span>](#framenavigationstarting) | <span data-ttu-id="3e441-130">FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-130">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span>
[<span data-ttu-id="3e441-131">変更履歴</span><span class="sxs-lookup"><span data-stu-id="3e441-131">HistoryChanged</span></span>](#historychanged) | <span data-ttu-id="3e441-132">履歴は、トップレベルのドキュメントのナビゲーション履歴の変更をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="3e441-132">HistoryChange listen to the change of navigation history for the top level document.</span></span>
[<span data-ttu-id="3e441-133">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="3e441-133">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="3e441-134">NavigationCompleted イベントは、WebView が完全に読み込まれたとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-134">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>
[<span data-ttu-id="3e441-135">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="3e441-135">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="3e441-136">NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-136">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span>
[<span data-ttu-id="3e441-137">NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="3e441-137">NewWindowRequested</span></span>](#newwindowrequested) | <span data-ttu-id="3e441-138">ウィンドウを開くなど、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-138">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span>
[<span data-ttu-id="3e441-139">PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="3e441-139">PermissionRequested</span></span>](#permissionrequested) | <span data-ttu-id="3e441-140">WebView のコンテンツが権限のある一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-140">Fires when content in a WebView requests permission to access some privileged resources.</span></span>
[<span data-ttu-id="3e441-141">ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="3e441-141">ProcessFailed</span></span>](#processfailed) | <span data-ttu-id="3e441-142">WebView プロセスが予期せず終了した場合、または応答不能になったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-142">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>
[<span data-ttu-id="3e441-143">Scriptて開く</span><span class="sxs-lookup"><span data-stu-id="3e441-143">ScriptDialogOpening</span></span>](#scriptdialogopening) | <span data-ttu-id="3e441-144">イベントは、webview の JavaScript ダイアログ (警告、確認、またはプロンプト) が表示されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-144">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span>
[<span data-ttu-id="3e441-145">設定</span><span class="sxs-lookup"><span data-stu-id="3e441-145">Settings</span></span>](#settings) | <span data-ttu-id="3e441-146">CoreWebView2Settings オブジェクトには、実行に関するさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e441-146">The CoreWebView2Settings object contains various modifiable settings for the running</span></span>
[<span data-ttu-id="3e441-147">Source</span><span class="sxs-lookup"><span data-stu-id="3e441-147">Source</span></span>](#source) | <span data-ttu-id="3e441-148">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="3e441-148">The URI of the current top level document.</span></span>
[<span data-ttu-id="3e441-149">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="3e441-149">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="3e441-150">SourceChanged Source プロパティが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-150">SourceChanged fires when the Source property changes.</span></span>
[<span data-ttu-id="3e441-151">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="3e441-151">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="3e441-152">このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。</span><span class="sxs-lookup"><span data-stu-id="3e441-152">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="3e441-153">WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="3e441-153">WebResourceRequested</span></span>](#webresourcerequested) | <span data-ttu-id="3e441-154">AddWebResourceRequestedFilter で追加された一致する URL とリソースコンテキストフィルターへの HTTP 要求を WebView が実行しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-154">Fires when the WebView is performing an HTTP request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span>
[<span data-ttu-id="3e441-155">WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="3e441-155">WebResourceResponseReceived</span></span>](#webresourceresponsereceived) | <span data-ttu-id="3e441-156">WebResourceResponseReceived イベントは、WebView が WebResource 要求に対する応答を受信して処理した後に発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-156">WebResourceResponseReceived event fires after the WebView has received and processed the response for a WebResource request.</span></span>
[<span data-ttu-id="3e441-157">WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="3e441-157">WindowCloseRequested</span></span>](#windowcloserequested) | <span data-ttu-id="3e441-158">ウィンドウを閉じるために、WebView 内のコンテンツが要求されたときに発生します。たとえば、close の後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-158">Fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span>
[<span data-ttu-id="3e441-159">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="3e441-159">AddHostObjectToScript</span></span>](#addhostobjecttoscript) | <span data-ttu-id="3e441-160">指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e441-160">Add the provided host object to script running in the WebView with the specified name.</span></span>
[<span data-ttu-id="3e441-161">AddScriptToExecuteOnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="3e441-161">AddScriptToExecuteOnDocumentCreatedAsync</span></span>](#addscripttoexecuteondocumentcreatedasync) | <span data-ttu-id="3e441-162">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e441-162">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="3e441-163">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="3e441-163">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="3e441-164">URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e441-164">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="3e441-165">Calldev| Protocolmethodasync</span><span class="sxs-lookup"><span data-stu-id="3e441-165">CallDevToolsProtocolMethodAsync</span></span>](#calldevtoolsprotocolmethodasync) | <span data-ttu-id="3e441-166">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3e441-166">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="3e441-167">CapturePreviewAsync</span><span class="sxs-lookup"><span data-stu-id="3e441-167">CapturePreviewAsync</span></span>](#capturepreviewasync) | <span data-ttu-id="3e441-168">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3e441-168">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="3e441-169">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="3e441-169">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="3e441-170">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e441-170">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="3e441-171">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="3e441-171">GetDevToolsProtocolEventReceiver</span></span>](#getdevtoolsprotocoleventreceiver) | <span data-ttu-id="3e441-172">DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。</span><span class="sxs-lookup"><span data-stu-id="3e441-172">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>
[<span data-ttu-id="3e441-173">GoBack</span><span class="sxs-lookup"><span data-stu-id="3e441-173">GoBack</span></span>](#goback) | <span data-ttu-id="3e441-174">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e441-174">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="3e441-175">GoForward</span><span class="sxs-lookup"><span data-stu-id="3e441-175">GoForward</span></span>](#goforward) | <span data-ttu-id="3e441-176">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e441-176">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="3e441-177">検索</span><span class="sxs-lookup"><span data-stu-id="3e441-177">Navigate</span></span>](#navigate) | <span data-ttu-id="3e441-178">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e441-178">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="3e441-179">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="3e441-179">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="3e441-180">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e441-180">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="3e441-181">Opendevツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3e441-181">OpenDevToolsWindow</span></span>](#opendevtoolswindow) | <span data-ttu-id="3e441-182">WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e441-182">Opens the DevTools window for the current document in the WebView.</span></span>
[<span data-ttu-id="3e441-183">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="3e441-183">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="3e441-184">指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="3e441-184">Post the specified webMessage to the top level document in this WebView.</span></span>
[<span data-ttu-id="3e441-185">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="3e441-185">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="3e441-186">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="3e441-186">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="3e441-187">再</span><span class="sxs-lookup"><span data-stu-id="3e441-187">Reload</span></span>](#reload) | <span data-ttu-id="3e441-188">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="3e441-188">Reload the current page.</span></span>
[<span data-ttu-id="3e441-189">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="3e441-189">RemoveHostObjectFromScript</span></span>](#removehostobjectfromscript) | <span data-ttu-id="3e441-190">名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="3e441-190">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>
[<span data-ttu-id="3e441-191">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="3e441-191">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="3e441-192">指定したスクリプト id を使用して、AddScriptToExecuteOnDocumentCreated で追加された対応する JavaScript を削除します。</span><span class="sxs-lookup"><span data-stu-id="3e441-192">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated with the specified script id.</span></span>
[<span data-ttu-id="3e441-193">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="3e441-193">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="3e441-194">以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="3e441-194">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>
[<span data-ttu-id="3e441-195">Stop</span><span class="sxs-lookup"><span data-stu-id="3e441-195">Stop</span></span>](#stop) | <span data-ttu-id="3e441-196">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="3e441-196">Stop all navigations and pending resource fetches.</span></span>

## <span data-ttu-id="3e441-197">Members</span><span class="sxs-lookup"><span data-stu-id="3e441-197">Members</span></span>

#### <span data-ttu-id="3e441-198">BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="3e441-198">BrowserProcessId</span></span> 

<span data-ttu-id="3e441-199">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="3e441-199">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="3e441-200">パブリック uint [ブラウザー processid](#browserprocessid)</span><span class="sxs-lookup"><span data-stu-id="3e441-200">public uint [BrowserProcessId](#browserprocessid)</span></span>

#### <span data-ttu-id="3e441-201">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="3e441-201">CanGoBack</span></span> 

<span data-ttu-id="3e441-202">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-202">Returns true if the webview can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="3e441-203">public bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="3e441-203">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="3e441-204">CanGoBack の値が変更されると、履歴変更イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-204">The HistoryChanged event will fire if CanGoBack changes value.</span></span>

#### <span data-ttu-id="3e441-205">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="3e441-205">CanGoForward</span></span> 

<span data-ttu-id="3e441-206">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-206">Returns true if the webview can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="3e441-207">public bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="3e441-207">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="3e441-208">CanGoForward の値が変更されると、履歴変更イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-208">The HistoryChanged event will fire if CanGoForward changes value.</span></span>

#### <span data-ttu-id="3e441-209">ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="3e441-209">ContainsFullScreenElement</span></span> 

<span data-ttu-id="3e441-210">WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3e441-210">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="3e441-211">パブリックブール型 [Fullscreenelement](#containsfullscreenelement)</span><span class="sxs-lookup"><span data-stu-id="3e441-211">public bool [ContainsFullScreenElement](#containsfullscreenelement)</span></span>

#### <span data-ttu-id="3e441-212">ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="3e441-212">ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="3e441-213">"の場合、要素のプロパティが変更されたときに通知します。</span><span class="sxs-lookup"><span data-stu-id="3e441-213">Notifies when the ContainsFullScreenElement property changes.</span></span>

> <span data-ttu-id="3e441-214">パブリックイベント EventHandler< オブジェクト > [Fullfullscreenelementchanged](#containsfullscreenelementchanged)</span><span class="sxs-lookup"><span data-stu-id="3e441-214">public event EventHandler< object > [ContainsFullScreenElementChanged](#containsfullscreenelementchanged)</span></span>

<span data-ttu-id="3e441-215">これは、WebView 内の HTML 要素が、WebView のサイズまたはフルスクリーンのままであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3e441-215">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="3e441-216">このイベントは、たとえば、ビデオ要素が全画面表示になっている要求の場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="3e441-216">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="3e441-217">次に、Fullfullscreenelementelementのリスナーが、応答で WebView のサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3e441-217">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

#### <span data-ttu-id="3e441-218">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="3e441-218">ContentLoading</span></span> 

<span data-ttu-id="3e441-219">ContentLoading は、コンテンツが読み込まれる前に発生します。 AddScriptToExecuteOnDocumentCreated ContentLoading によって追加されたスクリプトは、同じページナビゲーション (フラグメントナビゲーションや履歴の推移など) が発生した場合には発生しません。</span><span class="sxs-lookup"><span data-stu-id="3e441-219">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated ContentLoading will not fire if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span>

> <span data-ttu-id="3e441-220">パブリックイベントハンドラー< [CoreWebView2ContentLoadingEventArgs](microsoft-web-webview2-core-corewebview2contentloadingeventargs.md)  >  [contentloading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="3e441-220">public event EventHandler< [CoreWebView2ContentLoadingEventArgs](microsoft-web-webview2-core-corewebview2contentloadingeventargs.md) > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="3e441-221">これは、NavigationStarting イベントと SourceChanged イベントの後で、履歴の変更イベントと Navigationstarting イベントの前に発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-221">This follows the NavigationStarting and SourceChanged events and precedes the HistoryChanged and NavigationCompleted events.</span></span>

#### <span data-ttu-id="3e441-222">DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="3e441-222">DocumentTitle</span></span> 

<span data-ttu-id="3e441-223">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="3e441-223">The title for the current top level document.</span></span>

> <span data-ttu-id="3e441-224">パブリック文字列 [ドキュメントタイトル](#documenttitle)</span><span class="sxs-lookup"><span data-stu-id="3e441-224">public string [DocumentTitle](#documenttitle)</span></span>

<span data-ttu-id="3e441-225">ドキュメントに明示的なタイトルが含まれていない場合、または空の場合は、ドキュメントの URI と一致しないかもしれない既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-225">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

#### <span data-ttu-id="3e441-226">ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="3e441-226">DocumentTitleChanged</span></span> 

<span data-ttu-id="3e441-227">イベントは、WebView の DocumentTitle プロパティが変更されたとき、または NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-227">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

> <span data-ttu-id="3e441-228">パブリックイベントイベントハンドラー< オブジェクト >[ドキュメント](#documenttitlechanged)の概要</span><span class="sxs-lookup"><span data-stu-id="3e441-228">public event EventHandler< object > [DocumentTitleChanged](#documenttitlechanged)</span></span>

#### <span data-ttu-id="3e441-229">FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="3e441-229">FrameNavigationCompleted</span></span> 

<span data-ttu-id="3e441-230">FrameNavigationCompleted イベントが発生するのは、子フレームが完全に読み込まれた (読み込みが開始された) か、エラーが発生して読み込みを停止したときです。</span><span class="sxs-lookup"><span data-stu-id="3e441-230">FrameNavigationCompleted event fires when a child frame has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

> <span data-ttu-id="3e441-231">パブリックイベント EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [FrameNavigationCompleted](#framenavigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="3e441-231">public event EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md) > [FrameNavigationCompleted](#framenavigationcompleted)</span></span>

#### <span data-ttu-id="3e441-232">FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="3e441-232">FrameNavigationStarting</span></span> 

<span data-ttu-id="3e441-233">FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-233">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span>

> <span data-ttu-id="3e441-234">パブリックイベント EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [FrameNavigationStarting](#framenavigationstarting)</span><span class="sxs-lookup"><span data-stu-id="3e441-234">public event EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md) > [FrameNavigationStarting](#framenavigationstarting)</span></span>

<span data-ttu-id="3e441-235">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-235">This will fire for redirects as well.</span></span>

#### <span data-ttu-id="3e441-236">変更履歴</span><span class="sxs-lookup"><span data-stu-id="3e441-236">HistoryChanged</span></span> 

<span data-ttu-id="3e441-237">履歴は、トップレベルのドキュメントのナビゲーション履歴の変更をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="3e441-237">HistoryChange listen to the change of navigation history for the top level document.</span></span>

> <span data-ttu-id="3e441-238">パブリックイベント EventHandler< オブジェクト > [履歴の変更](#historychanged)</span><span class="sxs-lookup"><span data-stu-id="3e441-238">public event EventHandler< object > [HistoryChanged](#historychanged)</span></span>

<span data-ttu-id="3e441-239">履歴の変更を使って、CanGoBack/CanGoForward の値が変更されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e441-239">Use HistoryChange to check if CanGoBack/CanGoForward value has changed.</span></span> <span data-ttu-id="3e441-240">GoBack/GoForward を使用する場合にも変更履歴が発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-240">HistoryChanged also fires for using GoBack/GoForward.</span></span> <span data-ttu-id="3e441-241">変更履歴は、SourceChanged と ContentLoading の後に発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-241">HistoryChanged fires after SourceChanged and ContentLoading.</span></span> <span data-ttu-id="3e441-242">履歴変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e441-242">Add an event handler for the HistoryChanged event.</span></span>

#### <span data-ttu-id="3e441-243">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="3e441-243">NavigationCompleted</span></span> 

<span data-ttu-id="3e441-244">NavigationCompleted イベントは、WebView が完全に読み込まれたとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-244">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

> <span data-ttu-id="3e441-245">パブリックイベント EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [navigationcompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="3e441-245">public event EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md) > [NavigationCompleted](#navigationcompleted)</span></span>

#### <span data-ttu-id="3e441-246">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="3e441-246">NavigationStarting</span></span> 

<span data-ttu-id="3e441-247">NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-247">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span>

> <span data-ttu-id="3e441-248">パブリックイベント EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [navigationstarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="3e441-248">public event EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md) > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="3e441-249">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-249">This will fire for redirects as well.</span></span>

#### <span data-ttu-id="3e441-250">NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="3e441-250">NewWindowRequested</span></span> 

<span data-ttu-id="3e441-251">ウィンドウを開くなど、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-251">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span>

> <span data-ttu-id="3e441-252">パブリックイベント EventHandler< [CoreWebView2NewWindowRequestedEventArgs](microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md)  >  [newwindowrequested](#newwindowrequested)</span><span class="sxs-lookup"><span data-stu-id="3e441-252">public event EventHandler< [CoreWebView2NewWindowRequestedEventArgs](microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md) > [NewWindowRequested](#newwindowrequested)</span></span>

<span data-ttu-id="3e441-253">アプリは、開かれたウィンドウと見なされるターゲット webview を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-253">The app can pass a target webview that will be considered the opened window.</span></span>

#### <span data-ttu-id="3e441-254">PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="3e441-254">PermissionRequested</span></span> 

<span data-ttu-id="3e441-255">WebView のコンテンツが権限のある一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-255">Fires when content in a WebView requests permission to access some privileged resources.</span></span>

> <span data-ttu-id="3e441-256">パブリックイベント EventHandler< [CoreWebView2PermissionRequestedEventArgs](microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md)  >  [permissionrequested](#permissionrequested)</span><span class="sxs-lookup"><span data-stu-id="3e441-256">public event EventHandler< [CoreWebView2PermissionRequestedEventArgs](microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md) > [PermissionRequested](#permissionrequested)</span></span>

#### <span data-ttu-id="3e441-257">ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="3e441-257">ProcessFailed</span></span> 

<span data-ttu-id="3e441-258">WebView プロセスが予期せず終了した場合、または応答不能になったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-258">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>

> <span data-ttu-id="3e441-259">パブリックイベント EventHandler< [CoreWebView2ProcessFailedEventArgs](microsoft-web-webview2-core-corewebview2processfailedeventargs.md)  >  [processfailed](#processfailed)</span><span class="sxs-lookup"><span data-stu-id="3e441-259">public event EventHandler< [CoreWebView2ProcessFailedEventArgs](microsoft-web-webview2-core-corewebview2processfailedeventargs.md) > [ProcessFailed](#processfailed)</span></span>

#### <span data-ttu-id="3e441-260">Scriptて開く</span><span class="sxs-lookup"><span data-stu-id="3e441-260">ScriptDialogOpening</span></span> 

<span data-ttu-id="3e441-261">イベントは、webview の JavaScript ダイアログ (警告、確認、またはプロンプト) が表示されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-261">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span>

> <span data-ttu-id="3e441-262">パブリックイベント EventHandler< [CoreWebView2ScriptDialogOpeningEventArgs](microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md)  >  [script を開く](#scriptdialogopening)</span><span class="sxs-lookup"><span data-stu-id="3e441-262">public event EventHandler< [CoreWebView2ScriptDialogOpeningEventArgs](microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md) > [ScriptDialogOpening](#scriptdialogopening)</span></span>

<span data-ttu-id="3e441-263">このイベントは、CoreWebView2Settings Defaultscript Senabled プロパティが false に設定されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-263">This event only fires if the CoreWebView2Settings.AreDefaultScriptDialogsEnabled property is set to false.</span></span> <span data-ttu-id="3e441-264">Scriptdialogs 左中イベントを使うと、ダイアログを非表示にしたり、既定のダイアログをカスタムダイアログに置き換えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-264">The ScriptDialogOpening event can be used to suppress dialogs or replace default dialogs with custom dialogs.</span></span>

#### <span data-ttu-id="3e441-265">設定</span><span class="sxs-lookup"><span data-stu-id="3e441-265">Settings</span></span> 

<span data-ttu-id="3e441-266">CoreWebView2Settings オブジェクトには、実行に関するさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e441-266">The CoreWebView2Settings object contains various modifiable settings for the running</span></span>

> <span data-ttu-id="3e441-267">パブリック [CoreWebView2Settings](microsoft-web-webview2-core-corewebview2settings.md)の [設定](#settings)</span><span class="sxs-lookup"><span data-stu-id="3e441-267">public [CoreWebView2Settings](microsoft-web-webview2-core-corewebview2settings.md) [Settings](#settings)</span></span>

#### <span data-ttu-id="3e441-268">Source</span><span class="sxs-lookup"><span data-stu-id="3e441-268">Source</span></span> 

<span data-ttu-id="3e441-269">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="3e441-269">The URI of the current top level document.</span></span>

> <span data-ttu-id="3e441-270">パブリック文字列 [ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="3e441-270">public string [Source](#source)</span></span>

<span data-ttu-id="3e441-271">この値は、別のサイトやフラグメントナビゲーションへの移動などの場合に、SourceChanged イベント発生の一部として変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e441-271">This value potentially changes as a part of the SourceChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="3e441-272">ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションにも同じように表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-272">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

#### <span data-ttu-id="3e441-273">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="3e441-273">SourceChanged</span></span> 

<span data-ttu-id="3e441-274">SourceChanged Source プロパティが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-274">SourceChanged fires when the Source property changes.</span></span>

> <span data-ttu-id="3e441-275">パブリックイベント EventHandler< [CoreWebView2SourceChangedEventArgs](microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md)  >  [sourcechanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="3e441-275">public event EventHandler< [CoreWebView2SourceChangedEventArgs](microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md) > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="3e441-276">SourceChanged のサイトまたはフラグメントナビゲーションに移動する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-276">SourceChanged fires for navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="3e441-277">ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションについては、このような操作は発生しません。</span><span class="sxs-lookup"><span data-stu-id="3e441-277">It will not fires for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span> <span data-ttu-id="3e441-278">SourceChanged ドキュメントへのナビゲーションのためにコンテンツを読み込む前に、SourceChanged が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-278">SourceChanged fires before ContentLoading for navigation to a new document.</span></span> <span data-ttu-id="3e441-279">SourceChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e441-279">Add an event handler for the SourceChanged event.</span></span>

#### <span data-ttu-id="3e441-280">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="3e441-280">WebMessageReceived</span></span> 

<span data-ttu-id="3e441-281">このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。</span><span class="sxs-lookup"><span data-stu-id="3e441-281">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="3e441-282">パブリックイベント EventHandler< [CoreWebView2WebMessageReceivedEventArgs](microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md)  >  [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="3e441-282">public event EventHandler< [CoreWebView2WebMessageReceivedEventArgs](microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md) > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="3e441-283">PostMessage 関数は、 `void postMessage(object)` JSON 変換でサポートされているオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3e441-283">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span> <span data-ttu-id="3e441-284">PostMessage が呼び出されると、postMessage のオブジェクトパラメーターを JSON 文字列に変換して、CoreWebView2WebMessageReceivedEventHandler セットが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-284">When postMessage is called, the CoreWebView2WebMessageReceivedEventHandler set will be invoked with the postMessage's object parameter converted to a JSON string.</span></span>

#### <span data-ttu-id="3e441-285">WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="3e441-285">WebResourceRequested</span></span> 

<span data-ttu-id="3e441-286">AddWebResourceRequestedFilter で追加された一致する URL とリソースコンテキストフィルターへの HTTP 要求を WebView が実行しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-286">Fires when the WebView is performing an HTTP request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span>

> <span data-ttu-id="3e441-287">パブリックイベント EventHandler< [CoreWebView2WebResourceRequestedEventArgs](microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md)  >  [WebResourceRequested](#webresourcerequested)</span><span class="sxs-lookup"><span data-stu-id="3e441-287">public event EventHandler< [CoreWebView2WebResourceRequestedEventArgs](microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md) > [WebResourceRequested](#webresourcerequested)</span></span>

<span data-ttu-id="3e441-288">イベントを発生させるには、少なくとも1つのフィルターを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e441-288">At least one filter must be added for the event to fire.</span></span>

#### <span data-ttu-id="3e441-289">WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="3e441-289">WebResourceResponseReceived</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="3e441-290">WebResourceResponseReceived イベントは、WebView が WebResource 要求に対する応答を受信して処理した後に発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-290">WebResourceResponseReceived event fires after the WebView has received and processed the response for a WebResource request.</span></span>

> <span data-ttu-id="3e441-291">パブリックイベント EventHandler< [CoreWebView2WebResourceResponseReceivedEventArgs](microsoft-web-webview2-core-corewebview2webresourceresponsereceivedeventargs.md)  >  [WebResourceResponseReceived](#webresourceresponsereceived)</span><span class="sxs-lookup"><span data-stu-id="3e441-291">public event EventHandler< [CoreWebView2WebResourceResponseReceivedEventArgs](microsoft-web-webview2-core-corewebview2webresourceresponsereceivedeventargs.md) > [WebResourceResponseReceived](#webresourceresponsereceived)</span></span>

<span data-ttu-id="3e441-292">イベント引数には、WebResourceResponse によって送信された WebResourceRequest が含まれています。これには、認証ヘッダーなど、関連付けられた WebResourceRequested イベントの一部として含まれていないネットワークスタックによって追加されたヘッダーも含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e441-292">The event args include the WebResourceRequest as sent by the wire and WebResourceResponse received, including any additional headers added by the network stack that were not be included as part of the associated WebResourceRequested event, such as Authentication headers.</span></span>

#### <span data-ttu-id="3e441-293">WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="3e441-293">WindowCloseRequested</span></span> 

<span data-ttu-id="3e441-294">ウィンドウを閉じるために、WebView 内のコンテンツが要求されたときに発生します。たとえば、close の後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-294">Fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span>

> <span data-ttu-id="3e441-295">public イベント EventHandler< object > [WindowCloseRequested](#windowcloserequested)</span><span class="sxs-lookup"><span data-stu-id="3e441-295">public event EventHandler< object > [WindowCloseRequested](#windowcloserequested)</span></span>

<span data-ttu-id="3e441-296">アプリが適切である場合は、アプリで WebView と関連するアプリのウィンドウを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e441-296">The app should close the WebView and related app window if that makes sense to the app.</span></span>

#### <span data-ttu-id="3e441-297">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="3e441-297">AddHostObjectToScript</span></span> 

<span data-ttu-id="3e441-298">指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e441-298">Add the provided host object to script running in the WebView with the specified name.</span></span>

> <span data-ttu-id="3e441-299">public void [Addhostobjecttoscript](#addhostobjecttoscript)(文字列名、オブジェクト rawobject)</span><span class="sxs-lookup"><span data-stu-id="3e441-299">public void [AddHostObjectToScript](#addhostobjecttoscript)(string name, object rawObject)</span></span>

<span data-ttu-id="3e441-300">ホストオブジェクトは、でホストオブジェクトプロキシとして公開され `window.chrome.webview.hostObjects.{name}` ます。</span><span class="sxs-lookup"><span data-stu-id="3e441-300">Host objects are exposed as host object proxies via `window.chrome.webview.hostObjects.{name}`.</span></span> <span data-ttu-id="3e441-301">ホストオブジェクトプロキシは保証され、ホストオブジェクトを表すオブジェクトに解決されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-301">Host object proxies are promises and will resolve to an object representing the host object.</span></span> <span data-ttu-id="3e441-302">WebView の JavaScript コードは、appObject に次の方法でアクセスして、appObject の属性とメソッドにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3e441-302">JavaScript code in the WebView will be able to access appObject as following and then access attributes and methods of appObject:</span></span> 
```
let app_object = await window.chrome.webview.hostObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```
 <span data-ttu-id="3e441-303">単純型、IDispatch、配列はサポートされていますが、ジェネリック IUnknown、VT_DECIMAL、または VT_RECORD variant はサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e441-303">Note that while simple types, IDispatch and array are supported, generic IUnknown, VT_DECIMAL, or VT_RECORD variant is not supported.</span></span> <span data-ttu-id="3e441-304">コールバック関数などのリモート JavaScript オブジェクトは、IDispatch を実装するオブジェクトと共に VT_DISPATCH VARIANT として表されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-304">Remote JavaScript objects like callback functions are represented as an VT_DISPATCH VARIANT with the object implementing IDispatch.</span></span> <span data-ttu-id="3e441-305">JavaScript のコールバックメソッドは、DISPID の DISPID_VALUE を使って呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-305">The JavaScript callback method may be invoked using DISPID_VALUE for the DISPID.</span></span> <span data-ttu-id="3e441-306">入れ子になった配列は、最大3レベルまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3e441-306">Nested arrays are supported up to a depth of 3.</span></span> <span data-ttu-id="3e441-307">参照型での配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3e441-307">Arrays of by reference types are not supported.</span></span> <span data-ttu-id="3e441-308">VT_EMPTY と VT_NULL は JavaScript に NULL としてマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="3e441-308">VT_EMPTY and VT_NULL are mapped into JavaScript as null.</span></span> <span data-ttu-id="3e441-309">JavaScript は null で、undefined は VT_EMPTY にマップされます。</span><span class="sxs-lookup"><span data-stu-id="3e441-309">In JavaScript null and undefined are mapped to VT_EMPTY.</span></span>

<span data-ttu-id="3e441-310">さらに、すべてのホストオブジェクトがとして公開され `window.chrome.webview.hostObjects.sync.{name}` ます。</span><span class="sxs-lookup"><span data-stu-id="3e441-310">Additionally, all host objects are exposed as `window.chrome.webview.hostObjects.sync.{name}`.</span></span> <span data-ttu-id="3e441-311">ここでは、ホストオブジェクトが同期ホストオブジェクトプロキシとして公開されています。</span><span class="sxs-lookup"><span data-stu-id="3e441-311">Here the host objects are exposed as synchronous host object proxies.</span></span> <span data-ttu-id="3e441-312">これらは、ホストコードが実行されるためのクロスプロセスとの通信を待機している、実行中のスクリプトの実行を待機していて、機能やプロパティへのアクセスを同期することはできません。</span><span class="sxs-lookup"><span data-stu-id="3e441-312">These are not promises and calls to functions or property access synchronously block running script waiting to communicate cross process for the host code to run.</span></span> <span data-ttu-id="3e441-313">これにより、信頼性の問題が発生する可能性があり、上記で説明した promise ベースの非同期 API を使うことをお勧めし `window.chrome.webview.hostObjects.{name}` ます。</span><span class="sxs-lookup"><span data-stu-id="3e441-313">Accordingly this can result in reliability issues and it is recommended that you use the promise based asynchronous `window.chrome.webview.hostObjects.{name}` API described above.</span></span>

<span data-ttu-id="3e441-314">同期ホストオブジェクトプロキシと非同期ホストオブジェクトプロキシは、どちらも同じホストオブジェクトをプロキシすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-314">Synchronous host object proxies and asynchronous host object proxies can both proxy the same host object.</span></span> <span data-ttu-id="3e441-315">1つのプロキシによって加えられたリモートの変更は、他のプロキシと同期か非同期かにかかわらず、同じホストオブジェクトの他のプロキシにも反映されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-315">Remote changes made by one proxy will be reflected in any other proxy of that same host object whether the other proxies and synchronous or asynchronous.</span></span>

<span data-ttu-id="3e441-316">JavaScript はネイティブコードへの同期呼び出しでブロックされますが、ネイティブコードは JavaScript にコールバックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e441-316">While JavaScript is blocked on a synchronous call to native code, that native code is unable to call back to JavaScript.</span></span> <span data-ttu-id="3e441-317">これを実行しようとすると、HRESULT_FROM_WIN32 (ERROR_POSSIBLE_DEADLOCK) で失敗します。</span><span class="sxs-lookup"><span data-stu-id="3e441-317">Attempts to do so will fail with HRESULT_FROM_WIN32(ERROR_POSSIBLE_DEADLOCK).</span></span>

<span data-ttu-id="3e441-318">ホストオブジェクトプロキシは、すべてのプロパティ get、プロパティセット、メソッド呼び出しを受け取る JavaScript プロキシオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3e441-318">Host object proxies are JavaScript Proxy objects that intercept all property get, property set, and method invocations.</span></span> <span data-ttu-id="3e441-319">関数またはオブジェクトプロトタイプの一部であるプロパティまたはメソッドはローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-319">Properties or methods that are a part of the Function or Object prototype are run locally.</span></span> <span data-ttu-id="3e441-320">さらに、配列内のすべてのプロパティまたはメソッド `chrome.webview.hostObjects.options.forceLocalProperties` もローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-320">Additionally any property or method in the array `chrome.webview.hostObjects.options.forceLocalProperties` will also be run locally.</span></span> <span data-ttu-id="3e441-321">これは既定で、JavaScript のような、というようなオプションのメソッドが含まれてい `toJSON` `Symbol.toPrimitive` ます。</span><span class="sxs-lookup"><span data-stu-id="3e441-321">This defaults to including optional methods that have meaning in JavaScript like `toJSON` and `Symbol.toPrimitive`.</span></span> <span data-ttu-id="3e441-322">必要に応じて、この配列に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-322">You can add more to this array as required.</span></span>

<span data-ttu-id="3e441-323">最善の手段と `chrome.webview.hostObjects.cleanupSome` して、ガベージコレクションのホストオブジェクトプロキシを収集する方法があります。</span><span class="sxs-lookup"><span data-stu-id="3e441-323">There's a method `chrome.webview.hostObjects.cleanupSome` that will best effort garbage collect host object proxies.</span></span>

<span data-ttu-id="3e441-324">ホストオブジェクトプロキシには、ローカルで実行される次のメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="3e441-324">Host object proxies additionally have the following methods which run locally:</span></span>

* <span data-ttu-id="3e441-325">applyHostFunction、getHostProperty、setHostProperty: ホストオブジェクトでメソッドの呼び出し、プロパティの取得、プロパティの設定を実行します。</span><span class="sxs-lookup"><span data-stu-id="3e441-325">applyHostFunction, getHostProperty, setHostProperty: Perform a method invocation, property get, or property set on the host object.</span></span> <span data-ttu-id="3e441-326">これらのメソッドを使うと、競合するローカルメソッドまたはプロパティがある場合に、メソッドまたはプロパティを明示的に強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="3e441-326">You can use these to explicitly force a method or property to run remotely if there is a conflicting local method or property.</span></span> <span data-ttu-id="3e441-327">たとえば、 `proxy.toString()` はプロキシオブジェクトに対してローカル toString メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e441-327">For instance, `proxy.toString()` will run the local toString method on the proxy object.</span></span> <span data-ttu-id="3e441-328">ただし `proxy.applyHostFunction('toString')` `toString` 、代わりに host プロキシオブジェクトで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-328">But `proxy.applyHostFunction('toString')` runs `toString` on the host proxied object instead.</span></span>

* <span data-ttu-id="3e441-329">getLocalProperty、setLocalProperty: プロパティ get、またはローカルにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e441-329">getLocalProperty, setLocalProperty: Perform property get, or property set locally.</span></span> <span data-ttu-id="3e441-330">これらのメソッドを使うと、ホストオブジェクトプロキシ自体でプロパティを取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-330">You can use these methods to force getting or setting a property on the host object proxy itself rather than on the host object it represents.</span></span> <span data-ttu-id="3e441-331">たとえば、 `proxy.unknownProperty` は、host プロキシオブジェクトから名前が付けられたプロパティを取得し `unknownProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="3e441-331">For instance, `proxy.unknownProperty` will get the property named `unknownProperty` from the host proxied object.</span></span> <span data-ttu-id="3e441-332">ただし、この `proxy.getLocalProperty('unknownProperty')` プロパティの値は `unknownProperty` プロキシオブジェクト自体で取得されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-332">But `proxy.getLocalProperty('unknownProperty')` will get the value of the property `unknownProperty` on the proxy object itself.</span></span>

* <span data-ttu-id="3e441-333">同期: 非同期ホストオブジェクトプロキシは、同じホストオブジェクトの同期ホストオブジェクトプロキシの promise を返す同期メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="3e441-333">sync: Asynchronous host object proxies expose a sync method which returns a promise for a synchronous host object proxy for the same host object.</span></span> <span data-ttu-id="3e441-334">たとえば、 `chrome.webview.hostObjects.sample.methodCall()` 非同期ホストオブジェクトプロキシを返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-334">For example, `chrome.webview.hostObjects.sample.methodCall()` returns an asynchronous host object proxy.</span></span> <span data-ttu-id="3e441-335">代わりに、メソッドを使用して `sync` 同期ホストオブジェクトプロキシを取得できます。</span><span class="sxs-lookup"><span data-stu-id="3e441-335">You can use the `sync` method to obtain a synchronous host object proxy instead:</span></span> `const syncProxy = await chrome.webview.hostObjects.sample.methodCall().sync()`

* <span data-ttu-id="3e441-336">非同期: 同期ホストオブジェクトプロキシは、同じホストオブジェクトの非同期ホストオブジェクトプロキシをブロックして返す async メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="3e441-336">async: Synchronous host object proxies expose an async method which blocks and returns an asynchronous host object proxy for the same host object.</span></span> <span data-ttu-id="3e441-337">たとえば、 `chrome.webview.hostObjects.sync.sample.methodCall()` 同期ホストオブジェクトプロキシを返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-337">For example, `chrome.webview.hostObjects.sync.sample.methodCall()` returns a synchronous host object proxy.</span></span> <span data-ttu-id="3e441-338">このブロックに対してメソッドを呼び出す `async` と、同じホストオブジェクトの非同期ホストオブジェクトプロキシが返されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-338">Calling the `async` method on this blocks and then returns an asynchronous host object proxy for the same host object:</span></span> `const asyncProxy = chrome.webview.hostObjects.sync.sample.methodCall().async()`

* <span data-ttu-id="3e441-339">次に、非同期ホストオブジェクトプロキシには then メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="3e441-339">then: Asynchronous host object proxies have a then method.</span></span> <span data-ttu-id="3e441-340">これにより、awaitable を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-340">This allows them to be awaitable.</span></span> `then` <span data-ttu-id="3e441-341">は、host オブジェクトの表現によって解決される promise を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-341">will return a promise that resolves with a representation of the host object.</span></span> <span data-ttu-id="3e441-342">プロキシが JavaScript リテラルを表す場合は、そのリテラルのコピーがローカルに返されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-342">If the proxy represents a JavaScript literal then a copy of that is returned locally.</span></span> <span data-ttu-id="3e441-343">プロキシが関数を表す場合は、awaitable 以外のプロキシが返されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-343">If the proxy represents a function then a non-awaitable proxy is returned.</span></span> <span data-ttu-id="3e441-344">プロキシがリテラルプロパティと関数プロパティが混在した JavaScript オブジェクトを表している場合、オブジェクトのコピーが、一部のプロパティをホストオブジェクトプロキシとして返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-344">If the proxy represents a JavaScript object with a mix of literal properties and function properties, then the a copy of the object is returned with some properties as host object proxies.</span></span>

<span data-ttu-id="3e441-345">その他のすべてのプロパティとメソッドの呼び出し (上記のリモートオブジェクトプロキシメソッド、forceLocalProperties リスト、関数およびオブジェクトプロトタイプのプロパティ以外) は、リモートで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-345">All other property and method invocations (other than the above Remote object proxy methods, forceLocalProperties list, and properties on Function and Object prototypes) are run remotely.</span></span> <span data-ttu-id="3e441-346">非同期ホストオブジェクトプロキシは、メソッドのリモート呼び出しまたはプロパティの取得の非同期完了を表す promise を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-346">Asynchronous host object proxies return a promise representing asynchronous completion of remotely invoking the method, or getting the property.</span></span> <span data-ttu-id="3e441-347">この保証は、リモート操作が完了した後に解決され、その約束が、演算の結果値に解決されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-347">The promise resolves after the remote operations complete and the promises resolve to the resulting value of the operation.</span></span> <span data-ttu-id="3e441-348">同期ホストオブジェクトプロキシは、同じように動作しますが、JavaScript の実行をブロックし、リモート操作が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="3e441-348">Synchronous host object proxies work similarly but block JavaScript execution and wait for the remote operation to complete.</span></span>

<span data-ttu-id="3e441-349">非同期ホストオブジェクトプロキシのプロパティの設定は、若干異なります。</span><span class="sxs-lookup"><span data-stu-id="3e441-349">Setting a property on an asynchronous host object proxy works slightly differently.</span></span> <span data-ttu-id="3e441-350">Set はすぐに戻り値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-350">The set returns immediately and the return value is the value that will be set.</span></span> <span data-ttu-id="3e441-351">これは JavaScript プロキシオブジェクトの要件です。</span><span class="sxs-lookup"><span data-stu-id="3e441-351">This is a requirement of the JavaScript Proxy object.</span></span> <span data-ttu-id="3e441-352">プロパティセットが完了するのを非同期的に待つ必要がある場合は、上記のように、setHostProperty メソッドを使って、promise を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-352">If you need to asynchronously wait for the property set to complete, use the setHostProperty method which returns a promise as described above.</span></span> <span data-ttu-id="3e441-353">同期オブジェクトプロパティセットプロパティは、プロパティが設定されるまで同期的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3e441-353">Synchronous object property set property synchronously blocks until the property is set.</span></span>

#### <span data-ttu-id="3e441-354">AddScriptToExecuteOnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="3e441-354">AddScriptToExecuteOnDocumentCreatedAsync</span></span> 

<span data-ttu-id="3e441-355">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e441-355">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="3e441-356">パブリック async タスク< 文字列 > [AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync)(文字列 javaScript)</span><span class="sxs-lookup"><span data-stu-id="3e441-356">public async Task< string > [AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync)(string javaScript)</span></span>

##### <span data-ttu-id="3e441-357">返し</span><span class="sxs-lookup"><span data-stu-id="3e441-357">Returns</span></span>
<span data-ttu-id="3e441-358">[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)を呼び出したときに渡すことができるスクリプト id を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-358">Returns a script id that may be passed when calling [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated).</span></span> 

<span data-ttu-id="3e441-359">挿入されたスクリプトは、RemoveScriptToExecuteOnDocumentCreated で削除されるまで、将来のすべての上位レベルのドキュメントと子フレームのナビゲーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-359">The injected script will apply to all future top level document and child frame navigations until removed with RemoveScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="3e441-360">これは非同期的に適用されるため、今後のナビゲーションでスクリプトを実行する準備ができていることを確認する前に、完了ハンドラーが実行されるまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e441-360">This is applied asynchronously and you must wait for the completion handler to run before you can be sure that the script is ready to execute on future navigations.</span></span>

<span data-ttu-id="3e441-361">[サンドボックス](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)のプロパティまたは[コンテンツセキュリティポリシーの HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)によって、HTML ドキュメントに何らかのサンドボックスが含まれている場合は、このスクリプトの実行に影響します。</span><span class="sxs-lookup"><span data-stu-id="3e441-361">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="3e441-362">たとえば、' allow als ' キーワードが設定されていない場合、関数への呼び出し `alert` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-362">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

#### <span data-ttu-id="3e441-363">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="3e441-363">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="3e441-364">URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e441-364">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="3e441-365">パブリック void [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(文字列 Uri、CoreWebView2WebResourceContext resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="3e441-365">public void [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(string uri, CoreWebView2WebResourceContext ResourceContext)</span></span>

<span data-ttu-id="3e441-366">URI パラメーターは、ワイルドカード文字列 (0 以上、"?": 完全に1つ) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-366">URI parameter can be a wildcard string ('': zero or more, '?': exactly one).</span></span> <span data-ttu-id="3e441-367">nullptr は、L "" と同じです。</span><span class="sxs-lookup"><span data-stu-id="3e441-367">nullptr is equivalent to L"".</span></span> <span data-ttu-id="3e441-368">リソースコンテキストフィルターの説明については、「CoreWebView2WebResourceContext enum」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e441-368">See CoreWebView2WebResourceContext enum for description of resource context filters.</span></span>

#### <span data-ttu-id="3e441-369">Calldev| Protocolmethodasync</span><span class="sxs-lookup"><span data-stu-id="3e441-369">CallDevToolsProtocolMethodAsync</span></span> 

<span data-ttu-id="3e441-370">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3e441-370">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="3e441-371">パブリック async タスク< 文字列 > [CalldevparametersAsJson Protocolmethodasync](#calldevtoolsprotocolmethodasync)(文字列 methodName, string)</span><span class="sxs-lookup"><span data-stu-id="3e441-371">public async Task< string > [CallDevToolsProtocolMethodAsync](#calldevtoolsprotocolmethodasync)(string methodName, string parametersAsJson)</span></span>

##### <span data-ttu-id="3e441-372">返し</span><span class="sxs-lookup"><span data-stu-id="3e441-372">Returns</span></span>
<span data-ttu-id="3e441-373">メソッドの戻りオブジェクトを表す JSON 文字列。</span><span class="sxs-lookup"><span data-stu-id="3e441-373">A JSON string that represents the method's return object.</span></span> 

<span data-ttu-id="3e441-374">使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e441-374">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="3e441-375">MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="3e441-375">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="3e441-376">ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。</span><span class="sxs-lookup"><span data-stu-id="3e441-376">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="3e441-377">メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-377">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="3e441-378">Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-378">Invoke will be called with the method's return object as a JSON string.</span></span>

#### <span data-ttu-id="3e441-379">CapturePreviewAsync</span><span class="sxs-lookup"><span data-stu-id="3e441-379">CapturePreviewAsync</span></span> 

<span data-ttu-id="3e441-380">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3e441-380">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="3e441-381">パブリック async タスク [CapturePreviewAsync](#capturepreviewasync)(CoreWebView2CapturePreviewImageFormat imageformat、ストリーム画像 estream)</span><span class="sxs-lookup"><span data-stu-id="3e441-381">public async Task [CapturePreviewAsync](#capturepreviewasync)(CoreWebView2CapturePreviewImageFormat imageFormat, Stream imageStream)</span></span>

<span data-ttu-id="3e441-382">ImageFormat パラメーターを使用して、画像の形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e441-382">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="3e441-383">結果のイメージバイナリデータは、指定された imageStream パラメーターに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3e441-383">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="3e441-384">CapturePreview がストリームへの書き込みを終了すると、指定された handler パラメーターの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-384">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

#### <span data-ttu-id="3e441-385">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="3e441-385">ExecuteScriptAsync</span></span> 

<span data-ttu-id="3e441-386">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e441-386">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="3e441-387">パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列 javaScript)</span><span class="sxs-lookup"><span data-stu-id="3e441-387">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

##### <span data-ttu-id="3e441-388">返し</span><span class="sxs-lookup"><span data-stu-id="3e441-388">Returns</span></span>
<span data-ttu-id="3e441-389">指定された JavaScript を実行した結果を表す JSON エンコードされた文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-389">Returns a JSON encoded string that represents the result of running the provided JavaScript.</span></span> 

<span data-ttu-id="3e441-390">このメソッドは、指定された JavaScript を非同期的に実行し、指定された JavaScript の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-390">This method runs the provided JavaScript asynchronously and will return the result of the provided JavaScript.</span></span> <span data-ttu-id="3e441-391">提供された JavaScript の結果が `undefined` 、参照循環を含んでいる場合、または JSON にエンコードできない場合は、文字列 ' null ' が返されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-391">If the result of the provided JavaScript is `undefined`, contains a reference cycle, or otherwise cannot be encoded into JSON, the string 'null' is returned.</span></span> <span data-ttu-id="3e441-392">指定した JavaScript で呼び出される関数に明示的な戻り値がない場合 `undefined` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-392">If a called function in the provided JavaScript has no explicit return value, `undefined` is returned.</span></span> <span data-ttu-id="3e441-393">指定した JavaScript が処理されない例外をスローすると、' null ' が返されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-393">If the provided JavaScript throws an unhandled exception, 'null' is returned.</span></span> <span data-ttu-id="3e441-394">NavigationStarting イベントの後にこのメソッドが呼び出されると、指定された JavaScript は、読み込み時に新しいドキュメントで実行されます。これは、ContentLoading がトリガーされたときと同じです。</span><span class="sxs-lookup"><span data-stu-id="3e441-394">If this method is called after a NavigationStarting event, the provided JavaScript is run on the new document when it loads, around the same time that ContentLoading is triggered.</span></span> <span data-ttu-id="3e441-395">実行可能なのは IsScriptEnabled がに設定されている場合でも動作 `FALSE` します。</span><span class="sxs-lookup"><span data-stu-id="3e441-395">ExecuteScriptAsync will work even if IsScriptEnabled is set to `FALSE`.</span></span>

#### <span data-ttu-id="3e441-396">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="3e441-396">GetDevToolsProtocolEventReceiver</span></span> 

<span data-ttu-id="3e441-397">DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。</span><span class="sxs-lookup"><span data-stu-id="3e441-397">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>

> <span data-ttu-id="3e441-398">パブリック CoreWebView2DevToolsProtocolEventReceiver [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(文字列 eventName)</span><span class="sxs-lookup"><span data-stu-id="3e441-398">public CoreWebView2DevToolsProtocolEventReceiver [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(string eventName)</span></span>

<span data-ttu-id="3e441-399">使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e441-399">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="3e441-400">MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="3e441-400">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="3e441-401">ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。</span><span class="sxs-lookup"><span data-stu-id="3e441-401">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="3e441-402">メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-402">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="3e441-403">Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-403">Invoke will be called with the method's return object as a JSON string.</span></span>

#### <span data-ttu-id="3e441-404">GoBack</span><span class="sxs-lookup"><span data-stu-id="3e441-404">GoBack</span></span> 

<span data-ttu-id="3e441-405">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e441-405">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="3e441-406">パブリック void [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="3e441-406">public void [GoBack](#goback)()</span></span>

#### <span data-ttu-id="3e441-407">GoForward</span><span class="sxs-lookup"><span data-stu-id="3e441-407">GoForward</span></span> 

<span data-ttu-id="3e441-408">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e441-408">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="3e441-409">パブリック void [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="3e441-409">public void [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="3e441-410">検索</span><span class="sxs-lookup"><span data-stu-id="3e441-410">Navigate</span></span> 

<span data-ttu-id="3e441-411">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e441-411">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="3e441-412">パブリック void の [移動](#navigate)(文字列 uri)</span><span class="sxs-lookup"><span data-stu-id="3e441-412">public void [Navigate](#navigate)(string uri)</span></span>

<span data-ttu-id="3e441-413">詳細については、ナビゲーションイベントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e441-413">See the navigation events for more information.</span></span> <span data-ttu-id="3e441-414">これによってナビゲーションが開始されることに注意してください。この操作が完了すると、対応する NavigationStarting イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-414">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

#### <span data-ttu-id="3e441-415">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="3e441-415">NavigateToString</span></span> 

<span data-ttu-id="3e441-416">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e441-416">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="3e441-417">パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="3e441-417">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="3e441-418">HtmlContent パラメーターの文字数は 2 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3e441-418">The htmlContent parameter may not be larger than 2 MB of characters.</span></span> <span data-ttu-id="3e441-419">新しいページの起点は "空白" になります。</span><span class="sxs-lookup"><span data-stu-id="3e441-419">The origin of the new page will be about:blank.</span></span>

#### <span data-ttu-id="3e441-420">Opendevツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3e441-420">OpenDevToolsWindow</span></span> 

<span data-ttu-id="3e441-421">WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e441-421">Opens the DevTools window for the current document in the WebView.</span></span>

> <span data-ttu-id="3e441-422">パブリック void [Opendevツールウィンドウ](#opendevtoolswindow)()</span><span class="sxs-lookup"><span data-stu-id="3e441-422">public void [OpenDevToolsWindow](#opendevtoolswindow)()</span></span>

<span data-ttu-id="3e441-423">DevTools ウィンドウが既に開いているときに、何も呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="3e441-423">Does nothing if called when the DevTools window is already open.</span></span>

#### <span data-ttu-id="3e441-424">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="3e441-424">PostWebMessageAsJson</span></span> 

<span data-ttu-id="3e441-425">指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="3e441-425">Post the specified webMessage to the top level document in this WebView.</span></span>

> <span data-ttu-id="3e441-426">パブリック void [Postwebmessageasjson](#postwebmessageasjson)(String webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="3e441-426">public void [PostWebMessageAsJson](#postwebmessageasjson)(string webMessageAsJson)</span></span>

<span data-ttu-id="3e441-427">最上位のドキュメントのウィンドウには、"." というメッセージイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-427">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="3e441-428">このドキュメントの JavaScript は、次のようにしてイベントをサブスクライブし、サブスクライブを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="3e441-428">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span>

```
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

<span data-ttu-id="3e441-429">イベント引数は、のインスタンス `MessageEvent` です。</span><span class="sxs-lookup"><span data-stu-id="3e441-429">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="3e441-430">CoreWebView2Settings の設定は true である必要があります。また、このメソッドは E_INVALIDARG で失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e441-430">The CoreWebView2Settings.IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="3e441-431">イベント arg の data プロパティは、JSON 文字列として JavaScript オブジェクトに解析された webMessage 文字列のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="3e441-431">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="3e441-432">イベント arg の source プロパティは、オブジェクトへの参照です `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="3e441-432">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="3e441-433">Webview の HTML ドキュメントからホストにメッセージを送信する方法については、「SetWebMessageReceivedEventHandler」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e441-433">See SetWebMessageReceivedEventHandler for information on sending messages from the HTML document in the webview to the host.</span></span> <span data-ttu-id="3e441-434">このメッセージは非同期的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="3e441-434">This message is sent asynchronously.</span></span> <span data-ttu-id="3e441-435">メッセージがページに投稿される前にナビゲーションが発生した場合、メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="3e441-435">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

#### <span data-ttu-id="3e441-436">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="3e441-436">PostWebMessageAsString</span></span> 

<span data-ttu-id="3e441-437">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="3e441-437">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="3e441-438">パブリック void [Postwebmessageasstring](#postwebmessageasstring)(String webmessageasstring)</span><span class="sxs-lookup"><span data-stu-id="3e441-438">public void [PostWebMessageAsString](#postwebmessageasstring)(string webMessageAsString)</span></span>

<span data-ttu-id="3e441-439">これは、PostWebMessageAsJson とまったく同じように動作し `window.chrome.webview` ますが、message イベント arg の data プロパティは、webMessageAsString と同じ値を持つ文字列になります。</span><span class="sxs-lookup"><span data-stu-id="3e441-439">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="3e441-440">JSON オブジェクトではなく単純な文字列を使って通信する場合は、PostWebMessageAsJson の代わりに、これを使います。</span><span class="sxs-lookup"><span data-stu-id="3e441-440">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="3e441-441">再</span><span class="sxs-lookup"><span data-stu-id="3e441-441">Reload</span></span> 

<span data-ttu-id="3e441-442">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="3e441-442">Reload the current page.</span></span>

> <span data-ttu-id="3e441-443">パブリックの void [再読み込み](#reload)()</span><span class="sxs-lookup"><span data-stu-id="3e441-443">public void [Reload](#reload)()</span></span>

<span data-ttu-id="3e441-444">これは、すべてのナビゲーションイベント (HTTP キャッシュ内のエントリを含む) を含む、現在のトップレベルドキュメントの URI に移動する操作と似ています。</span><span class="sxs-lookup"><span data-stu-id="3e441-444">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="3e441-445">ただし、戻る/forward 履歴は変更されません。</span><span class="sxs-lookup"><span data-stu-id="3e441-445">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="3e441-446">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="3e441-446">RemoveHostObjectFromScript</span></span> 

<span data-ttu-id="3e441-447">名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="3e441-447">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>

> <span data-ttu-id="3e441-448">パブリック void [Removehostobjectfromscript](#removehostobjectfromscript)(文字列名)</span><span class="sxs-lookup"><span data-stu-id="3e441-448">public void [RemoveHostObjectFromScript](#removehostobjectfromscript)(string name)</span></span>

<span data-ttu-id="3e441-449">新しいアクセスの試行は拒否されますが、そのオブジェクトが WebView の JavaScript コードによって既に取得されている場合は、JavaScript コードはそのオブジェクトに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3e441-449">While new access attempts will be denied, if the object is already obtained by JavaScript code in the WebView, the JavaScript code will continue to have access to that object.</span></span> <span data-ttu-id="3e441-450">既に削除されているか追加されていない名前に対してこのメソッドを呼び出すと、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3e441-450">Calling this method for a name that is already removed or never added will fail.</span></span>

#### <span data-ttu-id="3e441-451">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="3e441-451">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="3e441-452">指定したスクリプト id を使用して、AddScriptToExecuteOnDocumentCreated で追加された対応する JavaScript を削除します。</span><span class="sxs-lookup"><span data-stu-id="3e441-452">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated with the specified script id.</span></span>

> <span data-ttu-id="3e441-453">パブリック void [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(文字列 id)</span><span class="sxs-lookup"><span data-stu-id="3e441-453">public void [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(string id)</span></span>

#### <span data-ttu-id="3e441-454">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="3e441-454">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="3e441-455">以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="3e441-455">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="3e441-456">パブリック void [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(文字列 Uri、 [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="3e441-456">public void [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(string uri, [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) ResourceContext)</span></span>

<span data-ttu-id="3e441-457">同じフィルターが複数回追加された場合は、削除が有効になるまで何度も削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e441-457">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="3e441-458">追加されていないフィルターの E_INVALIDARG を返します。</span><span class="sxs-lookup"><span data-stu-id="3e441-458">Returns E_INVALIDARG for a filter that was never added.</span></span>

#### <span data-ttu-id="3e441-459">Stop</span><span class="sxs-lookup"><span data-stu-id="3e441-459">Stop</span></span> 

<span data-ttu-id="3e441-460">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="3e441-460">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="3e441-461">パブリック void [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="3e441-461">public void [Stop](#stop)()</span></span>

<span data-ttu-id="3e441-462">スクリプトは停止されません。</span><span class="sxs-lookup"><span data-stu-id="3e441-462">Does not stop scripts.</span></span>

