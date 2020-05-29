---
description: 標準の JavaScript セマンティクスを使って、値をブール型 (Boolean) に変換します。
title: JsConvertValueToBoolean 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToBoolean
helpviewer_keywords:
- JsConvertValueToBoolean function
ms.assetid: 7298ec72-a388-4334-b81b-1691ab4cecf0
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 861871a030d5a47621ccaf40b6cd332f42a06583
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569386"
---
# <span data-ttu-id="2440c-103">JsConvertValueToBoolean 関数</span><span class="sxs-lookup"><span data-stu-id="2440c-103">JsConvertValueToBoolean Function</span></span>
<span data-ttu-id="2440c-104">標準の JavaScript セマンティクスを使って、値をブール型 (Boolean) に変換します。</span><span class="sxs-lookup"><span data-stu-id="2440c-104">Converts the value to Boolean using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="2440c-105">構文</span><span class="sxs-lookup"><span data-stu-id="2440c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToBoolean(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <span data-ttu-id="2440c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2440c-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="2440c-107">変換する値。</span><span class="sxs-lookup"><span data-stu-id="2440c-107">The value to be converted.</span></span>  
  
 `booleanValue`  
 <span data-ttu-id="2440c-108">変換された値。</span><span class="sxs-lookup"><span data-stu-id="2440c-108">The converted value.</span></span>  
  
## <span data-ttu-id="2440c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2440c-109">Return Value</span></span>  
 <span data-ttu-id="2440c-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="2440c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2440c-111">注釈</span><span class="sxs-lookup"><span data-stu-id="2440c-111">Remarks</span></span>  
 <span data-ttu-id="2440c-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="2440c-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="2440c-113">要件</span><span class="sxs-lookup"><span data-stu-id="2440c-113">Requirements</span></span>  
 <span data-ttu-id="2440c-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="2440c-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2440c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2440c-115">See Also</span></span>  
 [<span data-ttu-id="2440c-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2440c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)