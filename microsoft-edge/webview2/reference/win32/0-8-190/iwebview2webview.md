---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 5711a1dbf501df55fefc9709763c1fe225865e11
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886431"
---
# <span data-ttu-id="cbe9d-104">0.8.355-インターフェイス IWebView2WebView</span><span class="sxs-lookup"><span data-stu-id="cbe9d-104">0.8.355 - interface IWebView2WebView</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebView
  : public IUnknown
```

<span data-ttu-id="cbe9d-105">WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-105">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="cbe9d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="cbe9d-106">Summary</span></span>

 <span data-ttu-id="cbe9d-107">Members</span><span class="sxs-lookup"><span data-stu-id="cbe9d-107">Members</span></span>                        | <span data-ttu-id="cbe9d-108">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cbe9d-109">get_Settings</span><span class="sxs-lookup"><span data-stu-id="cbe9d-109">get_Settings</span></span>](#get_settings) | <span data-ttu-id="cbe9d-110">[IWebView2Settings](IWebView2Settings.md)オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-110">The [IWebView2Settings](IWebView2Settings.md) object contains various modifiable settings for the running WebView.</span></span>
[<span data-ttu-id="cbe9d-111">get_Source</span><span class="sxs-lookup"><span data-stu-id="cbe9d-111">get_Source</span></span>](#get_source) | <span data-ttu-id="cbe9d-112">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-112">The URI of the current top level document.</span></span>
[<span data-ttu-id="cbe9d-113">検索</span><span class="sxs-lookup"><span data-stu-id="cbe9d-113">Navigate</span></span>](#navigate) | <span data-ttu-id="cbe9d-114">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-114">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="cbe9d-115">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-115">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="cbe9d-116">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-116">Move focus into WebView.</span></span>
[<span data-ttu-id="cbe9d-117">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="cbe9d-117">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="cbe9d-118">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-118">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="cbe9d-119">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="cbe9d-119">add_NavigationStarting</span></span>](#add_navigationstarting) | <span data-ttu-id="cbe9d-120">NavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-120">Add an event handler for the NavigationStarting event.</span></span>
[<span data-ttu-id="cbe9d-121">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="cbe9d-121">remove_NavigationStarting</span></span>](#remove_navigationstarting) | <span data-ttu-id="cbe9d-122">Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-122">Remove an event handler previously added with add_NavigationStarting.</span></span>
[<span data-ttu-id="cbe9d-123">add_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="cbe9d-123">add_DocumentStateChanged</span></span>](#add_documentstatechanged) | <span data-ttu-id="cbe9d-124">DocumentStateChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-124">Add an event handler for the DocumentStateChanged event.</span></span>
[<span data-ttu-id="cbe9d-125">remove_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="cbe9d-125">remove_DocumentStateChanged</span></span>](#remove_documentstatechanged) | <span data-ttu-id="cbe9d-126">Add_DocumentStateChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-126">Remove an event handler previously added with add_DocumentStateChanged.</span></span>
[<span data-ttu-id="cbe9d-127">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="cbe9d-127">add_NavigationCompleted</span></span>](#add_navigationcompleted) | <span data-ttu-id="cbe9d-128">NavigationCompleted イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-128">Add an event handler for the NavigationCompleted event.</span></span>
[<span data-ttu-id="cbe9d-129">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="cbe9d-129">remove_NavigationCompleted</span></span>](#remove_navigationcompleted) | <span data-ttu-id="cbe9d-130">Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-130">Remove an event handler previously added with add_NavigationCompleted.</span></span>
[<span data-ttu-id="cbe9d-131">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="cbe9d-131">add_FrameNavigationStarting</span></span>](#add_framenavigationstarting) | <span data-ttu-id="cbe9d-132">FrameNavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-132">Add an event handler for the FrameNavigationStarting event.</span></span>
[<span data-ttu-id="cbe9d-133">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="cbe9d-133">remove_FrameNavigationStarting</span></span>](#remove_framenavigationstarting) | <span data-ttu-id="cbe9d-134">Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-134">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>
[<span data-ttu-id="cbe9d-135">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-135">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="cbe9d-136">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-136">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="cbe9d-137">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-137">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="cbe9d-138">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-138">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="cbe9d-139">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-139">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="cbe9d-140">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-140">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="cbe9d-141">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-141">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="cbe9d-142">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-142">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="cbe9d-143">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-143">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="cbe9d-144">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-144">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="cbe9d-145">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-145">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="cbe9d-146">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-146">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="cbe9d-147">add_WebResourceRequested_deprecated</span><span class="sxs-lookup"><span data-stu-id="cbe9d-147">add_WebResourceRequested_deprecated</span></span>](#add_webresourcerequested_deprecated) | <span data-ttu-id="cbe9d-148">この API は廃止されます。新しい add_WebResourceRequested API を使用してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-148">This API will be deprecated, please use the new add_WebResourceRequested API.</span></span>
[<span data-ttu-id="cbe9d-149">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-149">remove_WebResourceRequested</span></span>](#remove_webresourcerequested) | <span data-ttu-id="cbe9d-150">Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-150">Remove an event handler previously added with add_WebResourceRequested.</span></span>
[<span data-ttu-id="cbe9d-151">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="cbe9d-151">add_ScriptDialogOpening</span></span>](#add_scriptdialogopening) | <span data-ttu-id="cbe9d-152">Scriptの開始イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-152">Add an event handler for the ScriptDialogOpening event.</span></span>
[<span data-ttu-id="cbe9d-153">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="cbe9d-153">remove_ScriptDialogOpening</span></span>](#remove_scriptdialogopening) | <span data-ttu-id="cbe9d-154">Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-154">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>
[<span data-ttu-id="cbe9d-155">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="cbe9d-155">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="cbe9d-156">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-156">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="cbe9d-157">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="cbe9d-157">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="cbe9d-158">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-158">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="cbe9d-159">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-159">add_PermissionRequested</span></span>](#add_permissionrequested) | <span data-ttu-id="cbe9d-160">PermissionRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-160">Add an event handler for the PermissionRequested event.</span></span>
[<span data-ttu-id="cbe9d-161">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-161">remove_PermissionRequested</span></span>](#remove_permissionrequested) | <span data-ttu-id="cbe9d-162">Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-162">Remove an event handler previously added with add_PermissionRequested.</span></span>
[<span data-ttu-id="cbe9d-163">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="cbe9d-163">add_ProcessFailed</span></span>](#add_processfailed) | <span data-ttu-id="cbe9d-164">ProcessFailed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-164">Add an event handler for the ProcessFailed event.</span></span>
[<span data-ttu-id="cbe9d-165">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="cbe9d-165">remove_ProcessFailed</span></span>](#remove_processfailed) | <span data-ttu-id="cbe9d-166">Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-166">Remove an event handler previously added with add_ProcessFailed.</span></span>
[<span data-ttu-id="cbe9d-167">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="cbe9d-167">AddScriptToExecuteOnDocumentCreated</span></span>](#addscripttoexecuteondocumentcreated) | <span data-ttu-id="cbe9d-168">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-168">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="cbe9d-169">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="cbe9d-169">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="cbe9d-170">AddScriptToExecuteOnDocumentCreated によって追加された、対応する JavaScript を削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-170">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>
[<span data-ttu-id="cbe9d-171">Execuスクリプト</span><span class="sxs-lookup"><span data-stu-id="cbe9d-171">ExecuteScript</span></span>](#executescript) | <span data-ttu-id="cbe9d-172">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-172">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="cbe9d-173">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="cbe9d-173">CapturePreview</span></span>](#capturepreview) | <span data-ttu-id="cbe9d-174">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-174">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="cbe9d-175">再</span><span class="sxs-lookup"><span data-stu-id="cbe9d-175">Reload</span></span>](#reload) | <span data-ttu-id="cbe9d-176">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-176">Reload the current page.</span></span>
[<span data-ttu-id="cbe9d-177">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="cbe9d-177">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="cbe9d-178">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-178">The webview bounds.</span></span>
[<span data-ttu-id="cbe9d-179">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="cbe9d-179">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="cbe9d-180">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-180">Set the Bounds property.</span></span>
[<span data-ttu-id="cbe9d-181">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="cbe9d-181">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="cbe9d-182">WebView の現在のページのズームファクター。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-182">The zoom factor for the current page in the WebView.</span></span>
[<span data-ttu-id="cbe9d-183">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="cbe9d-183">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="cbe9d-184">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-184">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="cbe9d-185">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="cbe9d-185">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="cbe9d-186">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-186">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="cbe9d-187">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="cbe9d-187">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="cbe9d-188">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-188">Set the IsVisible property.</span></span>
[<span data-ttu-id="cbe9d-189">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="cbe9d-189">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="cbe9d-190">指定した webMessage をこの[IWebView2WebView]()のトップレベルのドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-190">Post the specified webMessage to the top level document in this [IWebView2WebView]().</span></span>
[<span data-ttu-id="cbe9d-191">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="cbe9d-191">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="cbe9d-192">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-192">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="cbe9d-193">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="cbe9d-193">add_WebMessageReceived</span></span>](#add_webmessagereceived) | <span data-ttu-id="cbe9d-194">このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-194">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="cbe9d-195">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="cbe9d-195">remove_WebMessageReceived</span></span>](#remove_webmessagereceived) | <span data-ttu-id="cbe9d-196">Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-196">Remove an event handler previously added with add_WebMessageReceived.</span></span>
[<span data-ttu-id="cbe9d-197">Close</span><span class="sxs-lookup"><span data-stu-id="cbe9d-197">Close</span></span>](#close) | <span data-ttu-id="cbe9d-198">Webview を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-198">Closes the webview and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="cbe9d-199">Calldevon Protocolメソッド</span><span class="sxs-lookup"><span data-stu-id="cbe9d-199">CallDevToolsProtocolMethod</span></span>](#calldevtoolsprotocolmethod) | <span data-ttu-id="cbe9d-200">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-200">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="cbe9d-201">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="cbe9d-201">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="cbe9d-202">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-202">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="cbe9d-203">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="cbe9d-203">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="cbe9d-204">Add_DevToolsProtocolEventReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-204">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>
[<span data-ttu-id="cbe9d-205">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="cbe9d-205">get_BrowserProcessId</span></span>](#get_browserprocessid) | <span data-ttu-id="cbe9d-206">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-206">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="cbe9d-207">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="cbe9d-207">get_CanGoBack</span></span>](#get_cangoback) | <span data-ttu-id="cbe9d-208">Webview をナビゲーション履歴の前のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-208">Can navigate the webview to the previous page in the navigation history.</span></span>
[<span data-ttu-id="cbe9d-209">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="cbe9d-209">get_CanGoForward</span></span>](#get_cangoforward) | <span data-ttu-id="cbe9d-210">Webview をナビゲーション履歴の次のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-210">Can navigate the webview to the next page in the navigation history.</span></span>
[<span data-ttu-id="cbe9d-211">GoBack</span><span class="sxs-lookup"><span data-stu-id="cbe9d-211">GoBack</span></span>](#goback) | <span data-ttu-id="cbe9d-212">ナビゲーション履歴で、webview を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-212">Navigates the webview to the previous page in the navigation history.</span></span>
[<span data-ttu-id="cbe9d-213">GoForward</span><span class="sxs-lookup"><span data-stu-id="cbe9d-213">GoForward</span></span>](#goforward) | <span data-ttu-id="cbe9d-214">Webview をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-214">Navigates the webview to the next page in the navigation history.</span></span>
[<span data-ttu-id="cbe9d-215">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-215">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span>](#webview2_capture_preview_image_format) | <span data-ttu-id="cbe9d-216">[IWebView2WebView:: CapturePreview](#capturepreview)メソッドで使用されている画像形式。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-216">Image format used by the [IWebView2WebView::CapturePreview](#capturepreview) method.</span></span>
[<span data-ttu-id="cbe9d-217">WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="cbe9d-217">WEBVIEW2_SCRIPT_DIALOG_KIND</span></span>](#webview2_script_dialog_kind) | <span data-ttu-id="cbe9d-218">[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)インターフェイスで使用される JavaScript ダイアログの種類。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-218">Kind of JavaScript dialog used in the [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) interface.</span></span>
[<span data-ttu-id="cbe9d-219">WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="cbe9d-219">WEBVIEW2_PROCESS_FAILED_KIND</span></span>](#webview2_process_failed_kind) | <span data-ttu-id="cbe9d-220">[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)インターフェイスで使用されているプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-220">Kind of process failure used in the [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) interface.</span></span>
[<span data-ttu-id="cbe9d-221">WEBVIEW2_PERMISSION_TYPE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-221">WEBVIEW2_PERMISSION_TYPE</span></span>](#webview2_permission_type) | <span data-ttu-id="cbe9d-222">アクセス許可要求の種類。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-222">The type of a permission request.</span></span>
[<span data-ttu-id="cbe9d-223">WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-223">WEBVIEW2_PERMISSION_STATE</span></span>](#webview2_permission_state) | <span data-ttu-id="cbe9d-224">アクセス許可要求に対する応答。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-224">Response to a permission request.</span></span>
[<span data-ttu-id="cbe9d-225">WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="cbe9d-225">WEBVIEW2_MOVE_FOCUS_REASON</span></span>](#webview2_move_focus_reason) | <span data-ttu-id="cbe9d-226">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-226">Reason for moving focus.</span></span>
[<span data-ttu-id="cbe9d-227">WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="cbe9d-227">WEBVIEW2_WEB_ERROR_STATUS</span></span>](#webview2_web_error_status) | <span data-ttu-id="cbe9d-228">Web ナビゲーションのエラー状態の値。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-228">Error status values for web navigations.</span></span>
[<span data-ttu-id="cbe9d-229">WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-229">WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span>](#webview2_web_resource_context) | <span data-ttu-id="cbe9d-230">Web リソース要求コンテキストの列挙。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-230">Enum for web resource request contexts.</span></span>

## <span data-ttu-id="cbe9d-231">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="cbe9d-231">Navigation events</span></span>

<span data-ttu-id="cbe9d-232">ナビゲーションイベントの通常のシーケンスは、NavigationStarting、DocumentStateChanged、Navigationstarting です。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-232">The normal sequence of navigation events is NavigationStarting, DocumentStateChanged and then NavigationCompleted.</span></span>

![dot-inline-dotgraph-1.png](media/dot-inline-dotgraph-1.png)

<span data-ttu-id="cbe9d-234">これは、同じ NavigationId イベント arg を持つナビゲーションイベント用であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-234">Note that this is for navigation events with the same NavigationId event arg.</span></span> <span data-ttu-id="cbe9d-235">異なる NavigationId イベント引数を持つナビゲーションイベントは、重複する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-235">Navigations events with different NavigationId event args may overlap.</span></span> <span data-ttu-id="cbe9d-236">たとえば、ナビゲーションを開始したときに NavigationStarting イベントが発生してから別のナビゲーションを開始した場合は、最初のナビで開始される navigationstarting 後に、2番目のナビゲーションのナビゲートが続いて、2番目のナビゲーションについて、該当するすべてのナビゲーションイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-236">For instance, if you start a navigation wait for its NavigationStarting event and then start another navigation you'll see the NavigationStarting for the first navigate followed by the NavigationStarting of the second navigate, followed by the NavigationCompleted for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span> <span data-ttu-id="cbe9d-237">エラーが発生した場合は、ナビゲーションがエラーページに続いているかどうかによって、DocumentStateChanged イベントが発生していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-237">In error cases there may or may not be a DocumentStateChanged event depending on whether the navigation is continued to an error page.</span></span> <span data-ttu-id="cbe9d-238">HTTP リダイレクトの場合、1つの行に複数の NavigationStarting イベントが存在します。最初の列の後には、IsRedirect フラグが設定されています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-238">In case of an HTTP redirect, there will be multiple NavigationStarting events in a row, with ones following the first will have their IsRedirect flag set.</span></span>

<span data-ttu-id="cbe9d-239">WebView 内のサブフレームの場合、唯一のナビゲーションイベントは NavigationStarting イベントです。これは、ホストがサブフレームナビゲーションをブロックする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-239">For subframes inside WebView, the only navigation event fired is the NavigationStarting event which gives host the ability to block subframe navigations.</span></span>

## <span data-ttu-id="cbe9d-240">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="cbe9d-240">Process model</span></span>

<span data-ttu-id="cbe9d-241">WebView2 は、Edge web ブラウザーと同じプロセスモデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-241">WebView2 uses the same process model as the Edge web browser.</span></span> <span data-ttu-id="cbe9d-242">ユーザーデータディレクトリを指定する WebView2 の呼び出しプロセスを提供するユーザーセッションの指定したユーザーデータディレクトリごとに、1つの Edge ブラウザープロセスが存在します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-242">There is one Edge browser process per specified user data directory in a user session that will serve any WebView2 calling process that specifies that user data directory.</span></span> <span data-ttu-id="cbe9d-243">つまり、1つの Edge ブラウザープロセスが複数の通話プロセスを処理している可能性があり、1つの呼び出しプロセスが複数の Edge ブラウザープロセスを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-243">This means one Edge browser process may be serving multiple calling processes and one calling process may be using multiple Edge browser processes.</span></span>

![dot-inline-dotgraph-2.png](media/dot-inline-dotgraph-2.png)

<span data-ttu-id="cbe9d-245">ブラウザープロセスが表示されない場合は、いくつかのレンダラープロセスが存在します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-245">Off of a browser process there will be some number of renderer processes.</span></span> <span data-ttu-id="cbe9d-246">これらは、さまざまな WebViews で複数のフレームを処理するために必要に応じて作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-246">These are created as necessary to service potentially multiple frames in different WebViews.</span></span> <span data-ttu-id="cbe9d-247">レンダラープロセスの数は、サイト分離ブラウザー機能と、関連付けられている WebViews でレンダリングされた個別の切断元の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-247">The number of renderer processes varies based on the site isolation browser feature and the number of distinct disconnected origins rendered in associated WebViews.</span></span>

![dot-inline-dotgraph-3.png](media/dot-inline-dotgraph-3.png)

<span data-ttu-id="cbe9d-249">クラッシュとハングに対処するには、これらのブラウザーと ProcessFailure イベントを使ってプロセスをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-249">You can react to crashes and hangs in these browser and renderer processes using the ProcessFailure event.</span></span>

<span data-ttu-id="cbe9d-250">Close メソッドを使用して、関連するブラウザーとレンダラープロセスを安全にシャットダウンできます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-250">You can safely shutdown associated browser and renderer processes using the Close method.</span></span>

## <span data-ttu-id="cbe9d-251">スレッドモデル</span><span class="sxs-lookup"><span data-stu-id="cbe9d-251">Threading model</span></span>

<span data-ttu-id="cbe9d-252">WebView2 は、UI スレッドで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-252">The WebView2 must be created on a UI thread.</span></span> <span data-ttu-id="cbe9d-253">特にメッセージポンプを持つスレッド。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-253">Specifically a thread with a message pump.</span></span> <span data-ttu-id="cbe9d-254">すべてのコールバックがそのスレッドで発生し、WebView への呼び出しはそのスレッドで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-254">All callbacks will occur on that thread and calls into the WebView must be done on that thread.</span></span> <span data-ttu-id="cbe9d-255">他のスレッドから WebView を使うことは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-255">It is not safe to use the WebView from another thread.</span></span>

<span data-ttu-id="cbe9d-256">イベントハンドラーと完了ハンドラーを含むコールバックは逐次実行されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-256">Callbacks including event handlers and completion handlers execute serially.</span></span> <span data-ttu-id="cbe9d-257">つまり、イベントハンドラーを実行していて、メッセージループを開始した場合、他のイベントハンドラーまたは完了コールバックによって reentrantly の実行が開始されません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-257">That is, if you have an event handler running and begin a message loop no other event handlers or completion callbacks will begin executing reentrantly.</span></span>

## <span data-ttu-id="cbe9d-258">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="cbe9d-258">Security</span></span>

<span data-ttu-id="cbe9d-259">実行前に、必ず WebView の Source プロパティを確認してください。 Executesscript、PostWebMessageAsJson、Postwebmessageasjson などのメソッドを使って、WebView に情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-259">Always check the Source property of the WebView before using ExecuteScript, PostWebMessageAsJson, PostWebMessageAsString, or any other method to send information into the WebView.</span></span> <span data-ttu-id="cbe9d-260">ナビゲーションを引き起こしているページのページまたはスクリプトをエンドユーザーが操作している場合、WebView が別のページに移動している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-260">The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation.</span></span> <span data-ttu-id="cbe9d-261">同様に、AddScriptToExecuteOnDocumentCreated には細心の注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-261">Similarly, be very careful with AddScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="cbe9d-262">今後のすべてのナビゲーションでは、このスクリプトが実行され、特定の元にのみ意図した情報へのアクセスを提供している場合、HTML ドキュメントはすべて、アクセス権を持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-262">All future navigations will run this script and if it provides access to information intended only for a certain origin, any HTML document may have access.</span></span>

<span data-ttu-id="cbe9d-263">ExecuteScript の呼び出しの結果を調べるとき、WebMessageReceived イベントが発生した場合、または WebView の HTML ドキュメントから情報を受信するその他のメカニズムを確認する場合は、HTML ドキュメントの URI が予期したとおりであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-263">When examining the result of an ExecuteScript method call, a WebMessageReceived event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.</span></span>

<span data-ttu-id="cbe9d-264">WebView に送信するメッセージを構築する場合は、PostWebMessageAsJson の使用をお勧めし、JSON ライブラリを使って JSON 文字列パラメーターを構築します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-264">When constructing a message to send into a WebView, prefer using PostWebMessageAsJson and construct the JSON string parameter using a JSON library.</span></span> <span data-ttu-id="cbe9d-265">これにより、JSON 文字列またはスクリプトへのエンコード情報の発生を回避することができます。また、攻撃者によって制御される入力によって、残りの JSON メッセージを変更したり、任意のスクリプトを実行したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-265">This will avoid any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script.</span></span>

## <span data-ttu-id="cbe9d-266">文字列型</span><span class="sxs-lookup"><span data-stu-id="cbe9d-266">String types</span></span>

<span data-ttu-id="cbe9d-267">文字列 out パラメーターは、LPWSTR null で終了された文字列です。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-267">String out parameters are LPWSTR null terminated strings.</span></span> <span data-ttu-id="cbe9d-268">呼び出し先は、、Cotaskmemalloc を使って文字列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-268">The callee allocates the string using CoTaskMemAlloc.</span></span> <span data-ttu-id="cbe9d-269">所有権は、呼び出し元に転送され、CoTaskMemFree を使ってメモリを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-269">Ownership is transferred to the caller and it is up to the caller to free the memory using CoTaskMemFree.</span></span>

<span data-ttu-id="cbe9d-270">パラメーター内の文字列は、LPCWSTR null で終了する文字列です。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-270">String in parameters are LPCWSTR null terminated strings.</span></span> <span data-ttu-id="cbe9d-271">呼び出し元は、同期関数呼び出しの間、文字列が有効であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-271">The caller ensures the string is valid for the duration of the synchronous function call.</span></span> <span data-ttu-id="cbe9d-272">呼び出し先がその値を関数呼び出しが完了した後のある時点まで保持する必要がある場合、呼び出し元は、その値の文字列値のコピーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-272">If the callee needs to retain that value to some point after the function call completes, the callee must allocate its own copy of the string value.</span></span>

## <span data-ttu-id="cbe9d-273">URI と JSON の解析</span><span class="sxs-lookup"><span data-stu-id="cbe9d-273">URI and JSON parsing</span></span>

<span data-ttu-id="cbe9d-274">さまざまなメソッドで Uri と JSON を文字列として指定または受け入れます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-274">Various methods provide or accept URIs and JSON as strings.</span></span> <span data-ttu-id="cbe9d-275">これらの文字列の解析と生成には、独自の好みのライブラリを使用してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-275">Please use your own preferred library for parsing and generating these strings.</span></span>

<span data-ttu-id="cbe9d-276">アプリで WinRT が利用できる場合は `RuntimeClass_Windows_Data_Json_JsonObject` 、 `IJsonObjectStatics` JSON 文字列の解析または生成、 `RuntimeClass_Windows_Foundation_Uri` および uri の解析と生成を行うことができ `IUriRuntimeClassFactory` ます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-276">If WinRT is available for your app you can use `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` to parse and produce URIs.</span></span> <span data-ttu-id="cbe9d-277">これらはどちらも Win32 アプリで動作します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-277">Both of these work in Win32 apps.</span></span>

<span data-ttu-id="cbe9d-278">IUri と CreateUri を使って Uri を解析する場合は、次の URI の作成フラグを使って、WebView の URI 解析とより厳密に一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-278">If you use IUri and CreateUri to parse URIs you may want to use the following URI creation flags to have CreateUri behavior more closely match the URI parsing in the WebView:</span></span> `Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO`

## <span data-ttu-id="cbe9d-279">デバッグ</span><span class="sxs-lookup"><span data-stu-id="cbe9d-279">Debugging</span></span>

<span data-ttu-id="cbe9d-280">標準のショートカット (または) で DevTools を開く。 `F12` `Ctrl+Shift+I`</span><span class="sxs-lookup"><span data-stu-id="cbe9d-280">Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`.</span></span> <span data-ttu-id="cbe9d-281">`--auto-open-devtools-for-tabs`コマンド引数スイッチを使うと、WebView を最初に作成したときに、DevTools ウィンドウをすぐに開くことができます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-281">You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView.</span></span> <span data-ttu-id="cbe9d-282">ブラウザープロセスに追加のコマンドライン引数を指定する方法については、CreateWebView のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-282">See CreateWebView documentation for how to provide additional command line arguments to the browser process.</span></span> <span data-ttu-id="cbe9d-283">WebView2 のさまざまなビルドを実行する場合は、CreateWebView ドキュメントでアプリケーションを変更せずに、LoaderOverride レジストリキーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-283">Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateWebView documentation.</span></span>

