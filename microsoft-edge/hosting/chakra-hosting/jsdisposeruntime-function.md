---
description: ランタイムを破棄します。
title: JsDisposeRuntime 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDisposeRuntime
helpviewer_keywords:
- JsDisposeRuntime function
ms.assetid: 0aefde3f-7250-48be-afc5-53ea85c12f30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 89166249616c265ce75ebc43a01c838d607bdd08
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570475"
---
# <span data-ttu-id="ed8d6-103">JsDisposeRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="ed8d6-103">JsDisposeRuntime Function</span></span>
<span data-ttu-id="ed8d6-104">ランタイムを破棄します。</span><span class="sxs-lookup"><span data-stu-id="ed8d6-104">Disposes a runtime.</span></span>  
  
## <span data-ttu-id="ed8d6-105">構文</span><span class="sxs-lookup"><span data-stu-id="ed8d6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDisposeRuntime(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="ed8d6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed8d6-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="ed8d6-107">破棄するランタイム。</span><span class="sxs-lookup"><span data-stu-id="ed8d6-107">The runtime to dispose.</span></span>  
  
## <span data-ttu-id="ed8d6-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ed8d6-108">Return Value</span></span>  
 <span data-ttu-id="ed8d6-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="ed8d6-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ed8d6-110">注釈</span><span class="sxs-lookup"><span data-stu-id="ed8d6-110">Remarks</span></span>  
 <span data-ttu-id="ed8d6-111">ランタイムが破棄されると、そのランタイムが所有するすべてのリソースが無効になり、使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ed8d6-111">Once a runtime has been disposed, all resources owned by it are invalid and cannot be used.</span></span> <span data-ttu-id="ed8d6-112">ランタイムがアクティブな場合 (つまり、特定のスレッドで現在の状態に設定されている場合)、破棄することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed8d6-112">If the runtime is active (i.e. it is set to be current on a particular thread), it cannot be disposed.</span></span>  
  
## <span data-ttu-id="ed8d6-113">要件</span><span class="sxs-lookup"><span data-stu-id="ed8d6-113">Requirements</span></span>  
 <span data-ttu-id="ed8d6-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="ed8d6-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ed8d6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed8d6-115">See Also</span></span>  
 [<span data-ttu-id="ed8d6-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ed8d6-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)