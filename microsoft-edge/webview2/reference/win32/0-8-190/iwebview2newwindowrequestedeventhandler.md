---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NewWindowRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 2fe743f0ffe39107252a184e2e98cc2904e3c640
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884975"
---
# <span data-ttu-id="d2d5d-104">0.8.355-インターフェイス IWebView2NewWindowRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d2d5d-104">0.8.355 - interface IWebView2NewWindowRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewWindowRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="d2d5d-105">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d2d5d-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="d2d5d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d2d5d-106">Summary</span></span>

 <span data-ttu-id="d2d5d-107">Members</span><span class="sxs-lookup"><span data-stu-id="d2d5d-107">Members</span></span>                        | <span data-ttu-id="d2d5d-108">説明</span><span class="sxs-lookup"><span data-stu-id="d2d5d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d2d5d-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="d2d5d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d2d5d-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d2d5d-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d2d5d-111">Members</span><span class="sxs-lookup"><span data-stu-id="d2d5d-111">Members</span></span>

#### <span data-ttu-id="d2d5d-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="d2d5d-112">Invoke</span></span> 

<span data-ttu-id="d2d5d-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d2d5d-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d2d5d-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2NewWindowRequestedEventArgs](IWebView2NewWindowRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="d2d5d-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2NewWindowRequestedEventArgs](IWebView2NewWindowRequestedEventArgs.md) \* args)</span></span>