## <span data-ttu-id="cbe9d-284">バージョン</span><span class="sxs-lookup"><span data-stu-id="cbe9d-284">Versioning</span></span>

<span data-ttu-id="cbe9d-285">特定のバージョンの SDK を使ってアプリをビルドすると、アプリは、インストールされているブラウザーバイナリの以前のバージョンまたは新しいバージョンで終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-285">After you've used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.</span></span> <span data-ttu-id="cbe9d-286">WebView2 のバージョン1.0.0.0 以降では、更新中に、SDK がインストールされているブラウザーバイナリのさまざまなバージョンで動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-286">Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that will prevent your SDK from working with different versions of installed browser binaries.</span></span> <span data-ttu-id="cbe9d-287">バージョン1.0.0.0 以降の SDK では、次のベストプラクティスに従って、インストールされているブラウザーのさまざまなバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-287">After version 1.0.0.0 different versions of the SDK can work with different versions of the installed browser by following these best practices:</span></span>

<span data-ttu-id="cbe9d-288">API への変更を考慮するために、DLL エクスポート CreateWebView2Environment を呼び出すときや、いずれかの WebView2 オブジェクトで QueryInterface を呼び出す場合は、エラーかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-288">To account for breaking changes to the API be sure to check for failure when calling the DLL export CreateWebView2Environment and when calling QueryInterface on any WebView2 object.</span></span> <span data-ttu-id="cbe9d-289">E_NOINTERFACE の戻り値は、SDK が Edge ブラウザーのバイナリと互換性がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-289">A return value of E_NOINTERFACE can indicate the SDK is not compatible with the Edge browser binaries.</span></span>

