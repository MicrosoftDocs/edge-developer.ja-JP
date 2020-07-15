---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2FocusChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2FocusChangedEventHandler
ms.openlocfilehash: fc952437a9d5ffa7bb709bb6fb322438851babcd
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879899"
---
# <span data-ttu-id="219f6-104">インターフェイス ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="219f6-104">interface ICoreWebView2FocusChangedEventHandler</span></span> 

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="219f6-105">呼び出し元は、このメソッドを実装して GotFocus イベントと LostFocus イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="219f6-105">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="219f6-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="219f6-106">Summary</span></span>

 <span data-ttu-id="219f6-107">Members</span><span class="sxs-lookup"><span data-stu-id="219f6-107">Members</span></span>                        | <span data-ttu-id="219f6-108">説明</span><span class="sxs-lookup"><span data-stu-id="219f6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="219f6-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="219f6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="219f6-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="219f6-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="219f6-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="219f6-111">There are no event args for this event.</span></span>

## <span data-ttu-id="219f6-112">Members</span><span class="sxs-lookup"><span data-stu-id="219f6-112">Members</span></span>

#### <span data-ttu-id="219f6-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="219f6-113">Invoke</span></span> 

<span data-ttu-id="219f6-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="219f6-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="219f6-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="219f6-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="219f6-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="219f6-116">There are no event args and the args parameter will be null.</span></span>

