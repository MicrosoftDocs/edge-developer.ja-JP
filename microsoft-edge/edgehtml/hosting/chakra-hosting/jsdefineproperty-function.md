---
description: プロパティ記述子から新しいオブジェクトの独自のプロパティを定義します。
title: JsDefineProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDefineProperty
helpviewer_keywords:
- JsDefineProperty function
ms.assetid: b2cf48d6-eb40-457c-aa8b-b16a50dc5d6a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a35dd6214190fa558c50cbb743b0f2b92b5e00b3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234876"
---
# <span data-ttu-id="c644c-103">JsDefineProperty 関数</span><span class="sxs-lookup"><span data-stu-id="c644c-103">JsDefineProperty Function</span></span>

<span data-ttu-id="c644c-104">プロパティ記述子から新しいオブジェクトの独自のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c644c-104">Defines a new object's own property from a property descriptor.</span></span>  
  
## <span data-ttu-id="c644c-105">構文</span><span class="sxs-lookup"><span data-stu-id="c644c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDefineProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef propertyDescriptor,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="c644c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c644c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="c644c-107">プロパティを持つオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c644c-107">The object that has the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="c644c-108">プロパティの ID。</span><span class="sxs-lookup"><span data-stu-id="c644c-108">The ID of the property.</span></span>  
  
 `propertyDescriptor`  
 <span data-ttu-id="c644c-109">プロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="c644c-109">The property descriptor.</span></span>  
  
 `result`  
 <span data-ttu-id="c644c-110">プロパティが定義されたかどうか。</span><span class="sxs-lookup"><span data-stu-id="c644c-110">Whether the property was defined.</span></span>  
  
## <span data-ttu-id="c644c-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="c644c-111">Return Value</span></span>  
 <span data-ttu-id="c644c-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="c644c-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c644c-113">注釈</span><span class="sxs-lookup"><span data-stu-id="c644c-113">Remarks</span></span>  
 <span data-ttu-id="c644c-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="c644c-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c644c-115">要件</span><span class="sxs-lookup"><span data-stu-id="c644c-115">Requirements</span></span>  
 <span data-ttu-id="c644c-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c644c-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c644c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c644c-117">See Also</span></span>  
 [<span data-ttu-id="c644c-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="c644c-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
