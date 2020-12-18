---
description: オブジェクト自身のプロパティのプロパティ記述子を取得します。
title: JsGetOwnPropertyDescriptor 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyDescriptor
helpviewer_keywords:
- JsGetOwnPropertyDescriptor function
ms.assetid: 44c417ce-ab63-44eb-a0ab-19838e3ab34f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 05c7a58fa12d7ca8013c512f40031963ebc8ac18
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234723"
---
# <span data-ttu-id="56c0d-103">JsGetOwnPropertyDescriptor 関数</span><span class="sxs-lookup"><span data-stu-id="56c0d-103">JsGetOwnPropertyDescriptor Function</span></span>

<span data-ttu-id="56c0d-104">オブジェクト自身のプロパティのプロパティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="56c0d-104">Gets a property descriptor for an object's own property.</span></span>  
  
## <span data-ttu-id="56c0d-105">構文</span><span class="sxs-lookup"><span data-stu-id="56c0d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyDescriptor(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *propertyDescriptor  
);  
```  
  
#### <span data-ttu-id="56c0d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="56c0d-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="56c0d-107">プロパティを持つオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="56c0d-107">The object that has the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="56c0d-108">プロパティの ID。</span><span class="sxs-lookup"><span data-stu-id="56c0d-108">The ID of the property.</span></span>  
  
 `propertyDescriptor`  
 <span data-ttu-id="56c0d-109">プロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="56c0d-109">The property descriptor.</span></span>  
  
## <span data-ttu-id="56c0d-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="56c0d-110">Return Value</span></span>  
 <span data-ttu-id="56c0d-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="56c0d-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="56c0d-112">注釈</span><span class="sxs-lookup"><span data-stu-id="56c0d-112">Remarks</span></span>  
 <span data-ttu-id="56c0d-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="56c0d-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="56c0d-114">要件</span><span class="sxs-lookup"><span data-stu-id="56c0d-114">Requirements</span></span>  
 <span data-ttu-id="56c0d-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="56c0d-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="56c0d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="56c0d-116">See Also</span></span>  
 [<span data-ttu-id="56c0d-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="56c0d-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
