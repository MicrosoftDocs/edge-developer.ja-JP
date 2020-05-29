---
description: コンテキストが属しているランタイムを取得します。
title: JsGetRuntime 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntime
helpviewer_keywords:
- JsGetRuntime function
ms.assetid: 5b62e940-a885-405a-9fdd-0495fb391b95
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6eeb132dd35fcb5104828bef8e8f27334a5f34e4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569313"
---
# <span data-ttu-id="53623-103">JsGetRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="53623-103">JsGetRuntime Function</span></span>
<span data-ttu-id="53623-104">コンテキストが属しているランタイムを取得します。</span><span class="sxs-lookup"><span data-stu-id="53623-104">Gets the runtime that the context belongs to.</span></span>  
  
## <span data-ttu-id="53623-105">構文</span><span class="sxs-lookup"><span data-stu-id="53623-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntime(  
   _In_ JsContextRef context,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### <span data-ttu-id="53623-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53623-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="53623-107">ランタイムを取得するコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="53623-107">The context to get the runtime from.</span></span>  
  
 `runtime`  
 <span data-ttu-id="53623-108">コンテキストが属しているランタイム。</span><span class="sxs-lookup"><span data-stu-id="53623-108">The runtime the context belongs to.</span></span>  
  
## <span data-ttu-id="53623-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="53623-109">Return Value</span></span>  
 <span data-ttu-id="53623-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="53623-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="53623-111">要件</span><span class="sxs-lookup"><span data-stu-id="53623-111">Requirements</span></span>  
 <span data-ttu-id="53623-112">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="53623-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="53623-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="53623-113">See Also</span></span>  
 [<span data-ttu-id="53623-114">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="53623-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)