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
ms.openlocfilehash: a8cd4dd948aa00aca7c2ef7d8c0c744b30db37e3
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654415"
---
# <span data-ttu-id="d7d6a-104">インターフェイス ICoreWebView2NewWindowRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d7d6a-104">interface ICoreWebView2NewWindowRequestedEventHandler</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="d7d6a-105">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d7d6a-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="d7d6a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d7d6a-106">Summary</span></span>

 <span data-ttu-id="d7d6a-107">Members</span><span class="sxs-lookup"><span data-stu-id="d7d6a-107">Members</span></span>                        | <span data-ttu-id="d7d6a-108">説明</span><span class="sxs-lookup"><span data-stu-id="d7d6a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d7d6a-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="d7d6a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d7d6a-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d7d6a-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d7d6a-111">Members</span><span class="sxs-lookup"><span data-stu-id="d7d6a-111">Members</span></span>

#### <span data-ttu-id="d7d6a-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="d7d6a-112">Invoke</span></span> 

<span data-ttu-id="d7d6a-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d7d6a-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d7d6a-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NewWindowRequestedEventArgs](icorewebview2newwindowrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="d7d6a-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NewWindowRequestedEventArgs](icorewebview2newwindowrequestedeventargs.md) \* args)</span></span>

