---
description: 指定したオブジェクトのインデックスの値を設定します。
title: JsSetIndexedProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetIndexedProperty
helpviewer_keywords:
- JsSetIndexedProperty function
ms.assetid: ccbc5bf4-d99b-485c-ab25-d2bd1ed2142e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 893849c42d9cbf0de160846d3397fcd5d7c77b7b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570375"
---
# <span data-ttu-id="a690a-103">JsSetIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="a690a-103">JsSetIndexedProperty Function</span></span>
<span data-ttu-id="a690a-104">指定したオブジェクトのインデックスの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a690a-104">Set the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="a690a-105">構文</span><span class="sxs-lookup"><span data-stu-id="a690a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _In_ JsValueRef value  
);  
```  
  
#### <span data-ttu-id="a690a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a690a-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="a690a-107">操作対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a690a-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="a690a-108">設定するインデックス。</span><span class="sxs-lookup"><span data-stu-id="a690a-108">The index to set.</span></span>  
  
 `value`  
 <span data-ttu-id="a690a-109">設定する値。</span><span class="sxs-lookup"><span data-stu-id="a690a-109">The value to set.</span></span>  
  
## <span data-ttu-id="a690a-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="a690a-110">Return Value</span></span>  
 <span data-ttu-id="a690a-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="a690a-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a690a-112">注釈</span><span class="sxs-lookup"><span data-stu-id="a690a-112">Remarks</span></span>  
 <span data-ttu-id="a690a-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="a690a-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a690a-114">要件</span><span class="sxs-lookup"><span data-stu-id="a690a-114">Requirements</span></span>  
 <span data-ttu-id="a690a-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="a690a-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a690a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a690a-116">See Also</span></span>  
 [<span data-ttu-id="a690a-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="a690a-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)