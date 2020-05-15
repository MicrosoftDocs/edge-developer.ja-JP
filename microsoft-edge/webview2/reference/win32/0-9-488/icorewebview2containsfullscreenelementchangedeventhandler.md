---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 85de243c00364f7fb57d3842b2ddbf78848905f6
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654497"
---
# <span data-ttu-id="202e6-104">インターフェイス ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="202e6-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="202e6-105">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="202e6-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="202e6-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="202e6-106">Summary</span></span>

 <span data-ttu-id="202e6-107">Members</span><span class="sxs-lookup"><span data-stu-id="202e6-107">Members</span></span>                        | <span data-ttu-id="202e6-108">説明</span><span class="sxs-lookup"><span data-stu-id="202e6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="202e6-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="202e6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="202e6-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="202e6-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="202e6-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="202e6-111">There are no event args for this event.</span></span>

## <span data-ttu-id="202e6-112">Members</span><span class="sxs-lookup"><span data-stu-id="202e6-112">Members</span></span>

#### <span data-ttu-id="202e6-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="202e6-113">Invoke</span></span> 

<span data-ttu-id="202e6-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="202e6-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="202e6-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="202e6-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="202e6-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="202e6-116">There are no event args and the args parameter will be null.</span></span>

