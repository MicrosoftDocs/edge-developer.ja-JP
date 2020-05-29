---
description: プロパティの型を取得します。
title: JsGetPropertyIdType 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2b6e85ad-c630-4a07-a759-3b344d06faaa
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a43cfc2efd69cc14813ad88850afbf602d477d71
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570445"
---
# <span data-ttu-id="dd06b-103">JsGetPropertyIdType 関数</span><span class="sxs-lookup"><span data-stu-id="dd06b-103">JsGetPropertyIdType Function</span></span>
<span data-ttu-id="dd06b-104">プロパティの型を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd06b-104">Gets the type of property.</span></span>  
  
## <span data-ttu-id="dd06b-105">構文</span><span class="sxs-lookup"><span data-stu-id="dd06b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdType(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsPropertyIdType* propertyIdType  
);  
```  
  
#### <span data-ttu-id="dd06b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd06b-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="dd06b-107">型を取得するプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="dd06b-107">The property ID to get the type of.</span></span>  
  
 `propertyIdType`  
 <span data-ttu-id="dd06b-108">`JsPropertyIdType`指定されたプロパティ ID の。</span><span class="sxs-lookup"><span data-stu-id="dd06b-108">The `JsPropertyIdType` of the given property ID.</span></span>  
  
## <span data-ttu-id="dd06b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="dd06b-109">Return Value</span></span>  
 <span data-ttu-id="dd06b-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="dd06b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="dd06b-111">注釈</span><span class="sxs-lookup"><span data-stu-id="dd06b-111">Remarks</span></span>  
 <span data-ttu-id="dd06b-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd06b-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="dd06b-113">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dd06b-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="dd06b-114">要件</span><span class="sxs-lookup"><span data-stu-id="dd06b-114">Requirements</span></span>  
 <span data-ttu-id="dd06b-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="dd06b-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="dd06b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd06b-116">See Also</span></span>  
 [<span data-ttu-id="dd06b-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="dd06b-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)