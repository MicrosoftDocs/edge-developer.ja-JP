---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 885ad6b161fbde6721e1812735ab50d7e0c3e8d9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885053"
---
# <span data-ttu-id="802a1-104">0.8.355-インターフェイス IWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="802a1-104">0.8.355 - interface IWebView2AcceleratorKeyPressedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="802a1-105">AcceleratorKeyPressed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="802a1-105">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="802a1-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="802a1-106">Summary</span></span>

 <span data-ttu-id="802a1-107">Members</span><span class="sxs-lookup"><span data-stu-id="802a1-107">Members</span></span>                        | <span data-ttu-id="802a1-108">説明</span><span class="sxs-lookup"><span data-stu-id="802a1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="802a1-109">get_KeyEventType</span><span class="sxs-lookup"><span data-stu-id="802a1-109">get_KeyEventType</span></span>](#get_keyeventtype) | <span data-ttu-id="802a1-110">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="802a1-110">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="802a1-111">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="802a1-111">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="802a1-112">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="802a1-112">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="802a1-113">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="802a1-113">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="802a1-114">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="802a1-114">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="802a1-115">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="802a1-115">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="802a1-116">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="802a1-116">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="802a1-117">ハンドル</span><span class="sxs-lookup"><span data-stu-id="802a1-117">Handle</span></span>](#handle) | <span data-ttu-id="802a1-118">これにより、ブラウザプロセスが続行されます。</span><span class="sxs-lookup"><span data-stu-id="802a1-118">Calling this will allow the browser process to continue.</span></span>

## <span data-ttu-id="802a1-119">Members</span><span class="sxs-lookup"><span data-stu-id="802a1-119">Members</span></span>

#### <span data-ttu-id="802a1-120">get_KeyEventType</span><span class="sxs-lookup"><span data-stu-id="802a1-120">get_KeyEventType</span></span> 

<span data-ttu-id="802a1-121">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="802a1-121">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="802a1-122">パブリック HRESULT [get_KeyEventType](#get_keyeventtype)(WEBVIEW2_KEY_EVENT_TYPE \* keyeventtype)</span><span class="sxs-lookup"><span data-stu-id="802a1-122">public HRESULT [get_KeyEventType](#get_keyeventtype)(WEBVIEW2_KEY_EVENT_TYPE \* keyEventType)</span></span>

<span data-ttu-id="802a1-123">これは、WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN、WEBVIEW2_KEY_EVENT_TYPE_KEY_UP、WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN、または WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="802a1-123">This is one of WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN, WEBVIEW2_KEY_EVENT_TYPE_KEY_UP, WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN, or WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP.</span></span>

#### <span data-ttu-id="802a1-124">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="802a1-124">get_VirtualKey</span></span> 

<span data-ttu-id="802a1-125">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="802a1-125">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="802a1-126">パブリック HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualkey)</span><span class="sxs-lookup"><span data-stu-id="802a1-126">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="802a1-127">これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="802a1-127">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="802a1-128">Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="802a1-128">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="802a1-129">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="802a1-129">get_KeyEventLParam</span></span> 

<span data-ttu-id="802a1-130">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="802a1-130">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="802a1-131">パブリック HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span><span class="sxs-lookup"><span data-stu-id="802a1-131">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="802a1-132">WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="802a1-132">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="802a1-133">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="802a1-133">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="802a1-134">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="802a1-134">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="802a1-135">パブリック HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span><span class="sxs-lookup"><span data-stu-id="802a1-135">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="802a1-136">ハンドル</span><span class="sxs-lookup"><span data-stu-id="802a1-136">Handle</span></span> 

<span data-ttu-id="802a1-137">これにより、ブラウザプロセスが続行されます。</span><span class="sxs-lookup"><span data-stu-id="802a1-137">Calling this will allow the browser process to continue.</span></span>

> <span data-ttu-id="802a1-138">パブリック HRESULT[ハンドル](#handle)(BOOL handled)</span><span class="sxs-lookup"><span data-stu-id="802a1-138">public HRESULT [Handle](#handle)(BOOL handled)</span></span>

<span data-ttu-id="802a1-139">TRUE を渡すと、ブラウザーはこのショートカットキーの既定の操作を実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="802a1-139">Passing TRUE will prevent the browser from performing the default action for this accelerator key.</span></span> <span data-ttu-id="802a1-140">イベントハンドラーが呼び出し[ハンドル ()](#handle)を使わずに返された場合は、ハンドル (FALSE) の呼び出しと同じです。</span><span class="sxs-lookup"><span data-stu-id="802a1-140">If the event handler returns without calling [Handle()](#handle), it is equivalent to calling Handle(FALSE).</span></span> <span data-ttu-id="802a1-141">呼び出し[ハンドル ()](#handle)は、既に呼び出されているか、イベントハンドラーから返された場合は何もしません。</span><span class="sxs-lookup"><span data-stu-id="802a1-141">Calling [Handle()](#handle) after it has already been called or the event handler has returned will do nothing.</span></span>

