---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: e47ca26475ba1b59fa4ea8c87a7aada0d8d6695f
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884135"
---
# <span data-ttu-id="b11f0-104">0.9.430-インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="b11f0-104">0.9.430 - interface ICoreWebView2HistoryChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="b11f0-105">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b11f0-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="b11f0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b11f0-106">Summary</span></span>

 <span data-ttu-id="b11f0-107">Members</span><span class="sxs-lookup"><span data-stu-id="b11f0-107">Members</span></span>                        | <span data-ttu-id="b11f0-108">説明</span><span class="sxs-lookup"><span data-stu-id="b11f0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b11f0-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b11f0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b11f0-110">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="b11f0-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="b11f0-111">Members</span><span class="sxs-lookup"><span data-stu-id="b11f0-111">Members</span></span>

#### <span data-ttu-id="b11f0-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="b11f0-112">Invoke</span></span> 

<span data-ttu-id="b11f0-113">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="b11f0-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="b11f0-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="b11f0-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview,IUnknown \* args)</span></span>

