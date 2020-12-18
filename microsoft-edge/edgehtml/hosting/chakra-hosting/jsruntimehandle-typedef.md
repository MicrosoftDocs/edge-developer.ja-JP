---
description: チャクラ ランタイムへのハンドル。
title: JsRuntimeHandle Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ab08243505b9699fe07ca2e80f7294adf9eb78ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234511"
---
# <span data-ttu-id="55cd6-103">JsRuntimeHandle Typedef</span><span class="sxs-lookup"><span data-stu-id="55cd6-103">JsRuntimeHandle Typedef</span></span>

<span data-ttu-id="55cd6-104">チャクラ ランタイムへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="55cd6-104">A handle to a Chakra runtime.</span></span>  
  
## <span data-ttu-id="55cd6-105">構文</span><span class="sxs-lookup"><span data-stu-id="55cd6-105">Syntax</span></span>  
  
```cpp  
typedef void *JsRuntimeHandle;  
```  
  
## <span data-ttu-id="55cd6-106">注釈</span><span class="sxs-lookup"><span data-stu-id="55cd6-106">Remarks</span></span>  
 <span data-ttu-id="55cd6-107">各 Chakra ランタイムには、独自の独立した実行エンジン、JIT コンパイラ、ガベージ コレクションヒープがあります。</span><span class="sxs-lookup"><span data-stu-id="55cd6-107">Each Chakra runtime has its own independent execution engine, JIT compiler, and garbage collected heap.</span></span> <span data-ttu-id="55cd6-108">そのため、各ランタイムは他のランタイムから完全に分離されます。</span><span class="sxs-lookup"><span data-stu-id="55cd6-108">As such, each runtime is completely isolated from other runtimes.</span></span>  
  
 <span data-ttu-id="55cd6-109">ランタイムは任意のスレッドで使用できますが、実行時に呼び出しできるのは 1 つのスレッドのみです。</span><span class="sxs-lookup"><span data-stu-id="55cd6-109">Runtimes can be used on any thread, but only one thread can call into a runtime at any time.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="55cd6-110">JsRuntimeHandle は、Chakra ホスティング API の他のオブジェクト参照とは異なり、ガベージ コレクションヒープ自体が含まれているので、ガベージ コレクションされません。</span><span class="sxs-lookup"><span data-stu-id="55cd6-110">A JsRuntimeHandle, unlike other object references in the Chakra hosting API, is not garbage collected since it contains the garbage collected heap itself.</span></span> <span data-ttu-id="55cd6-111">JsDisposeRuntime が呼び出されるまで、ランタイムは引き続き存在します。</span><span class="sxs-lookup"><span data-stu-id="55cd6-111">A runtime will continue to exist until JsDisposeRuntime is called.</span></span>  
  
## <span data-ttu-id="55cd6-112">要件</span><span class="sxs-lookup"><span data-stu-id="55cd6-112">Requirements</span></span>  
 <span data-ttu-id="55cd6-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="55cd6-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="55cd6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="55cd6-114">See Also</span></span>  
 [<span data-ttu-id="55cd6-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="55cd6-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
