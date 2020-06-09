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
ms.openlocfilehash: a90e7d3479f93d58d72db5c69cca53669a6d4501
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698989"
---
# <span data-ttu-id="4b5e0-104">インターフェイス ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="4b5e0-104">interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="4b5e0-105">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4b5e0-105">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="4b5e0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4b5e0-106">Summary</span></span>

 <span data-ttu-id="4b5e0-107">Members</span><span class="sxs-lookup"><span data-stu-id="4b5e0-107">Members</span></span>                        | <span data-ttu-id="4b5e0-108">説明</span><span class="sxs-lookup"><span data-stu-id="4b5e0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4b5e0-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="4b5e0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="4b5e0-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4b5e0-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="4b5e0-111">Members</span><span class="sxs-lookup"><span data-stu-id="4b5e0-111">Members</span></span>

#### <span data-ttu-id="4b5e0-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="4b5e0-112">Invoke</span></span> 

<span data-ttu-id="4b5e0-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4b5e0-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="4b5e0-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="4b5e0-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span></span>

