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
ms.openlocfilehash: 2a06c0b9e79d986e3b602ba8d970994b31ffd0f0
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699080"
---
# <span data-ttu-id="cdae7-104">インターフェイス ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="cdae7-104">interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="cdae7-105">呼び出し元は、NavigationCompleted イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="cdae7-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="cdae7-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="cdae7-106">Summary</span></span>

 <span data-ttu-id="cdae7-107">Members</span><span class="sxs-lookup"><span data-stu-id="cdae7-107">Members</span></span>                        | <span data-ttu-id="cdae7-108">説明</span><span class="sxs-lookup"><span data-stu-id="cdae7-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cdae7-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="cdae7-109">Invoke</span></span>](#invoke) | <span data-ttu-id="cdae7-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cdae7-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="cdae7-111">Members</span><span class="sxs-lookup"><span data-stu-id="cdae7-111">Members</span></span>

#### <span data-ttu-id="cdae7-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="cdae7-112">Invoke</span></span> 

<span data-ttu-id="cdae7-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cdae7-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="cdae7-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="cdae7-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span></span>

