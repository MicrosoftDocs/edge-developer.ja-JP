---
description: 名前に関連付けられているプロパティ ID を取得します。
title: JsGetPropertyIdFromName 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyIdFromName
helpviewer_keywords:
- JsGetPropertyIdFromName function
ms.assetid: 1674906f-746a-4c62-99cd-023276683a86
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: adc8de4d55fa0c74ad191b4621ceb3a54026d02d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234878"
---
# <span data-ttu-id="41a7f-103">JsGetPropertyIdFromName 関数</span><span class="sxs-lookup"><span data-stu-id="41a7f-103">JsGetPropertyIdFromName Function</span></span>

<span data-ttu-id="41a7f-104">名前に関連付けられているプロパティ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="41a7f-104">Gets the property ID associated with the name.</span></span>  
  
## <span data-ttu-id="41a7f-105">構文</span><span class="sxs-lookup"><span data-stu-id="41a7f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromName(  
   _In_z_ const wchar_t *name,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### <span data-ttu-id="41a7f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41a7f-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="41a7f-107">取得または作成するプロパティ ID の名前。</span><span class="sxs-lookup"><span data-stu-id="41a7f-107">The name of the property ID to get or create.</span></span> <span data-ttu-id="41a7f-108">名前は数字だけで構成できます。</span><span class="sxs-lookup"><span data-stu-id="41a7f-108">The name may consist of only digits.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="41a7f-109">指定された名前のこのランタイムのプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="41a7f-109">The property ID in this runtime for the given name.</span></span>  
  
## <span data-ttu-id="41a7f-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="41a7f-110">Return Value</span></span>  
 <span data-ttu-id="41a7f-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="41a7f-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="41a7f-112">注釈</span><span class="sxs-lookup"><span data-stu-id="41a7f-112">Remarks</span></span>  
 <span data-ttu-id="41a7f-113">プロパティの ID はコンテキストに固有の値であり、コンテキスト間では使用できません。</span><span class="sxs-lookup"><span data-stu-id="41a7f-113">Property IDs are specific to a context and cannot be used across contexts.</span></span>  
  
 <span data-ttu-id="41a7f-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="41a7f-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="41a7f-115">要件</span><span class="sxs-lookup"><span data-stu-id="41a7f-115">Requirements</span></span>  
 <span data-ttu-id="41a7f-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="41a7f-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="41a7f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="41a7f-117">See Also</span></span>  
 [<span data-ttu-id="41a7f-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="41a7f-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
