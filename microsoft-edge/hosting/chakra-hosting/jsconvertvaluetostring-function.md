---
description: 標準の JavaScript セマンティクスを使って、値を文字列に変換します。
title: JsConvertValueToString 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToString
helpviewer_keywords:
- JsConvertValueToString function
ms.assetid: a97aca04-b2ce-446a-acf4-49cd6777a85c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 21c77ca3050773c07572665c6d58e0ebc05d8ee9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569381"
---
# <span data-ttu-id="90d77-103">JsConvertValueToString 関数</span><span class="sxs-lookup"><span data-stu-id="90d77-103">JsConvertValueToString Function</span></span>
<span data-ttu-id="90d77-104">標準の JavaScript セマンティクスを使って、値を文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="90d77-104">Converts the value to string using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="90d77-105">構文</span><span class="sxs-lookup"><span data-stu-id="90d77-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToString(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *stringValue  
);  
```  
  
#### <span data-ttu-id="90d77-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90d77-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="90d77-107">変換する値。</span><span class="sxs-lookup"><span data-stu-id="90d77-107">The value to be converted.</span></span>  
  
 `stringValue`  
 <span data-ttu-id="90d77-108">変換された値。</span><span class="sxs-lookup"><span data-stu-id="90d77-108">The converted value.</span></span>  
  
## <span data-ttu-id="90d77-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="90d77-109">Return Value</span></span>  
 <span data-ttu-id="90d77-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="90d77-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="90d77-111">注釈</span><span class="sxs-lookup"><span data-stu-id="90d77-111">Remarks</span></span>  
 <span data-ttu-id="90d77-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="90d77-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="90d77-113">要件</span><span class="sxs-lookup"><span data-stu-id="90d77-113">Requirements</span></span>  
 <span data-ttu-id="90d77-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="90d77-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="90d77-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="90d77-115">See Also</span></span>  
 [<span data-ttu-id="90d77-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="90d77-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)