---
description: コンテキストが属するランタイムを取得します。
title: JsGetRuntime 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntime
helpviewer_keywords:
- JsGetRuntime function
ms.assetid: 5b62e940-a885-405a-9fdd-0495fb391b95
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 49739f0cf3675a44b9fc328e3eaa7d49c6282e53
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234741"
---
# <span data-ttu-id="142d4-103">JsGetRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="142d4-103">JsGetRuntime Function</span></span>

<span data-ttu-id="142d4-104">コンテキストが属するランタイムを取得します。</span><span class="sxs-lookup"><span data-stu-id="142d4-104">Gets the runtime that the context belongs to.</span></span>  
  
## <span data-ttu-id="142d4-105">構文</span><span class="sxs-lookup"><span data-stu-id="142d4-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntime(  
   _In_ JsContextRef context,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### <span data-ttu-id="142d4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="142d4-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="142d4-107">ランタイムを取得するコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="142d4-107">The context to get the runtime from.</span></span>  
  
 `runtime`  
 <span data-ttu-id="142d4-108">コンテキストが属するランタイム。</span><span class="sxs-lookup"><span data-stu-id="142d4-108">The runtime the context belongs to.</span></span>  
  
## <span data-ttu-id="142d4-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="142d4-109">Return Value</span></span>  
 <span data-ttu-id="142d4-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="142d4-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="142d4-111">要件</span><span class="sxs-lookup"><span data-stu-id="142d4-111">Requirements</span></span>  
 <span data-ttu-id="142d4-112">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="142d4-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="142d4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="142d4-113">See Also</span></span>  
 [<span data-ttu-id="142d4-114">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="142d4-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
