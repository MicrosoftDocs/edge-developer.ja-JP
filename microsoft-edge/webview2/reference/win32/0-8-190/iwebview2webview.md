---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 5c84cfb703c8901560307b7bba8bc7887cb19377
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654170"
---
# <span data-ttu-id="fa75f-104">インターフェイス IWebView2WebView</span><span class="sxs-lookup"><span data-stu-id="fa75f-104">interface IWebView2WebView</span></span> 

> [!NOTE]
> <span data-ttu-id="fa75f-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="fa75f-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView
  : public IUnknown
```

<span data-ttu-id="fa75f-107">WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-107">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="fa75f-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="fa75f-108">Summary</span></span>

 <span data-ttu-id="fa75f-109">Members</span><span class="sxs-lookup"><span data-stu-id="fa75f-109">Members</span></span>                        | <span data-ttu-id="fa75f-110">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fa75f-111">get_Settings</span><span class="sxs-lookup"><span data-stu-id="fa75f-111">get_Settings</span></span>](#get_settings) | <span data-ttu-id="fa75f-112">[IWebView2Settings](IWebView2Settings.md)オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-112">The [IWebView2Settings](IWebView2Settings.md) object contains various modifiable settings for the running WebView.</span></span>
[<span data-ttu-id="fa75f-113">get_Source</span><span class="sxs-lookup"><span data-stu-id="fa75f-113">get_Source</span></span>](#get_source) | <span data-ttu-id="fa75f-114">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="fa75f-114">The URI of the current top level document.</span></span>
[<span data-ttu-id="fa75f-115">検索</span><span class="sxs-lookup"><span data-stu-id="fa75f-115">Navigate</span></span>](#navigate) | <span data-ttu-id="fa75f-116">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-116">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="fa75f-117">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-117">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="fa75f-118">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-118">Move focus into WebView.</span></span>
[<span data-ttu-id="fa75f-119">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="fa75f-119">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="fa75f-120">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-120">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="fa75f-121">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="fa75f-121">add_NavigationStarting</span></span>](#add_navigationstarting) | <span data-ttu-id="fa75f-122">NavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-122">Add an event handler for the NavigationStarting event.</span></span>
[<span data-ttu-id="fa75f-123">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="fa75f-123">remove_NavigationStarting</span></span>](#remove_navigationstarting) | <span data-ttu-id="fa75f-124">Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-124">Remove an event handler previously added with add_NavigationStarting.</span></span>
[<span data-ttu-id="fa75f-125">add_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="fa75f-125">add_DocumentStateChanged</span></span>](#add_documentstatechanged) | <span data-ttu-id="fa75f-126">DocumentStateChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-126">Add an event handler for the DocumentStateChanged event.</span></span>
[<span data-ttu-id="fa75f-127">remove_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="fa75f-127">remove_DocumentStateChanged</span></span>](#remove_documentstatechanged) | <span data-ttu-id="fa75f-128">Add_DocumentStateChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-128">Remove an event handler previously added with add_DocumentStateChanged.</span></span>
[<span data-ttu-id="fa75f-129">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="fa75f-129">add_NavigationCompleted</span></span>](#add_navigationcompleted) | <span data-ttu-id="fa75f-130">NavigationCompleted イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-130">Add an event handler for the NavigationCompleted event.</span></span>
[<span data-ttu-id="fa75f-131">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="fa75f-131">remove_NavigationCompleted</span></span>](#remove_navigationcompleted) | <span data-ttu-id="fa75f-132">Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-132">Remove an event handler previously added with add_NavigationCompleted.</span></span>
[<span data-ttu-id="fa75f-133">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="fa75f-133">add_FrameNavigationStarting</span></span>](#add_framenavigationstarting) | <span data-ttu-id="fa75f-134">FrameNavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-134">Add an event handler for the FrameNavigationStarting event.</span></span>
[<span data-ttu-id="fa75f-135">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="fa75f-135">remove_FrameNavigationStarting</span></span>](#remove_framenavigationstarting) | <span data-ttu-id="fa75f-136">Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-136">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>
[<span data-ttu-id="fa75f-137">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-137">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="fa75f-138">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-138">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="fa75f-139">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-139">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="fa75f-140">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-140">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="fa75f-141">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-141">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="fa75f-142">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-142">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="fa75f-143">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-143">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="fa75f-144">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-144">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="fa75f-145">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-145">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="fa75f-146">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-146">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="fa75f-147">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-147">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="fa75f-148">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-148">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="fa75f-149">add_WebResourceRequested_deprecated</span><span class="sxs-lookup"><span data-stu-id="fa75f-149">add_WebResourceRequested_deprecated</span></span>](#add_webresourcerequested_deprecated) | <span data-ttu-id="fa75f-150">この API は廃止されます。新しい add_WebResourceRequested API を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-150">This API will be deprecated, please use the new add_WebResourceRequested API.</span></span>
[<span data-ttu-id="fa75f-151">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-151">remove_WebResourceRequested</span></span>](#remove_webresourcerequested) | <span data-ttu-id="fa75f-152">Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-152">Remove an event handler previously added with add_WebResourceRequested.</span></span>
[<span data-ttu-id="fa75f-153">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="fa75f-153">add_ScriptDialogOpening</span></span>](#add_scriptdialogopening) | <span data-ttu-id="fa75f-154">Scriptの開始イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-154">Add an event handler for the ScriptDialogOpening event.</span></span>
[<span data-ttu-id="fa75f-155">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="fa75f-155">remove_ScriptDialogOpening</span></span>](#remove_scriptdialogopening) | <span data-ttu-id="fa75f-156">Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-156">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>
[<span data-ttu-id="fa75f-157">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="fa75f-157">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="fa75f-158">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-158">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="fa75f-159">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="fa75f-159">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="fa75f-160">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-160">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="fa75f-161">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-161">add_PermissionRequested</span></span>](#add_permissionrequested) | <span data-ttu-id="fa75f-162">PermissionRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-162">Add an event handler for the PermissionRequested event.</span></span>
[<span data-ttu-id="fa75f-163">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-163">remove_PermissionRequested</span></span>](#remove_permissionrequested) | <span data-ttu-id="fa75f-164">Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-164">Remove an event handler previously added with add_PermissionRequested.</span></span>
[<span data-ttu-id="fa75f-165">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="fa75f-165">add_ProcessFailed</span></span>](#add_processfailed) | <span data-ttu-id="fa75f-166">ProcessFailed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-166">Add an event handler for the ProcessFailed event.</span></span>
[<span data-ttu-id="fa75f-167">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="fa75f-167">remove_ProcessFailed</span></span>](#remove_processfailed) | <span data-ttu-id="fa75f-168">Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-168">Remove an event handler previously added with add_ProcessFailed.</span></span>
[<span data-ttu-id="fa75f-169">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="fa75f-169">AddScriptToExecuteOnDocumentCreated</span></span>](#addscripttoexecuteondocumentcreated) | <span data-ttu-id="fa75f-170">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-170">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="fa75f-171">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="fa75f-171">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="fa75f-172">AddScriptToExecuteOnDocumentCreated によって追加された、対応する JavaScript を削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-172">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>
[<span data-ttu-id="fa75f-173">Execuスクリプト</span><span class="sxs-lookup"><span data-stu-id="fa75f-173">ExecuteScript</span></span>](#executescript) | <span data-ttu-id="fa75f-174">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-174">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="fa75f-175">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="fa75f-175">CapturePreview</span></span>](#capturepreview) | <span data-ttu-id="fa75f-176">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-176">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="fa75f-177">再</span><span class="sxs-lookup"><span data-stu-id="fa75f-177">Reload</span></span>](#reload) | <span data-ttu-id="fa75f-178">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-178">Reload the current page.</span></span>
[<span data-ttu-id="fa75f-179">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="fa75f-179">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="fa75f-180">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="fa75f-180">The webview bounds.</span></span>
[<span data-ttu-id="fa75f-181">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="fa75f-181">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="fa75f-182">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-182">Set the Bounds property.</span></span>
[<span data-ttu-id="fa75f-183">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="fa75f-183">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="fa75f-184">WebView の現在のページのズームファクター。</span><span class="sxs-lookup"><span data-stu-id="fa75f-184">The zoom factor for the current page in the WebView.</span></span>
[<span data-ttu-id="fa75f-185">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="fa75f-185">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="fa75f-186">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-186">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="fa75f-187">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="fa75f-187">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="fa75f-188">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-188">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="fa75f-189">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="fa75f-189">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="fa75f-190">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-190">Set the IsVisible property.</span></span>
[<span data-ttu-id="fa75f-191">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="fa75f-191">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="fa75f-192">指定した webMessage をこの[IWebView2WebView]()のトップレベルのドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-192">Post the specified webMessage to the top level document in this [IWebView2WebView]().</span></span>
[<span data-ttu-id="fa75f-193">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="fa75f-193">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="fa75f-194">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="fa75f-194">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="fa75f-195">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="fa75f-195">add_WebMessageReceived</span></span>](#add_webmessagereceived) | <span data-ttu-id="fa75f-196">このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-196">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="fa75f-197">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="fa75f-197">remove_WebMessageReceived</span></span>](#remove_webmessagereceived) | <span data-ttu-id="fa75f-198">Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-198">Remove an event handler previously added with add_WebMessageReceived.</span></span>
[<span data-ttu-id="fa75f-199">Close</span><span class="sxs-lookup"><span data-stu-id="fa75f-199">Close</span></span>](#close) | <span data-ttu-id="fa75f-200">Webview を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-200">Closes the webview and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="fa75f-201">Calldevon Protocolメソッド</span><span class="sxs-lookup"><span data-stu-id="fa75f-201">CallDevToolsProtocolMethod</span></span>](#calldevtoolsprotocolmethod) | <span data-ttu-id="fa75f-202">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-202">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="fa75f-203">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="fa75f-203">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="fa75f-204">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-204">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="fa75f-205">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="fa75f-205">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="fa75f-206">Add_DevToolsProtocolEventReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-206">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>
[<span data-ttu-id="fa75f-207">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="fa75f-207">get_BrowserProcessId</span></span>](#get_browserprocessid) | <span data-ttu-id="fa75f-208">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="fa75f-208">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="fa75f-209">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="fa75f-209">get_CanGoBack</span></span>](#get_cangoback) | <span data-ttu-id="fa75f-210">Webview をナビゲーション履歴の前のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-210">Can navigate the webview to the previous page in the navigation history.</span></span>
[<span data-ttu-id="fa75f-211">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="fa75f-211">get_CanGoForward</span></span>](#get_cangoforward) | <span data-ttu-id="fa75f-212">Webview をナビゲーション履歴の次のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-212">Can navigate the webview to the next page in the navigation history.</span></span>
[<span data-ttu-id="fa75f-213">GoBack</span><span class="sxs-lookup"><span data-stu-id="fa75f-213">GoBack</span></span>](#goback) | <span data-ttu-id="fa75f-214">ナビゲーション履歴で、webview を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-214">Navigates the webview to the previous page in the navigation history.</span></span>
[<span data-ttu-id="fa75f-215">GoForward</span><span class="sxs-lookup"><span data-stu-id="fa75f-215">GoForward</span></span>](#goforward) | <span data-ttu-id="fa75f-216">Webview をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-216">Navigates the webview to the next page in the navigation history.</span></span>
[<span data-ttu-id="fa75f-217">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="fa75f-217">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span>](#webview2_capture_preview_image_format) | <span data-ttu-id="fa75f-218">[IWebView2WebView:: CapturePreview](#capturepreview)メソッドで使用されている画像形式。</span><span class="sxs-lookup"><span data-stu-id="fa75f-218">Image format used by the [IWebView2WebView::CapturePreview](#capturepreview) method.</span></span>
[<span data-ttu-id="fa75f-219">WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="fa75f-219">WEBVIEW2_SCRIPT_DIALOG_KIND</span></span>](#webview2_script_dialog_kind) | <span data-ttu-id="fa75f-220">[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)インターフェイスで使用される JavaScript ダイアログの種類。</span><span class="sxs-lookup"><span data-stu-id="fa75f-220">Kind of JavaScript dialog used in the [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) interface.</span></span>
[<span data-ttu-id="fa75f-221">WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="fa75f-221">WEBVIEW2_PROCESS_FAILED_KIND</span></span>](#webview2_process_failed_kind) | <span data-ttu-id="fa75f-222">[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)インターフェイスで使用されているプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="fa75f-222">Kind of process failure used in the [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) interface.</span></span>
[<span data-ttu-id="fa75f-223">WEBVIEW2_PERMISSION_TYPE</span><span class="sxs-lookup"><span data-stu-id="fa75f-223">WEBVIEW2_PERMISSION_TYPE</span></span>](#webview2_permission_type) | <span data-ttu-id="fa75f-224">アクセス許可要求の種類。</span><span class="sxs-lookup"><span data-stu-id="fa75f-224">The type of a permission request.</span></span>
[<span data-ttu-id="fa75f-225">WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="fa75f-225">WEBVIEW2_PERMISSION_STATE</span></span>](#webview2_permission_state) | <span data-ttu-id="fa75f-226">アクセス許可要求に対する応答。</span><span class="sxs-lookup"><span data-stu-id="fa75f-226">Response to a permission request.</span></span>
[<span data-ttu-id="fa75f-227">WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="fa75f-227">WEBVIEW2_MOVE_FOCUS_REASON</span></span>](#webview2_move_focus_reason) | <span data-ttu-id="fa75f-228">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="fa75f-228">Reason for moving focus.</span></span>
[<span data-ttu-id="fa75f-229">WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="fa75f-229">WEBVIEW2_WEB_ERROR_STATUS</span></span>](#webview2_web_error_status) | <span data-ttu-id="fa75f-230">Web ナビゲーションのエラー状態の値。</span><span class="sxs-lookup"><span data-stu-id="fa75f-230">Error status values for web navigations.</span></span>
[<span data-ttu-id="fa75f-231">WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="fa75f-231">WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span>](#webview2_web_resource_context) | <span data-ttu-id="fa75f-232">Web リソース要求コンテキストの列挙。</span><span class="sxs-lookup"><span data-stu-id="fa75f-232">Enum for web resource request contexts.</span></span>

## <span data-ttu-id="fa75f-233">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="fa75f-233">Navigation events</span></span>

<span data-ttu-id="fa75f-234">ナビゲーションイベントの通常のシーケンスは、NavigationStarting、DocumentStateChanged、Navigationstarting です。</span><span class="sxs-lookup"><span data-stu-id="fa75f-234">The normal sequence of navigation events is NavigationStarting, DocumentStateChanged and then NavigationCompleted.</span></span>

![dot-inline-dotgraph-1](media/dot-inline-dotgraph-1.png)

<span data-ttu-id="fa75f-236">これは、同じ NavigationId イベント arg を持つナビゲーションイベント用であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-236">Note that this is for navigation events with the same NavigationId event arg.</span></span> <span data-ttu-id="fa75f-237">異なる NavigationId イベント引数を持つナビゲーションイベントは、重複する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-237">Navigations events with different NavigationId event args may overlap.</span></span> <span data-ttu-id="fa75f-238">たとえば、ナビゲーションを開始したときに NavigationStarting イベントが発生してから別のナビゲーションを開始した場合は、最初のナビで開始される navigationstarting 後に、2番目のナビゲーションのナビゲートが続いて、2番目のナビゲーションについて、該当するすべてのナビゲーションイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-238">For instance, if you start a navigation wait for its NavigationStarting event and then start another navigation you'll see the NavigationStarting for the first navigate followed by the NavigationStarting of the second navigate, followed by the NavigationCompleted for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span> <span data-ttu-id="fa75f-239">エラーが発生した場合は、ナビゲーションがエラーページに続いているかどうかによって、DocumentStateChanged イベントが発生していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-239">In error cases there may or may not be a DocumentStateChanged event depending on whether the navigation is continued to an error page.</span></span> <span data-ttu-id="fa75f-240">HTTP リダイレクトの場合、1つの行に複数の NavigationStarting イベントが存在します。最初の列の後には、IsRedirect フラグが設定されています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-240">In case of an HTTP redirect, there will be multiple NavigationStarting events in a row, with ones following the first will have their IsRedirect flag set.</span></span>

<span data-ttu-id="fa75f-241">WebView 内のサブフレームの場合、唯一のナビゲーションイベントは NavigationStarting イベントです。これは、ホストがサブフレームナビゲーションをブロックする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-241">For subframes inside WebView, the only navigation event fired is the NavigationStarting event which gives host the ability to block subframe navigations.</span></span>

## <span data-ttu-id="fa75f-242">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="fa75f-242">Process model</span></span>

<span data-ttu-id="fa75f-243">WebView2 は、Edge web ブラウザーと同じプロセスモデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-243">WebView2 uses the same process model as the Edge web browser.</span></span> <span data-ttu-id="fa75f-244">ユーザーデータディレクトリを指定する WebView2 の呼び出しプロセスを提供するユーザーセッションの指定したユーザーデータディレクトリごとに、1つの Edge ブラウザープロセスが存在します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-244">There is one Edge browser process per specified user data directory in a user session that will serve any WebView2 calling process that specifies that user data directory.</span></span> <span data-ttu-id="fa75f-245">つまり、1つの Edge ブラウザープロセスが複数の通話プロセスを処理している可能性があり、1つの呼び出しプロセスが複数の Edge ブラウザープロセスを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-245">This means one Edge browser process may be serving multiple calling processes and one calling process may be using multiple Edge browser processes.</span></span>

![dot-inline-dotgraph-2](media/dot-inline-dotgraph-2.png)

<span data-ttu-id="fa75f-247">ブラウザープロセスが表示されない場合は、いくつかのレンダラープロセスが存在します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-247">Off of a browser process there will be some number of renderer processes.</span></span> <span data-ttu-id="fa75f-248">これらは、さまざまな WebViews で複数のフレームを処理するために必要に応じて作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-248">These are created as necessary to service potentially multiple frames in different WebViews.</span></span> <span data-ttu-id="fa75f-249">レンダラープロセスの数は、サイト分離ブラウザー機能と、関連付けられている WebViews でレンダリングされた個別の切断元の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-249">The number of renderer processes varies based on the site isolation browser feature and the number of distinct disconnected origins rendered in associated WebViews.</span></span>

![dot-inline-dotgraph-3](media/dot-inline-dotgraph-3.png)

<span data-ttu-id="fa75f-251">クラッシュとハングに対処するには、これらのブラウザーと ProcessFailure イベントを使ってプロセスをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-251">You can react to crashes and hangs in these browser and renderer processes using the ProcessFailure event.</span></span>

<span data-ttu-id="fa75f-252">Close メソッドを使用して、関連するブラウザーとレンダラープロセスを安全にシャットダウンできます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-252">You can safely shutdown associated browser and renderer processes using the Close method.</span></span>

## <span data-ttu-id="fa75f-253">スレッドモデル</span><span class="sxs-lookup"><span data-stu-id="fa75f-253">Threading model</span></span>

<span data-ttu-id="fa75f-254">WebView2 は、UI スレッドで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-254">The WebView2 must be created on a UI thread.</span></span> <span data-ttu-id="fa75f-255">特にメッセージポンプを持つスレッド。</span><span class="sxs-lookup"><span data-stu-id="fa75f-255">Specifically a thread with a message pump.</span></span> <span data-ttu-id="fa75f-256">すべてのコールバックがそのスレッドで発生し、WebView への呼び出しはそのスレッドで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-256">All callbacks will occur on that thread and calls into the WebView must be done on that thread.</span></span> <span data-ttu-id="fa75f-257">他のスレッドから WebView を使うことは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-257">It is not safe to use the WebView from another thread.</span></span>

<span data-ttu-id="fa75f-258">イベントハンドラーと完了ハンドラーを含むコールバックは逐次実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-258">Callbacks including event handlers and completion handlers execute serially.</span></span> <span data-ttu-id="fa75f-259">つまり、イベントハンドラーを実行していて、メッセージループを開始した場合、他のイベントハンドラーまたは完了コールバックによって reentrantly の実行が開始されません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-259">That is, if you have an event handler running and begin a message loop no other event handlers or completion callbacks will begin executing reentrantly.</span></span>

## <span data-ttu-id="fa75f-260">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="fa75f-260">Security</span></span>

<span data-ttu-id="fa75f-261">実行前に、必ず WebView の Source プロパティを確認してください。 Executesscript、PostWebMessageAsJson、Postwebmessageasjson などのメソッドを使って、WebView に情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-261">Always check the Source property of the WebView before using ExecuteScript, PostWebMessageAsJson, PostWebMessageAsString, or any other method to send information into the WebView.</span></span> <span data-ttu-id="fa75f-262">ナビゲーションを引き起こしているページのページまたはスクリプトをエンドユーザーが操作している場合、WebView が別のページに移動している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-262">The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation.</span></span> <span data-ttu-id="fa75f-263">同様に、AddScriptToExecuteOnDocumentCreated には細心の注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-263">Similarly, be very careful with AddScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="fa75f-264">今後のすべてのナビゲーションでは、このスクリプトが実行され、特定の元にのみ意図した情報へのアクセスを提供している場合、HTML ドキュメントはすべて、アクセス権を持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-264">All future navigations will run this script and if it provides access to information intended only for a certain origin, any HTML document may have access.</span></span>

<span data-ttu-id="fa75f-265">ExecuteScript の呼び出しの結果を調べるとき、WebMessageReceived イベントが発生した場合、または WebView の HTML ドキュメントから情報を受信するその他のメカニズムを確認する場合は、HTML ドキュメントの URI が予期したとおりであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-265">When examining the result of an ExecuteScript method call, a WebMessageReceived event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.</span></span>

<span data-ttu-id="fa75f-266">WebView に送信するメッセージを構築する場合は、PostWebMessageAsJson の使用をお勧めし、JSON ライブラリを使って JSON 文字列パラメーターを構築します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-266">When constructing a message to send into a WebView, prefer using PostWebMessageAsJson and construct the JSON string parameter using a JSON library.</span></span> <span data-ttu-id="fa75f-267">これにより、JSON 文字列またはスクリプトへのエンコード情報の発生を回避することができます。また、攻撃者によって制御される入力によって、残りの JSON メッセージを変更したり、任意のスクリプトを実行したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-267">This will avoid any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script.</span></span>

## <span data-ttu-id="fa75f-268">文字列型</span><span class="sxs-lookup"><span data-stu-id="fa75f-268">String types</span></span>

<span data-ttu-id="fa75f-269">文字列 out パラメーターは、LPWSTR null で終了された文字列です。</span><span class="sxs-lookup"><span data-stu-id="fa75f-269">String out parameters are LPWSTR null terminated strings.</span></span> <span data-ttu-id="fa75f-270">呼び出し先は、、Cotaskmemalloc を使って文字列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-270">The callee allocates the string using CoTaskMemAlloc.</span></span> <span data-ttu-id="fa75f-271">所有権は、呼び出し元に転送され、CoTaskMemFree を使ってメモリを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-271">Ownership is transferred to the caller and it is up to the caller to free the memory using CoTaskMemFree.</span></span>

<span data-ttu-id="fa75f-272">パラメーター内の文字列は、LPCWSTR null で終了する文字列です。</span><span class="sxs-lookup"><span data-stu-id="fa75f-272">String in parameters are LPCWSTR null terminated strings.</span></span> <span data-ttu-id="fa75f-273">呼び出し元は、同期関数呼び出しの間、文字列が有効であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-273">The caller ensures the string is valid for the duration of the synchronous function call.</span></span> <span data-ttu-id="fa75f-274">呼び出し先がその値を関数呼び出しが完了した後のある時点まで保持する必要がある場合、呼び出し元は、その値の文字列値のコピーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-274">If the callee needs to retain that value to some point after the function call completes, the callee must allocate its own copy of the string value.</span></span>

## <span data-ttu-id="fa75f-275">URI と JSON の解析</span><span class="sxs-lookup"><span data-stu-id="fa75f-275">URI and JSON parsing</span></span>

<span data-ttu-id="fa75f-276">さまざまなメソッドで Uri と JSON を文字列として指定または受け入れます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-276">Various methods provide or accept URIs and JSON as strings.</span></span> <span data-ttu-id="fa75f-277">これらの文字列の解析と生成には、独自の好みのライブラリを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-277">Please use your own preferred library for parsing and generating these strings.</span></span>

<span data-ttu-id="fa75f-278">アプリで WinRT が利用できる場合は `RuntimeClass_Windows_Data_Json_JsonObject` 、 `IJsonObjectStatics` JSON 文字列の解析または生成、 `RuntimeClass_Windows_Foundation_Uri` および uri の解析と生成を行うことができ `IUriRuntimeClassFactory` ます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-278">If WinRT is available for your app you can use `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` to parse and produce URIs.</span></span> <span data-ttu-id="fa75f-279">これらはどちらも Win32 アプリで動作します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-279">Both of these work in Win32 apps.</span></span>

<span data-ttu-id="fa75f-280">IUri と CreateUri を使って Uri を解析する場合は、次の URI の作成フラグを使って、WebView の URI 解析とより厳密に一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-280">If you use IUri and CreateUri to parse URIs you may want to use the following URI creation flags to have CreateUri behavior more closely match the URI parsing in the WebView:</span></span> `Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO`

## <span data-ttu-id="fa75f-281">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fa75f-281">Debugging</span></span>

<span data-ttu-id="fa75f-282">標準のショートカット (または) で DevTools を開く。 `F12` `Ctrl+Shift+I`</span><span class="sxs-lookup"><span data-stu-id="fa75f-282">Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`.</span></span> <span data-ttu-id="fa75f-283">`--auto-open-devtools-for-tabs`コマンド引数スイッチを使うと、WebView を最初に作成したときに、DevTools ウィンドウをすぐに開くことができます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-283">You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView.</span></span> <span data-ttu-id="fa75f-284">ブラウザープロセスに追加のコマンドライン引数を指定する方法については、CreateWebView のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-284">See CreateWebView documentation for how to provide additional command line arguments to the browser process.</span></span> <span data-ttu-id="fa75f-285">WebView2 のさまざまなビルドを実行する場合は、CreateWebView ドキュメントでアプリケーションを変更せずに、LoaderOverride レジストリキーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-285">Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateWebView documentation.</span></span>

