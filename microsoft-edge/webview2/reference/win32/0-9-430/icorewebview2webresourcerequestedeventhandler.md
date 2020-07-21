---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: d35e21fde7788b1df5b201f8690196ecd0d82a34
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884093"
---
# <span data-ttu-id="68679-104">0.9.430-インターフェイス ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="68679-104">0.9.430 - interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="68679-105">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="68679-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="68679-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="68679-106">Summary</span></span>

 <span data-ttu-id="68679-107">Members</span><span class="sxs-lookup"><span data-stu-id="68679-107">Members</span></span>                        | <span data-ttu-id="68679-108">説明</span><span class="sxs-lookup"><span data-stu-id="68679-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="68679-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="68679-109">Invoke</span></span>](#invoke) | <span data-ttu-id="68679-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="68679-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="68679-111">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="68679-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="68679-112">Members</span><span class="sxs-lookup"><span data-stu-id="68679-112">Members</span></span>

#### <span data-ttu-id="68679-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="68679-113">Invoke</span></span> 

<span data-ttu-id="68679-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="68679-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="68679-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2WebResourceRequestedEventArgs](ICoreWebView2WebResourceRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="68679-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2WebResourceRequestedEventArgs](ICoreWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>

