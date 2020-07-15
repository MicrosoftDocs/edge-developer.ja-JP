---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebResourceRequestedEventHandler
ms.openlocfilehash: 9cd221ac1b528b0be52201daa0c15217534944a6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879227"
---
# <span data-ttu-id="45a50-104">インターフェイス ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="45a50-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="45a50-105">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="45a50-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="45a50-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="45a50-106">Summary</span></span>

 <span data-ttu-id="45a50-107">Members</span><span class="sxs-lookup"><span data-stu-id="45a50-107">Members</span></span>                        | <span data-ttu-id="45a50-108">説明</span><span class="sxs-lookup"><span data-stu-id="45a50-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="45a50-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="45a50-109">Invoke</span></span>](#invoke) | <span data-ttu-id="45a50-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="45a50-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="45a50-111">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="45a50-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="45a50-112">Members</span><span class="sxs-lookup"><span data-stu-id="45a50-112">Members</span></span>

#### <span data-ttu-id="45a50-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="45a50-113">Invoke</span></span> 

<span data-ttu-id="45a50-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="45a50-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="45a50-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="45a50-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

