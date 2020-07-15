---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 5d052488d23f3d016ba2fd71eb929d5aa2ebea6e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877365"
---
# <span data-ttu-id="8da8b-104">0.8.355-インターフェイス IWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="8da8b-104">0.8.355 - interface IWebView2AcceleratorKeyPressedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="8da8b-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8da8b-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="8da8b-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8da8b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="8da8b-107">AcceleratorKeyPressed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="8da8b-107">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="8da8b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8da8b-108">Summary</span></span>

 <span data-ttu-id="8da8b-109">Members</span><span class="sxs-lookup"><span data-stu-id="8da8b-109">Members</span></span>                        | <span data-ttu-id="8da8b-110">説明</span><span class="sxs-lookup"><span data-stu-id="8da8b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8da8b-111">get_KeyEventType</span><span class="sxs-lookup"><span data-stu-id="8da8b-111">get_KeyEventType</span></span>](#get_keyeventtype) | <span data-ttu-id="8da8b-112">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="8da8b-112">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="8da8b-113">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="8da8b-113">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="8da8b-114">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="8da8b-114">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="8da8b-115">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="8da8b-115">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="8da8b-116">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="8da8b-116">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="8da8b-117">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="8da8b-117">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="8da8b-118">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="8da8b-118">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="8da8b-119">ハンドル</span><span class="sxs-lookup"><span data-stu-id="8da8b-119">Handle</span></span>](#handle) | <span data-ttu-id="8da8b-120">これにより、ブラウザプロセスが続行されます。</span><span class="sxs-lookup"><span data-stu-id="8da8b-120">Calling this will allow the browser process to continue.</span></span>

## <span data-ttu-id="8da8b-121">Members</span><span class="sxs-lookup"><span data-stu-id="8da8b-121">Members</span></span>

#### <span data-ttu-id="8da8b-122">get_KeyEventType</span><span class="sxs-lookup"><span data-stu-id="8da8b-122">get_KeyEventType</span></span> 

<span data-ttu-id="8da8b-123">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="8da8b-123">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="8da8b-124">パブリック HRESULT [get_KeyEventType](#get_keyeventtype)(WEBVIEW2_KEY_EVENT_TYPE \* keyeventtype)</span><span class="sxs-lookup"><span data-stu-id="8da8b-124">public HRESULT [get_KeyEventType](#get_keyeventtype)(WEBVIEW2_KEY_EVENT_TYPE \* keyEventType)</span></span>

<span data-ttu-id="8da8b-125">これは、WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN、WEBVIEW2_KEY_EVENT_TYPE_KEY_UP、WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN、または WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8da8b-125">This is one of WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN, WEBVIEW2_KEY_EVENT_TYPE_KEY_UP, WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN, or WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP.</span></span>

#### <span data-ttu-id="8da8b-126">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="8da8b-126">get_VirtualKey</span></span> 

<span data-ttu-id="8da8b-127">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="8da8b-127">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="8da8b-128">パブリック HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualkey)</span><span class="sxs-lookup"><span data-stu-id="8da8b-128">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="8da8b-129">これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="8da8b-129">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="8da8b-130">Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8da8b-130">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="8da8b-131">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="8da8b-131">get_KeyEventLParam</span></span> 

<span data-ttu-id="8da8b-132">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="8da8b-132">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="8da8b-133">パブリック HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span><span class="sxs-lookup"><span data-stu-id="8da8b-133">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="8da8b-134">WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8da8b-134">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="8da8b-135">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="8da8b-135">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="8da8b-136">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="8da8b-136">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="8da8b-137">パブリック HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span><span class="sxs-lookup"><span data-stu-id="8da8b-137">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="8da8b-138">ハンドル</span><span class="sxs-lookup"><span data-stu-id="8da8b-138">Handle</span></span> 

<span data-ttu-id="8da8b-139">これにより、ブラウザプロセスが続行されます。</span><span class="sxs-lookup"><span data-stu-id="8da8b-139">Calling this will allow the browser process to continue.</span></span>

> <span data-ttu-id="8da8b-140">パブリック HRESULT[ハンドル](#handle)(BOOL handled)</span><span class="sxs-lookup"><span data-stu-id="8da8b-140">public HRESULT [Handle](#handle)(BOOL handled)</span></span>

<span data-ttu-id="8da8b-141">TRUE を渡すと、ブラウザーはこのショートカットキーの既定の操作を実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8da8b-141">Passing TRUE will prevent the browser from performing the default action for this accelerator key.</span></span> <span data-ttu-id="8da8b-142">イベントハンドラーが呼び出し[ハンドル ()](#handle)を使わずに返された場合は、ハンドル (FALSE) の呼び出しと同じです。</span><span class="sxs-lookup"><span data-stu-id="8da8b-142">If the event handler returns without calling [Handle()](#handle), it is equivalent to calling Handle(FALSE).</span></span> <span data-ttu-id="8da8b-143">呼び出し[ハンドル ()](#handle)は、既に呼び出されているか、イベントハンドラーから返された場合は何もしません。</span><span class="sxs-lookup"><span data-stu-id="8da8b-143">Calling [Handle()](#handle) after it has already been called or the event handler has returned will do nothing.</span></span>

