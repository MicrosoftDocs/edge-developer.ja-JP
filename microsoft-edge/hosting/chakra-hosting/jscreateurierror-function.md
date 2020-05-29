---
description: 新しい JavaScript URIError エラーオブジェクトを作成します。
title: JsCreateURIError 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateURIError
helpviewer_keywords:
- JsCreateURIError function
ms.assetid: 711fd237-12a2-4ff0-b58a-ad74c91e79fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5188827cd0b89b1dd6b54af005f6e118c4ae4c94
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569345"
---
# <span data-ttu-id="4532e-103">JsCreateURIError 関数</span><span class="sxs-lookup"><span data-stu-id="4532e-103">JsCreateURIError Function</span></span>
<span data-ttu-id="4532e-104">新しい JavaScript URIError エラーオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4532e-104">Creates a new JavaScript URIError error object.</span></span>  
  
## <span data-ttu-id="4532e-105">構文</span><span class="sxs-lookup"><span data-stu-id="4532e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateURIError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="4532e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4532e-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="4532e-107">Error オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4532e-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="4532e-108">新しいエラーオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4532e-108">The new error object.</span></span>  
  
## <span data-ttu-id="4532e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4532e-109">Return Value</span></span>  
 <span data-ttu-id="4532e-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="4532e-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4532e-111">注釈</span><span class="sxs-lookup"><span data-stu-id="4532e-111">Remarks</span></span>  
 <span data-ttu-id="4532e-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="4532e-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="4532e-113">要件</span><span class="sxs-lookup"><span data-stu-id="4532e-113">Requirements</span></span>  
 <span data-ttu-id="4532e-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="4532e-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4532e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4532e-115">See Also</span></span>  
 [<span data-ttu-id="4532e-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="4532e-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)