---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b3d6cc14ccaa6a803e0e987b68a74851a6c5f2f9
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699088"
---
# <span data-ttu-id="01e06-104">WebView2 クラス (CoreWebView2AcceleratorKeyPressedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="01e06-104">Microsoft.Web.WebView2.Core.CoreWebView2AcceleratorKeyPressedEventArgs class</span></span> 

<span data-ttu-id="01e06-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="01e06-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="01e06-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="01e06-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="01e06-107">AcceleratorKeyPressed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="01e06-107">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="01e06-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="01e06-108">Summary</span></span>

 <span data-ttu-id="01e06-109">Members</span><span class="sxs-lookup"><span data-stu-id="01e06-109">Members</span></span>                        | <span data-ttu-id="01e06-110">説明</span><span class="sxs-lookup"><span data-stu-id="01e06-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="01e06-111">Handled</span><span class="sxs-lookup"><span data-stu-id="01e06-111">Handled</span></span>](#handled) | <span data-ttu-id="01e06-112">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="01e06-112">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="01e06-113">KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="01e06-113">KeyEventKind</span></span>](#keyeventkind) | <span data-ttu-id="01e06-114">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="01e06-114">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="01e06-115">KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="01e06-115">KeyEventLParam</span></span>](#keyeventlparam) | <span data-ttu-id="01e06-116">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="01e06-116">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="01e06-117">PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="01e06-117">PhysicalKeyStatus</span></span>](#physicalkeystatus) | <span data-ttu-id="01e06-118">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="01e06-118">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="01e06-119">VirtualKey</span><span class="sxs-lookup"><span data-stu-id="01e06-119">VirtualKey</span></span>](#virtualkey) | <span data-ttu-id="01e06-120">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="01e06-120">The Win32 virtual key code of the key that was pressed or released.</span></span>

## <span data-ttu-id="01e06-121">Members</span><span class="sxs-lookup"><span data-stu-id="01e06-121">Members</span></span>

#### <span data-ttu-id="01e06-122">Handled</span><span class="sxs-lookup"><span data-stu-id="01e06-122">Handled</span></span> 

<span data-ttu-id="01e06-123">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="01e06-123">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="01e06-124">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="01e06-124">public bool [Handled](#handled)</span></span>

<span data-ttu-id="01e06-125">Handled プロパティが TRUE に設定されている場合、この操作によって WebView はこのアクセラレータキーの既定のアクションを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="01e06-125">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="01e06-126">それ以外の場合、WebView は、ショートカットキーの既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="01e06-126">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="01e06-127">KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="01e06-127">KeyEventKind</span></span> 

<span data-ttu-id="01e06-128">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="01e06-128">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="01e06-129">パブリック[CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [keyeventkind](#keyeventkind)</span><span class="sxs-lookup"><span data-stu-id="01e06-129">public [CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [KeyEventKind](#keyeventkind)</span></span>

#### <span data-ttu-id="01e06-130">KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="01e06-130">KeyEventLParam</span></span> 

<span data-ttu-id="01e06-131">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="01e06-131">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="01e06-132">パブリック int [Keyeventlparam](#keyeventlparam)</span><span class="sxs-lookup"><span data-stu-id="01e06-132">public int [KeyEventLParam](#keyeventlparam)</span></span>

<span data-ttu-id="01e06-133">WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01e06-133">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="01e06-134">PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="01e06-134">PhysicalKeyStatus</span></span> 

<span data-ttu-id="01e06-135">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="01e06-135">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="01e06-136">パブリック[CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [physicalkeystatus](#physicalkeystatus)</span><span class="sxs-lookup"><span data-stu-id="01e06-136">public [CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [PhysicalKeyStatus](#physicalkeystatus)</span></span>

#### <span data-ttu-id="01e06-137">VirtualKey</span><span class="sxs-lookup"><span data-stu-id="01e06-137">VirtualKey</span></span> 

<span data-ttu-id="01e06-138">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="01e06-138">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="01e06-139">パブリック uint の[Virtualkey](#virtualkey)</span><span class="sxs-lookup"><span data-stu-id="01e06-139">public uint [VirtualKey](#virtualkey)</span></span>

<span data-ttu-id="01e06-140">これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="01e06-140">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="01e06-141">Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="01e06-141">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

