---
description: オブジェクトのプロパティを設定します。
title: JsSetProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetProperty
helpviewer_keywords:
- JsSetProperty function
ms.assetid: 2c36bebf-ec86-425c-8131-2dd75fd30f40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 29c3e04fc240bd63fc755c6727752d053b94484d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234738"
---
# <span data-ttu-id="590c1-103">JsSetProperty 関数</span><span class="sxs-lookup"><span data-stu-id="590c1-103">JsSetProperty Function</span></span>

<span data-ttu-id="590c1-104">オブジェクトのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="590c1-104">Puts an object's property.</span></span>  
  
## <span data-ttu-id="590c1-105">構文</span><span class="sxs-lookup"><span data-stu-id="590c1-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef value,  
   _In_ bool useStrictRules  
);  
```  
  
#### <span data-ttu-id="590c1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="590c1-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="590c1-107">プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="590c1-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="590c1-108">プロパティの ID。</span><span class="sxs-lookup"><span data-stu-id="590c1-108">The ID of the property.</span></span>  
  
 `value`  
 <span data-ttu-id="590c1-109">プロパティの新しい値。</span><span class="sxs-lookup"><span data-stu-id="590c1-109">The new value of the property.</span></span>  
  
 `useStrictRules`  
 <span data-ttu-id="590c1-110">プロパティ セットは、厳密モードの規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="590c1-110">The property set should follow strict mode rules.</span></span>  
  
## <span data-ttu-id="590c1-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="590c1-111">Return Value</span></span>  
 <span data-ttu-id="590c1-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="590c1-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="590c1-113">注釈</span><span class="sxs-lookup"><span data-stu-id="590c1-113">Remarks</span></span>  
 <span data-ttu-id="590c1-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="590c1-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="590c1-115">要件</span><span class="sxs-lookup"><span data-stu-id="590c1-115">Requirements</span></span>  
 <span data-ttu-id="590c1-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="590c1-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="590c1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="590c1-117">See Also</span></span>  
 [<span data-ttu-id="590c1-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="590c1-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
