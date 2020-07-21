---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 30c39bf10c874c17787c235ebb1589de1c9449ff
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885556"
---
# <span data-ttu-id="45f56-104">0.9.515-インターフェイス ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="45f56-104">0.9.515 - interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="45f56-105">呼び出し元は、NavigationCompleted イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="45f56-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="45f56-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="45f56-106">Summary</span></span>

 <span data-ttu-id="45f56-107">Members</span><span class="sxs-lookup"><span data-stu-id="45f56-107">Members</span></span>                        | <span data-ttu-id="45f56-108">説明</span><span class="sxs-lookup"><span data-stu-id="45f56-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="45f56-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="45f56-109">Invoke</span></span>](#invoke) | <span data-ttu-id="45f56-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="45f56-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="45f56-111">Members</span><span class="sxs-lookup"><span data-stu-id="45f56-111">Members</span></span>

#### <span data-ttu-id="45f56-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="45f56-112">Invoke</span></span> 

<span data-ttu-id="45f56-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="45f56-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="45f56-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="45f56-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span></span>

