---
description: オブジェクトのすべてのプロパティのリストを取得します。
title: JsGetOwnPropertyNames 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyNames
helpviewer_keywords:
- JsGetOwnPropertyNames function
ms.assetid: 0c17ea06-b17f-4ea3-ad04-1259a4d1b6de
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4d00788b6ef581b923413e5c71a63bb27398a326
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234333"
---
# <span data-ttu-id="3081e-103">JsGetOwnPropertyNames 関数</span><span class="sxs-lookup"><span data-stu-id="3081e-103">JsGetOwnPropertyNames Function</span></span>

<span data-ttu-id="3081e-104">オブジェクトのすべてのプロパティのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="3081e-104">Gets the list of all properties on the object.</span></span>  
  
## <span data-ttu-id="3081e-105">構文</span><span class="sxs-lookup"><span data-stu-id="3081e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyNames(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertyNames  
);  
```  
  
#### <span data-ttu-id="3081e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3081e-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="3081e-107">プロパティ名を取得するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3081e-107">The object from which to get the property names.</span></span>  
  
 `propertyNames`  
 <span data-ttu-id="3081e-108">プロパティ名の配列。</span><span class="sxs-lookup"><span data-stu-id="3081e-108">An array of property names.</span></span>  
  
## <span data-ttu-id="3081e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="3081e-109">Return Value</span></span>  
 <span data-ttu-id="3081e-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="3081e-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3081e-111">注釈</span><span class="sxs-lookup"><span data-stu-id="3081e-111">Remarks</span></span>  
 <span data-ttu-id="3081e-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="3081e-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="3081e-113">要件</span><span class="sxs-lookup"><span data-stu-id="3081e-113">Requirements</span></span>  
 <span data-ttu-id="3081e-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="3081e-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3081e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3081e-115">See Also</span></span>  
 [<span data-ttu-id="3081e-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="3081e-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