## <span data-ttu-id="fa75f-286">バージョン</span><span class="sxs-lookup"><span data-stu-id="fa75f-286">Versioning</span></span>

<span data-ttu-id="fa75f-287">特定のバージョンの SDK を使ってアプリをビルドすると、アプリは、インストールされているブラウザーバイナリの以前のバージョンまたは新しいバージョンで終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-287">After you've used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.</span></span> <span data-ttu-id="fa75f-288">WebView2 のバージョン1.0.0.0 以降では、更新中に、SDK がインストールされているブラウザーバイナリのさまざまなバージョンで動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-288">Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that will prevent your SDK from working with different versions of installed browser binaries.</span></span> <span data-ttu-id="fa75f-289">バージョン1.0.0.0 以降の SDK では、次のベストプラクティスに従って、インストールされているブラウザーのさまざまなバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-289">After version 1.0.0.0 different versions of the SDK can work with different versions of the installed browser by following these best practices:</span></span>

<span data-ttu-id="fa75f-290">API への変更を考慮するために、DLL エクスポート CreateWebView2Environment を呼び出すときや、いずれかの WebView2 オブジェクトで QueryInterface を呼び出す場合は、エラーかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-290">To account for breaking changes to the API be sure to check for failure when calling the DLL export CreateWebView2Environment and when calling QueryInterface on any WebView2 object.</span></span> <span data-ttu-id="fa75f-291">E_NOINTERFACE の戻り値は、SDK が Edge ブラウザーのバイナリと互換性がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-291">A return value of E_NOINTERFACE can indicate the SDK is not compatible with the Edge browser binaries.</span></span>

