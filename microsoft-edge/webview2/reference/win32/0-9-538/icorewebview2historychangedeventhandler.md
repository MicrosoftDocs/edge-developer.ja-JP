---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 0f14f8d281d4729d797eb5271a19cff67becafab
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699047"
---
# <span data-ttu-id="63385-104">インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="63385-104">interface ICoreWebView2HistoryChangedEventHandler</span></span> 

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="63385-105">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="63385-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="63385-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="63385-106">Summary</span></span>

 <span data-ttu-id="63385-107">Members</span><span class="sxs-lookup"><span data-stu-id="63385-107">Members</span></span>                        | <span data-ttu-id="63385-108">説明</span><span class="sxs-lookup"><span data-stu-id="63385-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="63385-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="63385-109">Invoke</span></span>](#invoke) | <span data-ttu-id="63385-110">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="63385-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="63385-111">Members</span><span class="sxs-lookup"><span data-stu-id="63385-111">Members</span></span>

#### <span data-ttu-id="63385-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="63385-112">Invoke</span></span> 

<span data-ttu-id="63385-113">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="63385-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="63385-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="63385-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

