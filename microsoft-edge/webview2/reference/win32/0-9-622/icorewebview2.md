---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2
ms.openlocfilehash: 6717542349cff327875b609168dff0b82a933668
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012357"
---
# <span data-ttu-id="96b0c-104">インターフェイス ICoreWebView2</span><span class="sxs-lookup"><span data-stu-id="96b0c-104">interface ICoreWebView2</span></span> 

```
interface ICoreWebView2
  : public IUnknown
```

<span data-ttu-id="96b0c-105">WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-105">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="96b0c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="96b0c-106">Summary</span></span>

 <span data-ttu-id="96b0c-107">Members</span><span class="sxs-lookup"><span data-stu-id="96b0c-107">Members</span></span>                        | <span data-ttu-id="96b0c-108">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="96b0c-109">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-109">add_ContainsFullScreenElementChanged</span></span>](#add_containsfullscreenelementchanged) | <span data-ttu-id="96b0c-110">Fullfullscreenelementchanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-110">Add an event handler for the ContainsFullScreenElementChanged event.</span></span>
[<span data-ttu-id="96b0c-111">add_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="96b0c-111">add_ContentLoading</span></span>](#add_contentloading) | <span data-ttu-id="96b0c-112">ContentLoading イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-112">Add an event handler for the ContentLoading event.</span></span>
[<span data-ttu-id="96b0c-113">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-113">add_DocumentTitleChanged</span></span>](#add_documenttitlechanged) | <span data-ttu-id="96b0c-114">Documentechanged Lechanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-114">Add an event handler for the DocumentTitleChanged event.</span></span>
[<span data-ttu-id="96b0c-115">add_FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="96b0c-115">add_FrameNavigationCompleted</span></span>](#add_framenavigationcompleted) | <span data-ttu-id="96b0c-116">FrameNavigationCompleted イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-116">Add an event handler for the FrameNavigationCompleted event.</span></span>
[<span data-ttu-id="96b0c-117">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="96b0c-117">add_FrameNavigationStarting</span></span>](#add_framenavigationstarting) | <span data-ttu-id="96b0c-118">FrameNavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-118">Add an event handler for the FrameNavigationStarting event.</span></span>
[<span data-ttu-id="96b0c-119">add_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-119">add_HistoryChanged</span></span>](#add_historychanged) | <span data-ttu-id="96b0c-120">履歴変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-120">Add an event handler for the HistoryChanged event.</span></span>
[<span data-ttu-id="96b0c-121">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="96b0c-121">add_NavigationCompleted</span></span>](#add_navigationcompleted) | <span data-ttu-id="96b0c-122">NavigationCompleted イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-122">Add an event handler for the NavigationCompleted event.</span></span>
[<span data-ttu-id="96b0c-123">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="96b0c-123">add_NavigationStarting</span></span>](#add_navigationstarting) | <span data-ttu-id="96b0c-124">NavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-124">Add an event handler for the NavigationStarting event.</span></span>
[<span data-ttu-id="96b0c-125">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-125">add_NewWindowRequested</span></span>](#add_newwindowrequested) | <span data-ttu-id="96b0c-126">NewWindowRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-126">Add an event handler for the NewWindowRequested event.</span></span>
[<span data-ttu-id="96b0c-127">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-127">add_PermissionRequested</span></span>](#add_permissionrequested) | <span data-ttu-id="96b0c-128">PermissionRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-128">Add an event handler for the PermissionRequested event.</span></span>
[<span data-ttu-id="96b0c-129">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="96b0c-129">add_ProcessFailed</span></span>](#add_processfailed) | <span data-ttu-id="96b0c-130">ProcessFailed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-130">Add an event handler for the ProcessFailed event.</span></span>
[<span data-ttu-id="96b0c-131">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="96b0c-131">add_ScriptDialogOpening</span></span>](#add_scriptdialogopening) | <span data-ttu-id="96b0c-132">Scriptの開始イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-132">Add an event handler for the ScriptDialogOpening event.</span></span>
[<span data-ttu-id="96b0c-133">add_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-133">add_SourceChanged</span></span>](#add_sourcechanged) | <span data-ttu-id="96b0c-134">SourceChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-134">Add an event handler for the SourceChanged event.</span></span>
[<span data-ttu-id="96b0c-135">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="96b0c-135">add_WebMessageReceived</span></span>](#add_webmessagereceived) | <span data-ttu-id="96b0c-136">WebMessageReceived イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-136">Add an event handler for the WebMessageReceived event.</span></span>
[<span data-ttu-id="96b0c-137">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-137">add_WebResourceRequested</span></span>](#add_webresourcerequested) | <span data-ttu-id="96b0c-138">WebResourceRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-138">Add an event handler for the WebResourceRequested event.</span></span>
[<span data-ttu-id="96b0c-139">add_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-139">add_WindowCloseRequested</span></span>](#add_windowcloserequested) | <span data-ttu-id="96b0c-140">WindowCloseRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-140">Add an event handler for the WindowCloseRequested event.</span></span>
[<span data-ttu-id="96b0c-141">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="96b0c-141">AddHostObjectToScript</span></span>](#addhostobjecttoscript) | <span data-ttu-id="96b0c-142">指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-142">Add the provided host object to script running in the WebView with the specified name.</span></span>
[<span data-ttu-id="96b0c-143">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="96b0c-143">AddScriptToExecuteOnDocumentCreated</span></span>](#addscripttoexecuteondocumentcreated) | <span data-ttu-id="96b0c-144">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-144">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="96b0c-145">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="96b0c-145">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="96b0c-146">URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-146">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="96b0c-147">Calldevon Protocolメソッド</span><span class="sxs-lookup"><span data-stu-id="96b0c-147">CallDevToolsProtocolMethod</span></span>](#calldevtoolsprotocolmethod) | <span data-ttu-id="96b0c-148">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-148">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="96b0c-149">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="96b0c-149">CapturePreview</span></span>](#capturepreview) | <span data-ttu-id="96b0c-150">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="96b0c-150">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="96b0c-151">Execuスクリプト</span><span class="sxs-lookup"><span data-stu-id="96b0c-151">ExecuteScript</span></span>](#executescript) | <span data-ttu-id="96b0c-152">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-152">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="96b0c-153">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="96b0c-153">get_BrowserProcessId</span></span>](#get_browserprocessid) | <span data-ttu-id="96b0c-154">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="96b0c-154">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="96b0c-155">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="96b0c-155">get_CanGoBack</span></span>](#get_cangoback) | <span data-ttu-id="96b0c-156">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-156">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="96b0c-157">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="96b0c-157">get_CanGoForward</span></span>](#get_cangoforward) | <span data-ttu-id="96b0c-158">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-158">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="96b0c-159">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="96b0c-159">get_ContainsFullScreenElement</span></span>](#get_containsfullscreenelement) | <span data-ttu-id="96b0c-160">WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-160">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="96b0c-161">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="96b0c-161">get_DocumentTitle</span></span>](#get_documenttitle) | <span data-ttu-id="96b0c-162">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="96b0c-162">The title for the current top level document.</span></span>
[<span data-ttu-id="96b0c-163">get_Settings</span><span class="sxs-lookup"><span data-stu-id="96b0c-163">get_Settings</span></span>](#get_settings) | <span data-ttu-id="96b0c-164">[ICoreWebView2Settings](icorewebview2settings.md)オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96b0c-164">The [ICoreWebView2Settings](icorewebview2settings.md) object contains various modifiable settings for the running WebView.</span></span>
[<span data-ttu-id="96b0c-165">get_Source</span><span class="sxs-lookup"><span data-stu-id="96b0c-165">get_Source</span></span>](#get_source) | <span data-ttu-id="96b0c-166">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="96b0c-166">The URI of the current top level document.</span></span>
[<span data-ttu-id="96b0c-167">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="96b0c-167">GetDevToolsProtocolEventReceiver</span></span>](#getdevtoolsprotocoleventreceiver) | <span data-ttu-id="96b0c-168">DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-168">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>
[<span data-ttu-id="96b0c-169">GoBack</span><span class="sxs-lookup"><span data-stu-id="96b0c-169">GoBack</span></span>](#goback) | <span data-ttu-id="96b0c-170">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-170">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="96b0c-171">GoForward</span><span class="sxs-lookup"><span data-stu-id="96b0c-171">GoForward</span></span>](#goforward) | <span data-ttu-id="96b0c-172">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-172">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="96b0c-173">検索</span><span class="sxs-lookup"><span data-stu-id="96b0c-173">Navigate</span></span>](#navigate) | <span data-ttu-id="96b0c-174">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-174">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="96b0c-175">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="96b0c-175">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="96b0c-176">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-176">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="96b0c-177">Opendevツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="96b0c-177">OpenDevToolsWindow</span></span>](#opendevtoolswindow) | <span data-ttu-id="96b0c-178">WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-178">Opens the DevTools window for the current document in the WebView.</span></span>
[<span data-ttu-id="96b0c-179">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="96b0c-179">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="96b0c-180">指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-180">Post the specified webMessage to the top level document in this WebView.</span></span>
[<span data-ttu-id="96b0c-181">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="96b0c-181">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="96b0c-182">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="96b0c-182">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="96b0c-183">再</span><span class="sxs-lookup"><span data-stu-id="96b0c-183">Reload</span></span>](#reload) | <span data-ttu-id="96b0c-184">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="96b0c-184">Reload the current page.</span></span>
[<span data-ttu-id="96b0c-185">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-185">remove_ContainsFullScreenElementChanged</span></span>](#remove_containsfullscreenelementchanged) | <span data-ttu-id="96b0c-186">Add_ContainsFullScreenElementChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-186">Remove an event handler previously added with add_ContainsFullScreenElementChanged.</span></span>
[<span data-ttu-id="96b0c-187">remove_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="96b0c-187">remove_ContentLoading</span></span>](#remove_contentloading) | <span data-ttu-id="96b0c-188">Add_ContentLoading で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-188">Remove an event handler previously added with add_ContentLoading.</span></span>
[<span data-ttu-id="96b0c-189">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-189">remove_DocumentTitleChanged</span></span>](#remove_documenttitlechanged) | <span data-ttu-id="96b0c-190">Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-190">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>
[<span data-ttu-id="96b0c-191">remove_FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="96b0c-191">remove_FrameNavigationCompleted</span></span>](#remove_framenavigationcompleted) | <span data-ttu-id="96b0c-192">Add_FrameNavigationCompleted で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-192">Remove an event handler previously added with add_FrameNavigationCompleted.</span></span>
[<span data-ttu-id="96b0c-193">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="96b0c-193">remove_FrameNavigationStarting</span></span>](#remove_framenavigationstarting) | <span data-ttu-id="96b0c-194">Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-194">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>
[<span data-ttu-id="96b0c-195">remove_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-195">remove_HistoryChanged</span></span>](#remove_historychanged) | <span data-ttu-id="96b0c-196">Add_HistoryChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-196">Remove an event handler previously added with add_HistoryChanged.</span></span>
[<span data-ttu-id="96b0c-197">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="96b0c-197">remove_NavigationCompleted</span></span>](#remove_navigationcompleted) | <span data-ttu-id="96b0c-198">Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-198">Remove an event handler previously added with add_NavigationCompleted.</span></span>
[<span data-ttu-id="96b0c-199">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="96b0c-199">remove_NavigationStarting</span></span>](#remove_navigationstarting) | <span data-ttu-id="96b0c-200">Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-200">Remove an event handler previously added with add_NavigationStarting.</span></span>
[<span data-ttu-id="96b0c-201">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-201">remove_NewWindowRequested</span></span>](#remove_newwindowrequested) | <span data-ttu-id="96b0c-202">Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-202">Remove an event handler previously added with add_NewWindowRequested.</span></span>
[<span data-ttu-id="96b0c-203">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-203">remove_PermissionRequested</span></span>](#remove_permissionrequested) | <span data-ttu-id="96b0c-204">Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-204">Remove an event handler previously added with add_PermissionRequested.</span></span>
[<span data-ttu-id="96b0c-205">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="96b0c-205">remove_ProcessFailed</span></span>](#remove_processfailed) | <span data-ttu-id="96b0c-206">Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-206">Remove an event handler previously added with add_ProcessFailed.</span></span>
[<span data-ttu-id="96b0c-207">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="96b0c-207">remove_ScriptDialogOpening</span></span>](#remove_scriptdialogopening) | <span data-ttu-id="96b0c-208">Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-208">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>
[<span data-ttu-id="96b0c-209">remove_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-209">remove_SourceChanged</span></span>](#remove_sourcechanged) | <span data-ttu-id="96b0c-210">Add_SourceChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-210">Remove an event handler previously added with add_SourceChanged.</span></span>
[<span data-ttu-id="96b0c-211">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="96b0c-211">remove_WebMessageReceived</span></span>](#remove_webmessagereceived) | <span data-ttu-id="96b0c-212">Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-212">Remove an event handler previously added with add_WebMessageReceived.</span></span>
[<span data-ttu-id="96b0c-213">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-213">remove_WebResourceRequested</span></span>](#remove_webresourcerequested) | <span data-ttu-id="96b0c-214">Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-214">Remove an event handler previously added with add_WebResourceRequested.</span></span>
[<span data-ttu-id="96b0c-215">remove_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-215">remove_WindowCloseRequested</span></span>](#remove_windowcloserequested) | <span data-ttu-id="96b0c-216">Add_WindowCloseRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-216">Remove an event handler previously added with add_WindowCloseRequested.</span></span>
[<span data-ttu-id="96b0c-217">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="96b0c-217">RemoveHostObjectFromScript</span></span>](#removehostobjectfromscript) | <span data-ttu-id="96b0c-218">名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="96b0c-218">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>
[<span data-ttu-id="96b0c-219">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="96b0c-219">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="96b0c-220">指定したスクリプト id で、によって追加された対応する JavaScript を削除し `AddScriptToExecuteOnDocumentCreated` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-220">Remove the corresponding JavaScript added using `AddScriptToExecuteOnDocumentCreated` with the specified script id.</span></span>
[<span data-ttu-id="96b0c-221">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="96b0c-221">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="96b0c-222">以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-222">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>
[<span data-ttu-id="96b0c-223">Stop</span><span class="sxs-lookup"><span data-stu-id="96b0c-223">Stop</span></span>](#stop) | <span data-ttu-id="96b0c-224">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-224">Stop all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="96b0c-225">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="96b0c-225">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span>](#corewebview2_capture_preview_image_format) | <span data-ttu-id="96b0c-226">ICoreWebView2:: CapturePreview メソッドで使用されている画像形式。</span><span class="sxs-lookup"><span data-stu-id="96b0c-226">Image format used by the ICoreWebView2::CapturePreview method.</span></span>
[<span data-ttu-id="96b0c-227">COREWEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="96b0c-227">COREWEBVIEW2_KEY_EVENT_KIND</span></span>](#corewebview2_key_event_kind) | <span data-ttu-id="96b0c-228">AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="96b0c-228">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="96b0c-229">COREWEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="96b0c-229">COREWEBVIEW2_MOVE_FOCUS_REASON</span></span>](#corewebview2_move_focus_reason) | <span data-ttu-id="96b0c-230">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="96b0c-230">Reason for moving focus.</span></span>
[<span data-ttu-id="96b0c-231">COREWEBVIEW2_PERMISSION_KIND</span><span class="sxs-lookup"><span data-stu-id="96b0c-231">COREWEBVIEW2_PERMISSION_KIND</span></span>](#corewebview2_permission_kind) | <span data-ttu-id="96b0c-232">アクセス許可要求の種類。</span><span class="sxs-lookup"><span data-stu-id="96b0c-232">The type of a permission request.</span></span>
[<span data-ttu-id="96b0c-233">COREWEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="96b0c-233">COREWEBVIEW2_PERMISSION_STATE</span></span>](#corewebview2_permission_state) | <span data-ttu-id="96b0c-234">アクセス許可要求に対する応答。</span><span class="sxs-lookup"><span data-stu-id="96b0c-234">Response to a permission request.</span></span>
[<span data-ttu-id="96b0c-235">COREWEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="96b0c-235">COREWEBVIEW2_PHYSICAL_KEY_STATUS</span></span>](#corewebview2_physical_key_status) | <span data-ttu-id="96b0c-236">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="96b0c-236">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>
[<span data-ttu-id="96b0c-237">COREWEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="96b0c-237">COREWEBVIEW2_PROCESS_FAILED_KIND</span></span>](#corewebview2_process_failed_kind) | <span data-ttu-id="96b0c-238">ICoreWebView2ProcessFailedEventHandler インターフェイスで使用されているプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="96b0c-238">Kind of process failure used in the ICoreWebView2ProcessFailedEventHandler interface.</span></span>
[<span data-ttu-id="96b0c-239">COREWEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="96b0c-239">COREWEBVIEW2_SCRIPT_DIALOG_KIND</span></span>](#corewebview2_script_dialog_kind) | <span data-ttu-id="96b0c-240">ICoreWebView2ScriptDialogOpeningEventHandler インターフェイスで使用される JavaScript ダイアログの種類。</span><span class="sxs-lookup"><span data-stu-id="96b0c-240">Kind of JavaScript dialog used in the ICoreWebView2ScriptDialogOpeningEventHandler interface.</span></span>
[<span data-ttu-id="96b0c-241">COREWEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="96b0c-241">COREWEBVIEW2_WEB_ERROR_STATUS</span></span>](#corewebview2_web_error_status) | <span data-ttu-id="96b0c-242">Web ナビゲーションのエラー状態の値。</span><span class="sxs-lookup"><span data-stu-id="96b0c-242">Error status values for web navigations.</span></span>
[<span data-ttu-id="96b0c-243">COREWEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="96b0c-243">COREWEBVIEW2_WEB_RESOURCE_CONTEXT</span></span>](#corewebview2_web_resource_context) | <span data-ttu-id="96b0c-244">Web リソース要求コンテキストの列挙。</span><span class="sxs-lookup"><span data-stu-id="96b0c-244">Enum for web resource request contexts.</span></span>

## <span data-ttu-id="96b0c-245">Members</span><span class="sxs-lookup"><span data-stu-id="96b0c-245">Members</span></span>

#### <span data-ttu-id="96b0c-246">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-246">add_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="96b0c-247">Fullfullscreenelementchanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-247">Add an event handler for the ContainsFullScreenElementChanged event.</span></span>

> <span data-ttu-id="96b0c-248">パブリック HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([ICoreWebView2ContainsFullScreenElementChangedEventHandler](icorewebview2containsfullscreenelementchangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-248">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([ICoreWebView2ContainsFullScreenElementChangedEventHandler](icorewebview2containsfullscreenelementchangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-249">持つ Fullfullscreenelement プロパティが変更されたときに発生する、Fullfullscreenelementchanged。</span><span class="sxs-lookup"><span data-stu-id="96b0c-249">ContainsFullScreenElementChanged fires when the ContainsFullScreenElement property changes.</span></span> <span data-ttu-id="96b0c-250">これは、WebView 内の HTML 要素が、WebView のサイズまたはフルスクリーンのままであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-250">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="96b0c-251">このイベントは、たとえば、ビデオ要素が全画面表示になっている要求の場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="96b0c-251">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="96b0c-252">次に、Fullfullscreenelementelementのリスナーが、応答で WebView のサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-252">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

```cpp
    // Register a handler for the ContainsFullScreenChanged event.
    CHECK_FAILURE(m_webView->add_ContainsFullScreenElementChanged(
        Callback<ICoreWebView2ContainsFullScreenElementChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                if (m_fullScreenAllowed)
                {
                    CHECK_FAILURE(
                        sender->get_ContainsFullScreenElement(&m_containsFullscreenElement));
                    if (m_containsFullscreenElement)
                    {
                        EnterFullScreen();
                    }
                    else
                    {
                        ExitFullScreen();
                    }
                }
                return S_OK;
            })
            .Get(),
        nullptr));
```

#### <span data-ttu-id="96b0c-253">add_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="96b0c-253">add_ContentLoading</span></span> 

<span data-ttu-id="96b0c-254">ContentLoading イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-254">Add an event handler for the ContentLoading event.</span></span>

> <span data-ttu-id="96b0c-255">パブリック HRESULT [add_ContentLoading](#add_contentloading)([ICoreWebView2ContentLoadingEventHandler](icorewebview2contentloadingeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-255">public HRESULT [add_ContentLoading](#add_contentloading)([ICoreWebView2ContentLoadingEventHandler](icorewebview2contentloadingeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-256">ContentLoading は、コンテンツが読み込まれる前に、AddScriptToExecuteOnDocumentCreated によって追加されたスクリプトを含みます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-256">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="96b0c-257">同じページナビゲーションが発生した場合、ContentLoading は発生しません (フラグメントナビゲーションや履歴の状態ナビゲートなど)。</span><span class="sxs-lookup"><span data-stu-id="96b0c-257">ContentLoading will not fire if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span> <span data-ttu-id="96b0c-258">これは、NavigationStarting イベントと SourceChanged イベントの後で、履歴の変更イベントと Navigationstarting イベントの前に発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-258">This follows the NavigationStarting and SourceChanged events and precedes the HistoryChanged and NavigationCompleted events.</span></span>

#### <span data-ttu-id="96b0c-259">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-259">add_DocumentTitleChanged</span></span> 

<span data-ttu-id="96b0c-260">Documentechanged Lechanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-260">Add an event handler for the DocumentTitleChanged event.</span></span>

> <span data-ttu-id="96b0c-261">パブリック HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([ICoreWebView2DocumentTitleChangedEventHandler](icorewebview2documenttitlechangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-261">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([ICoreWebView2DocumentTitleChangedEventHandler](icorewebview2documenttitlechangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-262">Document肩書は、WebView の DocumentTitle プロパティが変更され、NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-262">DocumentTitleChanged fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

```cpp
    // Register a handler for the DocumentTitleChanged event.
    // This handler just announces the new title on the window's title bar.
    CHECK_FAILURE(m_webView->add_DocumentTitleChanged(
        Callback<ICoreWebView2DocumentTitleChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                wil::unique_cotaskmem_string title;
                CHECK_FAILURE(sender->get_DocumentTitle(&title));
                SetWindowText(m_appWindow->GetMainWindow(), title.get());
                return S_OK;
            })
            .Get(),
        &m_documentTitleChangedToken));
```

#### <span data-ttu-id="96b0c-263">add_FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="96b0c-263">add_FrameNavigationCompleted</span></span> 

<span data-ttu-id="96b0c-264">FrameNavigationCompleted イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-264">Add an event handler for the FrameNavigationCompleted event.</span></span>

> <span data-ttu-id="96b0c-265">パブリック HRESULT [add_FrameNavigationCompleted](#add_framenavigationcompleted)([ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-265">public HRESULT [add_FrameNavigationCompleted](#add_framenavigationcompleted)([ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-266">FrameNavigationCompleted は、子フレームが完全に読み込まれた (読み込みが開始された) か、エラーが発生して読み込みを停止したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-266">FrameNavigationCompleted fires when a child frame has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

```cpp
    // Register a handler for the FrameNavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    CHECK_FAILURE(m_webView->add_FrameNavigationCompleted(
        Callback<ICoreWebView2NavigationCompletedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    COREWEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    std::wstring error_msg = WebErrorStatusToString(webErrorStatus);
                    MessageBox(nullptr,
                       (std::wstring(L"IFrame navigation failed with the ") +
                         L"give in error " + error_msg).c_str(),
                       L"Navigation Failure", MB_OK);
                    if (webErrorStatus == COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }
                return S_OK;
            })
            .Get(),
        &m_frameNavigationCompletedToken));
```

#### <span data-ttu-id="96b0c-267">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="96b0c-267">add_FrameNavigationStarting</span></span> 

<span data-ttu-id="96b0c-268">FrameNavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-268">Add an event handler for the FrameNavigationStarting event.</span></span>

> <span data-ttu-id="96b0c-269">パブリック HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-269">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-270">FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-270">FrameNavigationStarting fires when a child frame in the WebView requests permission to navigate to a different URI.</span></span> <span data-ttu-id="96b0c-271">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-271">This will fire for redirects as well.</span></span>

<span data-ttu-id="96b0c-272">対応するナビゲーションは、イベントハンドラーから制御が返されるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-272">Corresponding navigations can be blocked until the event handler returns.</span></span>

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<ICoreWebView2NavigationStartingEventHandler>(
            [this](ICoreWebView2* sender,
                   ICoreWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));
        }
        return S_OK;
    }).Get(), &m_frameNavigationStartingToken));
```

#### <span data-ttu-id="96b0c-273">add_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-273">add_HistoryChanged</span></span> 

<span data-ttu-id="96b0c-274">履歴変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-274">Add an event handler for the HistoryChanged event.</span></span>

> <span data-ttu-id="96b0c-275">パブリック HRESULT [add_HistoryChanged](#add_historychanged)([ICoreWebView2HistoryChangedEventHandler](icorewebview2historychangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-275">public HRESULT [add_HistoryChanged](#add_historychanged)([ICoreWebView2HistoryChangedEventHandler](icorewebview2historychangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-276">履歴を変更すると、トップレベルドキュメントのナビゲーション履歴の変更がリッスンされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-276">HistoryChanged listens to the change of navigation history for the top level document.</span></span> <span data-ttu-id="96b0c-277">CanGoBack/CanGoForward の値が変更されたかどうかを確認するには、履歴の変更を使います。</span><span class="sxs-lookup"><span data-stu-id="96b0c-277">Use HistoryChanged to check if CanGoBack/CanGoForward value has changed.</span></span> <span data-ttu-id="96b0c-278">GoBack/GoForward を使用する場合にも変更履歴が発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-278">HistoryChanged also fires for using GoBack/GoForward.</span></span> <span data-ttu-id="96b0c-279">変更履歴は、SourceChanged と ContentLoading の後に発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-279">HistoryChanged fires after SourceChanged and ContentLoading.</span></span>

```cpp
    // Register a handler for the HistoryChanged event.
    // Update the Back, Forward buttons.
    CHECK_FAILURE(m_webView->add_HistoryChanged(
        Callback<ICoreWebView2HistoryChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                m_toolbar->SetItemEnabled(Toolbar::Item_BackButton, canGoBack);
                m_toolbar->SetItemEnabled(Toolbar::Item_ForwardButton, canGoForward);

                return S_OK;
            })
            .Get(),
        &m_historyChangedToken));
```

#### <span data-ttu-id="96b0c-280">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="96b0c-280">add_NavigationCompleted</span></span> 

<span data-ttu-id="96b0c-281">NavigationCompleted イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-281">Add an event handler for the NavigationCompleted event.</span></span>

> <span data-ttu-id="96b0c-282">パブリック HRESULT [add_NavigationCompleted](#add_navigationcompleted)([ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-282">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)([ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-283">NavigationCompleted は、WebView が完全に読み込まれるとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-283">NavigationCompleted fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

```cpp
    // Register a handler for the NavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    // Also update the Cancel buttons.
    CHECK_FAILURE(m_webView->add_NavigationCompleted(
        Callback<ICoreWebView2NavigationCompletedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    COREWEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }
                m_toolbar->SetItemEnabled(Toolbar::Item_CancelButton, false);
                m_toolbar->SetItemEnabled(Toolbar::Item_ReloadButton, true);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### <span data-ttu-id="96b0c-284">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="96b0c-284">add_NavigationStarting</span></span> 

<span data-ttu-id="96b0c-285">NavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-285">Add an event handler for the NavigationStarting event.</span></span>

> <span data-ttu-id="96b0c-286">パブリック HRESULT [add_NavigationStarting](#add_navigationstarting)([ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-286">public HRESULT [add_NavigationStarting](#add_navigationstarting)([ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-287">NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-287">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="96b0c-288">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-288">This will fire for redirects as well.</span></span>

<span data-ttu-id="96b0c-289">対応するナビゲーションは、イベントハンドラーから制御が返されるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-289">Corresponding navigations can be blocked until the event handler returns.</span></span>

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<ICoreWebView2NavigationStartingEventHandler>(
            [this](ICoreWebView2* sender,
                   ICoreWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
        }
        // Changes to settings will apply at the next navigation, which includes the
        // navigation after a NavigationStarting event.  We can use this to change
        // settings according to what site we're visiting.
        if (ShouldBlockScriptForUri(uri.get()))
        {
            m_settings->put_IsScriptEnabled(FALSE);
        }
        else
        {
            m_settings->put_IsScriptEnabled(m_isScriptEnabled);
        }
        return S_OK;
    }).Get(), &m_navigationStartingToken));
```

#### <span data-ttu-id="96b0c-290">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-290">add_NewWindowRequested</span></span> 

<span data-ttu-id="96b0c-291">NewWindowRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-291">Add an event handler for the NewWindowRequested event.</span></span>

> <span data-ttu-id="96b0c-292">パブリック HRESULT [add_NewWindowRequested](#add_newwindowrequested)([ICoreWebView2NewWindowRequestedEventHandler](icorewebview2newwindowrequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-292">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)([ICoreWebView2NewWindowRequestedEventHandler](icorewebview2newwindowrequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-293">NewWindowRequested は、WebView 内のコンテンツが、window からの移動などの新しいウィンドウを開くように要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-293">NewWindowRequested fires when content inside the WebView requests to open a new window, such as through window.open.</span></span> <span data-ttu-id="96b0c-294">アプリは、開かれたウィンドウと見なされるターゲット WebView を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-294">The app can pass a target WebView that will be considered the opened window.</span></span>

<span data-ttu-id="96b0c-295">新しいウィンドウが要求されたスクリプトは、イベント引数で遅延が発生しなかった場合に、イベントハンドラーから制御が返されるまでブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-295">Scripts resulted in the new window requested can be blocked until the event handler returns if a deferral is not taken on the event args.</span></span> <span data-ttu-id="96b0c-296">延期が行われると、遅延が完了するまで、スクリプトはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-296">If a deferral is taken, then scripts are blocked until the deferral is completed.</span></span>

```cpp
    // Register a handler for the NewWindowRequested event.
    // This handler will defer the event, create a new app window, and then once the
    // new window is ready, it'll provide that new window's WebView as the response to
    // the request.
    CHECK_FAILURE(m_webView->add_NewWindowRequested(
        Callback<ICoreWebView2NewWindowRequestedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NewWindowRequestedEventArgs* args) {
                wil::com_ptr<ICoreWebView2Deferral> deferral;
                CHECK_FAILURE(args->GetDeferral(&deferral));
                AppWindow* newAppWindow;

                wil::com_ptr<ICoreWebView2WindowFeatures> windowFeatures;
                CHECK_FAILURE(args->get_WindowFeatures(&windowFeatures));

                RECT windowRect = {0};
                UINT32 left = 0;
                UINT32 top = 0;
                UINT32 height = 0;
                UINT32 width = 0;
                BOOL shouldHaveToolbar = true;

                BOOL hasPosition = FALSE;
                BOOL hasSize = FALSE;
                CHECK_FAILURE(windowFeatures->HasPosition(&hasPosition));
                CHECK_FAILURE(windowFeatures->HasSize(&hasSize));

                bool useDefaultWindow = true;

                if (!!hasPosition && !!hasSize)
                {
                    CHECK_FAILURE(windowFeatures->get_Left(&left));
                    CHECK_FAILURE(windowFeatures->get_Top(&top));
                    CHECK_FAILURE(windowFeatures->get_Height(&height));
                    CHECK_FAILURE(windowFeatures->get_Width(&width));
                    useDefaultWindow = false;
                }
                CHECK_FAILURE(windowFeatures->get_Toolbar(&shouldHaveToolbar));

                windowRect.left = left;
                windowRect.right = left + (width < s_minNewWindowSize ? s_minNewWindowSize : width);
                windowRect.top = top;
                windowRect.bottom = top + (height < s_minNewWindowSize ? s_minNewWindowSize : height);

                if (!useDefaultWindow)
                {
                  newAppWindow = new AppWindow(m_creationModeId, L"", false, nullptr, true, windowRect, !!shouldHaveToolbar);
                }
                else
                {
                  newAppWindow = new AppWindow(m_creationModeId, L"");
                }
                newAppWindow->m_isPopupWindow = true;
                newAppWindow->m_onWebViewFirstInitialized = [args, deferral, newAppWindow]() {
                    CHECK_FAILURE(args->put_NewWindow(newAppWindow->m_webView.get()));
                    CHECK_FAILURE(args->put_Handled(TRUE));
                    CHECK_FAILURE(deferral->Complete());
                };

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### <span data-ttu-id="96b0c-297">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-297">add_PermissionRequested</span></span> 

<span data-ttu-id="96b0c-298">PermissionRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-298">Add an event handler for the PermissionRequested event.</span></span>

> <span data-ttu-id="96b0c-299">パブリック HRESULT [add_PermissionRequested](#add_permissionrequested)([ICoreWebView2PermissionRequestedEventHandler](icorewebview2permissionrequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-299">public HRESULT [add_PermissionRequested](#add_permissionrequested)([ICoreWebView2PermissionRequestedEventHandler](icorewebview2permissionrequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-300">PermissionRequested は、WebView のコンテンツが権限を持つ一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-300">PermissionRequested fires when content in a WebView requests permission to access some privileged resources.</span></span>

<span data-ttu-id="96b0c-301">イベント引数に対して遅延が発生しない場合は、イベントハンドラーから制御が返されるまで、後続のスクリプトをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-301">If a deferral is not taken on the event args, the subsequent scripts can be blocked until the event handler returns.</span></span> <span data-ttu-id="96b0c-302">延期が行われると、遅延が完了するまで、スクリプトはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-302">If a deferral is taken, then the scripts are blocked until the deferral is completed.</span></span>

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<ICoreWebView2PermissionRequestedEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        COREWEBVIEW2_PERMISSION_KIND kind = COREWEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionKind(&kind));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionKind(kind);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        COREWEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? COREWEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? COREWEBVIEW2_PERMISSION_STATE_DENY
            :                     COREWEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### <span data-ttu-id="96b0c-303">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="96b0c-303">add_ProcessFailed</span></span> 

<span data-ttu-id="96b0c-304">ProcessFailed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-304">Add an event handler for the ProcessFailed event.</span></span>

> <span data-ttu-id="96b0c-305">パブリック HRESULT [add_ProcessFailed](#add_processfailed)([ICoreWebView2ProcessFailedEventHandler](icorewebview2processfailedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-305">public HRESULT [add_ProcessFailed](#add_processfailed)([ICoreWebView2ProcessFailedEventHandler](icorewebview2processfailedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-306">ProcessFailed は、WebView プロセスが予期せず終了したか、応答しなくなったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-306">ProcessFailed fires when a WebView process is terminated unexpectedly or becomes unresponsive.</span></span>

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<ICoreWebView2ProcessFailedEventHandler>(
            [this](ICoreWebView2* sender,
                ICoreWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        COREWEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser process exited unexpectedly.  Recreate webview?",
                L"Browser process exited",
                MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        else if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser render process has stopped responding.  Recreate webview?",
                L"Web page unresponsive", MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        else if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser render process exited unexpectedly. Reload page?",
                L"Web page unresponsive", MB_YESNO);
            if (button == IDYES)
            {
                CHECK_FAILURE(m_webView->Reload());
            }
        }
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### <span data-ttu-id="96b0c-307">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="96b0c-307">add_ScriptDialogOpening</span></span> 

<span data-ttu-id="96b0c-308">Scriptの開始イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-308">Add an event handler for the ScriptDialogOpening event.</span></span>

> <span data-ttu-id="96b0c-309">パブリック HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([ICoreWebView2ScriptDialogOpeningEventHandler](icorewebview2scriptdialogopeningeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-309">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([ICoreWebView2ScriptDialogOpeningEventHandler](icorewebview2scriptdialogopeningeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-310">ScriptDialogOpening は、webview の JavaScript ダイアログ (アラート、確認、プロンプト、または "beforeunload") が表示されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-310">ScriptDialogOpening fires when a JavaScript dialog (alert, confirm, prompt, or beforeunload) will show for the webview.</span></span> <span data-ttu-id="96b0c-311">このイベントは、ICoreWebView2Settings:: Aredefaultscript プロパティが false に設定されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-311">This event only fires if the ICoreWebView2Settings::AreDefaultScriptDialogsEnabled property is set to false.</span></span> <span data-ttu-id="96b0c-312">Scriptdialogs 左中イベントを使うと、ダイアログを非表示にしたり、既定のダイアログをカスタムダイアログに置き換えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-312">The ScriptDialogOpening event can be used to suppress dialogs or replace default dialogs with custom dialogs.</span></span>

<span data-ttu-id="96b0c-313">イベント引数に対して遅延が発生しない場合は、イベントハンドラーから制御が返されるまで、後続のスクリプトをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-313">If a deferral is not taken on the event args, the subsequent scripts can be blocked until the event handler returns.</span></span> <span data-ttu-id="96b0c-314">延期が行われると、遅延が完了するまで、スクリプトはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-314">If a deferral is taken, then the scripts are blocked until the deferral is completed.</span></span>

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<ICoreWebView2ScriptDialogOpeningEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<ICoreWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            COREWEBVIEW2_SCRIPT_DIALOG_KIND type;
            wil::unique_cotaskmem_string message;
            wil::unique_cotaskmem_string defaultText;

            CHECK_FAILURE(eventArgs->get_Uri(&uri));
            CHECK_FAILURE(eventArgs->get_Kind(&type));
            CHECK_FAILURE(eventArgs->get_Message(&message));
            CHECK_FAILURE(eventArgs->get_DefaultText(&defaultText));

            std::wstring promptString = std::wstring(L"The page at '")
                + uri.get() + L"' says:";
            TextInputDialog dialog(
                m_appWindow->GetMainWindow(),
                L"Script Dialog",
                promptString.c_str(),
                message.get(),
                defaultText.get(),
                /* readonly */ type != COREWEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<ICoreWebView2Deferral> deferral;
            CHECK_FAILURE(args->GetDeferral(&deferral));
            m_completeDeferredDialog = [showDialog, deferral]
            {
                showDialog();
                CHECK_FAILURE(deferral->Complete());
            };
        }
        else
        {
            showDialog();
        }

        return S_OK;
    }).Get(), &m_scriptDialogOpeningToken));
```

#### <span data-ttu-id="96b0c-315">add_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-315">add_SourceChanged</span></span> 

<span data-ttu-id="96b0c-316">SourceChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-316">Add an event handler for the SourceChanged event.</span></span>

> <span data-ttu-id="96b0c-317">パブリック HRESULT [add_SourceChanged](#add_sourcechanged)([ICoreWebView2SourceChangedEventHandler](icorewebview2sourcechangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-317">public HRESULT [add_SourceChanged](#add_sourcechanged)([ICoreWebView2SourceChangedEventHandler](icorewebview2sourcechangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-318">SourceChanged Source プロパティが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-318">SourceChanged fires when the Source property changes.</span></span> <span data-ttu-id="96b0c-319">SourceChanged のサイトまたはフラグメントナビゲーションに移動する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-319">SourceChanged fires for navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="96b0c-320">ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションについては、このような操作は発生しません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-320">It will not fire for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span> <span data-ttu-id="96b0c-321">SourceChanged ドキュメントへのナビゲーションのためにコンテンツを読み込む前に、SourceChanged が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-321">SourceChanged fires before ContentLoading for navigation to a new document.</span></span>

```cpp
    // Register a handler for the SourceChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_SourceChanged(
        Callback<ICoreWebView2SourceChangedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2SourceChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(GetAddressBar(), uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### <span data-ttu-id="96b0c-322">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="96b0c-322">add_WebMessageReceived</span></span> 

<span data-ttu-id="96b0c-323">WebMessageReceived イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-323">Add an event handler for the WebMessageReceived event.</span></span>

> <span data-ttu-id="96b0c-324">パブリック HRESULT [add_WebMessageReceived](#add_webmessagereceived)([ICoreWebView2WebMessageReceivedEventHandler](icorewebview2webmessagereceivedeventhandler.md) \* handler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-324">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)([ICoreWebView2WebMessageReceivedEventHandler](icorewebview2webmessagereceivedeventhandler.md) \* handler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-325">WebMessageReceived は、ICoreWebView2Settings:: IsWebMessageEnabled setting が設定されているときに発生します。また、WebView 呼び出しの最上位レベルの文書です `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="96b0c-325">WebMessageReceived fires when the ICoreWebView2Settings::IsWebMessageEnabled setting is set and the top level document of the WebView calls `window.chrome.webview.postMessage`.</span></span> <span data-ttu-id="96b0c-326">PostMessage 関数は、 `void postMessage(object)` JSON 変換でサポートされているオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="96b0c-326">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span>

```html
        window.chrome.webview.addEventListener('message', arg => {
            if ("SetColor" in arg.data) {
                document.getElementById("colorable").style.color = arg.data.SetColor;
            }
            if ("WindowBounds" in arg.data) {
                document.getElementById("window-bounds").value = arg.data.WindowBounds;
            }
        });

        function SetTitleText() {
            let titleText = document.getElementById("title-text");
            window.chrome.webview.postMessage(`SetTitleText ${titleText.value}`);
        }
        function GetWindowBounds() {
            window.chrome.webview.postMessage("GetWindowBounds");
        }
```
 <span data-ttu-id="96b0c-327">PostMessage が呼び出されると、ハンドラーの Invoke メソッドが、JSON 文字列に変換された postMessage のオブジェクトパラメーターと共に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-327">When postMessage is called, the handler's Invoke method will be called with the postMessage's object parameter converted to a JSON string.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<ICoreWebView2WebMessageReceivedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->TryGetWebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### <span data-ttu-id="96b0c-328">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-328">add_WebResourceRequested</span></span> 

<span data-ttu-id="96b0c-329">WebResourceRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-329">Add an event handler for the WebResourceRequested event.</span></span>

> <span data-ttu-id="96b0c-330">パブリック HRESULT [add_WebResourceRequested](#add_webresourcerequested)([ICoreWebView2WebResourceRequestedEventHandler](icorewebview2webresourcerequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-330">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)([ICoreWebView2WebResourceRequestedEventHandler](icorewebview2webresourcerequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-331">WebResourceRequested は、AddWebResourceRequestedFilter によって追加された、一致する URL とリソースコンテキストフィルターへの URL 要求を実行しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-331">WebResourceRequested fires when the WebView is performing a URL request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span> <span data-ttu-id="96b0c-332">イベントを発生させるには、少なくとも1つのフィルターを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-332">At least one filter must be added for the event to fire.</span></span>

<span data-ttu-id="96b0c-333">要求された web リソースは、イベント引数で遅延が発生しなかった場合に、イベントハンドラーから制御が返されるまでブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-333">The web resource requested can be blocked until the event handler returns if a deferral is not taken on the event args.</span></span> <span data-ttu-id="96b0c-334">延期が行われた場合、保留が完了するまで、要求された web リソースはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-334">If a deferral is taken, then the web resource requested is blocked until the deferral is completed.</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        COREWEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<ICoreWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### <span data-ttu-id="96b0c-335">add_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-335">add_WindowCloseRequested</span></span> 

<span data-ttu-id="96b0c-336">WindowCloseRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-336">Add an event handler for the WindowCloseRequested event.</span></span>

> <span data-ttu-id="96b0c-337">パブリック HRESULT [add_WindowCloseRequested](#add_windowcloserequested)([ICoreWebView2WindowCloseRequestedEventHandler](icorewebview2windowcloserequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-337">public HRESULT [add_WindowCloseRequested](#add_windowcloserequested)([ICoreWebView2WindowCloseRequestedEventHandler](icorewebview2windowcloserequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="96b0c-338">WindowCloseRequested が呼び出された後など、WebView 内のコンテンツがウィンドウを閉じる必要がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-338">WindowCloseRequested fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span> <span data-ttu-id="96b0c-339">アプリが適切である場合は、アプリで WebView と関連するアプリのウィンドウを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-339">The app should close the WebView and related app window if that makes sense to the app.</span></span>

```cpp
    // Register a handler for the WindowCloseRequested event.
    // This handler will close the app window if it is not the main window.
    CHECK_FAILURE(m_webView->add_WindowCloseRequested(
        Callback<ICoreWebView2WindowCloseRequestedEventHandler>([this](
                                                                    ICoreWebView2* sender,
                                                                    IUnknown* args) {
            if (m_isPopupWindow)
            {
                CloseAppWindow();
            }
            return S_OK;
        }).Get(),
        nullptr));
```

#### <span data-ttu-id="96b0c-340">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="96b0c-340">AddHostObjectToScript</span></span> 

<span data-ttu-id="96b0c-341">指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-341">Add the provided host object to script running in the WebView with the specified name.</span></span>

> <span data-ttu-id="96b0c-342">パブリック HRESULT [Addhostobjecttoscript](#addhostobjecttoscript)(LPCWSTR NAME, VARIANT \* object)</span><span class="sxs-lookup"><span data-stu-id="96b0c-342">public HRESULT [AddHostObjectToScript](#addhostobjecttoscript)(LPCWSTR name, VARIANT \* object)</span></span>

<span data-ttu-id="96b0c-343">ホストオブジェクトは、でホストオブジェクトプロキシとして公開され `window.chrome.webview.hostObjects.<name>` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-343">Host objects are exposed as host object proxies via `window.chrome.webview.hostObjects.<name>`.</span></span> <span data-ttu-id="96b0c-344">ホストオブジェクトプロキシは保証され、ホストオブジェクトを表すオブジェクトに解決されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-344">Host object proxies are promises and will resolve to an object representing the host object.</span></span> <span data-ttu-id="96b0c-345">アプリが名前付きのオブジェクトを追加していない場合、promise は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-345">The promise is rejected if the app has not added an object with the name.</span></span> <span data-ttu-id="96b0c-346">JavaScript コードがオブジェクトのプロパティまたはメソッドにアクセスする場合、promise が返されます。これは、ホストからプロパティやメソッドに対して返された値に解決されます。また、オブジェクトやパラメーターのプロパティやメソッドが無効であるなどのエラーが発生した場合には拒否されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-346">When JavaScript code access a property or method of the object, a promise is return, which will resolve to the value returned from the host for the property or method, or rejected in case of error such as there is no such property or method on the object or parameters are invalid.</span></span> <span data-ttu-id="96b0c-347">たとえば、次のようなアプリケーションコードを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="96b0c-347">For example, when the application code does the following:</span></span>

```
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddHostObjectToScript(L"host_object", &host);
```

<span data-ttu-id="96b0c-348">WebView の JavaScript コードは、appObject に次の方法でアクセスして、appObject の属性とメソッドにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-348">JavaScript code in the WebView will be able to access appObject as following and then access attributes and methods of appObject:</span></span>

```
let app_object = await window.chrome.webview.hostObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

<span data-ttu-id="96b0c-349">単純型、IDispatch、配列はサポートされていますが、ジェネリック IUnknown、VT_DECIMAL、または VT_RECORD variant はサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="96b0c-349">Note that while simple types, IDispatch and array are supported, generic IUnknown, VT_DECIMAL, or VT_RECORD variant is not supported.</span></span> <span data-ttu-id="96b0c-350">コールバック関数などのリモート JavaScript オブジェクトは、IDispatch を実装するオブジェクトと共に VT_DISPATCH VARIANT として表されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-350">Remote JavaScript objects like callback functions are represented as an VT_DISPATCH VARIANT with the object implementing IDispatch.</span></span> <span data-ttu-id="96b0c-351">JavaScript のコールバックメソッドは、DISPID の DISPID_VALUE を使って呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-351">The JavaScript callback method may be invoked using DISPID_VALUE for the DISPID.</span></span> <span data-ttu-id="96b0c-352">入れ子になった配列は、最大3レベルまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-352">Nested arrays are supported up to a depth of 3.</span></span> <span data-ttu-id="96b0c-353">参照型での配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-353">Arrays of by reference types are not supported.</span></span> <span data-ttu-id="96b0c-354">VT_EMPTY と VT_NULL は JavaScript に NULL としてマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-354">VT_EMPTY and VT_NULL are mapped into JavaScript as null.</span></span> <span data-ttu-id="96b0c-355">JavaScript は null で、undefined は VT_EMPTY にマップされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-355">In JavaScript null and undefined are mapped to VT_EMPTY.</span></span>

<span data-ttu-id="96b0c-356">さらに、すべてのホストオブジェクトがとして公開され `window.chrome.webview.hostObjects.sync.<name>` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-356">Additionally, all host objects are exposed as `window.chrome.webview.hostObjects.sync.<name>`.</span></span> <span data-ttu-id="96b0c-357">ここでは、ホストオブジェクトが同期ホストオブジェクトプロキシとして公開されています。</span><span class="sxs-lookup"><span data-stu-id="96b0c-357">Here the host objects are exposed as synchronous host object proxies.</span></span> <span data-ttu-id="96b0c-358">これらは、ホストコードが実行されるためのクロスプロセスとの通信を待機している、実行中のスクリプトの実行を待機していて、機能やプロパティへのアクセスを同期することはできません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-358">These are not promises and calls to functions or property access synchronously block running script waiting to communicate cross process for the host code to run.</span></span> <span data-ttu-id="96b0c-359">これにより、信頼性の問題が発生する可能性があり、上記で説明した promise ベースの非同期 API を使うことをお勧めし `window.chrome.webview.hostObjects.<name>` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-359">Accordingly this can result in reliability issues and it is recommended that you use the promise based asynchronous `window.chrome.webview.hostObjects.<name>` API described above.</span></span>

<span data-ttu-id="96b0c-360">同期ホストオブジェクトプロキシと非同期ホストオブジェクトプロキシは、どちらも同じホストオブジェクトをプロキシすることができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-360">Synchronous host object proxies and asynchronous host object proxies can both proxy the same host object.</span></span> <span data-ttu-id="96b0c-361">1つのプロキシによって加えられたリモートの変更は、他のプロキシと同期か非同期かにかかわらず、同じホストオブジェクトの他のプロキシにも反映されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-361">Remote changes made by one proxy will be reflected in any other proxy of that same host object whether the other proxies and synchronous or asynchronous.</span></span>

<span data-ttu-id="96b0c-362">JavaScript はネイティブコードへの同期呼び出しでブロックされますが、ネイティブコードは JavaScript にコールバックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-362">While JavaScript is blocked on a synchronous call to native code, that native code is unable to call back to JavaScript.</span></span> <span data-ttu-id="96b0c-363">これを実行しようとすると、HRESULT_FROM_WIN32 (ERROR_POSSIBLE_DEADLOCK) で失敗します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-363">Attempts to do so will fail with HRESULT_FROM_WIN32(ERROR_POSSIBLE_DEADLOCK).</span></span>

<span data-ttu-id="96b0c-364">ホストオブジェクトプロキシは、すべてのプロパティ get、プロパティセット、メソッド呼び出しを受け取る JavaScript プロキシオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="96b0c-364">Host object proxies are JavaScript Proxy objects that intercept all property get, property set, and method invocations.</span></span> <span data-ttu-id="96b0c-365">関数またはオブジェクトプロトタイプの一部であるプロパティまたはメソッドはローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-365">Properties or methods that are a part of the Function or Object prototype are run locally.</span></span> <span data-ttu-id="96b0c-366">さらに、配列内のすべてのプロパティまたはメソッド `chrome.webview.hostObjects.options.forceLocalProperties` もローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-366">Additionally any property or method in the array `chrome.webview.hostObjects.options.forceLocalProperties` will also be run locally.</span></span> <span data-ttu-id="96b0c-367">これは既定で、JavaScript のような、というようなオプションのメソッドが含まれてい `toJSON` `Symbol.toPrimitive` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-367">This defaults to including optional methods that have meaning in JavaScript like `toJSON` and `Symbol.toPrimitive`.</span></span> <span data-ttu-id="96b0c-368">必要に応じて、この配列に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-368">You can add more to this array as required.</span></span>

<span data-ttu-id="96b0c-369">最善の手段と `chrome.webview.hostObjects.cleanupSome` して、ガベージコレクションのホストオブジェクトプロキシを収集する方法があります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-369">There's a method `chrome.webview.hostObjects.cleanupSome` that will best effort garbage collect host object proxies.</span></span>

<span data-ttu-id="96b0c-370">ホストオブジェクトプロキシには、ローカルで実行される次のメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-370">Host object proxies additionally have the following methods which run locally:</span></span>

* <span data-ttu-id="96b0c-371">applyHostFunction、getHostProperty、setHostProperty: ホストオブジェクトでメソッドの呼び出し、プロパティの取得、プロパティの設定を実行します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-371">applyHostFunction, getHostProperty, setHostProperty: Perform a method invocation, property get, or property set on the host object.</span></span> <span data-ttu-id="96b0c-372">これらのメソッドを使うと、競合するローカルメソッドまたはプロパティがある場合に、メソッドまたはプロパティを明示的に強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-372">You can use these to explicitly force a method or property to run remotely if there is a conflicting local method or property.</span></span> <span data-ttu-id="96b0c-373">たとえば、 `proxy.toString()` はプロキシオブジェクトに対してローカル toString メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-373">For instance, `proxy.toString()` will run the local toString method on the proxy object.</span></span> <span data-ttu-id="96b0c-374">ただし `proxy.applyHostFunction('toString')` `toString` 、代わりに host プロキシオブジェクトで実行されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-374">But `proxy.applyHostFunction('toString')` runs `toString` on the host proxied object instead.</span></span>

* <span data-ttu-id="96b0c-375">getLocalProperty、setLocalProperty: プロパティ get、またはローカルにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-375">getLocalProperty, setLocalProperty: Perform property get, or property set locally.</span></span> <span data-ttu-id="96b0c-376">これらのメソッドを使うと、ホストオブジェクトプロキシ自体でプロパティを取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-376">You can use these methods to force getting or setting a property on the host object proxy itself rather than on the host object it represents.</span></span> <span data-ttu-id="96b0c-377">たとえば、 `proxy.unknownProperty` は、host プロキシオブジェクトから名前が付けられたプロパティを取得し `unknownProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-377">For instance, `proxy.unknownProperty` will get the property named `unknownProperty` from the host proxied object.</span></span> <span data-ttu-id="96b0c-378">ただし、この `proxy.getLocalProperty('unknownProperty')` プロパティの値は `unknownProperty` プロキシオブジェクト自体で取得されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-378">But `proxy.getLocalProperty('unknownProperty')` will get the value of the property `unknownProperty` on the proxy object itself.</span></span>

* <span data-ttu-id="96b0c-379">同期: 非同期ホストオブジェクトプロキシは、同じホストオブジェクトの同期ホストオブジェクトプロキシの promise を返す同期メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-379">sync: Asynchronous host object proxies expose a sync method which returns a promise for a synchronous host object proxy for the same host object.</span></span> <span data-ttu-id="96b0c-380">たとえば、 `chrome.webview.hostObjects.sample.methodCall()` 非同期ホストオブジェクトプロキシを返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-380">For example, `chrome.webview.hostObjects.sample.methodCall()` returns an asynchronous host object proxy.</span></span> <span data-ttu-id="96b0c-381">代わりに、メソッドを使用して `sync` 同期ホストオブジェクトプロキシを取得できます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-381">You can use the `sync` method to obtain a synchronous host object proxy instead:</span></span> `const syncProxy = await chrome.webview.hostObjects.sample.methodCall().sync()`

* <span data-ttu-id="96b0c-382">非同期: 同期ホストオブジェクトプロキシは、同じホストオブジェクトの非同期ホストオブジェクトプロキシをブロックして返す async メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-382">async: Synchronous host object proxies expose an async method which blocks and returns an asynchronous host object proxy for the same host object.</span></span> <span data-ttu-id="96b0c-383">たとえば、 `chrome.webview.hostObjects.sync.sample.methodCall()` 同期ホストオブジェクトプロキシを返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-383">For example, `chrome.webview.hostObjects.sync.sample.methodCall()` returns a synchronous host object proxy.</span></span> <span data-ttu-id="96b0c-384">このブロックに対してメソッドを呼び出す `async` と、同じホストオブジェクトの非同期ホストオブジェクトプロキシが返されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-384">Calling the `async` method on this blocks and then returns an asynchronous host object proxy for the same host object:</span></span> `const asyncProxy = chrome.webview.hostObjects.sync.sample.methodCall().async()`

* <span data-ttu-id="96b0c-385">次に、非同期ホストオブジェクトプロキシには then メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-385">then: Asynchronous host object proxies have a then method.</span></span> <span data-ttu-id="96b0c-386">これにより、awaitable を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-386">This allows them to be awaitable.</span></span> `then` <span data-ttu-id="96b0c-387">は、host オブジェクトの表現によって解決される promise を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-387">will return a promise that resolves with a representation of the host object.</span></span> <span data-ttu-id="96b0c-388">プロキシが JavaScript リテラルを表す場合は、そのリテラルのコピーがローカルに返されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-388">If the proxy represents a JavaScript literal then a copy of that is returned locally.</span></span> <span data-ttu-id="96b0c-389">プロキシが関数を表す場合は、awaitable 以外のプロキシが返されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-389">If the proxy represents a function then a non-awaitable proxy is returned.</span></span> <span data-ttu-id="96b0c-390">プロキシがリテラルプロパティと関数プロパティが混在した JavaScript オブジェクトを表している場合、オブジェクトのコピーが、一部のプロパティをホストオブジェクトプロキシとして返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-390">If the proxy represents a JavaScript object with a mix of literal properties and function properties, then the a copy of the object is returned with some properties as host object proxies.</span></span>

<span data-ttu-id="96b0c-391">その他のすべてのプロパティとメソッドの呼び出し (上記のリモートオブジェクトプロキシメソッド、forceLocalProperties リスト、関数およびオブジェクトプロトタイプのプロパティ以外) は、リモートで実行されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-391">All other property and method invocations (other than the above Remote object proxy methods, forceLocalProperties list, and properties on Function and Object prototypes) are run remotely.</span></span> <span data-ttu-id="96b0c-392">非同期ホストオブジェクトプロキシは、メソッドのリモート呼び出しまたはプロパティの取得の非同期完了を表す promise を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-392">Asynchronous host object proxies return a promise representing asynchronous completion of remotely invoking the method, or getting the property.</span></span> <span data-ttu-id="96b0c-393">この保証は、リモート操作が完了した後に解決され、その約束が、演算の結果値に解決されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-393">The promise resolves after the remote operations complete and the promises resolve to the resulting value of the operation.</span></span> <span data-ttu-id="96b0c-394">同期ホストオブジェクトプロキシは、同じように動作しますが、JavaScript の実行をブロックし、リモート操作が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-394">Synchronous host object proxies work similarly but block JavaScript execution and wait for the remote operation to complete.</span></span>

<span data-ttu-id="96b0c-395">非同期ホストオブジェクトプロキシのプロパティの設定は、若干異なります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-395">Setting a property on an asynchronous host object proxy works slightly differently.</span></span> <span data-ttu-id="96b0c-396">Set はすぐに戻り値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-396">The set returns immediately and the return value is the value that will be set.</span></span> <span data-ttu-id="96b0c-397">これは JavaScript プロキシオブジェクトの要件です。</span><span class="sxs-lookup"><span data-stu-id="96b0c-397">This is a requirement of the JavaScript Proxy object.</span></span> <span data-ttu-id="96b0c-398">プロパティセットが完了するのを非同期的に待つ必要がある場合は、上記のように、setHostProperty メソッドを使って、promise を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-398">If you need to asynchronously wait for the property set to complete, use the setHostProperty method which returns a promise as described above.</span></span> <span data-ttu-id="96b0c-399">同期オブジェクトプロパティセットプロパティは、プロパティが設定されるまで同期的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-399">Synchronous object property set property synchronously blocks until the property is set.</span></span>

<span data-ttu-id="96b0c-400">たとえば、次のインターフェイスを持つ COM オブジェクトがあるとします。</span><span class="sxs-lookup"><span data-stu-id="96b0c-400">For example, suppose you have a COM object with the following interface</span></span>

```idl
    [uuid(3a14c9c0-bc3e-453f-a314-4ce4a0ec81d8), object, local]
    interface IHostObjectSample : IUnknown
    {
        // Demonstrate basic method call with some parameters and a return value.
        HRESULT MethodWithParametersAndReturnValue([in] BSTR stringParameter, [in] INT integerParameter, [out, retval] BSTR* stringResult);

        // Demonstrate getting and setting a property.
        [propget] HRESULT Property([out, retval] BSTR* stringResult);
        [propput] HRESULT Property([in] BSTR stringValue);

        [propget] HRESULT IndexedProperty(INT index, [out, retval] BSTR * stringResult);
        [propput] HRESULT IndexedProperty(INT index, [in] BSTR stringValue);

        // Demonstrate native calling back into JavaScript.
        HRESULT CallCallbackAsynchronously([in] IDispatch* callbackParameter);

    };
```
 <span data-ttu-id="96b0c-401">このインターフェイスのインスタンスは、の JavaScript に追加することができ `AddHostObjectToScript` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-401">We can add an instance of this interface into our JavaScript with `AddHostObjectToScript`.</span></span> <span data-ttu-id="96b0c-402">この場合は、次のように名前を指定し `sample` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-402">In this case we name it `sample`:</span></span>

```cpp
            VARIANT remoteObjectAsVariant = {};
            m_hostObject.query_to<IDispatch>(&remoteObjectAsVariant.pdispVal);
            remoteObjectAsVariant.vt = VT_DISPATCH;

            // We can call AddHostObjectToScript multiple times in a row without
            // calling RemoveHostObject first. This will replace the previous object
            // with the new object. In our case this is the same object and everything
            // is fine.
            CHECK_FAILURE(
                m_webView->AddHostObjectToScript(L"sample", &remoteObjectAsVariant));
            remoteObjectAsVariant.pdispVal->Release();
```
 <span data-ttu-id="96b0c-403">HTML 文書では、次の方法でこの COM オブジェクトを使うことができ `chrome.webview.hostObjects.sample` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-403">Then in the HTML document we can use this COM object via `chrome.webview.hostObjects.sample`:</span></span>

```html
        document.getElementById("getPropertyAsyncButton").addEventListener("click", async () => {
        const propertyValue = await chrome.webview.hostObjects.sample.property;
        document.getElementById("getPropertyAsyncOutput").textContent = propertyValue;
        });

        document.getElementById("getPropertySyncButton").addEventListener("click", () => {
        const propertyValue = chrome.webview.hostObjects.sync.sample.property;
        document.getElementById("getPropertySyncOutput").textContent = propertyValue;
        });

        document.getElementById("setPropertyAsyncButton").addEventListener("click", async () => {
        const propertyValue = document.getElementById("setPropertyAsyncInput").value;
        // The following line will work but it will return immediately before the property value has actually been set.
        // If you need to set the property and wait for the property to change value, use the setHostProperty function.
        chrome.webview.hostObjects.sample.property = propertyValue;
        document.getElementById("setPropertyAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertyExplicitAsyncButton").addEventListener("click", async () => {
        const propertyValue = document.getElementById("setPropertyExplicitAsyncInput").value;
        // If you care about waiting until the property has actually changed value use the setHostProperty function.
        await chrome.webview.hostObjects.sample.setHostProperty("property", propertyValue);
        document.getElementById("setPropertyExplicitAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertySyncButton").addEventListener("click", () => {
        const propertyValue = document.getElementById("setPropertySyncInput").value;
        chrome.webview.hostObjects.sync.sample.property = propertyValue;
        document.getElementById("setPropertySyncOutput").textContent = "Set";
        });

        document.getElementById("getIndexedPropertyAsyncButton").addEventListener("click", async () => {
        const index = parseInt(document.getElementById("getIndexedPropertyAsyncParam").value);
        const resultValue = await chrome.webview.hostObjects.sample.IndexedProperty[index];
        document.getElementById("getIndexedPropertyAsyncOutput").textContent = resultValue;
        });
        document.getElementById("setIndexedPropertyAsyncButton").addEventListener("click", async () => {
        const index = parseInt(document.getElementById("setIndexedPropertyAsyncParam1").value);
        const value = document.getElementById("setIndexedPropertyAsyncParam2").value;;
        chrome.webview.hostObjects.sample.IndexedProperty[index] = value;
        document.getElementById("setIndexedPropertyAsyncOutput").textContent = "Set";
        });
        document.getElementById("invokeMethodAsyncButton").addEventListener("click", async () => {
        const paramValue1 = document.getElementById("invokeMethodAsyncParam1").value;
        const paramValue2 = parseInt(document.getElementById("invokeMethodAsyncParam2").value);
        const resultValue = await chrome.webview.hostObjects.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
        document.getElementById("invokeMethodAsyncOutput").textContent = resultValue;
        });

        document.getElementById("invokeMethodSyncButton").addEventListener("click", () => {
        const paramValue1 = document.getElementById("invokeMethodSyncParam1").value;
        const paramValue2 = parseInt(document.getElementById("invokeMethodSyncParam2").value);
        const resultValue = chrome.webview.hostObjects.sync.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
        document.getElementById("invokeMethodSyncOutput").textContent = resultValue;
        });

        let callbackCount = 0;
        document.getElementById("invokeCallbackButton").addEventListener("click", async () => {
        chrome.webview.hostObjects.sample.CallCallbackAsynchronously(() => {
        document.getElementById("invokeCallbackOutput").textContent = "Native object called the callback " + (++callbackCount) + " time(s).";
        });
        });
```
<span data-ttu-id="96b0c-404">スクリプトにホストオブジェクトを公開すると、セキュリティ上のリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-404">Exposing host objects to script has security risk.</span></span> <span data-ttu-id="96b0c-405">[ベストプラクティス](https://docs.microsoft.com/microsoft-edge/webview2/concepts/security)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="96b0c-405">Please follow [best practices](https://docs.microsoft.com/microsoft-edge/webview2/concepts/security).</span></span>

#### <span data-ttu-id="96b0c-406">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="96b0c-406">AddScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="96b0c-407">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-407">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="96b0c-408">パブリック HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR JavaScript、 [ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](icorewebview2addscripttoexecuteondocumentcreatedcompletedhandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="96b0c-408">public HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR javaScript, [ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](icorewebview2addscripttoexecuteondocumentcreatedcompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="96b0c-409">このメソッドは、すべてのトップレベルのドキュメントと子フレームのページナビゲーションで実行されるスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-409">This method injects a script that runs on all top-level document and child frame page navigations.</span></span> <span data-ttu-id="96b0c-410">このメソッドは非同期的に実行されるため、挿入されたスクリプトを実行できるようになるには、完了ハンドラーが終了するまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-410">This method runs asynchronously, and you must wait for the completion handler to finish before the injected script is ready to run.</span></span> <span data-ttu-id="96b0c-411">このメソッドが完了すると、ハンドラーの `Invoke` メソッドが、挿入されたスクリプトので呼び出され `id` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-411">When this method completes, the handler's `Invoke` method is called with the `id` of the injected script.</span></span> `id` <span data-ttu-id="96b0c-412">は文字列です。</span><span class="sxs-lookup"><span data-stu-id="96b0c-412">is a string.</span></span> <span data-ttu-id="96b0c-413">挿入されたスクリプトを削除するには、を使用 `RemoveScriptToExecuteOnDocumentCreated` します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-413">To remove the injected script, use `RemoveScriptToExecuteOnDocumentCreated`.</span></span>

<span data-ttu-id="96b0c-414">[サンドボックス](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)のプロパティまたは[コンテンツセキュリティポリシーの HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)によって、HTML ドキュメントに何らかのサンドボックスが含まれている場合は、このスクリプトの実行に影響します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-414">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="96b0c-415">たとえば、' allow als ' キーワードが設定されていない場合、関数への呼び出し `alert` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-415">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

```cpp
// Prompt the user for some script and register it to execute whenever a new page loads.
void ScriptComponent::AddInitializeScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Add Initialize Script",
        L"Initialization Script:",
        L"Enter the JavaScript code to run as the initialization script that "
            L"runs before any script in the HTML document.",
    // This example script stops child frames from opening new windows.  Because
    // the initialization script runs before any script in the HTML document, we
    // can trust the results of our checks on window.parent and window.top.
        L"if (window.parent !== window.top) {\r\n"
        L"    delete window.open;\r\n"
        L"}");
    if (dialog.confirmed)
    {
        m_webView->AddScriptToExecuteOnDocumentCreated(
            dialog.input.c_str(),
            Callback<ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### <span data-ttu-id="96b0c-416">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="96b0c-416">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="96b0c-417">URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-417">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="96b0c-418">パブリック HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri、 [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="96b0c-418">public HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri, [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="96b0c-419">URI パラメーターには、ワイルドカード文字列 (' \* '、0以上、'? ': まったく1つ) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-419">The URI parameter can be a wildcard string ('\*': zero or more, '?': exactly one).</span></span> <span data-ttu-id="96b0c-420">nullptr は、L "" と同じです。</span><span class="sxs-lookup"><span data-stu-id="96b0c-420">nullptr is equivalent to L"".</span></span> <span data-ttu-id="96b0c-421">リソースコンテキストフィルターの説明については、「enum の COREWEBVIEW2_WEB_RESOURCE_CONTEXT」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96b0c-421">See COREWEBVIEW2_WEB_RESOURCE_CONTEXT enum for description of resource context filters.</span></span>

#### <span data-ttu-id="96b0c-422">Calldevon Protocolメソッド</span><span class="sxs-lookup"><span data-stu-id="96b0c-422">CallDevToolsProtocolMethod</span></span> 

<span data-ttu-id="96b0c-423">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-423">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="96b0c-424">パブリック HRESULT [呼び出し DevLPCWSTR Protocolmethod](#calldevtoolsprotocolmethod)(METHODNAME、LPCWSTR ParametersAsJson、 [ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](icorewebview2calldevtoolsprotocolmethodcompletedhandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="96b0c-424">public HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)(LPCWSTR methodName, LPCWSTR parametersAsJson, [ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](icorewebview2calldevtoolsprotocolmethodcompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="96b0c-425">使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="96b0c-425">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="96b0c-426">MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="96b0c-426">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="96b0c-427">ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。</span><span class="sxs-lookup"><span data-stu-id="96b0c-427">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="96b0c-428">メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-428">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="96b0c-429">Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-429">Invoke will be called with the method's return object as a JSON string.</span></span>

```cpp
// Prompt the user for the name and parameters of a CDP method, then call it.
void ScriptComponent::CallCdpMethod()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Call CDP Method",
        L"CDP method name:",
        L"Enter the CDP method name to call, followed by a space,\r\n"
            L"followed by the parameters in JSON format.",
        L"Runtime.evaluate {\"expression\":\"alert(\\\"test\\\")\"}");
    if (dialog.confirmed)
    {
        size_t delimiterPos = dialog.input.find(L' ');
        std::wstring methodName = dialog.input.substr(0, delimiterPos);
        std::wstring methodParams =
            (delimiterPos < dialog.input.size()
                ? dialog.input.substr(delimiterPos + 1)
                : L"{}");

        m_webView->CallDevToolsProtocolMethod(
            methodName.c_str(),
            methodParams.c_str(),
            Callback<ICoreWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### <span data-ttu-id="96b0c-430">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="96b0c-430">CapturePreview</span></span> 

<span data-ttu-id="96b0c-431">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="96b0c-431">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="96b0c-432">パブリック HRESULT [CapturePreview](#capturepreview)([COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format) imageformat、IStream \* imagestream、 [ICoreWebView2CapturePreviewCompletedHandler](icorewebview2capturepreviewcompletedhandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="96b0c-432">public HRESULT [CapturePreview](#capturepreview)([COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format) imageFormat, IStream \* imageStream, [ICoreWebView2CapturePreviewCompletedHandler](icorewebview2capturepreviewcompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="96b0c-433">ImageFormat パラメーターを使用して、画像の形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-433">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="96b0c-434">結果のイメージバイナリデータは、指定された imageStream パラメーターに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-434">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="96b0c-435">CapturePreview がストリームへの書き込みを終了すると、指定された handler パラメーターの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-435">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

```cpp
// Show the user a file selection dialog, then save a screenshot of the WebView
// to the selected file.
void FileComponent::SaveScreenshot()
{
    OPENFILENAME openFileName = {};
    openFileName.lStructSize = sizeof(openFileName);
    openFileName.hwndOwner = nullptr;
    openFileName.hInstance = nullptr;
    WCHAR fileName[MAX_PATH] = L"WebView2_Screenshot.png";
    openFileName.lpstrFile = fileName;
    openFileName.lpstrFilter = L"PNG File\0*.png\0";
    openFileName.nMaxFile = ARRAYSIZE(fileName);
    openFileName.Flags = OFN_OVERWRITEPROMPT;

    if (GetSaveFileName(&openFileName))
    {
        wil::com_ptr<IStream> stream;
        CHECK_FAILURE(SHCreateStreamOnFileEx(
            fileName, STGM_READWRITE | STGM_CREATE, FILE_ATTRIBUTE_NORMAL, TRUE, nullptr,
            &stream));

        HWND mainWindow = m_appWindow->GetMainWindow();

        CHECK_FAILURE(m_webView->CapturePreview(
            COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<ICoreWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### <span data-ttu-id="96b0c-436">Execuスクリプト</span><span class="sxs-lookup"><span data-stu-id="96b0c-436">ExecuteScript</span></span> 

<span data-ttu-id="96b0c-437">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-437">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="96b0c-438">パブリック HRESULT の [Executescript](#executescript)(LPCWSTR JavaScript、 [ICoreWebView2ExecuteScriptCompletedHandler](icorewebview2executescriptcompletedhandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="96b0c-438">public HRESULT [ExecuteScript](#executescript)(LPCWSTR javaScript, [ICoreWebView2ExecuteScriptCompletedHandler](icorewebview2executescriptcompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="96b0c-439">これは非同期的に実行されます。完了すると、ExecuteScriptCompletedHandler パラメーターでハンドラーが指定されると、指定された JavaScript を評価した結果を使って Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-439">This will execute asynchronously and when complete, if a handler is provided in the ExecuteScriptCompletedHandler parameter, its Invoke method will be called with the result of evaluating the provided JavaScript.</span></span> <span data-ttu-id="96b0c-440">結果値は、JSON でエンコードされた文字列です。</span><span class="sxs-lookup"><span data-stu-id="96b0c-440">The result value is a JSON encoded string.</span></span> <span data-ttu-id="96b0c-441">結果が定義されていない場合、参照循環が含まれている場合、または JSON にエンコードできない場合は、JSON null 値が文字列 ' null ' として返されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-441">If the result is undefined, contains a reference cycle, or otherwise cannot be encoded into JSON, the JSON null value will be returned as the string 'null'.</span></span> <span data-ttu-id="96b0c-442">明示的な戻り値のない関数は undefined を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-442">Note that a function that has no explicit return value returns undefined.</span></span> <span data-ttu-id="96b0c-443">実行されたスクリプトが未処理の例外をスローした場合、結果は ' null ' にもなります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-443">If the executed script throws an unhandled exception, then the result is also 'null'.</span></span> <span data-ttu-id="96b0c-444">このメソッドは非同期的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-444">This method is applied asynchronously.</span></span> <span data-ttu-id="96b0c-445">ナビゲーション中に、メソッドが NavigationStarting イベントの後で呼び出される場合、スクリプトは、コンテンツの読み込み時に新しいドキュメントで実行されます。これは、ContentLoading が呼び出されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-445">If the method is called after NavigationStarting event during a navigation, the script will be executed in the new document when loading it, around the time ContentLoading is fired.</span></span> <span data-ttu-id="96b0c-446">ExecuICoreWebView2Settings:: IsScriptEnabled が FALSE に設定されている場合でも動作します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-446">ExecuteScript will work even if ICoreWebView2Settings::IsScriptEnabled is set to FALSE.</span></span>

```cpp
// Prompt the user for some script and then execute it.
void ScriptComponent::InjectScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Inject Script",
        L"Enter script code:",
        L"Enter the JavaScript code to run in the webview.",
        L"window.getComputedStyle(document.body).backgroundColor");
    if (dialog.confirmed)
    {
        m_webView->ExecuteScript(dialog.input.c_str(),
            Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
                [](HRESULT error, PCWSTR result) -> HRESULT
        {
            if (error != S_OK) {
                ShowFailure(error, L"ExecuteScript failed");
            }
            MessageBox(nullptr, result, L"ExecuteScript Result", MB_OK);
            return S_OK;
        }).Get());
    }
}
```

#### <span data-ttu-id="96b0c-447">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="96b0c-447">get_BrowserProcessId</span></span> 

<span data-ttu-id="96b0c-448">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="96b0c-448">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="96b0c-449">パブリック HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* 値)</span><span class="sxs-lookup"><span data-stu-id="96b0c-449">public HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* value)</span></span>

#### <span data-ttu-id="96b0c-450">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="96b0c-450">get_CanGoBack</span></span> 

<span data-ttu-id="96b0c-451">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-451">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="96b0c-452">パブリック HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* CanGoBack)</span><span class="sxs-lookup"><span data-stu-id="96b0c-452">public HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* canGoBack)</span></span>

<span data-ttu-id="96b0c-453">CanGoBack の値が変更されると、履歴変更イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-453">The HistoryChanged event will fire if CanGoBack changes value.</span></span>

#### <span data-ttu-id="96b0c-454">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="96b0c-454">get_CanGoForward</span></span> 

<span data-ttu-id="96b0c-455">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-455">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="96b0c-456">パブリック HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* CanGoForward)</span><span class="sxs-lookup"><span data-stu-id="96b0c-456">public HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* canGoForward)</span></span>

<span data-ttu-id="96b0c-457">CanGoForward の値が変更されると、履歴変更イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-457">The HistoryChanged event will fire if CanGoForward changes value.</span></span>

#### <span data-ttu-id="96b0c-458">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="96b0c-458">get_ContainsFullScreenElement</span></span> 

<span data-ttu-id="96b0c-459">WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-459">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="96b0c-460">パブリック HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL \* Fullfullscreenelement)</span><span class="sxs-lookup"><span data-stu-id="96b0c-460">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL \* containsFullScreenElement)</span></span>

#### <span data-ttu-id="96b0c-461">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="96b0c-461">get_DocumentTitle</span></span> 

<span data-ttu-id="96b0c-462">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="96b0c-462">The title for the current top level document.</span></span>

> <span data-ttu-id="96b0c-463">パブリック HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span><span class="sxs-lookup"><span data-stu-id="96b0c-463">public HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span></span>

<span data-ttu-id="96b0c-464">ドキュメントに明示的なタイトルが含まれていない場合、または空の場合は、ドキュメントの URI と一致しないかもしれない既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-464">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

#### <span data-ttu-id="96b0c-465">get_Settings</span><span class="sxs-lookup"><span data-stu-id="96b0c-465">get_Settings</span></span> 

<span data-ttu-id="96b0c-466">[ICoreWebView2Settings](icorewebview2settings.md)オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96b0c-466">The [ICoreWebView2Settings](icorewebview2settings.md) object contains various modifiable settings for the running WebView.</span></span>

> <span data-ttu-id="96b0c-467">パブリック HRESULT [get_Settings](#get_settings)([ICoreWebView2Settings](icorewebview2settings.md) \* \* 設定)</span><span class="sxs-lookup"><span data-stu-id="96b0c-467">public HRESULT [get_Settings](#get_settings)([ICoreWebView2Settings](icorewebview2settings.md) \*\* settings)</span></span>

#### <span data-ttu-id="96b0c-468">get_Source</span><span class="sxs-lookup"><span data-stu-id="96b0c-468">get_Source</span></span> 

<span data-ttu-id="96b0c-469">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="96b0c-469">The URI of the current top level document.</span></span>

> <span data-ttu-id="96b0c-470">パブリック HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span><span class="sxs-lookup"><span data-stu-id="96b0c-470">public HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span></span>

<span data-ttu-id="96b0c-471">この値は、別のサイトやフラグメントナビゲーションへの移動などの場合に、SourceChanged イベント発生の一部として変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-471">This value potentially changes as a part of the SourceChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="96b0c-472">ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションにも同じように表示されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-472">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

```cpp
    // Register a handler for the SourceChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_SourceChanged(
        Callback<ICoreWebView2SourceChangedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2SourceChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(GetAddressBar(), uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### <span data-ttu-id="96b0c-473">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="96b0c-473">GetDevToolsProtocolEventReceiver</span></span> 

<span data-ttu-id="96b0c-474">DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-474">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>

> <span data-ttu-id="96b0c-475">パブリック HRESULT [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(LPCWSTR EventName, [ICoreWebView2DevToolsProtocolEventReceiver](icorewebview2devtoolsprotocoleventreceiver.md) \* \* レシーバー)</span><span class="sxs-lookup"><span data-stu-id="96b0c-475">public HRESULT [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(LPCWSTR eventName, [ICoreWebView2DevToolsProtocolEventReceiver](icorewebview2devtoolsprotocoleventreceiver.md) \*\* receiver)</span></span>

<span data-ttu-id="96b0c-476">EventName パラメーターは、形式におけるイベントの完全な名前です `{domain}.{event}` 。</span><span class="sxs-lookup"><span data-stu-id="96b0c-476">The eventName parameter is the full name of the event in the format `{domain}.{event}`.</span></span> <span data-ttu-id="96b0c-477">Devtools プロトコル [ビューアー](https://aka.ms/DevToolsProtocolDocs) を参照して、devtools プロトコルイベントの説明とイベント引数の一覧を確認してください。</span><span class="sxs-lookup"><span data-stu-id="96b0c-477">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list of DevTools Protocol events description, and event args.</span></span>

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        wil::com_ptr<ICoreWebView2DevToolsProtocolEventReceiver> receiver;
        CHECK_FAILURE(
            m_webView->GetDevToolsProtocolEventReceiver(eventName.c_str(), &receiver));

        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(receiver->remove_DevToolsProtocolEventReceived(
                preexistingToken->second));
        }

        CHECK_FAILURE(receiver->add_DevToolsProtocolEventReceived(
            Callback<ICoreWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](
                    ICoreWebView2* sender,
                    ICoreWebView2DevToolsProtocolEventReceivedEventArgs* args) -> HRESULT {
                    wil::unique_cotaskmem_string parameterObjectAsJson;
                    CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
                    MessageBox(
                        nullptr, parameterObjectAsJson.get(),
                        (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
                    return S_OK;
                })
                .Get(),
            &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### <span data-ttu-id="96b0c-478">GoBack</span><span class="sxs-lookup"><span data-stu-id="96b0c-478">GoBack</span></span> 

<span data-ttu-id="96b0c-479">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-479">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="96b0c-480">パブリック HRESULT [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="96b0c-480">public HRESULT [GoBack](#goback)()</span></span>

#### <span data-ttu-id="96b0c-481">GoForward</span><span class="sxs-lookup"><span data-stu-id="96b0c-481">GoForward</span></span> 

<span data-ttu-id="96b0c-482">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-482">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="96b0c-483">パブリック HRESULT [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="96b0c-483">public HRESULT [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="96b0c-484">検索</span><span class="sxs-lookup"><span data-stu-id="96b0c-484">Navigate</span></span> 

<span data-ttu-id="96b0c-485">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-485">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="96b0c-486">パブリック HRESULT [移動](#navigate)(LPCWSTR uri)</span><span class="sxs-lookup"><span data-stu-id="96b0c-486">public HRESULT [Navigate](#navigate)(LPCWSTR uri)</span></span>

<span data-ttu-id="96b0c-487">詳細については、ナビゲーションイベントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96b0c-487">See the navigation events for more information.</span></span> <span data-ttu-id="96b0c-488">これによってナビゲーションが開始されることに注意してください。この操作が完了すると、対応する NavigationStarting イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-488">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

```cpp
void ControlComponent::NavigateToAddressBar()
{
    int length = GetWindowTextLength(GetAddressBar());
    std::wstring uri(length, 0);
    PWSTR buffer = const_cast<PWSTR>(uri.data());
    GetWindowText(GetAddressBar(), buffer, length + 1);

    HRESULT hr = m_webView->Navigate(uri.c_str());
    if (hr == E_INVALIDARG)
    {
        // An invalid URI was provided.
        if (uri.find(L' ') == std::wstring::npos
            && uri.find(L'.') != std::wstring::npos)
        {
            // If it contains a dot and no spaces, try tacking http:// on the front.
            hr = m_webView->Navigate((L"http://" + uri).c_str());
        }
        else
        {
            // Otherwise treat it as a web search. We aren't bothering to escape
            // URL syntax characters such as & and #
            hr = m_webView->Navigate((L"https://bing.com/search?q=" + uri).c_str());
        }
    }
    if (hr != E_INVALIDARG) {
        CHECK_FAILURE(hr);
    }
}
```

#### <span data-ttu-id="96b0c-489">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="96b0c-489">NavigateToString</span></span> 

<span data-ttu-id="96b0c-490">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-490">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="96b0c-491">パブリック HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="96b0c-491">public HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlContent)</span></span>

<span data-ttu-id="96b0c-492">HtmlContent パラメーターの合計サイズは、2 MB を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-492">The htmlContent parameter may not be larger than 2 MB in total size.</span></span> <span data-ttu-id="96b0c-493">新しいページの起点は "空白" になります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-493">The origin of the new page will be about:blank.</span></span>

```cpp
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### <span data-ttu-id="96b0c-494">Opendevツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="96b0c-494">OpenDevToolsWindow</span></span> 

<span data-ttu-id="96b0c-495">WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-495">Opens the DevTools window for the current document in the WebView.</span></span>

> <span data-ttu-id="96b0c-496">パブリック HRESULT [Opendevツールウィンドウ](#opendevtoolswindow)()</span><span class="sxs-lookup"><span data-stu-id="96b0c-496">public HRESULT [OpenDevToolsWindow](#opendevtoolswindow)()</span></span>

<span data-ttu-id="96b0c-497">DevTools ウィンドウが既に開いているときに、何も呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-497">Does nothing if called when the DevTools window is already open.</span></span>

#### <span data-ttu-id="96b0c-498">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="96b0c-498">PostWebMessageAsJson</span></span> 

<span data-ttu-id="96b0c-499">指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-499">Post the specified webMessage to the top level document in this WebView.</span></span>

> <span data-ttu-id="96b0c-500">パブリック HRESULT [Postwebmessageasjson](#postwebmessageasjson)(LPCWSTR webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="96b0c-500">public HRESULT [PostWebMessageAsJson](#postwebmessageasjson)(LPCWSTR webMessageAsJson)</span></span>

<span data-ttu-id="96b0c-501">最上位のドキュメントのウィンドウには、"." というメッセージイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-501">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="96b0c-502">このドキュメントの JavaScript は、次のようにしてイベントをサブスクライブし、サブスクライブを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-502">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span>

```
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

<span data-ttu-id="96b0c-503">イベント引数は、のインスタンス `MessageEvent` です。</span><span class="sxs-lookup"><span data-stu-id="96b0c-503">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="96b0c-504">ICoreWebView2Settings:: IsWebMessageEnabled の設定は true である必要があります。また、このメソッドは E_INVALIDARG で失敗します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-504">The ICoreWebView2Settings::IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="96b0c-505">イベント arg の data プロパティは、JSON 文字列として JavaScript オブジェクトに解析された webMessage 文字列のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="96b0c-505">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="96b0c-506">イベント arg の source プロパティは、オブジェクトへの参照です `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="96b0c-506">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="96b0c-507">WebView の HTML ドキュメントからホストにメッセージを送信する方法については、「add_WebMessageReceived」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96b0c-507">See add_WebMessageReceived for information on sending messages from the HTML document in the WebView to the host.</span></span> <span data-ttu-id="96b0c-508">このメッセージは非同期的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-508">This message is sent asynchronously.</span></span> <span data-ttu-id="96b0c-509">メッセージがページに投稿される前にナビゲーションが発生した場合、メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-509">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<ICoreWebView2WebMessageReceivedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->TryGetWebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### <span data-ttu-id="96b0c-510">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="96b0c-510">PostWebMessageAsString</span></span> 

<span data-ttu-id="96b0c-511">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="96b0c-511">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="96b0c-512">パブリック HRESULT [Postwebmessageasstring](#postwebmessageasstring)(LPCWSTR webmessageasstring)</span><span class="sxs-lookup"><span data-stu-id="96b0c-512">public HRESULT [PostWebMessageAsString](#postwebmessageasstring)(LPCWSTR webMessageAsString)</span></span>

<span data-ttu-id="96b0c-513">これは、PostWebMessageAsJson とまったく同じように動作し `window.chrome.webview` ますが、message イベント arg の data プロパティは、webMessageAsString と同じ値を持つ文字列になります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-513">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="96b0c-514">JSON オブジェクトではなく単純な文字列を使って通信する場合は、PostWebMessageAsJson の代わりに、これを使います。</span><span class="sxs-lookup"><span data-stu-id="96b0c-514">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="96b0c-515">再</span><span class="sxs-lookup"><span data-stu-id="96b0c-515">Reload</span></span> 

<span data-ttu-id="96b0c-516">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="96b0c-516">Reload the current page.</span></span>

> <span data-ttu-id="96b0c-517">パブリック HRESULT [Reload](#reload)()</span><span class="sxs-lookup"><span data-stu-id="96b0c-517">public HRESULT [Reload](#reload)()</span></span>

<span data-ttu-id="96b0c-518">これは、すべてのナビゲーションイベント (HTTP キャッシュ内のエントリを含む) を含む、現在のトップレベルドキュメントの URI に移動する操作と似ています。</span><span class="sxs-lookup"><span data-stu-id="96b0c-518">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="96b0c-519">ただし、戻る/forward 履歴は変更されません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-519">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="96b0c-520">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-520">remove_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="96b0c-521">Add_ContainsFullScreenElementChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-521">Remove an event handler previously added with add_ContainsFullScreenElementChanged.</span></span>

> <span data-ttu-id="96b0c-522">パブリック HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-522">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-523">remove_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="96b0c-523">remove_ContentLoading</span></span> 

<span data-ttu-id="96b0c-524">Add_ContentLoading で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-524">Remove an event handler previously added with add_ContentLoading.</span></span>

> <span data-ttu-id="96b0c-525">パブリック HRESULT [remove_ContentLoading](#remove_contentloading)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-525">public HRESULT [remove_ContentLoading](#remove_contentloading)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-526">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-526">remove_DocumentTitleChanged</span></span> 

<span data-ttu-id="96b0c-527">Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-527">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>

> <span data-ttu-id="96b0c-528">パブリック HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-528">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-529">remove_FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="96b0c-529">remove_FrameNavigationCompleted</span></span> 

<span data-ttu-id="96b0c-530">Add_FrameNavigationCompleted で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-530">Remove an event handler previously added with add_FrameNavigationCompleted.</span></span>

> <span data-ttu-id="96b0c-531">パブリック HRESULT [remove_FrameNavigationCompleted](#remove_framenavigationcompleted)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-531">public HRESULT [remove_FrameNavigationCompleted](#remove_framenavigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-532">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="96b0c-532">remove_FrameNavigationStarting</span></span> 

<span data-ttu-id="96b0c-533">Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-533">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>

> <span data-ttu-id="96b0c-534">パブリック HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-534">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-535">remove_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-535">remove_HistoryChanged</span></span> 

<span data-ttu-id="96b0c-536">Add_HistoryChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-536">Remove an event handler previously added with add_HistoryChanged.</span></span>

> <span data-ttu-id="96b0c-537">パブリック HRESULT [remove_HistoryChanged](#remove_historychanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-537">public HRESULT [remove_HistoryChanged](#remove_historychanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-538">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="96b0c-538">remove_NavigationCompleted</span></span> 

<span data-ttu-id="96b0c-539">Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-539">Remove an event handler previously added with add_NavigationCompleted.</span></span>

> <span data-ttu-id="96b0c-540">パブリック HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-540">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-541">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="96b0c-541">remove_NavigationStarting</span></span> 

<span data-ttu-id="96b0c-542">Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-542">Remove an event handler previously added with add_NavigationStarting.</span></span>

> <span data-ttu-id="96b0c-543">パブリック HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-543">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-544">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-544">remove_NewWindowRequested</span></span> 

<span data-ttu-id="96b0c-545">Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-545">Remove an event handler previously added with add_NewWindowRequested.</span></span>

> <span data-ttu-id="96b0c-546">パブリック HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-546">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-547">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-547">remove_PermissionRequested</span></span> 

<span data-ttu-id="96b0c-548">Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-548">Remove an event handler previously added with add_PermissionRequested.</span></span>

> <span data-ttu-id="96b0c-549">パブリック HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-549">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-550">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="96b0c-550">remove_ProcessFailed</span></span> 

<span data-ttu-id="96b0c-551">Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-551">Remove an event handler previously added with add_ProcessFailed.</span></span>

> <span data-ttu-id="96b0c-552">パブリック HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-552">public HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-553">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="96b0c-553">remove_ScriptDialogOpening</span></span> 

<span data-ttu-id="96b0c-554">Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-554">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>

> <span data-ttu-id="96b0c-555">パブリック HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-555">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-556">remove_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="96b0c-556">remove_SourceChanged</span></span> 

<span data-ttu-id="96b0c-557">Add_SourceChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-557">Remove an event handler previously added with add_SourceChanged.</span></span>

> <span data-ttu-id="96b0c-558">パブリック HRESULT [remove_SourceChanged](#remove_sourcechanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-558">public HRESULT [remove_SourceChanged](#remove_sourcechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-559">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="96b0c-559">remove_WebMessageReceived</span></span> 

<span data-ttu-id="96b0c-560">Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-560">Remove an event handler previously added with add_WebMessageReceived.</span></span>

> <span data-ttu-id="96b0c-561">パブリック HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-561">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-562">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-562">remove_WebResourceRequested</span></span> 

<span data-ttu-id="96b0c-563">Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-563">Remove an event handler previously added with add_WebResourceRequested.</span></span>

> <span data-ttu-id="96b0c-564">パブリック HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-564">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-565">remove_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="96b0c-565">remove_WindowCloseRequested</span></span> 

<span data-ttu-id="96b0c-566">Add_WindowCloseRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-566">Remove an event handler previously added with add_WindowCloseRequested.</span></span>

> <span data-ttu-id="96b0c-567">パブリック HRESULT [remove_WindowCloseRequested](#remove_windowcloserequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="96b0c-567">public HRESULT [remove_WindowCloseRequested](#remove_windowcloserequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="96b0c-568">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="96b0c-568">RemoveHostObjectFromScript</span></span> 

<span data-ttu-id="96b0c-569">名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="96b0c-569">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>

> <span data-ttu-id="96b0c-570">パブリック HRESULT [Removehostobjectfromscript](#removehostobjectfromscript)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="96b0c-570">public HRESULT [RemoveHostObjectFromScript](#removehostobjectfromscript)(LPCWSTR name)</span></span>

<span data-ttu-id="96b0c-571">新しいアクセスの試行は拒否されますが、そのオブジェクトが WebView の JavaScript コードによって既に取得されている場合は、JavaScript コードはそのオブジェクトに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-571">While new access attempts will be denied, if the object is already obtained by JavaScript code in the WebView, the JavaScript code will continue to have access to that object.</span></span> <span data-ttu-id="96b0c-572">既に削除されているか追加されていない名前に対してこのメソッドを呼び出すと、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-572">Calling this method for a name that is already removed or never added will fail.</span></span>

#### <span data-ttu-id="96b0c-573">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="96b0c-573">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="96b0c-574">指定したスクリプト id で、によって追加された対応する JavaScript を削除し `AddScriptToExecuteOnDocumentCreated` ます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-574">Remove the corresponding JavaScript added using `AddScriptToExecuteOnDocumentCreated` with the specified script id.</span></span>

> <span data-ttu-id="96b0c-575">パブリック HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span><span class="sxs-lookup"><span data-stu-id="96b0c-575">public HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span></span>

#### <span data-ttu-id="96b0c-576">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="96b0c-576">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="96b0c-577">以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-577">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="96b0c-578">パブリック HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri、 [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="96b0c-578">public HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri, [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="96b0c-579">同じフィルターが複数回追加された場合は、削除が有効になるまで何度も削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b0c-579">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="96b0c-580">追加されていないフィルターの E_INVALIDARG を返します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-580">Returns E_INVALIDARG for a filter that was never added.</span></span>

#### <span data-ttu-id="96b0c-581">Stop</span><span class="sxs-lookup"><span data-stu-id="96b0c-581">Stop</span></span> 

<span data-ttu-id="96b0c-582">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-582">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="96b0c-583">パブリック HRESULT [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="96b0c-583">public HRESULT [Stop](#stop)()</span></span>

<span data-ttu-id="96b0c-584">スクリプトは停止されません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-584">Does not stop scripts.</span></span>

#### <span data-ttu-id="96b0c-585">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="96b0c-585">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span> 

<span data-ttu-id="96b0c-586">ICoreWebView2:: CapturePreview メソッドで使用されている画像形式。</span><span class="sxs-lookup"><span data-stu-id="96b0c-586">Image format used by the ICoreWebView2::CapturePreview method.</span></span>

> <span data-ttu-id="96b0c-587">列挙型 [COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format)</span><span class="sxs-lookup"><span data-stu-id="96b0c-587">enum [COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format)</span></span>

 <span data-ttu-id="96b0c-588">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-588">Values</span></span>                         | <span data-ttu-id="96b0c-589">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-589">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-590">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span><span class="sxs-lookup"><span data-stu-id="96b0c-590">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span></span>            | <span data-ttu-id="96b0c-591">PNG 画像形式。</span><span class="sxs-lookup"><span data-stu-id="96b0c-591">PNG image format.</span></span>
<span data-ttu-id="96b0c-592">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span><span class="sxs-lookup"><span data-stu-id="96b0c-592">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span></span>            | <span data-ttu-id="96b0c-593">JPEG イメージ形式。</span><span class="sxs-lookup"><span data-stu-id="96b0c-593">JPEG image format.</span></span>

#### <span data-ttu-id="96b0c-594">COREWEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="96b0c-594">COREWEBVIEW2_KEY_EVENT_KIND</span></span> 

<span data-ttu-id="96b0c-595">AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="96b0c-595">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="96b0c-596">列挙型 [COREWEBVIEW2_KEY_EVENT_KIND](#corewebview2_key_event_kind)</span><span class="sxs-lookup"><span data-stu-id="96b0c-596">enum [COREWEBVIEW2_KEY_EVENT_KIND](#corewebview2_key_event_kind)</span></span>

 <span data-ttu-id="96b0c-597">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-597">Values</span></span>                         | <span data-ttu-id="96b0c-598">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-598">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-599">COREWEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="96b0c-599">COREWEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span></span>            | <span data-ttu-id="96b0c-600">ウィンドウメッセージ WM_KEYDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-600">Correspond to window message WM_KEYDOWN.</span></span>
<span data-ttu-id="96b0c-601">COREWEBVIEW2_KEY_EVENT_KIND_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="96b0c-601">COREWEBVIEW2_KEY_EVENT_KIND_KEY_UP</span></span>            | <span data-ttu-id="96b0c-602">ウィンドウメッセージ WM_KEYUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-602">Correspond to window message WM_KEYUP.</span></span>
<span data-ttu-id="96b0c-603">COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="96b0c-603">COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span></span>            | <span data-ttu-id="96b0c-604">ウィンドウメッセージ WM_SYSKEYDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-604">Correspond to window message WM_SYSKEYDOWN.</span></span>
<span data-ttu-id="96b0c-605">COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="96b0c-605">COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span></span>            | <span data-ttu-id="96b0c-606">ウィンドウメッセージ WM_SYSKEYUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-606">Correspond to window message WM_SYSKEYUP.</span></span>

#### <span data-ttu-id="96b0c-607">COREWEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="96b0c-607">COREWEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="96b0c-608">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="96b0c-608">Reason for moving focus.</span></span>

> <span data-ttu-id="96b0c-609">列挙型 [COREWEBVIEW2_MOVE_FOCUS_REASON](#corewebview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="96b0c-609">enum [COREWEBVIEW2_MOVE_FOCUS_REASON](#corewebview2_move_focus_reason)</span></span>

 <span data-ttu-id="96b0c-610">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-610">Values</span></span>                         | <span data-ttu-id="96b0c-611">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-611">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-612">COREWEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="96b0c-612">COREWEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="96b0c-613">コード設定による WebView へのフォーカス。</span><span class="sxs-lookup"><span data-stu-id="96b0c-613">Code setting focus into WebView.</span></span>
<span data-ttu-id="96b0c-614">COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="96b0c-614">COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="96b0c-615">タブトラバーサルを前方に移動するためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="96b0c-615">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="96b0c-616">COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="96b0c-616">COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="96b0c-617">タブトラバーサルに戻るためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="96b0c-617">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="96b0c-618">COREWEBVIEW2_PERMISSION_KIND</span><span class="sxs-lookup"><span data-stu-id="96b0c-618">COREWEBVIEW2_PERMISSION_KIND</span></span> 

<span data-ttu-id="96b0c-619">アクセス許可要求の種類。</span><span class="sxs-lookup"><span data-stu-id="96b0c-619">The type of a permission request.</span></span>

> <span data-ttu-id="96b0c-620">列挙型 [COREWEBVIEW2_PERMISSION_KIND](#corewebview2_permission_kind)</span><span class="sxs-lookup"><span data-stu-id="96b0c-620">enum [COREWEBVIEW2_PERMISSION_KIND](#corewebview2_permission_kind)</span></span>

 <span data-ttu-id="96b0c-621">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-621">Values</span></span>                         | <span data-ttu-id="96b0c-622">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-622">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-623">COREWEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="96b0c-623">COREWEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION</span></span>            | <span data-ttu-id="96b0c-624">不明な権限。</span><span class="sxs-lookup"><span data-stu-id="96b0c-624">Unknown permission.</span></span>
<span data-ttu-id="96b0c-625">COREWEBVIEW2_PERMISSION_KIND_MICROPHONE</span><span class="sxs-lookup"><span data-stu-id="96b0c-625">COREWEBVIEW2_PERMISSION_KIND_MICROPHONE</span></span>            | <span data-ttu-id="96b0c-626">オーディオをキャプチャするためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="96b0c-626">Permission to capture audio.</span></span>
<span data-ttu-id="96b0c-627">COREWEBVIEW2_PERMISSION_KIND_CAMERA</span><span class="sxs-lookup"><span data-stu-id="96b0c-627">COREWEBVIEW2_PERMISSION_KIND_CAMERA</span></span>            | <span data-ttu-id="96b0c-628">ビデオをキャプチャするためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="96b0c-628">Permission to capture video.</span></span>
<span data-ttu-id="96b0c-629">COREWEBVIEW2_PERMISSION_KIND_GEOLOCATION</span><span class="sxs-lookup"><span data-stu-id="96b0c-629">COREWEBVIEW2_PERMISSION_KIND_GEOLOCATION</span></span>            | <span data-ttu-id="96b0c-630">位置情報へのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="96b0c-630">Permission to access geolocation.</span></span>
<span data-ttu-id="96b0c-631">COREWEBVIEW2_PERMISSION_KIND_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="96b0c-631">COREWEBVIEW2_PERMISSION_KIND_NOTIFICATIONS</span></span>            | <span data-ttu-id="96b0c-632">Web 通知を送信するためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="96b0c-632">Permission to send web notifications.</span></span>
<span data-ttu-id="96b0c-633">COREWEBVIEW2_PERMISSION_KIND_OTHER_SENSORS</span><span class="sxs-lookup"><span data-stu-id="96b0c-633">COREWEBVIEW2_PERMISSION_KIND_OTHER_SENSORS</span></span>            | <span data-ttu-id="96b0c-634">汎用センサーへのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="96b0c-634">Permission to access generic sensor.</span></span>
<span data-ttu-id="96b0c-635">COREWEBVIEW2_PERMISSION_KIND_CLIPBOARD_READ</span><span class="sxs-lookup"><span data-stu-id="96b0c-635">COREWEBVIEW2_PERMISSION_KIND_CLIPBOARD_READ</span></span>            | <span data-ttu-id="96b0c-636">ユーザーのジェスチャを使わずにシステムクリップボードを読み取る権限。</span><span class="sxs-lookup"><span data-stu-id="96b0c-636">Permission to read system clipboard without a user gesture.</span></span>

#### <span data-ttu-id="96b0c-637">COREWEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="96b0c-637">COREWEBVIEW2_PERMISSION_STATE</span></span> 

<span data-ttu-id="96b0c-638">アクセス許可要求に対する応答。</span><span class="sxs-lookup"><span data-stu-id="96b0c-638">Response to a permission request.</span></span>

> <span data-ttu-id="96b0c-639">列挙型 [COREWEBVIEW2_PERMISSION_STATE](#corewebview2_permission_state)</span><span class="sxs-lookup"><span data-stu-id="96b0c-639">enum [COREWEBVIEW2_PERMISSION_STATE](#corewebview2_permission_state)</span></span>

 <span data-ttu-id="96b0c-640">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-640">Values</span></span>                         | <span data-ttu-id="96b0c-641">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-641">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-642">COREWEBVIEW2_PERMISSION_STATE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="96b0c-642">COREWEBVIEW2_PERMISSION_STATE_DEFAULT</span></span>            | <span data-ttu-id="96b0c-643">既定のブラウザー動作を使用します。通常はユーザーに判断を求めます。</span><span class="sxs-lookup"><span data-stu-id="96b0c-643">Use default browser behavior, which normally prompt users for decision.</span></span>
<span data-ttu-id="96b0c-644">COREWEBVIEW2_PERMISSION_STATE_ALLOW</span><span class="sxs-lookup"><span data-stu-id="96b0c-644">COREWEBVIEW2_PERMISSION_STATE_ALLOW</span></span>            | <span data-ttu-id="96b0c-645">権限の要求を許可します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-645">Grant the permission request.</span></span>
<span data-ttu-id="96b0c-646">COREWEBVIEW2_PERMISSION_STATE_DENY</span><span class="sxs-lookup"><span data-stu-id="96b0c-646">COREWEBVIEW2_PERMISSION_STATE_DENY</span></span>            | <span data-ttu-id="96b0c-647">権限の要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-647">Deny the permission request.</span></span>

#### <span data-ttu-id="96b0c-648">COREWEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="96b0c-648">COREWEBVIEW2_PHYSICAL_KEY_STATUS</span></span> 

<span data-ttu-id="96b0c-649">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="96b0c-649">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

> <span data-ttu-id="96b0c-650">typedef [COREWEBVIEW2_PHYSICAL_KEY_STATUS](#corewebview2_physical_key_status)</span><span class="sxs-lookup"><span data-stu-id="96b0c-650">typedef [COREWEBVIEW2_PHYSICAL_KEY_STATUS](#corewebview2_physical_key_status)</span></span>

<span data-ttu-id="96b0c-651">詳細については、WM_KEYDOWN のドキュメントを参照してください。 [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span><span class="sxs-lookup"><span data-stu-id="96b0c-651">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span></span>

#### <span data-ttu-id="96b0c-652">COREWEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="96b0c-652">COREWEBVIEW2_PROCESS_FAILED_KIND</span></span> 

<span data-ttu-id="96b0c-653">ICoreWebView2ProcessFailedEventHandler インターフェイスで使用されているプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="96b0c-653">Kind of process failure used in the ICoreWebView2ProcessFailedEventHandler interface.</span></span>

> <span data-ttu-id="96b0c-654">列挙型 [COREWEBVIEW2_PROCESS_FAILED_KIND](#corewebview2_process_failed_kind)</span><span class="sxs-lookup"><span data-stu-id="96b0c-654">enum [COREWEBVIEW2_PROCESS_FAILED_KIND](#corewebview2_process_failed_kind)</span></span>

 <span data-ttu-id="96b0c-655">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-655">Values</span></span>                         | <span data-ttu-id="96b0c-656">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-656">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-657">COREWEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="96b0c-657">COREWEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span></span>            | <span data-ttu-id="96b0c-658">ブラウザープロセスが予期せず終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-658">Indicates the browser process terminated unexpectedly.</span></span>
<span data-ttu-id="96b0c-659">COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="96b0c-659">COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span></span>            | <span data-ttu-id="96b0c-660">レンダープロセスが予期せず終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-660">Indicates the render process terminated unexpectedly.</span></span>
<span data-ttu-id="96b0c-661">COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span><span class="sxs-lookup"><span data-stu-id="96b0c-661">COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span></span>            | <span data-ttu-id="96b0c-662">レンダープロセスが応答しなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-662">Indicates the render process becomes unresponsive.</span></span>

#### <span data-ttu-id="96b0c-663">COREWEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="96b0c-663">COREWEBVIEW2_SCRIPT_DIALOG_KIND</span></span> 

<span data-ttu-id="96b0c-664">ICoreWebView2ScriptDialogOpeningEventHandler インターフェイスで使用される JavaScript ダイアログの種類。</span><span class="sxs-lookup"><span data-stu-id="96b0c-664">Kind of JavaScript dialog used in the ICoreWebView2ScriptDialogOpeningEventHandler interface.</span></span>

> <span data-ttu-id="96b0c-665">列挙型 [COREWEBVIEW2_SCRIPT_DIALOG_KIND](#corewebview2_script_dialog_kind)</span><span class="sxs-lookup"><span data-stu-id="96b0c-665">enum [COREWEBVIEW2_SCRIPT_DIALOG_KIND](#corewebview2_script_dialog_kind)</span></span>

 <span data-ttu-id="96b0c-666">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-666">Values</span></span>                         | <span data-ttu-id="96b0c-667">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-667">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-668">COREWEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span><span class="sxs-lookup"><span data-stu-id="96b0c-668">COREWEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span></span>            | <span data-ttu-id="96b0c-669">ウィンドウで呼び出されるダイアログ。警告 JavaScript 関数。</span><span class="sxs-lookup"><span data-stu-id="96b0c-669">A dialog invoked via the window.alert JavaScript function.</span></span>
<span data-ttu-id="96b0c-670">COREWEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span><span class="sxs-lookup"><span data-stu-id="96b0c-670">COREWEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span></span>            | <span data-ttu-id="96b0c-671">ウィンドウを通じて呼び出されるダイアログ。 JavaScript 関数を確認してください。</span><span class="sxs-lookup"><span data-stu-id="96b0c-671">A dialog invoked via the window.confirm JavaScript function.</span></span>
<span data-ttu-id="96b0c-672">COREWEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span><span class="sxs-lookup"><span data-stu-id="96b0c-672">COREWEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span></span>            | <span data-ttu-id="96b0c-673">Window というプロンプトで呼び出されるダイアログ。</span><span class="sxs-lookup"><span data-stu-id="96b0c-673">A dialog invoked via the window.prompt JavaScript function.</span></span>
<span data-ttu-id="96b0c-674">COREWEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD</span><span class="sxs-lookup"><span data-stu-id="96b0c-674">COREWEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD</span></span>            | <span data-ttu-id="96b0c-675">Beforeunload JavaScript イベントによって呼び出されるダイアログ。</span><span class="sxs-lookup"><span data-stu-id="96b0c-675">A dialog invoked via the beforeunload JavaScript event.</span></span>

#### <span data-ttu-id="96b0c-676">COREWEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="96b0c-676">COREWEBVIEW2_WEB_ERROR_STATUS</span></span> 

<span data-ttu-id="96b0c-677">Web ナビゲーションのエラー状態の値。</span><span class="sxs-lookup"><span data-stu-id="96b0c-677">Error status values for web navigations.</span></span>

> <span data-ttu-id="96b0c-678">列挙型 [COREWEBVIEW2_WEB_ERROR_STATUS](#corewebview2_web_error_status)</span><span class="sxs-lookup"><span data-stu-id="96b0c-678">enum [COREWEBVIEW2_WEB_ERROR_STATUS](#corewebview2_web_error_status)</span></span>

 <span data-ttu-id="96b0c-679">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-679">Values</span></span>                         | <span data-ttu-id="96b0c-680">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-680">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-681">COREWEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="96b0c-681">COREWEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span></span>            | <span data-ttu-id="96b0c-682">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-682">An unknown error occurred.</span></span>
<span data-ttu-id="96b0c-683">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span><span class="sxs-lookup"><span data-stu-id="96b0c-683">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span></span>            | <span data-ttu-id="96b0c-684">SSL 証明書の共通名が web アドレスと一致しません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-684">The SSL certificate common name does not match the web address.</span></span>
<span data-ttu-id="96b0c-685">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="96b0c-685">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span></span>            | <span data-ttu-id="96b0c-686">SSL 証明書の有効期限が切れています。</span><span class="sxs-lookup"><span data-stu-id="96b0c-686">The SSL certificate has expired.</span></span>
<span data-ttu-id="96b0c-687">COREWEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span><span class="sxs-lookup"><span data-stu-id="96b0c-687">COREWEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span></span>            | <span data-ttu-id="96b0c-688">SSL クライアント証明書にエラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="96b0c-688">The SSL client certificate contains errors.</span></span>
<span data-ttu-id="96b0c-689">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span><span class="sxs-lookup"><span data-stu-id="96b0c-689">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span></span>            | <span data-ttu-id="96b0c-690">SSL 証明書が失効しています。</span><span class="sxs-lookup"><span data-stu-id="96b0c-690">The SSL certificate has been revoked.</span></span>
<span data-ttu-id="96b0c-691">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="96b0c-691">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span></span>            | <span data-ttu-id="96b0c-692">SSL 証明書が無効になっている可能性があります。これは、 &ndash; 証明書がホスト名の公開キーピンと一致しなかったことを意味します。証明書が信頼されていない機関によって署名されている、または脆弱な署名アルゴリズムを使用している場合、証明書が名前の制限を超えている証明書、証明書の有効期間が長い、証明書の透過情報がない、証明書が [従来のシマンテックルート](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html)にチェーンされている。</span><span class="sxs-lookup"><span data-stu-id="96b0c-692">The SSL certificate is invalid &ndash; this could mean the certificate did not match the public key pins for the host name, the certificate is signed by an untrusted authority or using a weak sign algorithm, the certificate claimed DNS names violate name constraints, the certificate contains a weak key, the certificate's validity period is too long, lack of revocation information or revocation mechanism, non-unique host name, lack of certificate transparency information, or the certificate is chained to a [legacy Symantec root](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html).</span></span>
<span data-ttu-id="96b0c-693">COREWEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="96b0c-693">COREWEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span></span>            | <span data-ttu-id="96b0c-694">ホストに到達できません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-694">The host is unreachable.</span></span>
<span data-ttu-id="96b0c-695">COREWEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96b0c-695">COREWEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span></span>            | <span data-ttu-id="96b0c-696">接続がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-696">The connection has timed out.</span></span>
<span data-ttu-id="96b0c-697">COREWEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span><span class="sxs-lookup"><span data-stu-id="96b0c-697">COREWEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span></span>            | <span data-ttu-id="96b0c-698">サーバーが無効または認識不能な応答を返しました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-698">The server returned an invalid or unrecognized response.</span></span>
<span data-ttu-id="96b0c-699">COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span><span class="sxs-lookup"><span data-stu-id="96b0c-699">COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span></span>            | <span data-ttu-id="96b0c-700">接続が中止されました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-700">The connection was aborted.</span></span>
<span data-ttu-id="96b0c-701">COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span><span class="sxs-lookup"><span data-stu-id="96b0c-701">COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span></span>            | <span data-ttu-id="96b0c-702">接続がリセットされました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-702">The connection was reset.</span></span>
<span data-ttu-id="96b0c-703">COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span><span class="sxs-lookup"><span data-stu-id="96b0c-703">COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span></span>            | <span data-ttu-id="96b0c-704">インターネット接続が切断されました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-704">The Internet connection has been lost.</span></span>
<span data-ttu-id="96b0c-705">COREWEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="96b0c-705">COREWEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span></span>            | <span data-ttu-id="96b0c-706">宛先に接続できません。</span><span class="sxs-lookup"><span data-stu-id="96b0c-706">Cannot connect to destination.</span></span>
<span data-ttu-id="96b0c-707">COREWEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="96b0c-707">COREWEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span></span>            | <span data-ttu-id="96b0c-708">指定されたホスト名を解決できませんでした。</span><span class="sxs-lookup"><span data-stu-id="96b0c-708">Could not resolve provided host name.</span></span>
<span data-ttu-id="96b0c-709">COREWEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span><span class="sxs-lookup"><span data-stu-id="96b0c-709">COREWEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span></span>            | <span data-ttu-id="96b0c-710">操作が取り消されました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-710">The operation was canceled.</span></span>
<span data-ttu-id="96b0c-711">COREWEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span><span class="sxs-lookup"><span data-stu-id="96b0c-711">COREWEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span></span>            | <span data-ttu-id="96b0c-712">要求のリダイレクトに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-712">The request redirect failed.</span></span>
<span data-ttu-id="96b0c-713">COREWEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span><span class="sxs-lookup"><span data-stu-id="96b0c-713">COREWEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span></span>            | <span data-ttu-id="96b0c-714">予期しないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="96b0c-714">An unexpected error occurred.</span></span>

#### <span data-ttu-id="96b0c-715">COREWEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="96b0c-715">COREWEBVIEW2_WEB_RESOURCE_CONTEXT</span></span> 

<span data-ttu-id="96b0c-716">Web リソース要求コンテキストの列挙。</span><span class="sxs-lookup"><span data-stu-id="96b0c-716">Enum for web resource request contexts.</span></span>

> <span data-ttu-id="96b0c-717">列挙型 [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context)</span><span class="sxs-lookup"><span data-stu-id="96b0c-717">enum [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context)</span></span>

 <span data-ttu-id="96b0c-718">値</span><span class="sxs-lookup"><span data-stu-id="96b0c-718">Values</span></span>                         | <span data-ttu-id="96b0c-719">説明</span><span class="sxs-lookup"><span data-stu-id="96b0c-719">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="96b0c-720">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span><span class="sxs-lookup"><span data-stu-id="96b0c-720">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span></span>            | <span data-ttu-id="96b0c-721">すべてのリソース。</span><span class="sxs-lookup"><span data-stu-id="96b0c-721">All resources.</span></span>
<span data-ttu-id="96b0c-722">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span><span class="sxs-lookup"><span data-stu-id="96b0c-722">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span></span>            | <span data-ttu-id="96b0c-723">ドキュメントリソース。</span><span class="sxs-lookup"><span data-stu-id="96b0c-723">Document resources.</span></span>
<span data-ttu-id="96b0c-724">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span><span class="sxs-lookup"><span data-stu-id="96b0c-724">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span></span>            | <span data-ttu-id="96b0c-725">CSS リソース。</span><span class="sxs-lookup"><span data-stu-id="96b0c-725">CSS resources.</span></span>
<span data-ttu-id="96b0c-726">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span><span class="sxs-lookup"><span data-stu-id="96b0c-726">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span></span>            | <span data-ttu-id="96b0c-727">画像リソース。</span><span class="sxs-lookup"><span data-stu-id="96b0c-727">Image resources.</span></span>
<span data-ttu-id="96b0c-728">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span><span class="sxs-lookup"><span data-stu-id="96b0c-728">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span></span>            | <span data-ttu-id="96b0c-729">その他のメディアリソース (ビデオなど)。</span><span class="sxs-lookup"><span data-stu-id="96b0c-729">Other media resources such as videos.</span></span>
<span data-ttu-id="96b0c-730">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span><span class="sxs-lookup"><span data-stu-id="96b0c-730">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span></span>            | <span data-ttu-id="96b0c-731">フォントリソース。</span><span class="sxs-lookup"><span data-stu-id="96b0c-731">Font resources.</span></span>
<span data-ttu-id="96b0c-732">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span><span class="sxs-lookup"><span data-stu-id="96b0c-732">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span></span>            | <span data-ttu-id="96b0c-733">スクリプトリソース。</span><span class="sxs-lookup"><span data-stu-id="96b0c-733">Script resources.</span></span>
<span data-ttu-id="96b0c-734">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span><span class="sxs-lookup"><span data-stu-id="96b0c-734">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span></span>            | <span data-ttu-id="96b0c-735">XML HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="96b0c-735">XML HTTP requests.</span></span>
<span data-ttu-id="96b0c-736">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span><span class="sxs-lookup"><span data-stu-id="96b0c-736">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span></span>            | <span data-ttu-id="96b0c-737">API 通信を取得します。</span><span class="sxs-lookup"><span data-stu-id="96b0c-737">Fetch API communication.</span></span>
<span data-ttu-id="96b0c-738">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span><span class="sxs-lookup"><span data-stu-id="96b0c-738">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span></span>            | <span data-ttu-id="96b0c-739">TextTrack のリソース。</span><span class="sxs-lookup"><span data-stu-id="96b0c-739">TextTrack resources.</span></span>
<span data-ttu-id="96b0c-740">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span><span class="sxs-lookup"><span data-stu-id="96b0c-740">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span></span>            | <span data-ttu-id="96b0c-741">EventSource API の通信。</span><span class="sxs-lookup"><span data-stu-id="96b0c-741">EventSource API communication.</span></span>
<span data-ttu-id="96b0c-742">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span><span class="sxs-lookup"><span data-stu-id="96b0c-742">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span></span>            | <span data-ttu-id="96b0c-743">WebSocket API 通信。</span><span class="sxs-lookup"><span data-stu-id="96b0c-743">WebSocket API communication.</span></span>
<span data-ttu-id="96b0c-744">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span><span class="sxs-lookup"><span data-stu-id="96b0c-744">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span></span>            | <span data-ttu-id="96b0c-745">Web App マニフェスト。</span><span class="sxs-lookup"><span data-stu-id="96b0c-745">Web App Manifests.</span></span>
<span data-ttu-id="96b0c-746">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span><span class="sxs-lookup"><span data-stu-id="96b0c-746">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span></span>            | <span data-ttu-id="96b0c-747">署名された HTTP 交換。</span><span class="sxs-lookup"><span data-stu-id="96b0c-747">Signed HTTP Exchanges.</span></span>
<span data-ttu-id="96b0c-748">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span><span class="sxs-lookup"><span data-stu-id="96b0c-748">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span></span>            | <span data-ttu-id="96b0c-749">Ping 要求。</span><span class="sxs-lookup"><span data-stu-id="96b0c-749">Ping requests.</span></span>
<span data-ttu-id="96b0c-750">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span><span class="sxs-lookup"><span data-stu-id="96b0c-750">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span></span>            | <span data-ttu-id="96b0c-751">CSP 違反レポート。</span><span class="sxs-lookup"><span data-stu-id="96b0c-751">CSP Violation Reports.</span></span>
<span data-ttu-id="96b0c-752">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span><span class="sxs-lookup"><span data-stu-id="96b0c-752">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span></span>            | <span data-ttu-id="96b0c-753">その他のリソース。</span><span class="sxs-lookup"><span data-stu-id="96b0c-753">Other resources.</span></span>

