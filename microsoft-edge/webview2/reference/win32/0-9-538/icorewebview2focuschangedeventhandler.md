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
ms.openlocfilehash: 6fc29b620df5bcd265a7576e4b7ca1c7ebd73e6f
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699055"
---
# <span data-ttu-id="f764b-104">インターフェイス ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f764b-104">interface ICoreWebView2FocusChangedEventHandler</span></span> 

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="f764b-105">呼び出し元は、このメソッドを実装して GotFocus イベントと LostFocus イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f764b-105">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="f764b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f764b-106">Summary</span></span>

 <span data-ttu-id="f764b-107">Members</span><span class="sxs-lookup"><span data-stu-id="f764b-107">Members</span></span>                        | <span data-ttu-id="f764b-108">説明</span><span class="sxs-lookup"><span data-stu-id="f764b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f764b-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f764b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f764b-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f764b-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="f764b-111">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="f764b-111">There are no event args for this event.</span></span>

## <span data-ttu-id="f764b-112">Members</span><span class="sxs-lookup"><span data-stu-id="f764b-112">Members</span></span>

#### <span data-ttu-id="f764b-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="f764b-113">Invoke</span></span> 

<span data-ttu-id="f764b-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f764b-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f764b-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="f764b-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="f764b-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="f764b-116">There are no event args and the args parameter will be null.</span></span>

