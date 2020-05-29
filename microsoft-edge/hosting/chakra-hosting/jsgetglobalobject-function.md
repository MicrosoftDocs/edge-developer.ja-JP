---
description: 現在のスクリプトコンテキストのグローバルオブジェクトを取得します。
title: JsGetGlobalObject 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetGlobalObject
helpviewer_keywords:
- JsGetGlobalObject function
ms.assetid: d3e91e64-1ca3-4d2b-aada-725ded0fd0b1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9f8b540485e75ef80d42ba66f031b3e827b475fa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569321"
---
# <span data-ttu-id="1febe-103">JsGetGlobalObject 関数</span><span class="sxs-lookup"><span data-stu-id="1febe-103">JsGetGlobalObject Function</span></span>
<span data-ttu-id="1febe-104">現在のスクリプトコンテキストのグローバルオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="1febe-104">Gets the global object in the current script context.</span></span>  
  
## <span data-ttu-id="1febe-105">構文</span><span class="sxs-lookup"><span data-stu-id="1febe-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetGlobalObject(  
   _Out_ JsValueRef *globalObject  
);  
```  
  
#### <span data-ttu-id="1febe-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1febe-106">Parameters</span></span>  
 `globalObject`  
 <span data-ttu-id="1febe-107">グローバルオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1febe-107">The global object.</span></span>  
  
## <span data-ttu-id="1febe-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="1febe-108">Return Value</span></span>  
 <span data-ttu-id="1febe-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="1febe-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1febe-110">注釈</span><span class="sxs-lookup"><span data-stu-id="1febe-110">Remarks</span></span>  
 <span data-ttu-id="1febe-111">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="1febe-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1febe-112">要件</span><span class="sxs-lookup"><span data-stu-id="1febe-112">Requirements</span></span>  
 <span data-ttu-id="1febe-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="1febe-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1febe-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1febe-114">See Also</span></span>  
 [<span data-ttu-id="1febe-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="1febe-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)