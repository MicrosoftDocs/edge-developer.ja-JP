---
description: 適切なスレッドで渡されたコンテキストで呼び出される JsRT callback `JsProjectionEnqueueCallback` 。
title: JsProjectionCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b30f9a7dc4671896eeacecbf58ef88f0383e9e7e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569278"
---
# <span data-ttu-id="fa53f-103">JsProjectionCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fa53f-103">JsProjectionCallback Typedef</span></span>
<span data-ttu-id="fa53f-104">適切なスレッドで渡されたコンテキストで呼び出される JsRT callback `JsProjectionEnqueueCallback` 。</span><span class="sxs-lookup"><span data-stu-id="fa53f-104">The JsRT callback which should be called with the context passed to `JsProjectionEnqueueCallback` on the correct thread.</span></span>  
  
## <span data-ttu-id="fa53f-105">構文</span><span class="sxs-lookup"><span data-stu-id="fa53f-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### <span data-ttu-id="fa53f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa53f-106">Parameters</span></span>  
 `jsContext`  
 <span data-ttu-id="fa53f-107">`JsSetProjectionEnqueueCallback`コールバックを受け取るには、呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa53f-107">Requires calling `JsSetProjectionEnqueueCallback` to receive callbacks.</span></span>  
  
## <span data-ttu-id="fa53f-108">注釈</span><span class="sxs-lookup"><span data-stu-id="fa53f-108">Remarks</span></span>  
 <span data-ttu-id="fa53f-109">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="fa53f-109">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="fa53f-110">要件</span><span class="sxs-lookup"><span data-stu-id="fa53f-110">Requirements</span></span>  
 <span data-ttu-id="fa53f-111">jsrt</span><span class="sxs-lookup"><span data-stu-id="fa53f-111">jsrt.h</span></span>  
  
## <span data-ttu-id="fa53f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa53f-112">See Also</span></span>  
 [<span data-ttu-id="fa53f-113">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="fa53f-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)