---
description: 型付き配列のよく使われるプロパティを取得します。
title: JsGetTypedArrayInfo 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 992bc4e9-3d06-4ad2-8b6b-88a437360f81
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 24046acc7118cd8f540ba8ceb9976368e93d51ff
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752270"
---
# <span data-ttu-id="f6a6b-103">JsGetTypedArrayInfo 関数</span><span class="sxs-lookup"><span data-stu-id="f6a6b-103">JsGetTypedArrayInfo Function</span></span>
<span data-ttu-id="f6a6b-104">型付き配列のよく使われるプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="f6a6b-104">Obtains frequently used properties of a typed array.</span></span>  
  
## <span data-ttu-id="f6a6b-105">構文</span><span class="sxs-lookup"><span data-stu-id="f6a6b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayInfo(  
  _In_ JsValueRef typedArray,  
  _Out_opt_ JsTypedArrayType *arrayType,  
  _Out_opt_ JsValueRef *arrayBuffer,  
  _Out_opt_ unsigned int *byteOffset,  
  _Out_opt_ unsigned int *byteLength  
);  
  
```  
  
#### <span data-ttu-id="f6a6b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6a6b-106">Parameters</span></span>  
 `typedArray`  
 <span data-ttu-id="f6a6b-107">型付き配列インスタンス。</span><span class="sxs-lookup"><span data-stu-id="f6a6b-107">The typed array instance.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="f6a6b-108">配列の型。</span><span class="sxs-lookup"><span data-stu-id="f6a6b-108">The type of the array.</span></span>  
  
 `arrayBuffer`  
 <span data-ttu-id="f6a6b-109">`ArrayBuffer`配列の backstore。</span><span class="sxs-lookup"><span data-stu-id="f6a6b-109">The `ArrayBuffer` backstore of the array.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="f6a6b-110">配列で参照される arrayBuffer の先頭からのオフセット (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="f6a6b-110">The offset in bytes from the start of arrayBuffer referenced by the array.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="f6a6b-111">配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="f6a6b-111">The number of bytes in the array.</span></span>  
  
## <span data-ttu-id="f6a6b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6a6b-112">Return Value</span></span>  
 <span data-ttu-id="f6a6b-113">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="f6a6b-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f6a6b-114">注釈</span><span class="sxs-lookup"><span data-stu-id="f6a6b-114">Remarks</span></span>  
 <span data-ttu-id="f6a6b-115">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f6a6b-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f6a6b-116">要件</span><span class="sxs-lookup"><span data-stu-id="f6a6b-116">Requirements</span></span>  
 <span data-ttu-id="f6a6b-117">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="f6a6b-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f6a6b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6a6b-118">See Also</span></span>  
 [<span data-ttu-id="f6a6b-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f6a6b-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)