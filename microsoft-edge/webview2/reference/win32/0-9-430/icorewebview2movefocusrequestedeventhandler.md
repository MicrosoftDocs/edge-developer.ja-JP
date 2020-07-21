---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2MoveFocusRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: d50f84edeb532d90a1268f553b38e4cbf256556a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884088"
---
# <span data-ttu-id="bcdd8-104">0.9.430-インターフェイス ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="bcdd8-104">0.9.430 - interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="bcdd8-105">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-105">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="bcdd8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="bcdd8-106">Summary</span></span>

 <span data-ttu-id="bcdd8-107">Members</span><span class="sxs-lookup"><span data-stu-id="bcdd8-107">Members</span></span>                        | <span data-ttu-id="bcdd8-108">説明</span><span class="sxs-lookup"><span data-stu-id="bcdd8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bcdd8-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="bcdd8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="bcdd8-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="bcdd8-111">Members</span><span class="sxs-lookup"><span data-stu-id="bcdd8-111">Members</span></span>

#### <span data-ttu-id="bcdd8-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="bcdd8-112">Invoke</span></span> 

<span data-ttu-id="bcdd8-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="bcdd8-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,[ICoreWebView2MoveFocusRequestedEventArgs](ICoreWebView2MoveFocusRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="bcdd8-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,[ICoreWebView2MoveFocusRequestedEventArgs](ICoreWebView2MoveFocusRequestedEventArgs.md) \* args)</span></span>

