---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WindowCloseRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9163eb811e018e346f610dae71d5fdb7e39de186
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885437"
---
# <span data-ttu-id="dc377-104">0.9.515-インターフェイス ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="dc377-104">0.9.515 - interface ICoreWebView2WindowCloseRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WindowCloseRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="dc377-105">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="dc377-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="dc377-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="dc377-106">Summary</span></span>

 <span data-ttu-id="dc377-107">Members</span><span class="sxs-lookup"><span data-stu-id="dc377-107">Members</span></span>                        | <span data-ttu-id="dc377-108">説明</span><span class="sxs-lookup"><span data-stu-id="dc377-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dc377-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="dc377-109">Invoke</span></span>](#invoke) | <span data-ttu-id="dc377-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dc377-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="dc377-111">Members</span><span class="sxs-lookup"><span data-stu-id="dc377-111">Members</span></span>

#### <span data-ttu-id="dc377-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="dc377-112">Invoke</span></span> 

<span data-ttu-id="dc377-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dc377-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="dc377-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="dc377-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="dc377-115">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="dc377-115">There are no event args and the args parameter will be null.</span></span>

