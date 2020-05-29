---
description: 現在のスクリプトコンテキスト内の値を取得し `false` ます。
title: JsGetFalseValue 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetFalseValue
helpviewer_keywords:
- JsGetFalseValue function
ms.assetid: 621a584c-4ca8-4ba0-b19a-6cb50cf830b6
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 52e54ad7eb34877c3cb83b06f5aba70edf285bca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569323"
---
# <span data-ttu-id="d6ff4-103">JsGetFalseValue 関数</span><span class="sxs-lookup"><span data-stu-id="d6ff4-103">JsGetFalseValue Function</span></span>
<span data-ttu-id="d6ff4-104">現在のスクリプトコンテキスト内の値を取得し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="d6ff4-104">Gets the value of `false` in the current script context.</span></span>  
  
## <span data-ttu-id="d6ff4-105">構文</span><span class="sxs-lookup"><span data-stu-id="d6ff4-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetFalseValue(  
   _Out_ JsValueRef *falseValue  
);  
```  
  
#### <span data-ttu-id="d6ff4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6ff4-106">Parameters</span></span>  
 `falseValue`  
 <span data-ttu-id="d6ff4-107">`false`値。</span><span class="sxs-lookup"><span data-stu-id="d6ff4-107">The `false` value.</span></span>  
  
## <span data-ttu-id="d6ff4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="d6ff4-108">Return Value</span></span>  
 <span data-ttu-id="d6ff4-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="d6ff4-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d6ff4-110">注釈</span><span class="sxs-lookup"><span data-stu-id="d6ff4-110">Remarks</span></span>  
 <span data-ttu-id="d6ff4-111">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="d6ff4-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="d6ff4-112">要件</span><span class="sxs-lookup"><span data-stu-id="d6ff4-112">Requirements</span></span>  
 <span data-ttu-id="d6ff4-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="d6ff4-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d6ff4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6ff4-114">See Also</span></span>  
 [<span data-ttu-id="d6ff4-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d6ff4-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)