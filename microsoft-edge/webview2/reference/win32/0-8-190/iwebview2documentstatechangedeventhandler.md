---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2DocumentStateChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 3d6bf8345e88dde213c15e51c26056d0239f0230
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886112"
---
# <span data-ttu-id="ae9db-104">0.8.355-インターフェイス IWebView2DocumentStateChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="ae9db-104">0.8.355 - interface IWebView2DocumentStateChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DocumentStateChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="ae9db-105">呼び出し元は、このインターフェイスを実装して DocumentStateChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ae9db-105">The caller implements this interface to receive the DocumentStateChanged event.</span></span>

## <span data-ttu-id="ae9db-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="ae9db-106">Summary</span></span>

 <span data-ttu-id="ae9db-107">Members</span><span class="sxs-lookup"><span data-stu-id="ae9db-107">Members</span></span>                        | <span data-ttu-id="ae9db-108">説明</span><span class="sxs-lookup"><span data-stu-id="ae9db-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ae9db-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="ae9db-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ae9db-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ae9db-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="ae9db-111">Members</span><span class="sxs-lookup"><span data-stu-id="ae9db-111">Members</span></span>

#### <span data-ttu-id="ae9db-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="ae9db-112">Invoke</span></span> 

<span data-ttu-id="ae9db-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ae9db-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="ae9db-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2DocumentStateChangedEventArgs](IWebView2DocumentStateChangedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="ae9db-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2DocumentStateChangedEventArgs](IWebView2DocumentStateChangedEventArgs.md) \* args)</span></span>

