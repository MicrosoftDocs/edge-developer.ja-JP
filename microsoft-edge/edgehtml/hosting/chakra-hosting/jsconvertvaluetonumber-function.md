---
description: 標準の JavaScript セマンティクスを使用して値を数値に変換します。
title: JsConvertValueToNumber 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToNumber
helpviewer_keywords:
- JsConvertValueToNumber function
ms.assetid: c47b8653-0591-4863-b8b5-33187b315816
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8d00950ef3835c6d75f8f55ffe5002b32c6ee160
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234548"
---
# <span data-ttu-id="9abde-103">JsConvertValueToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="9abde-103">JsConvertValueToNumber Function</span></span>

<span data-ttu-id="9abde-104">標準の JavaScript セマンティクスを使用して値を数値に変換します。</span><span class="sxs-lookup"><span data-stu-id="9abde-104">Converts the value to number using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="9abde-105">構文</span><span class="sxs-lookup"><span data-stu-id="9abde-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToNumber(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *numberValue  
);  
```  
  
#### <span data-ttu-id="9abde-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9abde-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="9abde-107">変換する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9abde-107">The value to be converted.</span></span>  
  
 `numberValue`  
 <span data-ttu-id="9abde-108">変換された値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9abde-108">The converted value.</span></span>  
  
## <span data-ttu-id="9abde-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="9abde-109">Return Value</span></span>  
 <span data-ttu-id="9abde-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="9abde-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9abde-111">注釈</span><span class="sxs-lookup"><span data-stu-id="9abde-111">Remarks</span></span>  
 <span data-ttu-id="9abde-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="9abde-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9abde-113">要件</span><span class="sxs-lookup"><span data-stu-id="9abde-113">Requirements</span></span>  
 <span data-ttu-id="9abde-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9abde-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9abde-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9abde-115">See Also</span></span>  
 [<span data-ttu-id="9abde-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="9abde-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
