---
description: 割り当てコールバック イベントの種類。
title: JsMemoryEventType 列挙 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a28010f908285098cf652b497b6d6c272bc763fc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234335"
---
# <span data-ttu-id="5e7d1-103">JsMemoryEventType 列挙</span><span class="sxs-lookup"><span data-stu-id="5e7d1-103">JsMemoryEventType Enumeration</span></span>

<span data-ttu-id="5e7d1-104">割り当てコールバック イベントの種類。</span><span class="sxs-lookup"><span data-stu-id="5e7d1-104">Allocation callback event type.</span></span>  
  
## <span data-ttu-id="5e7d1-105">構文</span><span class="sxs-lookup"><span data-stu-id="5e7d1-105">Syntax</span></span>  
  
```cpp  
enum JsMemoryEventType;  
```  
  
## <span data-ttu-id="5e7d1-106">Members</span><span class="sxs-lookup"><span data-stu-id="5e7d1-106">Members</span></span>  
  
### <span data-ttu-id="5e7d1-107">値</span><span class="sxs-lookup"><span data-stu-id="5e7d1-107">Values</span></span>  
  
|<span data-ttu-id="5e7d1-108">名前</span><span class="sxs-lookup"><span data-stu-id="5e7d1-108">Name</span></span>|<span data-ttu-id="5e7d1-109">説明</span><span class="sxs-lookup"><span data-stu-id="5e7d1-109">Description</span></span>|  
|----------|-----------------|  
|`JsMemoryAllocate`|<span data-ttu-id="5e7d1-110">メモリ割り当ての要求を示します。</span><span class="sxs-lookup"><span data-stu-id="5e7d1-110">Indicates a request for memory allocation.</span></span>|  
|`JsMemoryFailure`|<span data-ttu-id="5e7d1-111">失敗した割り当てイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="5e7d1-111">Indicates a failed allocation event.</span></span>|  
|`JsMemoryFree`|<span data-ttu-id="5e7d1-112">メモリ解放イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="5e7d1-112">Indicates a memory freeing event.</span></span>|  
  
## <span data-ttu-id="5e7d1-113">要件</span><span class="sxs-lookup"><span data-stu-id="5e7d1-113">Requirements</span></span>  
 <span data-ttu-id="5e7d1-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="5e7d1-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5e7d1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e7d1-115">See Also</span></span>  
 [<span data-ttu-id="5e7d1-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="5e7d1-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
