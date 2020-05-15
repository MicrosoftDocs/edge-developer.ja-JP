---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリの Microsoft Edge WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 0dc99911323cb4fe90231ae0b90e2e93fc678a16
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654309"
---
# <span data-ttu-id="82239-104">Reference (WebView2)</span><span class="sxs-lookup"><span data-stu-id="82239-104">Reference (WebView2)</span></span>  

<span data-ttu-id="82239-105">Microsoft Edge WebView2 コントロールを使用すると、 [Microsoft edge \ (Chromium \)](https://www.microsoftedgeinsider.com)を使ってアプリケーションの web コンテンツをレンダリングエンジンとしてホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="82239-105">The Microsoft Edge WebView2 control enables you to host web content in your application using [Microsoft Edge \(Chromium\)](https://www.microsoftedgeinsider.com) as the rendering engine.</span></span>  <span data-ttu-id="82239-106">詳細については、「 [Microsoft Edge WebView2 の概要](../../index.md)」および「 [WebView2 の使用を開始](../../gettingstarted/win32.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82239-106">For more information, see [Overview of Microsoft Edge WebView2](../../index.md)) and [Getting Started with WebView2](../../gettingstarted/win32.md).</span></span>  <span data-ttu-id="82239-107">[WebView2](0-9-515/microsoft-web-webview2-core-corewebview2.md)は、API の詳細を理解するのに最適な場所です。 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="82239-107">[Microsoft.Web.WebView2.Core.CoreWebView2](0-9-515/microsoft-web-webview2-core-corewebview2.md) is a great place to start learning the details of the API.</span></span>  

## <span data-ttu-id="82239-108">WebView2 の基本</span><span class="sxs-lookup"><span data-stu-id="82239-108">Microsoft.Web.WebView2.Core</span></span>
*   <span data-ttu-id="82239-109">[WebView2 の](0-9-515/namespace-microsoft-web-webview2-core.md)名前空間</span><span class="sxs-lookup"><span data-stu-id="82239-109">[Microsoft.Web.WebView2.Core](0-9-515/namespace-microsoft-web-webview2-core.md) namespace</span></span>
*   [<span data-ttu-id="82239-110">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="82239-110">CoreWebView2</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2.md)
*   [<span data-ttu-id="82239-111">CoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="82239-111">CoreWebView2Controller</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2controller.md)
*   [<span data-ttu-id="82239-112">CoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="82239-112">CoreWebView2Deferral</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2deferral.md)
*   [<span data-ttu-id="82239-113">CoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="82239-113">CoreWebView2DevToolsProtocolEventReceiver</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceiver.md)
*   [<span data-ttu-id="82239-114">CoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="82239-114">CoreWebView2Environment</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2environment.md)
*   [<span data-ttu-id="82239-115">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="82239-115">CoreWebView2EnvironmentOptions</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2environmentoptions.md)
*   [<span data-ttu-id="82239-116">CoreWebView2PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="82239-116">CoreWebView2PhysicalKeyStatus</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2physicalkeystatus.md)
*   [<span data-ttu-id="82239-117">CoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="82239-117">CoreWebView2Settings</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2settings.md)
*   [<span data-ttu-id="82239-118">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="82239-118">EdgeNotFoundException</span></span>](0-9-515/microsoft-web-webview2-core-edgenotfoundexception.md)

### <span data-ttu-id="82239-119">イベント引数</span><span class="sxs-lookup"><span data-stu-id="82239-119">Event arguments</span></span>

*   [<span data-ttu-id="82239-120">CoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-120">CoreWebView2AcceleratorKeyPressedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md)
*   [<span data-ttu-id="82239-121">CoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-121">CoreWebView2ContentLoadingEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2contentloadingeventargs.md)
*   [<span data-ttu-id="82239-122">CoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-122">CoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)
*   [<span data-ttu-id="82239-123">CoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-123">CoreWebView2MoveFocusRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md)
*   [<span data-ttu-id="82239-124">CoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-124">CoreWebView2NavigationCompletedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)
*   [<span data-ttu-id="82239-125">CoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-125">CoreWebView2NavigationStartingEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)
*   [<span data-ttu-id="82239-126">CoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-126">CoreWebView2NewWindowRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md)
*   [<span data-ttu-id="82239-127">CoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-127">CoreWebView2PermissionRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md)
*   [<span data-ttu-id="82239-128">CoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-128">CoreWebView2ProcessFailedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2processfailedeventargs.md)
*   [<span data-ttu-id="82239-129">CoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-129">CoreWebView2ScriptDialogOpeningEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md)
*   [<span data-ttu-id="82239-130">CoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-130">CoreWebView2SourceChangedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md)
*   [<span data-ttu-id="82239-131">CoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-131">CoreWebView2WebMessageReceivedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md)
*   [<span data-ttu-id="82239-132">CoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="82239-132">CoreWebView2WebResourceRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md)
