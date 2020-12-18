---
description: オブジェクトが拡張可能かどうかを示す値を返します。
title: JsGetExtensionAllowed 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetExtensionAllowed
helpviewer_keywords:
- JsGetExtensionAllowed function
ms.assetid: 839054a1-d643-47d9-89db-6a015bba0d91
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7bc9e3265b48a27d0da4bc4646b2b5e3b1765b86
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234773"
---
# <span data-ttu-id="90502-103">JsGetExtensionAllowed 関数</span><span class="sxs-lookup"><span data-stu-id="90502-103">JsGetExtensionAllowed Function</span></span>

<span data-ttu-id="90502-104">オブジェクトが拡張可能かどうかを示す値を返します。</span><span class="sxs-lookup"><span data-stu-id="90502-104">Returns a value that indicates whether an object is extensible or not.</span></span>  
  
## <span data-ttu-id="90502-105">構文</span><span class="sxs-lookup"><span data-stu-id="90502-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExtensionAllowed(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### <span data-ttu-id="90502-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90502-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="90502-107">テストするオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="90502-107">The object to test.</span></span>  
  
 `value`  
 <span data-ttu-id="90502-108">オブジェクトが拡張可能かどうか。</span><span class="sxs-lookup"><span data-stu-id="90502-108">Whether the object is extensible or not.</span></span>  
  
## <span data-ttu-id="90502-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="90502-109">Return Value</span></span>  
 <span data-ttu-id="90502-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="90502-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="90502-111">注釈</span><span class="sxs-lookup"><span data-stu-id="90502-111">Remarks</span></span>  
 <span data-ttu-id="90502-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="90502-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="90502-113">要件</span><span class="sxs-lookup"><span data-stu-id="90502-113">Requirements</span></span>  
 <span data-ttu-id="90502-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="90502-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="90502-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="90502-115">See Also</span></span>  
 [<span data-ttu-id="90502-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="90502-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
