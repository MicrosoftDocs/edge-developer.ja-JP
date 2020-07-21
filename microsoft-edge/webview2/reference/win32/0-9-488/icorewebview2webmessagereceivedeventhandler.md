---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebMessageReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b69854163a45c09d605cac2f544866d58546c71b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885185"
---
# <span data-ttu-id="76c0d-104">0.9.515-インターフェイス ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="76c0d-104">0.9.515 - interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="76c0d-105">呼び出し元は、このインターフェイスを実装して WebMessageReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="76c0d-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="76c0d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="76c0d-106">Summary</span></span>

 <span data-ttu-id="76c0d-107">Members</span><span class="sxs-lookup"><span data-stu-id="76c0d-107">Members</span></span>                        | <span data-ttu-id="76c0d-108">説明</span><span class="sxs-lookup"><span data-stu-id="76c0d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="76c0d-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="76c0d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="76c0d-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="76c0d-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="76c0d-111">Members</span><span class="sxs-lookup"><span data-stu-id="76c0d-111">Members</span></span>

#### <span data-ttu-id="76c0d-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="76c0d-112">Invoke</span></span> 

<span data-ttu-id="76c0d-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="76c0d-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="76c0d-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="76c0d-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span></span>

