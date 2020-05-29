---
description: 新しい JavaScript TypeError エラーオブジェクトを作成します。
title: JsCreateTypeError 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateTypeError
helpviewer_keywords:
- JsCreateTypeError function
ms.assetid: 8ef7bb77-2c98-482a-bccb-1f0fe2b826f5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 302bf75af3668dfdd0b40336e940e3eef3a74bce
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569346"
---
# <span data-ttu-id="eefb1-103">JsCreateTypeError 関数</span><span class="sxs-lookup"><span data-stu-id="eefb1-103">JsCreateTypeError Function</span></span>
<span data-ttu-id="eefb1-104">新しい JavaScript TypeError エラーオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="eefb1-104">Creates a new JavaScript TypeError error object.</span></span>  
  
## <span data-ttu-id="eefb1-105">構文</span><span class="sxs-lookup"><span data-stu-id="eefb1-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypeError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="eefb1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eefb1-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="eefb1-107">Error オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="eefb1-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="eefb1-108">新しいエラーオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="eefb1-108">The new error object.</span></span>  
  
## <span data-ttu-id="eefb1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="eefb1-109">Return Value</span></span>  
 <span data-ttu-id="eefb1-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="eefb1-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="eefb1-111">注釈</span><span class="sxs-lookup"><span data-stu-id="eefb1-111">Remarks</span></span>  
 <span data-ttu-id="eefb1-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="eefb1-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="eefb1-113">要件</span><span class="sxs-lookup"><span data-stu-id="eefb1-113">Requirements</span></span>  
 <span data-ttu-id="eefb1-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="eefb1-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="eefb1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="eefb1-115">See Also</span></span>  
 [<span data-ttu-id="eefb1-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="eefb1-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)