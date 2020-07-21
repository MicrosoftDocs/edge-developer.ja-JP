---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: b1d0bf7ea5f472d5a1c3682c2cbef564947ee54b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886186"
---
# <span data-ttu-id="845c1-104">0.8.355-インターフェイス IWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="845c1-104">0.8.355 - interface IWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="845c1-105">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="845c1-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="845c1-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="845c1-106">Summary</span></span>

 <span data-ttu-id="845c1-107">Members</span><span class="sxs-lookup"><span data-stu-id="845c1-107">Members</span></span>                        | <span data-ttu-id="845c1-108">説明</span><span class="sxs-lookup"><span data-stu-id="845c1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="845c1-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="845c1-109">Invoke</span></span>](#invoke) | <span data-ttu-id="845c1-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="845c1-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="845c1-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="845c1-111">There are no event args for this event.</span></span>

## <span data-ttu-id="845c1-112">Members</span><span class="sxs-lookup"><span data-stu-id="845c1-112">Members</span></span>

#### <span data-ttu-id="845c1-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="845c1-113">Invoke</span></span> 

<span data-ttu-id="845c1-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="845c1-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="845c1-115">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView5](IWebView2WebView5.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="845c1-115">public HRESULT [Invoke](#invoke)([IWebView2WebView5](IWebView2WebView5.md) \* webview,IUnknown \* args)</span></span>

<span data-ttu-id="845c1-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="845c1-116">There are no event args and the args parameter will be null.</span></span>

