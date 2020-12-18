---
description: オブジェクトのプロパティを削除します。
title: JsDeleteProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteProperty
helpviewer_keywords:
- JsDeleteProperty function
ms.assetid: 0f6ac6a7-3576-42f5-98d0-1c06542c8149
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 55089bd4cff7ef4d58bcce1d7531d4ca1c7381ae
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234359"
---
# <span data-ttu-id="8ca50-103">JsDeleteProperty 関数</span><span class="sxs-lookup"><span data-stu-id="8ca50-103">JsDeleteProperty Function</span></span>

<span data-ttu-id="8ca50-104">オブジェクトのプロパティを削除します。</span><span class="sxs-lookup"><span data-stu-id="8ca50-104">Deletes an object's property.</span></span>  
  
## <span data-ttu-id="8ca50-105">構文</span><span class="sxs-lookup"><span data-stu-id="8ca50-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDeleteProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ bool useStrictRules,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="8ca50-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ca50-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="8ca50-107">プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ca50-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="8ca50-108">プロパティの ID。</span><span class="sxs-lookup"><span data-stu-id="8ca50-108">The ID of the property.</span></span>  
  
 `useStrictRules`  
 <span data-ttu-id="8ca50-109">プロパティ セットは、厳密モードの規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ca50-109">The property set should follow strict mode rules.</span></span>  
  
 `result`  
 <span data-ttu-id="8ca50-110">プロパティが削除されたかどうか。</span><span class="sxs-lookup"><span data-stu-id="8ca50-110">Whether the property was deleted.</span></span>  
  
## <span data-ttu-id="8ca50-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="8ca50-111">Return Value</span></span>  
 <span data-ttu-id="8ca50-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="8ca50-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8ca50-113">注釈</span><span class="sxs-lookup"><span data-stu-id="8ca50-113">Remarks</span></span>  
 <span data-ttu-id="8ca50-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="8ca50-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="8ca50-115">要件</span><span class="sxs-lookup"><span data-stu-id="8ca50-115">Requirements</span></span>  
 <span data-ttu-id="8ca50-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="8ca50-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8ca50-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ca50-117">See Also</span></span>  
 [<span data-ttu-id="8ca50-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="8ca50-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
