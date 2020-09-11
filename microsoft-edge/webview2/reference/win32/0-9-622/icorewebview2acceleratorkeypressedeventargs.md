---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2AcceleratorKeyPressedEventArgs
ms.openlocfilehash: 7491756d5cc549f805f4f8003ac450cdc6c40b96
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012202"
---
# <span data-ttu-id="3e8a9-104">インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="3e8a9-104">interface ICoreWebView2AcceleratorKeyPressedEventArgs</span></span> 

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="3e8a9-105">AcceleratorKeyPressed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-105">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="3e8a9-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3e8a9-106">Summary</span></span>

 <span data-ttu-id="3e8a9-107">Members</span><span class="sxs-lookup"><span data-stu-id="3e8a9-107">Members</span></span>                        | <span data-ttu-id="3e8a9-108">説明</span><span class="sxs-lookup"><span data-stu-id="3e8a9-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3e8a9-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="3e8a9-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="3e8a9-110">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-110">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="3e8a9-111">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="3e8a9-111">get_KeyEventKind</span></span>](#get_keyeventkind) | <span data-ttu-id="3e8a9-112">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-112">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="3e8a9-113">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="3e8a9-113">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="3e8a9-114">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-114">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="3e8a9-115">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="3e8a9-115">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="3e8a9-116">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-116">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="3e8a9-117">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="3e8a9-117">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="3e8a9-118">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-118">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="3e8a9-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="3e8a9-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="3e8a9-120">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-120">Sets the Handled property.</span></span>

## <span data-ttu-id="3e8a9-121">Members</span><span class="sxs-lookup"><span data-stu-id="3e8a9-121">Members</span></span>

#### <span data-ttu-id="3e8a9-122">get_Handled</span><span class="sxs-lookup"><span data-stu-id="3e8a9-122">get_Handled</span></span> 

<span data-ttu-id="3e8a9-123">AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-123">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="3e8a9-124">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="3e8a9-124">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

<span data-ttu-id="3e8a9-125">Handled プロパティが TRUE に設定されている場合、この操作によって WebView はこのアクセラレータキーの既定のアクションを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-125">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="3e8a9-126">それ以外の場合、WebView は、ショートカットキーの既定のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-126">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="3e8a9-127">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="3e8a9-127">get_KeyEventKind</span></span> 

<span data-ttu-id="3e8a9-128">イベントを発生させる原因となったキーイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-128">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="3e8a9-129">パブリック HRESULT [get_KeyEventKind](#get_keyeventkind)(COREWEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span><span class="sxs-lookup"><span data-stu-id="3e8a9-129">public HRESULT [get_KeyEventKind](#get_keyeventkind)(COREWEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span></span>

#### <span data-ttu-id="3e8a9-130">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="3e8a9-130">get_KeyEventLParam</span></span> 

<span data-ttu-id="3e8a9-131">ウィンドウメッセージと共に送信された LPARAM の値。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-131">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="3e8a9-132">パブリック HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span><span class="sxs-lookup"><span data-stu-id="3e8a9-132">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="3e8a9-133">WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-133">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="3e8a9-134">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="3e8a9-134">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="3e8a9-135">ウィンドウメッセージの LPARAM で渡された情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-135">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="3e8a9-136">パブリック HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(COREWEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span><span class="sxs-lookup"><span data-stu-id="3e8a9-136">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(COREWEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="3e8a9-137">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="3e8a9-137">get_VirtualKey</span></span> 

<span data-ttu-id="3e8a9-138">押されたキーまたは離されたキーの Win32 仮想キーコード。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-138">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="3e8a9-139">パブリック HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualkey)</span><span class="sxs-lookup"><span data-stu-id="3e8a9-139">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="3e8a9-140">これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-140">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="3e8a9-141">Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-141">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="3e8a9-142">put_Handled</span><span class="sxs-lookup"><span data-stu-id="3e8a9-142">put_Handled</span></span> 

<span data-ttu-id="3e8a9-143">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e8a9-143">Sets the Handled property.</span></span>

> <span data-ttu-id="3e8a9-144">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="3e8a9-144">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>
