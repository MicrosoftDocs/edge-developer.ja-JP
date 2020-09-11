---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ContainsFullScreenElementChangedEventHandler
ms.openlocfilehash: e1c51ee30a7b61d5a5638adb4130b1add3bddb23
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010559"
---
# <span data-ttu-id="9879b-104">0.9.579-インターフェイス ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="9879b-104">0.9.579 - interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="9879b-105">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9879b-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="9879b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="9879b-106">Summary</span></span>

 <span data-ttu-id="9879b-107">Members</span><span class="sxs-lookup"><span data-stu-id="9879b-107">Members</span></span>                        | <span data-ttu-id="9879b-108">説明</span><span class="sxs-lookup"><span data-stu-id="9879b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9879b-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="9879b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="9879b-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9879b-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="9879b-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="9879b-111">There are no event args for this event.</span></span>

## <span data-ttu-id="9879b-112">Members</span><span class="sxs-lookup"><span data-stu-id="9879b-112">Members</span></span>

#### <span data-ttu-id="9879b-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="9879b-113">Invoke</span></span> 

<span data-ttu-id="9879b-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9879b-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="9879b-115">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="9879b-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="9879b-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="9879b-116">There are no event args and the args parameter will be null.</span></span>

