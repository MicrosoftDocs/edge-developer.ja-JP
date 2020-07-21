---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: ffa7f6e42802e8303a2ab68f3923dcc293c28d2a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885451"
---
# <span data-ttu-id="1076e-104">0.9.515-インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="1076e-104">0.9.515 - interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="1076e-105">呼び出し元は、このインターフェイスを実装して WebView から DevToolsProtocolEventReceived イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="1076e-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="1076e-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="1076e-106">Summary</span></span>

 <span data-ttu-id="1076e-107">Members</span><span class="sxs-lookup"><span data-stu-id="1076e-107">Members</span></span>                        | <span data-ttu-id="1076e-108">説明</span><span class="sxs-lookup"><span data-stu-id="1076e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1076e-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="1076e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="1076e-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1076e-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="1076e-111">Members</span><span class="sxs-lookup"><span data-stu-id="1076e-111">Members</span></span>

#### <span data-ttu-id="1076e-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="1076e-112">Invoke</span></span> 

<span data-ttu-id="1076e-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1076e-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="1076e-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="1076e-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span></span>

