---
description: コレクションの前に呼び出されるコールバック。
title: JsBeforeCollectCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 23ed386a6a28d356aa80cf85650a981d4836a6b6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234549"
---
# <span data-ttu-id="8c3e9-103">JsBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="8c3e9-103">JsBeforeCollectCallback Typedef</span></span>

<span data-ttu-id="8c3e9-104">コレクションの前に呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="8c3e9-104">A callback called before collection.</span></span>  
  
## <span data-ttu-id="8c3e9-105">構文</span><span class="sxs-lookup"><span data-stu-id="8c3e9-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsBeforeCollectCallback)(  
_In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="8c3e9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c3e9-106">Parameters</span></span>  
 <span data-ttu-id="8c3e9-107">callbackState</span><span class="sxs-lookup"><span data-stu-id="8c3e9-107">callbackState</span></span>  
 <span data-ttu-id="8c3e9-108">JsSetBeforeCollectCallback に渡された状態。</span><span class="sxs-lookup"><span data-stu-id="8c3e9-108">The state passed to JsSetBeforeCollectCallback.</span></span>  
  
## <span data-ttu-id="8c3e9-109">注釈</span><span class="sxs-lookup"><span data-stu-id="8c3e9-109">Remarks</span></span>  
 <span data-ttu-id="8c3e9-110">JsSetBeforeCollectCallback を使用して、このコールバックを登録します。</span><span class="sxs-lookup"><span data-stu-id="8c3e9-110">Use JsSetBeforeCollectCallback to register this callback.</span></span>  
  
## <span data-ttu-id="8c3e9-111">要件</span><span class="sxs-lookup"><span data-stu-id="8c3e9-111">Requirements</span></span>  
 <span data-ttu-id="8c3e9-112">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="8c3e9-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8c3e9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c3e9-113">See Also</span></span>  
 [<span data-ttu-id="8c3e9-114">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="8c3e9-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
