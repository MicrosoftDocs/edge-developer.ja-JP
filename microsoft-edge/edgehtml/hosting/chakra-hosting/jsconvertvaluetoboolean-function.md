---
description: 標準の JavaScript セマンティクスを使用して、値をブール値に変換します。
title: JsConvertValueToBoolean 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToBoolean
helpviewer_keywords:
- JsConvertValueToBoolean function
ms.assetid: 7298ec72-a388-4334-b81b-1691ab4cecf0
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d2e109690fc8a7a98a1ecb84d6f5abf6a646162b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234545"
---
# <span data-ttu-id="ddb6d-103">JsConvertValueToBoolean 関数</span><span class="sxs-lookup"><span data-stu-id="ddb6d-103">JsConvertValueToBoolean Function</span></span>

<span data-ttu-id="ddb6d-104">標準の JavaScript セマンティクスを使用して、値をブール値に変換します。</span><span class="sxs-lookup"><span data-stu-id="ddb6d-104">Converts the value to Boolean using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="ddb6d-105">構文</span><span class="sxs-lookup"><span data-stu-id="ddb6d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToBoolean(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <span data-ttu-id="ddb6d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ddb6d-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="ddb6d-107">変換する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddb6d-107">The value to be converted.</span></span>  
  
 `booleanValue`  
 <span data-ttu-id="ddb6d-108">変換された値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddb6d-108">The converted value.</span></span>  
  
## <span data-ttu-id="ddb6d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ddb6d-109">Return Value</span></span>  
 <span data-ttu-id="ddb6d-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ddb6d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ddb6d-111">注釈</span><span class="sxs-lookup"><span data-stu-id="ddb6d-111">Remarks</span></span>  
 <span data-ttu-id="ddb6d-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ddb6d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ddb6d-113">要件</span><span class="sxs-lookup"><span data-stu-id="ddb6d-113">Requirements</span></span>  
 <span data-ttu-id="ddb6d-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ddb6d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ddb6d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddb6d-115">See Also</span></span>  
 [<span data-ttu-id="ddb6d-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ddb6d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
