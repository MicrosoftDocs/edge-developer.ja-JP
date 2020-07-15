---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2AcceleratorKeyPressedEventHandler
ms.openlocfilehash: 26bbc2a5c55ebe5a9b7519a87b01c4dd17af375c
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879563"
---
# <span data-ttu-id="09996-104">インターフェイス ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="09996-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="09996-105">呼び出し元は、このインターフェイスを実装して AcceleratorKeyPressed イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="09996-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="09996-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="09996-106">Summary</span></span>

 <span data-ttu-id="09996-107">Members</span><span class="sxs-lookup"><span data-stu-id="09996-107">Members</span></span>                        | <span data-ttu-id="09996-108">説明</span><span class="sxs-lookup"><span data-stu-id="09996-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="09996-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="09996-109">Invoke</span></span>](#invoke) | <span data-ttu-id="09996-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="09996-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="09996-111">Members</span><span class="sxs-lookup"><span data-stu-id="09996-111">Members</span></span>

#### <span data-ttu-id="09996-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="09996-112">Invoke</span></span> 

<span data-ttu-id="09996-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="09996-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="09996-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="09996-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

