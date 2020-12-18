---
description: JsRT からアプリケーション コールバック JsProjectionEnqueueCallback に渡されたコンテキストは、適切なスレッド上のアプリケーションによって、提供されたコールバックで JsRT に戻されます `JsProjectionCallback` 。
title: JsProjectionCallbackContext Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7742b0186a49e99f2738b81357b9e55cfe00042b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234851"
---
# <span data-ttu-id="72018-103">JsProjectionCallbackContext Typedef</span><span class="sxs-lookup"><span data-stu-id="72018-103">JsProjectionCallbackContext Typedef</span></span>

<span data-ttu-id="72018-104">JsRT からアプリケーション コールバック JsProjectionEnqueueCallback に渡されたコンテキストは、適切なスレッド上のアプリケーションによって、提供されたコールバックで JsRT に戻されます `JsProjectionCallback` 。</span><span class="sxs-lookup"><span data-stu-id="72018-104">The context passed into application callback, JsProjectionEnqueueCallback, from JsRT and then passed back to JsRT in the provided callback, `JsProjectionCallback`, by the application on the correct thread.</span></span>  
  
## <span data-ttu-id="72018-105">構文</span><span class="sxs-lookup"><span data-stu-id="72018-105">Syntax</span></span>  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## <span data-ttu-id="72018-106">注釈</span><span class="sxs-lookup"><span data-stu-id="72018-106">Remarks</span></span>  
 <span data-ttu-id="72018-107">コールバックを受 `JsSetProjectionEnqueueCallback` け取る呼び出しが必要です。</span><span class="sxs-lookup"><span data-stu-id="72018-107">Requires calling `JsSetProjectionEnqueueCallback` to receive callbacks.</span></span>  
  
 <span data-ttu-id="72018-108">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="72018-108">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="72018-109">要件</span><span class="sxs-lookup"><span data-stu-id="72018-109">Requirements</span></span>  
 <span data-ttu-id="72018-110">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="72018-110">jsrt.h</span></span>  
  
## <span data-ttu-id="72018-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="72018-111">See Also</span></span>  
 [<span data-ttu-id="72018-112">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="72018-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
