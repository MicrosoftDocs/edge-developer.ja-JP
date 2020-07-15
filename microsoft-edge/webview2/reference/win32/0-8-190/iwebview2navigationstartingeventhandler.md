---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NavigationStartingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 14fe3e2260412a861ef07726309ed4df29f2a60b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878373"
---
# <span data-ttu-id="e0f8a-104">0.8.355-インターフェイス IWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="e0f8a-104">0.8.355 - interface IWebView2NavigationStartingEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="e0f8a-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0f8a-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="e0f8a-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f8a-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NavigationStartingEventHandler
  : public IUnknown
```

<span data-ttu-id="e0f8a-107">呼び出し元は、NavigationStarting イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e0f8a-107">The caller implements this interface to receive the NavigationStarting event.</span></span>

## <span data-ttu-id="e0f8a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="e0f8a-108">Summary</span></span>

 <span data-ttu-id="e0f8a-109">Members</span><span class="sxs-lookup"><span data-stu-id="e0f8a-109">Members</span></span>                        | <span data-ttu-id="e0f8a-110">説明</span><span class="sxs-lookup"><span data-stu-id="e0f8a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e0f8a-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="e0f8a-111">Invoke</span></span>](#invoke) | <span data-ttu-id="e0f8a-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0f8a-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="e0f8a-113">Members</span><span class="sxs-lookup"><span data-stu-id="e0f8a-113">Members</span></span>

#### <span data-ttu-id="e0f8a-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="e0f8a-114">Invoke</span></span> 

<span data-ttu-id="e0f8a-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0f8a-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="e0f8a-116">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2NavigationStartingEventArgs](IWebView2NavigationStartingEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="e0f8a-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2NavigationStartingEventArgs](IWebView2NavigationStartingEventArgs.md) \* args)</span></span>

