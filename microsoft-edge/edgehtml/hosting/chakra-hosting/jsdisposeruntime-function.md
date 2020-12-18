---
description: ランタイムを破棄します。
title: JsDisposeRuntime 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDisposeRuntime
helpviewer_keywords:
- JsDisposeRuntime function
ms.assetid: 0aefde3f-7250-48be-afc5-53ea85c12f30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8cff4578415cdf1aaa01b7203ce734cef9115301
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234730"
---
# <span data-ttu-id="84029-103">JsDisposeRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="84029-103">JsDisposeRuntime Function</span></span>

<span data-ttu-id="84029-104">ランタイムを破棄します。</span><span class="sxs-lookup"><span data-stu-id="84029-104">Disposes a runtime.</span></span>  
  
## <span data-ttu-id="84029-105">構文</span><span class="sxs-lookup"><span data-stu-id="84029-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDisposeRuntime(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="84029-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84029-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="84029-107">破棄するランタイム。</span><span class="sxs-lookup"><span data-stu-id="84029-107">The runtime to dispose.</span></span>  
  
## <span data-ttu-id="84029-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="84029-108">Return Value</span></span>  
 <span data-ttu-id="84029-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="84029-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="84029-110">注釈</span><span class="sxs-lookup"><span data-stu-id="84029-110">Remarks</span></span>  
 <span data-ttu-id="84029-111">ランタイムが破棄された後は、そのランタイムによって所有されているリソースはすべて無効であり、使用できません。</span><span class="sxs-lookup"><span data-stu-id="84029-111">Once a runtime has been disposed, all resources owned by it are invalid and cannot be used.</span></span> <span data-ttu-id="84029-112">ランタイムがアクティブな場合 (つまり、特定のスレッドで現在の状態に設定されている場合)、ランタイムを破棄することはできません。</span><span class="sxs-lookup"><span data-stu-id="84029-112">If the runtime is active (i.e. it is set to be current on a particular thread), it cannot be disposed.</span></span>  
  
## <span data-ttu-id="84029-113">要件</span><span class="sxs-lookup"><span data-stu-id="84029-113">Requirements</span></span>  
 <span data-ttu-id="84029-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="84029-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="84029-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="84029-115">See Also</span></span>  
 [<span data-ttu-id="84029-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="84029-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
