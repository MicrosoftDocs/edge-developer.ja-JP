---
description: フルガベージコレクションを実行します。
title: JsCollectGarbage 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCollectGarbage
helpviewer_keywords:
- JsCollectGarbage function
ms.assetid: 995c79a5-6e18-45be-81ff-2a5d3348edb8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1702ad960a0a2f366e97b8a994abd0700cec50e7
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569393"
---
# <span data-ttu-id="f8e3e-103">JsCollectGarbage 関数</span><span class="sxs-lookup"><span data-stu-id="f8e3e-103">JsCollectGarbage Function</span></span>
<span data-ttu-id="f8e3e-104">フルガベージコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-104">Performs a full garbage collection.</span></span>  
  
## <span data-ttu-id="f8e3e-105">構文</span><span class="sxs-lookup"><span data-stu-id="f8e3e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCollectGarbage(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="f8e3e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8e3e-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="f8e3e-107">ガベージコレクションが実行されるランタイム。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-107">The runtime in which the garbage collection will be performed.</span></span>  
  
## <span data-ttu-id="f8e3e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f8e3e-108">Return Value</span></span>  
 <span data-ttu-id="f8e3e-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="f8e3e-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f8e3e-110">要件</span><span class="sxs-lookup"><span data-stu-id="f8e3e-110">Requirements</span></span>  
 <span data-ttu-id="f8e3e-111">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="f8e3e-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f8e3e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8e3e-112">See Also</span></span>  
 [<span data-ttu-id="f8e3e-113">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="f8e3e-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)