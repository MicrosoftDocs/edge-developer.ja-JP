---
description: 呼び出し元に必要なスレッドにプロジェクション完了を呼び出す際に使用するコールバックを設定します。
title: JsSetProjectionEnqueueCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7dfedfeb1df5a97159a211795a2dd072d239bb35
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234509"
---
# <span data-ttu-id="a1bf1-103">JsSetProjectionEnqueueCallback 関数</span><span class="sxs-lookup"><span data-stu-id="a1bf1-103">JsSetProjectionEnqueueCallback Function</span></span>

<span data-ttu-id="a1bf1-104">呼び出し元に必要なスレッドにプロジェクション完了を呼び出す際に使用するコールバックを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1bf1-104">Sets the callback to be used in order to invoke a projection completion back to the callers required thread.</span></span>  
  
## <span data-ttu-id="a1bf1-105">構文</span><span class="sxs-lookup"><span data-stu-id="a1bf1-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### <span data-ttu-id="a1bf1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1bf1-106">Parameters</span></span>  
 `projectionEnqueueContext`  
 <span data-ttu-id="a1bf1-107">バックグラウンド スレッドでプロジェクション完了が発生するといつでも呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="a1bf1-107">The callback that will be invoked any time a projection completion occurs on a background thread.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="a1bf1-108">に提供されるアプリケーション コンテキスト `projectionEnqueueContext` 。</span><span class="sxs-lookup"><span data-stu-id="a1bf1-108">The application context provided to `projectionEnqueueContext`.</span></span>  
  
## <span data-ttu-id="a1bf1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1bf1-109">Return Value</span></span>  
 <span data-ttu-id="a1bf1-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="a1bf1-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a1bf1-111">注釈</span><span class="sxs-lookup"><span data-stu-id="a1bf1-111">Remarks</span></span>  
 <span data-ttu-id="a1bf1-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="a1bf1-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="a1bf1-113">呼び出しは、別の COM アパートメントまたは同じ MTA 内の別のスレッドから行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1bf1-113">The call should be coming from a different COM apartment or from a different thread in the same MTA.</span></span>  
  
 <span data-ttu-id="a1bf1-114">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a1bf1-114">This API is supported only in EdgeHTML mode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a1bf1-115">現在、PInvoke は、この API ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a1bf1-115">PInvoke is not currently supported for this API.</span></span>  
  
## <span data-ttu-id="a1bf1-116">要件</span><span class="sxs-lookup"><span data-stu-id="a1bf1-116">Requirements</span></span>  
 <span data-ttu-id="a1bf1-117">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="a1bf1-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a1bf1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1bf1-118">See Also</span></span>  
 [<span data-ttu-id="a1bf1-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="a1bf1-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
