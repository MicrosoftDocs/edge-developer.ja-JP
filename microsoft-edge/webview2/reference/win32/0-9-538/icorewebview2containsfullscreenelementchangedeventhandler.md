---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ContainsFullScreenElementChangedEventHandler
ms.openlocfilehash: 0f0efc8cc5315c35bef4c0ad122be37f26444f8d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877428"
---
# <span data-ttu-id="5a5d4-104">インターフェイス ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="5a5d4-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="5a5d4-105">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a5d4-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="5a5d4-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="5a5d4-106">Summary</span></span>

 <span data-ttu-id="5a5d4-107">Members</span><span class="sxs-lookup"><span data-stu-id="5a5d4-107">Members</span></span>                        | <span data-ttu-id="5a5d4-108">説明</span><span class="sxs-lookup"><span data-stu-id="5a5d4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5a5d4-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="5a5d4-109">Invoke</span></span>](#invoke) | <span data-ttu-id="5a5d4-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5a5d4-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="5a5d4-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="5a5d4-111">There are no event args for this event.</span></span>

## <span data-ttu-id="5a5d4-112">Members</span><span class="sxs-lookup"><span data-stu-id="5a5d4-112">Members</span></span>

#### <span data-ttu-id="5a5d4-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="5a5d4-113">Invoke</span></span> 

<span data-ttu-id="5a5d4-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5a5d4-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="5a5d4-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="5a5d4-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="5a5d4-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="5a5d4-116">There are no event args and the args parameter will be null.</span></span>

