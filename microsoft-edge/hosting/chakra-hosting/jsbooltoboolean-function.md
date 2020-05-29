---
description: 値からブール値を作成し `bool` ます。
title: JsBoolToBoolean 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsBoolToBoolean
helpviewer_keywords:
- JsBoolToBoolean function
ms.assetid: 24322ea3-0638-40a3-9b4c-fc912ebed3ff
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f795bdd02a2a21dc4a0c8948a76ef817d6e0fac6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569399"
---
# <span data-ttu-id="03f7e-103">JsBoolToBoolean 関数</span><span class="sxs-lookup"><span data-stu-id="03f7e-103">JsBoolToBoolean Function</span></span>
<span data-ttu-id="03f7e-104">値からブール値を作成し `bool` ます。</span><span class="sxs-lookup"><span data-stu-id="03f7e-104">Creates a Boolean value from a `bool` value.</span></span>  
  
## <span data-ttu-id="03f7e-105">構文</span><span class="sxs-lookup"><span data-stu-id="03f7e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode JsBoolToBoolean(  
   _In_ bool value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <span data-ttu-id="03f7e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="03f7e-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="03f7e-107">変換する値。</span><span class="sxs-lookup"><span data-stu-id="03f7e-107">The value to be converted.</span></span>  
  
 `booleanValue`  
 <span data-ttu-id="03f7e-108">変換された値。</span><span class="sxs-lookup"><span data-stu-id="03f7e-108">The converted value.</span></span>  
  
## <span data-ttu-id="03f7e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="03f7e-109">Return Value</span></span>  
 <span data-ttu-id="03f7e-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="03f7e-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="03f7e-111">注釈</span><span class="sxs-lookup"><span data-stu-id="03f7e-111">Remarks</span></span>  
 <span data-ttu-id="03f7e-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="03f7e-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="03f7e-113">要件</span><span class="sxs-lookup"><span data-stu-id="03f7e-113">Requirements</span></span>  
 <span data-ttu-id="03f7e-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="03f7e-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="03f7e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="03f7e-115">See Also</span></span>  
 [<span data-ttu-id="03f7e-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="03f7e-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)