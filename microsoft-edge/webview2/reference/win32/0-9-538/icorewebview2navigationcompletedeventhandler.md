---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationCompletedEventHandler
ms.openlocfilehash: 24651585298998eaa42b2be242785de1bf4d6f84
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879794"
---
# <span data-ttu-id="24930-104">インターフェイス ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="24930-104">interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="24930-105">呼び出し元は、NavigationCompleted イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="24930-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="24930-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="24930-106">Summary</span></span>

 <span data-ttu-id="24930-107">Members</span><span class="sxs-lookup"><span data-stu-id="24930-107">Members</span></span>                        | <span data-ttu-id="24930-108">説明</span><span class="sxs-lookup"><span data-stu-id="24930-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="24930-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="24930-109">Invoke</span></span>](#invoke) | <span data-ttu-id="24930-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="24930-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="24930-111">Members</span><span class="sxs-lookup"><span data-stu-id="24930-111">Members</span></span>

#### <span data-ttu-id="24930-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="24930-112">Invoke</span></span> 

<span data-ttu-id="24930-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="24930-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="24930-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="24930-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span></span>

