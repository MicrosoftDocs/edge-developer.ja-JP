---
description: 現在のコンテキストのヒープを列挙します。
title: JsEnumerateHeap 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsEnumerateHeap
helpviewer_keywords:
- JsEnumerateHeap function
ms.assetid: 3e518e0b-b959-4686-899c-83e6b1946c9d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bb76b28f24b769f71827e59be691188e34e9e1a3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234875"
---
# <span data-ttu-id="948f1-103">JsEnumerateHeap 関数</span><span class="sxs-lookup"><span data-stu-id="948f1-103">JsEnumerateHeap Function</span></span>

<span data-ttu-id="948f1-104">現在のコンテキストのヒープを列挙します。</span><span class="sxs-lookup"><span data-stu-id="948f1-104">Enumerates the heap of the current context.</span></span>  
  
## <span data-ttu-id="948f1-105">構文</span><span class="sxs-lookup"><span data-stu-id="948f1-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEnumerateHeap(  
   _Out_ IActiveScriptProfilerHeapEnum **enumerator  
);  
```  
  
#### <span data-ttu-id="948f1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="948f1-106">Parameters</span></span>  
 `enumerator`  
 <span data-ttu-id="948f1-107">ヒープ列挙子。</span><span class="sxs-lookup"><span data-stu-id="948f1-107">The heap enumerator.</span></span>  
  
## <span data-ttu-id="948f1-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="948f1-108">Return Value</span></span>  
 <span data-ttu-id="948f1-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="948f1-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="948f1-110">注釈</span><span class="sxs-lookup"><span data-stu-id="948f1-110">Remarks</span></span>  
 <span data-ttu-id="948f1-111">ヒープの列挙中は現在のコンテキストを削除できません。また、ヒープ列挙子が解放されるまで、コンテキストの状態を変更する呼び出しはすべて失敗します。</span><span class="sxs-lookup"><span data-stu-id="948f1-111">While the heap is being enumerated, the current context cannot be removed, and all calls to modify the state of the context will fail until the heap enumerator is released.</span></span>  
  
 <span data-ttu-id="948f1-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="948f1-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="948f1-113">この API はデスクトップ アプリでサポートされますが、ストア アプリではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="948f1-113">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="948f1-114">要件</span><span class="sxs-lookup"><span data-stu-id="948f1-114">Requirements</span></span>  
 <span data-ttu-id="948f1-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="948f1-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="948f1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="948f1-116">See Also</span></span>  
 [<span data-ttu-id="948f1-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="948f1-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
