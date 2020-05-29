---
description: プロジェクション API が元のスレッドとは別のスレッドで完了したときに、JsRT によって呼び出されるアプリケーションコールバック。
title: JsProjectionEnqueueCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 064a7d1077ae5222e44ab08ebe0592bb97b1f2af
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569277"
---
# <span data-ttu-id="3207c-103">JsProjectionEnqueueCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="3207c-103">JsProjectionEnqueueCallback Typedef</span></span>
<span data-ttu-id="3207c-104">プロジェクション API が元のスレッドとは別のスレッドで完了したときに、JsRT によって呼び出されるアプリケーションコールバック。</span><span class="sxs-lookup"><span data-stu-id="3207c-104">The application callback which is called by JsRT when a projection API is completed on a different thread than the original.</span></span>  
  
## <span data-ttu-id="3207c-105">構文</span><span class="sxs-lookup"><span data-stu-id="3207c-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="3207c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3207c-106">Parameters</span></span>  
 `jsCallback`  
 <span data-ttu-id="3207c-107">元のスレッドで呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="3207c-107">The callback to be invoked on the original thread.</span></span>  
  
 `jsContext`  
 <span data-ttu-id="3207c-108">アプリケーションのコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="3207c-108">The applications context.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="3207c-109">JsRT コンテキストを渡す必要があり `jsCallback` ます。</span><span class="sxs-lookup"><span data-stu-id="3207c-109">The JsRT context that must be passed into `jsCallback`.</span></span>  
  
## <span data-ttu-id="3207c-110">注釈</span><span class="sxs-lookup"><span data-stu-id="3207c-110">Remarks</span></span>  
 <span data-ttu-id="3207c-111">コールバックを受け取るには、JsSetProjectionEnqueueCallback を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3207c-111">Requires calling JsSetProjectionEnqueueCallback to receive callbacks.</span></span>  
  
 <span data-ttu-id="3207c-112">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3207c-112">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="3207c-113">要件</span><span class="sxs-lookup"><span data-stu-id="3207c-113">Requirements</span></span>  
 <span data-ttu-id="3207c-114">jsrt</span><span class="sxs-lookup"><span data-stu-id="3207c-114">jsrt.h</span></span>  
  
## <span data-ttu-id="3207c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3207c-115">See Also</span></span>  
 [<span data-ttu-id="3207c-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="3207c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)