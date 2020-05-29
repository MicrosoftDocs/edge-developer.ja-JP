---
description: JsRT からアプリケーションコールバックの JsProjectionEnqueueCallback に渡されたコンテキストが、指定されたコールバックで JsRT に渡された場合は、 `JsProjectionCallback` 正しいスレッド上のアプリケーションによって返されます。
title: JsProjectionCallbackContext Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 58d4c74da13ae0dd269f3c101bbf3d2b95e77732
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569279"
---
# <span data-ttu-id="57567-103">JsProjectionCallbackContext Typedef</span><span class="sxs-lookup"><span data-stu-id="57567-103">JsProjectionCallbackContext Typedef</span></span>
<span data-ttu-id="57567-104">JsRT からアプリケーションコールバックの JsProjectionEnqueueCallback に渡されたコンテキストが、指定されたコールバックで JsRT に渡された場合は、 `JsProjectionCallback` 正しいスレッド上のアプリケーションによって返されます。</span><span class="sxs-lookup"><span data-stu-id="57567-104">The context passed into application callback, JsProjectionEnqueueCallback, from JsRT and then passed back to JsRT in the provided callback, `JsProjectionCallback`, by the application on the correct thread.</span></span>  
  
## <span data-ttu-id="57567-105">構文</span><span class="sxs-lookup"><span data-stu-id="57567-105">Syntax</span></span>  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## <span data-ttu-id="57567-106">注釈</span><span class="sxs-lookup"><span data-stu-id="57567-106">Remarks</span></span>  
 <span data-ttu-id="57567-107">`JsSetProjectionEnqueueCallback`コールバックを受け取るには、呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="57567-107">Requires calling `JsSetProjectionEnqueueCallback` to receive callbacks.</span></span>  
  
 <span data-ttu-id="57567-108">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="57567-108">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="57567-109">要件</span><span class="sxs-lookup"><span data-stu-id="57567-109">Requirements</span></span>  
 <span data-ttu-id="57567-110">jsrt</span><span class="sxs-lookup"><span data-stu-id="57567-110">jsrt.h</span></span>  
  
## <span data-ttu-id="57567-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="57567-111">See Also</span></span>  
 [<span data-ttu-id="57567-112">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="57567-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)