---
description: Chakra ランタイムへのハンドル。
title: JsRuntimeHandle Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4ccdcf39ec6062db47e1b9de249d75c8804de405
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570390"
---
# <span data-ttu-id="dfb1e-103">JsRuntimeHandle Typedef</span><span class="sxs-lookup"><span data-stu-id="dfb1e-103">JsRuntimeHandle Typedef</span></span>
<span data-ttu-id="dfb1e-104">Chakra ランタイムへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="dfb1e-104">A handle to a Chakra runtime.</span></span>  
  
## <span data-ttu-id="dfb1e-105">構文</span><span class="sxs-lookup"><span data-stu-id="dfb1e-105">Syntax</span></span>  
  
```cpp  
typedef void *JsRuntimeHandle;  
```  
  
## <span data-ttu-id="dfb1e-106">注釈</span><span class="sxs-lookup"><span data-stu-id="dfb1e-106">Remarks</span></span>  
 <span data-ttu-id="dfb1e-107">各 Chakra ランタイムには、独自の独立した実行エンジン、JIT コンパイラ、およびガベージコレクションヒープがあります。</span><span class="sxs-lookup"><span data-stu-id="dfb1e-107">Each Chakra runtime has its own independent execution engine, JIT compiler, and garbage collected heap.</span></span> <span data-ttu-id="dfb1e-108">このように、各ランタイムは、他のランタイムから完全に分離されます。</span><span class="sxs-lookup"><span data-stu-id="dfb1e-108">As such, each runtime is completely isolated from other runtimes.</span></span>  
  
 <span data-ttu-id="dfb1e-109">ランタイムはどのスレッドでも使うことができますが、ランタイムをいつでも呼び出すことができるスレッドは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="dfb1e-109">Runtimes can be used on any thread, but only one thread can call into a runtime at any time.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="dfb1e-110">JsRuntimeHandle は、Chakra ホスティング API の他のオブジェクト参照とは異なり、ガベージコレクションされたヒープ自体が含まれているため、ガベージコレクションされません。</span><span class="sxs-lookup"><span data-stu-id="dfb1e-110">A JsRuntimeHandle, unlike other object references in the Chakra hosting API, is not garbage collected since it contains the garbage collected heap itself.</span></span> <span data-ttu-id="dfb1e-111">JsDisposeRuntime が呼び出されるまで、ランタイムは引き続き存在します。</span><span class="sxs-lookup"><span data-stu-id="dfb1e-111">A runtime will continue to exist until JsDisposeRuntime is called.</span></span>  
  
## <span data-ttu-id="dfb1e-112">要件</span><span class="sxs-lookup"><span data-stu-id="dfb1e-112">Requirements</span></span>  
 <span data-ttu-id="dfb1e-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="dfb1e-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="dfb1e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfb1e-114">See Also</span></span>  
 [<span data-ttu-id="dfb1e-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="dfb1e-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)