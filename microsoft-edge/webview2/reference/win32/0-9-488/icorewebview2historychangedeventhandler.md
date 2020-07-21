---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: d90f461f6c2a1e573b0514213ec34f83f0d23366
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885500"
---
# <span data-ttu-id="21a57-104">0.9.515-インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="21a57-104">0.9.515 - interface ICoreWebView2HistoryChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="21a57-105">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="21a57-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="21a57-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="21a57-106">Summary</span></span>

 <span data-ttu-id="21a57-107">Members</span><span class="sxs-lookup"><span data-stu-id="21a57-107">Members</span></span>                        | <span data-ttu-id="21a57-108">説明</span><span class="sxs-lookup"><span data-stu-id="21a57-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="21a57-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="21a57-109">Invoke</span></span>](#invoke) | <span data-ttu-id="21a57-110">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="21a57-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="21a57-111">Members</span><span class="sxs-lookup"><span data-stu-id="21a57-111">Members</span></span>

#### <span data-ttu-id="21a57-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="21a57-112">Invoke</span></span> 

<span data-ttu-id="21a57-113">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="21a57-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="21a57-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="21a57-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

