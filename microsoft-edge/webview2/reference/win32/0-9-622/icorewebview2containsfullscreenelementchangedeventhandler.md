---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ContainsFullScreenElementChangedEventHandler
ms.openlocfilehash: 0477f9868dc472cab71dad4b10ff85fa034515a1
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012386"
---
# <span data-ttu-id="5513a-104">インターフェイス ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="5513a-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="5513a-105">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5513a-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="5513a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="5513a-106">Summary</span></span>

 <span data-ttu-id="5513a-107">Members</span><span class="sxs-lookup"><span data-stu-id="5513a-107">Members</span></span>                        | <span data-ttu-id="5513a-108">説明</span><span class="sxs-lookup"><span data-stu-id="5513a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5513a-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="5513a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="5513a-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5513a-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="5513a-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="5513a-111">There are no event args for this event.</span></span>

## <span data-ttu-id="5513a-112">Members</span><span class="sxs-lookup"><span data-stu-id="5513a-112">Members</span></span>

#### <span data-ttu-id="5513a-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="5513a-113">Invoke</span></span> 

<span data-ttu-id="5513a-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5513a-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="5513a-115">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="5513a-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="5513a-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="5513a-116">There are no event args and the args parameter will be null.</span></span>

