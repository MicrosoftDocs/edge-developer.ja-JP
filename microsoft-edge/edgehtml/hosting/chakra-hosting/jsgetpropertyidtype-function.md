---
description: プロパティの種類を取得します。
title: JsGetPropertyIdType 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 2b6e85ad-c630-4a07-a759-3b344d06faaa
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 93ee11bf74014361c89aa93bbb58361b426f573f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234911"
---
# <span data-ttu-id="6ee93-103">JsGetPropertyIdType 関数</span><span class="sxs-lookup"><span data-stu-id="6ee93-103">JsGetPropertyIdType Function</span></span>

<span data-ttu-id="6ee93-104">プロパティの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="6ee93-104">Gets the type of property.</span></span>  
  
## <span data-ttu-id="6ee93-105">構文</span><span class="sxs-lookup"><span data-stu-id="6ee93-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdType(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsPropertyIdType* propertyIdType  
);  
```  
  
#### <span data-ttu-id="6ee93-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ee93-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="6ee93-107">型を取得するプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="6ee93-107">The property ID to get the type of.</span></span>  
  
 `propertyIdType`  
 <span data-ttu-id="6ee93-108">指定 `JsPropertyIdType` されたプロパティ ID の値。</span><span class="sxs-lookup"><span data-stu-id="6ee93-108">The `JsPropertyIdType` of the given property ID.</span></span>  
  
## <span data-ttu-id="6ee93-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6ee93-109">Return Value</span></span>  
 <span data-ttu-id="6ee93-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="6ee93-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6ee93-111">注釈</span><span class="sxs-lookup"><span data-stu-id="6ee93-111">Remarks</span></span>  
 <span data-ttu-id="6ee93-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ee93-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="6ee93-113">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6ee93-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="6ee93-114">要件</span><span class="sxs-lookup"><span data-stu-id="6ee93-114">Requirements</span></span>  
 <span data-ttu-id="6ee93-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6ee93-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6ee93-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ee93-116">See Also</span></span>  
 [<span data-ttu-id="6ee93-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="6ee93-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