<span data-ttu-id="fa75f-292">QueryInterface からのエラーのチェックは、SDK が Edge ブラウザーのバージョンよりも新しい場合や、アプリが Edge ブラウザーに認識されないインターフェイスを使用しようとした場合にも考慮されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-292">Checking for failure from QueryInterface will also account for cases where the SDK is newer than the version of the Edge browser and your app attempts to use an interface of which the Edge browser is unaware.</span></span>

<span data-ttu-id="fa75f-293">インターフェイスが利用できない場合は、可能であれば関連する機能を無効にするか、ブラウザーを更新する必要があることをエンドユーザーに知らせることができます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-293">When an interface is unavailable, you can consider disabling the associated feature if possible, or otherwise informing the end user they need to update their browser.</span></span>

## <span data-ttu-id="fa75f-294">Members</span><span class="sxs-lookup"><span data-stu-id="fa75f-294">Members</span></span>

#### <span data-ttu-id="fa75f-295">get_Settings</span><span class="sxs-lookup"><span data-stu-id="fa75f-295">get_Settings</span></span> 

<span data-ttu-id="fa75f-296">[IWebView2Settings](IWebView2Settings.md)オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-296">The [IWebView2Settings](IWebView2Settings.md) object contains various modifiable settings for the running WebView.</span></span>

