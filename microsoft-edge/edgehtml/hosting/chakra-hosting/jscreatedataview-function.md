---
description: Javascript オブジェクトを作成 `DataView` します。
title: JsCreateDataView 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1d6d170d53f3bfaf885713b6f3abca0b066f8c1d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234524"
---
# <span data-ttu-id="d161c-103">JsCreateDataView 関数</span><span class="sxs-lookup"><span data-stu-id="d161c-103">JsCreateDataView Function</span></span>

<span data-ttu-id="d161c-104">Javascript オブジェクトを作成 `DataView` します。</span><span class="sxs-lookup"><span data-stu-id="d161c-104">Creates a Javascript `DataView` object.</span></span>  
  
## <span data-ttu-id="d161c-105">構文</span><span class="sxs-lookup"><span data-stu-id="d161c-105">Syntax</span></span>  
  
```cpp  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="d161c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d161c-106">Parameters</span></span>  
 `arrayBuffer`  
 <span data-ttu-id="d161c-107">結果オブジェクト `ArrayBuffer` のストレージとして使用する既存の `DataView` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d161c-107">An existing `ArrayBuffer` object to use as the storage for the result `DataView` object.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="d161c-108">結果の開始から参照への `arrayBuffer` オフセットをバイト `DataView` 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="d161c-108">The offset in bytes from the start of `arrayBuffer` for result `DataView` to reference.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="d161c-109">結果 DataView が参照する ArrayBuffer のバイト数。</span><span class="sxs-lookup"><span data-stu-id="d161c-109">The number of bytes in the ArrayBuffer for result DataView to reference.</span></span>  
  
 `result`  
 <span data-ttu-id="d161c-110">新しい DataView オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d161c-110">The new DataView object.</span></span>  
  
## <span data-ttu-id="d161c-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="d161c-111">Return Value</span></span>  
 <span data-ttu-id="d161c-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="d161c-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d161c-113">注釈</span><span class="sxs-lookup"><span data-stu-id="d161c-113">Remarks</span></span>  
 <span data-ttu-id="d161c-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="d161c-114">Requires an active script context.</span></span>  
  
 <span data-ttu-id="d161c-115">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d161c-115">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="d161c-116">要件</span><span class="sxs-lookup"><span data-stu-id="d161c-116">Requirements</span></span>  
 <span data-ttu-id="d161c-117">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d161c-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d161c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d161c-118">See Also</span></span>  
 [<span data-ttu-id="d161c-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="d161c-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
