---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: e7a512201c1ef7917a54b93dbd06587294e76f78
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881180"
---
# <span data-ttu-id="e3035-104">0.9.430-インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e3035-104">0.9.430 - interface ICoreWebView2AcceleratorKeyPressedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="e3035-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3035-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="e3035-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3035-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="e3035-107">AcceleratorKeyPressed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e3035-107">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="e3035-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="e3035-108">Summary</span></span>

 <span data-ttu-id="e3035-109">Members</span><span class="sxs-lookup"><span data-stu-id="e3035-109">Members</span></span>                        | <span data-ttu-id="e3035-110">説明</span><span class="sxs-lookup"><span data-stu-id="e3035-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e3035-111">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="e3035-111">get_KeyEventKind</span></span>](#get_keyeventkind) | <span data-ttu-id="e3035-112">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="e3035-112">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="e3035-113">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="e3035-113">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="e3035-114">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="e3035-114">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="e3035-115">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="e3035-115">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="e3035-116">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="e3035-116">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="e3035-117">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="e3035-117">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="e3035-118">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="e3035-118">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="e3035-119">get_Handled</span><span class="sxs-lookup"><span data-stu-id="e3035-119">get_Handled</span></span>](#get_handled) | <span data-ttu-id="e3035-120">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e3035-120">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="e3035-121">put_Handled</span><span class="sxs-lookup"><span data-stu-id="e3035-121">put_Handled</span></span>](#put_handled) | <span data-ttu-id="e3035-122">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e3035-122">Sets the Handled property.</span></span>

## <span data-ttu-id="e3035-123">Members</span><span class="sxs-lookup"><span data-stu-id="e3035-123">Members</span></span>

#### <span data-ttu-id="e3035-124">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="e3035-124">get_KeyEventKind</span></span> 

<span data-ttu-id="e3035-125">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="e3035-125">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="e3035-126">パブリック HRESULT [get_KeyEventKind](#get_keyeventkind)(CORE_WEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span><span class="sxs-lookup"><span data-stu-id="e3035-126">public HRESULT [get_KeyEventKind](#get_keyeventkind)(CORE_WEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span></span>

#### <span data-ttu-id="e3035-127">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="e3035-127">get_VirtualKey</span></span> 

<span data-ttu-id="e3035-128">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="e3035-128">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="e3035-129">パブリック HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualkey)</span><span class="sxs-lookup"><span data-stu-id="e3035-129">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="e3035-130">これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="e3035-130">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="e3035-131">Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e3035-131">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="e3035-132">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="e3035-132">get_KeyEventLParam</span></span> 

<span data-ttu-id="e3035-133">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="e3035-133">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="e3035-134">パブリック HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span><span class="sxs-lookup"><span data-stu-id="e3035-134">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="e3035-135">WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3035-135">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="e3035-136">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="e3035-136">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="e3035-137">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="e3035-137">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="e3035-138">パブリック HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(CORE_WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span><span class="sxs-lookup"><span data-stu-id="e3035-138">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(CORE_WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="e3035-139">get_Handled</span><span class="sxs-lookup"><span data-stu-id="e3035-139">get_Handled</span></span> 

<span data-ttu-id="e3035-140">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e3035-140">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="e3035-141">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="e3035-141">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

<span data-ttu-id="e3035-142">Handled プロパティが TRUE に設定されている場合、この操作によって WebView はこのアクセラレータキーの既定のアクションを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e3035-142">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="e3035-143">それ以外の場合、WebView は、ショートカットキーの既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3035-143">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="e3035-144">put_Handled</span><span class="sxs-lookup"><span data-stu-id="e3035-144">put_Handled</span></span> 

<span data-ttu-id="e3035-145">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e3035-145">Sets the Handled property.</span></span>

> <span data-ttu-id="e3035-146">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="e3035-146">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

