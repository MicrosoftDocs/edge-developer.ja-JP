---
description: 標準の JavaScript セマンティクスを使って、値を数値に変換します。
title: JsConvertValueToNumber 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToNumber
helpviewer_keywords:
- JsConvertValueToNumber function
ms.assetid: c47b8653-0591-4863-b8b5-33187b315816
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 3b3f450a58aaf1c434e1d34cd51577e3a5a9ee31
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569384"
---
# <span data-ttu-id="dcabe-103">JsConvertValueToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="dcabe-103">JsConvertValueToNumber Function</span></span>
<span data-ttu-id="dcabe-104">標準の JavaScript セマンティクスを使って、値を数値に変換します。</span><span class="sxs-lookup"><span data-stu-id="dcabe-104">Converts the value to number using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="dcabe-105">構文</span><span class="sxs-lookup"><span data-stu-id="dcabe-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToNumber(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *numberValue  
);  
```  
  
#### <span data-ttu-id="dcabe-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dcabe-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="dcabe-107">変換する値。</span><span class="sxs-lookup"><span data-stu-id="dcabe-107">The value to be converted.</span></span>  
  
 `numberValue`  
 <span data-ttu-id="dcabe-108">変換された値。</span><span class="sxs-lookup"><span data-stu-id="dcabe-108">The converted value.</span></span>  
  
## <span data-ttu-id="dcabe-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="dcabe-109">Return Value</span></span>  
 <span data-ttu-id="dcabe-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="dcabe-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="dcabe-111">注釈</span><span class="sxs-lookup"><span data-stu-id="dcabe-111">Remarks</span></span>  
 <span data-ttu-id="dcabe-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="dcabe-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="dcabe-113">要件</span><span class="sxs-lookup"><span data-stu-id="dcabe-113">Requirements</span></span>  
 <span data-ttu-id="dcabe-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="dcabe-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="dcabe-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcabe-115">See Also</span></span>  
 [<span data-ttu-id="dcabe-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="dcabe-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)