---
description: 現在のコンテキストのヒープが列挙されているかどうかを示す値を返します。
title: JsIsEnumeratingHeap 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIsEnumeratingHeap
helpviewer_keywords:
- JsIsEnumeratingHeap function
ms.assetid: 5d14518e-3153-43f2-9a9c-068580cbd54f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5b66fc70ea79d78029f6bc0c900ade1aae38e604
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234901"
---
# <span data-ttu-id="ea395-103">JsIsEnumeratingHeap 関数</span><span class="sxs-lookup"><span data-stu-id="ea395-103">JsIsEnumeratingHeap Function</span></span>

<span data-ttu-id="ea395-104">現在のコンテキストのヒープが列挙されているかどうかを示す値を返します。</span><span class="sxs-lookup"><span data-stu-id="ea395-104">Returns a value that indicates whether the heap of the current context is being enumerated.</span></span>  
  
## <span data-ttu-id="ea395-105">構文</span><span class="sxs-lookup"><span data-stu-id="ea395-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIsEnumeratingHeap(  
   _Out_ bool *isEnumeratingHeap  
);  
```  
  
#### <span data-ttu-id="ea395-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea395-106">Parameters</span></span>  
 `isEnumeratingHeap`  
 <span data-ttu-id="ea395-107">ヒープが列挙されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea395-107">Whether the heap is being enumerated.</span></span>  
  
## <span data-ttu-id="ea395-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ea395-108">Return Value</span></span>  
 <span data-ttu-id="ea395-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ea395-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ea395-110">注釈</span><span class="sxs-lookup"><span data-stu-id="ea395-110">Remarks</span></span>  
 <span data-ttu-id="ea395-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea395-111">Requires an active script context.</span></span>  
  
 <span data-ttu-id="ea395-112">この API はデスクトップ アプリでサポートされますが、ストア アプリではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ea395-112">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="ea395-113">要件</span><span class="sxs-lookup"><span data-stu-id="ea395-113">Requirements</span></span>  
 <span data-ttu-id="ea395-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ea395-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ea395-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea395-115">See Also</span></span>  
 [<span data-ttu-id="ea395-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ea395-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
