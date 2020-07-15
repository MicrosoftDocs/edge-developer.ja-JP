---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2MoveFocusRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2MoveFocusRequestedEventHandler
ms.openlocfilehash: b0e7f3f005b90c5656eeeac09716130544b0ee20
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879836"
---
# <span data-ttu-id="f27ba-104">インターフェイス ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f27ba-104">interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="f27ba-105">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f27ba-105">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="f27ba-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f27ba-106">Summary</span></span>

 <span data-ttu-id="f27ba-107">Members</span><span class="sxs-lookup"><span data-stu-id="f27ba-107">Members</span></span>                        | <span data-ttu-id="f27ba-108">説明</span><span class="sxs-lookup"><span data-stu-id="f27ba-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f27ba-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f27ba-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f27ba-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f27ba-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f27ba-111">Members</span><span class="sxs-lookup"><span data-stu-id="f27ba-111">Members</span></span>

#### <span data-ttu-id="f27ba-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f27ba-112">Invoke</span></span> 

<span data-ttu-id="f27ba-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f27ba-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f27ba-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="f27ba-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span></span>

