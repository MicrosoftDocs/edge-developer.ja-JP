---
description: 現在のスクリプトコンテキスト内の値を取得し `undefined` ます。
title: JsGetUndefinedValue 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetUndefinedValue
helpviewer_keywords:
- JsGetUndefinedValue function
ms.assetid: e118eaf6-452c-42f2-86b8-e63c7d987cba
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5edd536a29f5003591de476cb5d21ddb64f48c0b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570437"
---
# <span data-ttu-id="af285-103">JsGetUndefinedValue 関数</span><span class="sxs-lookup"><span data-stu-id="af285-103">JsGetUndefinedValue Function</span></span>
<span data-ttu-id="af285-104">現在のスクリプトコンテキスト内の値を取得し `undefined` ます。</span><span class="sxs-lookup"><span data-stu-id="af285-104">Gets the value of `undefined` in the current script context.</span></span>  
  
## <span data-ttu-id="af285-105">構文</span><span class="sxs-lookup"><span data-stu-id="af285-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetUndefinedValue(  
   _Out_ JsValueRef *undefinedValue  
);  
```  
  
#### <span data-ttu-id="af285-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af285-106">Parameters</span></span>  
 `undefinedValue`  
 <span data-ttu-id="af285-107">`undefined`値。</span><span class="sxs-lookup"><span data-stu-id="af285-107">The `undefined` value.</span></span>  
  
## <span data-ttu-id="af285-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="af285-108">Return Value</span></span>  
 <span data-ttu-id="af285-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="af285-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="af285-110">注釈</span><span class="sxs-lookup"><span data-stu-id="af285-110">Remarks</span></span>  
 <span data-ttu-id="af285-111">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="af285-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="af285-112">要件</span><span class="sxs-lookup"><span data-stu-id="af285-112">Requirements</span></span>  
 <span data-ttu-id="af285-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="af285-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="af285-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="af285-114">See Also</span></span>  
 [<span data-ttu-id="af285-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="af285-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)