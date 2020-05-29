---
description: オブジェクトを収集する前に呼び出されるコールバック。
title: JsObjectBeforeCollectCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 27bbd1aed72cc751397ac4e6734f107612653b66
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569281"
---
# <span data-ttu-id="98996-103">JsObjectBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="98996-103">JsObjectBeforeCollectCallback Typedef</span></span>
<span data-ttu-id="98996-104">オブジェクトを収集する前に呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="98996-104">A callback called before collecting an object.</span></span>  
  
## <span data-ttu-id="98996-105">構文</span><span class="sxs-lookup"><span data-stu-id="98996-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="98996-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98996-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="98996-107">収集されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="98996-107">The object to be collected.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="98996-108">渡された状態 `JsSetObjectBeforeCollectCallback` 。</span><span class="sxs-lookup"><span data-stu-id="98996-108">The state passed to `JsSetObjectBeforeCollectCallback`.</span></span>  
  
## <span data-ttu-id="98996-109">注釈</span><span class="sxs-lookup"><span data-stu-id="98996-109">Remarks</span></span>  
 <span data-ttu-id="98996-110">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="98996-110">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="98996-111">要件</span><span class="sxs-lookup"><span data-stu-id="98996-111">Requirements</span></span>  
 <span data-ttu-id="98996-112">jsrt</span><span class="sxs-lookup"><span data-stu-id="98996-112">jsrt.h</span></span>  
  
## <span data-ttu-id="98996-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="98996-113">See Also</span></span>  
 [<span data-ttu-id="98996-114">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="98996-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)