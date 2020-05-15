---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f9dcfa996058f4499daff03d8cad033ac61db4c9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654426"
---
# <span data-ttu-id="c696a-104">インターフェイス ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c696a-104">interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="c696a-105">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c696a-105">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="c696a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c696a-106">Summary</span></span>

 <span data-ttu-id="c696a-107">Members</span><span class="sxs-lookup"><span data-stu-id="c696a-107">Members</span></span>                        | <span data-ttu-id="c696a-108">説明</span><span class="sxs-lookup"><span data-stu-id="c696a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c696a-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="c696a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c696a-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c696a-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="c696a-111">Members</span><span class="sxs-lookup"><span data-stu-id="c696a-111">Members</span></span>

#### <span data-ttu-id="c696a-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="c696a-112">Invoke</span></span> 

<span data-ttu-id="c696a-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c696a-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c696a-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="c696a-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span></span>

