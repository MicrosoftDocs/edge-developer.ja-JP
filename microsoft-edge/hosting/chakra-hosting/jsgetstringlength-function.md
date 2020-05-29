---
description: 文字列値の長さを取得します。
title: JsGetStringLength 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetStringLength
helpviewer_keywords:
- JsGetStringLength function
ms.assetid: e9f9f28c-e644-439c-aee5-7ce362f71347
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6b562b2dc58341523910db41fb8b748453b2a836
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569309"
---
# <span data-ttu-id="22701-103">JsGetStringLength 関数</span><span class="sxs-lookup"><span data-stu-id="22701-103">JsGetStringLength Function</span></span>
<span data-ttu-id="22701-104">文字列値の長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="22701-104">Gets the length of a string value.</span></span>  
  
## <span data-ttu-id="22701-105">構文</span><span class="sxs-lookup"><span data-stu-id="22701-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetStringLength(  
   _In_ JsValueRef stringValue,  
   _Out_ int *length  
);  
```  
  
#### <span data-ttu-id="22701-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22701-106">Parameters</span></span>  
 `stringValue`  
 <span data-ttu-id="22701-107">長さを取得する文字列値。</span><span class="sxs-lookup"><span data-stu-id="22701-107">The string value to get the length of.</span></span>  
  
 `length`  
 <span data-ttu-id="22701-108">文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="22701-108">The length of the string.</span></span>  
  
## <span data-ttu-id="22701-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="22701-109">Return Value</span></span>  
 <span data-ttu-id="22701-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="22701-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="22701-111">注釈</span><span class="sxs-lookup"><span data-stu-id="22701-111">Remarks</span></span>  
 <span data-ttu-id="22701-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="22701-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="22701-113">要件</span><span class="sxs-lookup"><span data-stu-id="22701-113">Requirements</span></span>  
 <span data-ttu-id="22701-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="22701-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="22701-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="22701-115">See Also</span></span>  
 [<span data-ttu-id="22701-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="22701-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)