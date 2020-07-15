---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceRequestedEventArgs2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 80ea596f28d1afeb451ce20d495961ca4eed507a
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878114"
---
# <span data-ttu-id="200c3-104">0.8.355-インターフェイス IWebView2WebResourceRequestedEventArgs2</span><span class="sxs-lookup"><span data-stu-id="200c3-104">0.8.355 - interface IWebView2WebResourceRequestedEventArgs2</span></span> 

> [!NOTE]
> <span data-ttu-id="200c3-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="200c3-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="200c3-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="200c3-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequestedEventArgs2
  : public IWebView2WebResourceRequestedEventArgs
```

<span data-ttu-id="200c3-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="200c3-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="200c3-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="200c3-108">Summary</span></span>

 <span data-ttu-id="200c3-109">Members</span><span class="sxs-lookup"><span data-stu-id="200c3-109">Members</span></span>                        | <span data-ttu-id="200c3-110">説明</span><span class="sxs-lookup"><span data-stu-id="200c3-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="200c3-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="200c3-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="200c3-112">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="200c3-112">The web resource request contexts.</span></span>

## <span data-ttu-id="200c3-113">Members</span><span class="sxs-lookup"><span data-stu-id="200c3-113">Members</span></span>

#### <span data-ttu-id="200c3-114">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="200c3-114">get_ResourceContext</span></span> 

<span data-ttu-id="200c3-115">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="200c3-115">The web resource request contexts.</span></span>

> <span data-ttu-id="200c3-116">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="200c3-116">public HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

