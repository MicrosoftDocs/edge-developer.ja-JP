---
description: 文字列ポインターから文字列値を作成します。
title: JsPointerToString 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsPointerToString
helpviewer_keywords:
- JsPointerToString function
ms.assetid: c71ce07e-4359-450c-afbf-a6ab7d48dddf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c00a060098f0b021afca27b300f3e0578e992cb9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234858"
---
# <span data-ttu-id="9b42c-103">JsPointerToString 関数</span><span class="sxs-lookup"><span data-stu-id="9b42c-103">JsPointerToString Function</span></span>

<span data-ttu-id="9b42c-104">文字列ポインターから文字列値を作成します。</span><span class="sxs-lookup"><span data-stu-id="9b42c-104">Creates a string value from a string pointer.</span></span>  
  
## <span data-ttu-id="9b42c-105">構文</span><span class="sxs-lookup"><span data-stu-id="9b42c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsPointerToString(  
   _In_reads_(stringLength) const wchar_t *stringValue,  
   _In_ size_t stringLength,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="9b42c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b42c-106">Parameters</span></span>  
 `stringValue`  
 <span data-ttu-id="9b42c-107">文字列値に変換する文字列ポインター。</span><span class="sxs-lookup"><span data-stu-id="9b42c-107">The string pointer to convert to a string value.</span></span>  
  
 `stringLength`  
 <span data-ttu-id="9b42c-108">変換する文字列の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b42c-108">The length of the string to convert.</span></span>  
  
 `value`  
 <span data-ttu-id="9b42c-109">新しい文字列値。</span><span class="sxs-lookup"><span data-stu-id="9b42c-109">The new string value.</span></span>  
  
## <span data-ttu-id="9b42c-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="9b42c-110">Return Value</span></span>  
 <span data-ttu-id="9b42c-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="9b42c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9b42c-112">注釈</span><span class="sxs-lookup"><span data-stu-id="9b42c-112">Remarks</span></span>  
 <span data-ttu-id="9b42c-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b42c-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9b42c-114">要件</span><span class="sxs-lookup"><span data-stu-id="9b42c-114">Requirements</span></span>  
 <span data-ttu-id="9b42c-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9b42c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9b42c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b42c-116">See Also</span></span>  
 [<span data-ttu-id="9b42c-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="9b42c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
