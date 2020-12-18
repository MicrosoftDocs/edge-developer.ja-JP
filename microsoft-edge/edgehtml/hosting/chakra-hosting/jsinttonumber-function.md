---
description: 値から数値を作成 `int` します。
title: JsIntToNumber 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 1393c4ac-7189-4e9c-8e54-b0e041c22112
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 24e861d1535ae79843fb35de8a047031a479fe16
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234909"
---
# <span data-ttu-id="7be4d-103">JsIntToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="7be4d-103">JsIntToNumber Function</span></span>

<span data-ttu-id="7be4d-104">値から数値を作成 `int` します。</span><span class="sxs-lookup"><span data-stu-id="7be4d-104">Creates a number value from an `int` value.</span></span>  
  
## <span data-ttu-id="7be4d-105">構文</span><span class="sxs-lookup"><span data-stu-id="7be4d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIntToNumber(  
   _In_ int intValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="7be4d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7be4d-106">Parameters</span></span>  
 `intValue`  
 <span data-ttu-id="7be4d-107">数値 `int` に変換する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7be4d-107">The `int` to convert to a number value.</span></span>  
  
 `value`  
 <span data-ttu-id="7be4d-108">新しい数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7be4d-108">The new number value.</span></span>  
  
## <span data-ttu-id="7be4d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7be4d-109">Return Value</span></span>  
 <span data-ttu-id="7be4d-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="7be4d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7be4d-111">注釈</span><span class="sxs-lookup"><span data-stu-id="7be4d-111">Remarks</span></span>  
 <span data-ttu-id="7be4d-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="7be4d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="7be4d-113">要件</span><span class="sxs-lookup"><span data-stu-id="7be4d-113">Requirements</span></span>  
 <span data-ttu-id="7be4d-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="7be4d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7be4d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7be4d-115">See Also</span></span>  
 [<span data-ttu-id="7be4d-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="7be4d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
