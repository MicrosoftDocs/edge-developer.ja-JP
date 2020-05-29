---
description: 配列バッファーによって使用される、基になるメモリ記憶域を取得します。
title: JsGetArrayBufferStorage 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e8d265f3e81015ba9f5d0547b6b1c7246c23ce5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570464"
---
# <span data-ttu-id="9d9b6-103">JsGetArrayBufferStorage 関数</span><span class="sxs-lookup"><span data-stu-id="9d9b6-103">JsGetArrayBufferStorage Function</span></span>
<span data-ttu-id="9d9b6-104">によって使用される、基になるメモリ記憶域を取得 `ArrayBuffer` します。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-104">Obtains the underlying memory storage used by an `ArrayBuffer`.</span></span>  
  
## <span data-ttu-id="9d9b6-105">構文</span><span class="sxs-lookup"><span data-stu-id="9d9b6-105">Syntax</span></span>  
  
```cpp  
JsErrorCode STDAPI_ JsGetArrayBufferStorage(  
   _In_ JsValueRef arrayBuffer,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <span data-ttu-id="9d9b6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d9b6-106">Parameters</span></span>  
 `arrayBuffer`  
 <span data-ttu-id="9d9b6-107">ArrayBuffer インスタンス。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-107">The ArrayBuffer instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9d9b6-108">ArrayBuffer のバッファー。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-108">The ArrayBuffer's buffer.</span></span> <span data-ttu-id="9d9b6-109">返されるバッファーの有効期間は、の有効期間と同じです `ArrayBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-109">The lifetime of the buffer returned is the same as the lifetime of the `ArrayBuffer`.</span></span> <span data-ttu-id="9d9b6-110">バッファーポインターは、 `ArrayBuffer` ガベージコレクションの目的で、への参照としてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-110">The buffer pointer does not count as a reference to the `ArrayBuffer` for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="9d9b6-111">バッファーのバイト数。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-111">The number of bytes in the buffer.</span></span>  
  
## <span data-ttu-id="9d9b6-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="9d9b6-112">Return Value</span></span>  
 <span data-ttu-id="9d9b6-113">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9d9b6-114">注釈</span><span class="sxs-lookup"><span data-stu-id="9d9b6-114">Remarks</span></span>  
 <span data-ttu-id="9d9b6-115">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="9d9b6-116">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9d9b6-116">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="9d9b6-117">要件</span><span class="sxs-lookup"><span data-stu-id="9d9b6-117">Requirements</span></span>  
 <span data-ttu-id="9d9b6-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="9d9b6-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9d9b6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d9b6-119">See Also</span></span>  
 [<span data-ttu-id="9d9b6-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9d9b6-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)