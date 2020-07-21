---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2DevToolsProtocolEventReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: a26a2c18c402bffe11353b2f53f0559acde3663b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886165"
---
# <span data-ttu-id="3ecb0-104">0.8.355-インターフェイス IWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="3ecb0-104">0.8.355 - interface IWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="3ecb0-105">呼び出し元はこのインターフェイスを実装して、 [IWebView2WebView](IWebView2WebView.md)から DevToolsProtocolEventReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3ecb0-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the [IWebView2WebView](IWebView2WebView.md).</span></span>

## <span data-ttu-id="3ecb0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3ecb0-106">Summary</span></span>

 <span data-ttu-id="3ecb0-107">Members</span><span class="sxs-lookup"><span data-stu-id="3ecb0-107">Members</span></span>                        | <span data-ttu-id="3ecb0-108">説明</span><span class="sxs-lookup"><span data-stu-id="3ecb0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3ecb0-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="3ecb0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3ecb0-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3ecb0-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="3ecb0-111">Members</span><span class="sxs-lookup"><span data-stu-id="3ecb0-111">Members</span></span>

#### <span data-ttu-id="3ecb0-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="3ecb0-112">Invoke</span></span> 

<span data-ttu-id="3ecb0-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3ecb0-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3ecb0-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2DevToolsProtocolEventReceivedEventArgs](IWebView2DevToolsProtocolEventReceivedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="3ecb0-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2DevToolsProtocolEventReceivedEventArgs](IWebView2DevToolsProtocolEventReceivedEventArgs.md) \* args)</span></span>

