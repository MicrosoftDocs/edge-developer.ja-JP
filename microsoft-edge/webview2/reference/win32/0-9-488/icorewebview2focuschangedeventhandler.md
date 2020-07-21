---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2FocusChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 5a0c15cf56283c9d2ba71b9f8261288977c6ef39
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885472"
---
# <span data-ttu-id="3641c-104">0.9.515-インターフェイス ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="3641c-104">0.9.515 - interface ICoreWebView2FocusChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="3641c-105">呼び出し元は、このメソッドを実装して GotFocus イベントと LostFocus イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3641c-105">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="3641c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3641c-106">Summary</span></span>

 <span data-ttu-id="3641c-107">Members</span><span class="sxs-lookup"><span data-stu-id="3641c-107">Members</span></span>                        | <span data-ttu-id="3641c-108">説明</span><span class="sxs-lookup"><span data-stu-id="3641c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3641c-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="3641c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3641c-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3641c-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="3641c-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="3641c-111">There are no event args for this event.</span></span>

## <span data-ttu-id="3641c-112">Members</span><span class="sxs-lookup"><span data-stu-id="3641c-112">Members</span></span>

#### <span data-ttu-id="3641c-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="3641c-113">Invoke</span></span> 

<span data-ttu-id="3641c-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3641c-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3641c-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="3641c-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="3641c-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="3641c-116">There are no event args and the args parameter will be null.</span></span>

