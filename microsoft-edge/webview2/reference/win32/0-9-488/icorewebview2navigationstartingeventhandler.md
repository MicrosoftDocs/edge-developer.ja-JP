---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2NavigationStartingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 6ec01c2b66c625c9961384b5c2ef04a8820a29e9
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880480"
---
# <span data-ttu-id="93449-104">0.9.515-インターフェイス ICoreWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="93449-104">0.9.515 - interface ICoreWebView2NavigationStartingEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="93449-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93449-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="93449-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93449-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationStartingEventHandler
  : public IUnknown
```

<span data-ttu-id="93449-107">呼び出し元は、NavigationStarting イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="93449-107">The caller implements this interface to receive the NavigationStarting event.</span></span>

## <span data-ttu-id="93449-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="93449-108">Summary</span></span>

 <span data-ttu-id="93449-109">Members</span><span class="sxs-lookup"><span data-stu-id="93449-109">Members</span></span>                        | <span data-ttu-id="93449-110">説明</span><span class="sxs-lookup"><span data-stu-id="93449-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="93449-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="93449-111">Invoke</span></span>](#invoke) | <span data-ttu-id="93449-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="93449-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="93449-113">Members</span><span class="sxs-lookup"><span data-stu-id="93449-113">Members</span></span>

#### <span data-ttu-id="93449-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="93449-114">Invoke</span></span> 

<span data-ttu-id="93449-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="93449-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="93449-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="93449-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span></span>

