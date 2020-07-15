---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NavigationStartingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationStartingEventHandler
ms.openlocfilehash: aca4e1090356b2dec147485f0290e1d19869ec63
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879752"
---
# <span data-ttu-id="cbf95-104">インターフェイス ICoreWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="cbf95-104">interface ICoreWebView2NavigationStartingEventHandler</span></span> 

```
interface ICoreWebView2NavigationStartingEventHandler
  : public IUnknown
```

<span data-ttu-id="cbf95-105">呼び出し元は、NavigationStarting イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="cbf95-105">The caller implements this interface to receive the NavigationStarting event.</span></span>

## <span data-ttu-id="cbf95-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="cbf95-106">Summary</span></span>

 <span data-ttu-id="cbf95-107">Members</span><span class="sxs-lookup"><span data-stu-id="cbf95-107">Members</span></span>                        | <span data-ttu-id="cbf95-108">説明</span><span class="sxs-lookup"><span data-stu-id="cbf95-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cbf95-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="cbf95-109">Invoke</span></span>](#invoke) | <span data-ttu-id="cbf95-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbf95-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="cbf95-111">Members</span><span class="sxs-lookup"><span data-stu-id="cbf95-111">Members</span></span>

#### <span data-ttu-id="cbf95-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="cbf95-112">Invoke</span></span> 

<span data-ttu-id="cbf95-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cbf95-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="cbf95-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="cbf95-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span></span>

