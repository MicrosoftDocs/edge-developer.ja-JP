---
description: DataView で使用される基になるメモリ ストレージを取得します。
title: JsGetDataViewStorage 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 7c2180e0-51d5-4cc8-ad21-8bf29ff7c583
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 55f357e4a94b1edbc417ebb14ab99db11083dff4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234774"
---
# <span data-ttu-id="cf03f-103">JsGetDataViewStorage 関数</span><span class="sxs-lookup"><span data-stu-id="cf03f-103">JsGetDataViewStorage Function</span></span>

<span data-ttu-id="cf03f-104">で使用される基になるメモリ 記憶域を取得します `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="cf03f-104">Obtains the underlying memory storage used by a `DataView`.</span></span>  
  
## <span data-ttu-id="cf03f-105">構文</span><span class="sxs-lookup"><span data-stu-id="cf03f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetDataViewStorage(  
   _In_ JsValueRef dataView,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <span data-ttu-id="cf03f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf03f-106">Parameters</span></span>  
 `dataView`  
 <span data-ttu-id="cf03f-107">DataView インスタンス。</span><span class="sxs-lookup"><span data-stu-id="cf03f-107">The DataView instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="cf03f-108">DataView のバッファー。</span><span class="sxs-lookup"><span data-stu-id="cf03f-108">The DataView's buffer.</span></span> <span data-ttu-id="cf03f-109">返されるバッファーの有効期間は、 `DataView`</span><span class="sxs-lookup"><span data-stu-id="cf03f-109">The lifetime of the buffer returned is the same as the lifetime of the `DataView`.</span></span> <span data-ttu-id="cf03f-110">バッファー ポインターは、ガベージ コレクションのために参照 `DataView` としてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="cf03f-110">The buffer pointer does not count as a reference to the `DataView` for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="cf03f-111">バッファー内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="cf03f-111">The number of bytes in the buffer.</span></span>  
  
## <span data-ttu-id="cf03f-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="cf03f-112">Return Value</span></span>  
 <span data-ttu-id="cf03f-113">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="cf03f-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="cf03f-114">注釈</span><span class="sxs-lookup"><span data-stu-id="cf03f-114">Remarks</span></span>  
 <span data-ttu-id="cf03f-115">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="cf03f-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="cf03f-116">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cf03f-116">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="cf03f-117">要件</span><span class="sxs-lookup"><span data-stu-id="cf03f-117">Requirements</span></span>  
 <span data-ttu-id="cf03f-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="cf03f-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="cf03f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf03f-119">See Also</span></span>  
 [<span data-ttu-id="cf03f-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="cf03f-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
