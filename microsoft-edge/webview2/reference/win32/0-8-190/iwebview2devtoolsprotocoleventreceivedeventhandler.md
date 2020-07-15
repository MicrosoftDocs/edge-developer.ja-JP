---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2DevToolsProtocolEventReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: fea602ee66d1183c1cd78da02471274ea43b38e8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878590"
---
# <span data-ttu-id="40126-104">0.8.355-インターフェイス IWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="40126-104">0.8.355 - interface IWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="40126-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40126-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="40126-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40126-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="40126-107">呼び出し元はこのインターフェイスを実装して、 [IWebView2WebView](IWebView2WebView.md)から DevToolsProtocolEventReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="40126-107">The caller implements this interface to receive DevToolsProtocolEventReceived events from the [IWebView2WebView](IWebView2WebView.md).</span></span>

## <span data-ttu-id="40126-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="40126-108">Summary</span></span>

 <span data-ttu-id="40126-109">Members</span><span class="sxs-lookup"><span data-stu-id="40126-109">Members</span></span>                        | <span data-ttu-id="40126-110">説明</span><span class="sxs-lookup"><span data-stu-id="40126-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="40126-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="40126-111">Invoke</span></span>](#invoke) | <span data-ttu-id="40126-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="40126-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="40126-113">Members</span><span class="sxs-lookup"><span data-stu-id="40126-113">Members</span></span>

#### <span data-ttu-id="40126-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="40126-114">Invoke</span></span> 

<span data-ttu-id="40126-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="40126-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="40126-116">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2DevToolsProtocolEventReceivedEventArgs](IWebView2DevToolsProtocolEventReceivedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="40126-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2DevToolsProtocolEventReceivedEventArgs](IWebView2DevToolsProtocolEventReceivedEventArgs.md) \* args)</span></span>

