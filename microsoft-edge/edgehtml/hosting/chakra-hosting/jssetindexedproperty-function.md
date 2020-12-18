---
description: オブジェクトの指定したインデックスに値を設定します。
title: JsSetIndexedProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetIndexedProperty
helpviewer_keywords:
- JsSetIndexedProperty function
ms.assetid: ccbc5bf4-d99b-485c-ab25-d2bd1ed2142e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1fa961750fa5db262e1512d8d26572280d5e726c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234507"
---
# <span data-ttu-id="50c42-103">JsSetIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="50c42-103">JsSetIndexedProperty Function</span></span>

<span data-ttu-id="50c42-104">オブジェクトの指定したインデックスに値を設定します。</span><span class="sxs-lookup"><span data-stu-id="50c42-104">Set the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="50c42-105">構文</span><span class="sxs-lookup"><span data-stu-id="50c42-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _In_ JsValueRef value  
);  
```  
  
#### <span data-ttu-id="50c42-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50c42-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="50c42-107">操作対象のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="50c42-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="50c42-108">設定するインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="50c42-108">The index to set.</span></span>  
  
 `value`  
 <span data-ttu-id="50c42-109">設定する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="50c42-109">The value to set.</span></span>  
  
## <span data-ttu-id="50c42-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="50c42-110">Return Value</span></span>  
 <span data-ttu-id="50c42-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="50c42-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="50c42-112">注釈</span><span class="sxs-lookup"><span data-stu-id="50c42-112">Remarks</span></span>  
 <span data-ttu-id="50c42-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="50c42-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="50c42-114">要件</span><span class="sxs-lookup"><span data-stu-id="50c42-114">Requirements</span></span>  
 <span data-ttu-id="50c42-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="50c42-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="50c42-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="50c42-116">See Also</span></span>  
 [<span data-ttu-id="50c42-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="50c42-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
