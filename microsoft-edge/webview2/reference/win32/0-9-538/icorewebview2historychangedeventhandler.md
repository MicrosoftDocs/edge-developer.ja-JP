---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2HistoryChangedEventHandler
ms.openlocfilehash: cf9d04c14f39a9ba1686d5cc9b002041313b645d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879913"
---
# <span data-ttu-id="2f1ff-104">インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="2f1ff-104">interface ICoreWebView2HistoryChangedEventHandler</span></span> 

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="2f1ff-105">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2f1ff-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="2f1ff-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2f1ff-106">Summary</span></span>

 <span data-ttu-id="2f1ff-107">Members</span><span class="sxs-lookup"><span data-stu-id="2f1ff-107">Members</span></span>                        | <span data-ttu-id="2f1ff-108">説明</span><span class="sxs-lookup"><span data-stu-id="2f1ff-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2f1ff-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="2f1ff-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2f1ff-110">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="2f1ff-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="2f1ff-111">Members</span><span class="sxs-lookup"><span data-stu-id="2f1ff-111">Members</span></span>

#### <span data-ttu-id="2f1ff-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="2f1ff-112">Invoke</span></span> 

<span data-ttu-id="2f1ff-113">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="2f1ff-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="2f1ff-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="2f1ff-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

