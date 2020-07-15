---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2CreateWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: fe81be15531cedae7a01355cbb6b6b27b52f15cc
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878632"
---
# <span data-ttu-id="e1821-104">0.8.355-インターフェイス IWebView2CreateWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="e1821-104">0.8.355 - interface IWebView2CreateWebView2EnvironmentCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="e1821-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1821-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="e1821-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1821-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CreateWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="e1821-107">呼び出し元はこのインターフェイスを実装して、CreateWebView2Environment 経由で作成された WebView2Environment を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e1821-107">The caller implements this interface to receive the WebView2Environment created via CreateWebView2Environment.</span></span>

## <span data-ttu-id="e1821-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="e1821-108">Summary</span></span>

 <span data-ttu-id="e1821-109">Members</span><span class="sxs-lookup"><span data-stu-id="e1821-109">Members</span></span>                        | <span data-ttu-id="e1821-110">説明</span><span class="sxs-lookup"><span data-stu-id="e1821-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e1821-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="e1821-111">Invoke</span></span>](#invoke) | <span data-ttu-id="e1821-112">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e1821-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="e1821-113">Members</span><span class="sxs-lookup"><span data-stu-id="e1821-113">Members</span></span>

#### <span data-ttu-id="e1821-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="e1821-114">Invoke</span></span> 

<span data-ttu-id="e1821-115">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e1821-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="e1821-116">パブリック HRESULT[呼び出し](#invoke)(hresult Result,[IWebView2Environment](IWebView2Environment.md) \* webviewenvironment)</span><span class="sxs-lookup"><span data-stu-id="e1821-116">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2Environment](IWebView2Environment.md) \* webViewEnvironment)</span></span>

