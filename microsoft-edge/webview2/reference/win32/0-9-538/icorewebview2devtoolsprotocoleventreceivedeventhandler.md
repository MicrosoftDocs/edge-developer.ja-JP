---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: c154b80e29476666bc0b2121b3eba63009946b36
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699006"
---
# <span data-ttu-id="346bf-104">インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="346bf-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="346bf-105">呼び出し元は、このインターフェイスを実装して WebView から DevToolsProtocolEventReceived イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="346bf-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="346bf-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="346bf-106">Summary</span></span>

 <span data-ttu-id="346bf-107">Members</span><span class="sxs-lookup"><span data-stu-id="346bf-107">Members</span></span>                        | <span data-ttu-id="346bf-108">説明</span><span class="sxs-lookup"><span data-stu-id="346bf-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="346bf-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="346bf-109">Invoke</span></span>](#invoke) | <span data-ttu-id="346bf-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="346bf-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="346bf-111">Members</span><span class="sxs-lookup"><span data-stu-id="346bf-111">Members</span></span>

#### <span data-ttu-id="346bf-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="346bf-112">Invoke</span></span> 

<span data-ttu-id="346bf-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="346bf-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="346bf-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="346bf-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span></span>

