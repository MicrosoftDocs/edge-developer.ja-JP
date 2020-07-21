---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 4f2bb4e5077fea7583f7d9f9886923ea1867e1ce
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883683"
---
# <span data-ttu-id="24ce1-104">0.9.515-インターフェイス ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="24ce1-104">0.9.515 - interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="24ce1-105">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="24ce1-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="24ce1-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="24ce1-106">Summary</span></span>

 <span data-ttu-id="24ce1-107">Members</span><span class="sxs-lookup"><span data-stu-id="24ce1-107">Members</span></span>                        | <span data-ttu-id="24ce1-108">説明</span><span class="sxs-lookup"><span data-stu-id="24ce1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="24ce1-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="24ce1-109">Invoke</span></span>](#invoke) | <span data-ttu-id="24ce1-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="24ce1-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="24ce1-111">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="24ce1-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="24ce1-112">Members</span><span class="sxs-lookup"><span data-stu-id="24ce1-112">Members</span></span>

#### <span data-ttu-id="24ce1-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="24ce1-113">Invoke</span></span> 

<span data-ttu-id="24ce1-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="24ce1-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="24ce1-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="24ce1-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

