---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 57a0b844181c7c1ea14a56e87cc11dc008773a28
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886305"
---
# <span data-ttu-id="44906-104">0.9.430-インターフェイス ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="44906-104">0.9.430 - interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="44906-105">呼び出し元は、NavigationCompleted イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="44906-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="44906-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="44906-106">Summary</span></span>

 <span data-ttu-id="44906-107">Members</span><span class="sxs-lookup"><span data-stu-id="44906-107">Members</span></span>                        | <span data-ttu-id="44906-108">説明</span><span class="sxs-lookup"><span data-stu-id="44906-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="44906-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="44906-109">Invoke</span></span>](#invoke) | <span data-ttu-id="44906-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44906-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="44906-111">Members</span><span class="sxs-lookup"><span data-stu-id="44906-111">Members</span></span>

#### <span data-ttu-id="44906-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="44906-112">Invoke</span></span> 

<span data-ttu-id="44906-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44906-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="44906-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2NavigationCompletedEventArgs](ICoreWebView2NavigationCompletedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="44906-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2NavigationCompletedEventArgs](ICoreWebView2NavigationCompletedEventArgs.md) \* args)</span></span>

