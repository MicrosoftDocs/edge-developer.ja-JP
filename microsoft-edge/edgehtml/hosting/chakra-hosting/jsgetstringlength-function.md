---
description: 文字列値の長さを取得します。
title: JsGetStringLength 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetStringLength
helpviewer_keywords:
- JsGetStringLength function
ms.assetid: e9f9f28c-e644-439c-aee5-7ce362f71347
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 10fd6be4bb839ccb9eb64c99931cdb474e3aa7a2
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235096"
---
# <span data-ttu-id="07143-103">JsGetStringLength 関数</span><span class="sxs-lookup"><span data-stu-id="07143-103">JsGetStringLength Function</span></span>

<span data-ttu-id="07143-104">文字列値の長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="07143-104">Gets the length of a string value.</span></span>  
  
## <span data-ttu-id="07143-105">構文</span><span class="sxs-lookup"><span data-stu-id="07143-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetStringLength(  
   _In_ JsValueRef stringValue,  
   _Out_ int *length  
);  
```  
  
#### <span data-ttu-id="07143-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07143-106">Parameters</span></span>  
 `stringValue`  
 <span data-ttu-id="07143-107">長さを取得する文字列値。</span><span class="sxs-lookup"><span data-stu-id="07143-107">The string value to get the length of.</span></span>  
  
 `length`  
 <span data-ttu-id="07143-108">文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="07143-108">The length of the string.</span></span>  
  
## <span data-ttu-id="07143-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="07143-109">Return Value</span></span>  
 <span data-ttu-id="07143-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="07143-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="07143-111">注釈</span><span class="sxs-lookup"><span data-stu-id="07143-111">Remarks</span></span>  
 <span data-ttu-id="07143-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="07143-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="07143-113">要件</span><span class="sxs-lookup"><span data-stu-id="07143-113">Requirements</span></span>  
 <span data-ttu-id="07143-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="07143-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="07143-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="07143-115">See Also</span></span>  
 [<span data-ttu-id="07143-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="07143-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
