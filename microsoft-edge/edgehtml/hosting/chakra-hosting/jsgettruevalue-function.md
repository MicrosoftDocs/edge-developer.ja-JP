---
description: 現在のスクリプト コンテキスト `true` の値を取得します。
title: JsGetTrueValue 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetTrueValue
helpviewer_keywords:
- JsGetTrueValue function
ms.assetid: c2a56d48-344b-492b-90b8-f570710f8310
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 58798e1e8aab57d626be0c8c878f9be39d0af942
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235091"
---
# <span data-ttu-id="10180-103">JsGetTrueValue 関数</span><span class="sxs-lookup"><span data-stu-id="10180-103">JsGetTrueValue Function</span></span>

<span data-ttu-id="10180-104">現在のスクリプト コンテキスト `true` の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="10180-104">Gets the value of `true` in the current script context.</span></span>  
  
## <span data-ttu-id="10180-105">構文</span><span class="sxs-lookup"><span data-stu-id="10180-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTrueValue(  
   _Out_ JsValueRef *trueValue  
);  
```  
  
#### <span data-ttu-id="10180-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10180-106">Parameters</span></span>  
 `trueValue`  
 <span data-ttu-id="10180-107">値 `true` を指定します。</span><span class="sxs-lookup"><span data-stu-id="10180-107">The `true` value.</span></span>  
  
## <span data-ttu-id="10180-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="10180-108">Return Value</span></span>  
 <span data-ttu-id="10180-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="10180-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="10180-110">注釈</span><span class="sxs-lookup"><span data-stu-id="10180-110">Remarks</span></span>  
 <span data-ttu-id="10180-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="10180-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="10180-112">要件</span><span class="sxs-lookup"><span data-stu-id="10180-112">Requirements</span></span>  
 <span data-ttu-id="10180-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="10180-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="10180-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="10180-114">See Also</span></span>  
 [<span data-ttu-id="10180-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="10180-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
