---
description: オブジェクトのインデックス付きプロパティが外部データに含まれているかどうかを判断します。
title: JsHasIndexedPropertiesExternalData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c676db20-3ef1-4f84-8b26-3e06fe0ab2bf
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c7f9f87b19016b3d837b637219eec936a11211e9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570433"
---
# <span data-ttu-id="5f26e-103">JsHasIndexedPropertiesExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="5f26e-103">JsHasIndexedPropertiesExternalData Function</span></span>
<span data-ttu-id="5f26e-104">オブジェクトのインデックス付きプロパティが外部データに含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5f26e-104">Determines whether an object has its indexed properties in external data.</span></span>  
  
## <span data-ttu-id="5f26e-105">構文</span><span class="sxs-lookup"><span data-stu-id="5f26e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool* value  
);  
```  
  
#### <span data-ttu-id="5f26e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f26e-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="5f26e-107">オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5f26e-107">The object.</span></span>  
  
 `value`  
 <span data-ttu-id="5f26e-108">オブジェクトのインデックス付きプロパティが外部データに含まれているかどうか</span><span class="sxs-lookup"><span data-stu-id="5f26e-108">Whether the object has its indexed properties in external data.</span></span>  
  
## <span data-ttu-id="5f26e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5f26e-109">Return Value</span></span>  
 <span data-ttu-id="5f26e-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="5f26e-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5f26e-111">注釈</span><span class="sxs-lookup"><span data-stu-id="5f26e-111">Remarks</span></span>  
 <span data-ttu-id="5f26e-112">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5f26e-112">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="5f26e-113">要件</span><span class="sxs-lookup"><span data-stu-id="5f26e-113">Requirements</span></span>  
 <span data-ttu-id="5f26e-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="5f26e-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5f26e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f26e-115">See Also</span></span>  
 [<span data-ttu-id="5f26e-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5f26e-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)