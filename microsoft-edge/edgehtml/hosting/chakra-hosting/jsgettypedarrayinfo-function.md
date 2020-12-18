---
description: 型指定された配列のよく使用されるプロパティを取得します。
title: JsGetTypedArrayInfo 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 992bc4e9-3d06-4ad2-8b6b-88a437360f81
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fdc9a05a2aebdabfd0c8e95c848d3bd5f97e580a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234893"
---
# <span data-ttu-id="124cd-103">JsGetTypedArrayInfo 関数</span><span class="sxs-lookup"><span data-stu-id="124cd-103">JsGetTypedArrayInfo Function</span></span>

<span data-ttu-id="124cd-104">型指定された配列のよく使用されるプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="124cd-104">Obtains frequently used properties of a typed array.</span></span>  
  
## <span data-ttu-id="124cd-105">構文</span><span class="sxs-lookup"><span data-stu-id="124cd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayInfo(  
  _In_ JsValueRef typedArray,  
  _Out_opt_ JsTypedArrayType *arrayType,  
  _Out_opt_ JsValueRef *arrayBuffer,  
  _Out_opt_ unsigned int *byteOffset,  
  _Out_opt_ unsigned int *byteLength  
);  
  
```  
  
#### <span data-ttu-id="124cd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="124cd-106">Parameters</span></span>  
 `typedArray`  
 <span data-ttu-id="124cd-107">型指定された配列インスタンス。</span><span class="sxs-lookup"><span data-stu-id="124cd-107">The typed array instance.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="124cd-108">配列の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="124cd-108">The type of the array.</span></span>  
  
 `arrayBuffer`  
 <span data-ttu-id="124cd-109">配列 `ArrayBuffer` のバックストア。</span><span class="sxs-lookup"><span data-stu-id="124cd-109">The `ArrayBuffer` backstore of the array.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="124cd-110">配列によって参照される arrayBuffer の開始からのオフセット (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="124cd-110">The offset in bytes from the start of arrayBuffer referenced by the array.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="124cd-111">配列内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="124cd-111">The number of bytes in the array.</span></span>  
  
## <span data-ttu-id="124cd-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="124cd-112">Return Value</span></span>  
 <span data-ttu-id="124cd-113">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="124cd-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="124cd-114">注釈</span><span class="sxs-lookup"><span data-stu-id="124cd-114">Remarks</span></span>  
 <span data-ttu-id="124cd-115">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="124cd-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="124cd-116">要件</span><span class="sxs-lookup"><span data-stu-id="124cd-116">Requirements</span></span>  
 <span data-ttu-id="124cd-117">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="124cd-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="124cd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="124cd-118">See Also</span></span>  
 [<span data-ttu-id="124cd-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="124cd-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
