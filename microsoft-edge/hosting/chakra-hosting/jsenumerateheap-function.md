---
description: 現在のコンテキストのヒープを列挙します。
title: JsEnumerateHeap 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEnumerateHeap
helpviewer_keywords:
- JsEnumerateHeap function
ms.assetid: 3e518e0b-b959-4686-899c-83e6b1946c9d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f1c2590388fcc09b641e3908d45eef7271bcb1ad
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570473"
---
# <span data-ttu-id="c2489-103">JsEnumerateHeap 関数</span><span class="sxs-lookup"><span data-stu-id="c2489-103">JsEnumerateHeap Function</span></span>
<span data-ttu-id="c2489-104">現在のコンテキストのヒープを列挙します。</span><span class="sxs-lookup"><span data-stu-id="c2489-104">Enumerates the heap of the current context.</span></span>  
  
## <span data-ttu-id="c2489-105">構文</span><span class="sxs-lookup"><span data-stu-id="c2489-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEnumerateHeap(  
   _Out_ IActiveScriptProfilerHeapEnum **enumerator  
);  
```  
  
#### <span data-ttu-id="c2489-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2489-106">Parameters</span></span>  
 `enumerator`  
 <span data-ttu-id="c2489-107">ヒープ列挙子。</span><span class="sxs-lookup"><span data-stu-id="c2489-107">The heap enumerator.</span></span>  
  
## <span data-ttu-id="c2489-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c2489-108">Return Value</span></span>  
 <span data-ttu-id="c2489-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="c2489-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c2489-110">注釈</span><span class="sxs-lookup"><span data-stu-id="c2489-110">Remarks</span></span>  
 <span data-ttu-id="c2489-111">ヒープが列挙されている間、現在のコンテキストを削除することはできません。コンテキストの状態を変更するすべての呼び出しは、ヒープ列挙子が解放されるまで失敗します。</span><span class="sxs-lookup"><span data-stu-id="c2489-111">While the heap is being enumerated, the current context cannot be removed, and all calls to modify the state of the context will fail until the heap enumerator is released.</span></span>  
  
 <span data-ttu-id="c2489-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2489-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="c2489-113">この API はデスクトップアプリでサポートされますが、ストアアプリではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c2489-113">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="c2489-114">要件</span><span class="sxs-lookup"><span data-stu-id="c2489-114">Requirements</span></span>  
 <span data-ttu-id="c2489-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="c2489-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c2489-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2489-116">See Also</span></span>  
 [<span data-ttu-id="c2489-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="c2489-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)