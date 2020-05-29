---
description: オブジェクト自体のプロパティのプロパティ記述子を取得します。
title: JsGetOwnPropertyDescriptor 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyDescriptor
helpviewer_keywords:
- JsGetOwnPropertyDescriptor function
ms.assetid: 44c417ce-ab63-44eb-a0ab-19838e3ab34f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6f500aec8b892cb2ad437bd7159ab14165a8bfb4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570457"
---
# <span data-ttu-id="26471-103">JsGetOwnPropertyDescriptor 関数</span><span class="sxs-lookup"><span data-stu-id="26471-103">JsGetOwnPropertyDescriptor Function</span></span>
<span data-ttu-id="26471-104">オブジェクト自体のプロパティのプロパティ記述子を取得します。</span><span class="sxs-lookup"><span data-stu-id="26471-104">Gets a property descriptor for an object's own property.</span></span>  
  
## <span data-ttu-id="26471-105">構文</span><span class="sxs-lookup"><span data-stu-id="26471-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyDescriptor(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *propertyDescriptor  
);  
```  
  
#### <span data-ttu-id="26471-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26471-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="26471-107">プロパティが設定されているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="26471-107">The object that has the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="26471-108">プロパティの ID です。</span><span class="sxs-lookup"><span data-stu-id="26471-108">The ID of the property.</span></span>  
  
 `propertyDescriptor`  
 <span data-ttu-id="26471-109">プロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="26471-109">The property descriptor.</span></span>  
  
## <span data-ttu-id="26471-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="26471-110">Return Value</span></span>  
 <span data-ttu-id="26471-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="26471-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="26471-112">注釈</span><span class="sxs-lookup"><span data-stu-id="26471-112">Remarks</span></span>  
 <span data-ttu-id="26471-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="26471-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="26471-114">要件</span><span class="sxs-lookup"><span data-stu-id="26471-114">Requirements</span></span>  
 <span data-ttu-id="26471-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="26471-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="26471-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="26471-116">See Also</span></span>  
 [<span data-ttu-id="26471-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="26471-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)