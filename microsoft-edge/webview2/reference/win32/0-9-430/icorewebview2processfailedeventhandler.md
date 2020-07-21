---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: ed9b94b5bd9015b07cf44cf2cbeec330688242ff
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884107"
---
# <span data-ttu-id="46a97-104">0.9.430-インターフェイス ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="46a97-104">0.9.430 - interface ICoreWebView2ProcessFailedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="46a97-105">呼び出し元は、ProcessFailed イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="46a97-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="46a97-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="46a97-106">Summary</span></span>

 <span data-ttu-id="46a97-107">Members</span><span class="sxs-lookup"><span data-stu-id="46a97-107">Members</span></span>                        | <span data-ttu-id="46a97-108">説明</span><span class="sxs-lookup"><span data-stu-id="46a97-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="46a97-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="46a97-109">Invoke</span></span>](#invoke) | <span data-ttu-id="46a97-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="46a97-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="46a97-111">Members</span><span class="sxs-lookup"><span data-stu-id="46a97-111">Members</span></span>

#### <span data-ttu-id="46a97-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="46a97-112">Invoke</span></span> 

<span data-ttu-id="46a97-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="46a97-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="46a97-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2ProcessFailedEventArgs](ICoreWebView2ProcessFailedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="46a97-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2ProcessFailedEventArgs](ICoreWebView2ProcessFailedEventArgs.md) \* args)</span></span>

