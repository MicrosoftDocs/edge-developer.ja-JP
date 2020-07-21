---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 70ecc1898f9a72656f12b912d103116c381d4218
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885675"
---
# <span data-ttu-id="53e82-104">0.8.355-インターフェイス IWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="53e82-104">0.8.355 - interface IWebView2WebResourceRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="53e82-105">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="53e82-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="53e82-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="53e82-106">Summary</span></span>

 <span data-ttu-id="53e82-107">Members</span><span class="sxs-lookup"><span data-stu-id="53e82-107">Members</span></span>                        | <span data-ttu-id="53e82-108">説明</span><span class="sxs-lookup"><span data-stu-id="53e82-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="53e82-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="53e82-109">Invoke</span></span>](#invoke) | <span data-ttu-id="53e82-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="53e82-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="53e82-111">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="53e82-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="53e82-112">Members</span><span class="sxs-lookup"><span data-stu-id="53e82-112">Members</span></span>

#### <span data-ttu-id="53e82-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="53e82-113">Invoke</span></span> 

<span data-ttu-id="53e82-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="53e82-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="53e82-115">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="53e82-115">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>

