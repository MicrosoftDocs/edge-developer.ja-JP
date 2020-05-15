---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 17c912605a90dba73e5876cd6d3c26b15cdd98ec
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654425"
---
# <span data-ttu-id="72e6e-104">インターフェイス ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="72e6e-104">interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="72e6e-105">呼び出し元は、NavigationCompleted イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="72e6e-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="72e6e-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="72e6e-106">Summary</span></span>

 <span data-ttu-id="72e6e-107">Members</span><span class="sxs-lookup"><span data-stu-id="72e6e-107">Members</span></span>                        | <span data-ttu-id="72e6e-108">説明</span><span class="sxs-lookup"><span data-stu-id="72e6e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="72e6e-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="72e6e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="72e6e-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="72e6e-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="72e6e-111">Members</span><span class="sxs-lookup"><span data-stu-id="72e6e-111">Members</span></span>

#### <span data-ttu-id="72e6e-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="72e6e-112">Invoke</span></span> 

<span data-ttu-id="72e6e-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="72e6e-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="72e6e-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="72e6e-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span></span>

