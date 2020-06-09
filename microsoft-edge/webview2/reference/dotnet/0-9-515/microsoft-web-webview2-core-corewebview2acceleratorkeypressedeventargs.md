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
ms.openlocfilehash: b0df25ffe3b00267dfff15cd50d1d3db6a7e38bb
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698219"
---
# <span data-ttu-id="e93dc-104">WebView2 クラス (CoreWebView2AcceleratorKeyPressedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="e93dc-104">Microsoft.Web.WebView2.Core.CoreWebView2AcceleratorKeyPressedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="e93dc-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e93dc-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="e93dc-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e93dc-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="e93dc-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="e93dc-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e93dc-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e93dc-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e93dc-109">AcceleratorKeyPressed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e93dc-109">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="e93dc-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="e93dc-110">Summary</span></span>

 <span data-ttu-id="e93dc-111">Members</span><span class="sxs-lookup"><span data-stu-id="e93dc-111">Members</span></span>                        | <span data-ttu-id="e93dc-112">説明</span><span class="sxs-lookup"><span data-stu-id="e93dc-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e93dc-113">Handled</span><span class="sxs-lookup"><span data-stu-id="e93dc-113">Handled</span></span>](#handled) | <span data-ttu-id="e93dc-114">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e93dc-114">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="e93dc-115">KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="e93dc-115">KeyEventKind</span></span>](#keyeventkind) | <span data-ttu-id="e93dc-116">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="e93dc-116">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="e93dc-117">KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="e93dc-117">KeyEventLParam</span></span>](#keyeventlparam) | <span data-ttu-id="e93dc-118">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="e93dc-118">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="e93dc-119">PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="e93dc-119">PhysicalKeyStatus</span></span>](#physicalkeystatus) | <span data-ttu-id="e93dc-120">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="e93dc-120">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="e93dc-121">VirtualKey</span><span class="sxs-lookup"><span data-stu-id="e93dc-121">VirtualKey</span></span>](#virtualkey) | <span data-ttu-id="e93dc-122">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="e93dc-122">The Win32 virtual key code of the key that was pressed or released.</span></span>

## <span data-ttu-id="e93dc-123">Members</span><span class="sxs-lookup"><span data-stu-id="e93dc-123">Members</span></span>

#### <span data-ttu-id="e93dc-124">Handled</span><span class="sxs-lookup"><span data-stu-id="e93dc-124">Handled</span></span> 

<span data-ttu-id="e93dc-125">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e93dc-125">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="e93dc-126">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="e93dc-126">public bool [Handled](#handled)</span></span>

<span data-ttu-id="e93dc-127">Handled プロパティが TRUE に設定されている場合、この操作によって WebView はこのアクセラレータキーの既定のアクションを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e93dc-127">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="e93dc-128">それ以外の場合、WebView は、ショートカットキーの既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e93dc-128">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="e93dc-129">KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="e93dc-129">KeyEventKind</span></span> 

<span data-ttu-id="e93dc-130">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="e93dc-130">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="e93dc-131">パブリック[CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [keyeventkind](#keyeventkind)</span><span class="sxs-lookup"><span data-stu-id="e93dc-131">public [CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [KeyEventKind](#keyeventkind)</span></span>

#### <span data-ttu-id="e93dc-132">KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="e93dc-132">KeyEventLParam</span></span> 

<span data-ttu-id="e93dc-133">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="e93dc-133">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="e93dc-134">パブリック int [Keyeventlparam](#keyeventlparam)</span><span class="sxs-lookup"><span data-stu-id="e93dc-134">public int [KeyEventLParam](#keyeventlparam)</span></span>

<span data-ttu-id="e93dc-135">WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e93dc-135">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="e93dc-136">PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="e93dc-136">PhysicalKeyStatus</span></span> 

<span data-ttu-id="e93dc-137">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="e93dc-137">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="e93dc-138">パブリック[CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [physicalkeystatus](#physicalkeystatus)</span><span class="sxs-lookup"><span data-stu-id="e93dc-138">public [CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [PhysicalKeyStatus](#physicalkeystatus)</span></span>

#### <span data-ttu-id="e93dc-139">VirtualKey</span><span class="sxs-lookup"><span data-stu-id="e93dc-139">VirtualKey</span></span> 

<span data-ttu-id="e93dc-140">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="e93dc-140">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="e93dc-141">パブリック uint の[Virtualkey](#virtualkey)</span><span class="sxs-lookup"><span data-stu-id="e93dc-141">public uint [VirtualKey](#virtualkey)</span></span>

<span data-ttu-id="e93dc-142">これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="e93dc-142">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="e93dc-143">Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e93dc-143">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

