---
description: オブジェクトが指定されたインデックスに値を持つかどうかをテストします。
title: JsHasIndexedProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasIndexedProperty
helpviewer_keywords:
- JsHasIndexedProperty function
ms.assetid: 30436a3d-fda0-407e-aba2-142be2310372
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9eb1794c465b4b116978a2150285e2fed3ae1d9b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234739"
---
# <span data-ttu-id="ece90-103">Jshasedproperty 関数</span><span class="sxs-lookup"><span data-stu-id="ece90-103">JsHasIndexedProperty Function</span></span>

<span data-ttu-id="ece90-104">オブジェクトが指定されたインデックスに値を持つかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="ece90-104">Tests whether an object has a value at the specified index.</span></span>  
  
## <span data-ttu-id="ece90-105">構文</span><span class="sxs-lookup"><span data-stu-id="ece90-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="ece90-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ece90-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="ece90-107">操作対象のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ece90-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="ece90-108">テストするインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ece90-108">The index to test.</span></span>  
  
 `result`  
 <span data-ttu-id="ece90-109">オブジェクトが指定されたインデックスに値を持つかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ece90-109">Whether the object has an value at the specified index.</span></span>  
  
## <span data-ttu-id="ece90-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="ece90-110">Return Value</span></span>  
 <span data-ttu-id="ece90-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ece90-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ece90-112">注釈</span><span class="sxs-lookup"><span data-stu-id="ece90-112">Remarks</span></span>  
 <span data-ttu-id="ece90-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ece90-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ece90-114">要件</span><span class="sxs-lookup"><span data-stu-id="ece90-114">Requirements</span></span>  
 <span data-ttu-id="ece90-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ece90-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ece90-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ece90-116">See Also</span></span>  
 [<span data-ttu-id="ece90-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ece90-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
