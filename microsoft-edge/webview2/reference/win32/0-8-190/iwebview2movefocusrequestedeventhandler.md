---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2MoveFocusRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: fe84f29798b01aed2787559c717f2893c9eda7f9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885941"
---
# <span data-ttu-id="61822-104">0.8.355-インターフェイス IWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="61822-104">0.8.355 - interface IWebView2MoveFocusRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="61822-105">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="61822-105">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="61822-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="61822-106">Summary</span></span>

 <span data-ttu-id="61822-107">Members</span><span class="sxs-lookup"><span data-stu-id="61822-107">Members</span></span>                        | <span data-ttu-id="61822-108">説明</span><span class="sxs-lookup"><span data-stu-id="61822-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="61822-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="61822-109">Invoke</span></span>](#invoke) | <span data-ttu-id="61822-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="61822-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="61822-111">Members</span><span class="sxs-lookup"><span data-stu-id="61822-111">Members</span></span>

#### <span data-ttu-id="61822-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="61822-112">Invoke</span></span> 

<span data-ttu-id="61822-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="61822-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="61822-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2MoveFocusRequestedEventArgs](IWebView2MoveFocusRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="61822-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2MoveFocusRequestedEventArgs](IWebView2MoveFocusRequestedEventArgs.md) \* args)</span></span>

