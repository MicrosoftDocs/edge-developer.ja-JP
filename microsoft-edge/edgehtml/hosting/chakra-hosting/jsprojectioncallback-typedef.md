---
description: 正しいスレッドで渡されたコンテキストで呼び出す必要がある JsRT `JsProjectionEnqueueCallback` コールバック。
title: JsProjectionCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 211325b536dc84340974b02973f1de9d5749a60a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234855"
---
# <span data-ttu-id="37016-103">JsProjectionCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="37016-103">JsProjectionCallback Typedef</span></span>

<span data-ttu-id="37016-104">正しいスレッドで渡されたコンテキストで呼び出す必要がある JsRT `JsProjectionEnqueueCallback` コールバック。</span><span class="sxs-lookup"><span data-stu-id="37016-104">The JsRT callback which should be called with the context passed to `JsProjectionEnqueueCallback` on the correct thread.</span></span>  
  
## <span data-ttu-id="37016-105">構文</span><span class="sxs-lookup"><span data-stu-id="37016-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### <span data-ttu-id="37016-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37016-106">Parameters</span></span>  
 `jsContext`  
 <span data-ttu-id="37016-107">コールバックを受 `JsSetProjectionEnqueueCallback` け取る呼び出しが必要です。</span><span class="sxs-lookup"><span data-stu-id="37016-107">Requires calling `JsSetProjectionEnqueueCallback` to receive callbacks.</span></span>  
  
## <span data-ttu-id="37016-108">注釈</span><span class="sxs-lookup"><span data-stu-id="37016-108">Remarks</span></span>  
 <span data-ttu-id="37016-109">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="37016-109">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="37016-110">要件</span><span class="sxs-lookup"><span data-stu-id="37016-110">Requirements</span></span>  
 <span data-ttu-id="37016-111">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="37016-111">jsrt.h</span></span>  
  
## <span data-ttu-id="37016-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="37016-112">See Also</span></span>  
 [<span data-ttu-id="37016-113">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="37016-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
