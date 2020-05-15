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
ms.openlocfilehash: 889728489b6c4b06cd224915a0e12ee0a4144653
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654211"
---
# <span data-ttu-id="448ed-104">インターフェイス ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="448ed-104">interface ICoreWebView2WindowCloseRequestedEventHandler</span></span> 

```
interface ICoreWebView2WindowCloseRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="448ed-105">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="448ed-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="448ed-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="448ed-106">Summary</span></span>

 <span data-ttu-id="448ed-107">Members</span><span class="sxs-lookup"><span data-stu-id="448ed-107">Members</span></span>                        | <span data-ttu-id="448ed-108">説明</span><span class="sxs-lookup"><span data-stu-id="448ed-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="448ed-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="448ed-109">Invoke</span></span>](#invoke) | <span data-ttu-id="448ed-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="448ed-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="448ed-111">Members</span><span class="sxs-lookup"><span data-stu-id="448ed-111">Members</span></span>

#### <span data-ttu-id="448ed-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="448ed-112">Invoke</span></span> 

<span data-ttu-id="448ed-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="448ed-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="448ed-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="448ed-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="448ed-115">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="448ed-115">There are no event args and the args parameter will be null.</span></span>

