---
description: ArrayBuffer で使用される基になるメモリ 記憶域を取得します。
title: JsGetArrayBufferStorage 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 64b031a81506e68322759eff49da7467cac6f219
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234653"
---
# <span data-ttu-id="73975-103">JsGetArrayBufferStorage 関数</span><span class="sxs-lookup"><span data-stu-id="73975-103">JsGetArrayBufferStorage Function</span></span>

<span data-ttu-id="73975-104">で使用される基になるメモリ 記憶域を取得します `ArrayBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="73975-104">Obtains the underlying memory storage used by an `ArrayBuffer`.</span></span>  
  
## <span data-ttu-id="73975-105">構文</span><span class="sxs-lookup"><span data-stu-id="73975-105">Syntax</span></span>  
  
```cpp  
JsErrorCode STDAPI_ JsGetArrayBufferStorage(  
   _In_ JsValueRef arrayBuffer,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <span data-ttu-id="73975-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73975-106">Parameters</span></span>  
 `arrayBuffer`  
 <span data-ttu-id="73975-107">ArrayBuffer インスタンス。</span><span class="sxs-lookup"><span data-stu-id="73975-107">The ArrayBuffer instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="73975-108">ArrayBuffer のバッファー。</span><span class="sxs-lookup"><span data-stu-id="73975-108">The ArrayBuffer's buffer.</span></span> <span data-ttu-id="73975-109">返されるバッファーの有効期間は、 `ArrayBuffer`</span><span class="sxs-lookup"><span data-stu-id="73975-109">The lifetime of the buffer returned is the same as the lifetime of the `ArrayBuffer`.</span></span> <span data-ttu-id="73975-110">バッファー ポインターは、ガベージ コレクションのために参照 `ArrayBuffer` としてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="73975-110">The buffer pointer does not count as a reference to the `ArrayBuffer` for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="73975-111">バッファー内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="73975-111">The number of bytes in the buffer.</span></span>  
  
## <span data-ttu-id="73975-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="73975-112">Return Value</span></span>  
 <span data-ttu-id="73975-113">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="73975-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="73975-114">注釈</span><span class="sxs-lookup"><span data-stu-id="73975-114">Remarks</span></span>  
 <span data-ttu-id="73975-115">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="73975-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="73975-116">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73975-116">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="73975-117">要件</span><span class="sxs-lookup"><span data-stu-id="73975-117">Requirements</span></span>  
 <span data-ttu-id="73975-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="73975-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="73975-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="73975-119">See Also</span></span>  
 [<span data-ttu-id="73975-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="73975-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
