---
description: スクリプト コンテキストへの参照。
title: JsContextRef Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c8a8fcbd67afb150d682cfc19321f0f13acfe3a6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234547"
---
# <span data-ttu-id="49943-103">JsContextRef Typedef</span><span class="sxs-lookup"><span data-stu-id="49943-103">JsContextRef Typedef</span></span>

<span data-ttu-id="49943-104">スクリプト コンテキストへの参照。</span><span class="sxs-lookup"><span data-stu-id="49943-104">A reference to a script context.</span></span>  
  
## <span data-ttu-id="49943-105">構文</span><span class="sxs-lookup"><span data-stu-id="49943-105">Syntax</span></span>  
  
```cpp  
typedef JsRef JsContextRef;  
```  
  
## <span data-ttu-id="49943-106">注釈</span><span class="sxs-lookup"><span data-stu-id="49943-106">Remarks</span></span>  
 <span data-ttu-id="49943-107">各スクリプト コンテキストには、他のスクリプト コンテキストのグローバル オブジェクトとは異なる、独自のグローバル オブジェクトが含まれる。</span><span class="sxs-lookup"><span data-stu-id="49943-107">Each script context contains its own global object, distinct from the global object in other script contexts.</span></span>  
  
 <span data-ttu-id="49943-108">多くの Chakra ホスティング API には、使用して設定できる "アクティブな" スクリプト コンテキストが必要です `JsSetCurrentContext` 。</span><span class="sxs-lookup"><span data-stu-id="49943-108">Many Chakra hosting APIs require an "active" script context, which can be set using `JsSetCurrentContext`.</span></span> <span data-ttu-id="49943-109">現在のコンテキストを設定する必要がある、Chakra ホスティング API は、ドキュメント内で明示的に注意してください。</span><span class="sxs-lookup"><span data-stu-id="49943-109">Chakra hosting APIs that require a current context to be set will note that explicitly in their documentation.</span></span>  
  
## <span data-ttu-id="49943-110">要件</span><span class="sxs-lookup"><span data-stu-id="49943-110">Requirements</span></span>  
 <span data-ttu-id="49943-111">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="49943-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="49943-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="49943-112">See Also</span></span>  
 [<span data-ttu-id="49943-113">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="49943-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
