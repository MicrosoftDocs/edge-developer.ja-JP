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
ms.openlocfilehash: 8c717bb57a5dc984d6cb2bbbbac79cf91d64fe2f
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699021"
---
# <span data-ttu-id="904c0-104">インターフェイス ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="904c0-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="904c0-105">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="904c0-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="904c0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="904c0-106">Summary</span></span>

 <span data-ttu-id="904c0-107">Members</span><span class="sxs-lookup"><span data-stu-id="904c0-107">Members</span></span>                        | <span data-ttu-id="904c0-108">説明</span><span class="sxs-lookup"><span data-stu-id="904c0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="904c0-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="904c0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="904c0-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="904c0-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="904c0-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="904c0-111">There are no event args for this event.</span></span>

## <span data-ttu-id="904c0-112">Members</span><span class="sxs-lookup"><span data-stu-id="904c0-112">Members</span></span>

#### <span data-ttu-id="904c0-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="904c0-113">Invoke</span></span> 

<span data-ttu-id="904c0-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="904c0-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="904c0-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="904c0-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="904c0-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="904c0-116">There are no event args and the args parameter will be null.</span></span>

