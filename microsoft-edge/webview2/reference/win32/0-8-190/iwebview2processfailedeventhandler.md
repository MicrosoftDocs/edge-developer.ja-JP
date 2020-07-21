---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 97a0d8f2afda5f6391a574e6ad62fbd2e17abcc1
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884940"
---
# <span data-ttu-id="9a2aa-104">0.8.355-インターフェイス IWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="9a2aa-104">0.8.355 - interface IWebView2ProcessFailedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="9a2aa-105">呼び出し元は、ProcessFailed イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="9a2aa-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="9a2aa-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="9a2aa-106">Summary</span></span>

 <span data-ttu-id="9a2aa-107">Members</span><span class="sxs-lookup"><span data-stu-id="9a2aa-107">Members</span></span>                        | <span data-ttu-id="9a2aa-108">説明</span><span class="sxs-lookup"><span data-stu-id="9a2aa-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9a2aa-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="9a2aa-109">Invoke</span></span>](#invoke) | <span data-ttu-id="9a2aa-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9a2aa-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="9a2aa-111">Members</span><span class="sxs-lookup"><span data-stu-id="9a2aa-111">Members</span></span>

#### <span data-ttu-id="9a2aa-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="9a2aa-112">Invoke</span></span> 

<span data-ttu-id="9a2aa-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9a2aa-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="9a2aa-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2ProcessFailedEventArgs](IWebView2ProcessFailedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="9a2aa-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2ProcessFailedEventArgs](IWebView2ProcessFailedEventArgs.md) \* args)</span></span>

