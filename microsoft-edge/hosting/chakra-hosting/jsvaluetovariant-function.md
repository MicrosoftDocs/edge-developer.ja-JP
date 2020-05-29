---
description: 渡された引数を `VARIANT` JavaScript 値のプロジェクションとして初期化します。
title: JsValueToVariant 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d8748fddcc149cf09fbd46ad3ad489cd66200b71
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569262"
---
# <span data-ttu-id="7df1c-103">JsValueToVariant 関数</span><span class="sxs-lookup"><span data-stu-id="7df1c-103">JsValueToVariant Function</span></span>
<span data-ttu-id="7df1c-104">渡された引数を `VARIANT` JavaScript 値のプロジェクションとして初期化します。</span><span class="sxs-lookup"><span data-stu-id="7df1c-104">Initializes the passed in `VARIANT` as a projection of a JavaScript value.</span></span>  
  
## <span data-ttu-id="7df1c-105">構文</span><span class="sxs-lookup"><span data-stu-id="7df1c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### <span data-ttu-id="7df1c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7df1c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="7df1c-107">プロジェクトの JavaScript 値 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="7df1c-107">A JavaScript value to project as a `VARIANT`.</span></span>  
  
 `variant`  
 <span data-ttu-id="7df1c-108">`VARIANT`プロジェクションとして初期化される構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7df1c-108">A pointer to a `VARIANT` struct that will be initialized as a projection.</span></span>  
  
## <span data-ttu-id="7df1c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7df1c-109">Return Value</span></span>  
  
## <span data-ttu-id="7df1c-110">注釈</span><span class="sxs-lookup"><span data-stu-id="7df1c-110">Remarks</span></span>  
 <span data-ttu-id="7df1c-111">プロジェクション `VARIANT` を COM オートメーションクライアントで使って、投影された JavaScript オブジェクトを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7df1c-111">The projection `VARIANT` can be used by COM automation clients to call into the projected JavaScript object.</span></span>  
  
 <span data-ttu-id="7df1c-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="7df1c-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="7df1c-113">要件</span><span class="sxs-lookup"><span data-stu-id="7df1c-113">Requirements</span></span>  
 <span data-ttu-id="7df1c-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="7df1c-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7df1c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7df1c-115">See Also</span></span>  
 [<span data-ttu-id="7df1c-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="7df1c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)