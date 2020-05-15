---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 602c00258e9ff3362269ebe90de8306ecbd7503e
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654221"
---
# <span data-ttu-id="7527b-104">インターフェイス IWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="7527b-104">interface IWebView2WebResourceRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="7527b-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7527b-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="7527b-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7527b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="7527b-107">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7527b-107">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="7527b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="7527b-108">Summary</span></span>

 <span data-ttu-id="7527b-109">Members</span><span class="sxs-lookup"><span data-stu-id="7527b-109">Members</span></span>                        | <span data-ttu-id="7527b-110">説明</span><span class="sxs-lookup"><span data-stu-id="7527b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7527b-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="7527b-111">Invoke</span></span>](#invoke) | <span data-ttu-id="7527b-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7527b-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="7527b-113">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="7527b-113">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="7527b-114">Members</span><span class="sxs-lookup"><span data-stu-id="7527b-114">Members</span></span>

#### <span data-ttu-id="7527b-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="7527b-115">Invoke</span></span> 

<span data-ttu-id="7527b-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7527b-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="7527b-117">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="7527b-117">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>

