---
description: Javascript の配列オブジェクトを作成します。
title: JsCreateArray 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateArray
helpviewer_keywords:
- JsCreateArray function
ms.assetid: a119949a-e427-4349-9d00-5ec20fb9319c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: fb6a65df1484eb308224a42bb5a65443855c6215
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569379"
---
# <span data-ttu-id="5e1e8-103">JsCreateArray 関数</span><span class="sxs-lookup"><span data-stu-id="5e1e8-103">JsCreateArray Function</span></span>
<span data-ttu-id="5e1e8-104">Javascript の配列オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e1e8-104">Creates a Javascript array object.</span></span>  
  
## <span data-ttu-id="5e1e8-105">構文</span><span class="sxs-lookup"><span data-stu-id="5e1e8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArray(  
   _In_ unsigned int length,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="5e1e8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e1e8-106">Parameters</span></span>  
 `length`  
 <span data-ttu-id="5e1e8-107">配列の初期の長さ。</span><span class="sxs-lookup"><span data-stu-id="5e1e8-107">The initial length of the array.</span></span>  
  
 `result`  
 <span data-ttu-id="5e1e8-108">新しい配列オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5e1e8-108">The new array object.</span></span>  
  
## <span data-ttu-id="5e1e8-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5e1e8-109">Return Value</span></span>  
 <span data-ttu-id="5e1e8-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="5e1e8-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5e1e8-111">注釈</span><span class="sxs-lookup"><span data-stu-id="5e1e8-111">Remarks</span></span>  
 <span data-ttu-id="5e1e8-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5e1e8-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5e1e8-113">要件</span><span class="sxs-lookup"><span data-stu-id="5e1e8-113">Requirements</span></span>  
 <span data-ttu-id="5e1e8-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="5e1e8-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5e1e8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e1e8-115">See Also</span></span>  
 [<span data-ttu-id="5e1e8-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5e1e8-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)