---
description: 割り当てのコールバックイベントの種類。
title: JsMemoryEventType 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e9833777ed8fe5a19fd2a1487715296279f7351
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569286"
---
# <span data-ttu-id="9ed4d-103">JsMemoryEventType 列挙</span><span class="sxs-lookup"><span data-stu-id="9ed4d-103">JsMemoryEventType Enumeration</span></span>
<span data-ttu-id="9ed4d-104">割り当てのコールバックイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="9ed4d-104">Allocation callback event type.</span></span>  
  
## <span data-ttu-id="9ed4d-105">構文</span><span class="sxs-lookup"><span data-stu-id="9ed4d-105">Syntax</span></span>  
  
```cpp  
enum JsMemoryEventType;  
```  
  
## <span data-ttu-id="9ed4d-106">Members</span><span class="sxs-lookup"><span data-stu-id="9ed4d-106">Members</span></span>  
  
### <span data-ttu-id="9ed4d-107">値</span><span class="sxs-lookup"><span data-stu-id="9ed4d-107">Values</span></span>  
  
|<span data-ttu-id="9ed4d-108">名前</span><span class="sxs-lookup"><span data-stu-id="9ed4d-108">Name</span></span>|<span data-ttu-id="9ed4d-109">説明</span><span class="sxs-lookup"><span data-stu-id="9ed4d-109">Description</span></span>|  
|----------|-----------------|  
|`JsMemoryAllocate`|<span data-ttu-id="9ed4d-110">メモリの割り当て要求を示します。</span><span class="sxs-lookup"><span data-stu-id="9ed4d-110">Indicates a request for memory allocation.</span></span>|  
|`JsMemoryFailure`|<span data-ttu-id="9ed4d-111">失敗した割り当てイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="9ed4d-111">Indicates a failed allocation event.</span></span>|  
|`JsMemoryFree`|<span data-ttu-id="9ed4d-112">メモリ解放イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="9ed4d-112">Indicates a memory freeing event.</span></span>|  
  
## <span data-ttu-id="9ed4d-113">要件</span><span class="sxs-lookup"><span data-stu-id="9ed4d-113">Requirements</span></span>  
 <span data-ttu-id="9ed4d-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="9ed4d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9ed4d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ed4d-115">See Also</span></span>  
 [<span data-ttu-id="9ed4d-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9ed4d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)