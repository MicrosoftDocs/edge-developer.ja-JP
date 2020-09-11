---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2HistoryChangedEventHandler
ms.openlocfilehash: 68cecdec63e64bde978156f17d6755a483abcc66
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011343"
---
# <span data-ttu-id="52479-104">0.9.579-インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="52479-104">0.9.579 - interface ICoreWebView2HistoryChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="52479-105">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="52479-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="52479-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="52479-106">Summary</span></span>

 <span data-ttu-id="52479-107">Members</span><span class="sxs-lookup"><span data-stu-id="52479-107">Members</span></span>                        | <span data-ttu-id="52479-108">説明</span><span class="sxs-lookup"><span data-stu-id="52479-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="52479-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="52479-109">Invoke</span></span>](#invoke) | <span data-ttu-id="52479-110">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="52479-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="52479-111">Members</span><span class="sxs-lookup"><span data-stu-id="52479-111">Members</span></span>

#### <span data-ttu-id="52479-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="52479-112">Invoke</span></span> 

<span data-ttu-id="52479-113">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="52479-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="52479-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="52479-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