<span data-ttu-id="cbe9d-290">QueryInterface からのエラーのチェックは、SDK が Edge ブラウザーのバージョンよりも新しい場合や、アプリが Edge ブラウザーに認識されないインターフェイスを使用しようとした場合にも考慮されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-290">Checking for failure from QueryInterface will also account for cases where the SDK is newer than the version of the Edge browser and your app attempts to use an interface of which the Edge browser is unaware.</span></span>

<span data-ttu-id="cbe9d-291">インターフェイスが利用できない場合は、可能であれば関連する機能を無効にするか、ブラウザーを更新する必要があることをエンドユーザーに知らせることができます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-291">When an interface is unavailable, you can consider disabling the associated feature if possible, or otherwise informing the end user they need to update their browser.</span></span>

## <span data-ttu-id="cbe9d-292">Members</span><span class="sxs-lookup"><span data-stu-id="cbe9d-292">Members</span></span>

#### <span data-ttu-id="cbe9d-293">get_Settings</span><span class="sxs-lookup"><span data-stu-id="cbe9d-293">get_Settings</span></span> 

<span data-ttu-id="cbe9d-294">[IWebView2Settings](IWebView2Settings.md)オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-294">The [IWebView2Settings](IWebView2Settings.md) object contains various modifiable settings for the running WebView.</span></span>

> <span data-ttu-id="cbe9d-295">パブリック HRESULT [get_Settings](#get_settings)([IWebView2Settings](IWebView2Settings.md) \* \* 設定)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-295">public HRESULT [get_Settings](#get_settings)([IWebView2Settings](IWebView2Settings.md) \*\* settings)</span></span>

#### <span data-ttu-id="cbe9d-296">get_Source</span><span class="sxs-lookup"><span data-stu-id="cbe9d-296">get_Source</span></span> 

<span data-ttu-id="cbe9d-297">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-297">The URI of the current top level document.</span></span>

> <span data-ttu-id="cbe9d-298">パブリック HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-298">public HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span></span>

<span data-ttu-id="cbe9d-299">この値は、別のサイトやフラグメントナビゲーションへの移動など、一部の状況では、DocumentStateChanged イベントの発生の一部として変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-299">This value potentially changes as a part of the DocumentStateChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="cbe9d-300">ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションにも同じように表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-300">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_documentStateChangedToken));
```

#### <span data-ttu-id="cbe9d-301">検索</span><span class="sxs-lookup"><span data-stu-id="cbe9d-301">Navigate</span></span> 

<span data-ttu-id="cbe9d-302">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-302">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="cbe9d-303">パブリック HRESULT[移動](#navigate)(LPCWSTR uri)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-303">public HRESULT [Navigate](#navigate)(LPCWSTR uri)</span></span>

<span data-ttu-id="cbe9d-304">詳細については、ナビゲーションイベントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-304">See the navigation events for more information.</span></span> <span data-ttu-id="cbe9d-305">これによってナビゲーションが開始されることに注意してください。この操作が完了すると、対応する NavigationStarting イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-305">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

```cpp
void ControlComponent::NavigateToAddressBar()
{
    WCHAR uri[2048] = L"";
    GetWindowText(m_toolbar->addressBarWindow, uri, ARRAYSIZE(uri));
    CHECK_FAILURE(m_webView->Navigate(uri));
}
```

#### <span data-ttu-id="cbe9d-306">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-306">MoveFocus</span></span> 

<span data-ttu-id="cbe9d-307">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-307">Move focus into WebView.</span></span>

> <span data-ttu-id="cbe9d-308">パブリック HRESULT [MoveFocus](#movefocus)([WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)の理由)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-308">public HRESULT [MoveFocus](#movefocus)([WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason) reason)</span></span>

<span data-ttu-id="cbe9d-309">WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-309">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="cbe9d-310">プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-310">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="cbe9d-311">次の理由から、フォーカスは最初の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-311">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="cbe9d-312">前の理由から、フォーカスは最後の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-312">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="cbe9d-313">また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-313">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="cbe9d-314">Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-314">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="cbe9d-315">または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-315">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="cbe9d-316">プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-316">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="cbe9d-317">WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-317">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

```cpp
    while (GetMessage(&msg, nullptr, 0, 0))
    {
        if (!TranslateAccelerator(msg.hwnd, hAccelTable, &msg))
        {
            // Calling IsDialogMessage handles Tab traversal automatically. If the
            // app wants the platform to auto handle tab, then call IsDialogMessage
            // before calling TranslateMessage/DispatchMessage. If the app wants to
            // handle tabbing itself, then skip calling IsDialogMessage and call
            // TranslateMessage/DispatchMessage directly.
            if (!g_autoTabHandle || !IsDialogMessage(GetAncestor(msg.hwnd, GA_ROOT), &msg))
            {
                TranslateMessage(&msg);
                DispatchMessage(&msg);
            }
        }
    }
