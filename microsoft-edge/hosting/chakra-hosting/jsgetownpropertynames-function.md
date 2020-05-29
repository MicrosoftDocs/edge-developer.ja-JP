---
description: オブジェクトのすべてのプロパティの一覧を取得します。
title: JsGetOwnPropertyNames 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyNames
helpviewer_keywords:
- JsGetOwnPropertyNames function
ms.assetid: 0c17ea06-b17f-4ea3-ad04-1259a4d1b6de
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5355caab864724d72fdb2c7abb3dc70e39662b55
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570450"
---
# <span data-ttu-id="8f667-103">JsGetOwnPropertyNames 関数</span><span class="sxs-lookup"><span data-stu-id="8f667-103">JsGetOwnPropertyNames Function</span></span>
<span data-ttu-id="8f667-104">オブジェクトのすべてのプロパティの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f667-104">Gets the list of all properties on the object.</span></span>  
  
## <span data-ttu-id="8f667-105">構文</span><span class="sxs-lookup"><span data-stu-id="8f667-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyNames(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertyNames  
);  
```  
  
#### <span data-ttu-id="8f667-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f667-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="8f667-107">プロパティ名を取得する対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8f667-107">The object from which to get the property names.</span></span>  
  
 `propertyNames`  
 <span data-ttu-id="8f667-108">プロパティ名の配列。</span><span class="sxs-lookup"><span data-stu-id="8f667-108">An array of property names.</span></span>  
  
## <span data-ttu-id="8f667-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="8f667-109">Return Value</span></span>  
 <span data-ttu-id="8f667-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="8f667-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8f667-111">注釈</span><span class="sxs-lookup"><span data-stu-id="8f667-111">Remarks</span></span>  
 <span data-ttu-id="8f667-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f667-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="8f667-113">要件</span><span class="sxs-lookup"><span data-stu-id="8f667-113">Requirements</span></span>  
 <span data-ttu-id="8f667-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="8f667-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8f667-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f667-115">See Also</span></span>  
 [<span data-ttu-id="8f667-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="8f667-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)