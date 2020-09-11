---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WindowCloseRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WindowCloseRequestedEventHandler
ms.openlocfilehash: f5c1799225df5460029b3ad0c40db63a2e16113c
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012199"
---
# <span data-ttu-id="daf07-104">インターフェイス ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="daf07-104">interface ICoreWebView2WindowCloseRequestedEventHandler</span></span> 

```
interface ICoreWebView2WindowCloseRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="daf07-105">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="daf07-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="daf07-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="daf07-106">Summary</span></span>

 <span data-ttu-id="daf07-107">Members</span><span class="sxs-lookup"><span data-stu-id="daf07-107">Members</span></span>                        | <span data-ttu-id="daf07-108">説明</span><span class="sxs-lookup"><span data-stu-id="daf07-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="daf07-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="daf07-109">Invoke</span></span>](#invoke) | <span data-ttu-id="daf07-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="daf07-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="daf07-111">Members</span><span class="sxs-lookup"><span data-stu-id="daf07-111">Members</span></span>

#### <span data-ttu-id="daf07-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="daf07-112">Invoke</span></span> 

<span data-ttu-id="daf07-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="daf07-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="daf07-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="daf07-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="daf07-115">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="daf07-115">There are no event args and the args parameter will be null.</span></span>

