---
description: 標準の JavaScript セマンティクスを使用して値をオブジェクトに変換します。
title: JsConvertValueToObject 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToObject
helpviewer_keywords:
- JsConvertValueToObject function
ms.assetid: 6528b28a-1d2b-417f-bf78-bf05547c52e1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6f3676b512585b0750c994bcfcdf9d2e6e4e1cc3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234531"
---
# <span data-ttu-id="aa58a-103">JsConvertValueToObject 関数</span><span class="sxs-lookup"><span data-stu-id="aa58a-103">JsConvertValueToObject Function</span></span>

<span data-ttu-id="aa58a-104">標準の JavaScript セマンティクスを使用して値をオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="aa58a-104">Converts the value to object using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="aa58a-105">構文</span><span class="sxs-lookup"><span data-stu-id="aa58a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToObject(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="aa58a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa58a-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="aa58a-107">変換する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa58a-107">The value to be converted.</span></span>  
  
 `object`  
 <span data-ttu-id="aa58a-108">変換された値を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa58a-108">The converted value.</span></span>  
  
## <span data-ttu-id="aa58a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="aa58a-109">Return Value</span></span>  
 <span data-ttu-id="aa58a-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="aa58a-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="aa58a-111">注釈</span><span class="sxs-lookup"><span data-stu-id="aa58a-111">Remarks</span></span>  
 <span data-ttu-id="aa58a-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="aa58a-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="aa58a-113">要件</span><span class="sxs-lookup"><span data-stu-id="aa58a-113">Requirements</span></span>  
 <span data-ttu-id="aa58a-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="aa58a-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="aa58a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa58a-115">See Also</span></span>  
 [<span data-ttu-id="aa58a-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="aa58a-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
