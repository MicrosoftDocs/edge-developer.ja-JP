---
description: プロジェクション API が元のスレッドとは異なるスレッドで完了すると JsRT によって呼び出されるアプリケーション コールバック。
title: JsProjectionEnqueueCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 47527d5e32076e40a82ab5452c2e0f624e8a2818
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235090"
---
# <span data-ttu-id="92ff0-103">JsProjectionEnqueueCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="92ff0-103">JsProjectionEnqueueCallback Typedef</span></span>

<span data-ttu-id="92ff0-104">プロジェクション API が元のスレッドとは異なるスレッドで完了すると JsRT によって呼び出されるアプリケーション コールバック。</span><span class="sxs-lookup"><span data-stu-id="92ff0-104">The application callback which is called by JsRT when a projection API is completed on a different thread than the original.</span></span>  
  
## <span data-ttu-id="92ff0-105">構文</span><span class="sxs-lookup"><span data-stu-id="92ff0-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="92ff0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92ff0-106">Parameters</span></span>  
 `jsCallback`  
 <span data-ttu-id="92ff0-107">元のスレッドで呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="92ff0-107">The callback to be invoked on the original thread.</span></span>  
  
 `jsContext`  
 <span data-ttu-id="92ff0-108">アプリケーション コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="92ff0-108">The applications context.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="92ff0-109">に渡す必要がある JsRT コンテキスト `jsCallback` 。</span><span class="sxs-lookup"><span data-stu-id="92ff0-109">The JsRT context that must be passed into `jsCallback`.</span></span>  
  
## <span data-ttu-id="92ff0-110">注釈</span><span class="sxs-lookup"><span data-stu-id="92ff0-110">Remarks</span></span>  
 <span data-ttu-id="92ff0-111">コールバックを受信するには、JsSetProjectionEnqueueCallback を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92ff0-111">Requires calling JsSetProjectionEnqueueCallback to receive callbacks.</span></span>  
  
 <span data-ttu-id="92ff0-112">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="92ff0-112">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="92ff0-113">要件</span><span class="sxs-lookup"><span data-stu-id="92ff0-113">Requirements</span></span>  
 <span data-ttu-id="92ff0-114">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="92ff0-114">jsrt.h</span></span>  
  
## <span data-ttu-id="92ff0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="92ff0-115">See Also</span></span>  
 [<span data-ttu-id="92ff0-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="92ff0-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
