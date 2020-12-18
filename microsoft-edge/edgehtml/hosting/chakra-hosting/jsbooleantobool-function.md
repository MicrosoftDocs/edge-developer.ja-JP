---
description: ブール値 `bool` の値を取得します。
title: JsBooleanToBool 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsBooleanToBool
helpviewer_keywords:
- JsBooleanToBool function
ms.assetid: ab16ac71-fe47-475d-a7ee-46e4643dee60
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 36bf2dc32b94466d8cdea37886e86a42c4ec01d3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234542"
---
# <span data-ttu-id="b86bf-103">JsBooleanToBool 関数</span><span class="sxs-lookup"><span data-stu-id="b86bf-103">JsBooleanToBool Function</span></span>

<span data-ttu-id="b86bf-104">ブール値 `bool` の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b86bf-104">Retrieves the `bool` value of a Boolean value.</span></span>  
  
## <span data-ttu-id="b86bf-105">構文</span><span class="sxs-lookup"><span data-stu-id="b86bf-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsBooleanToBool(  
   _In_ JsValueRef value,  
   _Out_ bool *boolValue  
);  
```  
  
#### <span data-ttu-id="b86bf-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b86bf-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="b86bf-107">変換する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b86bf-107">The value to be converted.</span></span>  
  
 `boolValue`  
 <span data-ttu-id="b86bf-108">変換された値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b86bf-108">The converted value.</span></span>  
  
## <span data-ttu-id="b86bf-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b86bf-109">Return Value</span></span>  
 <span data-ttu-id="b86bf-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b86bf-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b86bf-111">注釈</span><span class="sxs-lookup"><span data-stu-id="b86bf-111">Remarks</span></span>  
 <span data-ttu-id="b86bf-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="b86bf-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b86bf-113">要件</span><span class="sxs-lookup"><span data-stu-id="b86bf-113">Requirements</span></span>  
 <span data-ttu-id="b86bf-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b86bf-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b86bf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b86bf-115">See Also</span></span>  
 [<span data-ttu-id="b86bf-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="b86bf-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
