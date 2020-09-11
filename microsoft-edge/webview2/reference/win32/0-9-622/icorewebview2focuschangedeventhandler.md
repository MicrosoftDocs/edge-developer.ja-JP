---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2FocusChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2FocusChangedEventHandler
ms.openlocfilehash: f94e6f8323862d092bf9157061333f5e801db891
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012305"
---
# <span data-ttu-id="1b6ea-104">インターフェイス ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="1b6ea-104">interface ICoreWebView2FocusChangedEventHandler</span></span> 

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="1b6ea-105">呼び出し元は、このメソッドを実装して GotFocus イベントと LostFocus イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1b6ea-105">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="1b6ea-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="1b6ea-106">Summary</span></span>

 <span data-ttu-id="1b6ea-107">Members</span><span class="sxs-lookup"><span data-stu-id="1b6ea-107">Members</span></span>                        | <span data-ttu-id="1b6ea-108">説明</span><span class="sxs-lookup"><span data-stu-id="1b6ea-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1b6ea-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="1b6ea-109">Invoke</span></span>](#invoke) | <span data-ttu-id="1b6ea-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1b6ea-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="1b6ea-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="1b6ea-111">There are no event args for this event.</span></span>

## <span data-ttu-id="1b6ea-112">Members</span><span class="sxs-lookup"><span data-stu-id="1b6ea-112">Members</span></span>

#### <span data-ttu-id="1b6ea-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="1b6ea-113">Invoke</span></span> 

<span data-ttu-id="1b6ea-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1b6ea-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="1b6ea-115">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="1b6ea-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="1b6ea-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="1b6ea-116">There are no event args and the args parameter will be null.</span></span>

