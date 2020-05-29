---
description: JavaScript オブジェクトを作成 `ArrayBuffer` します。
title: JsCreateArrayBuffer 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c9e74184-7dd9-41a7-a1fe-9575e1701392
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 7e81c50317de5243fbcdf761c09c084f97a8e1e0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569380"
---
# <span data-ttu-id="1aad6-103">JsCreateArrayBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="1aad6-103">JsCreateArrayBuffer Function</span></span>
<span data-ttu-id="1aad6-104">JavaScript オブジェクトを作成 `ArrayBuffer` します。</span><span class="sxs-lookup"><span data-stu-id="1aad6-104">Creates a JavaScript `ArrayBuffer` object.</span></span>  
  
## <span data-ttu-id="1aad6-105">構文</span><span class="sxs-lookup"><span data-stu-id="1aad6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArrayBuffer(  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="1aad6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1aad6-106">Parameters</span></span>  
 `byteLength`  
 <span data-ttu-id="1aad6-107">ArrayBuffer のバイト数。</span><span class="sxs-lookup"><span data-stu-id="1aad6-107">The number of bytes in the ArrayBuffer.</span></span>  
  
 `result`  
 <span data-ttu-id="1aad6-108">新しい ArrayBuffer オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1aad6-108">The new ArrayBuffer object.</span></span>  
  
## <span data-ttu-id="1aad6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="1aad6-109">Return Value</span></span>  
 <span data-ttu-id="1aad6-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="1aad6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1aad6-111">注釈</span><span class="sxs-lookup"><span data-stu-id="1aad6-111">Remarks</span></span>  
 <span data-ttu-id="1aad6-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="1aad6-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="1aad6-113">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1aad6-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="1aad6-114">要件</span><span class="sxs-lookup"><span data-stu-id="1aad6-114">Requirements</span></span>  
 <span data-ttu-id="1aad6-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="1aad6-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1aad6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1aad6-116">See Also</span></span>  
 [<span data-ttu-id="1aad6-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="1aad6-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)