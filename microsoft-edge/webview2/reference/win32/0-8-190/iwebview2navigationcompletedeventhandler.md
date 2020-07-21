---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NavigationCompletedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: cf799ae12b977f66bfba4d1b7664e3abc6241304
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885922"
---
# <span data-ttu-id="4c3be-104">0.8.355-インターフェイス IWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="4c3be-104">0.8.355 - interface IWebView2NavigationCompletedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="4c3be-105">呼び出し元は、NavigationCompleted イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4c3be-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="4c3be-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4c3be-106">Summary</span></span>

 <span data-ttu-id="4c3be-107">Members</span><span class="sxs-lookup"><span data-stu-id="4c3be-107">Members</span></span>                        | <span data-ttu-id="4c3be-108">説明</span><span class="sxs-lookup"><span data-stu-id="4c3be-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4c3be-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="4c3be-109">Invoke</span></span>](#invoke) | <span data-ttu-id="4c3be-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4c3be-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="4c3be-111">Members</span><span class="sxs-lookup"><span data-stu-id="4c3be-111">Members</span></span>

#### <span data-ttu-id="4c3be-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="4c3be-112">Invoke</span></span> 

<span data-ttu-id="4c3be-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4c3be-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="4c3be-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2NavigationCompletedEventArgs](IWebView2NavigationCompletedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="4c3be-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2NavigationCompletedEventArgs](IWebView2NavigationCompletedEventArgs.md) \* args)</span></span>

