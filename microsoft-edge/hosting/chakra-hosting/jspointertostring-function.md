---
description: 文字列ポインターから文字列値を作成します。
title: JsPointerToString 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsPointerToString
helpviewer_keywords:
- JsPointerToString function
ms.assetid: c71ce07e-4359-450c-afbf-a6ab7d48dddf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b3c5b2d6439244bc9584e15c361412c8a1e87557
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570415"
---
# <span data-ttu-id="b573f-103">JsPointerToString 関数</span><span class="sxs-lookup"><span data-stu-id="b573f-103">JsPointerToString Function</span></span>
<span data-ttu-id="b573f-104">文字列ポインターから文字列値を作成します。</span><span class="sxs-lookup"><span data-stu-id="b573f-104">Creates a string value from a string pointer.</span></span>  
  
## <span data-ttu-id="b573f-105">構文</span><span class="sxs-lookup"><span data-stu-id="b573f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsPointerToString(  
   _In_reads_(stringLength) const wchar_t *stringValue,  
   _In_ size_t stringLength,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="b573f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b573f-106">Parameters</span></span>  
 `stringValue`  
 <span data-ttu-id="b573f-107">文字列値に変換する文字列ポインター。</span><span class="sxs-lookup"><span data-stu-id="b573f-107">The string pointer to convert to a string value.</span></span>  
  
 `stringLength`  
 <span data-ttu-id="b573f-108">変換する文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="b573f-108">The length of the string to convert.</span></span>  
  
 `value`  
 <span data-ttu-id="b573f-109">新しい文字列値。</span><span class="sxs-lookup"><span data-stu-id="b573f-109">The new string value.</span></span>  
  
## <span data-ttu-id="b573f-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="b573f-110">Return Value</span></span>  
 <span data-ttu-id="b573f-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="b573f-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b573f-112">注釈</span><span class="sxs-lookup"><span data-stu-id="b573f-112">Remarks</span></span>  
 <span data-ttu-id="b573f-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="b573f-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b573f-114">要件</span><span class="sxs-lookup"><span data-stu-id="b573f-114">Requirements</span></span>  
 <span data-ttu-id="b573f-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="b573f-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b573f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b573f-116">See Also</span></span>  
 [<span data-ttu-id="b573f-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b573f-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)