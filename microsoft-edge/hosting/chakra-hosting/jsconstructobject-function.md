---
description: コンストラクターとして関数を呼び出します。
title: JsConstructObject 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConstructObject
helpviewer_keywords:
- JsConstructObject function
ms.assetid: b07d2440-db55-4a6a-8376-56b40a8039a1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6fb9654b5c7321d6c6b0b255ec897fb30a114041
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569391"
---
# <span data-ttu-id="8194b-103">JsConstructObject 関数</span><span class="sxs-lookup"><span data-stu-id="8194b-103">JsConstructObject Function</span></span>
<span data-ttu-id="8194b-104">コンストラクターとして関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8194b-104">Invokes a function as a constructor.</span></span>  
  
## <span data-ttu-id="8194b-105">構文</span><span class="sxs-lookup"><span data-stu-id="8194b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConstructObject(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="8194b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8194b-106">Parameters</span></span>  
 `function`  
 <span data-ttu-id="8194b-107">コンストラクターとして呼び出す関数。</span><span class="sxs-lookup"><span data-stu-id="8194b-107">The function to invoke as a constructor.</span></span>  
  
 `arguments`  
 <span data-ttu-id="8194b-108">呼び出しの引数。</span><span class="sxs-lookup"><span data-stu-id="8194b-108">The arguments to the call.</span></span>  
  
 `argumentCount`  
 <span data-ttu-id="8194b-109">関数に渡される引数の数。</span><span class="sxs-lookup"><span data-stu-id="8194b-109">The number of arguments being passed in to the function.</span></span>  
  
 `result`  
 <span data-ttu-id="8194b-110">関数呼び出しから返される値。</span><span class="sxs-lookup"><span data-stu-id="8194b-110">The value returned from the function invocation.</span></span>  
  
## <span data-ttu-id="8194b-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="8194b-111">Return Value</span></span>  
 <span data-ttu-id="8194b-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="8194b-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8194b-113">注釈</span><span class="sxs-lookup"><span data-stu-id="8194b-113">Remarks</span></span>  
 <span data-ttu-id="8194b-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="8194b-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="8194b-115">要件</span><span class="sxs-lookup"><span data-stu-id="8194b-115">Requirements</span></span>  
 <span data-ttu-id="8194b-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="8194b-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8194b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8194b-117">See Also</span></span>  
 [<span data-ttu-id="8194b-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="8194b-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)