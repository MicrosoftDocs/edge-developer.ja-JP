---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2DevToolsProtocolEventReceivedEventHandler
ms.openlocfilehash: 2cb38d40e4e4a5e527cc8e8643b31ae7ceebecbe
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879598"
---
# <span data-ttu-id="e2891-104">インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="e2891-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="e2891-105">呼び出し元は、このインターフェイスを実装して WebView から DevToolsProtocolEventReceived イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="e2891-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="e2891-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e2891-106">Summary</span></span>

 <span data-ttu-id="e2891-107">Members</span><span class="sxs-lookup"><span data-stu-id="e2891-107">Members</span></span>                        | <span data-ttu-id="e2891-108">説明</span><span class="sxs-lookup"><span data-stu-id="e2891-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e2891-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="e2891-109">Invoke</span></span>](#invoke) | <span data-ttu-id="e2891-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2891-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="e2891-111">Members</span><span class="sxs-lookup"><span data-stu-id="e2891-111">Members</span></span>

#### <span data-ttu-id="e2891-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="e2891-112">Invoke</span></span> 

<span data-ttu-id="e2891-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2891-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="e2891-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="e2891-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span></span>