> <span data-ttu-id="fa75f-297">パブリック HRESULT [get_Settings](#get_settings)([IWebView2Settings](IWebView2Settings.md) \* \* 設定)</span><span class="sxs-lookup"><span data-stu-id="fa75f-297">public HRESULT [get_Settings](#get_settings)([IWebView2Settings](IWebView2Settings.md) \*\* settings)</span></span>

#### <span data-ttu-id="fa75f-298">get_Source</span><span class="sxs-lookup"><span data-stu-id="fa75f-298">get_Source</span></span> 

<span data-ttu-id="fa75f-299">現在の最上位レベルのドキュメントの URI。</span><span class="sxs-lookup"><span data-stu-id="fa75f-299">The URI of the current top level document.</span></span>

> <span data-ttu-id="fa75f-300">パブリック HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span><span class="sxs-lookup"><span data-stu-id="fa75f-300">public HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span></span>

<span data-ttu-id="fa75f-301">この値は、別のサイトやフラグメントナビゲーションへの移動など、一部の状況では、DocumentStateChanged イベントの発生の一部として変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-301">This value potentially changes as a part of the DocumentStateChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="fa75f-302">ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションにも同じように表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-302">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

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

#### <span data-ttu-id="fa75f-303">検索</span><span class="sxs-lookup"><span data-stu-id="fa75f-303">Navigate</span></span> 

<span data-ttu-id="fa75f-304">最上位レベルのドキュメントを指定した URI に移動します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-304">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="fa75f-305">パブリック HRESULT[移動](#navigate)(LPCWSTR uri)</span><span class="sxs-lookup"><span data-stu-id="fa75f-305">public HRESULT [Navigate](#navigate)(LPCWSTR uri)</span></span>

<span data-ttu-id="fa75f-306">詳細については、ナビゲーションイベントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-306">See the navigation events for more information.</span></span> <span data-ttu-id="fa75f-307">これによってナビゲーションが開始されることに注意してください。この操作が完了すると、対応する NavigationStarting イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-307">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

```cpp
void ControlComponent::NavigateToAddressBar()
{
    WCHAR uri[2048] = L"";
    GetWindowText(m_toolbar->addressBarWindow, uri, ARRAYSIZE(uri));
    CHECK_FAILURE(m_webView->Navigate(uri));
}
```

#### <span data-ttu-id="fa75f-308">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-308">MoveFocus</span></span> 

<span data-ttu-id="fa75f-309">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-309">Move focus into WebView.</span></span>

> <span data-ttu-id="fa75f-310">パブリック HRESULT [MoveFocus](#movefocus)([WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)の理由)</span><span class="sxs-lookup"><span data-stu-id="fa75f-310">public HRESULT [MoveFocus](#movefocus)([WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason) reason)</span></span>

<span data-ttu-id="fa75f-311">WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-311">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="fa75f-312">プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-312">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="fa75f-313">次の理由から、フォーカスは最初の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-313">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="fa75f-314">前の理由から、フォーカスは最後の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-314">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="fa75f-315">また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-315">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="fa75f-316">Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-316">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="fa75f-317">または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-317">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="fa75f-318">プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-318">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="fa75f-319">WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-319">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

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

#### <span data-ttu-id="fa75f-320">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="fa75f-320">NavigateToString</span></span> 

<span data-ttu-id="fa75f-321">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-321">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="fa75f-322">パブリック HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="fa75f-322">public HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlContent)</span></span>

<span data-ttu-id="fa75f-323">HtmlContent パラメーターの文字数は 2 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-323">The htmlContent parameter may not be larger than 2 MB of characters.</span></span> <span data-ttu-id="fa75f-324">新しいページの起点は "空白" になります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-324">The origin of the new page will be about:blank.</span></span>

```cpp
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### <span data-ttu-id="fa75f-325">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="fa75f-325">add_NavigationStarting</span></span> 

<span data-ttu-id="fa75f-326">NavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-326">Add an event handler for the NavigationStarting event.</span></span>

> <span data-ttu-id="fa75f-327">パブリック HRESULT [add_NavigationStarting](#add_navigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-327">public HRESULT [add_NavigationStarting](#add_navigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-328">NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-328">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="fa75f-329">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-329">This will fire for redirects as well.</span></span>

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

#### <span data-ttu-id="fa75f-330">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="fa75f-330">remove_NavigationStarting</span></span> 

<span data-ttu-id="fa75f-331">Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-331">Remove an event handler previously added with add_NavigationStarting.</span></span>

> <span data-ttu-id="fa75f-332">パブリック HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-332">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-333">add_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="fa75f-333">add_DocumentStateChanged</span></span> 

<span data-ttu-id="fa75f-334">DocumentStateChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-334">Add an event handler for the DocumentStateChanged event.</span></span>

> <span data-ttu-id="fa75f-335">パブリック HRESULT [add_DocumentStateChanged](#add_documentstatechanged)([IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-335">public HRESULT [add_DocumentStateChanged](#add_documentstatechanged)([IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-336">DocumentStateChanged は、webview のメインフレームでの読み込みが開始されたとき、または同じページナビゲーション (フラグメントナビゲーションや履歴の推移など) が発生した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-336">DocumentStateChanged fires when new content has started loading on the webview's main frame or if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span> <span data-ttu-id="fa75f-337">これは、NavigationStarting イベントの後に、Navigationstarting イベントの前に続きます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-337">This follows the NavigationStarting event and precedes the NavigationCompleted event.</span></span>

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

#### <span data-ttu-id="fa75f-338">remove_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="fa75f-338">remove_DocumentStateChanged</span></span> 

<span data-ttu-id="fa75f-339">Add_DocumentStateChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-339">Remove an event handler previously added with add_DocumentStateChanged.</span></span>

> <span data-ttu-id="fa75f-340">パブリック HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-340">public HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-341">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="fa75f-341">add_NavigationCompleted</span></span> 

<span data-ttu-id="fa75f-342">NavigationCompleted イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-342">Add an event handler for the NavigationCompleted event.</span></span>

> <span data-ttu-id="fa75f-343">パブリック HRESULT [add_NavigationCompleted](#add_navigationcompleted)([IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-343">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)([IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-344">NavigationCompleted イベントは、WebView が完全に読み込まれたとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-344">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

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

#### <span data-ttu-id="fa75f-345">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="fa75f-345">remove_NavigationCompleted</span></span> 

<span data-ttu-id="fa75f-346">Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-346">Remove an event handler previously added with add_NavigationCompleted.</span></span>

> <span data-ttu-id="fa75f-347">パブリック HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-347">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-348">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="fa75f-348">add_FrameNavigationStarting</span></span> 

<span data-ttu-id="fa75f-349">FrameNavigationStarting イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-349">Add an event handler for the FrameNavigationStarting event.</span></span>

> <span data-ttu-id="fa75f-350">パブリック HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-350">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-351">FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-351">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="fa75f-352">これは、リダイレクトの場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-352">This will fire for redirects as well.</span></span>

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

#### <span data-ttu-id="fa75f-353">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="fa75f-353">remove_FrameNavigationStarting</span></span> 

<span data-ttu-id="fa75f-354">Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-354">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>

> <span data-ttu-id="fa75f-355">パブリック HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-355">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-356">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-356">add_MoveFocusRequested</span></span> 

<span data-ttu-id="fa75f-357">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-357">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="fa75f-358">パブリック HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-358">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-359">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-359">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="fa75f-360">このイベントが発生すると、WebView のフォーカスが変更されません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-360">The WebView's focus has not changed when this event is fired.</span></span>

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

#### <span data-ttu-id="fa75f-361">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-361">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="fa75f-362">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-362">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="fa75f-363">パブリック HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-363">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-364">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-364">add_GotFocus</span></span> 

<span data-ttu-id="fa75f-365">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-365">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="fa75f-366">パブリック HRESULT [add_GotFocus](#add_gotfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-366">public HRESULT [add_GotFocus](#add_gotfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-367">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-367">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="fa75f-368">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-368">remove_GotFocus</span></span> 

<span data-ttu-id="fa75f-369">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-369">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="fa75f-370">パブリック HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-370">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-371">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-371">add_LostFocus</span></span> 

<span data-ttu-id="fa75f-372">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-372">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="fa75f-373">パブリック HRESULT [add_LostFocus](#add_lostfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-373">public HRESULT [add_LostFocus](#add_lostfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-374">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-374">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="fa75f-375">MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-375">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="fa75f-376">フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-376">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="fa75f-377">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="fa75f-377">remove_LostFocus</span></span> 

<span data-ttu-id="fa75f-378">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-378">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="fa75f-379">パブリック HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-379">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-380">add_WebResourceRequested_deprecated</span><span class="sxs-lookup"><span data-stu-id="fa75f-380">add_WebResourceRequested_deprecated</span></span> 

<span data-ttu-id="fa75f-381">この API は廃止されます。新しい add_WebResourceRequested API を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-381">This API will be deprecated, please use the new add_WebResourceRequested API.</span></span>

> <span data-ttu-id="fa75f-382">パブリック HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)(LPCWSTR \* Const urlfilter、[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) \* Const ResourceContextFilter、SIZE_T filterlength、[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-382">public HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)(LPCWSTR \*const urlFilter,[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) \*const resourceContextFilter,SIZE_T filterLength,[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-383">WebResourceRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-383">Add an event handler for the WebResourceRequested event.</span></span> <span data-ttu-id="fa75f-384">WebView が HTTP 要求を実行したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-384">Fires when the WebView has performs any HTTP request.</span></span> <span data-ttu-id="fa75f-385">UrlFilter を使って、リッスンする url のサイズフィルターの長さを指定してリストを渡します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-385">Use urlFilter to pass in a list with size filterLength of urls to listen for.</span></span> <span data-ttu-id="fa75f-386">各 url エントリでもワイルドカードをサポートしています。 ' \* ' は0個以上の文字と一致し、"?" は1文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-386">Each url entry also supports wildcards: '\*' matches zero or more characters, and '?' matches exactly one character.</span></span> <span data-ttu-id="fa75f-387">UrlFilter の各エントリについて、WebResourceRequested を起動する必要があるリソースの種類を表す、一致する resourceContextFilter を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-387">For each urlFilter entry, provide a matching resourceContextFilter representing the types of resources for which WebResourceRequested should fire.</span></span> <span data-ttu-id="fa75f-388">FilterLength が0の場合、イベントはすべてのネットワーク要求に対して発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-388">If filterLength is 0, the event will fire for all network requests.</span></span> <span data-ttu-id="fa75f-389">サポートされているリソースコンテキストは、ドキュメント、スタイルシート、画像、メディア、フォント、スクリプト、XHR、取得です。</span><span class="sxs-lookup"><span data-stu-id="fa75f-389">The supported resource contexts are: Document, Stylesheet, Image, Media, Font, Script, XHR, Fetch.</span></span>

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

#### <span data-ttu-id="fa75f-390">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-390">remove_WebResourceRequested</span></span> 

<span data-ttu-id="fa75f-391">Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-391">Remove an event handler previously added with add_WebResourceRequested.</span></span>

> <span data-ttu-id="fa75f-392">パブリック HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-392">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-393">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="fa75f-393">add_ScriptDialogOpening</span></span> 

<span data-ttu-id="fa75f-394">Scriptの開始イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-394">Add an event handler for the ScriptDialogOpening event.</span></span>

> <span data-ttu-id="fa75f-395">パブリック HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-395">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-396">イベントは、webview の JavaScript ダイアログ (警告、確認、またはプロンプト) が表示されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-396">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span> <span data-ttu-id="fa75f-397">このイベントは、IWebView2Settings:: Aredefaultscript プロパティが false に設定されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-397">This event only fires if the IWebView2Settings::AreDefaultScriptDialogsEnabled property is set to false.</span></span>

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

#### <span data-ttu-id="fa75f-398">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="fa75f-398">remove_ScriptDialogOpening</span></span> 

<span data-ttu-id="fa75f-399">Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-399">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>

> <span data-ttu-id="fa75f-400">パブリック HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-400">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-401">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="fa75f-401">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="fa75f-402">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-402">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="fa75f-403">パブリック HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-403">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-404">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-404">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="fa75f-405">呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-405">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="fa75f-406">ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-406">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="fa75f-407">WebView は、各サイトで使用されている直前の拡大率を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-407">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="fa75f-408">そのため、別のページに移動するときにズーム倍率が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-408">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="fa75f-409">このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは DocumentStateChanged イベントの直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-409">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the DocumentStateChanged event.</span></span>

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

#### <span data-ttu-id="fa75f-410">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="fa75f-410">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="fa75f-411">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-411">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="fa75f-412">パブリック HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-412">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-413">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-413">add_PermissionRequested</span></span> 

<span data-ttu-id="fa75f-414">PermissionRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-414">Add an event handler for the PermissionRequested event.</span></span>

> <span data-ttu-id="fa75f-415">パブリック HRESULT [add_PermissionRequested](#add_permissionrequested)([IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-415">public HRESULT [add_PermissionRequested](#add_permissionrequested)([IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-416">WebView のコンテンツが権限のある一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-416">Fires when content in a WebView requests permission to access some privileged resources.</span></span>

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

#### <span data-ttu-id="fa75f-417">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="fa75f-417">remove_PermissionRequested</span></span> 

<span data-ttu-id="fa75f-418">Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-418">Remove an event handler previously added with add_PermissionRequested.</span></span>

> <span data-ttu-id="fa75f-419">パブリック HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-419">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-420">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="fa75f-420">add_ProcessFailed</span></span> 

<span data-ttu-id="fa75f-421">ProcessFailed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-421">Add an event handler for the ProcessFailed event.</span></span>

> <span data-ttu-id="fa75f-422">パブリック HRESULT [add_ProcessFailed](#add_processfailed)([IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-422">public HRESULT [add_ProcessFailed](#add_processfailed)([IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-423">WebView プロセスが予期せず終了した場合、または応答不能になったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-423">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>

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

#### <span data-ttu-id="fa75f-424">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="fa75f-424">remove_ProcessFailed</span></span> 

<span data-ttu-id="fa75f-425">Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-425">Remove an event handler previously added with add_ProcessFailed.</span></span>

> <span data-ttu-id="fa75f-426">パブリック HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-426">public HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-427">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="fa75f-427">AddScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="fa75f-428">グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-428">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="fa75f-429">パブリック HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR JavaScript、[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="fa75f-429">public HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR javaScript,[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="fa75f-430">挿入されたスクリプトは、RemoveScriptToExecuteOnDocumentCreated で削除されるまで、将来のすべての上位レベルのドキュメントと子フレームのナビゲーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-430">The injected script will apply to all future top level document and child frame navigations until removed with RemoveScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="fa75f-431">これは非同期的に適用されるため、今後のナビゲーションでスクリプトを実行する準備ができていることを確認する前に、完了ハンドラーが実行されるまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-431">This is applied asynchronously and you must wait for the completion handler to run before you can be sure that the script is ready to execute on future navigations.</span></span>

<span data-ttu-id="fa75f-432">[サンドボックス](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)のプロパティまたは[コンテンツセキュリティポリシーの HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)によって、HTML ドキュメントに何らかのサンドボックスが含まれている場合は、このスクリプトの実行に影響します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-432">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="fa75f-433">たとえば、' allow als ' キーワードが設定されていない場合、関数への呼び出し `alert` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-433">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

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

#### <span data-ttu-id="fa75f-434">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="fa75f-434">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="fa75f-435">AddScriptToExecuteOnDocumentCreated によって追加された、対応する JavaScript を削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-435">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>

> <span data-ttu-id="fa75f-436">パブリック HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span><span class="sxs-lookup"><span data-stu-id="fa75f-436">public HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span></span>

#### <span data-ttu-id="fa75f-437">Execuスクリプト</span><span class="sxs-lookup"><span data-stu-id="fa75f-437">ExecuteScript</span></span> 

<span data-ttu-id="fa75f-438">WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-438">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="fa75f-439">パブリック HRESULT の[Executescript](#executescript)(LPCWSTR JavaScript、[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="fa75f-439">public HRESULT [ExecuteScript](#executescript)(LPCWSTR javaScript,[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="fa75f-440">これは非同期的に実行されます。完了すると、ExecuteScriptCompletedHandler パラメーターでハンドラーが指定されると、指定された JavaScript を評価した結果を使って Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-440">This will execute asynchronously and when complete, if a handler is provided in the ExecuteScriptCompletedHandler parameter, its Invoke method will be called with the result of evaluating the provided JavaScript.</span></span> <span data-ttu-id="fa75f-441">結果値は、JSON でエンコードされた文字列です。</span><span class="sxs-lookup"><span data-stu-id="fa75f-441">The result value is a JSON encoded string.</span></span> <span data-ttu-id="fa75f-442">結果が定義されていない場合、参照循環が含まれている場合、または JSON にエンコードできない場合は、JSON null 値が文字列 ' null ' として返されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-442">If the result is undefined, contains a reference cycle, or otherwise cannot be encoded into JSON, the JSON null value will be returned as the string 'null'.</span></span> <span data-ttu-id="fa75f-443">明示的な戻り値のない関数は undefined を返します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-443">Note that a function that has no explicit return value returns undefined.</span></span> <span data-ttu-id="fa75f-444">実行されたスクリプトが未処理の例外をスローした場合、結果は ' null ' にもなります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-444">If the executed script throws an unhandled exception, then the result is also 'null'.</span></span> <span data-ttu-id="fa75f-445">このメソッドは非同期的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-445">This method is applied asynchronously.</span></span> <span data-ttu-id="fa75f-446">1つのドキュメントに対して webview を実行しているときに、操作が行われたときに、その呼び出しが行われてから JavaScript が実行される前に、移動が行われると、スクリプトは実行されず、ハンドラーは errorCode パラメーターの E_FAIL で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-446">If the call is made while the webview is on one document, and a navigation occurs after the call is made but before the JavaScript is executed, then the script will not be executed and the handler will be called with E_FAIL for its errorCode parameter.</span></span> <span data-ttu-id="fa75f-447">実行方法 IsScriptEnabled が FALSE に設定されている場合でも、スクリプトは機能します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-447">ExecuteScript will work even if IsScriptEnabled is set to FALSE.</span></span>

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

#### <span data-ttu-id="fa75f-448">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="fa75f-448">CapturePreview</span></span> 

<span data-ttu-id="fa75f-449">WebView が表示されている画像をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-449">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="fa75f-450">パブリック HRESULT [CapturePreview](#capturepreview)([WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) imageformat、IStream \* imagestream、[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="fa75f-450">public HRESULT [CapturePreview](#capturepreview)([WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) imageFormat,IStream \* imageStream,[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="fa75f-451">ImageFormat パラメーターを使用して、画像の形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-451">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="fa75f-452">結果のイメージバイナリデータは、指定された imageStream パラメーターに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-452">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="fa75f-453">CapturePreview がストリームへの書き込みを終了すると、指定された handler パラメーターの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-453">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

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

#### <span data-ttu-id="fa75f-454">再</span><span class="sxs-lookup"><span data-stu-id="fa75f-454">Reload</span></span> 

<span data-ttu-id="fa75f-455">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-455">Reload the current page.</span></span>

> <span data-ttu-id="fa75f-456">パブリック HRESULT [Reload](#reload)()</span><span class="sxs-lookup"><span data-stu-id="fa75f-456">public HRESULT [Reload](#reload)()</span></span>

<span data-ttu-id="fa75f-457">これは、すべてのナビゲーションイベント (HTTP キャッシュ内のエントリを含む) を含む、現在のトップレベルドキュメントの URI に移動する操作と似ています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-457">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="fa75f-458">ただし、戻る/forward 履歴は変更されません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-458">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="fa75f-459">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="fa75f-459">get_Bounds</span></span> 

<span data-ttu-id="fa75f-460">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="fa75f-460">The webview bounds.</span></span>

> <span data-ttu-id="fa75f-461">パブリック HRESULT [get_Bounds](#get_bounds)(RECT \* 境界)</span><span class="sxs-lookup"><span data-stu-id="fa75f-461">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="fa75f-462">境界は親 HWND を基準としています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-462">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="fa75f-463">アプリには、WebView を配置する2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-463">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="fa75f-464">WebView 親 HWND である子 HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-464">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="fa75f-465">WebView が必要な場所にこのウィンドウを配置します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-465">Position this window where the WebView should be.</span></span> <span data-ttu-id="fa75f-466">この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-466">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="fa75f-467">アプリの一番上のウィンドウは、WebView 親 HWND として使います。</span><span class="sxs-lookup"><span data-stu-id="fa75f-467">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="fa75f-468">Webview の左上隅を、アプリ内で適切に配置されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-468">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="fa75f-469">バインドされた値は、ホストの座標空間にあります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-469">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="fa75f-470">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="fa75f-470">put_Bounds</span></span> 

<span data-ttu-id="fa75f-471">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-471">Set the Bounds property.</span></span>

> <span data-ttu-id="fa75f-472">パブリック HRESULT [put_Bounds](#put_bounds)(四角形の境界)</span><span class="sxs-lookup"><span data-stu-id="fa75f-472">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

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

#### <span data-ttu-id="fa75f-473">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="fa75f-473">get_ZoomFactor</span></span> 

<span data-ttu-id="fa75f-474">WebView の現在のページのズームファクター。</span><span class="sxs-lookup"><span data-stu-id="fa75f-474">The zoom factor for the current page in the WebView.</span></span>

> <span data-ttu-id="fa75f-475">パブリック HRESULT [get_ZoomFactor](#get_zoomfactor)(Double \* ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="fa75f-475">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="fa75f-476">ズーム倍率はサイトごとに維持されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-476">The zoom factor is persisted per site.</span></span> <span data-ttu-id="fa75f-477">ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-477">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="fa75f-478">WebView を別のサイトからページに移動すると、前のページに設定されているズーム倍率は適用されません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-478">When WebView navigates to a page from a different site, the zoom factor set for the previous page will not be applied.</span></span> <span data-ttu-id="fa75f-479">アプリで特定のページの拡大率を設定する場合は、最初に DocumentStateChanged イベントハンドラーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-479">If the app wants to set the zoom factor for a certain page, the earliest place to do it is in the DocumentStateChanged event handler.</span></span> <span data-ttu-id="fa75f-480">これにより、指定されたズームファクターの ZoomFactorChanged イベントを受け取る前に、永続化されたズームファクターの ZoomFactorChanged イベントを受け取ることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-480">Note that if it does that, it might receive a ZoomFactorChanged event for the persisted zoom factor before receiving the ZoomFactorChanged event for the specified zoom factor.</span></span> <span data-ttu-id="fa75f-481">0以下の zoomFactor を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-481">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="fa75f-482">WebView には、内部でサポートされているズームファクター範囲もあります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-482">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="fa75f-483">指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-483">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="fa75f-484">この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。</span><span class="sxs-lookup"><span data-stu-id="fa75f-484">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="fa75f-485">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="fa75f-485">put_ZoomFactor</span></span> 

<span data-ttu-id="fa75f-486">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-486">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="fa75f-487">パブリック HRESULT [put_ZoomFactor](#put_zoomfactor)(double ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="fa75f-487">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="fa75f-488">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="fa75f-488">get_IsVisible</span></span> 

<span data-ttu-id="fa75f-489">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-489">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="fa75f-490">パブリック HRESULT [get_IsVisible](#get_isvisible)(BOOL \* IsVisible)</span><span class="sxs-lookup"><span data-stu-id="fa75f-490">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="fa75f-491">IsVisible が false に設定されている場合、webview は透過的であり、表示されません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-491">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="fa75f-492">ただし、この操作を行っても、webview (CreateWebView に渡された HWND パラメーター) が含まれているウィンドウには影響しません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-492">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateWebView).</span></span> <span data-ttu-id="fa75f-493">ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-493">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="fa75f-494">子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-494">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="fa75f-495">パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-495">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="fa75f-496">アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-496">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_webView->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_webView->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="fa75f-497">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="fa75f-497">put_IsVisible</span></span> 

<span data-ttu-id="fa75f-498">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-498">Set the IsVisible property.</span></span>

> <span data-ttu-id="fa75f-499">パブリック HRESULT [put_IsVisible](#put_isvisible)(BOOL IsVisible)</span><span class="sxs-lookup"><span data-stu-id="fa75f-499">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

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

#### <span data-ttu-id="fa75f-500">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="fa75f-500">PostWebMessageAsJson</span></span> 

<span data-ttu-id="fa75f-501">指定した webMessage をこの[IWebView2WebView]()のトップレベルのドキュメントに投稿します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-501">Post the specified webMessage to the top level document in this [IWebView2WebView]().</span></span>

> <span data-ttu-id="fa75f-502">パブリック HRESULT [Postwebmessageasjson](#postwebmessageasjson)(LPCWSTR webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="fa75f-502">public HRESULT [PostWebMessageAsJson](#postwebmessageasjson)(LPCWSTR webMessageAsJson)</span></span>

<span data-ttu-id="fa75f-503">最上位のドキュメントのウィンドウには、"." というメッセージイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-503">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="fa75f-504">このドキュメントの JavaScript は、次のようにしてイベントをサブスクライブし、サブスクライブを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-504">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span> 

```cpp
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

 <span data-ttu-id="fa75f-505">イベント引数は、のインスタンス `MessageEvent` です。</span><span class="sxs-lookup"><span data-stu-id="fa75f-505">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="fa75f-506">IWebView2Settings:: IsWebMessageEnabled の設定は true である必要があります。また、このメソッドは E_INVALIDARG で失敗します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-506">The IWebView2Settings::IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="fa75f-507">イベント arg の data プロパティは、JSON 文字列として JavaScript オブジェクトに解析された webMessage 文字列のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="fa75f-507">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="fa75f-508">イベント arg の source プロパティは、オブジェクトへの参照です `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="fa75f-508">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="fa75f-509">Webview の HTML ドキュメントからホストにメッセージを送信する方法については、「SetWebMessageReceivedEventHandler」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-509">See SetWebMessageReceivedEventHandler for information on sending messages from the HTML document in the webview to the host.</span></span> <span data-ttu-id="fa75f-510">このメッセージは非同期的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-510">This message is sent asynchronously.</span></span> <span data-ttu-id="fa75f-511">メッセージがページに投稿される前にナビゲーションが発生した場合、メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-511">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

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

#### <span data-ttu-id="fa75f-512">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="fa75f-512">PostWebMessageAsString</span></span> 

<span data-ttu-id="fa75f-513">これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。</span><span class="sxs-lookup"><span data-stu-id="fa75f-513">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="fa75f-514">パブリック HRESULT [Postwebmessageasstring](#postwebmessageasstring)(LPCWSTR webmessageasstring)</span><span class="sxs-lookup"><span data-stu-id="fa75f-514">public HRESULT [PostWebMessageAsString](#postwebmessageasstring)(LPCWSTR webMessageAsString)</span></span>

<span data-ttu-id="fa75f-515">これは、PostWebMessageAsJson とまったく同じように動作し `window.chrome.webview` ますが、message イベント arg の data プロパティは、webMessageAsString と同じ値を持つ文字列になります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-515">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="fa75f-516">JSON オブジェクトではなく単純な文字列を使って通信する場合は、PostWebMessageAsJson の代わりに、これを使います。</span><span class="sxs-lookup"><span data-stu-id="fa75f-516">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="fa75f-517">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="fa75f-517">add_WebMessageReceived</span></span> 

<span data-ttu-id="fa75f-518">このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-518">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="fa75f-519">パブリック HRESULT [add_WebMessageReceived](#add_webmessagereceived)([IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) \* handler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-519">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)([IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-520">PostMessage 関数は、 `void postMessage(object)` JSON 変換でサポートされているオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="fa75f-520">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span>

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

 <span data-ttu-id="fa75f-521">PostMessage が呼び出されると、この SetWebMessageReceivedEventHandler メソッドによって設定された[IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md)が、postMessage のオブジェクトパラメーターを JSON 文字列に変換して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-521">When postMessage is called, the [IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) set via this SetWebMessageReceivedEventHandler method will be invoked with the postMessage's object parameter converted to a JSON string.</span></span>

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

#### <span data-ttu-id="fa75f-522">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="fa75f-522">remove_WebMessageReceived</span></span> 

<span data-ttu-id="fa75f-523">Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-523">Remove an event handler previously added with add_WebMessageReceived.</span></span>

> <span data-ttu-id="fa75f-524">パブリック HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-524">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-525">Close</span><span class="sxs-lookup"><span data-stu-id="fa75f-525">Close</span></span> 

<span data-ttu-id="fa75f-526">Webview を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-526">Closes the webview and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="fa75f-527">パブリック HRESULT [Close](#close)()</span><span class="sxs-lookup"><span data-stu-id="fa75f-527">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="fa75f-528">ブラウザーの instace をクリーンアップすると、webview に電源が入っているリソースが解放されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-528">Cleaning up the browser instace will release the resources powering the webview.</span></span> <span data-ttu-id="fa75f-529">他の webviews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-529">The browser instance will be shut down if there are no other webviews using it.</span></span>

<span data-ttu-id="fa75f-530">Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="fa75f-530">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="fa75f-531">具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-531">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="fa75f-532">"閉じる" は、WebView が最終的な参照を失い、destructed されたときに暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-532">Close is implicitly called when the WebView loses its final reference and is destructed.</span></span> <span data-ttu-id="fa75f-533">ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-533">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="fa75f-534">具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-534">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="fa75f-535">Close は、すべてのイベントハンドラーを解放することで、このサイクルを中断します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-535">Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="fa75f-536">ただし、このような状況を回避するには、webview で明示的に Close を呼び出し、webview を適切にクリーンアップするために、WebView への参照をキャプチャしないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-536">But to avoid this situation it is best practice to both explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

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

#### <span data-ttu-id="fa75f-537">Calldevon Protocolメソッド</span><span class="sxs-lookup"><span data-stu-id="fa75f-537">CallDevToolsProtocolMethod</span></span> 

<span data-ttu-id="fa75f-538">非同期の Devて Protocol メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-538">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="fa75f-539">パブリック HRESULT[呼び出し DevLPCWSTR Protocolmethod](#calldevtoolsprotocolmethod)(METHODNAME、LPCWSTR ParametersAsJson、[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="fa75f-539">public HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)(LPCWSTR methodName,LPCWSTR parametersAsJson,[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="fa75f-540">使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-540">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="fa75f-541">MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="fa75f-541">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="fa75f-542">ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。</span><span class="sxs-lookup"><span data-stu-id="fa75f-542">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="fa75f-543">メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-543">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="fa75f-544">Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-544">Invoke will be called with the method's return object as a JSON string.</span></span>

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

#### <span data-ttu-id="fa75f-545">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="fa75f-545">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="fa75f-546">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="fa75f-546">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="fa75f-547">パブリック HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)(LPCWSTR EventName、[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-547">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)(LPCWSTR eventName,[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="fa75f-548">使用できるイベントの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-548">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available events.</span></span> <span data-ttu-id="fa75f-549">EventName パラメーターは、形式におけるイベントの完全な名前です `{domain}.{event}` 。</span><span class="sxs-lookup"><span data-stu-id="fa75f-549">The eventName parameter is the full name of the event in the format `{domain}.{event}`.</span></span> <span data-ttu-id="fa75f-550">ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-550">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="fa75f-551">Invoke は、JSON 文字列として CDP イベントのパラメーターオブジェクトを含むイベント引数オブジェクトで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-551">Invoke will be called with the an event args object containing the CDP event's parameter object as a JSON string.</span></span>

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

#### <span data-ttu-id="fa75f-552">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="fa75f-552">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="fa75f-553">Add_DevToolsProtocolEventReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-553">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="fa75f-554">パブリック HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(LPCWSTR EventName, EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="fa75f-554">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(LPCWSTR eventName,EventRegistrationToken token)</span></span>

#### <span data-ttu-id="fa75f-555">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="fa75f-555">get_BrowserProcessId</span></span> 

<span data-ttu-id="fa75f-556">WebView をホストしているブラウザープロセスのプロセス id。</span><span class="sxs-lookup"><span data-stu-id="fa75f-556">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="fa75f-557">パブリック HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* 値)</span><span class="sxs-lookup"><span data-stu-id="fa75f-557">public HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* value)</span></span>

#### <span data-ttu-id="fa75f-558">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="fa75f-558">get_CanGoBack</span></span> 

<span data-ttu-id="fa75f-559">Webview をナビゲーション履歴の前のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-559">Can navigate the webview to the previous page in the navigation history.</span></span>

> <span data-ttu-id="fa75f-560">パブリック HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* CanGoBack)</span><span class="sxs-lookup"><span data-stu-id="fa75f-560">public HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* canGoBack)</span></span>

