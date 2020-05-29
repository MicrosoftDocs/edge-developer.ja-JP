---
description: 標準の JavaScript セマンティクスを使って値をオブジェクトに変換します。
title: JsConvertValueToObject 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToObject
helpviewer_keywords:
- JsConvertValueToObject function
ms.assetid: 6528b28a-1d2b-417f-bf78-bf05547c52e1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6a8b1a8933cdcaaf250a2e28ed8fc758ea66cc0e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569383"
---
# <span data-ttu-id="d2718-103">JsConvertValueToObject 関数</span><span class="sxs-lookup"><span data-stu-id="d2718-103">JsConvertValueToObject Function</span></span>
<span data-ttu-id="d2718-104">標準の JavaScript セマンティクスを使って値をオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="d2718-104">Converts the value to object using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="d2718-105">構文</span><span class="sxs-lookup"><span data-stu-id="d2718-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToObject(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="d2718-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2718-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="d2718-107">変換する値。</span><span class="sxs-lookup"><span data-stu-id="d2718-107">The value to be converted.</span></span>  
  
 `object`  
 <span data-ttu-id="d2718-108">変換された値。</span><span class="sxs-lookup"><span data-stu-id="d2718-108">The converted value.</span></span>  
  
## <span data-ttu-id="d2718-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d2718-109">Return Value</span></span>  
 <span data-ttu-id="d2718-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="d2718-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d2718-111">注釈</span><span class="sxs-lookup"><span data-stu-id="d2718-111">Remarks</span></span>  
 <span data-ttu-id="d2718-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="d2718-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="d2718-113">要件</span><span class="sxs-lookup"><span data-stu-id="d2718-113">Requirements</span></span>  
 <span data-ttu-id="d2718-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="d2718-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d2718-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2718-115">See Also</span></span>  
 [<span data-ttu-id="d2718-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d2718-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)