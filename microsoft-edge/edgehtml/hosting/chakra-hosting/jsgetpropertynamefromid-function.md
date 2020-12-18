---
description: プロパティ ID に関連付けられている名前を取得します。
title: JsGetPropertyNameFromId 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyNameFromId
helpviewer_keywords:
- JsGetPropertyNameFromId function
ms.assetid: b4ca442c-573d-4bc3-adf7-1b8d48480b3a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 42061ab54a70fed571740961a909a6da17fb0733
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234740"
---
# <span data-ttu-id="bc31a-103">JsGetPropertyNameFromId 関数</span><span class="sxs-lookup"><span data-stu-id="bc31a-103">JsGetPropertyNameFromId Function</span></span>

<span data-ttu-id="bc31a-104">プロパティ ID に関連付けられている名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc31a-104">Gets the name associated with the property ID.</span></span>  
  
## <span data-ttu-id="bc31a-105">構文</span><span class="sxs-lookup"><span data-stu-id="bc31a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyNameFromId(  
   _In_ JsPropertyIdRef propertyId,  
   _Outptr_result_z_ const wchar_t **name  
);  
```  
  
#### <span data-ttu-id="bc31a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc31a-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="bc31a-107">名前を取得するプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="bc31a-107">The property ID to get the name of.</span></span>  
  
 `name`  
 <span data-ttu-id="bc31a-108">プロパティ ID に関連付けられている名前。</span><span class="sxs-lookup"><span data-stu-id="bc31a-108">The name associated with the property ID.</span></span>  
  
## <span data-ttu-id="bc31a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bc31a-109">Return Value</span></span>  
 <span data-ttu-id="bc31a-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bc31a-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bc31a-111">注釈</span><span class="sxs-lookup"><span data-stu-id="bc31a-111">Remarks</span></span>  
 <span data-ttu-id="bc31a-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="bc31a-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="bc31a-113">返されるバッファーは、ランタイムが有効で、ランタイムが破棄された後は使用できない限り有効です。</span><span class="sxs-lookup"><span data-stu-id="bc31a-113">The returned buffer is valid as long as the runtime is alive and cannot be used once the runtime has been disposed.</span></span>  
  
## <span data-ttu-id="bc31a-114">要件</span><span class="sxs-lookup"><span data-stu-id="bc31a-114">Requirements</span></span>  
 <span data-ttu-id="bc31a-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bc31a-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bc31a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc31a-116">See Also</span></span>  
 [<span data-ttu-id="bc31a-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="bc31a-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
