---
description: 新しい JavaScript SyntaxError error オブジェクトを作成します。
title: JsCreateSyntaxError 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateSyntaxError
helpviewer_keywords:
- JsCreateSyntaxError function
ms.assetid: 839845fc-60c4-4ffc-bfcc-fd7a8f06126f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 8f7459e8300df56aa8ccfaa78ef97ce2b6ec6fa0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569349"
---
# <span data-ttu-id="f10a8-103">JsCreateSyntaxError 関数</span><span class="sxs-lookup"><span data-stu-id="f10a8-103">JsCreateSyntaxError Function</span></span>
<span data-ttu-id="f10a8-104">新しい JavaScript SyntaxError error オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f10a8-104">Creates a new JavaScript SyntaxError error object.</span></span>  
  
## <span data-ttu-id="f10a8-105">構文</span><span class="sxs-lookup"><span data-stu-id="f10a8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateSyntaxError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="f10a8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f10a8-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="f10a8-107">Error オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="f10a8-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="f10a8-108">新しいエラーオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f10a8-108">The new error object.</span></span>  
  
## <span data-ttu-id="f10a8-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f10a8-109">Return Value</span></span>  
 <span data-ttu-id="f10a8-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="f10a8-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f10a8-111">注釈</span><span class="sxs-lookup"><span data-stu-id="f10a8-111">Remarks</span></span>  
 <span data-ttu-id="f10a8-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f10a8-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f10a8-113">要件</span><span class="sxs-lookup"><span data-stu-id="f10a8-113">Requirements</span></span>  
 <span data-ttu-id="f10a8-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="f10a8-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f10a8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f10a8-115">See Also</span></span>  
 [<span data-ttu-id="f10a8-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="f10a8-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)