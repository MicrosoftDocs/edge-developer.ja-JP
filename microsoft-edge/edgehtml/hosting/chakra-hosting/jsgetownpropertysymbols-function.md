---
description: オブジェクトのすべてのシンボル プロパティのリストを取得します。
title: JsGetOwnPropertySymbols 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 57c431e3-de0b-4ed0-b750-87a86448daff
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d44da140f61a17d4cdc3a959c8fa7d017cbab1cc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234894"
---
# <span data-ttu-id="92239-103">JsGetOwnPropertySymbols 関数</span><span class="sxs-lookup"><span data-stu-id="92239-103">JsGetOwnPropertySymbols Function</span></span>

<span data-ttu-id="92239-104">オブジェクトのすべてのシンボル プロパティのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="92239-104">Gets the list of all symbol properties on the object.</span></span>  
  
## <span data-ttu-id="92239-105">構文</span><span class="sxs-lookup"><span data-stu-id="92239-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertySymbols(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertySymbols  
);  
```  
  
#### <span data-ttu-id="92239-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92239-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="92239-107">プロパティ シンボルを取得するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="92239-107">The object from which to get the property symbols.</span></span>  
  
 `propertySymbols`  
 <span data-ttu-id="92239-108">プロパティ 記号の配列。</span><span class="sxs-lookup"><span data-stu-id="92239-108">An array of property symbols.</span></span>  
  
## <span data-ttu-id="92239-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="92239-109">Return Value</span></span>  
 <span data-ttu-id="92239-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="92239-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="92239-111">注釈</span><span class="sxs-lookup"><span data-stu-id="92239-111">Remarks</span></span>  
 <span data-ttu-id="92239-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="92239-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="92239-113">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="92239-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="92239-114">要件</span><span class="sxs-lookup"><span data-stu-id="92239-114">Requirements</span></span>  
 <span data-ttu-id="92239-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="92239-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="92239-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="92239-116">See Also</span></span>  
 [<span data-ttu-id="92239-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="92239-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
