---
description: 型指定された配列で使用される基になるメモリ 記憶域を取得します。
title: JsGetTypedArrayStorage 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 442727228433368de14bac528ea416fcc2a95fa8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234390"
---
# <span data-ttu-id="bebc7-103">JsGetTypedArrayStorage 関数</span><span class="sxs-lookup"><span data-stu-id="bebc7-103">JsGetTypedArrayStorage Function</span></span>

<span data-ttu-id="bebc7-104">型指定された配列で使用される基になるメモリ 記憶域を取得します。</span><span class="sxs-lookup"><span data-stu-id="bebc7-104">Obtains the underlying memory storage used by a typed array.</span></span>  
  
## <span data-ttu-id="bebc7-105">構文</span><span class="sxs-lookup"><span data-stu-id="bebc7-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayStorage(  
   _In_ JsValueRef typedArray,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength,  
   _Out_opt_ JsTypedArrayType *arrayType,  
   _Out_opt_ int *elementSize  
);  
```  
  
#### <span data-ttu-id="bebc7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bebc7-106">Parameters</span></span>  
 `typedArray`  
 <span data-ttu-id="bebc7-107">型指定された配列インスタンス。</span><span class="sxs-lookup"><span data-stu-id="bebc7-107">The typed array instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="bebc7-108">配列のバッファー。</span><span class="sxs-lookup"><span data-stu-id="bebc7-108">The array's buffer.</span></span> <span data-ttu-id="bebc7-109">返されるバッファーの有効期間は、配列の有効期間と同じです。</span><span class="sxs-lookup"><span data-stu-id="bebc7-109">The lifetime of the buffer returned is the same as the lifetime of the array.</span></span> <span data-ttu-id="bebc7-110">バッファー ポインターは、ガベージ コレクションのために配列への参照としてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="bebc7-110">The buffer pointer does not count as a reference to the array for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="bebc7-111">バッファー内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="bebc7-111">The number of bytes in the buffer.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="bebc7-112">配列の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="bebc7-112">The type of the array.</span></span>  
  
 `elementSize`  
 <span data-ttu-id="bebc7-113">配列の要素のサイズ。</span><span class="sxs-lookup"><span data-stu-id="bebc7-113">The size of an element of the array.</span></span>  
  
## <span data-ttu-id="bebc7-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="bebc7-114">Return Value</span></span>  
 <span data-ttu-id="bebc7-115">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bebc7-115">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bebc7-116">注釈</span><span class="sxs-lookup"><span data-stu-id="bebc7-116">Remarks</span></span>  
 <span data-ttu-id="bebc7-117">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="bebc7-117">Requires an active script context.</span></span>  
  
 <span data-ttu-id="bebc7-118">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bebc7-118">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="bebc7-119">要件</span><span class="sxs-lookup"><span data-stu-id="bebc7-119">Requirements</span></span>  
 <span data-ttu-id="bebc7-120">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bebc7-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bebc7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="bebc7-121">See Also</span></span>  
 [<span data-ttu-id="bebc7-122">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="bebc7-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
