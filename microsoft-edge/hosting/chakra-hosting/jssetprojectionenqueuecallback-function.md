---
description: 呼び出し元の要求されたスレッドへのプロジェクション完了を呼び出すために使用されるコールバックを設定します。
title: JsSetProjectionEnqueueCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 02da0238360b0dc6fff9bb86c9f5ab04d1ba7112
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570369"
---
# <span data-ttu-id="700ef-103">JsSetProjectionEnqueueCallback 関数</span><span class="sxs-lookup"><span data-stu-id="700ef-103">JsSetProjectionEnqueueCallback Function</span></span>
<span data-ttu-id="700ef-104">呼び出し元の要求されたスレッドへのプロジェクション完了を呼び出すために使用されるコールバックを設定します。</span><span class="sxs-lookup"><span data-stu-id="700ef-104">Sets the callback to be used in order to invoke a projection completion back to the callers required thread.</span></span>  
  
## <span data-ttu-id="700ef-105">構文</span><span class="sxs-lookup"><span data-stu-id="700ef-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### <span data-ttu-id="700ef-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="700ef-106">Parameters</span></span>  
 `projectionEnqueueContext`  
 <span data-ttu-id="700ef-107">バックグラウンドスレッドでプロジェクションの完了が発生するたびに呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="700ef-107">The callback that will be invoked any time a projection completion occurs on a background thread.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="700ef-108">提供されるアプリケーションコンテキスト `projectionEnqueueContext` 。</span><span class="sxs-lookup"><span data-stu-id="700ef-108">The application context provided to `projectionEnqueueContext`.</span></span>  
  
## <span data-ttu-id="700ef-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="700ef-109">Return Value</span></span>  
 <span data-ttu-id="700ef-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="700ef-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="700ef-111">注釈</span><span class="sxs-lookup"><span data-stu-id="700ef-111">Remarks</span></span>  
 <span data-ttu-id="700ef-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="700ef-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="700ef-113">呼び出しは、別の COM アパートメントから、または同じ MTA 内の別のスレッドから行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="700ef-113">The call should be coming from a different COM apartment or from a different thread in the same MTA.</span></span>  
  
 <span data-ttu-id="700ef-114">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="700ef-114">This API is supported only in EdgeHTML mode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="700ef-115">PInvoke は、この API では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="700ef-115">PInvoke is not currently supported for this API.</span></span>  
  
## <span data-ttu-id="700ef-116">要件</span><span class="sxs-lookup"><span data-stu-id="700ef-116">Requirements</span></span>  
 <span data-ttu-id="700ef-117">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="700ef-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="700ef-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="700ef-118">See Also</span></span>  
 [<span data-ttu-id="700ef-119">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="700ef-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)