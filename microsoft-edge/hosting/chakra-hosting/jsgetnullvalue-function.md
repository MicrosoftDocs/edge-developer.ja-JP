---
description: 現在のスクリプトコンテキスト内の値を取得し `null` ます。
title: JsGetNullValue 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetNullValue
helpviewer_keywords:
- JsGetNullValue function
ms.assetid: 132a1496-8dfe-4d3c-a8f8-389f5b0b50d2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 84164aa9ce5d522b0933d928d85b26c652be066f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570456"
---
# <span data-ttu-id="29be6-103">JsGetNullValue 関数</span><span class="sxs-lookup"><span data-stu-id="29be6-103">JsGetNullValue Function</span></span>
<span data-ttu-id="29be6-104">現在のスクリプトコンテキスト内の値を取得し `null` ます。</span><span class="sxs-lookup"><span data-stu-id="29be6-104">Gets the value of `null` in the current script context.</span></span>  
  
## <span data-ttu-id="29be6-105">構文</span><span class="sxs-lookup"><span data-stu-id="29be6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetNullValue(  
   _Out_ JsValueRef *nullValue  
);  
```  
  
#### <span data-ttu-id="29be6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29be6-106">Parameters</span></span>  
 `nullValue`  
 <span data-ttu-id="29be6-107">`null`値。</span><span class="sxs-lookup"><span data-stu-id="29be6-107">The `null` value.</span></span>  
  
## <span data-ttu-id="29be6-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="29be6-108">Return Value</span></span>  
 <span data-ttu-id="29be6-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="29be6-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="29be6-110">注釈</span><span class="sxs-lookup"><span data-stu-id="29be6-110">Remarks</span></span>  
 <span data-ttu-id="29be6-111">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="29be6-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="29be6-112">要件</span><span class="sxs-lookup"><span data-stu-id="29be6-112">Requirements</span></span>  
 <span data-ttu-id="29be6-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="29be6-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="29be6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="29be6-114">See Also</span></span>  
 [<span data-ttu-id="29be6-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="29be6-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)