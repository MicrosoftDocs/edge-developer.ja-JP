---
description: 現在のスクリプト コンテキスト `undefined` の値を取得します。
title: JsGetUndefinedValue 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetUndefinedValue
helpviewer_keywords:
- JsGetUndefinedValue function
ms.assetid: e118eaf6-452c-42f2-86b8-e63c7d987cba
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 34bfaec4548ee2b77d6d98749c3049bb8f679134
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234389"
---
# <span data-ttu-id="0f887-103">JsGetUndefinedValue 関数</span><span class="sxs-lookup"><span data-stu-id="0f887-103">JsGetUndefinedValue Function</span></span>

<span data-ttu-id="0f887-104">現在のスクリプト コンテキスト `undefined` の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f887-104">Gets the value of `undefined` in the current script context.</span></span>  
  
## <span data-ttu-id="0f887-105">構文</span><span class="sxs-lookup"><span data-stu-id="0f887-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetUndefinedValue(  
   _Out_ JsValueRef *undefinedValue  
);  
```  
  
#### <span data-ttu-id="0f887-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f887-106">Parameters</span></span>  
 `undefinedValue`  
 <span data-ttu-id="0f887-107">値 `undefined` を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f887-107">The `undefined` value.</span></span>  
  
## <span data-ttu-id="0f887-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0f887-108">Return Value</span></span>  
 <span data-ttu-id="0f887-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0f887-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0f887-110">注釈</span><span class="sxs-lookup"><span data-stu-id="0f887-110">Remarks</span></span>  
 <span data-ttu-id="0f887-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f887-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0f887-112">要件</span><span class="sxs-lookup"><span data-stu-id="0f887-112">Requirements</span></span>  
 <span data-ttu-id="0f887-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="0f887-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0f887-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f887-114">See Also</span></span>  
 [<span data-ttu-id="0f887-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="0f887-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
