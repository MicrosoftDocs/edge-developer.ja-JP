---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: c08a851eb21947cae4af465a233dc4c49508c84c
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884212"
---
# <span data-ttu-id="b994a-104">0.9.430-インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="b994a-104">0.9.430 - interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="b994a-105">呼び出し元は、このインターフェイスを実装して WebView から DevToolsProtocolEventReceived イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="b994a-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="b994a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b994a-106">Summary</span></span>

 <span data-ttu-id="b994a-107">Members</span><span class="sxs-lookup"><span data-stu-id="b994a-107">Members</span></span>                        | <span data-ttu-id="b994a-108">説明</span><span class="sxs-lookup"><span data-stu-id="b994a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b994a-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b994a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b994a-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b994a-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="b994a-111">Members</span><span class="sxs-lookup"><span data-stu-id="b994a-111">Members</span></span>

#### <span data-ttu-id="b994a-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="b994a-112">Invoke</span></span> 

<span data-ttu-id="b994a-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b994a-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="b994a-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2DevToolsProtocolEventReceivedEventArgs](ICoreWebView2DevToolsProtocolEventReceivedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="b994a-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2DevToolsProtocolEventReceivedEventArgs](ICoreWebView2DevToolsProtocolEventReceivedEventArgs.md) \* args)</span></span>

