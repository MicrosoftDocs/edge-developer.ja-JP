---
description: 新しい JavaScript ReferenceError エラーオブジェクトを作成します。
title: JsCreateReferenceError 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateReferenceError
helpviewer_keywords:
- JsCreateReferenceError function
ms.assetid: 1d0b2339-4bea-4dd0-a46a-4dcbf0be3bd8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 958af7111a233077aa7a2c2391b26666f55c634b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569358"
---
# <span data-ttu-id="48fbf-103">JsCreateReferenceError 関数</span><span class="sxs-lookup"><span data-stu-id="48fbf-103">JsCreateReferenceError Function</span></span>
<span data-ttu-id="48fbf-104">新しい JavaScript ReferenceError エラーオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="48fbf-104">Creates a new JavaScript ReferenceError error object.</span></span>
  
## <span data-ttu-id="48fbf-105">構文</span><span class="sxs-lookup"><span data-stu-id="48fbf-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateReferenceError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="48fbf-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48fbf-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="48fbf-107">Error オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="48fbf-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="48fbf-108">新しいエラーオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="48fbf-108">The new error object.</span></span>  
  
## <span data-ttu-id="48fbf-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="48fbf-109">Return Value</span></span>  
 <span data-ttu-id="48fbf-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="48fbf-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="48fbf-111">注釈</span><span class="sxs-lookup"><span data-stu-id="48fbf-111">Remarks</span></span>  
 <span data-ttu-id="48fbf-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="48fbf-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="48fbf-113">要件</span><span class="sxs-lookup"><span data-stu-id="48fbf-113">Requirements</span></span>  
 <span data-ttu-id="48fbf-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="48fbf-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="48fbf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="48fbf-115">See Also</span></span>  
 [<span data-ttu-id="48fbf-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="48fbf-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)