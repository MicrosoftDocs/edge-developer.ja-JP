---
description: JsValueRef の JavaScript 型を取得します。
title: JsGetValueType 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetValueType
helpviewer_keywords:
- JsGetValueType function
ms.assetid: f403cf7c-c8c0-4a17-bfa9-0302d00e760e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b2e9937ca13bf2a680a4a33c07020d06c53efdf3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234394"
---
# <span data-ttu-id="f3fc1-103">JsGetValueType 関数</span><span class="sxs-lookup"><span data-stu-id="f3fc1-103">JsGetValueType Function</span></span>

<span data-ttu-id="f3fc1-104">JsValueRef の JavaScript 型を取得します。</span><span class="sxs-lookup"><span data-stu-id="f3fc1-104">Gets the JavaScript type of a JsValueRef.</span></span>  
  
## <span data-ttu-id="f3fc1-105">構文</span><span class="sxs-lookup"><span data-stu-id="f3fc1-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetValueType(  
   _In_ JsValueRef value,  
   _Out_ JsValueType *type  
);  
```  
  
#### <span data-ttu-id="f3fc1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3fc1-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="f3fc1-107">返される型の値。</span><span class="sxs-lookup"><span data-stu-id="f3fc1-107">The value whose type is to be returned.</span></span>  
  
 `type`  
 <span data-ttu-id="f3fc1-108">値の型。</span><span class="sxs-lookup"><span data-stu-id="f3fc1-108">The type of the value.</span></span>  
  
## <span data-ttu-id="f3fc1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f3fc1-109">Return Value</span></span>  
 <span data-ttu-id="f3fc1-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="f3fc1-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f3fc1-111">注釈</span><span class="sxs-lookup"><span data-stu-id="f3fc1-111">Remarks</span></span>  
 <span data-ttu-id="f3fc1-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f3fc1-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f3fc1-113">要件</span><span class="sxs-lookup"><span data-stu-id="f3fc1-113">Requirements</span></span>  
 <span data-ttu-id="f3fc1-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f3fc1-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f3fc1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3fc1-115">See Also</span></span>  
 [<span data-ttu-id="f3fc1-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f3fc1-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
