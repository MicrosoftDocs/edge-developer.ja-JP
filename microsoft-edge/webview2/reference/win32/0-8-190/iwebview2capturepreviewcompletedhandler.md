---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 9e8b1cc973eefbd41c1fac0d7d9723ba35ec7302
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878681"
---
# <span data-ttu-id="5eb9c-104">0.8.355-インターフェイス IWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="5eb9c-104">0.8.355 - interface IWebView2CapturePreviewCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="5eb9c-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5eb9c-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="5eb9c-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eb9c-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="5eb9c-107">呼び出し元は、このメソッドを実装して CapturePreview メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5eb9c-107">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="5eb9c-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="5eb9c-108">Summary</span></span>

 <span data-ttu-id="5eb9c-109">Members</span><span class="sxs-lookup"><span data-stu-id="5eb9c-109">Members</span></span>                        | <span data-ttu-id="5eb9c-110">説明</span><span class="sxs-lookup"><span data-stu-id="5eb9c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5eb9c-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="5eb9c-111">Invoke</span></span>](#invoke) | <span data-ttu-id="5eb9c-112">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5eb9c-112">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="5eb9c-113">結果は、CapturePreview メソッド呼び出しで提供されたストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5eb9c-113">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="5eb9c-114">Members</span><span class="sxs-lookup"><span data-stu-id="5eb9c-114">Members</span></span>

#### <span data-ttu-id="5eb9c-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="5eb9c-115">Invoke</span></span> 

<span data-ttu-id="5eb9c-116">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5eb9c-116">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="5eb9c-117">パブリック HRESULT[呼び出し](#invoke)(hresult 結果)</span><span class="sxs-lookup"><span data-stu-id="5eb9c-117">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

