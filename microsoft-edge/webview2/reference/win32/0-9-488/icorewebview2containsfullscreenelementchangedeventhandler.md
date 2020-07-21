---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 41687dcb162d8d56e773b9050898e9f22bd034ab
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883883"
---
# <span data-ttu-id="d60e3-104">0.9.515-インターフェイス ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d60e3-104">0.9.515 - interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="d60e3-105">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d60e3-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="d60e3-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d60e3-106">Summary</span></span>

 <span data-ttu-id="d60e3-107">Members</span><span class="sxs-lookup"><span data-stu-id="d60e3-107">Members</span></span>                        | <span data-ttu-id="d60e3-108">説明</span><span class="sxs-lookup"><span data-stu-id="d60e3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d60e3-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="d60e3-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d60e3-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d60e3-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="d60e3-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="d60e3-111">There are no event args for this event.</span></span>

## <span data-ttu-id="d60e3-112">Members</span><span class="sxs-lookup"><span data-stu-id="d60e3-112">Members</span></span>

#### <span data-ttu-id="d60e3-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="d60e3-113">Invoke</span></span> 

<span data-ttu-id="d60e3-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d60e3-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d60e3-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="d60e3-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="d60e3-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="d60e3-116">There are no event args and the args parameter will be null.</span></span>

