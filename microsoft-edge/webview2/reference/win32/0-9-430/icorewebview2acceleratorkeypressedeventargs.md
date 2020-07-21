---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 280df2816696ce4abce118976b3eb9abf76267e3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884415"
---
# <span data-ttu-id="57f68-104">0.9.430-インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="57f68-104">0.9.430 - interface ICoreWebView2AcceleratorKeyPressedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="57f68-105">AcceleratorKeyPressed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="57f68-105">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="57f68-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="57f68-106">Summary</span></span>

 <span data-ttu-id="57f68-107">Members</span><span class="sxs-lookup"><span data-stu-id="57f68-107">Members</span></span>                        | <span data-ttu-id="57f68-108">説明</span><span class="sxs-lookup"><span data-stu-id="57f68-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="57f68-109">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="57f68-109">get_KeyEventKind</span></span>](#get_keyeventkind) | <span data-ttu-id="57f68-110">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="57f68-110">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="57f68-111">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="57f68-111">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="57f68-112">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="57f68-112">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="57f68-113">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="57f68-113">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="57f68-114">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="57f68-114">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="57f68-115">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="57f68-115">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="57f68-116">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="57f68-116">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="57f68-117">get_Handled</span><span class="sxs-lookup"><span data-stu-id="57f68-117">get_Handled</span></span>](#get_handled) | <span data-ttu-id="57f68-118">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="57f68-118">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="57f68-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="57f68-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="57f68-120">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="57f68-120">Sets the Handled property.</span></span>

## <span data-ttu-id="57f68-121">Members</span><span class="sxs-lookup"><span data-stu-id="57f68-121">Members</span></span>

#### <span data-ttu-id="57f68-122">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="57f68-122">get_KeyEventKind</span></span> 

<span data-ttu-id="57f68-123">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="57f68-123">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="57f68-124">パブリック HRESULT [get_KeyEventKind](#get_keyeventkind)(CORE_WEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span><span class="sxs-lookup"><span data-stu-id="57f68-124">public HRESULT [get_KeyEventKind](#get_keyeventkind)(CORE_WEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span></span>

#### <span data-ttu-id="57f68-125">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="57f68-125">get_VirtualKey</span></span> 

<span data-ttu-id="57f68-126">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="57f68-126">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="57f68-127">パブリック HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualkey)</span><span class="sxs-lookup"><span data-stu-id="57f68-127">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="57f68-128">これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="57f68-128">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="57f68-129">Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="57f68-129">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="57f68-130">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="57f68-130">get_KeyEventLParam</span></span> 

<span data-ttu-id="57f68-131">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="57f68-131">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="57f68-132">パブリック HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span><span class="sxs-lookup"><span data-stu-id="57f68-132">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="57f68-133">WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57f68-133">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="57f68-134">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="57f68-134">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="57f68-135">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="57f68-135">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="57f68-136">パブリック HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(CORE_WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span><span class="sxs-lookup"><span data-stu-id="57f68-136">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(CORE_WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="57f68-137">get_Handled</span><span class="sxs-lookup"><span data-stu-id="57f68-137">get_Handled</span></span> 

<span data-ttu-id="57f68-138">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="57f68-138">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="57f68-139">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="57f68-139">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

<span data-ttu-id="57f68-140">Handled プロパティが TRUE に設定されている場合、この操作によって WebView はこのアクセラレータキーの既定のアクションを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="57f68-140">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="57f68-141">それ以外の場合、WebView は、ショートカットキーの既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="57f68-141">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="57f68-142">put_Handled</span><span class="sxs-lookup"><span data-stu-id="57f68-142">put_Handled</span></span> 

<span data-ttu-id="57f68-143">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="57f68-143">Sets the Handled property.</span></span>

> <span data-ttu-id="57f68-144">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="57f68-144">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

