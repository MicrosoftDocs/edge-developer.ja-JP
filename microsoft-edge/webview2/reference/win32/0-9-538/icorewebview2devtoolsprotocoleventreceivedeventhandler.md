---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2DevToolsProtocolEventReceivedEventHandler
ms.openlocfilehash: 163ab3f16b6d835fc64aef4ea0fdff2883084faa
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010266"
---
# <span data-ttu-id="f2233-104">0.9.579-インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f2233-104">0.9.579 - interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="f2233-105">呼び出し元は、このインターフェイスを実装して WebView から DevToolsProtocolEventReceived イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="f2233-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="f2233-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f2233-106">Summary</span></span>

 <span data-ttu-id="f2233-107">Members</span><span class="sxs-lookup"><span data-stu-id="f2233-107">Members</span></span>                        | <span data-ttu-id="f2233-108">説明</span><span class="sxs-lookup"><span data-stu-id="f2233-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f2233-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f2233-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f2233-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f2233-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f2233-111">Members</span><span class="sxs-lookup"><span data-stu-id="f2233-111">Members</span></span>

#### <span data-ttu-id="f2233-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f2233-112">Invoke</span></span> 

<span data-ttu-id="f2233-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f2233-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f2233-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="f2233-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span></span>

