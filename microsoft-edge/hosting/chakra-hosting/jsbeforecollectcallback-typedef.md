---
description: Collection の前に呼び出されたコールバック。
title: JsBeforeCollectCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 17f279c2d2ffcc8d02819994dddebfc22baa4cab
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569400"
---
# <span data-ttu-id="b081f-103">JsBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="b081f-103">JsBeforeCollectCallback Typedef</span></span>
<span data-ttu-id="b081f-104">Collection の前に呼び出されたコールバック。</span><span class="sxs-lookup"><span data-stu-id="b081f-104">A callback called before collection.</span></span>  
  
## <span data-ttu-id="b081f-105">構文</span><span class="sxs-lookup"><span data-stu-id="b081f-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsBeforeCollectCallback)(  
_In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="b081f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b081f-106">Parameters</span></span>  
 <span data-ttu-id="b081f-107">/ステータス</span><span class="sxs-lookup"><span data-stu-id="b081f-107">callbackState</span></span>  
 <span data-ttu-id="b081f-108">JsSetBeforeCollectCallback に渡される状態。</span><span class="sxs-lookup"><span data-stu-id="b081f-108">The state passed to JsSetBeforeCollectCallback.</span></span>  
  
## <span data-ttu-id="b081f-109">注釈</span><span class="sxs-lookup"><span data-stu-id="b081f-109">Remarks</span></span>  
 <span data-ttu-id="b081f-110">このコールバックを登録するには、JsSetBeforeCollectCallback を使用します。</span><span class="sxs-lookup"><span data-stu-id="b081f-110">Use JsSetBeforeCollectCallback to register this callback.</span></span>  
  
## <span data-ttu-id="b081f-111">要件</span><span class="sxs-lookup"><span data-stu-id="b081f-111">Requirements</span></span>  
 <span data-ttu-id="b081f-112">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="b081f-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b081f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b081f-113">See Also</span></span>  
 [<span data-ttu-id="b081f-114">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b081f-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)