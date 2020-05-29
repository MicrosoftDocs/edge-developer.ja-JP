---
description: 型指定された配列によって使用される、基になるメモリ記憶域を取得します。
title: JsGetTypedArrayStorage 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f03414d64fa819ac464217c8362d02e866d45296
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570444"
---
# <span data-ttu-id="9336e-103">JsGetTypedArrayStorage 関数</span><span class="sxs-lookup"><span data-stu-id="9336e-103">JsGetTypedArrayStorage Function</span></span>
<span data-ttu-id="9336e-104">型指定された配列によって使用される、基になるメモリ記憶域を取得します。</span><span class="sxs-lookup"><span data-stu-id="9336e-104">Obtains the underlying memory storage used by a typed array.</span></span>  
  
## <span data-ttu-id="9336e-105">構文</span><span class="sxs-lookup"><span data-stu-id="9336e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayStorage(  
   _In_ JsValueRef typedArray,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength,  
   _Out_opt_ JsTypedArrayType *arrayType,  
   _Out_opt_ int *elementSize  
);  
```  
  
#### <span data-ttu-id="9336e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9336e-106">Parameters</span></span>  
 `typedArray`  
 <span data-ttu-id="9336e-107">型付き配列インスタンス。</span><span class="sxs-lookup"><span data-stu-id="9336e-107">The typed array instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9336e-108">配列のバッファー。</span><span class="sxs-lookup"><span data-stu-id="9336e-108">The array's buffer.</span></span> <span data-ttu-id="9336e-109">返されるバッファーの有効期間は、配列の有効期間と同じです。</span><span class="sxs-lookup"><span data-stu-id="9336e-109">The lifetime of the buffer returned is the same as the lifetime of the array.</span></span> <span data-ttu-id="9336e-110">バッファーポインターは、ガベージコレクションを目的として、配列への参照としてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="9336e-110">The buffer pointer does not count as a reference to the array for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="9336e-111">バッファーのバイト数。</span><span class="sxs-lookup"><span data-stu-id="9336e-111">The number of bytes in the buffer.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="9336e-112">配列の型。</span><span class="sxs-lookup"><span data-stu-id="9336e-112">The type of the array.</span></span>  
  
 `elementSize`  
 <span data-ttu-id="9336e-113">配列の要素のサイズ。</span><span class="sxs-lookup"><span data-stu-id="9336e-113">The size of an element of the array.</span></span>  
  
## <span data-ttu-id="9336e-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="9336e-114">Return Value</span></span>  
 <span data-ttu-id="9336e-115">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="9336e-115">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9336e-116">注釈</span><span class="sxs-lookup"><span data-stu-id="9336e-116">Remarks</span></span>  
 <span data-ttu-id="9336e-117">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="9336e-117">Requires an active script context.</span></span>  
  
 <span data-ttu-id="9336e-118">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9336e-118">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="9336e-119">要件</span><span class="sxs-lookup"><span data-stu-id="9336e-119">Requirements</span></span>  
 <span data-ttu-id="9336e-120">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="9336e-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9336e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9336e-121">See Also</span></span>  
 [<span data-ttu-id="9336e-122">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9336e-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)