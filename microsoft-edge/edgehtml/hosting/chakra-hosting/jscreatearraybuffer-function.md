---
description: JavaScript オブジェクトを作成 `ArrayBuffer` します。
title: JsCreateArrayBuffer 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c9e74184-7dd9-41a7-a1fe-9575e1701392
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3bee44d77f78bd35705211c598db78ab09000c71
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234525"
---
# <span data-ttu-id="ef3bb-103">JsCreateArrayBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="ef3bb-103">JsCreateArrayBuffer Function</span></span>

<span data-ttu-id="ef3bb-104">JavaScript オブジェクトを作成 `ArrayBuffer` します。</span><span class="sxs-lookup"><span data-stu-id="ef3bb-104">Creates a JavaScript `ArrayBuffer` object.</span></span>  
  
## <span data-ttu-id="ef3bb-105">構文</span><span class="sxs-lookup"><span data-stu-id="ef3bb-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArrayBuffer(  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="ef3bb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef3bb-106">Parameters</span></span>  
 `byteLength`  
 <span data-ttu-id="ef3bb-107">ArrayBuffer 内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="ef3bb-107">The number of bytes in the ArrayBuffer.</span></span>  
  
 `result`  
 <span data-ttu-id="ef3bb-108">新しい ArrayBuffer オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ef3bb-108">The new ArrayBuffer object.</span></span>  
  
## <span data-ttu-id="ef3bb-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ef3bb-109">Return Value</span></span>  
 <span data-ttu-id="ef3bb-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ef3bb-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ef3bb-111">注釈</span><span class="sxs-lookup"><span data-stu-id="ef3bb-111">Remarks</span></span>  
 <span data-ttu-id="ef3bb-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ef3bb-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="ef3bb-113">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ef3bb-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="ef3bb-114">要件</span><span class="sxs-lookup"><span data-stu-id="ef3bb-114">Requirements</span></span>  
 <span data-ttu-id="ef3bb-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ef3bb-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ef3bb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef3bb-116">See Also</span></span>  
 [<span data-ttu-id="ef3bb-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ef3bb-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
