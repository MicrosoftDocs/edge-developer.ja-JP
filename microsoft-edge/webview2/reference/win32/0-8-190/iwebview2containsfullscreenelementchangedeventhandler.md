---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 70e9ad7782fe495ffd366664ecb132edd0c57df5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878653"
---
# <span data-ttu-id="262ee-104">0.8.355-インターフェイス IWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="262ee-104">0.8.355 - interface IWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="262ee-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="262ee-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="262ee-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="262ee-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="262ee-107">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="262ee-107">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="262ee-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="262ee-108">Summary</span></span>

 <span data-ttu-id="262ee-109">Members</span><span class="sxs-lookup"><span data-stu-id="262ee-109">Members</span></span>                        | <span data-ttu-id="262ee-110">説明</span><span class="sxs-lookup"><span data-stu-id="262ee-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="262ee-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="262ee-111">Invoke</span></span>](#invoke) | <span data-ttu-id="262ee-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="262ee-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="262ee-113">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="262ee-113">There are no event args for this event.</span></span>

## <span data-ttu-id="262ee-114">Members</span><span class="sxs-lookup"><span data-stu-id="262ee-114">Members</span></span>

#### <span data-ttu-id="262ee-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="262ee-115">Invoke</span></span> 

<span data-ttu-id="262ee-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="262ee-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="262ee-117">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView5](IWebView2WebView5.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="262ee-117">public HRESULT [Invoke](#invoke)([IWebView2WebView5](IWebView2WebView5.md) \* webview,IUnknown \* args)</span></span>

<span data-ttu-id="262ee-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="262ee-118">There are no event args and the args parameter will be null.</span></span>