<span data-ttu-id="fa75f-561">DocumentStateChanged イベントを使用して値を変更 get_CanGoBack ます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-561">get_CanGoBack change value with the DocumentStateChanged event.</span></span>

#### <span data-ttu-id="fa75f-562">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="fa75f-562">get_CanGoForward</span></span> 

<span data-ttu-id="fa75f-563">Webview をナビゲーション履歴の次のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-563">Can navigate the webview to the next page in the navigation history.</span></span>

> <span data-ttu-id="fa75f-564">パブリック HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* CanGoForward)</span><span class="sxs-lookup"><span data-stu-id="fa75f-564">public HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* canGoForward)</span></span>

<span data-ttu-id="fa75f-565">DocumentStateChanged イベントを使用して値を変更 get_CanGoForward ます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-565">get_CanGoForward change value with the DocumentStateChanged event.</span></span>

#### <span data-ttu-id="fa75f-566">GoBack</span><span class="sxs-lookup"><span data-stu-id="fa75f-566">GoBack</span></span> 

<span data-ttu-id="fa75f-567">ナビゲーション履歴で、webview を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-567">Navigates the webview to the previous page in the navigation history.</span></span>

> <span data-ttu-id="fa75f-568">パブリック HRESULT [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="fa75f-568">public HRESULT [GoBack](#goback)()</span></span>

#### <span data-ttu-id="fa75f-569">GoForward</span><span class="sxs-lookup"><span data-stu-id="fa75f-569">GoForward</span></span> 

<span data-ttu-id="fa75f-570">Webview をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-570">Navigates the webview to the next page in the navigation history.</span></span>

> <span data-ttu-id="fa75f-571">パブリック HRESULT [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="fa75f-571">public HRESULT [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="fa75f-572">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="fa75f-572">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span> 

<span data-ttu-id="fa75f-573">[IWebView2WebView:: CapturePreview](#capturepreview)メソッドで使用されている画像形式。</span><span class="sxs-lookup"><span data-stu-id="fa75f-573">Image format used by the [IWebView2WebView::CapturePreview](#capturepreview) method.</span></span>

> <span data-ttu-id="fa75f-574">列挙型[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)</span><span class="sxs-lookup"><span data-stu-id="fa75f-574">enum [WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)</span></span>

 <span data-ttu-id="fa75f-575">値</span><span class="sxs-lookup"><span data-stu-id="fa75f-575">Values</span></span>                         | <span data-ttu-id="fa75f-576">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-576">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="fa75f-577">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span><span class="sxs-lookup"><span data-stu-id="fa75f-577">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span></span>            | <span data-ttu-id="fa75f-578">PNG 画像形式。</span><span class="sxs-lookup"><span data-stu-id="fa75f-578">PNG image format.</span></span>
<span data-ttu-id="fa75f-579">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span><span class="sxs-lookup"><span data-stu-id="fa75f-579">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span></span>            | <span data-ttu-id="fa75f-580">JPEG イメージ形式。</span><span class="sxs-lookup"><span data-stu-id="fa75f-580">JPEG image format.</span></span>

#### <span data-ttu-id="fa75f-581">WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="fa75f-581">WEBVIEW2_SCRIPT_DIALOG_KIND</span></span> 

<span data-ttu-id="fa75f-582">[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)インターフェイスで使用される JavaScript ダイアログの種類。</span><span class="sxs-lookup"><span data-stu-id="fa75f-582">Kind of JavaScript dialog used in the [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) interface.</span></span>

> <span data-ttu-id="fa75f-583">列挙型[WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)</span><span class="sxs-lookup"><span data-stu-id="fa75f-583">enum [WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)</span></span>

 <span data-ttu-id="fa75f-584">値</span><span class="sxs-lookup"><span data-stu-id="fa75f-584">Values</span></span>                         | <span data-ttu-id="fa75f-585">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-585">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="fa75f-586">WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span><span class="sxs-lookup"><span data-stu-id="fa75f-586">WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span></span>            | <span data-ttu-id="fa75f-587">ウィンドウで呼び出されるダイアログ。警告 JavaScript 関数。</span><span class="sxs-lookup"><span data-stu-id="fa75f-587">A dialog invoked via the window.alert JavaScript function.</span></span>
<span data-ttu-id="fa75f-588">WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span><span class="sxs-lookup"><span data-stu-id="fa75f-588">WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span></span>            | <span data-ttu-id="fa75f-589">ウィンドウを通じて呼び出されるダイアログ。 JavaScript 関数を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fa75f-589">A dialog invoked via the window.confirm JavaScript function.</span></span>
<span data-ttu-id="fa75f-590">WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span><span class="sxs-lookup"><span data-stu-id="fa75f-590">WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span></span>            | <span data-ttu-id="fa75f-591">Window というプロンプトで呼び出されるダイアログ。</span><span class="sxs-lookup"><span data-stu-id="fa75f-591">A dialog invoked via the window.prompt JavaScript function.</span></span>

#### <span data-ttu-id="fa75f-592">WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="fa75f-592">WEBVIEW2_PROCESS_FAILED_KIND</span></span> 

<span data-ttu-id="fa75f-593">[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)インターフェイスで使用されているプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="fa75f-593">Kind of process failure used in the [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) interface.</span></span>

> <span data-ttu-id="fa75f-594">列挙型[WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)</span><span class="sxs-lookup"><span data-stu-id="fa75f-594">enum [WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)</span></span>

 <span data-ttu-id="fa75f-595">値</span><span class="sxs-lookup"><span data-stu-id="fa75f-595">Values</span></span>                         | <span data-ttu-id="fa75f-596">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-596">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="fa75f-597">WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="fa75f-597">WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span></span>            | <span data-ttu-id="fa75f-598">ブラウザープロセスが予期せず終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-598">Indicates the browser process terminated unexpectedly.</span></span>
<span data-ttu-id="fa75f-599">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="fa75f-599">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span></span>            | <span data-ttu-id="fa75f-600">レンダープロセスが予期せず終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-600">Indicates the render process terminated unexpectedly.</span></span>
<span data-ttu-id="fa75f-601">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span><span class="sxs-lookup"><span data-stu-id="fa75f-601">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span></span>            | <span data-ttu-id="fa75f-602">レンダープロセスが応答しなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-602">Indicates the render process becomes unresponsive.</span></span>

#### <span data-ttu-id="fa75f-603">WEBVIEW2_PERMISSION_TYPE</span><span class="sxs-lookup"><span data-stu-id="fa75f-603">WEBVIEW2_PERMISSION_TYPE</span></span> 

<span data-ttu-id="fa75f-604">アクセス許可要求の種類。</span><span class="sxs-lookup"><span data-stu-id="fa75f-604">The type of a permission request.</span></span>

> <span data-ttu-id="fa75f-605">列挙型[WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)</span><span class="sxs-lookup"><span data-stu-id="fa75f-605">enum [WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)</span></span>

 <span data-ttu-id="fa75f-606">値</span><span class="sxs-lookup"><span data-stu-id="fa75f-606">Values</span></span>                         | <span data-ttu-id="fa75f-607">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-607">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="fa75f-608">WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="fa75f-608">WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION</span></span>            | <span data-ttu-id="fa75f-609">不明な権限。</span><span class="sxs-lookup"><span data-stu-id="fa75f-609">Unknown permission.</span></span>
<span data-ttu-id="fa75f-610">WEBVIEW2_PERMISSION_TYPE_MICROPHONE</span><span class="sxs-lookup"><span data-stu-id="fa75f-610">WEBVIEW2_PERMISSION_TYPE_MICROPHONE</span></span>            | <span data-ttu-id="fa75f-611">オーディオをキャプチャするためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="fa75f-611">Permission to capture audio.</span></span>
<span data-ttu-id="fa75f-612">WEBVIEW2_PERMISSION_TYPE_CAMERA</span><span class="sxs-lookup"><span data-stu-id="fa75f-612">WEBVIEW2_PERMISSION_TYPE_CAMERA</span></span>            | <span data-ttu-id="fa75f-613">ビデオをキャプチャするためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="fa75f-613">Permission to capture video.</span></span>
<span data-ttu-id="fa75f-614">WEBVIEW2_PERMISSION_TYPE_GEOLOCATION</span><span class="sxs-lookup"><span data-stu-id="fa75f-614">WEBVIEW2_PERMISSION_TYPE_GEOLOCATION</span></span>            | <span data-ttu-id="fa75f-615">位置情報へのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="fa75f-615">Permission to access geolocation.</span></span>
<span data-ttu-id="fa75f-616">WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="fa75f-616">WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS</span></span>            | <span data-ttu-id="fa75f-617">Web 通知を送信するためのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="fa75f-617">Permission to send web notifications.</span></span>
<span data-ttu-id="fa75f-618">WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS</span><span class="sxs-lookup"><span data-stu-id="fa75f-618">WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS</span></span>            | <span data-ttu-id="fa75f-619">汎用センサーへのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="fa75f-619">Permission to access generic sensor.</span></span>
<span data-ttu-id="fa75f-620">WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ</span><span class="sxs-lookup"><span data-stu-id="fa75f-620">WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ</span></span>            | <span data-ttu-id="fa75f-621">ユーザーのジェスチャを使わずにシステムクリップボードを読み取る権限。</span><span class="sxs-lookup"><span data-stu-id="fa75f-621">Permission to read system clipboard without a user gesture.</span></span>

#### <span data-ttu-id="fa75f-622">WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="fa75f-622">WEBVIEW2_PERMISSION_STATE</span></span> 

<span data-ttu-id="fa75f-623">アクセス許可要求に対する応答。</span><span class="sxs-lookup"><span data-stu-id="fa75f-623">Response to a permission request.</span></span>

> <span data-ttu-id="fa75f-624">列挙型[WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)</span><span class="sxs-lookup"><span data-stu-id="fa75f-624">enum [WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)</span></span>

 <span data-ttu-id="fa75f-625">値</span><span class="sxs-lookup"><span data-stu-id="fa75f-625">Values</span></span>                         | <span data-ttu-id="fa75f-626">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-626">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="fa75f-627">WEBVIEW2_PERMISSION_STATE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fa75f-627">WEBVIEW2_PERMISSION_STATE_DEFAULT</span></span>            | <span data-ttu-id="fa75f-628">既定のブラウザー動作を使用します。通常はユーザーに判断を求めます。</span><span class="sxs-lookup"><span data-stu-id="fa75f-628">Use default browser behavior, which normally prompt users for decision.</span></span>
<span data-ttu-id="fa75f-629">WEBVIEW2_PERMISSION_STATE_ALLOW</span><span class="sxs-lookup"><span data-stu-id="fa75f-629">WEBVIEW2_PERMISSION_STATE_ALLOW</span></span>            | <span data-ttu-id="fa75f-630">権限の要求を許可します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-630">Grant the permission request.</span></span>
<span data-ttu-id="fa75f-631">WEBVIEW2_PERMISSION_STATE_DENY</span><span class="sxs-lookup"><span data-stu-id="fa75f-631">WEBVIEW2_PERMISSION_STATE_DENY</span></span>            | <span data-ttu-id="fa75f-632">権限の要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-632">Deny the permission request.</span></span>

#### <span data-ttu-id="fa75f-633">WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="fa75f-633">WEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="fa75f-634">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="fa75f-634">Reason for moving focus.</span></span>

> <span data-ttu-id="fa75f-635">列挙型[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="fa75f-635">enum [WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)</span></span>

 <span data-ttu-id="fa75f-636">値</span><span class="sxs-lookup"><span data-stu-id="fa75f-636">Values</span></span>                         | <span data-ttu-id="fa75f-637">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-637">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="fa75f-638">WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="fa75f-638">WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="fa75f-639">コード設定による WebView へのフォーカス。</span><span class="sxs-lookup"><span data-stu-id="fa75f-639">Code setting focus into WebView.</span></span>
<span data-ttu-id="fa75f-640">WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="fa75f-640">WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="fa75f-641">タブトラバーサルを前方に移動するためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="fa75f-641">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="fa75f-642">WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="fa75f-642">WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="fa75f-643">タブトラバーサルに戻るためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="fa75f-643">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="fa75f-644">WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="fa75f-644">WEBVIEW2_WEB_ERROR_STATUS</span></span> 

<span data-ttu-id="fa75f-645">Web ナビゲーションのエラー状態の値。</span><span class="sxs-lookup"><span data-stu-id="fa75f-645">Error status values for web navigations.</span></span>

> <span data-ttu-id="fa75f-646">列挙型[WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)</span><span class="sxs-lookup"><span data-stu-id="fa75f-646">enum [WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)</span></span>

 <span data-ttu-id="fa75f-647">値</span><span class="sxs-lookup"><span data-stu-id="fa75f-647">Values</span></span>                         | <span data-ttu-id="fa75f-648">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-648">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="fa75f-649">WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="fa75f-649">WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span></span>            | <span data-ttu-id="fa75f-650">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-650">An unknown error occurred.</span></span>
<span data-ttu-id="fa75f-651">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span><span class="sxs-lookup"><span data-stu-id="fa75f-651">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span></span>            | <span data-ttu-id="fa75f-652">SSL 証明書の共通名が web アドレスと一致しません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-652">The SSL certificate common name does not match the web address.</span></span>
<span data-ttu-id="fa75f-653">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="fa75f-653">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span></span>            | <span data-ttu-id="fa75f-654">SSL 証明書の有効期限が切れています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-654">The SSL certificate has expired.</span></span>
<span data-ttu-id="fa75f-655">WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span><span class="sxs-lookup"><span data-stu-id="fa75f-655">WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span></span>            | <span data-ttu-id="fa75f-656">SSL クライアント証明書にエラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-656">The SSL client certificate contains errors.</span></span>
<span data-ttu-id="fa75f-657">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span><span class="sxs-lookup"><span data-stu-id="fa75f-657">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span></span>            | <span data-ttu-id="fa75f-658">SSL 証明書が失効しています。</span><span class="sxs-lookup"><span data-stu-id="fa75f-658">The SSL certificate has been revoked.</span></span>
<span data-ttu-id="fa75f-659">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="fa75f-659">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span></span>            | <span data-ttu-id="fa75f-660">SSL 証明書が無効です。</span><span class="sxs-lookup"><span data-stu-id="fa75f-660">The SSL certificate is invalid.</span></span>
<span data-ttu-id="fa75f-661">WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="fa75f-661">WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span></span>            | <span data-ttu-id="fa75f-662">ホストに到達できません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-662">The host is unreachable.</span></span>
<span data-ttu-id="fa75f-663">WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa75f-663">WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span></span>            | <span data-ttu-id="fa75f-664">接続がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-664">The connection has timed out.</span></span>
<span data-ttu-id="fa75f-665">WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span><span class="sxs-lookup"><span data-stu-id="fa75f-665">WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span></span>            | <span data-ttu-id="fa75f-666">サーバーが無効または認識不能な応答を返しました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-666">The server returned an invalid or unrecognized response.</span></span>
<span data-ttu-id="fa75f-667">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span><span class="sxs-lookup"><span data-stu-id="fa75f-667">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span></span>            | <span data-ttu-id="fa75f-668">接続が中止されました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-668">The connection was aborted.</span></span>
<span data-ttu-id="fa75f-669">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span><span class="sxs-lookup"><span data-stu-id="fa75f-669">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span></span>            | <span data-ttu-id="fa75f-670">接続がリセットされました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-670">The connection was reset.</span></span>
<span data-ttu-id="fa75f-671">WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span><span class="sxs-lookup"><span data-stu-id="fa75f-671">WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span></span>            | <span data-ttu-id="fa75f-672">インターネット接続が切断されました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-672">The Internet connection has been lost.</span></span>
<span data-ttu-id="fa75f-673">WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="fa75f-673">WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span></span>            | <span data-ttu-id="fa75f-674">宛先に接続できません。</span><span class="sxs-lookup"><span data-stu-id="fa75f-674">Cannot connect to destination.</span></span>
<span data-ttu-id="fa75f-675">WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="fa75f-675">WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span></span>            | <span data-ttu-id="fa75f-676">指定されたホスト名を解決できませんでした。</span><span class="sxs-lookup"><span data-stu-id="fa75f-676">Could not resolve provided host name.</span></span>
<span data-ttu-id="fa75f-677">WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span><span class="sxs-lookup"><span data-stu-id="fa75f-677">WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span></span>            | <span data-ttu-id="fa75f-678">操作が取り消されました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-678">The operation was canceled.</span></span>
<span data-ttu-id="fa75f-679">WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span><span class="sxs-lookup"><span data-stu-id="fa75f-679">WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span></span>            | <span data-ttu-id="fa75f-680">要求のリダイレクトに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-680">The request redirect failed.</span></span>
<span data-ttu-id="fa75f-681">WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span><span class="sxs-lookup"><span data-stu-id="fa75f-681">WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span></span>            | <span data-ttu-id="fa75f-682">予期しないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fa75f-682">An unexpected error occurred.</span></span>

#### <span data-ttu-id="fa75f-683">WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="fa75f-683">WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span> 

<span data-ttu-id="fa75f-684">Web リソース要求コンテキストの列挙。</span><span class="sxs-lookup"><span data-stu-id="fa75f-684">Enum for web resource request contexts.</span></span>

> <span data-ttu-id="fa75f-685">列挙型[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)</span><span class="sxs-lookup"><span data-stu-id="fa75f-685">enum [WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)</span></span>

 <span data-ttu-id="fa75f-686">値</span><span class="sxs-lookup"><span data-stu-id="fa75f-686">Values</span></span>                         | <span data-ttu-id="fa75f-687">説明</span><span class="sxs-lookup"><span data-stu-id="fa75f-687">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="fa75f-688">WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span><span class="sxs-lookup"><span data-stu-id="fa75f-688">WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span></span>            | <span data-ttu-id="fa75f-689">すべてのリソース。</span><span class="sxs-lookup"><span data-stu-id="fa75f-689">All resources.</span></span>
<span data-ttu-id="fa75f-690">WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span><span class="sxs-lookup"><span data-stu-id="fa75f-690">WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span></span>            | <span data-ttu-id="fa75f-691">ドキュメントリソース。</span><span class="sxs-lookup"><span data-stu-id="fa75f-691">Document resources.</span></span>
<span data-ttu-id="fa75f-692">WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span><span class="sxs-lookup"><span data-stu-id="fa75f-692">WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span></span>            | <span data-ttu-id="fa75f-693">CSS リソース。</span><span class="sxs-lookup"><span data-stu-id="fa75f-693">CSS resources.</span></span>
<span data-ttu-id="fa75f-694">WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span><span class="sxs-lookup"><span data-stu-id="fa75f-694">WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span></span>            | <span data-ttu-id="fa75f-695">画像リソース。</span><span class="sxs-lookup"><span data-stu-id="fa75f-695">Image resources.</span></span>
<span data-ttu-id="fa75f-696">WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span><span class="sxs-lookup"><span data-stu-id="fa75f-696">WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span></span>            | <span data-ttu-id="fa75f-697">その他のメディアリソース (ビデオなど)。</span><span class="sxs-lookup"><span data-stu-id="fa75f-697">Other media resources such as videos.</span></span>
<span data-ttu-id="fa75f-698">WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span><span class="sxs-lookup"><span data-stu-id="fa75f-698">WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span></span>            | <span data-ttu-id="fa75f-699">フォントリソース。</span><span class="sxs-lookup"><span data-stu-id="fa75f-699">Font resources.</span></span>
<span data-ttu-id="fa75f-700">WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span><span class="sxs-lookup"><span data-stu-id="fa75f-700">WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span></span>            | <span data-ttu-id="fa75f-701">スクリプトリソース。</span><span class="sxs-lookup"><span data-stu-id="fa75f-701">Script resources.</span></span>
<span data-ttu-id="fa75f-702">WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span><span class="sxs-lookup"><span data-stu-id="fa75f-702">WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span></span>            | <span data-ttu-id="fa75f-703">XML HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="fa75f-703">XML HTTP requests.</span></span>
<span data-ttu-id="fa75f-704">WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span><span class="sxs-lookup"><span data-stu-id="fa75f-704">WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span></span>            | <span data-ttu-id="fa75f-705">API 通信を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa75f-705">Fetch API communication.</span></span>
<span data-ttu-id="fa75f-706">WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span><span class="sxs-lookup"><span data-stu-id="fa75f-706">WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span></span>            | <span data-ttu-id="fa75f-707">TextTrack のリソース。</span><span class="sxs-lookup"><span data-stu-id="fa75f-707">TextTrack resources.</span></span>
<span data-ttu-id="fa75f-708">WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span><span class="sxs-lookup"><span data-stu-id="fa75f-708">WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span></span>            | 
<span data-ttu-id="fa75f-709">WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span><span class="sxs-lookup"><span data-stu-id="fa75f-709">WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span></span>            | 
<span data-ttu-id="fa75f-710">WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span><span class="sxs-lookup"><span data-stu-id="fa75f-710">WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span></span>            | 
<span data-ttu-id="fa75f-711">WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span><span class="sxs-lookup"><span data-stu-id="fa75f-711">WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span></span>            | 
<span data-ttu-id="fa75f-712">WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span><span class="sxs-lookup"><span data-stu-id="fa75f-712">WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span></span>            | 
<span data-ttu-id="fa75f-713">WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span><span class="sxs-lookup"><span data-stu-id="fa75f-713">WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span></span>            | 
<span data-ttu-id="fa75f-714">WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span><span class="sxs-lookup"><span data-stu-id="fa75f-714">WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span></span>            | <span data-ttu-id="fa75f-715">その他のリソース。</span><span class="sxs-lookup"><span data-stu-id="fa75f-715">Other resources.</span></span>
