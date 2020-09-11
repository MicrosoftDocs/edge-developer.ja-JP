---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 92fad0c93e4942a92f5940834b0057043491b539
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010209"
---
# <span data-ttu-id="fe943-104">0.9.579-Reference (WebView2 Win32 C++)</span><span class="sxs-lookup"><span data-stu-id="fe943-104">0.9.579 - Reference (WebView2 Win32 C++)</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]

<span data-ttu-id="fe943-105">Microsoft Edge WebView2 コントロールを使用すると、 [Microsoft edge \ (Chromium \)](https://www.microsoftedgeinsider.com) を使ってアプリケーションの web コンテンツをレンダリングエンジンとしてホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe943-105">The Microsoft Edge WebView2 control enables you to host web content in your application using [Microsoft Edge \(Chromium\)](https://www.microsoftedgeinsider.com) as the rendering engine.</span></span>  <span data-ttu-id="fe943-106">詳細については、「 [Microsoft Edge WebView2 の概要](../../index.md)」および「 [WebView2 の使用を開始](../../gettingstarted/win32.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe943-106">For more information, see [Overview of Microsoft Edge WebView2](../../index.md)) and [Getting Started with WebView2](../../gettingstarted/win32.md).</span></span>  <span data-ttu-id="fe943-107">[ICoreWebView2](0-9-538/ICoreWebView2.md) は、API の詳細を理解するのに最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="fe943-107">[ICoreWebView2](0-9-538/ICoreWebView2.md) is a great place to start learning the details of the API.</span></span>  

## <span data-ttu-id="fe943-108">グローバル</span><span class="sxs-lookup"><span data-stu-id="fe943-108">Globals</span></span>  

*   [<span data-ttu-id="fe943-109">グローバル</span><span class="sxs-lookup"><span data-stu-id="fe943-109">Globals</span></span>](0-9-538/webview2-idl.md)  

## <span data-ttu-id="fe943-110">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe943-110">Interfaces</span></span>  
*   [<span data-ttu-id="fe943-111">ICoreWebView2</span><span class="sxs-lookup"><span data-stu-id="fe943-111">ICoreWebView2</span></span>](0-9-538/icorewebview2.md)
*   [<span data-ttu-id="fe943-112">ICoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="fe943-112">ICoreWebView2Controller</span></span>](0-9-538/icorewebview2controller.md)
*   [<span data-ttu-id="fe943-113">ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="fe943-113">ICoreWebView2Deferral</span></span>](0-9-538/icorewebview2deferral.md)
*   [<span data-ttu-id="fe943-114">ICoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="fe943-114">ICoreWebView2DevToolsProtocolEventReceiver</span></span>](0-9-538/icorewebview2devtoolsprotocoleventreceiver.md)
*   [<span data-ttu-id="fe943-115">ICoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="fe943-115">ICoreWebView2Environment</span></span>](0-9-538/icorewebview2environment.md)
*   [<span data-ttu-id="fe943-116">ICoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="fe943-116">ICoreWebView2EnvironmentOptions</span></span>](0-9-538/icorewebview2environmentoptions.md)
*   [<span data-ttu-id="fe943-117">ICoreWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="fe943-117">ICoreWebView2HttpHeadersCollectionIterator</span></span>](0-9-538/icorewebview2httpheaderscollectioniterator.md)
*   [<span data-ttu-id="fe943-118">ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="fe943-118">ICoreWebView2HttpRequestHeaders</span></span>](0-9-538/icorewebview2httprequestheaders.md)
*   [<span data-ttu-id="fe943-119">ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="fe943-119">ICoreWebView2HttpResponseHeaders</span></span>](0-9-538/icorewebview2httpresponseheaders.md)
*   [<span data-ttu-id="fe943-120">ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="fe943-120">ICoreWebView2Settings</span></span>](0-9-538/icorewebview2settings.md)
*   [<span data-ttu-id="fe943-121">ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="fe943-121">ICoreWebView2WebResourceRequest</span></span>](0-9-538/icorewebview2webresourcerequest.md)
*   [<span data-ttu-id="fe943-122">ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="fe943-122">ICoreWebView2WebResourceResponse</span></span>](0-9-538/icorewebview2webresourceresponse.md)

### <span data-ttu-id="fe943-123">イベント引数</span><span class="sxs-lookup"><span data-stu-id="fe943-123">Event arguments</span></span>

*   [<span data-ttu-id="fe943-124">ICoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-124">ICoreWebView2AcceleratorKeyPressedEventArgs</span></span>](0-9-538/icorewebview2acceleratorkeypressedeventargs.md)
*   [<span data-ttu-id="fe943-125">ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-125">ICoreWebView2ContentLoadingEventArgs</span></span>](0-9-538/icorewebview2contentloadingeventargs.md)
*   [<span data-ttu-id="fe943-126">ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-126">ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span>](0-9-538/icorewebview2devtoolsprotocoleventreceivedeventargs.md)
*   [<span data-ttu-id="fe943-127">ICoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-127">ICoreWebView2MoveFocusRequestedEventArgs</span></span>](0-9-538/icorewebview2movefocusrequestedeventargs.md)
*   [<span data-ttu-id="fe943-128">ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-128">ICoreWebView2NavigationCompletedEventArgs</span></span>](0-9-538/icorewebview2navigationcompletedeventargs.md)
*   [<span data-ttu-id="fe943-129">ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-129">ICoreWebView2NavigationStartingEventArgs</span></span>](0-9-538/icorewebview2navigationstartingeventargs.md)
*   [<span data-ttu-id="fe943-130">ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-130">ICoreWebView2NewWindowRequestedEventArgs</span></span>](0-9-538/icorewebview2newwindowrequestedeventargs.md)
*   [<span data-ttu-id="fe943-131">ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-131">ICoreWebView2PermissionRequestedEventArgs</span></span>](0-9-538/icorewebview2permissionrequestedeventargs.md)
*   [<span data-ttu-id="fe943-132">ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-132">ICoreWebView2ProcessFailedEventArgs</span></span>](0-9-538/icorewebview2processfailedeventargs.md)
*   [<span data-ttu-id="fe943-133">ICoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-133">ICoreWebView2ScriptDialogOpeningEventArgs</span></span>](0-9-538/icorewebview2scriptdialogopeningeventargs.md)
*   [<span data-ttu-id="fe943-134">ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-134">ICoreWebView2SourceChangedEventArgs</span></span>](0-9-538/icorewebview2sourcechangedeventargs.md)
*   [<span data-ttu-id="fe943-135">ICoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-135">ICoreWebView2WebMessageReceivedEventArgs</span></span>](0-9-538/icorewebview2webmessagereceivedeventargs.md)
*   [<span data-ttu-id="fe943-136">ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-136">ICoreWebView2WebResourceRequestedEventArgs</span></span>](0-9-538/icorewebview2webresourcerequestedeventargs.md)

### <span data-ttu-id="fe943-137">デリゲート</span><span class="sxs-lookup"><span data-stu-id="fe943-137">Delegates</span></span>

*   [<span data-ttu-id="fe943-138">ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-138">ICoreWebView2AcceleratorKeyPressedEventHandler</span></span>](0-9-538/icorewebview2acceleratorkeypressedeventhandler.md)
*   [<span data-ttu-id="fe943-139">ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-139">ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span>](0-9-538/icorewebview2addscripttoexecuteondocumentcreatedcompletedhandler.md)
*   [<span data-ttu-id="fe943-140">ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-140">ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span>](0-9-538/icorewebview2calldevtoolsprotocolmethodcompletedhandler.md)
*   [<span data-ttu-id="fe943-141">ICoreWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-141">ICoreWebView2CapturePreviewCompletedHandler</span></span>](0-9-538/icorewebview2capturepreviewcompletedhandler.md)
*   [<span data-ttu-id="fe943-142">ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-142">ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span>](0-9-538/icorewebview2containsfullscreenelementchangedeventhandler.md)
*   [<span data-ttu-id="fe943-143">ICoreWebView2ContentLoadingEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-143">ICoreWebView2ContentLoadingEventHandler</span></span>](0-9-538/icorewebview2contentloadingeventhandler.md)
*   [<span data-ttu-id="fe943-144">ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-144">ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span>](0-9-538/icorewebview2createcorewebview2controllercompletedhandler.md)
*   [<span data-ttu-id="fe943-145">ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-145">ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span>](0-9-538/icorewebview2createcorewebview2environmentcompletedhandler.md)
*   [<span data-ttu-id="fe943-146">ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-146">ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span>](0-9-538/icorewebview2devtoolsprotocoleventreceivedeventhandler.md)
*   [<span data-ttu-id="fe943-147">ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-147">ICoreWebView2DocumentTitleChangedEventHandler</span></span>](0-9-538/icorewebview2documenttitlechangedeventhandler.md)
*   [<span data-ttu-id="fe943-148">ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-148">ICoreWebView2ExecuteScriptCompletedHandler</span></span>](0-9-538/icorewebview2executescriptcompletedhandler.md)
*   [<span data-ttu-id="fe943-149">ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-149">ICoreWebView2FocusChangedEventHandler</span></span>](0-9-538/icorewebview2focuschangedeventhandler.md)
*   [<span data-ttu-id="fe943-150">ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-150">ICoreWebView2HistoryChangedEventHandler</span></span>](0-9-538/icorewebview2historychangedeventhandler.md)
*   [<span data-ttu-id="fe943-151">ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-151">ICoreWebView2MoveFocusRequestedEventHandler</span></span>](0-9-538/icorewebview2movefocusrequestedeventhandler.md)
*   [<span data-ttu-id="fe943-152">ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-152">ICoreWebView2NavigationCompletedEventHandler</span></span>](0-9-538/icorewebview2navigationcompletedeventhandler.md)
*   [<span data-ttu-id="fe943-153">ICoreWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-153">ICoreWebView2NavigationStartingEventHandler</span></span>](0-9-538/icorewebview2navigationstartingeventhandler.md)
*   [<span data-ttu-id="fe943-154">ICoreWebView2NewBrowserVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-154">ICoreWebView2NewBrowserVersionAvailableEventHandler</span></span>](0-9-538/icorewebview2newbrowserversionavailableeventhandler.md)
*   [<span data-ttu-id="fe943-155">ICoreWebView2NewWindowRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-155">ICoreWebView2NewWindowRequestedEventHandler</span></span>](0-9-538/icorewebview2newwindowrequestedeventhandler.md)
*   [<span data-ttu-id="fe943-156">ICoreWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-156">ICoreWebView2PermissionRequestedEventHandler</span></span>](0-9-538/icorewebview2permissionrequestedeventhandler.md)
*   [<span data-ttu-id="fe943-157">ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-157">ICoreWebView2ProcessFailedEventHandler</span></span>](0-9-538/icorewebview2processfailedeventhandler.md)
*   [<span data-ttu-id="fe943-158">ICoreWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-158">ICoreWebView2ScriptDialogOpeningEventHandler</span></span>](0-9-538/icorewebview2scriptdialogopeningeventhandler.md)
*   [<span data-ttu-id="fe943-159">ICoreWebView2SourceChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-159">ICoreWebView2SourceChangedEventHandler</span></span>](0-9-538/icorewebview2sourcechangedeventhandler.md)
*   [<span data-ttu-id="fe943-160">ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-160">ICoreWebView2WebMessageReceivedEventHandler</span></span>](0-9-538/icorewebview2webmessagereceivedeventhandler.md)
*   [<span data-ttu-id="fe943-161">ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-161">ICoreWebView2WebResourceRequestedEventHandler</span></span>](0-9-538/icorewebview2webresourcerequestedeventhandler.md)
*   [<span data-ttu-id="fe943-162">ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-162">ICoreWebView2WindowCloseRequestedEventHandler</span></span>](0-9-538/icorewebview2windowcloserequestedeventhandler.md)
*   [<span data-ttu-id="fe943-163">ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-163">ICoreWebView2ZoomFactorChangedEventHandler</span></span>](0-9-538/icorewebview2zoomfactorchangedeventhandler.md)

### <span data-ttu-id="fe943-164">試験的な</span><span class="sxs-lookup"><span data-stu-id="fe943-164">Experimental</span></span>

*   [<span data-ttu-id="fe943-165">ICoreWebView2Experimental</span><span class="sxs-lookup"><span data-stu-id="fe943-165">ICoreWebView2Experimental</span></span>](0-9-538/icorewebview2experimental.md)
*   [<span data-ttu-id="fe943-166">ICoreWebView2ExperimentalCompositionController</span><span class="sxs-lookup"><span data-stu-id="fe943-166">ICoreWebView2ExperimentalCompositionController</span></span>](0-9-538/icorewebview2experimentalcompositioncontroller.md)
*   [<span data-ttu-id="fe943-167">ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-167">ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span>](0-9-538/icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md)
*   [<span data-ttu-id="fe943-168">ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-168">ICoreWebView2ExperimentalCursorChangedEventHandler</span></span>](0-9-538/icorewebview2experimentalcursorchangedeventhandler.md)
*   [<span data-ttu-id="fe943-169">ICoreWebView2ExperimentalEnvironment</span><span class="sxs-lookup"><span data-stu-id="fe943-169">ICoreWebView2ExperimentalEnvironment</span></span>](0-9-538/icorewebview2experimentalenvironment.md)
*   [<span data-ttu-id="fe943-170">ICoreWebView2ExperimentalEnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="fe943-170">ICoreWebView2ExperimentalEnvironmentOptions</span></span>](0-9-538/icorewebview2experimentalenvironmentoptions.md)
*   [<span data-ttu-id="fe943-171">ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-171">ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span></span>](0-9-538/icorewebview2experimentalnewwindowrequestedeventargs.md)
*   [<span data-ttu-id="fe943-172">ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="fe943-172">ICoreWebView2ExperimentalPointerInfo</span></span>](0-9-538/icorewebview2experimentalpointerinfo.md)
*   [<span data-ttu-id="fe943-173">ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe943-173">ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs</span></span>](0-9-538/icorewebview2experimentalwebresourceresponsereceivedeventargs.md)
*   [<span data-ttu-id="fe943-174">ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-174">ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span></span>](0-9-538/icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md)
*   [<span data-ttu-id="fe943-175">ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fe943-175">ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler</span></span>](0-9-538/icorewebview2experimentalwebresourceresponsereceivedeventhandler.md)
*   [<span data-ttu-id="fe943-176">ICoreWebView2ExperimentalWindowFeatures</span><span class="sxs-lookup"><span data-stu-id="fe943-176">ICoreWebView2ExperimentalWindowFeatures</span></span>](0-9-538/icorewebview2experimentalwindowfeatures.md)