```

```cpp
        if (wParam == VK_TAB)
        {
            // Find out if the window is one we've customized for tab handling
            for (int i = 0; i < m_tabbableWindows.size(); i++)
            {
                if (m_tabbableWindows[i].first == hWnd)
                {
                    if (GetKeyState(VK_SHIFT) < 0)
                    {
                        TabBackwards(i);
                    }
                    else
                    {
                        TabForwards(i);
                    }
                    return true;
                }
            }
        }
```

```cpp
void ControlComponent::TabForwards(int currentIndex)
{
    // Find first enabled window after the active one
    for (int i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_NEXT);
}

void ControlComponent::TabBackwards(int currentIndex)
{
    // Find first enabled window before the active one
    for (int i = currentIndex - 1; i >= 0; i--)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    CHECK_FAILURE(m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### <span data-ttu-id="cbe9d-318">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="cbe9d-318">NavigateToString</span></span> 

<span data-ttu-id="cbe9d-319">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-319">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="cbe9d-320">パブリック HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-320">public HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlContent)</span></span>

<span data-ttu-id="cbe9d-321">HtmlContent パラメーターの文字数は 2 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-321">The htmlContent parameter may not be larger than 2 MB of characters.</span></span> <span data-ttu-id="cbe9d-322">新しいページの起点は "空白" になります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-322">The origin of the new page will be about:blank.</span></span>

```cpp
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### <span data-ttu-id="cbe9d-323">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="cbe9d-323">add_NavigationStarting</span></span> 

<span data-ttu-id="cbe9d-324">NavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-324">Add an event handler for the NavigationStarting event.</span></span>

> <span data-ttu-id="cbe9d-325">パブリック HRESULT [add_NavigationStarting](#add_navigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-325">public HRESULT [add_NavigationStarting](#add_navigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-326">NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-326">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="cbe9d-327">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-327">This will fire for redirects as well.</span></span>

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            if (userInitiated)
            {
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
            }
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

#### <span data-ttu-id="cbe9d-328">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="cbe9d-328">remove_NavigationStarting</span></span> 

<span data-ttu-id="cbe9d-329">Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-329">Remove an event handler previously added with add_NavigationStarting.</span></span>

> <span data-ttu-id="cbe9d-330">パブリック HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-330">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-331">add_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="cbe9d-331">add_DocumentStateChanged</span></span> 

<span data-ttu-id="cbe9d-332">DocumentStateChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-332">Add an event handler for the DocumentStateChanged event.</span></span>

> <span data-ttu-id="cbe9d-333">パブリック HRESULT [add_DocumentStateChanged](#add_documentstatechanged)([IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-333">public HRESULT [add_DocumentStateChanged](#add_documentstatechanged)([IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-334">DocumentStateChanged は、webview のメインフレームでの読み込みが開始されたとき、または同じページナビゲーション (フラグメントナビゲーションや履歴の推移など) が発生した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-334">DocumentStateChanged fires when new content has started loading on the webview's main frame or if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span> <span data-ttu-id="cbe9d-335">これは、NavigationStarting イベントの後に、Navigationstarting イベントの前に続きます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-335">This follows the NavigationStarting event and precedes the NavigationCompleted event.</span></span>

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_documentStateChangedToken));
```

#### <span data-ttu-id="cbe9d-336">remove_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="cbe9d-336">remove_DocumentStateChanged</span></span> 

<span data-ttu-id="cbe9d-337">Add_DocumentStateChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-337">Remove an event handler previously added with add_DocumentStateChanged.</span></span>

> <span data-ttu-id="cbe9d-338">パブリック HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-338">public HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-339">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="cbe9d-339">add_NavigationCompleted</span></span> 

<span data-ttu-id="cbe9d-340">NavigationCompleted イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-340">Add an event handler for the NavigationCompleted event.</span></span>

> <span data-ttu-id="cbe9d-341">パブリック HRESULT [add_NavigationCompleted](#add_navigationcompleted)([IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-341">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)([IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-342">NavigationCompleted イベントは、WebView が完全に読み込まれたとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-342">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

```cpp
    // Register a handler for the NavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    // Also update the Back, Forward, and Cancel buttons.
    CHECK_FAILURE(m_webView->add_NavigationCompleted(
        Callback<IWebView2NavigationCompletedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    WEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }

                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                EnableWindow(m_toolbar->backWindow, canGoBack);
                EnableWindow(m_toolbar->forwardWindow, canGoForward);
                EnableWindow(m_toolbar->cancelWindow, FALSE);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### <span data-ttu-id="cbe9d-343">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="cbe9d-343">remove_NavigationCompleted</span></span> 

<span data-ttu-id="cbe9d-344">Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-344">Remove an event handler previously added with add_NavigationCompleted.</span></span>

> <span data-ttu-id="cbe9d-345">パブリック HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-345">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-346">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="cbe9d-346">add_FrameNavigationStarting</span></span> 

<span data-ttu-id="cbe9d-347">FrameNavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-347">Add an event handler for the FrameNavigationStarting event.</span></span>

> <span data-ttu-id="cbe9d-348">パブリック HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-348">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-349">FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-349">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="cbe9d-350">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-350">This will fire for redirects as well.</span></span>

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
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

#### <span data-ttu-id="cbe9d-351">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="cbe9d-351">remove_FrameNavigationStarting</span></span> 

<span data-ttu-id="cbe9d-352">Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-352">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>

> <span data-ttu-id="cbe9d-353">パブリック HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-353">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-354">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-354">add_MoveFocusRequested</span></span> 

<span data-ttu-id="cbe9d-355">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-355">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="cbe9d-356">パブリック HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-356">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-357">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-357">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="cbe9d-358">このイベントが発生すると、WebView のフォーカスが変更されません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-358">The WebView's focus has not changed when this event is fired.</span></span>

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_webView->add_MoveFocusRequested(
        Callback<IWebView2MoveFocusRequestedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2MoveFocusRequestedEventArgs* args)
                -> HRESULT {
                if (!g_autoTabHandle)
                {
                    WEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == WEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
                    {
                        TabBackwards(int(m_tabbableWindows.size()));
                    }
                    CHECK_FAILURE(args->put_Handled(TRUE));
                }
                return S_OK;
            })
            .Get(),
        &m_moveFocusRequestedToken));
```

#### <span data-ttu-id="cbe9d-359">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-359">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="cbe9d-360">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-360">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="cbe9d-361">パブリック HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-361">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-362">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-362">add_GotFocus</span></span> 

<span data-ttu-id="cbe9d-363">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-363">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="cbe9d-364">パブリック HRESULT [add_GotFocus](#add_gotfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-364">public HRESULT [add_GotFocus](#add_gotfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-365">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-365">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="cbe9d-366">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-366">remove_GotFocus</span></span> 

<span data-ttu-id="cbe9d-367">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-367">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="cbe9d-368">パブリック HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-368">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-369">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-369">add_LostFocus</span></span> 

<span data-ttu-id="cbe9d-370">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-370">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="cbe9d-371">パブリック HRESULT [add_LostFocus](#add_lostfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-371">public HRESULT [add_LostFocus](#add_lostfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-372">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-372">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="cbe9d-373">MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-373">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="cbe9d-374">フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-374">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="cbe9d-375">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="cbe9d-375">remove_LostFocus</span></span> 

<span data-ttu-id="cbe9d-376">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-376">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="cbe9d-377">パブリック HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-377">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-378">add_WebResourceRequested_deprecated</span><span class="sxs-lookup"><span data-stu-id="cbe9d-378">add_WebResourceRequested_deprecated</span></span> 

<span data-ttu-id="cbe9d-379">この API は廃止されます。新しい add_WebResourceRequested API を使用してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-379">This API will be deprecated, please use the new add_WebResourceRequested API.</span></span>

> <span data-ttu-id="cbe9d-380">パブリック HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)(LPCWSTR \* Const urlfilter、[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) \* Const ResourceContextFilter、SIZE_T filterlength、[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-380">public HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)(LPCWSTR \*const urlFilter,[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) \*const resourceContextFilter,SIZE_T filterLength,[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-381">WebResourceRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-381">Add an event handler for the WebResourceRequested event.</span></span> <span data-ttu-id="cbe9d-382">WebView が HTTP 要求を実行したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-382">Fires when the WebView has performs any HTTP request.</span></span> <span data-ttu-id="cbe9d-383">UrlFilter を使って、リッスンする url のサイズフィルターの長さを指定してリストを渡します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-383">Use urlFilter to pass in a list with size filterLength of urls to listen for.</span></span> <span data-ttu-id="cbe9d-384">各 url エントリでもワイルドカードをサポートしています。 ' \* ' は0個以上の文字と一致し、"?" は1文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-384">Each url entry also supports wildcards: '\*' matches zero or more characters, and '?' matches exactly one character.</span></span> <span data-ttu-id="cbe9d-385">UrlFilter の各エントリについて、WebResourceRequested を起動する必要があるリソースの種類を表す、一致する resourceContextFilter を提供します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-385">For each urlFilter entry, provide a matching resourceContextFilter representing the types of resources for which WebResourceRequested should fire.</span></span> <span data-ttu-id="cbe9d-386">FilterLength が0の場合、イベントはすべてのネットワーク要求に対して発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-386">If filterLength is 0, the event will fire for all network requests.</span></span> <span data-ttu-id="cbe9d-387">サポートされているリソースコンテキストは、ドキュメント、スタイルシート、画像、メディア、フォント、スクリプト、XHR、取得です。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-387">The supported resource contexts are: Document, Stylesheet, Image, Media, Font, Script, XHR, Fetch.</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<IWebView2WebResourceRequestedEventHandler>(
                    [this](
                        IWebView2WebView* sender,
                        IWebView2WebResourceRequestedEventArgs* args) {
                        wil::com_ptr<IWebView2WebResourceRequestedEventArgs2>
                            webResourceEventArgs2;
                        args->QueryInterface(IID_PPV_ARGS(&webResourceEventArgs2));
                        WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            webResourceEventArgs2->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<IWebView2WebResourceResponse> response;
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

#### <span data-ttu-id="cbe9d-388">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-388">remove_WebResourceRequested</span></span> 

<span data-ttu-id="cbe9d-389">Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-389">Remove an event handler previously added with add_WebResourceRequested.</span></span>

> <span data-ttu-id="cbe9d-390">パブリック HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-390">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-391">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="cbe9d-391">add_ScriptDialogOpening</span></span> 

<span data-ttu-id="cbe9d-392">Scriptの開始イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-392">Add an event handler for the ScriptDialogOpening event.</span></span>

> <span data-ttu-id="cbe9d-393">パブリック HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-393">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-394">イベントは、webview の JavaScript ダイアログ (警告、確認、またはプロンプト) が表示されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-394">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span> <span data-ttu-id="cbe9d-395">このイベントは、IWebView2Settings:: Aredefaultscript プロパティが false に設定されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-395">This event only fires if the IWebView2Settings::AreDefaultScriptDialogsEnabled property is set to false.</span></span>

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<IWebView2ScriptDialogOpeningEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<IWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            WEBVIEW2_SCRIPT_DIALOG_KIND type;
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
                /* readonly */ type != WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<IWebView2Deferral> deferral;
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

#### <span data-ttu-id="cbe9d-396">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="cbe9d-396">remove_ScriptDialogOpening</span></span> 

<span data-ttu-id="cbe9d-397">Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-397">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>

> <span data-ttu-id="cbe9d-398">パブリック HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-398">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-399">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="cbe9d-399">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="cbe9d-400">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-400">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="cbe9d-401">パブリック HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-401">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-402">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-402">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="cbe9d-403">呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-403">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="cbe9d-404">ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-404">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="cbe9d-405">WebView は、各サイトで使用されている直前の拡大率を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-405">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="cbe9d-406">そのため、別のページに移動するときにズーム倍率が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-406">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="cbe9d-407">このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは DocumentStateChanged イベントの直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-407">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the DocumentStateChanged event.</span></span>

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_webView->add_ZoomFactorChanged(
        Callback<IWebView2ZoomFactorChangedEventHandler>(
            [this](IWebView2WebView* sender, IUnknown* args) -> HRESULT {
                double zoomFactor;
                CHECK_FAILURE(sender->get_ZoomFactor(&zoomFactor));

                std::wstring message = L"WebView2APISample (Zoom: " +
                                       std::to_wstring(int(zoomFactor * 100)) + L"%)";
                SetWindowText(m_appWindow->GetMainWindow(), message.c_str());
                return S_OK;
            })
            .Get(),
        &m_zoomFactorChangedToken));
```

#### <span data-ttu-id="cbe9d-408">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="cbe9d-408">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="cbe9d-409">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-409">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="cbe9d-410">パブリック HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-410">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-411">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-411">add_PermissionRequested</span></span> 

<span data-ttu-id="cbe9d-412">PermissionRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-412">Add an event handler for the PermissionRequested event.</span></span>

> <span data-ttu-id="cbe9d-413">パブリック HRESULT [add_PermissionRequested](#add_permissionrequested)([IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-413">public HRESULT [add_PermissionRequested](#add_permissionrequested)([IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-414">WebView のコンテンツが権限のある一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-414">Fires when content in a WebView requests permission to access some privileged resources.</span></span>

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<IWebView2PermissionRequestedEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        WEBVIEW2_PERMISSION_TYPE type = WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionType(&type));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionType(type);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        WEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? WEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? WEBVIEW2_PERMISSION_STATE_DENY
            :                     WEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### <span data-ttu-id="cbe9d-415">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="cbe9d-415">remove_PermissionRequested</span></span> 

<span data-ttu-id="cbe9d-416">Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-416">Remove an event handler previously added with add_PermissionRequested.</span></span>

> <span data-ttu-id="cbe9d-417">パブリック HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-417">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-418">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="cbe9d-418">add_ProcessFailed</span></span> 

<span data-ttu-id="cbe9d-419">ProcessFailed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-419">Add an event handler for the ProcessFailed event.</span></span>

> <span data-ttu-id="cbe9d-420">パブリック HRESULT [add_ProcessFailed](#add_processfailed)([IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-420">public HRESULT [add_ProcessFailed](#add_processfailed)([IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-421">WebView プロセスが予期せず終了した場合、または応答不能になったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-421">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<IWebView2ProcessFailedEventHandler>(
            [this](IWebView2WebView* sender,
                IWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        WEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
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
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### <span data-ttu-id="cbe9d-422">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="cbe9d-422">remove_ProcessFailed</span></span> 

<span data-ttu-id="cbe9d-423">Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-423">Remove an event handler previously added with add_ProcessFailed.</span></span>

> <span data-ttu-id="cbe9d-424">パブリック HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-424">public HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-425">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="cbe9d-425">AddScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="cbe9d-426">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-426">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="cbe9d-427">パブリック HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR JavaScript、[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-427">public HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR javaScript,[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="cbe9d-428">挿入されたスクリプトは、RemoveScriptToExecuteOnDocumentCreated で削除されるまで、将来のすべての上位レベルのドキュメントと子フレームのナビゲーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-428">The injected script will apply to all future top level document and child frame navigations until removed with RemoveScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="cbe9d-429">これは非同期的に適用されるため、今後のナビゲーションでスクリプトを実行する準備ができていることを確認する前に、完了ハンドラーが実行されるまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-429">This is applied asynchronously and you must wait for the completion handler to run before you can be sure that the script is ready to execute on future navigations.</span></span>

<span data-ttu-id="cbe9d-430">[サンドボックス](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)のプロパティまたは[コンテンツセキュリティポリシーの HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)によって、HTML ドキュメントに何らかのサンドボックスが含まれている場合は、このスクリプトの実行に影響します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-430">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="cbe9d-431">たとえば、' allow als ' キーワードが設定されていない場合、関数への呼び出し `alert` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-431">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

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
            Callback<IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### <span data-ttu-id="cbe9d-432">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="cbe9d-432">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="cbe9d-433">AddScriptToExecuteOnDocumentCreated によって追加された、対応する JavaScript を削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-433">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>

> <span data-ttu-id="cbe9d-434">パブリック HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-434">public HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span></span>

#### <span data-ttu-id="cbe9d-435">Execuスクリプト</span><span class="sxs-lookup"><span data-stu-id="cbe9d-435">ExecuteScript</span></span> 

<span data-ttu-id="cbe9d-436">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-436">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="cbe9d-437">パブリック HRESULT の[Executescript](#executescript)(LPCWSTR JavaScript、[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-437">public HRESULT [ExecuteScript](#executescript)(LPCWSTR javaScript,[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="cbe9d-438">これは非同期的に実行されます。完了すると、ExecuteScriptCompletedHandler パラメーターでハンドラーが指定されると、指定された JavaScript を評価した結果を使って Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-438">This will execute asynchronously and when complete, if a handler is provided in the ExecuteScriptCompletedHandler parameter, its Invoke method will be called with the result of evaluating the provided JavaScript.</span></span> <span data-ttu-id="cbe9d-439">結果値は、JSON でエンコードされた文字列です。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-439">The result value is a JSON encoded string.</span></span> <span data-ttu-id="cbe9d-440">結果が定義されていない場合、参照循環が含まれている場合、または JSON にエンコードできない場合は、JSON null 値が文字列 ' null ' として返されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-440">If the result is undefined, contains a reference cycle, or otherwise cannot be encoded into JSON, the JSON null value will be returned as the string 'null'.</span></span> <span data-ttu-id="cbe9d-441">明示的な戻り値のない関数は undefined を返します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-441">Note that a function that has no explicit return value returns undefined.</span></span> <span data-ttu-id="cbe9d-442">実行されたスクリプトが未処理の例外をスローした場合、結果は ' null ' にもなります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-442">If the executed script throws an unhandled exception, then the result is also 'null'.</span></span> <span data-ttu-id="cbe9d-443">このメソッドは非同期的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-443">This method is applied asynchronously.</span></span> <span data-ttu-id="cbe9d-444">1つのドキュメントに対して webview を実行しているときに、操作が行われたときに、その呼び出しが行われてから JavaScript が実行される前に、移動が行われると、スクリプトは実行されず、ハンドラーは errorCode パラメーターの E_FAIL で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-444">If the call is made while the webview is on one document, and a navigation occurs after the call is made but before the JavaScript is executed, then the script will not be executed and the handler will be called with E_FAIL for its errorCode parameter.</span></span> <span data-ttu-id="cbe9d-445">実行方法 IsScriptEnabled が FALSE に設定されている場合でも、スクリプトは機能します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-445">ExecuteScript will work even if IsScriptEnabled is set to FALSE.</span></span>

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
            Callback<IWebView2ExecuteScriptCompletedHandler>(
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

#### <span data-ttu-id="cbe9d-446">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="cbe9d-446">CapturePreview</span></span> 

<span data-ttu-id="cbe9d-447">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-447">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="cbe9d-448">パブリック HRESULT [CapturePreview](#capturepreview)([WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) imageformat、IStream \* imagestream、[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-448">public HRESULT [CapturePreview](#capturepreview)([WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) imageFormat,IStream \* imageStream,[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="cbe9d-449">ImageFormat パラメーターを使用して、画像の形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-449">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="cbe9d-450">結果のイメージバイナリデータは、指定された imageStream パラメーターに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-450">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="cbe9d-451">CapturePreview がストリームへの書き込みを終了すると、指定された handler パラメーターの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-451">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

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
            WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<IWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### <span data-ttu-id="cbe9d-452">再</span><span class="sxs-lookup"><span data-stu-id="cbe9d-452">Reload</span></span> 

<span data-ttu-id="cbe9d-453">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-453">Reload the current page.</span></span>

> <span data-ttu-id="cbe9d-454">パブリック HRESULT [Reload](#reload)()</span><span class="sxs-lookup"><span data-stu-id="cbe9d-454">public HRESULT [Reload](#reload)()</span></span>

<span data-ttu-id="cbe9d-455">これは、すべてのナビゲーションイベント (HTTP キャッシュ内のエントリを含む) を含む、現在のトップレベルドキュメントの URI に移動する操作と似ています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-455">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="cbe9d-456">ただし、戻る/forward 履歴は変更されません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-456">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="cbe9d-457">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="cbe9d-457">get_Bounds</span></span> 

<span data-ttu-id="cbe9d-458">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-458">The webview bounds.</span></span>

> <span data-ttu-id="cbe9d-459">パブリック HRESULT [get_Bounds](#get_bounds)(RECT \* 境界)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-459">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="cbe9d-460">境界は親 HWND を基準としています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-460">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="cbe9d-461">アプリには、WebView を配置する2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-461">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="cbe9d-462">WebView 親 HWND である子 HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-462">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="cbe9d-463">WebView が必要な場所にこのウィンドウを配置します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-463">Position this window where the WebView should be.</span></span> <span data-ttu-id="cbe9d-464">この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-464">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="cbe9d-465">アプリの一番上のウィンドウは、WebView 親 HWND として使います。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-465">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="cbe9d-466">Webview の左上隅を、アプリ内で適切に配置されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-466">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="cbe9d-467">バインドされた値は、ホストの座標空間にあります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-467">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="cbe9d-468">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="cbe9d-468">put_Bounds</span></span> 

<span data-ttu-id="cbe9d-469">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-469">Set the Bounds property.</span></span>

> <span data-ttu-id="cbe9d-470">パブリック HRESULT [put_Bounds](#put_bounds)(四角形の境界)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-470">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        (m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio + m_webViewBounds.top);
    desiredBounds.right = LONG(
        (m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio + m_webViewBounds.left);

    m_webView->put_Bounds(desiredBounds);
}
```

#### <span data-ttu-id="cbe9d-471">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="cbe9d-471">get_ZoomFactor</span></span> 

<span data-ttu-id="cbe9d-472">WebView の現在のページのズームファクター。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-472">The zoom factor for the current page in the WebView.</span></span>

> <span data-ttu-id="cbe9d-473">パブリック HRESULT [get_ZoomFactor](#get_zoomfactor)(Double \* ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-473">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="cbe9d-474">ズーム倍率はサイトごとに維持されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-474">The zoom factor is persisted per site.</span></span> <span data-ttu-id="cbe9d-475">ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-475">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="cbe9d-476">WebView を別のサイトからページに移動すると、前のページに設定されているズーム倍率は適用されません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-476">When WebView navigates to a page from a different site, the zoom factor set for the previous page will not be applied.</span></span> <span data-ttu-id="cbe9d-477">アプリで特定のページの拡大率を設定する場合は、最初に DocumentStateChanged イベントハンドラーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-477">If the app wants to set the zoom factor for a certain page, the earliest place to do it is in the DocumentStateChanged event handler.</span></span> <span data-ttu-id="cbe9d-478">これにより、指定されたズームファクターの ZoomFactorChanged イベントを受け取る前に、永続化されたズームファクターの ZoomFactorChanged イベントを受け取ることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-478">Note that if it does that, it might receive a ZoomFactorChanged event for the persisted zoom factor before receiving the ZoomFactorChanged event for the specified zoom factor.</span></span> <span data-ttu-id="cbe9d-479">0以下の zoomFactor を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-479">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="cbe9d-480">WebView には、内部でサポートされているズームファクター範囲もあります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-480">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="cbe9d-481">指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-481">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="cbe9d-482">この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-482">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="cbe9d-483">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="cbe9d-483">put_ZoomFactor</span></span> 

<span data-ttu-id="cbe9d-484">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-484">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="cbe9d-485">パブリック HRESULT [put_ZoomFactor](#put_zoomfactor)(double ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-485">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="cbe9d-486">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="cbe9d-486">get_IsVisible</span></span> 

<span data-ttu-id="cbe9d-487">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-487">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="cbe9d-488">パブリック HRESULT [get_IsVisible](#get_isvisible)(BOOL \* IsVisible)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-488">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="cbe9d-489">IsVisible が false に設定されている場合、webview は透過的であり、表示されません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-489">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="cbe9d-490">ただし、この操作を行っても、webview (CreateWebView に渡された HWND パラメーター) が含まれているウィンドウには影響しません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-490">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateWebView).</span></span> <span data-ttu-id="cbe9d-491">ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-491">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="cbe9d-492">子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-492">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="cbe9d-493">パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-493">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="cbe9d-494">アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-494">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_webView->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_webView->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="cbe9d-495">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="cbe9d-495">put_IsVisible</span></span> 

<span data-ttu-id="cbe9d-496">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-496">Set the IsVisible property.</span></span>

> <span data-ttu-id="cbe9d-497">パブリック HRESULT [put_IsVisible](#put_isvisible)(BOOL IsVisible)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-497">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_webView->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_webView->put_IsVisible(TRUE);
            }
        }
    }
```

#### <span data-ttu-id="cbe9d-498">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="cbe9d-498">PostWebMessageAsJson</span></span> 

<span data-ttu-id="cbe9d-499">指定した webMessage をこの[IWebView2WebView]()のトップレベルのドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-499">Post the specified webMessage to the top level document in this [IWebView2WebView]().</span></span>

> <span data-ttu-id="cbe9d-500">パブリック HRESULT [Postwebmessageasjson](#postwebmessageasjson)(LPCWSTR webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-500">public HRESULT [PostWebMessageAsJson](#postwebmessageasjson)(LPCWSTR webMessageAsJson)</span></span>

<span data-ttu-id="cbe9d-501">最上位のドキュメントのウィンドウには、"." というメッセージイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-501">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="cbe9d-502">このドキュメントの JavaScript は、次のようにしてイベントをサブスクライブし、サブスクライブを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-502">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span> 

```cpp
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

 <span data-ttu-id="cbe9d-503">イベント引数は、のインスタンス `MessageEvent` です。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-503">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="cbe9d-504">IWebView2Settings:: IsWebMessageEnabled の設定は true である必要があります。また、このメソッドは E_INVALIDARG で失敗します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-504">The IWebView2Settings::IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="cbe9d-505">イベント arg の data プロパティは、JSON 文字列として JavaScript オブジェクトに解析された webMessage 文字列のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-505">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="cbe9d-506">イベント arg の source プロパティは、オブジェクトへの参照です `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-506">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="cbe9d-507">Webview の HTML ドキュメントからホストにメッセージを送信する方法については、「SetWebMessageReceivedEventHandler」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-507">See SetWebMessageReceivedEventHandler for information on sending messages from the HTML document in the webview to the host.</span></span> <span data-ttu-id="cbe9d-508">このメッセージは非同期的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-508">This message is sent asynchronously.</span></span> <span data-ttu-id="cbe9d-509">メッセージがページに投稿される前にナビゲーションが発生した場合、メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-509">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
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

#### <span data-ttu-id="cbe9d-510">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="cbe9d-510">PostWebMessageAsString</span></span> 

<span data-ttu-id="cbe9d-511">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-511">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="cbe9d-512">パブリック HRESULT [Postwebmessageasstring](#postwebmessageasstring)(LPCWSTR webmessageasstring)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-512">public HRESULT [PostWebMessageAsString](#postwebmessageasstring)(LPCWSTR webMessageAsString)</span></span>

<span data-ttu-id="cbe9d-513">これは、PostWebMessageAsJson とまったく同じように動作し `window.chrome.webview` ますが、message イベント arg の data プロパティは、webMessageAsString と同じ値を持つ文字列になります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-513">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="cbe9d-514">JSON オブジェクトではなく単純な文字列を使って通信する場合は、PostWebMessageAsJson の代わりに、これを使います。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-514">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="cbe9d-515">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="cbe9d-515">add_WebMessageReceived</span></span> 

<span data-ttu-id="cbe9d-516">このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-516">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="cbe9d-517">パブリック HRESULT [add_WebMessageReceived](#add_webmessagereceived)([IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) \* handler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-517">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)([IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-518">PostMessage 関数は、 `void postMessage(object)` JSON 変換でサポートされているオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-518">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span>

```cpp
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

 <span data-ttu-id="cbe9d-519">PostMessage が呼び出されると、この SetWebMessageReceivedEventHandler メソッドによって設定された[IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md)が、postMessage のオブジェクトパラメーターを JSON 文字列に変換して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-519">When postMessage is called, the [IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) set via this SetWebMessageReceivedEventHandler method will be invoked with the postMessage's object parameter converted to a JSON string.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
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

#### <span data-ttu-id="cbe9d-520">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="cbe9d-520">remove_WebMessageReceived</span></span> 

<span data-ttu-id="cbe9d-521">Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-521">Remove an event handler previously added with add_WebMessageReceived.</span></span>

> <span data-ttu-id="cbe9d-522">パブリック HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-522">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-523">Close</span><span class="sxs-lookup"><span data-stu-id="cbe9d-523">Close</span></span> 

<span data-ttu-id="cbe9d-524">Webview を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-524">Closes the webview and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="cbe9d-525">パブリック HRESULT [Close](#close)()</span><span class="sxs-lookup"><span data-stu-id="cbe9d-525">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="cbe9d-526">ブラウザーの instace をクリーンアップすると、webview に電源が入っているリソースが解放されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-526">Cleaning up the browser instace will release the resources powering the webview.</span></span> <span data-ttu-id="cbe9d-527">他の webviews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-527">The browser instance will be shut down if there are no other webviews using it.</span></span>

<span data-ttu-id="cbe9d-528">Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-528">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="cbe9d-529">具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-529">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="cbe9d-530">"閉じる" は、WebView が最終的な参照を失い、destructed されたときに暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-530">Close is implicitly called when the WebView loses its final reference and is destructed.</span></span> <span data-ttu-id="cbe9d-531">ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-531">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="cbe9d-532">具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-532">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="cbe9d-533">Close は、すべてのイベントハンドラーを解放することで、このサイクルを中断します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-533">Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="cbe9d-534">ただし、このような状況を回避するには、webview で明示的に Close を呼び出し、webview を適切にクリーンアップするために、WebView への参照をキャプチャしないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-534">But to avoid this situation it is best practice to both explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView()
{
    DeleteAllComponents();
    if (m_webView)
    {
        m_webView->Close();
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
}
```

#### <span data-ttu-id="cbe9d-535">Calldevon Protocolメソッド</span><span class="sxs-lookup"><span data-stu-id="cbe9d-535">CallDevToolsProtocolMethod</span></span> 

<span data-ttu-id="cbe9d-536">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-536">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="cbe9d-537">パブリック HRESULT[呼び出し DevLPCWSTR Protocolmethod](#calldevtoolsprotocolmethod)(METHODNAME、LPCWSTR ParametersAsJson、[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-537">public HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)(LPCWSTR methodName,LPCWSTR parametersAsJson,[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="cbe9d-538">使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-538">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="cbe9d-539">MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-539">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="cbe9d-540">ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-540">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="cbe9d-541">メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-541">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="cbe9d-542">Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-542">Invoke will be called with the method's return object as a JSON string.</span></span>

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
            Callback<IWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### <span data-ttu-id="cbe9d-543">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="cbe9d-543">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="cbe9d-544">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-544">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="cbe9d-545">パブリック HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)(LPCWSTR EventName、[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-545">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)(LPCWSTR eventName,[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="cbe9d-546">使用できるイベントの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-546">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available events.</span></span> <span data-ttu-id="cbe9d-547">EventName パラメーターは、形式におけるイベントの完全な名前です `{domain}.{event}` 。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-547">The eventName parameter is the full name of the event in the format `{domain}.{event}`.</span></span> <span data-ttu-id="cbe9d-548">ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-548">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="cbe9d-549">Invoke は、JSON 文字列として CDP イベントのパラメーターオブジェクトを含むイベント引数オブジェクトで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-549">Invoke will be called with the an event args object containing the CDP event's parameter object as a JSON string.</span></span>

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
        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(m_webView->remove_DevToolsProtocolEventReceived(
                eventName.c_str(),
                preexistingToken->second));
        }

        CHECK_FAILURE(m_webView->add_DevToolsProtocolEventReceived(
            eventName.c_str(),
            Callback<IWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](IWebView2WebView* sender,
                            IWebView2DevToolsProtocolEventReceivedEventArgs* args)
                -> HRESULT
        {
            wil::unique_cotaskmem_string parameterObjectAsJson;
            CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
            MessageBox(nullptr, parameterObjectAsJson.get(),
                       (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
            return S_OK;
        }).Get(), &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### <span data-ttu-id="cbe9d-550">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="cbe9d-550">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="cbe9d-551">Add_DevToolsProtocolEventReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-551">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="cbe9d-552">パブリック HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(LPCWSTR EventName, EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-552">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(LPCWSTR eventName,EventRegistrationToken token)</span></span>

#### <span data-ttu-id="cbe9d-553">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="cbe9d-553">get_BrowserProcessId</span></span> 

<span data-ttu-id="cbe9d-554">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-554">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="cbe9d-555">パブリック HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* 値)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-555">public HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* value)</span></span>

#### <span data-ttu-id="cbe9d-556">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="cbe9d-556">get_CanGoBack</span></span> 

<span data-ttu-id="cbe9d-557">Webview をナビゲーション履歴の前のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-557">Can navigate the webview to the previous page in the navigation history.</span></span>

> <span data-ttu-id="cbe9d-558">パブリック HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* CanGoBack)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-558">public HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* canGoBack)</span></span>

<span data-ttu-id="cbe9d-559">DocumentStateChanged イベントを使用して値を変更 get_CanGoBack ます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-559">get_CanGoBack change value with the DocumentStateChanged event.</span></span>

#### <span data-ttu-id="cbe9d-560">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="cbe9d-560">get_CanGoForward</span></span> 

<span data-ttu-id="cbe9d-561">Webview をナビゲーション履歴の次のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-561">Can navigate the webview to the next page in the navigation history.</span></span>

> <span data-ttu-id="cbe9d-562">パブリック HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* CanGoForward)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-562">public HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* canGoForward)</span></span>

<span data-ttu-id="cbe9d-563">DocumentStateChanged イベントを使用して値を変更 get_CanGoForward ます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-563">get_CanGoForward change value with the DocumentStateChanged event.</span></span>

#### <span data-ttu-id="cbe9d-564">GoBack</span><span class="sxs-lookup"><span data-stu-id="cbe9d-564">GoBack</span></span> 

<span data-ttu-id="cbe9d-565">ナビゲーション履歴で、webview を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-565">Navigates the webview to the previous page in the navigation history.</span></span>

> <span data-ttu-id="cbe9d-566">パブリック HRESULT [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="cbe9d-566">public HRESULT [GoBack](#goback)()</span></span>

#### <span data-ttu-id="cbe9d-567">GoForward</span><span class="sxs-lookup"><span data-stu-id="cbe9d-567">GoForward</span></span> 

<span data-ttu-id="cbe9d-568">Webview をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-568">Navigates the webview to the next page in the navigation history.</span></span>

> <span data-ttu-id="cbe9d-569">パブリック HRESULT [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="cbe9d-569">public HRESULT [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="cbe9d-570">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-570">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span> 

<span data-ttu-id="cbe9d-571">[IWebView2WebView:: CapturePreview](#capturepreview)メソッドで使用されている画像形式。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-571">Image format used by the [IWebView2WebView::CapturePreview](#capturepreview) method.</span></span>

> <span data-ttu-id="cbe9d-572">列挙型[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-572">enum [WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)</span></span>

 <span data-ttu-id="cbe9d-573">値</span><span class="sxs-lookup"><span data-stu-id="cbe9d-573">Values</span></span>                         | <span data-ttu-id="cbe9d-574">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-574">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="cbe9d-575">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span><span class="sxs-lookup"><span data-stu-id="cbe9d-575">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span></span>            | <span data-ttu-id="cbe9d-576">PNG 画像形式。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-576">PNG image format.</span></span>
<span data-ttu-id="cbe9d-577">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span><span class="sxs-lookup"><span data-stu-id="cbe9d-577">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span></span>            | <span data-ttu-id="cbe9d-578">JPEG イメージ形式。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-578">JPEG image format.</span></span>

#### <span data-ttu-id="cbe9d-579">WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="cbe9d-579">WEBVIEW2_SCRIPT_DIALOG_KIND</span></span> 

<span data-ttu-id="cbe9d-580">[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)インターフェイスで使用される JavaScript ダイアログの種類。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-580">Kind of JavaScript dialog used in the [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) interface.</span></span>

> <span data-ttu-id="cbe9d-581">列挙型[WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-581">enum [WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)</span></span>

 <span data-ttu-id="cbe9d-582">値</span><span class="sxs-lookup"><span data-stu-id="cbe9d-582">Values</span></span>                         | <span data-ttu-id="cbe9d-583">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-583">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="cbe9d-584">WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-584">WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span></span>            | <span data-ttu-id="cbe9d-585">ウィンドウで呼び出されるダイアログ。警告 JavaScript 関数。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-585">A dialog invoked via the window.alert JavaScript function.</span></span>
<span data-ttu-id="cbe9d-586">WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span><span class="sxs-lookup"><span data-stu-id="cbe9d-586">WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span></span>            | <span data-ttu-id="cbe9d-587">ウィンドウを通じて呼び出されるダイアログ。 JavaScript 関数を確認してください。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-587">A dialog invoked via the window.confirm JavaScript function.</span></span>
<span data-ttu-id="cbe9d-588">WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-588">WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span></span>            | <span data-ttu-id="cbe9d-589">Window というプロンプトで呼び出されるダイアログ。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-589">A dialog invoked via the window.prompt JavaScript function.</span></span>

#### <span data-ttu-id="cbe9d-590">WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="cbe9d-590">WEBVIEW2_PROCESS_FAILED_KIND</span></span> 

<span data-ttu-id="cbe9d-591">[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)インターフェイスで使用されているプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-591">Kind of process failure used in the [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) interface.</span></span>

> <span data-ttu-id="cbe9d-592">列挙型[WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-592">enum [WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)</span></span>

 <span data-ttu-id="cbe9d-593">値</span><span class="sxs-lookup"><span data-stu-id="cbe9d-593">Values</span></span>                         | <span data-ttu-id="cbe9d-594">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-594">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="cbe9d-595">WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-595">WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span></span>            | <span data-ttu-id="cbe9d-596">ブラウザープロセスが予期せず終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-596">Indicates the browser process terminated unexpectedly.</span></span>
<span data-ttu-id="cbe9d-597">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-597">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span></span>            | <span data-ttu-id="cbe9d-598">レンダープロセスが予期せず終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-598">Indicates the render process terminated unexpectedly.</span></span>
<span data-ttu-id="cbe9d-599">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-599">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span></span>            | <span data-ttu-id="cbe9d-600">レンダープロセスが応答しなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-600">Indicates the render process becomes unresponsive.</span></span>

#### <span data-ttu-id="cbe9d-601">WEBVIEW2_PERMISSION_TYPE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-601">WEBVIEW2_PERMISSION_TYPE</span></span> 

<span data-ttu-id="cbe9d-602">アクセス許可要求の種類。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-602">The type of a permission request.</span></span>

> <span data-ttu-id="cbe9d-603">列挙型[WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-603">enum [WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)</span></span>

 <span data-ttu-id="cbe9d-604">値</span><span class="sxs-lookup"><span data-stu-id="cbe9d-604">Values</span></span>                         | <span data-ttu-id="cbe9d-605">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-605">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="cbe9d-606">WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="cbe9d-606">WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION</span></span>            | <span data-ttu-id="cbe9d-607">不明な権限。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-607">Unknown permission.</span></span>
<span data-ttu-id="cbe9d-608">WEBVIEW2_PERMISSION_TYPE_MICROPHONE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-608">WEBVIEW2_PERMISSION_TYPE_MICROPHONE</span></span>            | <span data-ttu-id="cbe9d-609">オーディオをキャプチャするためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-609">Permission to capture audio.</span></span>
<span data-ttu-id="cbe9d-610">WEBVIEW2_PERMISSION_TYPE_CAMERA</span><span class="sxs-lookup"><span data-stu-id="cbe9d-610">WEBVIEW2_PERMISSION_TYPE_CAMERA</span></span>            | <span data-ttu-id="cbe9d-611">ビデオをキャプチャするためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-611">Permission to capture video.</span></span>
<span data-ttu-id="cbe9d-612">WEBVIEW2_PERMISSION_TYPE_GEOLOCATION</span><span class="sxs-lookup"><span data-stu-id="cbe9d-612">WEBVIEW2_PERMISSION_TYPE_GEOLOCATION</span></span>            | <span data-ttu-id="cbe9d-613">位置情報へのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-613">Permission to access geolocation.</span></span>
<span data-ttu-id="cbe9d-614">WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="cbe9d-614">WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS</span></span>            | <span data-ttu-id="cbe9d-615">Web 通知を送信するためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-615">Permission to send web notifications.</span></span>
<span data-ttu-id="cbe9d-616">WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS</span><span class="sxs-lookup"><span data-stu-id="cbe9d-616">WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS</span></span>            | <span data-ttu-id="cbe9d-617">汎用センサーへのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-617">Permission to access generic sensor.</span></span>
<span data-ttu-id="cbe9d-618">WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ</span><span class="sxs-lookup"><span data-stu-id="cbe9d-618">WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ</span></span>            | <span data-ttu-id="cbe9d-619">ユーザーのジェスチャを使わずにシステムクリップボードを読み取る権限。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-619">Permission to read system clipboard without a user gesture.</span></span>

#### <span data-ttu-id="cbe9d-620">WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-620">WEBVIEW2_PERMISSION_STATE</span></span> 

<span data-ttu-id="cbe9d-621">アクセス許可要求に対する応答。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-621">Response to a permission request.</span></span>

> <span data-ttu-id="cbe9d-622">列挙型[WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-622">enum [WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)</span></span>

 <span data-ttu-id="cbe9d-623">値</span><span class="sxs-lookup"><span data-stu-id="cbe9d-623">Values</span></span>                         | <span data-ttu-id="cbe9d-624">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-624">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="cbe9d-625">WEBVIEW2_PERMISSION_STATE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-625">WEBVIEW2_PERMISSION_STATE_DEFAULT</span></span>            | <span data-ttu-id="cbe9d-626">既定のブラウザー動作を使用します。通常はユーザーに判断を求めます。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-626">Use default browser behavior, which normally prompt users for decision.</span></span>
<span data-ttu-id="cbe9d-627">WEBVIEW2_PERMISSION_STATE_ALLOW</span><span class="sxs-lookup"><span data-stu-id="cbe9d-627">WEBVIEW2_PERMISSION_STATE_ALLOW</span></span>            | <span data-ttu-id="cbe9d-628">権限の要求を許可します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-628">Grant the permission request.</span></span>
<span data-ttu-id="cbe9d-629">WEBVIEW2_PERMISSION_STATE_DENY</span><span class="sxs-lookup"><span data-stu-id="cbe9d-629">WEBVIEW2_PERMISSION_STATE_DENY</span></span>            | <span data-ttu-id="cbe9d-630">権限の要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-630">Deny the permission request.</span></span>

#### <span data-ttu-id="cbe9d-631">WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="cbe9d-631">WEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="cbe9d-632">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-632">Reason for moving focus.</span></span>

> <span data-ttu-id="cbe9d-633">列挙型[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-633">enum [WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)</span></span>

 <span data-ttu-id="cbe9d-634">値</span><span class="sxs-lookup"><span data-stu-id="cbe9d-634">Values</span></span>                         | <span data-ttu-id="cbe9d-635">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-635">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="cbe9d-636">WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="cbe9d-636">WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="cbe9d-637">コード設定による WebView へのフォーカス。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-637">Code setting focus into WebView.</span></span>
<span data-ttu-id="cbe9d-638">WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-638">WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="cbe9d-639">タブトラバーサルを前方に移動するためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-639">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="cbe9d-640">WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="cbe9d-640">WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="cbe9d-641">タブトラバーサルに戻るためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-641">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="cbe9d-642">WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="cbe9d-642">WEBVIEW2_WEB_ERROR_STATUS</span></span> 

<span data-ttu-id="cbe9d-643">Web ナビゲーションのエラー状態の値。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-643">Error status values for web navigations.</span></span>

> <span data-ttu-id="cbe9d-644">列挙型[WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-644">enum [WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)</span></span>

 <span data-ttu-id="cbe9d-645">値</span><span class="sxs-lookup"><span data-stu-id="cbe9d-645">Values</span></span>                         | <span data-ttu-id="cbe9d-646">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-646">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="cbe9d-647">WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="cbe9d-647">WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span></span>            | <span data-ttu-id="cbe9d-648">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-648">An unknown error occurred.</span></span>
<span data-ttu-id="cbe9d-649">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-649">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span></span>            | <span data-ttu-id="cbe9d-650">SSL 証明書の共通名が web アドレスと一致しません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-650">The SSL certificate common name does not match the web address.</span></span>
<span data-ttu-id="cbe9d-651">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-651">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span></span>            | <span data-ttu-id="cbe9d-652">SSL 証明書の有効期限が切れています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-652">The SSL certificate has expired.</span></span>
<span data-ttu-id="cbe9d-653">WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span><span class="sxs-lookup"><span data-stu-id="cbe9d-653">WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span></span>            | <span data-ttu-id="cbe9d-654">SSL クライアント証明書にエラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-654">The SSL client certificate contains errors.</span></span>
<span data-ttu-id="cbe9d-655">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-655">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span></span>            | <span data-ttu-id="cbe9d-656">SSL 証明書が失効しています。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-656">The SSL certificate has been revoked.</span></span>
<span data-ttu-id="cbe9d-657">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="cbe9d-657">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span></span>            | <span data-ttu-id="cbe9d-658">SSL 証明書が無効です。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-658">The SSL certificate is invalid.</span></span>
<span data-ttu-id="cbe9d-659">WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-659">WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span></span>            | <span data-ttu-id="cbe9d-660">ホストに到達できません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-660">The host is unreachable.</span></span>
<span data-ttu-id="cbe9d-661">WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-661">WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span></span>            | <span data-ttu-id="cbe9d-662">接続がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-662">The connection has timed out.</span></span>
<span data-ttu-id="cbe9d-663">WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-663">WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span></span>            | <span data-ttu-id="cbe9d-664">サーバーが無効または認識不能な応答を返しました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-664">The server returned an invalid or unrecognized response.</span></span>
<span data-ttu-id="cbe9d-665">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-665">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span></span>            | <span data-ttu-id="cbe9d-666">接続が中止されました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-666">The connection was aborted.</span></span>
<span data-ttu-id="cbe9d-667">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span><span class="sxs-lookup"><span data-stu-id="cbe9d-667">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span></span>            | <span data-ttu-id="cbe9d-668">接続がリセットされました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-668">The connection was reset.</span></span>
<span data-ttu-id="cbe9d-669">WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-669">WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span></span>            | <span data-ttu-id="cbe9d-670">インターネット接続が切断されました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-670">The Internet connection has been lost.</span></span>
<span data-ttu-id="cbe9d-671">WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-671">WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span></span>            | <span data-ttu-id="cbe9d-672">宛先に接続できません。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-672">Cannot connect to destination.</span></span>
<span data-ttu-id="cbe9d-673">WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-673">WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span></span>            | <span data-ttu-id="cbe9d-674">指定されたホスト名を解決できませんでした。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-674">Could not resolve provided host name.</span></span>
<span data-ttu-id="cbe9d-675">WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-675">WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span></span>            | <span data-ttu-id="cbe9d-676">操作が取り消されました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-676">The operation was canceled.</span></span>
<span data-ttu-id="cbe9d-677">WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span><span class="sxs-lookup"><span data-stu-id="cbe9d-677">WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span></span>            | <span data-ttu-id="cbe9d-678">要求のリダイレクトに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-678">The request redirect failed.</span></span>
<span data-ttu-id="cbe9d-679">WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span><span class="sxs-lookup"><span data-stu-id="cbe9d-679">WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span></span>            | <span data-ttu-id="cbe9d-680">予期しないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-680">An unexpected error occurred.</span></span>

#### <span data-ttu-id="cbe9d-681">WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-681">WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span> 

<span data-ttu-id="cbe9d-682">Web リソース要求コンテキストの列挙。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-682">Enum for web resource request contexts.</span></span>

> <span data-ttu-id="cbe9d-683">列挙型[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)</span><span class="sxs-lookup"><span data-stu-id="cbe9d-683">enum [WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)</span></span>

 <span data-ttu-id="cbe9d-684">値</span><span class="sxs-lookup"><span data-stu-id="cbe9d-684">Values</span></span>                         | <span data-ttu-id="cbe9d-685">説明</span><span class="sxs-lookup"><span data-stu-id="cbe9d-685">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="cbe9d-686">WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span><span class="sxs-lookup"><span data-stu-id="cbe9d-686">WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span></span>            | <span data-ttu-id="cbe9d-687">すべてのリソース。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-687">All resources.</span></span>
<span data-ttu-id="cbe9d-688">WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-688">WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span></span>            | <span data-ttu-id="cbe9d-689">ドキュメントリソース。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-689">Document resources.</span></span>
<span data-ttu-id="cbe9d-690">WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span><span class="sxs-lookup"><span data-stu-id="cbe9d-690">WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span></span>            | <span data-ttu-id="cbe9d-691">CSS リソース。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-691">CSS resources.</span></span>
<span data-ttu-id="cbe9d-692">WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-692">WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span></span>            | <span data-ttu-id="cbe9d-693">画像リソース。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-693">Image resources.</span></span>
<span data-ttu-id="cbe9d-694">WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span><span class="sxs-lookup"><span data-stu-id="cbe9d-694">WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span></span>            | <span data-ttu-id="cbe9d-695">その他のメディアリソース (ビデオなど)。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-695">Other media resources such as videos.</span></span>
<span data-ttu-id="cbe9d-696">WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-696">WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span></span>            | <span data-ttu-id="cbe9d-697">フォントリソース。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-697">Font resources.</span></span>
<span data-ttu-id="cbe9d-698">WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-698">WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span></span>            | <span data-ttu-id="cbe9d-699">スクリプトリソース。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-699">Script resources.</span></span>
<span data-ttu-id="cbe9d-700">WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span><span class="sxs-lookup"><span data-stu-id="cbe9d-700">WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span></span>            | <span data-ttu-id="cbe9d-701">XML HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-701">XML HTTP requests.</span></span>
<span data-ttu-id="cbe9d-702">WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span><span class="sxs-lookup"><span data-stu-id="cbe9d-702">WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span></span>            | <span data-ttu-id="cbe9d-703">API 通信を取得します。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-703">Fetch API communication.</span></span>
<span data-ttu-id="cbe9d-704">WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span><span class="sxs-lookup"><span data-stu-id="cbe9d-704">WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span></span>            | <span data-ttu-id="cbe9d-705">TextTrack のリソース。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-705">TextTrack resources.</span></span>
<span data-ttu-id="cbe9d-706">WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-706">WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span></span>            | 
<span data-ttu-id="cbe9d-707">WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span><span class="sxs-lookup"><span data-stu-id="cbe9d-707">WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span></span>            | 
<span data-ttu-id="cbe9d-708">WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span><span class="sxs-lookup"><span data-stu-id="cbe9d-708">WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span></span>            | 
<span data-ttu-id="cbe9d-709">WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span><span class="sxs-lookup"><span data-stu-id="cbe9d-709">WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span></span>            | 
<span data-ttu-id="cbe9d-710">WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span><span class="sxs-lookup"><span data-stu-id="cbe9d-710">WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span></span>            | 
<span data-ttu-id="cbe9d-711">WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span><span class="sxs-lookup"><span data-stu-id="cbe9d-711">WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span></span>            | 
<span data-ttu-id="cbe9d-712">WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span><span class="sxs-lookup"><span data-stu-id="cbe9d-712">WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span></span>            | <span data-ttu-id="cbe9d-713">その他のリソース。</span><span class="sxs-lookup"><span data-stu-id="cbe9d-713">Other resources.</span></span>
