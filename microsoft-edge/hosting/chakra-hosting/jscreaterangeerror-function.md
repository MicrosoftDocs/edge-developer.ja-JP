---
description: 新しい JavaScript RangeError エラーオブジェクトを作成します。
title: JsCreateRangeError 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRangeError
helpviewer_keywords:
- JsCreateRangeError function
ms.assetid: 0ab05de7-57af-4cfd-9aa5-0a69a893cc97
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 3759f1c04a2eb13488f756ae2c135373d9db1f74
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569360"
---
# <span data-ttu-id="22266-103">JsCreateRangeError 関数</span><span class="sxs-lookup"><span data-stu-id="22266-103">JsCreateRangeError Function</span></span>
<span data-ttu-id="22266-104">新しい JavaScript RangeError エラーオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="22266-104">Creates a new JavaScript RangeError error object.</span></span>
  
## <span data-ttu-id="22266-105">構文</span><span class="sxs-lookup"><span data-stu-id="22266-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateRangeError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="22266-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22266-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="22266-107">Error オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="22266-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="22266-108">新しいエラーオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="22266-108">The new error object.</span></span>  
  
## <span data-ttu-id="22266-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="22266-109">Return Value</span></span>  
 <span data-ttu-id="22266-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="22266-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="22266-111">注釈</span><span class="sxs-lookup"><span data-stu-id="22266-111">Remarks</span></span>  
 <span data-ttu-id="22266-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="22266-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="22266-113">要件</span><span class="sxs-lookup"><span data-stu-id="22266-113">Requirements</span></span>  
 <span data-ttu-id="22266-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="22266-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="22266-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="22266-115">See Also</span></span>  
 [<span data-ttu-id="22266-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="22266-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)