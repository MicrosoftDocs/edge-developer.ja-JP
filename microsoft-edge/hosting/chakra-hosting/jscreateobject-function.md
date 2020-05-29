---
description: 新しいオブジェクトを作成します。
title: JsCreateObject 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateObject
helpviewer_keywords:
- JsCreateObject function
ms.assetid: 6c1d01a4-9254-443e-b974-6f0b0c861ca2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9ed988aae0921978819d379562d4a966e4a082a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569361"
---
# <span data-ttu-id="f1e9f-103">JsCreateObject 関数</span><span class="sxs-lookup"><span data-stu-id="f1e9f-103">JsCreateObject Function</span></span>
<span data-ttu-id="f1e9f-104">新しいオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1e9f-104">Creates a new object.</span></span>
  
## <span data-ttu-id="f1e9f-105">構文</span><span class="sxs-lookup"><span data-stu-id="f1e9f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateObject(  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="f1e9f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1e9f-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="f1e9f-107">新しいオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f1e9f-107">The new object.</span></span>  
  
## <span data-ttu-id="f1e9f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1e9f-108">Return Value</span></span>  
 <span data-ttu-id="f1e9f-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="f1e9f-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f1e9f-110">注釈</span><span class="sxs-lookup"><span data-stu-id="f1e9f-110">Remarks</span></span>  
 <span data-ttu-id="f1e9f-111">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1e9f-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f1e9f-112">要件</span><span class="sxs-lookup"><span data-stu-id="f1e9f-112">Requirements</span></span>  
 <span data-ttu-id="f1e9f-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="f1e9f-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f1e9f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1e9f-114">See Also</span></span>  
 [<span data-ttu-id="f1e9f-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="f1e9f-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)