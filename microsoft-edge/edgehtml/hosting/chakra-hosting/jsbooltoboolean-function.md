---
description: 値からブール値を作成 `bool` します。
title: JsBoolToBoolean 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsBoolToBoolean
helpviewer_keywords:
- JsBoolToBoolean function
ms.assetid: 24322ea3-0638-40a3-9b4c-fc912ebed3ff
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3d6ec9f85d53e0d78c6bbe1c7d3282971831717b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234546"
---
# <span data-ttu-id="1e599-103">JsBoolToBoolean 関数</span><span class="sxs-lookup"><span data-stu-id="1e599-103">JsBoolToBoolean Function</span></span>

<span data-ttu-id="1e599-104">値からブール値を作成 `bool` します。</span><span class="sxs-lookup"><span data-stu-id="1e599-104">Creates a Boolean value from a `bool` value.</span></span>  
  
## <span data-ttu-id="1e599-105">構文</span><span class="sxs-lookup"><span data-stu-id="1e599-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode JsBoolToBoolean(  
   _In_ bool value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <span data-ttu-id="1e599-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e599-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="1e599-107">変換する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e599-107">The value to be converted.</span></span>  
  
 `booleanValue`  
 <span data-ttu-id="1e599-108">変換された値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e599-108">The converted value.</span></span>  
  
## <span data-ttu-id="1e599-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e599-109">Return Value</span></span>  
 <span data-ttu-id="1e599-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1e599-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1e599-111">注釈</span><span class="sxs-lookup"><span data-stu-id="1e599-111">Remarks</span></span>  
 <span data-ttu-id="1e599-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="1e599-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1e599-113">要件</span><span class="sxs-lookup"><span data-stu-id="1e599-113">Requirements</span></span>  
 <span data-ttu-id="1e599-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="1e599-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1e599-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e599-115">See Also</span></span>  
 [<span data-ttu-id="1e599-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="1e599-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
