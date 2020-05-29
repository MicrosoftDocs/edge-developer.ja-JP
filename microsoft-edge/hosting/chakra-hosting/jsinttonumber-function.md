---
description: 値から数値を作成し `int` ます。
title: JsIntToNumber 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1393c4ac-7189-4e9c-8e54-b0e041c22112
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: dd8f51638292346ec3058f9537d72b8fd21bebc6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569297"
---
# <span data-ttu-id="ef2b6-103">JsIntToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="ef2b6-103">JsIntToNumber Function</span></span>
<span data-ttu-id="ef2b6-104">値から数値を作成し `int` ます。</span><span class="sxs-lookup"><span data-stu-id="ef2b6-104">Creates a number value from an `int` value.</span></span>  
  
## <span data-ttu-id="ef2b6-105">構文</span><span class="sxs-lookup"><span data-stu-id="ef2b6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIntToNumber(  
   _In_ int intValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="ef2b6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef2b6-106">Parameters</span></span>  
 `intValue`  
 <span data-ttu-id="ef2b6-107">`int`数値に変換するには、を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef2b6-107">The `int` to convert to a number value.</span></span>  
  
 `value`  
 <span data-ttu-id="ef2b6-108">新しい数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef2b6-108">The new number value.</span></span>  
  
## <span data-ttu-id="ef2b6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ef2b6-109">Return Value</span></span>  
 <span data-ttu-id="ef2b6-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="ef2b6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ef2b6-111">注釈</span><span class="sxs-lookup"><span data-stu-id="ef2b6-111">Remarks</span></span>  
 <span data-ttu-id="ef2b6-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ef2b6-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ef2b6-113">要件</span><span class="sxs-lookup"><span data-stu-id="ef2b6-113">Requirements</span></span>  
 <span data-ttu-id="ef2b6-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="ef2b6-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ef2b6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef2b6-115">See Also</span></span>  
 [<span data-ttu-id="ef2b6-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ef2b6-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)