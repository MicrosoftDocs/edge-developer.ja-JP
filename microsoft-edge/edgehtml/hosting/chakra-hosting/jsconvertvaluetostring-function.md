---
description: 標準の JavaScript セマンティクスを使用して値を文字列に変換します。
title: JsConvertValueToString 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToString
helpviewer_keywords:
- JsConvertValueToString function
ms.assetid: a97aca04-b2ce-446a-acf4-49cd6777a85c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 499f9555f6385b8458524fb4e14b92339c0aa478
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234530"
---
# <span data-ttu-id="defe2-103">JsConvertValueToString 関数</span><span class="sxs-lookup"><span data-stu-id="defe2-103">JsConvertValueToString Function</span></span>

<span data-ttu-id="defe2-104">標準の JavaScript セマンティクスを使用して値を文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="defe2-104">Converts the value to string using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="defe2-105">構文</span><span class="sxs-lookup"><span data-stu-id="defe2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToString(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *stringValue  
);  
```  
  
#### <span data-ttu-id="defe2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="defe2-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="defe2-107">変換する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe2-107">The value to be converted.</span></span>  
  
 `stringValue`  
 <span data-ttu-id="defe2-108">変換された値を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe2-108">The converted value.</span></span>  
  
## <span data-ttu-id="defe2-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="defe2-109">Return Value</span></span>  
 <span data-ttu-id="defe2-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="defe2-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="defe2-111">注釈</span><span class="sxs-lookup"><span data-stu-id="defe2-111">Remarks</span></span>  
 <span data-ttu-id="defe2-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="defe2-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="defe2-113">要件</span><span class="sxs-lookup"><span data-stu-id="defe2-113">Requirements</span></span>  
 <span data-ttu-id="defe2-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="defe2-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="defe2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="defe2-115">See Also</span></span>  
 [<span data-ttu-id="defe2-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="defe2-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
