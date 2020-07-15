---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: c0980f26ef06497cded81e2f9c7c00162af18d9b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878093"
---
# <span data-ttu-id="65282-104">0.8.355-インターフェイス IWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="65282-104">0.8.355 - interface IWebView2WebResourceRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="65282-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65282-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="65282-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65282-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="65282-107">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="65282-107">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="65282-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="65282-108">Summary</span></span>

 <span data-ttu-id="65282-109">Members</span><span class="sxs-lookup"><span data-stu-id="65282-109">Members</span></span>                        | <span data-ttu-id="65282-110">説明</span><span class="sxs-lookup"><span data-stu-id="65282-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="65282-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="65282-111">Invoke</span></span>](#invoke) | <span data-ttu-id="65282-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="65282-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="65282-113">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="65282-113">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="65282-114">Members</span><span class="sxs-lookup"><span data-stu-id="65282-114">Members</span></span>

#### <span data-ttu-id="65282-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="65282-115">Invoke</span></span> 

<span data-ttu-id="65282-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="65282-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="65282-117">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="65282-117">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>

