---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: c4f76c468cc5001c9eae347247dd5ffb8a60594f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654520"
---
# <span data-ttu-id="76126-104">インターフェイス ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="76126-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="76126-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76126-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="76126-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76126-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="76126-107">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="76126-107">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="76126-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="76126-108">Summary</span></span>

 <span data-ttu-id="76126-109">Members</span><span class="sxs-lookup"><span data-stu-id="76126-109">Members</span></span>                        | <span data-ttu-id="76126-110">説明</span><span class="sxs-lookup"><span data-stu-id="76126-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="76126-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="76126-111">Invoke</span></span>](#invoke) | <span data-ttu-id="76126-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="76126-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="76126-113">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="76126-113">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="76126-114">Members</span><span class="sxs-lookup"><span data-stu-id="76126-114">Members</span></span>

#### <span data-ttu-id="76126-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="76126-115">Invoke</span></span> 

<span data-ttu-id="76126-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="76126-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="76126-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2WebResourceRequestedEventArgs](ICoreWebView2WebResourceRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="76126-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2WebResourceRequestedEventArgs](ICoreWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>
