---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WebMessageReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebMessageReceivedEventHandler
ms.openlocfilehash: 47402035918c49a86c8e973c207d4f54d7d829c7
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879353"
---
# <span data-ttu-id="aef79-104">インターフェイス ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="aef79-104">interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="aef79-105">呼び出し元は、このインターフェイスを実装して WebMessageReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="aef79-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="aef79-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="aef79-106">Summary</span></span>

 <span data-ttu-id="aef79-107">Members</span><span class="sxs-lookup"><span data-stu-id="aef79-107">Members</span></span>                        | <span data-ttu-id="aef79-108">説明</span><span class="sxs-lookup"><span data-stu-id="aef79-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="aef79-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="aef79-109">Invoke</span></span>](#invoke) | <span data-ttu-id="aef79-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="aef79-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="aef79-111">Members</span><span class="sxs-lookup"><span data-stu-id="aef79-111">Members</span></span>

#### <span data-ttu-id="aef79-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="aef79-112">Invoke</span></span> 

<span data-ttu-id="aef79-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="aef79-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="aef79-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="aef79-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span></span>

