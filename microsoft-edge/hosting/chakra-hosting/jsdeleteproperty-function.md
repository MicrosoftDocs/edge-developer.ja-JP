---
description: オブジェクトのプロパティを削除します。
title: JsDeleteProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteProperty
helpviewer_keywords:
- JsDeleteProperty function
ms.assetid: 0f6ac6a7-3576-42f5-98d0-1c06542c8149
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c5539238324d59126b45f19fa9a6f8facc0f2ee3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569341"
---
# <span data-ttu-id="5c3d3-103">JsDeleteProperty 関数</span><span class="sxs-lookup"><span data-stu-id="5c3d3-103">JsDeleteProperty Function</span></span>
<span data-ttu-id="5c3d3-104">オブジェクトのプロパティを削除します。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-104">Deletes an object's property.</span></span>  
  
## <span data-ttu-id="5c3d3-105">構文</span><span class="sxs-lookup"><span data-stu-id="5c3d3-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDeleteProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ bool useStrictRules,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="5c3d3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c3d3-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="5c3d3-107">プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="5c3d3-108">プロパティの ID です。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-108">The ID of the property.</span></span>  
  
 `useStrictRules`  
 <span data-ttu-id="5c3d3-109">プロパティセットは、strict モードの規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-109">The property set should follow strict mode rules.</span></span>  
  
 `result`  
 <span data-ttu-id="5c3d3-110">プロパティが削除されたかどうか</span><span class="sxs-lookup"><span data-stu-id="5c3d3-110">Whether the property was deleted.</span></span>  
  
## <span data-ttu-id="5c3d3-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="5c3d3-111">Return Value</span></span>  
 <span data-ttu-id="5c3d3-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5c3d3-113">注釈</span><span class="sxs-lookup"><span data-stu-id="5c3d3-113">Remarks</span></span>  
 <span data-ttu-id="5c3d3-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5c3d3-115">要件</span><span class="sxs-lookup"><span data-stu-id="5c3d3-115">Requirements</span></span>  
 <span data-ttu-id="5c3d3-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="5c3d3-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5c3d3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c3d3-117">See Also</span></span>  
 [<span data-ttu-id="5c3d3-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5c3d3-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)