---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 25d11995dd305a1958d6252c2ddf3afdb313fad1
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697183"
---
# <span data-ttu-id="64642-104">インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="64642-104">interface ICoreWebView2AcceleratorKeyPressedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="64642-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64642-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="64642-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64642-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="64642-107">AcceleratorKeyPressed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="64642-107">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="64642-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="64642-108">Summary</span></span>

 <span data-ttu-id="64642-109">Members</span><span class="sxs-lookup"><span data-stu-id="64642-109">Members</span></span>                        | <span data-ttu-id="64642-110">説明</span><span class="sxs-lookup"><span data-stu-id="64642-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="64642-111">get_Handled</span><span class="sxs-lookup"><span data-stu-id="64642-111">get_Handled</span></span>](#get_handled) | <span data-ttu-id="64642-112">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="64642-112">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="64642-113">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="64642-113">get_KeyEventKind</span></span>](#get_keyeventkind) | <span data-ttu-id="64642-114">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="64642-114">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="64642-115">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="64642-115">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="64642-116">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="64642-116">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="64642-117">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="64642-117">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="64642-118">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="64642-118">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="64642-119">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="64642-119">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="64642-120">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="64642-120">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="64642-121">put_Handled</span><span class="sxs-lookup"><span data-stu-id="64642-121">put_Handled</span></span>](#put_handled) | <span data-ttu-id="64642-122">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="64642-122">Sets the Handled property.</span></span>

## <span data-ttu-id="64642-123">Members</span><span class="sxs-lookup"><span data-stu-id="64642-123">Members</span></span>

#### <span data-ttu-id="64642-124">get_Handled</span><span class="sxs-lookup"><span data-stu-id="64642-124">get_Handled</span></span> 

<span data-ttu-id="64642-125">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="64642-125">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="64642-126">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="64642-126">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

<span data-ttu-id="64642-127">Handled プロパティが TRUE に設定されている場合、この操作によって WebView はこのアクセラレータキーの既定のアクションを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="64642-127">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="64642-128">それ以外の場合、WebView は、ショートカットキーの既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="64642-128">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="64642-129">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="64642-129">get_KeyEventKind</span></span> 

<span data-ttu-id="64642-130">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="64642-130">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="64642-131">パブリック HRESULT [get_KeyEventKind](#get_keyeventkind)(COREWEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span><span class="sxs-lookup"><span data-stu-id="64642-131">public HRESULT [get_KeyEventKind](#get_keyeventkind)(COREWEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span></span>

#### <span data-ttu-id="64642-132">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="64642-132">get_KeyEventLParam</span></span> 

<span data-ttu-id="64642-133">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="64642-133">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="64642-134">パブリック HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span><span class="sxs-lookup"><span data-stu-id="64642-134">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="64642-135">WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64642-135">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="64642-136">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="64642-136">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="64642-137">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="64642-137">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="64642-138">パブリック HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(COREWEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span><span class="sxs-lookup"><span data-stu-id="64642-138">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(COREWEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="64642-139">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="64642-139">get_VirtualKey</span></span> 

<span data-ttu-id="64642-140">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="64642-140">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="64642-141">パブリック HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualkey)</span><span class="sxs-lookup"><span data-stu-id="64642-141">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="64642-142">これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="64642-142">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="64642-143">Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="64642-143">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="64642-144">put_Handled</span><span class="sxs-lookup"><span data-stu-id="64642-144">put_Handled</span></span> 

<span data-ttu-id="64642-145">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="64642-145">Sets the Handled property.</span></span>

> <span data-ttu-id="64642-146">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="64642-146">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

