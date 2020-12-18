---
description: 渡されたメソッドを `VARIANT` JavaScript 値のプロジェクションとして初期化します。
title: JsValueToVariant 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f383f2d8bc3aab70b4a361b370698cd71cb714d3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234678"
---
# <span data-ttu-id="3cd02-103">JsValueToVariant 関数</span><span class="sxs-lookup"><span data-stu-id="3cd02-103">JsValueToVariant Function</span></span>

<span data-ttu-id="3cd02-104">渡されたメソッドを `VARIANT` JavaScript 値のプロジェクションとして初期化します。</span><span class="sxs-lookup"><span data-stu-id="3cd02-104">Initializes the passed in `VARIANT` as a projection of a JavaScript value.</span></span>  
  
## <span data-ttu-id="3cd02-105">構文</span><span class="sxs-lookup"><span data-stu-id="3cd02-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### <span data-ttu-id="3cd02-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3cd02-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="3cd02-107">A JavaScript value to project as a `VARIANT` .</span><span class="sxs-lookup"><span data-stu-id="3cd02-107">A JavaScript value to project as a `VARIANT`.</span></span>  
  
 `variant`  
 <span data-ttu-id="3cd02-108">プロジェクションとして初期化 `VARIANT` される構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3cd02-108">A pointer to a `VARIANT` struct that will be initialized as a projection.</span></span>  
  
## <span data-ttu-id="3cd02-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="3cd02-109">Return Value</span></span>  
  
## <span data-ttu-id="3cd02-110">注釈</span><span class="sxs-lookup"><span data-stu-id="3cd02-110">Remarks</span></span>  
 <span data-ttu-id="3cd02-111">プロジェクションは `VARIANT` 、COM オートメーション クライアントが投影された JavaScript オブジェクトを呼び出す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cd02-111">The projection `VARIANT` can be used by COM automation clients to call into the projected JavaScript object.</span></span>  
  
 <span data-ttu-id="3cd02-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="3cd02-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="3cd02-113">要件</span><span class="sxs-lookup"><span data-stu-id="3cd02-113">Requirements</span></span>  
 <span data-ttu-id="3cd02-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="3cd02-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3cd02-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cd02-115">See Also</span></span>  
 [<span data-ttu-id="3cd02-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="3cd02-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
