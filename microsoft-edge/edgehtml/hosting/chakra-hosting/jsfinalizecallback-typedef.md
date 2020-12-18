---
description: 最終処理コールバック。
title: JsFinalizeCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: aa7a0269-b9d4-4717-97ac-8da7eb6ced15
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 794edbb3a61c8c213c0908740ed0a867488a2c6d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234659"
---
# <span data-ttu-id="858ba-103">JsFinalizeCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="858ba-103">JsFinalizeCallback Typedef</span></span>

<span data-ttu-id="858ba-104">最終処理コールバック。</span><span class="sxs-lookup"><span data-stu-id="858ba-104">A finalizer callback.</span></span>  
  
## <span data-ttu-id="858ba-105">構文</span><span class="sxs-lookup"><span data-stu-id="858ba-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsFinalizeCallback)(  
   _In_opt_ void *data  
);  
```  
  
#### <span data-ttu-id="858ba-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="858ba-106">Parameters</span></span>  
 <span data-ttu-id="858ba-107">data</span><span class="sxs-lookup"><span data-stu-id="858ba-107">data</span></span>  
 <span data-ttu-id="858ba-108">最終処理されるオブジェクトの作成時に渡された外部データ。</span><span class="sxs-lookup"><span data-stu-id="858ba-108">The external data that was passed in when creating the object being finalized.</span></span>  
  
## <span data-ttu-id="858ba-109">要件</span><span class="sxs-lookup"><span data-stu-id="858ba-109">Requirements</span></span>  
 <span data-ttu-id="858ba-110">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="858ba-110">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="858ba-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="858ba-111">See Also</span></span>  
 [<span data-ttu-id="858ba-112">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="858ba-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
