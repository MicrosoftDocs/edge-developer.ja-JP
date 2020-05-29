---
description: '`bool`ブール値の値を取得します。'
title: JsBooleanToBool 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsBooleanToBool
helpviewer_keywords:
- JsBooleanToBool function
ms.assetid: ab16ac71-fe47-475d-a7ee-46e4643dee60
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 55b0ef1278cbc73652fc8427e004cab002d76e5b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569401"
---
# <span data-ttu-id="5f4f7-103">JsBooleanToBool 関数</span><span class="sxs-lookup"><span data-stu-id="5f4f7-103">JsBooleanToBool Function</span></span>
<span data-ttu-id="5f4f7-104">`bool`ブール値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5f4f7-104">Retrieves the `bool` value of a Boolean value.</span></span>  
  
## <span data-ttu-id="5f4f7-105">構文</span><span class="sxs-lookup"><span data-stu-id="5f4f7-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsBooleanToBool(  
   _In_ JsValueRef value,  
   _Out_ bool *boolValue  
);  
```  
  
#### <span data-ttu-id="5f4f7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f4f7-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="5f4f7-107">変換する値。</span><span class="sxs-lookup"><span data-stu-id="5f4f7-107">The value to be converted.</span></span>  
  
 `boolValue`  
 <span data-ttu-id="5f4f7-108">変換された値。</span><span class="sxs-lookup"><span data-stu-id="5f4f7-108">The converted value.</span></span>  
  
## <span data-ttu-id="5f4f7-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5f4f7-109">Return Value</span></span>  
 <span data-ttu-id="5f4f7-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="5f4f7-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5f4f7-111">注釈</span><span class="sxs-lookup"><span data-stu-id="5f4f7-111">Remarks</span></span>  
 <span data-ttu-id="5f4f7-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5f4f7-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5f4f7-113">要件</span><span class="sxs-lookup"><span data-stu-id="5f4f7-113">Requirements</span></span>  
 <span data-ttu-id="5f4f7-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="5f4f7-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5f4f7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f4f7-115">See Also</span></span>  
 [<span data-ttu-id="5f4f7-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5f4f7-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)