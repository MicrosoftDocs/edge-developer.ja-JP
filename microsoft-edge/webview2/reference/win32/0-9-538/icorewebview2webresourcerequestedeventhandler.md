---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 64f29f8c771a14d569fd45f7359614795bbc0386
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699096"
---
# <span data-ttu-id="966d8-104">インターフェイス ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="966d8-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="966d8-105">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="966d8-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="966d8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="966d8-106">Summary</span></span>

 <span data-ttu-id="966d8-107">Members</span><span class="sxs-lookup"><span data-stu-id="966d8-107">Members</span></span>                        | <span data-ttu-id="966d8-108">説明</span><span class="sxs-lookup"><span data-stu-id="966d8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="966d8-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="966d8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="966d8-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="966d8-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="966d8-111">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="966d8-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="966d8-112">Members</span><span class="sxs-lookup"><span data-stu-id="966d8-112">Members</span></span>

#### <span data-ttu-id="966d8-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="966d8-113">Invoke</span></span> 

<span data-ttu-id="966d8-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="966d8-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="966d8-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="966d8-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

