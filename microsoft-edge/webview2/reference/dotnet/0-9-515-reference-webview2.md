---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 の基本リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 32092f4b434506229ffdd3612a68725b67f566a8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879976"
---
# <span data-ttu-id="7e7b0-104">0-9-515 基準 (WebView2)</span><span class="sxs-lookup"><span data-stu-id="7e7b0-104">0-9-515 - Reference (WebView2)</span></span>  

> [!NOTE]
> <span data-ttu-id="7e7b0-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e7b0-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="7e7b0-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7b0-106">Please refer to [WebView2 API reference](../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="7e7b0-107">Microsoft Edge WebView2 コントロールを使用すると、 [Microsoft edge \ (Chromium \)](https://www.microsoftedgeinsider.com)を使ってアプリケーションの web コンテンツをレンダリングエンジンとしてホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="7e7b0-107">The Microsoft Edge WebView2 control enables you to host web content in your application using [Microsoft Edge \(Chromium\)](https://www.microsoftedgeinsider.com) as the rendering engine.</span></span>  <span data-ttu-id="7e7b0-108">詳細については、「 [Microsoft Edge WebView2 の概要](../../index.md)」および「 [WebView2 の使用を開始](../../gettingstarted/win32.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e7b0-108">For more information, see [Overview of Microsoft Edge WebView2](../../index.md)) and [Getting Started with WebView2](../../gettingstarted/win32.md).</span></span>  <span data-ttu-id="7e7b0-109">[WebView2](0-9-515/microsoft-web-webview2-core-corewebview2.md)は、API の詳細を理解するのに最適な場所です。 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="7e7b0-109">[Microsoft.Web.WebView2.Core.CoreWebView2](0-9-515/microsoft-web-webview2-core-corewebview2.md) is a great place to start learning the details of the API.</span></span>  

## <span data-ttu-id="7e7b0-110">WebView2 の基本</span><span class="sxs-lookup"><span data-stu-id="7e7b0-110">Microsoft.Web.WebView2.Core</span></span>
*   <span data-ttu-id="7e7b0-111">[WebView2 の](0-9-515/namespace-microsoft-web-webview2-core.md)名前空間</span><span class="sxs-lookup"><span data-stu-id="7e7b0-111">[Microsoft.Web.WebView2.Core](0-9-515/namespace-microsoft-web-webview2-core.md) namespace</span></span>
*   [<span data-ttu-id="7e7b0-112">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="7e7b0-112">CoreWebView2</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2.md)
*   [<span data-ttu-id="7e7b0-113">CoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="7e7b0-113">CoreWebView2Controller</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2controller.md)
*   [<span data-ttu-id="7e7b0-114">CoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="7e7b0-114">CoreWebView2Deferral</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2deferral.md)
*   [<span data-ttu-id="7e7b0-115">CoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="7e7b0-115">CoreWebView2DevToolsProtocolEventReceiver</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceiver.md)
*   [<span data-ttu-id="7e7b0-116">CoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="7e7b0-116">CoreWebView2Environment</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2environment.md)
*   [<span data-ttu-id="7e7b0-117">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="7e7b0-117">CoreWebView2EnvironmentOptions</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2environmentoptions.md)
*   [<span data-ttu-id="7e7b0-118">CoreWebView2PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="7e7b0-118">CoreWebView2PhysicalKeyStatus</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2physicalkeystatus.md)
*   [<span data-ttu-id="7e7b0-119">CoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="7e7b0-119">CoreWebView2Settings</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2settings.md)
*   [<span data-ttu-id="7e7b0-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="7e7b0-120">EdgeNotFoundException</span></span>](0-9-515/microsoft-web-webview2-core-edgenotfoundexception.md)

### <span data-ttu-id="7e7b0-121">イベント引数</span><span class="sxs-lookup"><span data-stu-id="7e7b0-121">Event arguments</span></span>

*   [<span data-ttu-id="7e7b0-122">CoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-122">CoreWebView2AcceleratorKeyPressedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md)
*   [<span data-ttu-id="7e7b0-123">CoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-123">CoreWebView2ContentLoadingEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2contentloadingeventargs.md)
*   [<span data-ttu-id="7e7b0-124">CoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-124">CoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)
*   [<span data-ttu-id="7e7b0-125">CoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-125">CoreWebView2MoveFocusRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md)
*   [<span data-ttu-id="7e7b0-126">CoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-126">CoreWebView2NavigationCompletedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)
*   [<span data-ttu-id="7e7b0-127">CoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-127">CoreWebView2NavigationStartingEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)
*   [<span data-ttu-id="7e7b0-128">CoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-128">CoreWebView2NewWindowRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md)
*   [<span data-ttu-id="7e7b0-129">CoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-129">CoreWebView2PermissionRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md)
*   [<span data-ttu-id="7e7b0-130">CoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-130">CoreWebView2ProcessFailedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2processfailedeventargs.md)
*   [<span data-ttu-id="7e7b0-131">CoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-131">CoreWebView2ScriptDialogOpeningEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md)
*   [<span data-ttu-id="7e7b0-132">CoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-132">CoreWebView2SourceChangedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md)
*   [<span data-ttu-id="7e7b0-133">CoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-133">CoreWebView2WebMessageReceivedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md)
*   [<span data-ttu-id="7e7b0-134">CoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e7b0-134">CoreWebView2WebResourceRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md)
