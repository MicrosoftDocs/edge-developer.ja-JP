---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 52218ddcbecdaf3bdb736af877493c85d4460c10
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878044"
---
# <span data-ttu-id="89bba-104">0.8.355-インターフェイス IWebView2WebView2</span><span class="sxs-lookup"><span data-stu-id="89bba-104">0.8.355 - interface IWebView2WebView2</span></span> 

> [!NOTE]
> <span data-ttu-id="89bba-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89bba-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="89bba-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89bba-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView2
  : public IUnknown
```

<span data-ttu-id="89bba-107">プライマリ WebView オブジェクトによって実装されるその他の機能。</span><span class="sxs-lookup"><span data-stu-id="89bba-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="89bba-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="89bba-108">Summary</span></span>

 <span data-ttu-id="89bba-109">Members</span><span class="sxs-lookup"><span data-stu-id="89bba-109">Members</span></span>                        | <span data-ttu-id="89bba-110">説明</span><span class="sxs-lookup"><span data-stu-id="89bba-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="89bba-111">Stop</span><span class="sxs-lookup"><span data-stu-id="89bba-111">Stop</span></span>](#stop) | <span data-ttu-id="89bba-112">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="89bba-112">Stop all navigations and pending resource fetches.</span></span>

<span data-ttu-id="89bba-113">このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="89bba-113">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="89bba-114">詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89bba-114">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="89bba-115">Members</span><span class="sxs-lookup"><span data-stu-id="89bba-115">Members</span></span>

#### <span data-ttu-id="89bba-116">Stop</span><span class="sxs-lookup"><span data-stu-id="89bba-116">Stop</span></span> 

<span data-ttu-id="89bba-117">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="89bba-117">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="89bba-118">パブリック HRESULT [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="89bba-118">public HRESULT [Stop](#stop)()</span></span>

