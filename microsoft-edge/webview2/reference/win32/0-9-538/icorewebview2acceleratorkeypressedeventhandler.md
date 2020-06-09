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
ms.openlocfilehash: 05dd401064635a6b20f1936b1efaac025b45749f
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699028"
---
# <span data-ttu-id="4c5d5-104">インターフェイス ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="4c5d5-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="4c5d5-105">呼び出し元は、このインターフェイスを実装して AcceleratorKeyPressed イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4c5d5-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="4c5d5-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4c5d5-106">Summary</span></span>

 <span data-ttu-id="4c5d5-107">Members</span><span class="sxs-lookup"><span data-stu-id="4c5d5-107">Members</span></span>                        | <span data-ttu-id="4c5d5-108">説明</span><span class="sxs-lookup"><span data-stu-id="4c5d5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4c5d5-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="4c5d5-109">Invoke</span></span>](#invoke) | <span data-ttu-id="4c5d5-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4c5d5-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="4c5d5-111">Members</span><span class="sxs-lookup"><span data-stu-id="4c5d5-111">Members</span></span>

#### <span data-ttu-id="4c5d5-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="4c5d5-112">Invoke</span></span> 

<span data-ttu-id="4c5d5-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4c5d5-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="4c5d5-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="4c5d5-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

