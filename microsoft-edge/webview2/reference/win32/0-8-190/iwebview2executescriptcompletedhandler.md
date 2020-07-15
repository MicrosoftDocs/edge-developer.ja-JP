---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2ExecuteScriptCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: ecd3215c343925614b81d5da96fbf996350fd5a5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878506"
---
# <span data-ttu-id="68859-104">0.8.355-インターフェイス IWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="68859-104">0.8.355 - interface IWebView2ExecuteScriptCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="68859-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68859-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="68859-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68859-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="68859-107">呼び出し元は、このインターフェイスを実装して、ExecuteScript メソッドの結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="68859-107">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="68859-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="68859-108">Summary</span></span>

 <span data-ttu-id="68859-109">Members</span><span class="sxs-lookup"><span data-stu-id="68859-109">Members</span></span>                        | <span data-ttu-id="68859-110">説明</span><span class="sxs-lookup"><span data-stu-id="68859-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="68859-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="68859-111">Invoke</span></span>](#invoke) | <span data-ttu-id="68859-112">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="68859-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="68859-113">Members</span><span class="sxs-lookup"><span data-stu-id="68859-113">Members</span></span>

#### <span data-ttu-id="68859-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="68859-114">Invoke</span></span> 

<span data-ttu-id="68859-115">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="68859-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="68859-116">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR resultObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="68859-116">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR resultObjectAsJson)</span></span>

