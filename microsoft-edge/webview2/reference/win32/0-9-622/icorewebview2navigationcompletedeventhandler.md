---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationCompletedEventHandler
ms.openlocfilehash: 3ff529c649eb455e8ea1b14ebbd25533631d2b99
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012334"
---
# <span data-ttu-id="3a7aa-104">インターフェイス ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="3a7aa-104">interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="3a7aa-105">呼び出し元は、NavigationCompleted イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="3a7aa-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="3a7aa-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3a7aa-106">Summary</span></span>

 <span data-ttu-id="3a7aa-107">Members</span><span class="sxs-lookup"><span data-stu-id="3a7aa-107">Members</span></span>                        | <span data-ttu-id="3a7aa-108">説明</span><span class="sxs-lookup"><span data-stu-id="3a7aa-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3a7aa-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="3a7aa-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3a7aa-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3a7aa-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="3a7aa-111">Members</span><span class="sxs-lookup"><span data-stu-id="3a7aa-111">Members</span></span>

#### <span data-ttu-id="3a7aa-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="3a7aa-112">Invoke</span></span> 

<span data-ttu-id="3a7aa-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3a7aa-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3a7aa-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="3a7aa-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span></span>

