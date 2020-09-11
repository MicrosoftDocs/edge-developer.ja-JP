---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationCompletedEventHandler
ms.openlocfilehash: 7e61f54882d653a28ec31a97c59758eeff300b26
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011266"
---
# <span data-ttu-id="b2992-104">0.9.579-インターフェイス ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="b2992-104">0.9.579 - interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="b2992-105">呼び出し元は、NavigationCompleted イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="b2992-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="b2992-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b2992-106">Summary</span></span>

 <span data-ttu-id="b2992-107">Members</span><span class="sxs-lookup"><span data-stu-id="b2992-107">Members</span></span>                        | <span data-ttu-id="b2992-108">説明</span><span class="sxs-lookup"><span data-stu-id="b2992-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b2992-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b2992-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b2992-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b2992-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="b2992-111">Members</span><span class="sxs-lookup"><span data-stu-id="b2992-111">Members</span></span>

#### <span data-ttu-id="b2992-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="b2992-112">Invoke</span></span> 

<span data-ttu-id="b2992-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b2992-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="b2992-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="b2992-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span></span>

