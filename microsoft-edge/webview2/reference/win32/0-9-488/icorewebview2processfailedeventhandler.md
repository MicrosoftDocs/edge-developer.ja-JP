---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 6b7d48fbec0c3bb0008f0f429bf6414ed855a09f
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884793"
---
# <span data-ttu-id="d8741-104">0.9.515-インターフェイス ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d8741-104">0.9.515 - interface ICoreWebView2ProcessFailedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="d8741-105">呼び出し元は、ProcessFailed イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="d8741-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="d8741-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d8741-106">Summary</span></span>

 <span data-ttu-id="d8741-107">Members</span><span class="sxs-lookup"><span data-stu-id="d8741-107">Members</span></span>                        | <span data-ttu-id="d8741-108">説明</span><span class="sxs-lookup"><span data-stu-id="d8741-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d8741-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="d8741-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d8741-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d8741-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d8741-111">Members</span><span class="sxs-lookup"><span data-stu-id="d8741-111">Members</span></span>

#### <span data-ttu-id="d8741-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="d8741-112">Invoke</span></span> 

<span data-ttu-id="d8741-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d8741-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d8741-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="d8741-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* args)</span></span>

