---
description: オブジェクトの指定されたインデックスの値を取得します。
title: JsGetIndexedProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetIndexedProperty
helpviewer_keywords:
- JsGetIndexedProperty function
ms.assetid: f61ea388-0ae6-4a19-b3b5-75ed49a3f32d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 7bb048b841462e27604ab169c69e4c051209a67d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570453"
---
# <span data-ttu-id="1228c-103">JsGetIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="1228c-103">JsGetIndexedProperty Function</span></span>
<span data-ttu-id="1228c-104">オブジェクトの指定されたインデックスの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1228c-104">Retrieve the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="1228c-105">構文</span><span class="sxs-lookup"><span data-stu-id="1228c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="1228c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1228c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="1228c-107">操作対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1228c-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="1228c-108">取得するインデックス。</span><span class="sxs-lookup"><span data-stu-id="1228c-108">The index to retrieve.</span></span>  
  
 `result`  
 <span data-ttu-id="1228c-109">取得された値。</span><span class="sxs-lookup"><span data-stu-id="1228c-109">The retrieved value.</span></span>  
  
## <span data-ttu-id="1228c-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="1228c-110">Return Value</span></span>  
 <span data-ttu-id="1228c-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="1228c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1228c-112">注釈</span><span class="sxs-lookup"><span data-stu-id="1228c-112">Remarks</span></span>  
 <span data-ttu-id="1228c-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="1228c-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1228c-114">要件</span><span class="sxs-lookup"><span data-stu-id="1228c-114">Requirements</span></span>  
 <span data-ttu-id="1228c-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="1228c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1228c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1228c-116">See Also</span></span>  
 [<span data-ttu-id="1228c-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="1228c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)